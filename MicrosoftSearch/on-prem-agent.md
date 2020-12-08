---
title: 内部部署代理
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
description: 本地代理
ms.openlocfilehash: 5dbca392fefdcc11de253fd244cc98a6adcee68a
ms.sourcegitcommit: e8d770fa72ac83e074a5de57098cb55d06d8db07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588364"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="437b2-103">图形连接器代理</span><span class="sxs-lookup"><span data-stu-id="437b2-103">Graph connector agent</span></span>

<span data-ttu-id="437b2-104">若要使用本地图形连接器，需要安装 *graph 连接器代理* 软件。</span><span class="sxs-lookup"><span data-stu-id="437b2-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="437b2-105">它允许在本地数据和图形连接器 Api 之间进行安全的数据传输。</span><span class="sxs-lookup"><span data-stu-id="437b2-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="437b2-106">本文将指导您完成安装和配置代理。</span><span class="sxs-lookup"><span data-stu-id="437b2-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="437b2-107">安装</span><span class="sxs-lookup"><span data-stu-id="437b2-107">Installation</span></span>

<span data-ttu-id="437b2-108">[在此处](https://aka.ms/gcadownload)下载最新版本的 Graph 连接器代理，并使用安装向导安装该软件。</span><span class="sxs-lookup"><span data-stu-id="437b2-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="437b2-109">使用以下所述的计算机的推荐配置，软件最长可处理三个连接。</span><span class="sxs-lookup"><span data-stu-id="437b2-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="437b2-110">超过此数目的任何连接可能会降低代理上所有连接的性能。</span><span class="sxs-lookup"><span data-stu-id="437b2-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="437b2-111">建议的配置：</span><span class="sxs-lookup"><span data-stu-id="437b2-111">Recommended configuration:</span></span>

* <span data-ttu-id="437b2-112">Windows 10、Windows Server 2016 R2 及更高版本</span><span class="sxs-lookup"><span data-stu-id="437b2-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="437b2-113">.NET Core Desktop Runtime 3.1 (x64) </span><span class="sxs-lookup"><span data-stu-id="437b2-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="437b2-114">8核，3 GHz</span><span class="sxs-lookup"><span data-stu-id="437b2-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="437b2-115">16 GB RAM，2 GB 磁盘空间</span><span class="sxs-lookup"><span data-stu-id="437b2-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="437b2-116">通过443对数据源和 internet 的网络访问</span><span class="sxs-lookup"><span data-stu-id="437b2-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="437b2-117">创建和配置代理的应用程序</span><span class="sxs-lookup"><span data-stu-id="437b2-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="437b2-118">在使用代理之前，必须创建一个应用并配置身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="437b2-118">Before using the agent, you must create an app and configure the authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="437b2-119">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="437b2-119">Create an app</span></span>

1. <span data-ttu-id="437b2-120">转到 [Azure 门户](https://portal.azure.com) ，并使用管理员凭据登录租户。</span><span class="sxs-lookup"><span data-stu-id="437b2-120">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="437b2-121">从导航窗格导航到 " **Azure Active Directory**  ->  **应用程序注册**"，然后选择 "**新建注册**"。</span><span class="sxs-lookup"><span data-stu-id="437b2-121">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="437b2-122">提供应用程序的名称并选择 " **注册**"。</span><span class="sxs-lookup"><span data-stu-id="437b2-122">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="437b2-123">记下应用程序 (客户端) ID。</span><span class="sxs-lookup"><span data-stu-id="437b2-123">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="437b2-124">从导航窗格中打开 **API 权限** ，并选择 " **添加权限**"。</span><span class="sxs-lookup"><span data-stu-id="437b2-124">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="437b2-125">依次选择 " **Microsoft Graph** " 和 " **应用程序权限**"。</span><span class="sxs-lookup"><span data-stu-id="437b2-125">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="437b2-126">从权限中搜索 "ExternalItem" 和 "Directory. All" 并选择 " **添加权限**"。</span><span class="sxs-lookup"><span data-stu-id="437b2-126">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="437b2-127">选择 " **授予管理员同意 [TenantName]** " 并通过选择 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="437b2-127">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="437b2-128">检查权限是否处于 "已授予" 状态。</span><span class="sxs-lookup"><span data-stu-id="437b2-128">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="437b2-129">![权限显示为 "在右侧绿色中授予" 列。](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="437b2-129">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="437b2-130">配置身份验证</span><span class="sxs-lookup"><span data-stu-id="437b2-130">Configure Authentication</span></span>

<span data-ttu-id="437b2-131">可以使用客户端密码或证书提供身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="437b2-131">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="437b2-132">按照您选择的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="437b2-132">Follow the steps for your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="437b2-133">配置客户端机密以进行身份验证</span><span class="sxs-lookup"><span data-stu-id="437b2-133">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="437b2-134">转到 [Azure 门户](https://portal.azure.com) ，并使用管理员凭据登录租户。</span><span class="sxs-lookup"><span data-stu-id="437b2-134">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="437b2-135">从导航窗格中打开 " **应用注册** "，然后转到相应的应用程序。</span><span class="sxs-lookup"><span data-stu-id="437b2-135">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="437b2-136">在 " **管理**" 下，选择 " **证书和密码**"。</span><span class="sxs-lookup"><span data-stu-id="437b2-136">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="437b2-137">选择 " **新建客户端密码** "，然后选择密码的有效期。</span><span class="sxs-lookup"><span data-stu-id="437b2-137">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="437b2-138">复制生成的机密并将其保存，因为它不会再次显示。</span><span class="sxs-lookup"><span data-stu-id="437b2-138">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="437b2-139">使用此客户端密码和应用程序 ID 配置代理。</span><span class="sxs-lookup"><span data-stu-id="437b2-139">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="437b2-140">不能在代理的 " **名称** " 字段中使用空格。</span><span class="sxs-lookup"><span data-stu-id="437b2-140">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="437b2-141">接受字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="437b2-141">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="437b2-142">使用证书进行身份验证</span><span class="sxs-lookup"><span data-stu-id="437b2-142">Using a certificate for authentication</span></span>

<span data-ttu-id="437b2-143">使用基于证书的身份验证有三个简单的步骤：</span><span class="sxs-lookup"><span data-stu-id="437b2-143">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="437b2-144">创建或获取证书</span><span class="sxs-lookup"><span data-stu-id="437b2-144">Create or obtain a certificate</span></span>
1. <span data-ttu-id="437b2-145">将证书上传到 Azure 门户</span><span class="sxs-lookup"><span data-stu-id="437b2-145">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="437b2-146">将证书分配给代理</span><span class="sxs-lookup"><span data-stu-id="437b2-146">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="437b2-147">步骤1：获取证书</span><span class="sxs-lookup"><span data-stu-id="437b2-147">Step 1: Get a certificate</span></span>

<span data-ttu-id="437b2-148">下面的脚本可用于生成自签名证书。</span><span class="sxs-lookup"><span data-stu-id="437b2-148">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="437b2-149">您的组织可能不允许自签名证书。</span><span class="sxs-lookup"><span data-stu-id="437b2-149">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="437b2-150">在这种情况下，请使用此信息来了解这些要求，并根据组织的策略获取证书。</span><span class="sxs-lookup"><span data-stu-id="437b2-150">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="437b2-151">步骤2：在 Azure 门户中上传证书</span><span class="sxs-lookup"><span data-stu-id="437b2-151">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="437b2-152">打开应用程序并导航到左侧窗格中的 "证书和密码" 部分</span><span class="sxs-lookup"><span data-stu-id="437b2-152">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="437b2-153">选择 "上载证书" 并上载 .cer 文件</span><span class="sxs-lookup"><span data-stu-id="437b2-153">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="437b2-154">打开 " **应用注册** "，然后从导航窗格中选择 " **证书和密码** "。</span><span class="sxs-lookup"><span data-stu-id="437b2-154">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="437b2-155">复制证书指纹。</span><span class="sxs-lookup"><span data-stu-id="437b2-155">Copy the certificate thumbprint.</span></span>

![在左窗格中选择了 "证书和密码" 时的 thumbrint 证书列表](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="437b2-157">步骤3：将证书分配给代理</span><span class="sxs-lookup"><span data-stu-id="437b2-157">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="437b2-158">如果使用了示例脚本生成证书，则可以在脚本中标识的位置找到 PFX 文件。</span><span class="sxs-lookup"><span data-stu-id="437b2-158">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="437b2-159">将证书 pfx 文件下载到代理计算机上。</span><span class="sxs-lookup"><span data-stu-id="437b2-159">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="437b2-160">双击 pfx 文件以启动 "证书安装" 对话框。</span><span class="sxs-lookup"><span data-stu-id="437b2-160">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="437b2-161">安装证书时，为存储位置选择 "本地计算机"。</span><span class="sxs-lookup"><span data-stu-id="437b2-161">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="437b2-162">安装证书后，通过 "开始" 菜单打开 "管理计算机证书"</span><span class="sxs-lookup"><span data-stu-id="437b2-162">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="437b2-163">选择 "个人" 下新安装的证书-> "证书"</span><span class="sxs-lookup"><span data-stu-id="437b2-163">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="437b2-164">右键单击证书，然后选择 "所有任务"-> "管理私钥 ..."</span><span class="sxs-lookup"><span data-stu-id="437b2-164">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="437b2-165">选项</span><span class="sxs-lookup"><span data-stu-id="437b2-165">Option</span></span>
1. <span data-ttu-id="437b2-166">在 "权限" 对话框中，选择 "添加选项"。</span><span class="sxs-lookup"><span data-stu-id="437b2-166">In the permissions dialog, select add option.</span></span> <span data-ttu-id="437b2-167">在 "用户选择" 对话框中，写入： "NT Service\GcaHostService"，然后单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="437b2-167">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="437b2-168">不要单击 "检查姓名" 按钮。</span><span class="sxs-lookup"><span data-stu-id="437b2-168">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="437b2-169">在 "权限" 对话框中单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="437b2-169">Click okay on the permissions dialog.</span></span> <span data-ttu-id="437b2-170">此时，代理计算机已配置为使用证书生成令牌的代理。</span><span class="sxs-lookup"><span data-stu-id="437b2-170">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
