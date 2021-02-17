---
title: 本地代理
ms.author: rusamai
author: rsamai
manager: jameslau
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
ms.openlocfilehash: bd5212d42fe21583aa6a4e0dc8060d5e191a7292
ms.sourcegitcommit: 35b4246cb3e38c6fe21540686e28fe54154b33f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2021
ms.locfileid: "50259426"
---
# <a name="graph-connector-agent"></a>Graph 连接器代理

使用 On-prem Graph 连接器需要安装 *Graph 连接器代理* 软件。 它允许在本地数据和 Graph 连接器 API 之间安全数据传输。 本文将指导您完成代理的安装和配置。

## <a name="installation"></a>安装

在此处下载最新版本的 Graph 连接器 [代理](https://aka.ms/gcadownload) ，然后使用安装向导安装软件。 使用下面所述的计算机的建议配置，软件可以处理最多三个连接。 除此之外的任何连接都可能会降低代理上所有连接的性能。

建议的配置：

* Windows 10、Windows Server 2016 R2 及以上版本
* [.NET Core Desktop Runtime 3.1 (x64) ](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 核，3 GHz
* 16 GB RAM，2 GB 磁盘空间
* 通过 443 对数据源和 Internet 的网络访问

安装代理后，如果组织的代理服务器或防火墙阻止与未知域的通信，请将以下这些域添加到允许列表中。

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>login.microsoftonline.</span>com
4. https://<span>gcs.office。</span>com/
5. https://<span>graph.microsoft.</span>com/


## <a name="create-and-configure-an-app-for-the-agent"></a>为代理创建和配置应用  

首先，登录并注意，帐户所需的最低权限是搜索管理员。 然后，代理将要求您提供身份验证详细信息。 使用以下步骤创建应用并生成所需的身份验证详细信息。

### <a name="create-an-app"></a>创建应用

1. 转到 [Azure 门户，](https://portal.azure.com) 然后使用租户的管理员凭据登录。
2. 从导航 **窗格导航到 Azure Active Directory** 应用注册  ->  ，然后选择 **"新建注册"。**
3. 提供应用的名称，然后选择"注册 **"。**
4. 记下应用程序应用程序 (客户端) ID。
5. 从 **导航窗格中打开 API** 权限，然后选择 **"添加权限"。**
6. 选择 **Microsoft Graph，** 然后选择 **应用程序权限**。
7. 从权限中搜索"ExternalItem.ReadWrite.All"和"Directory.Read.All"，然后选择 **"添加权限"。**
8. 选择 **"为 [TenantName]** 授予管理员同意"，然后通过选择"是 **"确认**。
9. 检查权限是否位于"已授予"状态。
     ![右侧列显示为绿色授予的权限。](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>配置身份验证

可以使用客户端密码或证书提供身份验证详细信息。 按照你选择的步骤操作。

#### <a name="configuring-the-client-secret-for-authentication"></a>配置客户端密码进行身份验证

1. 转到 [Azure 门户，](https://portal.azure.com) 然后使用租户的管理员凭据登录。
2. 从 **导航窗格中** 打开应用注册，然后转到相应的应用。 在 **"管理**"下，**选择"证书和密码"。**
3. 选择 **"新建** 客户端密码"，然后选择密码的过期期限。 复制生成的密码并保存它，因为它不会再次显示。
4. 使用此客户端密码和应用程序 ID 配置代理。 不能在代理的"名称" **字段中** 使用空格。 接受字母数字字符。

#### <a name="using-a-certificate-for-authentication"></a>使用证书进行身份验证

使用基于证书的身份验证有三个简单的步骤：

1. 创建或获取证书
1. 将证书上载到 Azure 门户
1. 将证书分配给代理

##### <a name="step-1-get-a-certificate"></a>步骤 1：获取证书

下面的脚本可用于生成自签名证书。 您的组织可能不允许自签名证书。 在这种情况下，请使用此信息了解要求，并根据组织策略获取证书。

```Powershell
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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>步骤 2：在 Azure 门户中上载证书

1. 打开应用程序，然后从左窗格导航到"证书和机密"部分
1. 选择"上载证书"并上载 .cer 文件
1. 打开 **应用注册** ，然后 **从导航窗格中** 选择证书和密码。 复制证书指纹。

![在左窗格中选择证书和密码时指纹证书列表](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>步骤 3：将证书分配给代理

如果使用示例脚本生成证书，可以在脚本中标识的位置找到 PFX 文件。

1. 将证书 pfx 文件下载到代理计算机。
1. 双击 pfx 文件以启动证书安装对话框。
1. 安装证书时，选择"本地计算机"作为存储位置。
1. 安装证书后，通过"开始"菜单打开"管理计算机证书"
1. 在"个人"->"证书"下选择新安装的证书
1. 右键单击证书并选择"所有任务"->"管理私钥..." 选项
1. 在权限对话框中，选择"添加"选项。 在用户选择对话框中，写入："NT Service\GcaHostService"，然后单击"确定"。 不要单击"检查姓名"按钮。
1. 单击"权限"对话框上的"确定"。 代理计算机现在配置为代理使用证书生成令牌。

## <a name="troubleshooting"></a>疑难解答
1. 如果连接失败，出现错误"1011： Graph 连接器代理不可访问或脱机。"，登录到安装了代理的计算机，如果代理应用程序尚未运行，则启动它。 如果连接继续失败，请验证在注册期间提供给代理的证书或客户端密码尚未过期并且具有所需的权限。
