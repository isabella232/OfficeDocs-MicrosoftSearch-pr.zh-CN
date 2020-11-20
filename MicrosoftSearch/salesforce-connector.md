---
title: 用于 Microsoft 搜索的 Salesforce 连接器
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
description: 设置用于 Microsoft 搜索的 Salesforce 连接器
ms.openlocfilehash: 149d1d9a297e09e9b895aeb0947c7ff4a3cbdf84
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367646"
---
# <a name="salesforce-connector-preview"></a><span data-ttu-id="04b59-103"> (预览的 Salesforce 连接器) </span><span class="sxs-lookup"><span data-stu-id="04b59-103">Salesforce connector (preview)</span></span>

<span data-ttu-id="04b59-104">使用 Salesforce 图形连接器，组织可以在你的 Salesforce 实例中索引联系人、商机、潜在客户和帐户对象。</span><span class="sxs-lookup"><span data-stu-id="04b59-104">With the Salesforce Graph connector, your organization can index Contacts, Opportunities, Leads and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="04b59-105">在从 Salesforce 配置连接器和索引内容之后，最终用户可以从任何 Microsoft Search client 中搜索这些项目。</span><span class="sxs-lookup"><span data-stu-id="04b59-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

<span data-ttu-id="04b59-106">本文适用于 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理员或任何配置、运行和监控 Salesforce 连接器的人。</span><span class="sxs-lookup"><span data-stu-id="04b59-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors a Salesforce connector.</span></span> <span data-ttu-id="04b59-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="04b59-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="04b59-108">目前，Salesforce Graph 连接器支持夏季 ' 19 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="04b59-108">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="connection-settings"></a><span data-ttu-id="04b59-109">连接设置</span><span class="sxs-lookup"><span data-stu-id="04b59-109">Connection settings</span></span>

<span data-ttu-id="04b59-110">若要连接到您的 Salesforce 实例，需要您的 Salesforce 实例 URL、客户端 ID 和 OAuth 身份验证的客户端密码。</span><span class="sxs-lookup"><span data-stu-id="04b59-110">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="04b59-111">以下步骤介绍了您或您的 Salesforce 管理员如何从 Salesforce 帐户获取此信息：</span><span class="sxs-lookup"><span data-stu-id="04b59-111">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="04b59-112">登录到您的 Salesforce 实例，然后转到 "设置"</span><span class="sxs-lookup"><span data-stu-id="04b59-112">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="04b59-113">导航到 "应用程序-> 应用程序管理器"。</span><span class="sxs-lookup"><span data-stu-id="04b59-113">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="04b59-114">选择 " **新建已连接的应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="04b59-114">Select **New connected app**.</span></span>

- <span data-ttu-id="04b59-115">完成 "API" 部分，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04b59-115">Complete the API section as follows:</span></span>

    - <span data-ttu-id="04b59-116">选中 " **启用 Oauth 设置**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="04b59-116">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="04b59-117">将回调 URL 指定为： [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="04b59-117">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="04b59-118">选择 "这些必需的 OAuth 作用域"。</span><span class="sxs-lookup"><span data-stu-id="04b59-118">Select these required OAuth scopes.</span></span> 

        - <span data-ttu-id="04b59-119">访问和管理您的数据 (api) </span><span class="sxs-lookup"><span data-stu-id="04b59-119">Access and manage your data (api)</span></span> 

        - <span data-ttu-id="04b59-120">随时以您的身份执行请求 (refresh_token，offline_access) </span><span class="sxs-lookup"><span data-stu-id="04b59-120">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span> 

    - <span data-ttu-id="04b59-121">选中 " **需要 web 服务器流的密码**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="04b59-121">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="04b59-122">保存应用程序。</span><span class="sxs-lookup"><span data-stu-id="04b59-122">Save the app.</span></span>
    
      ![Salesforce 实例中的 API 部分，管理员输入了上面列出的所有必需配置。](media/salesforce-connector/sf1.png)

- <span data-ttu-id="04b59-124">复制使用者密钥和使用者密码。</span><span class="sxs-lookup"><span data-stu-id="04b59-124">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="04b59-125">当您在 Microsoft 365 管理门户中配置 Graph 连接器的连接设置时，这些设置将用作客户端 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="04b59-125">These will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  ![管理员提交所有必需的配置后，Salesforce 实例中的 API 部分返回的结果。](media/salesforce-connector/clientsecret.png)
- <span data-ttu-id="04b59-128">在关闭您的 Salesforce 实例之前，请执行以下步骤以确保刷新令牌不会过期：</span><span class="sxs-lookup"><span data-stu-id="04b59-128">Before closing your Salesforce instance, perform the following steps to ensure that refresh tokens do not expire:</span></span>
    - <span data-ttu-id="04b59-129">转到应用程序-> 应用程序管理器</span><span class="sxs-lookup"><span data-stu-id="04b59-129">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="04b59-130">查找刚创建的应用程序，然后选择右侧的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="04b59-130">Find the app you just created and select the drop down on the right.</span></span> <span data-ttu-id="04b59-131">选择 " **管理**</span><span class="sxs-lookup"><span data-stu-id="04b59-131">Select **Manage**</span></span>
    - <span data-ttu-id="04b59-132">选择 **编辑策略**</span><span class="sxs-lookup"><span data-stu-id="04b59-132">Select **edit policies**</span></span>
    - <span data-ttu-id="04b59-133">对于 "刷新令牌" 策略，请选择 " **刷新令牌" 在废除前有效**</span><span class="sxs-lookup"><span data-stu-id="04b59-133">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  ![选择名为 "刷新令牌在吊销前有效的刷新令牌策略"](media/salesforce-connector/oauthpolicies.png)

<span data-ttu-id="04b59-135">现在，您可以使用 [M365 管理中心](https://admin.microsoft.com/) 完成 Graph 连接器的其余设置过程。</span><span class="sxs-lookup"><span data-stu-id="04b59-135">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>  

<span data-ttu-id="04b59-136">为您的 Graph 连接器配置连接设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04b59-136">Configure the Connection settings for your Graph connector as follows:</span></span>

- <span data-ttu-id="04b59-137">对于实例 URL，请使用 https：//[域]. 我的 .com，其中的域将成为您的组织的 Salesforce 域。</span><span class="sxs-lookup"><span data-stu-id="04b59-137">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span> 
- <span data-ttu-id="04b59-138">输入你从 Salesforce 实例获取的客户端 ID 和客户端密码，并选择 "登录"。</span><span class="sxs-lookup"><span data-stu-id="04b59-138">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>
- <span data-ttu-id="04b59-139">如果这是你第一次尝试使用这些设置登录，你将看到一个弹出窗口，要求你使用管理员用户名和密码登录到 Salesforce。</span><span class="sxs-lookup"><span data-stu-id="04b59-139">If this is the first time you have attempted to Sign in with these settings, you will get a pop up asking you to login to Salesforce with your admin username and password.</span></span> <span data-ttu-id="04b59-140">下面的屏幕截图显示弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="04b59-140">The screenshot below shows the popup.</span></span> <span data-ttu-id="04b59-141">输入你的凭据，然后选择 "登录"。</span><span class="sxs-lookup"><span data-stu-id="04b59-141">Enter your credentials and select Log in.</span></span>

  ![登录弹出窗口要求输入用户名和密码。](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="04b59-143">如果没有出现弹出窗口，则可能在浏览器中被阻止，因此您必须允许弹出窗口和重定向。</span><span class="sxs-lookup"><span data-stu-id="04b59-143">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

  >[!NOTE]
  ><span data-ttu-id="04b59-144">如果您的组织使用 (SSO) 的单一登录，则可以在登录接口的右下角选择 " **使用自** 定义域"。</span><span class="sxs-lookup"><span data-stu-id="04b59-144">If your organization uses single sign-on (SSO), you can select **Use Custom Domain** in the bottom, right-hand corner of the login interface.</span></span> <span data-ttu-id="04b59-145">输入域，然后选择 " **继续**"。</span><span class="sxs-lookup"><span data-stu-id="04b59-145">Enter the domain and then select **Continue**.</span></span> <span data-ttu-id="04b59-146">它将转到您的组织特定登录页，您可以在其中使用 SSO 登录选项。</span><span class="sxs-lookup"><span data-stu-id="04b59-146">It will go to your organization specific login page where you will have an option to login with SSO.</span></span>

- <span data-ttu-id="04b59-147">通过在下面的屏幕截图中搜索显示 "连接成功" 的绿色标题，检查连接是否成功。</span><span class="sxs-lookup"><span data-stu-id="04b59-147">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  ![成功登录的屏幕截图。](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="04b59-150">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="04b59-150">Manage search permissions</span></span>
<span data-ttu-id="04b59-151">你将需要选择哪些用户将看到来自此数据源的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="04b59-151">You will need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="04b59-152">如果仅允许某些 Azure Active Directory (Azure AD) 或非 Azure AD 用户查看搜索结果，则需要映射这些标识。</span><span class="sxs-lookup"><span data-stu-id="04b59-152">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, you will then need to map the identities.</span></span>

### <a name="select-permissions"></a><span data-ttu-id="04b59-153">选择权限</span><span class="sxs-lookup"><span data-stu-id="04b59-153">Select Permissions</span></span>
<span data-ttu-id="04b59-154">您可以选择从您的 Salesforce 实例中)  (Acl 中引入访问控制列表，也可以允许组织中的所有人查看此数据源中的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="04b59-154">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or you can allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="04b59-155">Acl 可以包含 Azure Active Directory (AAD) 标识 (从 Azure AD 联合到 Salesforce) 的用户、非 Azure AD 标识 (在 Azure AD) 中具有相应标识的本机 Salesforce 用户，或两者兼有。</span><span class="sxs-lookup"><span data-stu-id="04b59-155">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

![选择管理员已完成的 "权限" 屏幕。管理员已选择 "只有可访问此数据源的人员" 选项，并且还从 "标识类型" 的下拉菜单中选择了 "AAD"。](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a><span data-ttu-id="04b59-157">映射非 AAD 标识</span><span class="sxs-lookup"><span data-stu-id="04b59-157">Map non-AAD identities</span></span> 
<span data-ttu-id="04b59-158">如果你选择从 Salesforce 实例中引入 ACL 并为标识类型选择了 "非 AAD"，请参阅 [映射你的非 AZURE AD 标识](map-non-aad.md) ，了解有关标识标识的说明。</span><span class="sxs-lookup"><span data-stu-id="04b59-158">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="map-aad-identities"></a><span data-ttu-id="04b59-159">映射 AAD 标识</span><span class="sxs-lookup"><span data-stu-id="04b59-159">Map AAD identities</span></span>
<span data-ttu-id="04b59-160">如果你选择从 Salesforce 实例中引入 ACL 并为标识类型选择了 "AAD"，请参阅 [映射 AZURE AD 标识](map-aad.md) 以获取有关映射标识的说明。</span><span class="sxs-lookup"><span data-stu-id="04b59-160">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="04b59-161">若要了解如何设置适用于 Salesforce 的 Azure AD SSO，请参阅本 [教程](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/salesforce-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="04b59-161">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="04b59-162">分配属性标签</span><span class="sxs-lookup"><span data-stu-id="04b59-162">Assign property labels</span></span> 
<span data-ttu-id="04b59-163">通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。</span><span class="sxs-lookup"><span data-stu-id="04b59-163">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="04b59-164">虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。</span><span class="sxs-lookup"><span data-stu-id="04b59-164">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span> <span data-ttu-id="04b59-165">默认情况下，某些标签（如 "Title"、"URL"、"CreatedBy" 和 "LastModifiedBy"）已分配了源属性。</span><span class="sxs-lookup"><span data-stu-id="04b59-165">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

![分配显示默认源属性的属性标签屏幕。](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a><span data-ttu-id="04b59-167">管理架构</span><span class="sxs-lookup"><span data-stu-id="04b59-167">Manage Schema</span></span>
<span data-ttu-id="04b59-168">您可以选择应为其编制索引的源属性，以便它们可以显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="04b59-168">You can select what source properties should be indexed so that they can show up in search results.</span></span> <span data-ttu-id="04b59-169">默认情况下，连接向导根据一组源属性选择一个搜索架构。</span><span class="sxs-lookup"><span data-stu-id="04b59-169">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="04b59-170">您可以通过选中 "搜索架构" 页中每个属性和属性的复选框对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="04b59-170">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="04b59-171">搜索架构属性包括搜索、查询、检索和优化。</span><span class="sxs-lookup"><span data-stu-id="04b59-171">Search schema attributes include Search, Query, Retrieve and Refine.</span></span> <span data-ttu-id="04b59-172">优化允许您定义可在以后用作搜索体验中的自定义精简条件或筛选器的属性。</span><span class="sxs-lookup"><span data-stu-id="04b59-172">Refine allows you to define the properties which can be later used as custom refiners or filters in the search experience.</span></span>  

![为每个 source 属性选择架构。](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="04b59-175">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="04b59-175">Set the refresh schedule</span></span>

<span data-ttu-id="04b59-176">Salesforce 连接器仅支持当前完全爬网的刷新计划。</span><span class="sxs-lookup"><span data-stu-id="04b59-176">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="04b59-177">完全爬网可查找以前同步到 Microsoft 搜索索引的已删除对象和用户。</span><span class="sxs-lookup"><span data-stu-id="04b59-177">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="04b59-178">建议的日程安排为一周完全爬网。</span><span class="sxs-lookup"><span data-stu-id="04b59-178">The recommended schedule is one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="04b59-179">限制</span><span class="sxs-lookup"><span data-stu-id="04b59-179">Limitations</span></span>

- <span data-ttu-id="04b59-180">Graph 连接器目前不支持基于区域的共享和使用 Salesforce 中的个人组共享基于区域的共享和共享 Apex。</span><span class="sxs-lookup"><span data-stu-id="04b59-180">The Graph connector does not currently support Apex based , territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="04b59-181">在 Salesforce API 中存在一个已知的错误，图连接器使用的是潜在客户的专用组织范围默认值在当前未生效的情况。</span><span class="sxs-lookup"><span data-stu-id="04b59-181">There is a known bug in the Salesforce API that the Graph connector uses where the private org wide defaults for leads is not honored currently.</span></span>  
- <span data-ttu-id="04b59-182">如果字段具有字段级安全性 (FLS) 设置配置文件，Graph 连接器将不会为该 Salesforce 组织中的任何配置文件摄取该字段。因此，用户将无法搜索这些域的值，也不会显示在结果中。</span><span class="sxs-lookup"><span data-stu-id="04b59-182">If a field has field level security (FLS) set for a profile, the Graph connector will not ingest that field for any profiles in that Salesforce org. Users will thus not be able to search on values for those fields, nor will it  show up in the results.</span></span>  
- <span data-ttu-id="04b59-183">在 "管理架构" 屏幕中，这些常用的标准属性名称列出一次，所做的选择使其可查询、搜索和检索适用于所有或无。</span><span class="sxs-lookup"><span data-stu-id="04b59-183">In the Manage Schema screen these common standard property names are listed once and the selection done to make them queryable, searchable and retrievable apply to all or none.</span></span>
    - <span data-ttu-id="04b59-184">名称</span><span class="sxs-lookup"><span data-stu-id="04b59-184">Name</span></span>
    - <span data-ttu-id="04b59-185">URL</span><span class="sxs-lookup"><span data-stu-id="04b59-185">Url</span></span> 
    - <span data-ttu-id="04b59-186">说明</span><span class="sxs-lookup"><span data-stu-id="04b59-186">Description</span></span>
    - <span data-ttu-id="04b59-187">Fax</span><span class="sxs-lookup"><span data-stu-id="04b59-187">Fax</span></span>
    - <span data-ttu-id="04b59-188">电话版</span><span class="sxs-lookup"><span data-stu-id="04b59-188">Phone</span></span>
    - <span data-ttu-id="04b59-189">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="04b59-189">MobilePhone</span></span>
    - <span data-ttu-id="04b59-190">电子邮件</span><span class="sxs-lookup"><span data-stu-id="04b59-190">Email</span></span>
    - <span data-ttu-id="04b59-191">类型</span><span class="sxs-lookup"><span data-stu-id="04b59-191">Type</span></span>
    - <span data-ttu-id="04b59-192">标题</span><span class="sxs-lookup"><span data-stu-id="04b59-192">Title</span></span>
    - <span data-ttu-id="04b59-193">AccountId</span><span class="sxs-lookup"><span data-stu-id="04b59-193">AccountId</span></span>
    - <span data-ttu-id="04b59-194">AccountName</span><span class="sxs-lookup"><span data-stu-id="04b59-194">AccountName</span></span>
    - <span data-ttu-id="04b59-195">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="04b59-195">AccountUrl</span></span>
    - <span data-ttu-id="04b59-196">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="04b59-196">AccountOwner</span></span>
    - <span data-ttu-id="04b59-197">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="04b59-197">AccountOwnerUrl</span></span>
    - <span data-ttu-id="04b59-198">所有者</span><span class="sxs-lookup"><span data-stu-id="04b59-198">Owner</span></span>
    - <span data-ttu-id="04b59-199">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="04b59-199">OwnerUrl</span></span>
    - <span data-ttu-id="04b59-200">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="04b59-200">CreatedBy</span></span> 
    - <span data-ttu-id="04b59-201">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="04b59-201">CreatedByUrl</span></span> 
    - <span data-ttu-id="04b59-202">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="04b59-202">LastModifiedBy</span></span> 
    - <span data-ttu-id="04b59-203">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="04b59-203">LastModifiedByUrl</span></span> 
    - <span data-ttu-id="04b59-204">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="04b59-204">LastModifiedDate</span></span>
    - <span data-ttu-id="04b59-205">ObjectName</span><span class="sxs-lookup"><span data-stu-id="04b59-205">ObjectName</span></span> 
