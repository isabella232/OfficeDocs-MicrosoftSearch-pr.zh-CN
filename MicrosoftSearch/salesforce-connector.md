---
title: Microsoft 搜索的 Salesforce Graph 连接器
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 为 Microsoft 搜索设置 Salesforce Graph 连接器
ms.openlocfilehash: 86140a4650593e08188f171be54f1753b73ecf7a
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508820"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="92ee5-103">Salesforce Graph 连接器 (预览) </span><span class="sxs-lookup"><span data-stu-id="92ee5-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="92ee5-104">Salesforce Graph 连接器允许组织索引 Salesforce 实例中的联系人、机会、线索和帐户对象。</span><span class="sxs-lookup"><span data-stu-id="92ee5-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="92ee5-105">配置 Salesforce 中的连接器和索引内容后，最终用户可以从任何 Microsoft 搜索客户端搜索这些项目。</span><span class="sxs-lookup"><span data-stu-id="92ee5-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="92ee5-106">阅读 [**Graph 连接器的安装程序文章**](configure-connector.md) ，了解一般 Graph 连接器设置说明。</span><span class="sxs-lookup"><span data-stu-id="92ee5-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="92ee5-107">本文适用于配置、运行和监视 Salesforce Graph 连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="92ee5-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="92ee5-108">它补充了常规安装过程，并显示了仅适用于 Salesforce Graph 连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="92ee5-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="92ee5-109">本文还包括有关 [限制的信息](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="92ee5-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="92ee5-110">Salesforce Graph 连接器当前支持"19 世纪 19 日"或更高版本。</span><span class="sxs-lookup"><span data-stu-id="92ee5-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="92ee5-111">在开始使用之前</span><span class="sxs-lookup"><span data-stu-id="92ee5-111">Before you get started</span></span>

<span data-ttu-id="92ee5-112">若要连接到 Salesforce 实例，需要 Salesforce 实例 URL、客户端 ID 和客户端密码进行 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="92ee5-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="92ee5-113">以下步骤介绍了你或 Salesforce 管理员如何从 Salesforce 帐户获取此信息：</span><span class="sxs-lookup"><span data-stu-id="92ee5-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="92ee5-114">登录到 Salesforce 实例并转到安装程序</span><span class="sxs-lookup"><span data-stu-id="92ee5-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="92ee5-115">导航到应用 ->应用管理器。</span><span class="sxs-lookup"><span data-stu-id="92ee5-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="92ee5-116">选择 **"新建已连接的应用"。**</span><span class="sxs-lookup"><span data-stu-id="92ee5-116">Select **New connected app**.</span></span>

- <span data-ttu-id="92ee5-117">完成 API 部分，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92ee5-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="92ee5-118">选中"启用 **Oauth 设置"复选框**。</span><span class="sxs-lookup"><span data-stu-id="92ee5-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="92ee5-119">将回调 URL 指定为： [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="92ee5-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="92ee5-120">选择所需的 OAuth 作用域。</span><span class="sxs-lookup"><span data-stu-id="92ee5-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="92ee5-121">访问和管理你的数据 (api) </span><span class="sxs-lookup"><span data-stu-id="92ee5-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="92ee5-122">随时代表您执行请求， (refresh_token offline_access) </span><span class="sxs-lookup"><span data-stu-id="92ee5-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="92ee5-123">选中 Web 服务器 **流的"需要密码"复选框**。</span><span class="sxs-lookup"><span data-stu-id="92ee5-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="92ee5-124">保存应用。</span><span class="sxs-lookup"><span data-stu-id="92ee5-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="92ee5-125">![管理员输入上面列出的所有必需配置后，Salesforce 实例中的 API 部分。](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="92ee5-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="92ee5-126">复制使用者密钥和使用者密码。</span><span class="sxs-lookup"><span data-stu-id="92ee5-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="92ee5-127">在 Microsoft 365 管理门户中为 Graph 连接器配置连接设置时，此信息将用作客户端 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="92ee5-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="92ee5-128">![管理员提交所有必需配置后，Salesforce 实例中的 API 部分返回的结果。</span><span class="sxs-lookup"><span data-stu-id="92ee5-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="92ee5-129">使用者密钥位于左列的顶部，使用者密码位于右列的顶部。](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="92ee5-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="92ee5-130">在关闭 Salesforce 实例之前，请执行以下步骤以确保刷新令牌不会过期：</span><span class="sxs-lookup"><span data-stu-id="92ee5-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="92ee5-131">转到应用 ->应用管理器</span><span class="sxs-lookup"><span data-stu-id="92ee5-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="92ee5-132">找到你创建的应用，然后选择右侧下拉列表。</span><span class="sxs-lookup"><span data-stu-id="92ee5-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="92ee5-133">选择 **"管理"**</span><span class="sxs-lookup"><span data-stu-id="92ee5-133">Select **Manage**</span></span>
    - <span data-ttu-id="92ee5-134">选择 **编辑策略**</span><span class="sxs-lookup"><span data-stu-id="92ee5-134">Select **edit policies**</span></span>
    - <span data-ttu-id="92ee5-135">对于刷新令牌策略，选择 **"刷新令牌在吊销前有效"**</span><span class="sxs-lookup"><span data-stu-id="92ee5-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="92ee5-136">![选择名为"刷新令牌在吊销前有效"的刷新令牌策略](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="92ee5-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="92ee5-137">现在，可以使用 [M365 管理](https://admin.microsoft.com/) 中心完成 Graph 连接器的其余设置过程。</span><span class="sxs-lookup"><span data-stu-id="92ee5-137">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="92ee5-138">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="92ee5-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="92ee5-139">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="92ee5-139">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="92ee5-140">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="92ee5-140">Step 2: Name the connection</span></span>

<span data-ttu-id="92ee5-141">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="92ee5-141">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="92ee5-142">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="92ee5-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="92ee5-143">对于实例 URL，请使用 https：//[domain].my.salesforce.com，其中域是组织的 Salesforce 域。</span><span class="sxs-lookup"><span data-stu-id="92ee5-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="92ee5-144">输入从 Salesforce 实例获取的客户端 ID 和客户端密码，然后选择"登录"。</span><span class="sxs-lookup"><span data-stu-id="92ee5-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="92ee5-145">首次尝试使用这些设置登录时，你收到一个弹出窗口，要求您使用管理员用户名和密码登录 Salesforce。</span><span class="sxs-lookup"><span data-stu-id="92ee5-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="92ee5-146">下面的屏幕截图显示了弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="92ee5-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="92ee5-147">输入凭据并选择"登录"。</span><span class="sxs-lookup"><span data-stu-id="92ee5-147">Enter your credentials and select "Log In".</span></span>

  ![登录弹出窗口，要求输入用户名和密码。](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="92ee5-149">如果未显示弹出窗口，它可能在浏览器中被阻止，因此必须允许弹出窗口和重定向。</span><span class="sxs-lookup"><span data-stu-id="92ee5-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="92ee5-150">通过搜索显示"连接成功"的绿色横幅来检查连接是否成功，如以下屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="92ee5-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="92ee5-151">![成功登录的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="92ee5-151">![Screenshot of successful login.</span></span> <span data-ttu-id="92ee5-152">显示"连接成功"的绿色横幅位于 Salesforce 实例 URL 的字段下](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="92ee5-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="92ee5-153">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="92ee5-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="92ee5-154">你需要选择哪些用户将看到此数据源中的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="92ee5-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="92ee5-155">如果你只允许某些 Azure Active Directory (Azure AD) 或非 Azure AD 用户查看搜索结果，请确保映射标识。</span><span class="sxs-lookup"><span data-stu-id="92ee5-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

## <a name="step-4a-select-permissions"></a><span data-ttu-id="92ee5-156">步骤 4a：选择权限</span><span class="sxs-lookup"><span data-stu-id="92ee5-156">Step 4a: Select permissions</span></span>

<span data-ttu-id="92ee5-157">你可以选择从 Salesforce 实例 (ACL) 访问控制列表，或允许组织中的每个人查看来自此数据源的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="92ee5-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="92ee5-158">ACL 可以包括 Azure Active Directory (AAD) 标识、从 Azure AD 联合到 Salesforce) 的 (用户、在 Azure AD) 中具有相应标识的非 Azure AD 标识 (本机 Salesforce 用户，或两者。</span><span class="sxs-lookup"><span data-stu-id="92ee5-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="92ee5-159">如果使用第三方标识提供程序（如 Ping ID 或 secureAuth），则应该选择"非 AAD"作为标识类型。</span><span class="sxs-lookup"><span data-stu-id="92ee5-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="92ee5-160">![选择管理员已完成的权限屏幕。管理员已选择"仅有权访问此数据源的人"选项，并且还从标识类型的下拉菜单中选择了"AAD"。](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="92ee5-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="92ee5-161">如果选择从 Salesforce 实例中获取 ACL，并且为标识类型选择了"非 AAD"，请参阅"映射非 [Azure AD](map-non-aad.md) 标识"，获取有关映射标识的说明。</span><span class="sxs-lookup"><span data-stu-id="92ee5-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

## <a name="step-4b-map-aad-identities"></a><span data-ttu-id="92ee5-162">步骤 4b：映射 AAD 标识</span><span class="sxs-lookup"><span data-stu-id="92ee5-162">Step 4b: Map AAD identities</span></span>

<span data-ttu-id="92ee5-163">如果选择从 Salesforce 实例中获取 ACL，并且为标识类型选择了"AAD"，请参阅"映射 [Azure AD 标识](map-aad.md) "，获取有关映射标识的说明。</span><span class="sxs-lookup"><span data-stu-id="92ee5-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="92ee5-164">若要了解如何为 Salesforce 设置 Azure AD SSO，请参阅 [本教程](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="92ee5-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="92ee5-165">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="92ee5-165">Step 5: Assign property labels</span></span>

<span data-ttu-id="92ee5-166">可以通过从选项菜单中选择来为每个标签分配源属性。</span><span class="sxs-lookup"><span data-stu-id="92ee5-166">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="92ee5-167">虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更好的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="92ee5-167">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="92ee5-168">默认情况下，某些标签（如"Title"、"URL"、"CreatedBy"和"LastModifiedBy"）已分配有源属性。</span><span class="sxs-lookup"><span data-stu-id="92ee5-168">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="92ee5-169">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="92ee5-169">Step 6: Manage schema</span></span>

<span data-ttu-id="92ee5-170">可以选择应索引哪些源属性，以便它们在搜索结果中显示。</span><span class="sxs-lookup"><span data-stu-id="92ee5-170">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="92ee5-171">默认情况下，连接向导基于一组源属性选择搜索架构。</span><span class="sxs-lookup"><span data-stu-id="92ee5-171">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="92ee5-172">您可以通过选中搜索架构页中每个属性和属性的复选框来修改它。</span><span class="sxs-lookup"><span data-stu-id="92ee5-172">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="92ee5-173">搜索架构属性包括搜索、查询、检索和优化。</span><span class="sxs-lookup"><span data-stu-id="92ee5-173">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="92ee5-174">利用优化，您可以定义稍后可在搜索体验中用作自定义精简程序或筛选器的属性。</span><span class="sxs-lookup"><span data-stu-id="92ee5-174">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="92ee5-175">![选择每个源属性的架构。</span><span class="sxs-lookup"><span data-stu-id="92ee5-175">![Select the schema for each source property.</span></span> <span data-ttu-id="92ee5-176">选项包括查询、搜索、检索和优化](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="92ee5-176">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="92ee5-177">步骤 7：设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="92ee5-177">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="92ee5-178">Salesforce 连接器当前仅支持完全爬网的刷新计划。</span><span class="sxs-lookup"><span data-stu-id="92ee5-178">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="92ee5-179">完全爬网将查找已删除的对象和以前同步到 Microsoft 搜索索引的用户。</span><span class="sxs-lookup"><span data-stu-id="92ee5-179">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="92ee5-180">建议的完全爬网计划为一周。</span><span class="sxs-lookup"><span data-stu-id="92ee5-180">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="92ee5-181">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="92ee5-181">Step 8: Review connection</span></span>

<span data-ttu-id="92ee5-182">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="92ee5-182">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="92ee5-183">限制</span><span class="sxs-lookup"><span data-stu-id="92ee5-183">Limitations</span></span>

- <span data-ttu-id="92ee5-184">Graph 连接器当前不支持使用 Salesforce 中的个人组进行基于 Apex、基于区域共享和共享。</span><span class="sxs-lookup"><span data-stu-id="92ee5-184">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="92ee5-185">Graph 连接器使用的 Salesforce API 中存在一个已知 Bug，其中当前不采用潜在客户的专用组织范围的默认值。</span><span class="sxs-lookup"><span data-stu-id="92ee5-185">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="92ee5-186">如果字段的字段级别 (为配置文件) FLS，则 Graph 连接器不会为 Salesforce 组织的任何配置文件输入该字段。因此，用户将无法搜索这些字段的值，也不会在结果中显示。</span><span class="sxs-lookup"><span data-stu-id="92ee5-186">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="92ee5-187">在"管理架构"屏幕中，这些常用标准属性名称列出一次，选项为"查询"、"**搜索**"、"检索"和"**精简**"，并应用于全部或全部不应用。</span><span class="sxs-lookup"><span data-stu-id="92ee5-187">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="92ee5-188">名称</span><span class="sxs-lookup"><span data-stu-id="92ee5-188">Name</span></span>
    - <span data-ttu-id="92ee5-189">URL</span><span class="sxs-lookup"><span data-stu-id="92ee5-189">Url</span></span>
    - <span data-ttu-id="92ee5-190">说明</span><span class="sxs-lookup"><span data-stu-id="92ee5-190">Description</span></span>
    - <span data-ttu-id="92ee5-191">Fax</span><span class="sxs-lookup"><span data-stu-id="92ee5-191">Fax</span></span>
    - <span data-ttu-id="92ee5-192">电话版</span><span class="sxs-lookup"><span data-stu-id="92ee5-192">Phone</span></span>
    - <span data-ttu-id="92ee5-193">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="92ee5-193">MobilePhone</span></span>
    - <span data-ttu-id="92ee5-194">电子邮件</span><span class="sxs-lookup"><span data-stu-id="92ee5-194">Email</span></span>
    - <span data-ttu-id="92ee5-195">类型</span><span class="sxs-lookup"><span data-stu-id="92ee5-195">Type</span></span>
    - <span data-ttu-id="92ee5-196">标题</span><span class="sxs-lookup"><span data-stu-id="92ee5-196">Title</span></span>
    - <span data-ttu-id="92ee5-197">AccountId</span><span class="sxs-lookup"><span data-stu-id="92ee5-197">AccountId</span></span>
    - <span data-ttu-id="92ee5-198">AccountName</span><span class="sxs-lookup"><span data-stu-id="92ee5-198">AccountName</span></span>
    - <span data-ttu-id="92ee5-199">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="92ee5-199">AccountUrl</span></span>
    - <span data-ttu-id="92ee5-200">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="92ee5-200">AccountOwner</span></span>
    - <span data-ttu-id="92ee5-201">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="92ee5-201">AccountOwnerUrl</span></span>
    - <span data-ttu-id="92ee5-202">所有者</span><span class="sxs-lookup"><span data-stu-id="92ee5-202">Owner</span></span>
    - <span data-ttu-id="92ee5-203">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="92ee5-203">OwnerUrl</span></span>
    - <span data-ttu-id="92ee5-204">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="92ee5-204">CreatedBy</span></span>
    - <span data-ttu-id="92ee5-205">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="92ee5-205">CreatedByUrl</span></span>
    - <span data-ttu-id="92ee5-206">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="92ee5-206">LastModifiedBy</span></span>
    - <span data-ttu-id="92ee5-207">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="92ee5-207">LastModifiedByUrl</span></span>
    - <span data-ttu-id="92ee5-208">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="92ee5-208">LastModifiedDate</span></span>
    - <span data-ttu-id="92ee5-209">ObjectName</span><span class="sxs-lookup"><span data-stu-id="92ee5-209">ObjectName</span></span>
