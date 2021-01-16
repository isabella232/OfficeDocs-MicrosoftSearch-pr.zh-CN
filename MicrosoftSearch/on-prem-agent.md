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
ms.openlocfilehash: 31220196849fe90ab2611e9c2b83a1cec0a02b34
ms.sourcegitcommit: a04f1df14a3221776ccd141f6060328612d80e06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876495"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="191f5-103">Graph 连接器代理</span><span class="sxs-lookup"><span data-stu-id="191f5-103">Graph connector agent</span></span>

<span data-ttu-id="191f5-104">使用 On-prem Graph 连接器需要安装 *Graph 连接器代理* 软件。</span><span class="sxs-lookup"><span data-stu-id="191f5-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="191f5-105">它允许在本地数据和 Graph 连接器 API 之间安全数据传输。</span><span class="sxs-lookup"><span data-stu-id="191f5-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="191f5-106">本文将指导您完成代理的安装和配置。</span><span class="sxs-lookup"><span data-stu-id="191f5-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="191f5-107">安装</span><span class="sxs-lookup"><span data-stu-id="191f5-107">Installation</span></span>

<span data-ttu-id="191f5-108">在此处下载最新版本的 Graph 连接器 [代理](https://aka.ms/gcadownload) ，然后使用安装向导安装软件。</span><span class="sxs-lookup"><span data-stu-id="191f5-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="191f5-109">使用如下所述计算机的建议配置，软件可处理最多三个连接。</span><span class="sxs-lookup"><span data-stu-id="191f5-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="191f5-110">除此之外的任何连接都可能会降低代理上所有连接的性能。</span><span class="sxs-lookup"><span data-stu-id="191f5-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="191f5-111">建议的配置：</span><span class="sxs-lookup"><span data-stu-id="191f5-111">Recommended configuration:</span></span>

* <span data-ttu-id="191f5-112">Windows 10、Windows Server 2016 R2 及以上版本</span><span class="sxs-lookup"><span data-stu-id="191f5-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="191f5-113">.NET Core Desktop Runtime 3.1 (x64) </span><span class="sxs-lookup"><span data-stu-id="191f5-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="191f5-114">8 核，3 GHz</span><span class="sxs-lookup"><span data-stu-id="191f5-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="191f5-115">16 GB RAM，2 GB 磁盘空间</span><span class="sxs-lookup"><span data-stu-id="191f5-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="191f5-116">通过 443 对数据源和 Internet 的网络访问</span><span class="sxs-lookup"><span data-stu-id="191f5-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="191f5-117">为代理创建和配置应用</span><span class="sxs-lookup"><span data-stu-id="191f5-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="191f5-118">首先，登录并注意帐户所需的最低权限是搜索管理员。</span><span class="sxs-lookup"><span data-stu-id="191f5-118">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="191f5-119">然后，代理将要求您提供身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="191f5-119">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="191f5-120">使用以下步骤创建应用并生成所需的身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="191f5-120">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="191f5-121">创建应用</span><span class="sxs-lookup"><span data-stu-id="191f5-121">Create an app</span></span>

1. <span data-ttu-id="191f5-122">转到 [Azure 门户，](https://portal.azure.com) 然后使用租户的管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="191f5-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="191f5-123">从导航 **窗格导航到 Azure Active Directory** 应用注册  ->  ，然后选择 **"新建注册"。**</span><span class="sxs-lookup"><span data-stu-id="191f5-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="191f5-124">提供应用的名称，然后选择"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="191f5-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="191f5-125">记下应用程序客户端 (ID) ID。</span><span class="sxs-lookup"><span data-stu-id="191f5-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="191f5-126">从 **导航窗格中打开 API** 权限，然后选择 **"添加权限"。**</span><span class="sxs-lookup"><span data-stu-id="191f5-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="191f5-127">选择 **Microsoft Graph，** 然后选择 **应用程序权限**。</span><span class="sxs-lookup"><span data-stu-id="191f5-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="191f5-128">从权限中搜索"ExternalItem.ReadWrite.All"和"Directory.Read.All"，然后选择 **"添加权限"。**</span><span class="sxs-lookup"><span data-stu-id="191f5-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="191f5-129">选择 **"授予管理员同意 [TenantName]"，** 然后通过选择"是 **"确认**。</span><span class="sxs-lookup"><span data-stu-id="191f5-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="191f5-130">检查权限是否位于"已授予"状态。</span><span class="sxs-lookup"><span data-stu-id="191f5-130">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="191f5-131">![右侧列上显示为绿色授予的权限。](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="191f5-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="191f5-132">配置身份验证</span><span class="sxs-lookup"><span data-stu-id="191f5-132">Configure Authentication</span></span>

<span data-ttu-id="191f5-133">可以使用客户端密码或证书提供身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="191f5-133">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="191f5-134">按照你选择的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="191f5-134">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="191f5-135">配置客户端密码进行身份验证</span><span class="sxs-lookup"><span data-stu-id="191f5-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="191f5-136">转到 [Azure 门户，](https://portal.azure.com) 然后使用租户的管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="191f5-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="191f5-137">从 **导航窗格** 打开应用注册，然后转到相应的应用。</span><span class="sxs-lookup"><span data-stu-id="191f5-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="191f5-138">在 **"管理**"下 **，选择"证书和密码"。**</span><span class="sxs-lookup"><span data-stu-id="191f5-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="191f5-139">选择 **"新建** 客户端密码"，然后选择密码的过期期限。</span><span class="sxs-lookup"><span data-stu-id="191f5-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="191f5-140">复制生成的密码并保存它，因为它不会再次显示。</span><span class="sxs-lookup"><span data-stu-id="191f5-140">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="191f5-141">使用此客户端密码和应用程序 ID 配置代理。</span><span class="sxs-lookup"><span data-stu-id="191f5-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="191f5-142">不能在代理的"名称" **字段中** 使用空格。</span><span class="sxs-lookup"><span data-stu-id="191f5-142">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="191f5-143">接受字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="191f5-143">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="191f5-144">使用证书进行身份验证</span><span class="sxs-lookup"><span data-stu-id="191f5-144">Using a certificate for authentication</span></span>

<span data-ttu-id="191f5-145">使用基于证书的身份验证有三个简单的步骤：</span><span class="sxs-lookup"><span data-stu-id="191f5-145">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="191f5-146">创建或获取证书</span><span class="sxs-lookup"><span data-stu-id="191f5-146">Create or obtain a certificate</span></span>
1. <span data-ttu-id="191f5-147">将证书上载到 Azure 门户</span><span class="sxs-lookup"><span data-stu-id="191f5-147">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="191f5-148">将证书分配给代理</span><span class="sxs-lookup"><span data-stu-id="191f5-148">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="191f5-149">步骤 1：获取证书</span><span class="sxs-lookup"><span data-stu-id="191f5-149">Step 1: Get a certificate</span></span>

<span data-ttu-id="191f5-150">下面的脚本可用于生成自签名证书。</span><span class="sxs-lookup"><span data-stu-id="191f5-150">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="191f5-151">你的组织可能不允许自签名证书。</span><span class="sxs-lookup"><span data-stu-id="191f5-151">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="191f5-152">在这种情况下，请使用此信息了解要求，并根据组织策略获取证书。</span><span class="sxs-lookup"><span data-stu-id="191f5-152">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="191f5-153">步骤 2：在 Azure 门户中上载证书</span><span class="sxs-lookup"><span data-stu-id="191f5-153">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="191f5-154">打开应用程序，然后从左窗格导航到"证书和机密"部分</span><span class="sxs-lookup"><span data-stu-id="191f5-154">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="191f5-155">选择"上载证书"并上载 .cer 文件</span><span class="sxs-lookup"><span data-stu-id="191f5-155">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="191f5-156">打开 **应用注册** ，然后从 **导航窗格中** 选择证书和密码。</span><span class="sxs-lookup"><span data-stu-id="191f5-156">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="191f5-157">复制证书指纹。</span><span class="sxs-lookup"><span data-stu-id="191f5-157">Copy the certificate thumbprint.</span></span>

![在左窗格中选择证书和密码时指纹证书列表](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="191f5-159">步骤 3：将证书分配给代理</span><span class="sxs-lookup"><span data-stu-id="191f5-159">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="191f5-160">如果使用示例脚本生成证书，可以在脚本中标识的位置找到 PFX 文件。</span><span class="sxs-lookup"><span data-stu-id="191f5-160">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="191f5-161">将证书 pfx 文件下载到代理计算机上。</span><span class="sxs-lookup"><span data-stu-id="191f5-161">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="191f5-162">双击 pfx 文件以启动证书安装对话框。</span><span class="sxs-lookup"><span data-stu-id="191f5-162">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="191f5-163">安装证书时，选择"本地计算机"作为存储位置。</span><span class="sxs-lookup"><span data-stu-id="191f5-163">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="191f5-164">安装证书后，通过"开始"菜单打开"管理计算机证书"</span><span class="sxs-lookup"><span data-stu-id="191f5-164">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="191f5-165">Select the newly installed certificate under "Personal" -> 'Certificates'</span><span class="sxs-lookup"><span data-stu-id="191f5-165">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="191f5-166">右键单击证书并选择"所有任务"->"管理私钥..."</span><span class="sxs-lookup"><span data-stu-id="191f5-166">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="191f5-167">选项</span><span class="sxs-lookup"><span data-stu-id="191f5-167">Option</span></span>
1. <span data-ttu-id="191f5-168">在"权限"对话框中，选择"添加"选项。</span><span class="sxs-lookup"><span data-stu-id="191f5-168">In the permissions dialog, select add option.</span></span> <span data-ttu-id="191f5-169">在用户选择对话框中，写入："NT Service\GcaHostService"，然后单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="191f5-169">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="191f5-170">不要单击"检查姓名"按钮。</span><span class="sxs-lookup"><span data-stu-id="191f5-170">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="191f5-171">单击"权限"对话框上的"确定"。</span><span class="sxs-lookup"><span data-stu-id="191f5-171">Click okay on the permissions dialog.</span></span> <span data-ttu-id="191f5-172">现在，代理计算机配置为使用证书生成令牌。</span><span class="sxs-lookup"><span data-stu-id="191f5-172">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
