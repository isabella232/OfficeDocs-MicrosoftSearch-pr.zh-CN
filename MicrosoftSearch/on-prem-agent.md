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
description: On-prem 代理
ms.openlocfilehash: 7aef2ea57c92929d4d4f45e1a738c84e6a3f4bba
ms.sourcegitcommit: ab4f81ded967168689e6e81c90e115b94719335c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50173059"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="a449b-103">图形连接器代理</span><span class="sxs-lookup"><span data-stu-id="a449b-103">Graph connector agent</span></span>

<span data-ttu-id="a449b-104">使用 On-prem Graph 连接器需要安装 *Graph 连接器代理* 软件。</span><span class="sxs-lookup"><span data-stu-id="a449b-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="a449b-105">它允许在本地数据和 Graph 连接器 API 之间安全数据传输。</span><span class="sxs-lookup"><span data-stu-id="a449b-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="a449b-106">本文将指导您完成代理的安装和配置。</span><span class="sxs-lookup"><span data-stu-id="a449b-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="a449b-107">安装</span><span class="sxs-lookup"><span data-stu-id="a449b-107">Installation</span></span>

<span data-ttu-id="a449b-108">在此处下载最新版本的 Graph 连接器 [代理](https://aka.ms/gcadownload) ，然后使用安装向导安装软件。</span><span class="sxs-lookup"><span data-stu-id="a449b-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="a449b-109">使用如下所述计算机的建议配置，软件可处理最多三个连接。</span><span class="sxs-lookup"><span data-stu-id="a449b-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="a449b-110">除此之外的任何连接都可能会降低代理上所有连接的性能。</span><span class="sxs-lookup"><span data-stu-id="a449b-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="a449b-111">建议的配置：</span><span class="sxs-lookup"><span data-stu-id="a449b-111">Recommended configuration:</span></span>

* <span data-ttu-id="a449b-112">Windows 10、Windows Server 2016 R2 及以上版本</span><span class="sxs-lookup"><span data-stu-id="a449b-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="a449b-113">.NET Core Desktop Runtime 3.1 (x64) </span><span class="sxs-lookup"><span data-stu-id="a449b-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="a449b-114">8 核，3 GHz</span><span class="sxs-lookup"><span data-stu-id="a449b-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="a449b-115">16 GB RAM，2 GB 磁盘空间</span><span class="sxs-lookup"><span data-stu-id="a449b-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="a449b-116">通过 443 对数据源和 Internet 的网络访问</span><span class="sxs-lookup"><span data-stu-id="a449b-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="a449b-117">安装代理后，如果组织的代理服务器或防火墙阻止与未知域的通信，请将以下这些域添加到允许列表中。</span><span class="sxs-lookup"><span data-stu-id="a449b-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="a449b-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="a449b-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="a449b-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a449b-119">\*.events.data.microsoft.com</span></span>
3. https://login.microsoftonline.com
4. https://gcs.office.com
5. https://graph.microsoft.com/


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="a449b-120">为代理创建和配置应用</span><span class="sxs-lookup"><span data-stu-id="a449b-120">Create and configure an App for the agent</span></span>  

<span data-ttu-id="a449b-121">首先，登录并注意帐户所需的最低权限是搜索管理员。</span><span class="sxs-lookup"><span data-stu-id="a449b-121">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="a449b-122">然后，代理将要求您提供身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="a449b-122">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="a449b-123">使用以下步骤创建应用并生成所需的身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="a449b-123">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="a449b-124">创建应用</span><span class="sxs-lookup"><span data-stu-id="a449b-124">Create an app</span></span>

1. <span data-ttu-id="a449b-125">转到 [Azure 门户，](https://portal.azure.com) 然后使用租户的管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="a449b-125">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="a449b-126">从导航 **窗格导航到 Azure Active Directory** 应用注册  ->  ，然后选择 **"新建注册"。**</span><span class="sxs-lookup"><span data-stu-id="a449b-126">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="a449b-127">提供应用的名称，然后选择"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="a449b-127">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="a449b-128">记下应用程序客户端 (ID) ID。</span><span class="sxs-lookup"><span data-stu-id="a449b-128">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="a449b-129">从 **导航窗格中打开 API** 权限，然后选择 **"添加权限"。**</span><span class="sxs-lookup"><span data-stu-id="a449b-129">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="a449b-130">选择 **Microsoft Graph，** 然后选择 **应用程序权限**。</span><span class="sxs-lookup"><span data-stu-id="a449b-130">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="a449b-131">从权限中搜索"ExternalItem.ReadWrite.All"和"Directory.Read.All"，然后选择 **"添加权限"。**</span><span class="sxs-lookup"><span data-stu-id="a449b-131">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="a449b-132">选择 **"授予管理员同意 [TenantName]"，** 然后通过选择"是 **"确认**。</span><span class="sxs-lookup"><span data-stu-id="a449b-132">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="a449b-133">检查权限是否位于"已授予"状态。</span><span class="sxs-lookup"><span data-stu-id="a449b-133">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="a449b-134">![右侧列显示为绿色授予的权限。](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="a449b-134">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="a449b-135">配置身份验证</span><span class="sxs-lookup"><span data-stu-id="a449b-135">Configure Authentication</span></span>

<span data-ttu-id="a449b-136">可以使用客户端密码或证书提供身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="a449b-136">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="a449b-137">按照你选择的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a449b-137">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="a449b-138">配置客户端密码进行身份验证</span><span class="sxs-lookup"><span data-stu-id="a449b-138">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="a449b-139">转到 [Azure 门户，](https://portal.azure.com) 然后使用租户的管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="a449b-139">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="a449b-140">从 **导航窗格中** 打开应用注册，然后转到相应的应用。</span><span class="sxs-lookup"><span data-stu-id="a449b-140">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="a449b-141">在 **"管理**"下 **，选择证书和密码**。</span><span class="sxs-lookup"><span data-stu-id="a449b-141">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="a449b-142">选择 **"新建** 客户端密码"，然后选择密码的过期期限。</span><span class="sxs-lookup"><span data-stu-id="a449b-142">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="a449b-143">复制生成的密码并保存它，因为它不会再次显示。</span><span class="sxs-lookup"><span data-stu-id="a449b-143">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="a449b-144">使用此客户端密码和应用程序 ID 配置代理。</span><span class="sxs-lookup"><span data-stu-id="a449b-144">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="a449b-145">不能在代理的"名称" **字段中** 使用空格。</span><span class="sxs-lookup"><span data-stu-id="a449b-145">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="a449b-146">接受字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="a449b-146">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="a449b-147">使用证书进行身份验证</span><span class="sxs-lookup"><span data-stu-id="a449b-147">Using a certificate for authentication</span></span>

<span data-ttu-id="a449b-148">使用基于证书的身份验证有三个简单的步骤：</span><span class="sxs-lookup"><span data-stu-id="a449b-148">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="a449b-149">创建或获取证书</span><span class="sxs-lookup"><span data-stu-id="a449b-149">Create or obtain a certificate</span></span>
1. <span data-ttu-id="a449b-150">将证书上载到 Azure 门户</span><span class="sxs-lookup"><span data-stu-id="a449b-150">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="a449b-151">将证书分配给代理</span><span class="sxs-lookup"><span data-stu-id="a449b-151">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="a449b-152">步骤 1：获取证书</span><span class="sxs-lookup"><span data-stu-id="a449b-152">Step 1: Get a certificate</span></span>

<span data-ttu-id="a449b-153">下面的脚本可用于生成自签名证书。</span><span class="sxs-lookup"><span data-stu-id="a449b-153">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="a449b-154">你的组织可能不允许自签名证书。</span><span class="sxs-lookup"><span data-stu-id="a449b-154">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="a449b-155">在这种情况下，使用此信息了解要求，并根据组织策略获取证书。</span><span class="sxs-lookup"><span data-stu-id="a449b-155">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="a449b-156">步骤 2：在 Azure 门户中上载证书</span><span class="sxs-lookup"><span data-stu-id="a449b-156">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="a449b-157">打开应用程序，然后从左窗格导航到"证书和机密"部分</span><span class="sxs-lookup"><span data-stu-id="a449b-157">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="a449b-158">选择"上载证书"并上载 .cer 文件</span><span class="sxs-lookup"><span data-stu-id="a449b-158">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="a449b-159">打开 **应用注册** ，然后从 **导航窗格中** 选择证书和密码。</span><span class="sxs-lookup"><span data-stu-id="a449b-159">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="a449b-160">复制证书指纹。</span><span class="sxs-lookup"><span data-stu-id="a449b-160">Copy the certificate thumbprint.</span></span>

![在左窗格中选择证书和密码时指纹证书列表](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="a449b-162">步骤 3：将证书分配给代理</span><span class="sxs-lookup"><span data-stu-id="a449b-162">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="a449b-163">如果使用示例脚本生成证书，可以在脚本中标识的位置找到 PFX 文件。</span><span class="sxs-lookup"><span data-stu-id="a449b-163">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="a449b-164">将证书 pfx 文件下载到代理计算机上。</span><span class="sxs-lookup"><span data-stu-id="a449b-164">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="a449b-165">双击 pfx 文件以启动证书安装对话框。</span><span class="sxs-lookup"><span data-stu-id="a449b-165">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="a449b-166">安装证书时，选择"本地计算机"作为存储位置。</span><span class="sxs-lookup"><span data-stu-id="a449b-166">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="a449b-167">安装证书后，通过"开始"菜单打开"管理计算机证书"</span><span class="sxs-lookup"><span data-stu-id="a449b-167">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="a449b-168">Select the newly installed certificate under "Personal" -> 'Certificates'</span><span class="sxs-lookup"><span data-stu-id="a449b-168">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="a449b-169">右键单击证书并选择"所有任务"->"管理私钥..."</span><span class="sxs-lookup"><span data-stu-id="a449b-169">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="a449b-170">选项</span><span class="sxs-lookup"><span data-stu-id="a449b-170">Option</span></span>
1. <span data-ttu-id="a449b-171">在"权限"对话框中，选择"添加"选项。</span><span class="sxs-lookup"><span data-stu-id="a449b-171">In the permissions dialog, select add option.</span></span> <span data-ttu-id="a449b-172">在用户选择对话框中，写入："NT Service\GcaHostService"，然后单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="a449b-172">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="a449b-173">不要单击"检查姓名"按钮。</span><span class="sxs-lookup"><span data-stu-id="a449b-173">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="a449b-174">单击"权限"对话框上的"确定"。</span><span class="sxs-lookup"><span data-stu-id="a449b-174">Click okay on the permissions dialog.</span></span> <span data-ttu-id="a449b-175">现在，代理计算机配置为使用证书生成令牌。</span><span class="sxs-lookup"><span data-stu-id="a449b-175">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
