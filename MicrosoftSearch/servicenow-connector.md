---
title: 用于 Microsoft 搜索的 ServiceNow 连接器
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置用于 Microsoft 搜索的 ServiceNow 连接器
ms.openlocfilehash: 520232f8055d5432ccb96a840a9466ae6a4e3b1a
ms.sourcegitcommit: ac4e261c01262be747341f810d2d1faf220d3961
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "49382557"
---
# <a name="servicenow-connector"></a><span data-ttu-id="7ca97-103">ServiceNow 连接器</span><span class="sxs-lookup"><span data-stu-id="7ca97-103">ServiceNow connector</span></span>

<span data-ttu-id="7ca97-104">使用 ServiceNow 连接器，组织可以对所有用户可见或受组织内的用户条件权限限制的知识库文章编制索引。</span><span class="sxs-lookup"><span data-stu-id="7ca97-104">With the ServiceNow connector, your organization can index knowledge-base articles that are visible to all users or restricted with user criteria permissions within your organization.</span></span> <span data-ttu-id="7ca97-105">在从 ServiceNow 配置连接器和索引内容之后，最终用户可以从任何 Microsoft Search client 中搜索这些文章。</span><span class="sxs-lookup"><span data-stu-id="7ca97-105">After you configure the connector and index content from ServiceNow, end users can search for those articles from any Microsoft Search client.</span></span>  

<span data-ttu-id="7ca97-106">本文适用于 Microsoft 365 管理员或任何配置、运行和监视 ServiceNow 连接器的人。</span><span class="sxs-lookup"><span data-stu-id="7ca97-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a ServiceNow connector.</span></span> <span data-ttu-id="7ca97-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="7ca97-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

<span data-ttu-id="7ca97-108">了解如何在 microsoft Search 中设置 microsoft [构建的连接器以](https://docs.microsoft.com/microsoftsearch/configure-connector)访问 microsoft 构建的连接器。</span><span class="sxs-lookup"><span data-stu-id="7ca97-108">Learn how to access Microsoft built connectors from [Set up your Microsoft-built connector for Microsoft Search](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span> <span data-ttu-id="7ca97-109">有关特定于 ServiceNow 连接器的特定配置，请见下面一文。</span><span class="sxs-lookup"><span data-stu-id="7ca97-109">ServiceNow connector specific configuration is explained in the article below.</span></span>

## <a name="connection-settings"></a><span data-ttu-id="7ca97-110">连接设置</span><span class="sxs-lookup"><span data-stu-id="7ca97-110">Connection Settings</span></span>
<span data-ttu-id="7ca97-111">若要连接到你的 ServiceNow 数据，你需要组织的 **servicenow 实例 URL**、此帐户的凭据以及用于 OAuth 身份验证的客户端 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="7ca97-111">To connect to your ServiceNow data, you need your organization's **ServiceNow instance URL**, credentials for this account, and the Client ID and Client Secret for OAuth authentication.</span></span>  

<span data-ttu-id="7ca97-112">您的组织的 **ServiceNow 实例 URL** 的外观通常如下所示 **https:// &lt; 您的组织域> service-now.com**。</span><span class="sxs-lookup"><span data-stu-id="7ca97-112">Your organization’s **ServiceNow instance URL** typically looks like **https://&lt;your-organization-domain>.service-now.com**.</span></span> <span data-ttu-id="7ca97-113">除了此 URL，您还需要一个帐户，用于设置与 ServiceNow 的连接，以及允许 Microsoft Search 根据刷新计划定期更新 ServiceNow 中的文章。</span><span class="sxs-lookup"><span data-stu-id="7ca97-113">Along with this URL, you will need an account for setting up the connection to ServiceNow as well as for allowing Microsoft Search to periodically update the articles from ServiceNow based on the refresh schedule.</span></span> <span data-ttu-id="7ca97-114">帐户应至少具有 <em>知识</em> 角色。</span><span class="sxs-lookup"><span data-stu-id="7ca97-114">The account should at least have <em>knowledge</em> role.</span></span> <span data-ttu-id="7ca97-115">[了解如何为 ServiceNow 帐户分配角色](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-115">[Learn how to assign role for ServiceNow accounts](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span>

>[!NOTE]
><span data-ttu-id="7ca97-116">如果要对用户和组标识进行爬网，以在 Microsoft 搜索结果中接受知识库文章的访问权限，则该帐户应具有在 ServiceNow 中读取以下表记录的访问权限：</span><span class="sxs-lookup"><span data-stu-id="7ca97-116">If you want to crawl user and group identities to honor access permissions of knowledge articles in Microsoft Search results, the account should have access to read the following table records in ServiceNow:</span></span>
>* <span data-ttu-id="7ca97-117">kb_uc_can_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="7ca97-117">kb_uc_can_contribute_mtom</span></span>
>* <span data-ttu-id="7ca97-118">kb_uc_can_read_mtom</span><span class="sxs-lookup"><span data-stu-id="7ca97-118">kb_uc_can_read_mtom</span></span>
>* <span data-ttu-id="7ca97-119">kb_uc_cannot_read_mtom</span><span class="sxs-lookup"><span data-stu-id="7ca97-119">kb_uc_cannot_read_mtom</span></span>
>* <span data-ttu-id="7ca97-120">kb_uc_cannot_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="7ca97-120">kb_uc_cannot_contribute_mtom</span></span>
>* <span data-ttu-id="7ca97-121">sys_user</span><span class="sxs-lookup"><span data-stu-id="7ca97-121">sys_user</span></span>
>* <span data-ttu-id="7ca97-122">sys_user_has_role</span><span class="sxs-lookup"><span data-stu-id="7ca97-122">sys_user_has_role</span></span>
>* <span data-ttu-id="7ca97-123">sys_user_grmember</span><span class="sxs-lookup"><span data-stu-id="7ca97-123">sys_user_grmember</span></span>
>* <span data-ttu-id="7ca97-124">user_criteria</span><span class="sxs-lookup"><span data-stu-id="7ca97-124">user_criteria</span></span>
>* <span data-ttu-id="7ca97-125">kb_knowledge_base</span><span class="sxs-lookup"><span data-stu-id="7ca97-125">kb_knowledge_base</span></span>  
> <span data-ttu-id="7ca97-126">您可以为用于连接 Microsoft 搜索的帐户创建和分配角色。</span><span class="sxs-lookup"><span data-stu-id="7ca97-126">You can create and assign a role for the account you use to connect with Microsoft Search.</span></span> <span data-ttu-id="7ca97-127">可以在该角色上分配对表的 "读取" 访问权限。</span><span class="sxs-lookup"><span data-stu-id="7ca97-127">Read access to the tables can be assigned on that role.</span></span> <span data-ttu-id="7ca97-128">若要了解如何设置对表记录的读取访问权限，请参阅 [保护表记录](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-128">To learn about setting read access to table records, see [Securing Table Records](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls).</span></span>

<span data-ttu-id="7ca97-129">若要从 ServiceNow 验证和同步内容，请选择 **以下三** 种受支持的方法之一：</span><span class="sxs-lookup"><span data-stu-id="7ca97-129">To authenticate and sync content from ServiceNow, choose **one of three** supported methods:</span></span> 
1. <span data-ttu-id="7ca97-130">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="7ca97-130">Basic authentication</span></span> 
2. <span data-ttu-id="7ca97-131"> (建议的 ServiceNow OAuth) </span><span class="sxs-lookup"><span data-stu-id="7ca97-131">ServiceNow OAuth (recommended)</span></span>
3. <span data-ttu-id="7ca97-132">Azure AD OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="7ca97-132">Azure AD OpenID Connect</span></span>

#### <a name="basic-authentication"></a><span data-ttu-id="7ca97-133">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="7ca97-133">Basic authentication</span></span>

<span data-ttu-id="7ca97-134">输入具有 **知识** 角色的 ServiceNow 帐户的用户名和密码，以向你的实例进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7ca97-134">Enter the username and password of ServiceNow account with **knowledge** role to authenticate to your instance.</span></span>

#### <a name="servicenow-oauth"></a><span data-ttu-id="7ca97-135">ServiceNow OAuth</span><span class="sxs-lookup"><span data-stu-id="7ca97-135">ServiceNow OAuth</span></span>

<span data-ttu-id="7ca97-136">若要使用 ServiceNow OAuth 进行身份验证，ServiceNow 管理员需要在你的 ServiceNow 实例中预配终结点，以便 Microsoft Search 应用可以访问该实例。</span><span class="sxs-lookup"><span data-stu-id="7ca97-136">To use ServiceNow OAuth for authentication, a ServiceNow admin needs to provision an endpoint in your ServiceNow instance, so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="7ca97-137">若要了解详细信息，请参阅在 ServiceNow 文档中 [创建客户端以访问实例的终结点](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) 。</span><span class="sxs-lookup"><span data-stu-id="7ca97-137">To learn more, see [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in the ServiceNow documentation.</span></span>

<span data-ttu-id="7ca97-138">下表提供了有关如何填写终结点创建表单的指导：</span><span class="sxs-lookup"><span data-stu-id="7ca97-138">The following table provides guidance on how to fill out the endpoint creation form:</span></span>

<span data-ttu-id="7ca97-139">**Field**</span><span class="sxs-lookup"><span data-stu-id="7ca97-139">**Field**</span></span> | <span data-ttu-id="7ca97-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ca97-140">**Description**</span></span> | <span data-ttu-id="7ca97-141">**推荐值**</span><span class="sxs-lookup"><span data-stu-id="7ca97-141">**Recommended Value**</span></span>
--- | --- | ---
<span data-ttu-id="7ca97-142">名称</span><span class="sxs-lookup"><span data-stu-id="7ca97-142">Name</span></span> | <span data-ttu-id="7ca97-143">此唯一值标识您需要 OAuth 访问的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7ca97-143">This unique value identifies the application that you require OAuth access for.</span></span> | <span data-ttu-id="7ca97-144">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="7ca97-144">Microsoft Search</span></span>
<span data-ttu-id="7ca97-145">客户端 ID</span><span class="sxs-lookup"><span data-stu-id="7ca97-145">Client ID</span></span> | <span data-ttu-id="7ca97-146">应用程序的只读、自动生成的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="7ca97-146">A read-only, auto-generated unique ID for the application.</span></span> <span data-ttu-id="7ca97-147">实例在请求访问令牌时使用客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="7ca97-147">The instance uses the client ID when it requests an access token.</span></span> | <span data-ttu-id="7ca97-148">不适用</span><span class="sxs-lookup"><span data-stu-id="7ca97-148">NA</span></span>
<span data-ttu-id="7ca97-149">客户端密码</span><span class="sxs-lookup"><span data-stu-id="7ca97-149">Client secret</span></span> | <span data-ttu-id="7ca97-150">使用此共享机密字符串，ServiceNow 实例和 Microsoft Search 授权相互之间的通信。</span><span class="sxs-lookup"><span data-stu-id="7ca97-150">With this shared secret string, the ServiceNow instance and Microsoft Search authorize communications with each other.</span></span> | <span data-ttu-id="7ca97-151">将此视为密码，以遵循安全性最佳实践。</span><span class="sxs-lookup"><span data-stu-id="7ca97-151">Follow security best-practices by treating this as a password.</span></span>
<span data-ttu-id="7ca97-152">重定向 URL</span><span class="sxs-lookup"><span data-stu-id="7ca97-152">Redirect URL</span></span> | <span data-ttu-id="7ca97-153">授权服务器重定向到的必需回调 URL。</span><span class="sxs-lookup"><span data-stu-id="7ca97-153">A required callback URL that the authorization server redirects to.</span></span> | https://gcs.office.com/v1.0/admin/oauth/callback
<span data-ttu-id="7ca97-154">徽标 URL</span><span class="sxs-lookup"><span data-stu-id="7ca97-154">Logo URL</span></span> | <span data-ttu-id="7ca97-155">包含应用程序徽标的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="7ca97-155">A URL that contains the image for the application logo.</span></span> | <span data-ttu-id="7ca97-156">不适用</span><span class="sxs-lookup"><span data-stu-id="7ca97-156">NA</span></span>
<span data-ttu-id="7ca97-157">活动</span><span class="sxs-lookup"><span data-stu-id="7ca97-157">Active</span></span> | <span data-ttu-id="7ca97-158">选中此复选框可使应用程序注册表处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="7ca97-158">Select the check box to make the application registry active.</span></span> | <span data-ttu-id="7ca97-159">设置为活动</span><span class="sxs-lookup"><span data-stu-id="7ca97-159">Set to active</span></span>
<span data-ttu-id="7ca97-160">刷新令牌生命期</span><span class="sxs-lookup"><span data-stu-id="7ca97-160">Refresh token lifespan</span></span> | <span data-ttu-id="7ca97-161">刷新令牌有效的秒数。</span><span class="sxs-lookup"><span data-stu-id="7ca97-161">The number of seconds that a refresh token is valid.</span></span> <span data-ttu-id="7ca97-162">默认情况下，刷新令牌在100天内过期 (8640000 秒) 。</span><span class="sxs-lookup"><span data-stu-id="7ca97-162">By default, refresh tokens expire in 100 days (8640000 seconds).</span></span> | <span data-ttu-id="7ca97-163">31536000 (1 年) </span><span class="sxs-lookup"><span data-stu-id="7ca97-163">31,536,000 (1 year)</span></span>
<span data-ttu-id="7ca97-164">访问令牌生命周期</span><span class="sxs-lookup"><span data-stu-id="7ca97-164">Access token lifespan</span></span> | <span data-ttu-id="7ca97-165">访问令牌有效的秒数。</span><span class="sxs-lookup"><span data-stu-id="7ca97-165">The number of seconds that an access token is valid.</span></span> | <span data-ttu-id="7ca97-166">43200 (12 小时) </span><span class="sxs-lookup"><span data-stu-id="7ca97-166">43,200 (12 hours)</span></span>

<span data-ttu-id="7ca97-167">输入客户端 id 和客户端密码以连接到你的实例。</span><span class="sxs-lookup"><span data-stu-id="7ca97-167">Enter the client id and client secret to connect to your instance.</span></span> <span data-ttu-id="7ca97-168">连接后，使用 ServiceNow 帐户凭据对要进行爬网的权限进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7ca97-168">After connecting, use a ServiceNow account credential to authenticate permission to crawl.</span></span> <span data-ttu-id="7ca97-169">帐户应至少具有 **知识** 角色。</span><span class="sxs-lookup"><span data-stu-id="7ca97-169">The account should at least have **knowledge** role.</span></span>

#### <a name="azure-ad-openid-connect"></a><span data-ttu-id="7ca97-170">Azure AD OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="7ca97-170">Azure AD OpenID Connect</span></span>

<span data-ttu-id="7ca97-171">若要使用 Azure AD OpenID Connect 进行身份验证，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7ca97-171">To use Azure AD OpenID Connect for authentication, follow the steps below.</span></span>

###### <a name="step-1-register-a-new-application-in-azure-active-directory"></a><span data-ttu-id="7ca97-172">步骤1：在 Azure Active Directory 中注册新应用程序</span><span class="sxs-lookup"><span data-stu-id="7ca97-172">Step 1: Register a new application in Azure Active Directory</span></span>

<span data-ttu-id="7ca97-173">若要了解如何在 Azure Active Directory 中注册新应用程序，请参阅 [注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-173">To learn about registering a new application in Azure Active Directory, see [Register an application](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application).</span></span> <span data-ttu-id="7ca97-174">选择 "单个租户组织目录"。</span><span class="sxs-lookup"><span data-stu-id="7ca97-174">Select single tenant organizational directory.</span></span> <span data-ttu-id="7ca97-175">不需要重定向 URI。</span><span class="sxs-lookup"><span data-stu-id="7ca97-175">Redirect URI is not needed.</span></span> <span data-ttu-id="7ca97-176">注册后，记下应用程序 (客户端) ID 和目录 (租户) ID。</span><span class="sxs-lookup"><span data-stu-id="7ca97-176">After registration, note down the Application (client) ID and Directory (tenant) ID.</span></span>

###### <a name="step-2-create-a-client-secret"></a><span data-ttu-id="7ca97-177">步骤2：创建客户端密码</span><span class="sxs-lookup"><span data-stu-id="7ca97-177">Step 2: Create a client secret</span></span>

<span data-ttu-id="7ca97-178">若要了解如何创建客户端密码，请参阅 [创建客户端密码](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-178">To learn about creating a client secret, see [Creating a client secret](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).</span></span> <span data-ttu-id="7ca97-179">记录客户端密码。</span><span class="sxs-lookup"><span data-stu-id="7ca97-179">Take a note of client secret.</span></span>

###### <a name="step-3-retrieve-service-principal-object-identifier"></a><span data-ttu-id="7ca97-180">步骤3：检索服务主体对象标识符</span><span class="sxs-lookup"><span data-stu-id="7ca97-180">Step 3: Retrieve Service Principal Object Identifier</span></span>

<span data-ttu-id="7ca97-181">按照步骤检索服务主体对象标识符</span><span class="sxs-lookup"><span data-stu-id="7ca97-181">Follow the steps to retrieve Service Principal Object Identifier</span></span>

1. <span data-ttu-id="7ca97-182">运行 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ca97-182">Run PowerShell</span></span>
2. <span data-ttu-id="7ca97-183">使用以下命令安装 Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ca97-183">Install Azure PowerShell using the following command</span></span>
```<language>
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
```
3. <span data-ttu-id="7ca97-184">连接到 Azure</span><span class="sxs-lookup"><span data-stu-id="7ca97-184">Connect to Azure</span></span>
```<language>
    Connect-AzAccount
```
4. <span data-ttu-id="7ca97-185">获取服务主体对象标识符</span><span class="sxs-lookup"><span data-stu-id="7ca97-185">Get Service Principal Object Identifier</span></span>
```<language>
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
```
<span data-ttu-id="7ca97-186">将 "应用程序 ID" 替换为应用程序 (客户端) ID (没有引号) 在步骤1中注册的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7ca97-186">Replace "Application-ID" with Application (client) ID (without quotes) of the application you registered in step 1.</span></span> <span data-ttu-id="7ca97-187">请注意 PowerShell 输出中 ID 对象的值。</span><span class="sxs-lookup"><span data-stu-id="7ca97-187">Note the value of ID object from PowerShell output.</span></span> <span data-ttu-id="7ca97-188">它是服务主体 ID。</span><span class="sxs-lookup"><span data-stu-id="7ca97-188">It is the Service Principal ID.</span></span>

<span data-ttu-id="7ca97-189">现在，你已拥有 Azure 门户所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="7ca97-189">Now you have all the information required from Azure portal.</span></span> <span data-ttu-id="7ca97-190">下面的表中给出了信息的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="7ca97-190">A quick summary of the information is given in the table below.</span></span>

<span data-ttu-id="7ca97-191">**属性**</span><span class="sxs-lookup"><span data-stu-id="7ca97-191">**Property**</span></span> | <span data-ttu-id="7ca97-192">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ca97-192">**Description**</span></span>
--- | ---
<span data-ttu-id="7ca97-193"> (租户 ID) 的目录 ID</span><span class="sxs-lookup"><span data-stu-id="7ca97-193">Directory ID (Tenant ID)</span></span> | <span data-ttu-id="7ca97-194">这是从步骤 1) 中引用 Azure Active Directory 租户 (的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="7ca97-194">This is a unique ID referring the Azure Active Directory tenant (from step 1).</span></span>
<span data-ttu-id="7ca97-195"> (客户端 ID) 的应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="7ca97-195">Application ID (Client ID)</span></span> | <span data-ttu-id="7ca97-196">这是引用在步骤1中注册的应用程序的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="7ca97-196">This is a unique ID referring the application registered in step 1.</span></span>
<span data-ttu-id="7ca97-197">客户端密码</span><span class="sxs-lookup"><span data-stu-id="7ca97-197">Client Secret</span></span> | <span data-ttu-id="7ca97-198">这是第2步) 中的应用程序 (的机密密钥。</span><span class="sxs-lookup"><span data-stu-id="7ca97-198">This is the secret key of the application (from step 2).</span></span> <span data-ttu-id="7ca97-199">像密码一样对待它。</span><span class="sxs-lookup"><span data-stu-id="7ca97-199">Treat it like a password.</span></span>
<span data-ttu-id="7ca97-200">服务主体 ID</span><span class="sxs-lookup"><span data-stu-id="7ca97-200">Service Principal ID</span></span> | <span data-ttu-id="7ca97-201">作为服务运行的应用程序的标识。</span><span class="sxs-lookup"><span data-stu-id="7ca97-201">An identity for the application running as a service.</span></span> <span data-ttu-id="7ca97-202">步骤3中的 () </span><span class="sxs-lookup"><span data-stu-id="7ca97-202">(from step 3)</span></span>

###### <a name="step-4-register-servicenow-application"></a><span data-ttu-id="7ca97-203">步骤4：注册 ServiceNow 应用程序</span><span class="sxs-lookup"><span data-stu-id="7ca97-203">Step 4: Register ServiceNow Application</span></span>

<span data-ttu-id="7ca97-204">需要在 ServiceNow 实例中执行以下配置。</span><span class="sxs-lookup"><span data-stu-id="7ca97-204">The following configuration need to be done in the ServiceNow instance.</span></span>

1. <span data-ttu-id="7ca97-205">注册新的 OAuth OIDC 实体。</span><span class="sxs-lookup"><span data-stu-id="7ca97-205">Register a new OAuth OIDC entity.</span></span> <span data-ttu-id="7ca97-206">若要了解详情，请参阅 [Create a OAUTH OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-206">To learn, see [Create an OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).</span></span>
2. <span data-ttu-id="7ca97-207">下表提供了有关如何填写 OIDC 提供程序注册表单的指南</span><span class="sxs-lookup"><span data-stu-id="7ca97-207">The following table provides guidance on how to fill out OIDC provider registration form</span></span>

<span data-ttu-id="7ca97-208">**Field**</span><span class="sxs-lookup"><span data-stu-id="7ca97-208">**Field**</span></span> | <span data-ttu-id="7ca97-209">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ca97-209">**Description**</span></span> | <span data-ttu-id="7ca97-210">**推荐值**</span><span class="sxs-lookup"><span data-stu-id="7ca97-210">**Recommended Value**</span></span>
--- | --- | ---
<span data-ttu-id="7ca97-211">名称</span><span class="sxs-lookup"><span data-stu-id="7ca97-211">Name</span></span> | <span data-ttu-id="7ca97-212">标识 OAuth OIDC 实体的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="7ca97-212">A unique name that identifies the OAuth OIDC entity.</span></span> | <span data-ttu-id="7ca97-213">Azure AD</span><span class="sxs-lookup"><span data-stu-id="7ca97-213">Azure AD</span></span>
<span data-ttu-id="7ca97-214">客户端 ID</span><span class="sxs-lookup"><span data-stu-id="7ca97-214">Client ID</span></span> | <span data-ttu-id="7ca97-215">在第三方 OAuth OIDC 服务器中注册的应用程序的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="7ca97-215">The client ID of the application registered in the third-party OAuth OIDC server.</span></span> <span data-ttu-id="7ca97-216">请求访问令牌时，实例使用客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="7ca97-216">The instance uses the client ID when requesting an access token.</span></span> | <span data-ttu-id="7ca97-217">第1步中的应用程序 (客户端) ID</span><span class="sxs-lookup"><span data-stu-id="7ca97-217">Application (Client) ID from step 1</span></span>
<span data-ttu-id="7ca97-218">客户端密码</span><span class="sxs-lookup"><span data-stu-id="7ca97-218">Client Secret</span></span> | <span data-ttu-id="7ca97-219">在第三方 OAuth OIDC 服务器中注册的应用程序的客户端密码。</span><span class="sxs-lookup"><span data-stu-id="7ca97-219">The client secret of the application registered in the third-party OAuth OIDC server.</span></span> | <span data-ttu-id="7ca97-220">步骤2中的客户端密码</span><span class="sxs-lookup"><span data-stu-id="7ca97-220">Client Secret from step 2</span></span>

<span data-ttu-id="7ca97-221">所有其他值都可以是默认值。</span><span class="sxs-lookup"><span data-stu-id="7ca97-221">All other values can be default.</span></span>

3. <span data-ttu-id="7ca97-222">在 OIDC 提供程序注册表单中，需要添加新的 OIDC 提供程序配置。</span><span class="sxs-lookup"><span data-stu-id="7ca97-222">In the OIDC provider registration form, you need to add a new OIDC provider configuration.</span></span> <span data-ttu-id="7ca97-223">单击 "针对 *OAUTH OIDC Provider 配置* " 字段的 "搜索" 图标，打开 OIDC 配置的记录。</span><span class="sxs-lookup"><span data-stu-id="7ca97-223">Click the search icon against *OAuth OIDC Provider Configuration* field to open the records of OIDC configurations.</span></span> <span data-ttu-id="7ca97-224">单击"新建"。</span><span class="sxs-lookup"><span data-stu-id="7ca97-224">Click New.</span></span>
4. <span data-ttu-id="7ca97-225">下表提供了有关如何填写 OIDC 提供程序配置表单的指南</span><span class="sxs-lookup"><span data-stu-id="7ca97-225">The following table provides guidance on how to fill out OIDC provider configuration form</span></span>

<span data-ttu-id="7ca97-226">**字段**</span><span class="sxs-lookup"><span data-stu-id="7ca97-226">**Field**</span></span> | <span data-ttu-id="7ca97-227">**推荐值**</span><span class="sxs-lookup"><span data-stu-id="7ca97-227">**Recommended Value**</span></span>
--- | ---
<span data-ttu-id="7ca97-228">OIDC 提供程序</span><span class="sxs-lookup"><span data-stu-id="7ca97-228">OIDC Provider</span></span> |  <span data-ttu-id="7ca97-229">Azure AD</span><span class="sxs-lookup"><span data-stu-id="7ca97-229">Azure AD</span></span>
<span data-ttu-id="7ca97-230">OIDC 元数据 URL</span><span class="sxs-lookup"><span data-stu-id="7ca97-230">OIDC Metadata URL</span></span> | <span data-ttu-id="7ca97-231">此格式必须采用 https \: //login.microsoftonline.com/"tenandId"/.well-known/openid-configuration</span><span class="sxs-lookup"><span data-stu-id="7ca97-231">This must be in the form https\://login.microsoftonline.com/"tenandId"/.well-known/openid-configuration</span></span> <br/><span data-ttu-id="7ca97-232">将 "tenantID" 从步骤 1 (中的目录 (租户) ID 替换为) 不带引号的 ID。</span><span class="sxs-lookup"><span data-stu-id="7ca97-232">Replace "tenantID" with Directory (tenant) ID from step 1 (without quotes).</span></span>
<span data-ttu-id="7ca97-233">OIDC 配置缓存寿命范围</span><span class="sxs-lookup"><span data-stu-id="7ca97-233">OIDC Configuration Cache Life Span</span></span> |  <span data-ttu-id="7ca97-234">120</span><span class="sxs-lookup"><span data-stu-id="7ca97-234">120</span></span>
<span data-ttu-id="7ca97-235">应用程序</span><span class="sxs-lookup"><span data-stu-id="7ca97-235">Application</span></span> | <span data-ttu-id="7ca97-236">全球</span><span class="sxs-lookup"><span data-stu-id="7ca97-236">Global</span></span>
<span data-ttu-id="7ca97-237">用户声明</span><span class="sxs-lookup"><span data-stu-id="7ca97-237">User Claim</span></span> | <span data-ttu-id="7ca97-238">sub</span><span class="sxs-lookup"><span data-stu-id="7ca97-238">sub</span></span>
<span data-ttu-id="7ca97-239">用户字段</span><span class="sxs-lookup"><span data-stu-id="7ca97-239">User Field</span></span> | <span data-ttu-id="7ca97-240">用户 ID</span><span class="sxs-lookup"><span data-stu-id="7ca97-240">User ID</span></span>
<span data-ttu-id="7ca97-241">启用 JTI 声明验证</span><span class="sxs-lookup"><span data-stu-id="7ca97-241">Enable JTI claim verification</span></span> | <span data-ttu-id="7ca97-242">禁用</span><span class="sxs-lookup"><span data-stu-id="7ca97-242">Disabled</span></span>

5. <span data-ttu-id="7ca97-243">单击 "提交" 并更新 "OAuth OIDC 实体" 表单。</span><span class="sxs-lookup"><span data-stu-id="7ca97-243">Click Submit and Update the OAuth OIDC Entity form.</span></span>

###### <a name="step-5-create-a-servicenow-account"></a><span data-ttu-id="7ca97-244">步骤5：创建 ServiceNow 帐户</span><span class="sxs-lookup"><span data-stu-id="7ca97-244">Step 5: Create a ServiceNow account</span></span>

<span data-ttu-id="7ca97-245">请参阅说明创建 ServiceNow 帐户， [在 ServiceNow 中创建一个用户](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-245">Refer the instructions to create a ServiceNow account, [create a user in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).</span></span>

<span data-ttu-id="7ca97-246">下表提供了有关如何填写 ServiceNow 用户帐户注册的指南。</span><span class="sxs-lookup"><span data-stu-id="7ca97-246">The following table provides guidance on how to fill out the ServiceNow user account registration</span></span>

<span data-ttu-id="7ca97-247">**字段**</span><span class="sxs-lookup"><span data-stu-id="7ca97-247">**Field**</span></span> | <span data-ttu-id="7ca97-248">**推荐值**</span><span class="sxs-lookup"><span data-stu-id="7ca97-248">**Recommended Value**</span></span>
--- | ---
<span data-ttu-id="7ca97-249">用户 ID</span><span class="sxs-lookup"><span data-stu-id="7ca97-249">User ID</span></span> | <span data-ttu-id="7ca97-250">步骤3中的服务主体 ID</span><span class="sxs-lookup"><span data-stu-id="7ca97-250">Service Principal ID from step 3</span></span>
<span data-ttu-id="7ca97-251">仅 Web 服务访问</span><span class="sxs-lookup"><span data-stu-id="7ca97-251">Web service access only</span></span> | <span data-ttu-id="7ca97-252">Checked</span><span class="sxs-lookup"><span data-stu-id="7ca97-252">Checked</span></span>

<span data-ttu-id="7ca97-253">所有其他值都可以保留为默认值。</span><span class="sxs-lookup"><span data-stu-id="7ca97-253">All other values can be left to default.</span></span>

###### <a name="step-6-enable-knowledge-role-for-the-servicenow-account"></a><span data-ttu-id="7ca97-254">步骤6：为 ServiceNow 帐户启用知识角色</span><span class="sxs-lookup"><span data-stu-id="7ca97-254">Step 6: Enable Knowledge role for the ServiceNow account</span></span>

<span data-ttu-id="7ca97-255">访问使用 ServiceNow 主体 ID 创建的 ServiceNow 帐户作为用户 ID，并分配知识角色。</span><span class="sxs-lookup"><span data-stu-id="7ca97-255">Access the ServiceNow account you created with ServiceNow Principal ID as User ID and assign the knowledge role.</span></span> <span data-ttu-id="7ca97-256">可在此处找到向 ServiceNow 帐户分配角色的说明，可在此处 [为用户分配角色](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-256">Instructions to assigning a role to a ServiceNow account can be found here, [assign a role to a user](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span>

<span data-ttu-id="7ca97-257">使用 "应用程序 ID" 作为 "客户端 (ID) " 中的 "应用程序 ID" 和 "客户端密钥" (从步骤 2) 在管理中心配置向导中使用 Azure AD OpenID Connect 向你的 ServiceNow 实例进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7ca97-257">Use Application ID as Client ID (from step 1), and Client secret (from step 2) in admin center configuration wizard to authenticate to your ServiceNow instance using Azure AD OpenID Connect.</span></span>

## <a name="filter-data"></a><span data-ttu-id="7ca97-258">筛选数据</span><span class="sxs-lookup"><span data-stu-id="7ca97-258">Filter data</span></span>

<span data-ttu-id="7ca97-259">使用 ServiceNow 查询字符串，可以指定用于同步文章的条件。</span><span class="sxs-lookup"><span data-stu-id="7ca97-259">With a ServiceNow query string, you can specify conditions for syncing articles.</span></span> <span data-ttu-id="7ca97-260">它类似于 **SQL Select** 语句中的 **Where** 子句。</span><span class="sxs-lookup"><span data-stu-id="7ca97-260">It's like a **Where** clause in a **SQL Select** statement.</span></span> <span data-ttu-id="7ca97-261">例如，您可以选择仅对已发布和活动的文章编制索引。</span><span class="sxs-lookup"><span data-stu-id="7ca97-261">For example, you can choose to index only articles that are published and active.</span></span> <span data-ttu-id="7ca97-262">若要了解如何创建自己的查询字符串，请参阅 [使用筛选器生成已编码的查询字符串](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-262">To learn about creating your own query string, see [Generate an encoded query string using a filter](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="7ca97-263">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="7ca97-263">Manage search permissions</span></span>

<span data-ttu-id="7ca97-264">ServiceNow 连接器支持对 **所有人** 可见的搜索权限，或仅支持对 **此数据源具有访问权限的用户**。</span><span class="sxs-lookup"><span data-stu-id="7ca97-264">The ServiceNow connector supports search permissions visible to **Everyone** or **Only people with access to this data source**.</span></span> <span data-ttu-id="7ca97-265">索引数据将显示在搜索结果中，并对组织中的所有用户或对其分别拥有访问权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="7ca97-265">Indexed data appears in the search results and is visible to all users in the organization or users who have access to them respectively.</span></span> <span data-ttu-id="7ca97-266">ServiceNow 连接器支持不带高级脚本的默认用户条件权限。</span><span class="sxs-lookup"><span data-stu-id="7ca97-266">ServiceNow Connector supports default user criteria permissions without advanced scripts.</span></span> <span data-ttu-id="7ca97-267">当连接器遇到高级脚本的用户条件时，使用该用户条件的所有数据将不会显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="7ca97-267">When the connector encounters a user criteria with advanced script, all data using that user criteria will not be showed in search results.</span></span>

<span data-ttu-id="7ca97-268">如果您选择 " **仅有权访问此数据源的人员**"，则需要进一步选择您的 ServiceNow 实例是否有 Azure Active DIRECTORY (AAD) 预配的用户或非 AAD 用户。</span><span class="sxs-lookup"><span data-stu-id="7ca97-268">If you choose **Only people with access to this data source**, you need to further choose whether your ServiceNow instance has Azure Active Directory (AAD) provisioned users or Non-AAD users.</span></span>

>[!NOTE]
><span data-ttu-id="7ca97-269">如果 **只选择了具有此数据源访问权限的用户**，则 ServiceNow 连接器将处于 **预览阶段**。</span><span class="sxs-lookup"><span data-stu-id="7ca97-269">The ServiceNow connector is in **preview** if you choose **Only people with access to this data source**.</span></span>

>[!NOTE]
><span data-ttu-id="7ca97-270">如果选择 "AAD" 作为标识源的类型，请确保要为 ServiceNow 中的电子邮件目标属性分配 UPN 源属性。</span><span class="sxs-lookup"><span data-stu-id="7ca97-270">If you choose AAD as the type of identity source, make sure you are assigning UPN source property to email targeted property in ServiceNow.</span></span> <span data-ttu-id="7ca97-271">若要验证或更改映射，请参阅 [在 Azure Active Directory 中自定义用户预配属性-用于 SaaS 应用程序的映射](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-271">To verify or change your mappings, see [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes).</span></span>

<span data-ttu-id="7ca97-272">如果你选择从你的 ServiceNow 实例中引入 ACL 并为标识类型选择了 "非 AAD"，请参阅 [映射你的非 AZURE AD 标识](map-non-aad.md) ，了解有关标识标识的说明。</span><span class="sxs-lookup"><span data-stu-id="7ca97-272">If you chose to ingest an ACL from your ServiceNow instance and selected "non-AAD" for the identity type see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="7ca97-273">分配属性标签</span><span class="sxs-lookup"><span data-stu-id="7ca97-273">Assign property labels</span></span>

<span data-ttu-id="7ca97-274">通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。</span><span class="sxs-lookup"><span data-stu-id="7ca97-274">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="7ca97-275">虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。</span><span class="sxs-lookup"><span data-stu-id="7ca97-275">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="7ca97-276">管理架构</span><span class="sxs-lookup"><span data-stu-id="7ca97-276">Manage schema</span></span>

<span data-ttu-id="7ca97-277">在 " **管理架构** " 屏幕上，您可以选择更改架构属性， (可 **查询**、可 **搜索**、 **检索** 和 **可精简**) 与属性相关联，添加可选别名，然后选择 **Content** 属性。</span><span class="sxs-lookup"><span data-stu-id="7ca97-277">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="7ca97-278">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="7ca97-278">Set the refresh schedule</span></span>

<span data-ttu-id="7ca97-279">ServiceNow 连接器支持完全爬网和增量爬网的刷新计划。</span><span class="sxs-lookup"><span data-stu-id="7ca97-279">The ServiceNow connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="7ca97-280">我们建议您同时设置这两个。</span><span class="sxs-lookup"><span data-stu-id="7ca97-280">We recommend that you set both.</span></span>

<span data-ttu-id="7ca97-281">完全爬网计划可查找以前同步到 Microsoft 搜索索引的已删除文章以及从同步筛选器中移出的所有文章。</span><span class="sxs-lookup"><span data-stu-id="7ca97-281">A full crawl schedule finds deleted articles that were previously synced to the Microsoft Search index and any articles that moved out of the sync filter.</span></span> <span data-ttu-id="7ca97-282">首次连接到 ServiceNow 时，将运行完全爬网以同步所有知识库文章。</span><span class="sxs-lookup"><span data-stu-id="7ca97-282">When you first connect to ServiceNow, a full crawl runs to sync all the knowledge-base articles.</span></span> <span data-ttu-id="7ca97-283">若要同步新项目并进行更新，需要安排增量爬网。</span><span class="sxs-lookup"><span data-stu-id="7ca97-283">To sync new items and make updates, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="7ca97-284">对于完全爬网，建议默认值为一天，对于增量爬网，建议默认值为4小时。</span><span class="sxs-lookup"><span data-stu-id="7ca97-284">The recommended default is one day for a full crawl and four hours for an incremental crawl.</span></span>
>[!NOTE]
><span data-ttu-id="7ca97-285">对于标识，仅应用已计划的完全爬网。</span><span class="sxs-lookup"><span data-stu-id="7ca97-285">For identities, only full crawl scheduled will be applied.</span></span>

## <a name="review-and-publish"></a><span data-ttu-id="7ca97-286">查看和发布</span><span class="sxs-lookup"><span data-stu-id="7ca97-286">Review and publish</span></span>

<span data-ttu-id="7ca97-287">配置连接器后，可以查看并发布连接。</span><span class="sxs-lookup"><span data-stu-id="7ca97-287">After you configure your connector, you can review and publish the connection.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ca97-288">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7ca97-288">Next steps</span></span>

<span data-ttu-id="7ca97-289">发布连接后，需要自定义搜索结果页面。</span><span class="sxs-lookup"><span data-stu-id="7ca97-289">After publishing the connection, you need to customize the search results page.</span></span> <span data-ttu-id="7ca97-290">若要了解有关自定义搜索结果的信息，请参阅 [自定义搜索结果页](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)。</span><span class="sxs-lookup"><span data-stu-id="7ca97-290">To learn about customizing search results, see [Customize the search results page](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).</span></span>