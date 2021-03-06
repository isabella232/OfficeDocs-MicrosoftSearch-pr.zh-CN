---
title: 用于 Microsoft 搜索的 ServiceNow Graph 连接器
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
description: 为 Microsoft 搜索设置 ServiceNow Graph 连接器
ms.openlocfilehash: eaf8014876b03c0b64c012cf7e83c4e4b84838b9
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508676"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a><span data-ttu-id="0a52b-103">ServiceNow Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="0a52b-103">ServiceNow Graph Connector</span></span>

<span data-ttu-id="0a52b-104">ServiceNow Graph 连接器允许组织根据组织内的用户条件权限为用户可见的基于知识的文章编制索引。</span><span class="sxs-lookup"><span data-stu-id="0a52b-104">The ServiceNow Graph connector allows your organization to index knowledge-based articles visible to users according to the user criteria permissions within your organization.</span></span> <span data-ttu-id="0a52b-105">从 ServiceNow 配置连接器和索引内容后，用户可以从任何 Microsoft 搜索客户端搜索文章。</span><span class="sxs-lookup"><span data-stu-id="0a52b-105">After you configure the connector and index content from ServiceNow, users can search for the articles from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="0a52b-106">阅读 [**Graph 连接器的安装程序文章**](configure-connector.md) ，了解一般 Graph 连接器设置说明。</span><span class="sxs-lookup"><span data-stu-id="0a52b-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="0a52b-107">本文适用于配置、运行和监视 ServiceNow Graph 连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="0a52b-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="0a52b-108">它补充了常规安装过程，并显示了仅适用于 ServiceNow Graph 连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="0a52b-108">It supplements the general setup process, and shows instructions that apply to only for the ServiceNow Graph connector.</span></span> <span data-ttu-id="0a52b-109">本文还包括有关[疑难解答和](#troubleshooting)[限制的信息](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-109">This article also includes information about [Troubleshooting](#troubleshooting) and [Limitations](#limitations).</span></span>
  
## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0a52b-110">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="0a52b-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0a52b-111">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="0a52b-112">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="0a52b-112">Step 2: Name the connection</span></span>

<span data-ttu-id="0a52b-113">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a><span data-ttu-id="0a52b-114">步骤 3：连接设置</span><span class="sxs-lookup"><span data-stu-id="0a52b-114">Step 3: Connection Settings</span></span>

<span data-ttu-id="0a52b-115">若要连接到 ServiceNow 数据，请使用组织的此帐户的 **ServiceNow** 实例 URL 凭据、客户端 ID 和客户端密码进行 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0a52b-115">To connect to your ServiceNow data, use your organization's **ServiceNow instance URL** credentials for this account, the Client ID, and Client Secret for OAuth authentication.</span></span>  

<span data-ttu-id="0a52b-116">组织的 **ServiceNow** 实例 URL 通常类似于https://域 **&lt;>.service-now.com。**</span><span class="sxs-lookup"><span data-stu-id="0a52b-116">Your organization's **ServiceNow instance URL** typically looks like **https://&lt;your-organization-domain>.service-now.com**.</span></span> <span data-ttu-id="0a52b-117">除了此 URL，还需要一个帐户来设置与 ServiceNow 的连接，并允许 Microsoft 搜索根据刷新计划从 ServiceNow 更新文章。</span><span class="sxs-lookup"><span data-stu-id="0a52b-117">Along with this URL, you need an account for setting up the connection to ServiceNow and for allowing Microsoft Search to update the articles from ServiceNow based on the refresh schedule.</span></span> <span data-ttu-id="0a52b-118">该帐户至少应具有 <em>知识</em> 角色。</span><span class="sxs-lookup"><span data-stu-id="0a52b-118">The account should at least have <em>knowledge</em> role.</span></span> <span data-ttu-id="0a52b-119">[了解如何为 ServiceNow 帐户分配角色](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-119">[Learn how to assign role for ServiceNow accounts](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span>

>[!NOTE]
><span data-ttu-id="0a52b-120">如果要对用户和组标识进行爬网以遵循 Microsoft 搜索结果中知识文章的访问权限，则帐户应有权访问在 ServiceNow 中读取下表记录：</span><span class="sxs-lookup"><span data-stu-id="0a52b-120">If you want to crawl user and group identities to honor access permissions of knowledge articles in Microsoft Search results, the account should have access to read the following table records in ServiceNow:</span></span>
>* <span data-ttu-id="0a52b-121">kb_uc_can_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="0a52b-121">kb_uc_can_contribute_mtom</span></span>
>* <span data-ttu-id="0a52b-122">kb_uc_can_read_mtom</span><span class="sxs-lookup"><span data-stu-id="0a52b-122">kb_uc_can_read_mtom</span></span>
>* <span data-ttu-id="0a52b-123">kb_uc_cannot_read_mtom</span><span class="sxs-lookup"><span data-stu-id="0a52b-123">kb_uc_cannot_read_mtom</span></span>
>* <span data-ttu-id="0a52b-124">kb_uc_cannot_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="0a52b-124">kb_uc_cannot_contribute_mtom</span></span>
>* <span data-ttu-id="0a52b-125">sys_user</span><span class="sxs-lookup"><span data-stu-id="0a52b-125">sys_user</span></span>
>* <span data-ttu-id="0a52b-126">sys_user_has_role</span><span class="sxs-lookup"><span data-stu-id="0a52b-126">sys_user_has_role</span></span>
>* <span data-ttu-id="0a52b-127">sys_user_grmember</span><span class="sxs-lookup"><span data-stu-id="0a52b-127">sys_user_grmember</span></span>
>* <span data-ttu-id="0a52b-128">user_criteria</span><span class="sxs-lookup"><span data-stu-id="0a52b-128">user_criteria</span></span>
>* <span data-ttu-id="0a52b-129">kb_knowledge_base</span><span class="sxs-lookup"><span data-stu-id="0a52b-129">kb_knowledge_base</span></span>  
> <span data-ttu-id="0a52b-130">你可以为用于与 Microsoft 搜索连接的帐户创建和分配角色。</span><span class="sxs-lookup"><span data-stu-id="0a52b-130">You can create and assign a role for the account you use to connect with Microsoft Search.</span></span> <span data-ttu-id="0a52b-131">可以在该角色上分配对表的读取权限。</span><span class="sxs-lookup"><span data-stu-id="0a52b-131">Read access to the tables can be assigned on that role.</span></span> <span data-ttu-id="0a52b-132">若要了解如何设置对表记录的读取访问权限，请参阅["保护表记录"。](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)</span><span class="sxs-lookup"><span data-stu-id="0a52b-132">To learn about setting read access to table records, see [Securing Table Records](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls).</span></span>

<span data-ttu-id="0a52b-133">若要对 ServiceNow 中的内容进行身份验证和同步，请选择 **以下三种** 受支持的方法之一：</span><span class="sxs-lookup"><span data-stu-id="0a52b-133">To authenticate and sync content from ServiceNow, choose **one of three** supported methods:</span></span>

1. <span data-ttu-id="0a52b-134">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="0a52b-134">Basic authentication</span></span>
1. <span data-ttu-id="0a52b-135">ServiceNow OAuth (推荐) </span><span class="sxs-lookup"><span data-stu-id="0a52b-135">ServiceNow OAuth (recommended)</span></span>
1. <span data-ttu-id="0a52b-136">Azure AD OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="0a52b-136">Azure AD OpenID Connect</span></span>

### <a name="basic-authentication"></a><span data-ttu-id="0a52b-137">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="0a52b-137">Basic authentication</span></span>

<span data-ttu-id="0a52b-138">输入具有知识角色的 ServiceNow 帐户 **的用户名和密码** ，以向实例进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0a52b-138">Enter the username and password of ServiceNow account with **knowledge** role to authenticate to your instance.</span></span>

### <a name="servicenow-oauth"></a><span data-ttu-id="0a52b-139">ServiceNow OAuth</span><span class="sxs-lookup"><span data-stu-id="0a52b-139">ServiceNow OAuth</span></span>

<span data-ttu-id="0a52b-140">若要使用 ServiceNow OAuth 进行身份验证，请设置 ServiceNow 实例中的终结点。</span><span class="sxs-lookup"><span data-stu-id="0a52b-140">To use ServiceNow OAuth for authentication, provision an endpoint in your ServiceNow instance.</span></span> <span data-ttu-id="0a52b-141">Microsoft 搜索应用将使用它访问实例。</span><span class="sxs-lookup"><span data-stu-id="0a52b-141">The Microsoft Search app will use it to access the instance.</span></span> <span data-ttu-id="0a52b-142">若要了解更多信息，请参阅 ["为客户端创建终结点以访问](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) ServiceNow 文档中的实例"。</span><span class="sxs-lookup"><span data-stu-id="0a52b-142">To learn more, see [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in the ServiceNow documentation.</span></span>

<span data-ttu-id="0a52b-143">下表提供了有关如何填写终结点创建表单的指南：</span><span class="sxs-lookup"><span data-stu-id="0a52b-143">The following table provides guidance on how to fill out the endpoint creation form:</span></span>

<span data-ttu-id="0a52b-144">字段</span><span class="sxs-lookup"><span data-stu-id="0a52b-144">Field</span></span> | <span data-ttu-id="0a52b-145">说明</span><span class="sxs-lookup"><span data-stu-id="0a52b-145">Description</span></span> | <span data-ttu-id="0a52b-146">建议值</span><span class="sxs-lookup"><span data-stu-id="0a52b-146">Recommended Value</span></span> 
--- | --- | ---
<span data-ttu-id="0a52b-147">名称</span><span class="sxs-lookup"><span data-stu-id="0a52b-147">Name</span></span> | <span data-ttu-id="0a52b-148">标识需要 OAuth 访问的应用程序的唯一值。</span><span class="sxs-lookup"><span data-stu-id="0a52b-148">Unique value that identifies the application that you require OAuth access for.</span></span> | <span data-ttu-id="0a52b-149">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="0a52b-149">Microsoft Search</span></span>
<span data-ttu-id="0a52b-150">客户端 ID</span><span class="sxs-lookup"><span data-stu-id="0a52b-150">Client ID</span></span> | <span data-ttu-id="0a52b-151">应用程序的只读自动生成的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="0a52b-151">A read-only, auto generated unique ID for the application.</span></span> <span data-ttu-id="0a52b-152">实例在请求访问令牌时使用客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="0a52b-152">The instance uses the client ID when it requests an access token.</span></span> | <span data-ttu-id="0a52b-153">不适用</span><span class="sxs-lookup"><span data-stu-id="0a52b-153">NA</span></span>
<span data-ttu-id="0a52b-154">客户端密码</span><span class="sxs-lookup"><span data-stu-id="0a52b-154">Client secret</span></span> | <span data-ttu-id="0a52b-155">通过此共享密码字符串，ServiceNow 实例和 Microsoft 搜索可授权相互通信。</span><span class="sxs-lookup"><span data-stu-id="0a52b-155">With this shared secret string, the ServiceNow instance and Microsoft Search authorize communications with each other.</span></span> | <span data-ttu-id="0a52b-156">将密码视为密码，以遵循安全最佳做法。</span><span class="sxs-lookup"><span data-stu-id="0a52b-156">Follow security best-practices by treating the secret as a password.</span></span>
<span data-ttu-id="0a52b-157">重定向 URL</span><span class="sxs-lookup"><span data-stu-id="0a52b-157">Redirect URL</span></span> | <span data-ttu-id="0a52b-158">授权服务器重定向到的必需回调 URL。</span><span class="sxs-lookup"><span data-stu-id="0a52b-158">A required callback URL that the authorization server redirects to.</span></span> | https://gcs.office.com/v1.0/admin/oauth/callback
<span data-ttu-id="0a52b-159">徽标 URL</span><span class="sxs-lookup"><span data-stu-id="0a52b-159">Logo URL</span></span> | <span data-ttu-id="0a52b-160">包含应用程序徽标的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="0a52b-160">A URL that contains the image for the application logo.</span></span> | <span data-ttu-id="0a52b-161">不适用</span><span class="sxs-lookup"><span data-stu-id="0a52b-161">NA</span></span>
<span data-ttu-id="0a52b-162">活动</span><span class="sxs-lookup"><span data-stu-id="0a52b-162">Active</span></span> | <span data-ttu-id="0a52b-163">选中此复选框可激活应用程序注册表。</span><span class="sxs-lookup"><span data-stu-id="0a52b-163">Select the check box to make the application registry active.</span></span> | <span data-ttu-id="0a52b-164">设置为活动</span><span class="sxs-lookup"><span data-stu-id="0a52b-164">Set to active</span></span>
<span data-ttu-id="0a52b-165">刷新令牌有效期</span><span class="sxs-lookup"><span data-stu-id="0a52b-165">Refresh token lifespan</span></span> | <span data-ttu-id="0a52b-166">刷新令牌有效的秒数。</span><span class="sxs-lookup"><span data-stu-id="0a52b-166">The number of seconds that a refresh token is valid.</span></span> <span data-ttu-id="0a52b-167">默认情况下，刷新令牌在 100 天后过期 (8，640，000 秒) 。</span><span class="sxs-lookup"><span data-stu-id="0a52b-167">By default, refresh tokens expire in 100 days (8,640,000 seconds).</span></span> | <span data-ttu-id="0a52b-168">31，536，000 (一年) </span><span class="sxs-lookup"><span data-stu-id="0a52b-168">31,536,000 (1 year)</span></span>
<span data-ttu-id="0a52b-169">访问令牌有效期</span><span class="sxs-lookup"><span data-stu-id="0a52b-169">Access token lifespan</span></span> | <span data-ttu-id="0a52b-170">访问令牌有效的秒数。</span><span class="sxs-lookup"><span data-stu-id="0a52b-170">The number of seconds that an access token is valid.</span></span> | <span data-ttu-id="0a52b-171">43，200 (12 小时) </span><span class="sxs-lookup"><span data-stu-id="0a52b-171">43,200 (12 hours)</span></span>

<span data-ttu-id="0a52b-172">输入客户端 ID 和客户端密码以连接到实例。</span><span class="sxs-lookup"><span data-stu-id="0a52b-172">Enter the client ID and client secret to connect to your instance.</span></span> <span data-ttu-id="0a52b-173">连接后，使用 ServiceNow 帐户凭据对爬网权限进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0a52b-173">After connecting, use a ServiceNow account credential to authenticate permission to crawl.</span></span> <span data-ttu-id="0a52b-174">该帐户至少应具有 **知识** 角色。</span><span class="sxs-lookup"><span data-stu-id="0a52b-174">The account should at least have **knowledge** role.</span></span>

### <a name="azure-ad-openid-connect"></a><span data-ttu-id="0a52b-175">Azure AD OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="0a52b-175">Azure AD OpenID Connect</span></span>

<span data-ttu-id="0a52b-176">若要使用 Azure AD OpenID Connect 进行身份验证，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="0a52b-176">To use Azure AD OpenID Connect for authentication, follow the steps below.</span></span>

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a><span data-ttu-id="0a52b-177">步骤 3.a：在 Azure Active Directory 中注册新应用程序</span><span class="sxs-lookup"><span data-stu-id="0a52b-177">Step 3.a: Register a new application in Azure Active Directory</span></span>

<span data-ttu-id="0a52b-178">若要了解如何在 Azure Active Directory 中注册新应用程序，请参阅["注册应用程序"。](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application)</span><span class="sxs-lookup"><span data-stu-id="0a52b-178">To learn about registering a new application in Azure Active Directory, see [Register an application](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application).</span></span> <span data-ttu-id="0a52b-179">选择单个租户组织目录。</span><span class="sxs-lookup"><span data-stu-id="0a52b-179">Select single tenant organizational directory.</span></span> <span data-ttu-id="0a52b-180">不需要重定向 URI。</span><span class="sxs-lookup"><span data-stu-id="0a52b-180">Redirect URI isn't needed.</span></span> <span data-ttu-id="0a52b-181">注册后，记下应用程序 (客户端) ID 和目录 (租户) ID。</span><span class="sxs-lookup"><span data-stu-id="0a52b-181">After registration, note down the Application (client) ID and Directory (tenant) ID.</span></span>

## <a name="step-3b-create-a-client-secret"></a><span data-ttu-id="0a52b-182">步骤 3.b：创建客户端密码</span><span class="sxs-lookup"><span data-stu-id="0a52b-182">Step 3.b: Create a client secret</span></span>

<span data-ttu-id="0a52b-183">若要了解如何创建客户端密码，请参阅"[创建客户端密码"。](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)</span><span class="sxs-lookup"><span data-stu-id="0a52b-183">To learn about creating a client secret, see [Creating a client secret](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).</span></span> <span data-ttu-id="0a52b-184">记下客户端密码。</span><span class="sxs-lookup"><span data-stu-id="0a52b-184">Take a note of client secret.</span></span>

## <a name="step-3c-retrieve-service-principal-object-identifier"></a><span data-ttu-id="0a52b-185">步骤 3.c：检索服务主体对象标识符</span><span class="sxs-lookup"><span data-stu-id="0a52b-185">Step 3.c: Retrieve Service Principal Object Identifier</span></span>

<span data-ttu-id="0a52b-186">按照步骤检索服务主体对象标识符</span><span class="sxs-lookup"><span data-stu-id="0a52b-186">Follow the steps to retrieve Service Principal Object Identifier</span></span>

1. <span data-ttu-id="0a52b-187">运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0a52b-187">Run PowerShell.</span></span>

2. <span data-ttu-id="0a52b-188">使用以下命令安装 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0a52b-188">Install Azure PowerShell using the following command.</span></span>

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. <span data-ttu-id="0a52b-189">连接到 Azure。</span><span class="sxs-lookup"><span data-stu-id="0a52b-189">Connect to Azure.</span></span>

   ```powershell
   Connect-AzAccount
   ```

4. <span data-ttu-id="0a52b-190">获取服务主体对象标识符。</span><span class="sxs-lookup"><span data-stu-id="0a52b-190">Get Service Principal Object Identifier.</span></span>

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   <span data-ttu-id="0a52b-191">将"Application-ID"替换为 (客户端) ID (，而不) 步骤 3.a 中注册的应用程序的引号。</span><span class="sxs-lookup"><span data-stu-id="0a52b-191">Replace "Application-ID" with Application (client) ID (without quotes) of the application you registered in step 3.a.</span></span> <span data-ttu-id="0a52b-192">请注意 PowerShell 输出中的 ID 对象的值。</span><span class="sxs-lookup"><span data-stu-id="0a52b-192">Note the value of ID object from PowerShell output.</span></span> <span data-ttu-id="0a52b-193">它是服务主体 ID。</span><span class="sxs-lookup"><span data-stu-id="0a52b-193">It's the Service Principal ID.</span></span>

<span data-ttu-id="0a52b-194">现在，你已拥有 Azure 门户中所需的全部信息。</span><span class="sxs-lookup"><span data-stu-id="0a52b-194">Now you have all the information required from Azure portal.</span></span> <span data-ttu-id="0a52b-195">下表中提供了信息的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="0a52b-195">A quick summary of the information is given in the table below.</span></span>

<span data-ttu-id="0a52b-196">属性</span><span class="sxs-lookup"><span data-stu-id="0a52b-196">Property</span></span> | <span data-ttu-id="0a52b-197">说明</span><span class="sxs-lookup"><span data-stu-id="0a52b-197">Description</span></span> 
--- | ---
<span data-ttu-id="0a52b-198">租户 ID (的目录 ID) </span><span class="sxs-lookup"><span data-stu-id="0a52b-198">Directory ID (Tenant ID)</span></span> | <span data-ttu-id="0a52b-199">步骤 3.a 中的 Azure Active Directory 租户的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="0a52b-199">Unique ID of the Azure Active Directory tenant, from step 3.a.</span></span>
<span data-ttu-id="0a52b-200">客户端 ID (应用程序 ID) </span><span class="sxs-lookup"><span data-stu-id="0a52b-200">Application ID (Client ID)</span></span> | <span data-ttu-id="0a52b-201">步骤 3.a 中注册的应用程序的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="0a52b-201">Unique ID of the application registered in step 3.a.</span></span>
<span data-ttu-id="0a52b-202">客户端密码</span><span class="sxs-lookup"><span data-stu-id="0a52b-202">Client Secret</span></span> | <span data-ttu-id="0a52b-203">应用程序的密钥从步骤 3.b (开始) 。</span><span class="sxs-lookup"><span data-stu-id="0a52b-203">The secret key of the application (from step 3.b).</span></span> <span data-ttu-id="0a52b-204">像密码一样对待它。</span><span class="sxs-lookup"><span data-stu-id="0a52b-204">Treat it like a password.</span></span>
<span data-ttu-id="0a52b-205">服务主体 ID</span><span class="sxs-lookup"><span data-stu-id="0a52b-205">Service Principal ID</span></span> | <span data-ttu-id="0a52b-206">作为服务运行的应用程序的标识。</span><span class="sxs-lookup"><span data-stu-id="0a52b-206">An identity for the application running as a service.</span></span> <span data-ttu-id="0a52b-207"> (步骤 3.c) </span><span class="sxs-lookup"><span data-stu-id="0a52b-207">(from step 3.c)</span></span>

## <a name="step-3d-register-servicenow-application"></a><span data-ttu-id="0a52b-208">步骤 3.d：注册 ServiceNow 应用程序</span><span class="sxs-lookup"><span data-stu-id="0a52b-208">Step 3.d: Register ServiceNow Application</span></span>

<span data-ttu-id="0a52b-209">ServiceNow 实例需要以下配置：</span><span class="sxs-lookup"><span data-stu-id="0a52b-209">The ServiceNow instance needs the following configuration:</span></span>

1. <span data-ttu-id="0a52b-210">注册新的 OAuth OIDC 实体。</span><span class="sxs-lookup"><span data-stu-id="0a52b-210">Register a new OAuth OIDC entity.</span></span> <span data-ttu-id="0a52b-211">若要了解，请参阅["创建 OAuth OIDC 提供程序"。](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)</span><span class="sxs-lookup"><span data-stu-id="0a52b-211">To learn, see [Create an OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).</span></span>

2. <span data-ttu-id="0a52b-212">下表提供了有关如何填写 OIDC 提供程序注册表单的指南</span><span class="sxs-lookup"><span data-stu-id="0a52b-212">The following table provides guidance on how to fill out OIDC provider registration form</span></span>

   <span data-ttu-id="0a52b-213">字段</span><span class="sxs-lookup"><span data-stu-id="0a52b-213">Field</span></span> | <span data-ttu-id="0a52b-214">说明</span><span class="sxs-lookup"><span data-stu-id="0a52b-214">Description</span></span> | <span data-ttu-id="0a52b-215">建议值</span><span class="sxs-lookup"><span data-stu-id="0a52b-215">Recommended Value</span></span>
   --- | --- | ---
   <span data-ttu-id="0a52b-216">名称</span><span class="sxs-lookup"><span data-stu-id="0a52b-216">Name</span></span> | <span data-ttu-id="0a52b-217">标识 OAuth OIDC 实体的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="0a52b-217">A unique name that identifies the OAuth OIDC entity.</span></span> | <span data-ttu-id="0a52b-218">Azure AD</span><span class="sxs-lookup"><span data-stu-id="0a52b-218">Azure AD</span></span>
   <span data-ttu-id="0a52b-219">客户端 ID</span><span class="sxs-lookup"><span data-stu-id="0a52b-219">Client ID</span></span> | <span data-ttu-id="0a52b-220">第三方 OAuth OIDC 服务器中注册的应用程序的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="0a52b-220">The client ID of the application registered in the third-party OAuth OIDC server.</span></span> <span data-ttu-id="0a52b-221">该实例在请求访问令牌时使用客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="0a52b-221">The instance uses the client ID when requesting an access token.</span></span> | <span data-ttu-id="0a52b-222">步骤 3.a (客户端) ID 的应用程序</span><span class="sxs-lookup"><span data-stu-id="0a52b-222">Application (Client) ID from step 3.a</span></span>
   <span data-ttu-id="0a52b-223">客户端密码</span><span class="sxs-lookup"><span data-stu-id="0a52b-223">Client Secret</span></span> | <span data-ttu-id="0a52b-224">第三方 OAuth OIDC 服务器中注册的应用程序的客户端密码。</span><span class="sxs-lookup"><span data-stu-id="0a52b-224">The client secret of the application registered in the third-party OAuth OIDC server.</span></span> | <span data-ttu-id="0a52b-225">步骤 3.b 中的客户端密码</span><span class="sxs-lookup"><span data-stu-id="0a52b-225">Client Secret from step 3.b</span></span>

   <span data-ttu-id="0a52b-226">所有其他值可以是默认值。</span><span class="sxs-lookup"><span data-stu-id="0a52b-226">All other values can be default.</span></span>

3. <span data-ttu-id="0a52b-227">在 OIDC 提供程序注册表单中，需要添加新的 OIDC 提供程序配置。</span><span class="sxs-lookup"><span data-stu-id="0a52b-227">In the OIDC provider registration form, you need to add a new OIDC provider configuration.</span></span> <span data-ttu-id="0a52b-228">针对 *OAuth OIDC 提供程序配置* 字段选择搜索图标以打开 OIDC 配置的记录。</span><span class="sxs-lookup"><span data-stu-id="0a52b-228">Select the search icon against *OAuth OIDC Provider Configuration* field to open the records of OIDC configurations.</span></span> <span data-ttu-id="0a52b-229">选择"新建"。</span><span class="sxs-lookup"><span data-stu-id="0a52b-229">Select New.</span></span>

4. <span data-ttu-id="0a52b-230">下表提供了有关如何填写 OIDC 提供程序配置表单的指南</span><span class="sxs-lookup"><span data-stu-id="0a52b-230">The following table provides guidance on how to fill out OIDC provider configuration form</span></span>

   <span data-ttu-id="0a52b-231">字段</span><span class="sxs-lookup"><span data-stu-id="0a52b-231">Field</span></span> | <span data-ttu-id="0a52b-232">建议值</span><span class="sxs-lookup"><span data-stu-id="0a52b-232">Recommended Value</span></span>
   --- | ---
   <span data-ttu-id="0a52b-233">OIDC 提供程序</span><span class="sxs-lookup"><span data-stu-id="0a52b-233">OIDC Provider</span></span> |  <span data-ttu-id="0a52b-234">Azure AD</span><span class="sxs-lookup"><span data-stu-id="0a52b-234">Azure AD</span></span>
   <span data-ttu-id="0a52b-235">OIDC 元数据 URL</span><span class="sxs-lookup"><span data-stu-id="0a52b-235">OIDC Metadata URL</span></span> | <span data-ttu-id="0a52b-236">URL 格式必须为 https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration</span><span class="sxs-lookup"><span data-stu-id="0a52b-236">The URL must be in the form https\://login.microsoftonline.com/<tenandId">/.well-known/openid-configuration</span></span> <br/><span data-ttu-id="0a52b-237">将"tenantID"替换为 (3.a) 的 Directory 租户 id。</span><span class="sxs-lookup"><span data-stu-id="0a52b-237">Replace "tenantID" with Directory (tenant) ID from step 3.a.</span></span>
   <span data-ttu-id="0a52b-238">OIDC 配置缓存生命周期</span><span class="sxs-lookup"><span data-stu-id="0a52b-238">OIDC Configuration Cache Life Span</span></span> |  <span data-ttu-id="0a52b-239">120</span><span class="sxs-lookup"><span data-stu-id="0a52b-239">120</span></span>
   <span data-ttu-id="0a52b-240">应用程序</span><span class="sxs-lookup"><span data-stu-id="0a52b-240">Application</span></span> | <span data-ttu-id="0a52b-241">全球</span><span class="sxs-lookup"><span data-stu-id="0a52b-241">Global</span></span>
   <span data-ttu-id="0a52b-242">用户声明</span><span class="sxs-lookup"><span data-stu-id="0a52b-242">User Claim</span></span> | <span data-ttu-id="0a52b-243">sub</span><span class="sxs-lookup"><span data-stu-id="0a52b-243">sub</span></span>
   <span data-ttu-id="0a52b-244">用户字段</span><span class="sxs-lookup"><span data-stu-id="0a52b-244">User Field</span></span> | <span data-ttu-id="0a52b-245">用户 ID</span><span class="sxs-lookup"><span data-stu-id="0a52b-245">User ID</span></span>
   <span data-ttu-id="0a52b-246">启用 JTI 声明验证</span><span class="sxs-lookup"><span data-stu-id="0a52b-246">Enable JTI claim verification</span></span> | <span data-ttu-id="0a52b-247">禁用</span><span class="sxs-lookup"><span data-stu-id="0a52b-247">Disabled</span></span>

5. <span data-ttu-id="0a52b-248">选择"提交并更新 OAuth OIDC 实体"表单。</span><span class="sxs-lookup"><span data-stu-id="0a52b-248">Select Submit and Update the OAuth OIDC Entity form.</span></span>

## <a name="step-3e-create-a-servicenow-account"></a><span data-ttu-id="0a52b-249">步骤 3.e：创建 ServiceNow 帐户</span><span class="sxs-lookup"><span data-stu-id="0a52b-249">Step 3.e: Create a ServiceNow account</span></span>

<span data-ttu-id="0a52b-250">请参阅有关创建 ServiceNow 帐户、在 [ServiceNow 中创建用户的说明](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-250">Refer the instructions to create a ServiceNow account, [create a user in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).</span></span>

<span data-ttu-id="0a52b-251">下表提供了有关如何填写 ServiceNow 用户帐户注册的指南</span><span class="sxs-lookup"><span data-stu-id="0a52b-251">The following table provides guidance on how to fill out the ServiceNow user account registration</span></span>

<span data-ttu-id="0a52b-252">字段</span><span class="sxs-lookup"><span data-stu-id="0a52b-252">Field</span></span> | <span data-ttu-id="0a52b-253">建议值</span><span class="sxs-lookup"><span data-stu-id="0a52b-253">Recommended Value</span></span>
--- | ---
<span data-ttu-id="0a52b-254">用户 ID</span><span class="sxs-lookup"><span data-stu-id="0a52b-254">User ID</span></span> | <span data-ttu-id="0a52b-255">步骤 3.c 中的服务主体 ID</span><span class="sxs-lookup"><span data-stu-id="0a52b-255">Service Principal ID from step 3.c</span></span>
<span data-ttu-id="0a52b-256">仅 Web 服务访问</span><span class="sxs-lookup"><span data-stu-id="0a52b-256">Web service access only</span></span> | <span data-ttu-id="0a52b-257">Checked</span><span class="sxs-lookup"><span data-stu-id="0a52b-257">Checked</span></span>

<span data-ttu-id="0a52b-258">所有其他值都可以设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="0a52b-258">All other values can be left to default.</span></span>

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a><span data-ttu-id="0a52b-259">步骤 3.f：为 ServiceNow 帐户启用"知识"角色</span><span class="sxs-lookup"><span data-stu-id="0a52b-259">Step 3.f: Enable Knowledge role for the ServiceNow account</span></span>

<span data-ttu-id="0a52b-260">访问使用 ServiceNow 主体 ID 作为用户 ID 创建的 ServiceNow 帐户，并分配知识角色。</span><span class="sxs-lookup"><span data-stu-id="0a52b-260">Access the ServiceNow account you created with ServiceNow Principal ID as User ID, and assign the knowledge role.</span></span> <span data-ttu-id="0a52b-261">有关将角色分配给 ServiceNow 帐户的说明，可在此处找到：向用户分配 [角色](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-261">Instructions to assigning a role to a ServiceNow account can be found here: [assign a role to a user](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span>

<span data-ttu-id="0a52b-262">使用步骤 3.a 中的应用程序 ID 作为客户端 ID，使用步骤 3.b 中的客户端密码，使用 Azure AD OpenID Connect 对 ServiceNow 实例进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0a52b-262">Use Application ID as Client ID from step 3.a, and Client secret from step 3.b, to authenticate to your ServiceNow instance using Azure AD OpenID Connect.</span></span>

## <a name="step-4-select-properties-and-filter-data"></a><span data-ttu-id="0a52b-263">步骤 4：选择属性和筛选数据</span><span class="sxs-lookup"><span data-stu-id="0a52b-263">Step 4: Select properties and filter data</span></span>

<span data-ttu-id="0a52b-264">在此步骤中，可以从 ServiceNow 数据源中添加或删除可用属性。</span><span class="sxs-lookup"><span data-stu-id="0a52b-264">In this step, you can add or remove available properties from your ServiceNow data source.</span></span> <span data-ttu-id="0a52b-265">默认情况下，Microsoft 365 已选择几个属性。</span><span class="sxs-lookup"><span data-stu-id="0a52b-265">Microsoft 365 has already selected few properties by default.</span></span>

<span data-ttu-id="0a52b-266">使用 ServiceNow 查询字符串，可以指定用于同步文章的条件。</span><span class="sxs-lookup"><span data-stu-id="0a52b-266">With a ServiceNow query string, you can specify conditions for syncing articles.</span></span> <span data-ttu-id="0a52b-267">它就像 **Select** 语句中的 **Where SQL** 子句。</span><span class="sxs-lookup"><span data-stu-id="0a52b-267">It's like a **Where** clause in a **SQL Select** statement.</span></span> <span data-ttu-id="0a52b-268">例如，可以选择仅对已发布和处于活动状态的文章编制索引。</span><span class="sxs-lookup"><span data-stu-id="0a52b-268">For example, you can choose to index only articles that are published and active.</span></span> <span data-ttu-id="0a52b-269">若要了解如何创建自己的查询字符串，请参阅使用筛选器生成编码 [的查询字符串](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-269">To learn about creating your own query string, see [Generate an encoded query string using a filter](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).</span></span>

<span data-ttu-id="0a52b-270">使用预览结果按钮验证所选属性和查询筛选器的示例值。</span><span class="sxs-lookup"><span data-stu-id="0a52b-270">Use the preview results button to verify the sample values of the selected properties and query filter.</span></span>

## <a name="step-5-manage-search-permissions"></a><span data-ttu-id="0a52b-271">步骤 5：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="0a52b-271">Step 5: Manage search permissions</span></span>

<span data-ttu-id="0a52b-272">ServiceNow 连接器支持对具有此数据源访问权限的 **任何人** 或仅用户可见的 **搜索权限**。</span><span class="sxs-lookup"><span data-stu-id="0a52b-272">The ServiceNow connector supports search permissions visible to **Everyone** or **Only people with access to this data source**.</span></span> <span data-ttu-id="0a52b-273">已编制索引的数据显示在搜索结果中，并且对组织中分别具有访问权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="0a52b-273">Indexed data appears in the search results and is visible to users in the organization who have access to them respectively.</span></span> <span data-ttu-id="0a52b-274">ServiceNow 连接器支持没有高级脚本的默认用户条件权限。</span><span class="sxs-lookup"><span data-stu-id="0a52b-274">ServiceNow Connector supports default user criteria permissions without advanced scripts.</span></span> <span data-ttu-id="0a52b-275">当连接器找到具有高级脚本的用户条件时，使用该用户条件的所有数据将不会显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="0a52b-275">When the connector finds a user criteria with advanced script, all data using that user criteria won't be shown in search results.</span></span>

<span data-ttu-id="0a52b-276">如果选择"仅 **有权访问** 此数据源的用户"，则需要进一步选择 ServiceNow 实例是具有 Azure Active Directory (AAD) 设置的用户还是非 AAD 用户。</span><span class="sxs-lookup"><span data-stu-id="0a52b-276">If you select **Only people with access to this data source**, you need to further choose whether your ServiceNow instance has Azure Active Directory (AAD) provisioned users or Non-AAD users.</span></span>

>[!NOTE]
><span data-ttu-id="0a52b-277">如果选择"仅有权访问此数据源的人"，则 ServiceNow 连接器为 **预览版**。</span><span class="sxs-lookup"><span data-stu-id="0a52b-277">The ServiceNow connector is in **preview** if you choose **Only people with access to this data source**.</span></span>

>[!NOTE]
><span data-ttu-id="0a52b-278">如果选择 AAD 作为标识源类型，请确保将 UPN 源属性分配给 ServiceNow 中的电子邮件目标属性。</span><span class="sxs-lookup"><span data-stu-id="0a52b-278">If you choose AAD as the type of identity source, make sure you are assigning UPN source property to email targeted property in ServiceNow.</span></span> <span data-ttu-id="0a52b-279">若要验证或更改映射，请参阅在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes)中为 SaaS 应用程序自定义用户预配属性映射。</span><span class="sxs-lookup"><span data-stu-id="0a52b-279">To verify or change your mappings, see [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes).</span></span>

<span data-ttu-id="0a52b-280">如果选择从 ServiceNow 实例中获取 ACL，并且为标识类型选择了"非 AAD"，请参阅"映射非 [Azure AD](map-non-aad.md) 标识"，获取有关映射标识的说明。</span><span class="sxs-lookup"><span data-stu-id="0a52b-280">If you chose to ingest an ACL from your ServiceNow instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

## <a name="step-6-assign-property-labels"></a><span data-ttu-id="0a52b-281">步骤 6：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="0a52b-281">Step 6: Assign property labels</span></span>

<span data-ttu-id="0a52b-282">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-282">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a><span data-ttu-id="0a52b-283">步骤 7：管理架构</span><span class="sxs-lookup"><span data-stu-id="0a52b-283">Step 7: Manage schema</span></span>

<span data-ttu-id="0a52b-284">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-284">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a><span data-ttu-id="0a52b-285">步骤 8：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="0a52b-285">Step 8: Choose refresh settings</span></span>

<span data-ttu-id="0a52b-286">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-286">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
><span data-ttu-id="0a52b-287">对于标识，将仅应用计划的完全爬网。</span><span class="sxs-lookup"><span data-stu-id="0a52b-287">For identities, only full crawl scheduled will be applied.</span></span>

## <a name="step-9-review-connection"></a><span data-ttu-id="0a52b-288">步骤 9：查看连接</span><span class="sxs-lookup"><span data-stu-id="0a52b-288">Step 9: Review Connection</span></span>

<span data-ttu-id="0a52b-289">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-289">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a><span data-ttu-id="0a52b-290">疑难解答</span><span class="sxs-lookup"><span data-stu-id="0a52b-290">Troubleshooting</span></span>

<span data-ttu-id="0a52b-291">发布连接后，自定义结果页面后，可以在管理中心的"连接器 **"选项卡**[下查看状态](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="0a52b-291">After publishing your connection, customizing the results page, you can review the status under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="0a52b-292">若要了解如何进行更新和删除，请参阅["管理连接器"。](manage-connector.md)</span><span class="sxs-lookup"><span data-stu-id="0a52b-292">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="0a52b-293">限制</span><span class="sxs-lookup"><span data-stu-id="0a52b-293">Limitations</span></span>

<span data-ttu-id="0a52b-294">ServiceNow Graph 连接器在其最新版本中具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="0a52b-294">ServiceNow Graph connector has the following limitations in its latest release:</span></span>

- <span data-ttu-id="0a52b-295">为组织中每个人都可用的知识文章编制索引是一项普遍可用的功能。</span><span class="sxs-lookup"><span data-stu-id="0a52b-295">Indexing knowledge articles available to everyone in an organization is a generally available feature.</span></span>
- <span data-ttu-id="0a52b-296">*只有具有"管理搜索权限* "步骤下此数据源功能的访问权限的用户才位于预览阶段，并且仅处理 [用户条件](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) 权限。</span><span class="sxs-lookup"><span data-stu-id="0a52b-296">*Only people with access to this data source* feature under Manage Search permissions step is in preview and processes only [user criteria](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) permissions.</span></span> <span data-ttu-id="0a52b-297">其他任何类型的访问权限不会应用于搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="0a52b-297">Any other type of access permissions won't be applied in the search results.</span></span>
- <span data-ttu-id="0a52b-298">当前预览版本中不支持具有高级脚本的用户条件。</span><span class="sxs-lookup"><span data-stu-id="0a52b-298">User criteria with advanced scripts aren't supported in the current preview version.</span></span> <span data-ttu-id="0a52b-299">对具有访问限制的知识文章编制索引时将拒绝所有人访问，并且除非我们支持，才能在搜索结果中向任何用户显示这些知识文章。</span><span class="sxs-lookup"><span data-stu-id="0a52b-299">Knowledge articles with an access restriction will be indexed with deny everyone access, and won't appear in search results to any user until we support them.</span></span>
