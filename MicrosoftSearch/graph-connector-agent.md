---
title: 本地代理
ms.author: rusamai
author: rsamai
manager: jameslau
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: On-prem Agent
ms.openlocfilehash: a17ad4637f7618a6f1109fb5de177c9a673a4fa6b791711e807107676749ccc5
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2021
ms.locfileid: "54534219"
---
# <a name="microsoft-graph-connector-agent"></a>Microsoft Graph 连接器代理

使用 On-prem 连接器需要安装 *Microsoft Graph连接器代理* 软件。 它允许在本地数据和连接器 API 之间安全数据传输。 本文将指导您完成代理的安装和配置。

## <a name="installation"></a>安装

从下载最新版本的 Graph 连接器代理，然后使用安装向导 [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) 安装软件。 使用下面介绍的推荐计算机配置，软件可以处理最多三个连接。 任何超过该范围的连接都可能会降低代理上所有连接的性能。

建议的配置：

* Windows 10、Windows Server 2016 R2 及以上
* [.NET Core Desktop Runtime 3.1 (x64) ](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 核，3 GHz
* 16 GB RAM，2 GB 磁盘空间
* 通过 443 对数据源和 Internet 的网络访问

安装代理后，如果组织的代理服务器或防火墙阻止与未知域的通信，请将以下这些域添加到允许列表中。

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>login.microsoftonline。</span>com
4. https://<span>gcs.office。</span>com/
5. https://<span>graph.microsoft。</span>com/


## <a name="create-and-configure-an-app-for-the-agent"></a>为代理创建和配置应用  

首先，登录并注意，帐户上所需的最低权限是搜索管理员。 然后，代理将要求您提供身份验证详细信息。 使用以下步骤创建应用并生成所需的身份验证详细信息。

### <a name="create-an-app"></a>创建应用

1. 转到 [Azure 门户，](https://portal.azure.com) 然后使用租户的管理员凭据登录。

2. 从导航 **Azure Active Directory**  ->  导航窗格中导航到"应用注册"，然后选择"新建 **注册"。**

3. 提供应用的名称，**然后选择注册。**

4. 记下应用程序客户端 (ID) ID。

5. 从 **导航窗格中打开 API** 权限，然后选择"**添加权限"。**

6. 选择 **"Microsoft Graph"，** 然后选择"**应用程序权限"。**

7. 从权限搜索"ExternalItem.ReadWrite.All"和"Directory.Read.All"，然后选择 **添加权限**。

8. 选择 **"授予 [TenantName]** 的管理员同意"，然后通过选择"是 **"确认**。

9. 检查权限是否位于"已授予"状态。

    :::image type="content" alt-text="右侧列显示为绿色授予的权限。" source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

### <a name="configure-authentication"></a>配置身份验证

可以使用客户端密码或证书提供身份验证详细信息。 按照你选择的步骤操作。

#### <a name="configuring-the-client-secret-for-authentication"></a>配置客户端密码进行身份验证

1. 转到 [Azure 门户，](https://portal.azure.com) 然后使用租户的管理员凭据登录。

2. 从 **导航窗格中** 打开应用注册，然后转到相应的应用。 在 **"管理"** 下，选择 **"证书和密码"。**

3. 选择 **"新建** 客户端密码"，然后选择密码的过期期限。 复制生成的密码并保存它，因为它不会再次显示。

4. 使用此客户端密码和应用程序 ID 配置代理。 您不能在代理的 **"名称"字段中** 使用空格。 接受字母数字字符。

#### <a name="using-a-certificate-for-authentication"></a>使用证书进行身份验证

使用基于证书的身份验证有三个简单的步骤：

1. 创建或获取证书
2. Upload证书到 Azure 门户
3. 将证书分配给代理

##### <a name="step-1-get-a-certificate"></a>步骤 1：获取证书

下面的脚本可用于生成自签名证书。 你的组织可能不允许自签名证书。 在这种情况下，请使用此信息了解要求，并根据组织策略获取证书。

```powershell
$dnsName = "<TenantDomain like agent.onmicrosoft.com>" # Your DNS name
$password = "<password>" # Certificate password
$folderPath = "D:\New folder\" # Where do you want the files to get saved to? The folder needs to exist.
$fileName = "agentcert" # What do you want to call the cert files? without the file extension
$yearsValid = 10 # Number of years until you need to renew the certificate
$certStoreLocation = "cert:\LocalMachine\My"
$expirationDate = (Get-Date).AddYears($yearsValid)
$certificate = New-SelfSignedCertificate -DnsName $dnsName -CertStoreLocation $certStoreLocation -NotAfter $expirationDate -KeyExportPolicy Exportable -KeySpec Signature
$certificatePath = $certStoreLocation + '\' + $certificate.Thumbprint
$filePath = $folderPath + '\' + $fileName
$securePassword = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-Certificate -Cert $certificatePath -FilePath ($filePath + '.cer')
Export-PfxCertificate -Cert $certificatePath -FilePath ($filePath + '.pfx') -Password $securePassword
```

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>步骤 2：Upload Azure 门户中的证书

1. 打开应用程序，然后从左窗格导航到"证书和机密"部分。

2. 选择 **Upload证书** 并上载 .cer 文件。

3. 打开 **应用注册** ，然后从导航 **窗格中选择** 证书和密码。 复制证书指纹。

:::image type="content" alt-text="在左窗格中选择证书和密码时指纹证书列表" source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>步骤 3：将证书分配给代理

如果使用示例脚本生成证书，可以在脚本中标识的位置找到 PFX 文件。

1. 将证书 pfx 文件下载到代理计算机上。

2. 双击 pfx 文件以启动证书安装对话框。

3. 在 **安装证书** 时，选择"本地计算机"作为存储位置。

4. 安装证书后，通过"管理 **计算机证书""开始"菜单。**

5. 选择"个人证书"下 **新安装的**  >  **证书**。

6. 右键单击证书，然后选择"**所有任务**  >  **管理私钥"** 选项。

7. 在"权限"对话框中，选择"添加"选项。 在用户选择对话框中，编写 **：NT Service\GcaHostService，** 然后单击 **确定**。 不要单击"检查 **名称"** 按钮。

8. 单击"权限"对话框上的"确定"。 现在，代理计算机配置为代理使用证书生成令牌。

## <a name="troubleshooting"></a>疑难解答

### <a name="installation-failure"></a>安装失败
如果安装失败，请运行以下方法检查安装日志：msiexec /i " <path to msi>\GcaInstaller.msi" /L*V " <destination path> \install.log"。 如果错误无法解决，请通过日志 MicrosoftGraphConnectorsFeedback@service.microsoft.com 支持。

### <a name="registration-failure"></a>注册失败

如果登录配置应用失败，出现错误"登录失败。" Please click on sign in button to try again." 即使在浏览器身份验证成功之后，打开 services.msc 并检查 GcaHostService 是否正在运行。 如果不是，请手动启动它。

如果服务启动失败，出现错误"服务由于登录失败而未启动"，请检查虚拟帐户 NT Service\GcaHostService 是否有权作为计算机上服务登录。 有关 [说明，](/windows/security/threat-protection/security-policy-settings/log-on-as-a-service) 请查看此链接。 如果在"本地策略"\"用户权限分配"中，添加用户或组的选项显示为灰色，则意味着尝试添加此帐户的用户在此计算机上没有管理员权限，或者存在覆盖此帐户的组策略。 需要更新组策略以允许主机服务作为服务登录。

### <a name="connection-failure"></a>连接失败

如果在创建连接时"测试连接"操作失败，出现错误"请检查用户名/密码和数据源路径"，即使提供的用户名和密码正确，请确保用户帐户对安装了 Graph 连接器代理的计算机具有交互式登录权限。 请参阅有关 [登录策略管理的文档](/windows/security/threat-protection/security-policy-settings/allow-log-on-locally#policy-management) 以检查登录权限。 还要确保数据源和代理计算机位于同一网络上。

如果连接失败，出现错误"1011： Graph 连接器代理不可访问或脱机。"，请登录到安装了代理的计算机，如果代理应用程序尚未运行，请启动它。 如果连接继续失败，请验证在注册期间提供给代理的证书或客户端密码是否尚未过期且具有所需的权限。
