---
title: 在本地代理上
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
ms.openlocfilehash: 487c5b179e09fd99fa26ae7a237e89ca38b7be4d
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408939"
---
# <a name="on-prem-agent"></a><span data-ttu-id="82105-103">本地代理</span><span class="sxs-lookup"><span data-stu-id="82105-103">On-Prem Agent</span></span>

## <a name="graph-connector-agent"></a><span data-ttu-id="82105-104">图形连接器代理</span><span class="sxs-lookup"><span data-stu-id="82105-104">Graph connector agent</span></span>

<span data-ttu-id="82105-105">本地 Graph 连接器要求您安装 *graph 连接器代理* 软件。</span><span class="sxs-lookup"><span data-stu-id="82105-105">On-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="82105-106">它允许在本地数据和云服务之间进行快速且安全的数据传输。</span><span class="sxs-lookup"><span data-stu-id="82105-106">It allows quick and secure data transfer between on-premises data and cloud services.</span></span> <span data-ttu-id="82105-107">本文将指导您完成安装和配置软件的步骤。</span><span class="sxs-lookup"><span data-stu-id="82105-107">This article guides you through the steps of installing and configuring the software.</span></span> <span data-ttu-id="82105-108">配置完成后，将可以从 [Microsoft 365 管理中心](https://admin.microsoft.com)创建到本地数据源的连接。</span><span class="sxs-lookup"><span data-stu-id="82105-108">Once configured, it will be available for creating connections to your on-prem data sources from the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

## <a name="installation"></a><span data-ttu-id="82105-109">安装</span><span class="sxs-lookup"><span data-stu-id="82105-109">Installation</span></span>

<span data-ttu-id="82105-110">使用 [此链接](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) 下载 Graph 连接器代理的最新版本，并使用安装向导安装该软件。</span><span class="sxs-lookup"><span data-stu-id="82105-110">Download the latest version of Graph connector agent using [this link](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) and install the software using the installation wizard.</span></span> <span data-ttu-id="82105-111">使用下面所述的计算机的推荐配置，软件可以无缝处理最高三个连接。</span><span class="sxs-lookup"><span data-stu-id="82105-111">With the recommended configuration of the machine described below, the software can seamlessly handle up to three connections.</span></span> <span data-ttu-id="82105-112">超过此范围的任何连接可能会降低性能。</span><span class="sxs-lookup"><span data-stu-id="82105-112">Any connections beyond that might degrade the performance.</span></span>

<span data-ttu-id="82105-113">建议的配置：</span><span class="sxs-lookup"><span data-stu-id="82105-113">Recommended configuration:</span></span>

* <span data-ttu-id="82105-114">Windows 10、Windows Server 2012 R2 及更高版本</span><span class="sxs-lookup"><span data-stu-id="82105-114">Windows 10, Windows Server 2012 R2 and above</span></span>
* <span data-ttu-id="82105-115">8核，3GHz</span><span class="sxs-lookup"><span data-stu-id="82105-115">8 cores, 3GHz</span></span>
* <span data-ttu-id="82105-116">16 GB RAM，1GB 磁盘空间</span><span class="sxs-lookup"><span data-stu-id="82105-116">16GB RAM, 1GB Disk Space</span></span>
* <span data-ttu-id="82105-117">通过443对数据源和 internet 的网络访问</span><span class="sxs-lookup"><span data-stu-id="82105-117">Network access to data source and internet through 443</span></span>

## <a name="creating-app-for-the-agent"></a><span data-ttu-id="82105-118">创建代理的应用程序</span><span class="sxs-lookup"><span data-stu-id="82105-118">Creating App for the agent</span></span>  

<span data-ttu-id="82105-119">在创建连接之前，需要对代理实例进行多个重要的关键参数馈送。</span><span class="sxs-lookup"><span data-stu-id="82105-119">The agent instance needs to be fed few critical parameters before you create connections.</span></span> <span data-ttu-id="82105-120">这些参数包括使用 Graph 摄取 Api 所需的身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="82105-120">These parameters include authentication details required for using Graph ingestion APIs.</span></span>  

<span data-ttu-id="82105-121">为代理创建应用程序的步骤。</span><span class="sxs-lookup"><span data-stu-id="82105-121">Steps for creating App for the agent.</span></span>

1. <span data-ttu-id="82105-122">转到 [Azure 门户](https://portal.azure.com) ，并使用管理员凭据登录租户。</span><span class="sxs-lookup"><span data-stu-id="82105-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="82105-123">从导航窗格导航到 " **Azure Active Directory**  ->  **应用程序注册**"，然后选择 "**新建注册**"。</span><span class="sxs-lookup"><span data-stu-id="82105-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="82105-124">提供应用程序的名称并选择 " **注册**"。</span><span class="sxs-lookup"><span data-stu-id="82105-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="82105-125">记下应用程序 (客户端) ID。</span><span class="sxs-lookup"><span data-stu-id="82105-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="82105-126">从导航窗格中打开 **API 权限** ，并选择 " **添加权限**"。</span><span class="sxs-lookup"><span data-stu-id="82105-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="82105-127">依次选择 " **Microsoft Graph** " 和 " **应用程序权限**"。</span><span class="sxs-lookup"><span data-stu-id="82105-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="82105-128">从权限中搜索 "ExternalItem" 和 "Directory. All" 并选择 " **添加权限**"。</span><span class="sxs-lookup"><span data-stu-id="82105-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="82105-129">选择 " **授予管理员同意 [TenantName]** " 并通过选择 **"是"** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="82105-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="82105-130">检查权限是否处于 "已授予" 状态。</span><span class="sxs-lookup"><span data-stu-id="82105-130">Check that the permissions are in the granted state.</span></span>
     <span data-ttu-id="82105-131">![权限显示为 "在右侧绿色中授予" 列。](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="82105-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

## <a name="configuring-graph-connector-agent"></a><span data-ttu-id="82105-132">配置 Graph 连接器代理</span><span class="sxs-lookup"><span data-stu-id="82105-132">Configuring Graph connector agent</span></span>

<span data-ttu-id="82105-133">为代理创建应用后，必须使用适当的身份验证详细信息配置代理。</span><span class="sxs-lookup"><span data-stu-id="82105-133">Once you have created the App for the agent, you must configure the agent with appropriate authentication details.</span></span>

<span data-ttu-id="82105-134">可以按以下形式之一提供身份验证详细信息。</span><span class="sxs-lookup"><span data-stu-id="82105-134">Authentication details can be provided in one of the following forms.</span></span>

### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="82105-135">配置客户端机密以进行身份验证</span><span class="sxs-lookup"><span data-stu-id="82105-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="82105-136">转到 [Azure 门户](https://portal.azure.com) ，并使用管理员凭据登录租户。</span><span class="sxs-lookup"><span data-stu-id="82105-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="82105-137">从导航窗格中打开 " **应用注册** "，然后转到相应的应用程序。</span><span class="sxs-lookup"><span data-stu-id="82105-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="82105-138">在 " **管理**" 下，选择 " **证书和密码**"。</span><span class="sxs-lookup"><span data-stu-id="82105-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="82105-139">选择 " **新建客户端密码** "，然后选择密码的有效期。</span><span class="sxs-lookup"><span data-stu-id="82105-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="82105-140">复制生成的机密并将其保存，因为它将不会再次显示。</span><span class="sxs-lookup"><span data-stu-id="82105-140">Copy the generated secret and save it because it will not be shown again.</span></span>
4. <span data-ttu-id="82105-141">使用此客户端密码和应用程序 ID 配置代理。</span><span class="sxs-lookup"><span data-stu-id="82105-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="82105-142">不要在代理的 " **名称** " 字段中使用任何空格。</span><span class="sxs-lookup"><span data-stu-id="82105-142">Do not use any blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="82105-143">接受字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="82105-143">Alpha numeric characters are accepted.</span></span>

## <a name="using-thumbprint-certificate-for-authentication"></a><span data-ttu-id="82105-144">使用指纹证书进行身份验证</span><span class="sxs-lookup"><span data-stu-id="82105-144">Using thumbprint certificate for authentication</span></span>

<span data-ttu-id="82105-145">如果已通过 [配置客户端密码进行身份验证](#configuring-the-client-secret-for-authentication) 来配置身份验证详细信息，则可以直接跳转到 [安装程序概述](configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="82105-145">If you have already configured the authentication details by following [Configuring the client secret for authentication](#configuring-the-client-secret-for-authentication) , then you can jump directly to [Setup overview](configure-connector.md).</span></span>

1. <span data-ttu-id="82105-146">打开 " **应用注册** "，然后从导航窗格中选择 " **证书和密码** "。</span><span class="sxs-lookup"><span data-stu-id="82105-146">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="82105-147">复制证书指纹。</span><span class="sxs-lookup"><span data-stu-id="82105-147">Copy the certificate thumbprint.</span></span>
<span data-ttu-id="82105-148">![在左窗格中选择了 "证书和密码" 时的 thumbrint 证书列表](media/onprem-agent/certificates.png)</span><span class="sxs-lookup"><span data-stu-id="82105-148">![List of thumbrint certificates when Certificates and secrets is selected in the left pane](media/onprem-agent/certificates.png)</span></span>
2. <span data-ttu-id="82105-149">使用客户端密码或指纹来注册 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="82105-149">Use either the client secret or thumbprint to register the Graph connector agent.</span></span>
<span data-ttu-id="82105-150">![注册表单，询问名称、应用程序 id、凭据类型和证书](media/onprem-agent/register.png)</span><span class="sxs-lookup"><span data-stu-id="82105-150">![Register form asking for name, app id, credential type, and certificate](media/onprem-agent/register.png)</span></span>
