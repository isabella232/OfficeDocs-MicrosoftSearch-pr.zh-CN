---
title: ServiceNow Graph Microsoft 搜索连接器
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
description: 为 Microsoft 搜索设置 ServiceNow Graph连接器
ms.openlocfilehash: ac5d0b23547ce7ccd0d8bb6399b092f9bc9e5303
ms.sourcegitcommit: f12e7ff0a94d30a9de1f93266715180e7530de3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879305"
---
<!---Previous ms.author: kam1 --->


# <a name="servicenow-graph-connector"></a><span data-ttu-id="b6645-103">ServiceNow Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="b6645-103">ServiceNow Graph Connector</span></span>

<span data-ttu-id="b6645-104">借助 Microsoft Graph Connector for ServiceNow，组织可以索引对所有用户可见的知识库文章，或对组织中具有用户条件权限受限的知识库文章编制索引。</span><span class="sxs-lookup"><span data-stu-id="b6645-104">With the Microsoft Graph Connector for ServiceNow, your organization can index knowledge-base articles that are visible to all users or restricted with user criteria permissions within your organization.</span></span> <span data-ttu-id="b6645-105">从 ServiceNow 配置连接器并索引内容后，最终用户可以从任何 Microsoft 搜索客户端搜索这些文章。</span><span class="sxs-lookup"><span data-stu-id="b6645-105">After you configure the connector and index content from ServiceNow, end users can search for those articles from any Microsoft Search client.</span></span>  

<span data-ttu-id="b6645-106">本文适用于配置Microsoft 365运行和监视 ServiceNow 连接器的管理员Graph用户。</span><span class="sxs-lookup"><span data-stu-id="b6645-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a ServiceNow Graph  connector.</span></span> <span data-ttu-id="b6645-107">它补充了设置连接器文章中提供的Graph[说明](configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="b6645-107">It supplements the general instructions provided in the [Set up your Graph connector](configure-connector.md) article.</span></span> <span data-ttu-id="b6645-108">如果尚未这样做，请阅读整个设置 Graph 连接器一文，了解常规设置过程。</span><span class="sxs-lookup"><span data-stu-id="b6645-108">If you have not already done so, read the entire Set up your Graph Connector article to understand the general setup process.</span></span>

<span data-ttu-id="b6645-109">下面列出了安装过程的每一步以及一条说明，指示你应遵循常规设置说明或仅适用于 ServiceNow Graph 连接器的其他说明，包括有关疑难解答和限制[的信息。](#limitations) [](#troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="b6645-109">Each step in the setup process is listed below along with either a note that indicates you should follow the general setup instructions OR other instructions that apply to only ServiceNow Graph connector including information about [Troubleshooting](#troubleshooting) and [Limitations](#limitations).</span></span>  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b6645-110">步骤 1：在Graph管理中心中添加Microsoft 365连接器。</span><span class="sxs-lookup"><span data-stu-id="b6645-110">Step 1: Add a Graph connector in the Microsoft 365 admin center.</span></span>
<span data-ttu-id="b6645-111">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="b6645-111">Follow the general setup instructions.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="b6645-112">步骤 2：命名连接。</span><span class="sxs-lookup"><span data-stu-id="b6645-112">Step 2: Name the connection.</span></span>
<span data-ttu-id="b6645-113">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="b6645-113">Follow the general setup instructions.</span></span>


## <a name="step-3-connection-settings"></a><span data-ttu-id="b6645-114">步骤 3：连接设置</span><span class="sxs-lookup"><span data-stu-id="b6645-114">Step 3: Connection Settings</span></span>
<span data-ttu-id="b6645-115">若要连接到 ServiceNow 数据，你需要组织的 **ServiceNow 实例 URL**。</span><span class="sxs-lookup"><span data-stu-id="b6645-115">To connect to your ServiceNow data, you need your organization's **ServiceNow instance URL**.</span></span> <span data-ttu-id="b6645-116">组织的 ServiceNow 实例 URL 通常 https:// **&lt; 组织域>.service-now.com**。</span><span class="sxs-lookup"><span data-stu-id="b6645-116">Your organization’s ServiceNow instance URL typically looks like **https://&lt;your-organization-domain>.service-now.com**.</span></span> 

<span data-ttu-id="b6645-117">除了此 URL 外，还需要一个服务帐户来设置与 ServiceNow 的连接，以及允许 Microsoft 搜索根据刷新计划定期更新知识文章。</span><span class="sxs-lookup"><span data-stu-id="b6645-117">Along with this URL, you will need a **service account** for setting up the connection to ServiceNow as well as for allowing Microsoft Search to periodically update the knowledge articles based on the refresh schedule.</span></span> <span data-ttu-id="b6645-118">该服务帐户将需要对以下 **ServiceNow** 表记录的读取权限，以成功对各种实体进行爬网。</span><span class="sxs-lookup"><span data-stu-id="b6645-118">The service account will need read access to the following **ServiceNow table records** to successfully crawl various entities.</span></span>

<span data-ttu-id="b6645-119">**功能**</span><span class="sxs-lookup"><span data-stu-id="b6645-119">**Feature**</span></span> | <span data-ttu-id="b6645-120">**需要读取访问权限的表**</span><span class="sxs-lookup"><span data-stu-id="b6645-120">**Read access required tables**</span></span> | <span data-ttu-id="b6645-121">**描述**</span><span class="sxs-lookup"><span data-stu-id="b6645-121">**Description**</span></span>
--- | --- | ---
<span data-ttu-id="b6645-122">索引可供所有人使用的知识 <em>文章</em></span><span class="sxs-lookup"><span data-stu-id="b6645-122">Index knowledge articles available to <em>Everyone</em></span></span> | <span data-ttu-id="b6645-123">kb_knowledge</span><span class="sxs-lookup"><span data-stu-id="b6645-123">kb_knowledge</span></span> | <span data-ttu-id="b6645-124">用于对知识库文章进行爬网</span><span class="sxs-lookup"><span data-stu-id="b6645-124">For crawling knowledge articles</span></span>
<span data-ttu-id="b6645-125">索引和支持用户条件权限</span><span class="sxs-lookup"><span data-stu-id="b6645-125">Index and support user criteria permissions</span></span> | <span data-ttu-id="b6645-126">kb_uc_can_read_mtom</span><span class="sxs-lookup"><span data-stu-id="b6645-126">kb_uc_can_read_mtom</span></span> | <span data-ttu-id="b6645-127">Who阅读此知识库</span><span class="sxs-lookup"><span data-stu-id="b6645-127">Who can read this knowledge base</span></span>
| | <span data-ttu-id="b6645-128">kb_uc_can_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="b6645-128">kb_uc_can_contribute_mtom</span></span> | <span data-ttu-id="b6645-129">Who可参与此知识库</span><span class="sxs-lookup"><span data-stu-id="b6645-129">Who can contribute to this knowledge base</span></span>
| | <span data-ttu-id="b6645-130">kb_uc_cannot_read_mtom</span><span class="sxs-lookup"><span data-stu-id="b6645-130">kb_uc_cannot_read_mtom</span></span> | <span data-ttu-id="b6645-131">Who无法读取此知识库</span><span class="sxs-lookup"><span data-stu-id="b6645-131">Who cannot read this knowledge base</span></span>
| | <span data-ttu-id="b6645-132">kb_uc_cannot_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="b6645-132">kb_uc_cannot_contribute_mtom</span></span> | <span data-ttu-id="b6645-133">Who无法参与此知识库</span><span class="sxs-lookup"><span data-stu-id="b6645-133">Who cannot contribute to this knowledge base</span></span>
| | <span data-ttu-id="b6645-134">sys_user</span><span class="sxs-lookup"><span data-stu-id="b6645-134">sys_user</span></span> | <span data-ttu-id="b6645-135">读取用户表</span><span class="sxs-lookup"><span data-stu-id="b6645-135">Read user table</span></span>
| | <span data-ttu-id="b6645-136">sys_user_has_role</span><span class="sxs-lookup"><span data-stu-id="b6645-136">sys_user_has_role</span></span> | <span data-ttu-id="b6645-137">读取用户的角色信息</span><span class="sxs-lookup"><span data-stu-id="b6645-137">Read role information of users</span></span>
| | <span data-ttu-id="b6645-138">sys_user_grmember</span><span class="sxs-lookup"><span data-stu-id="b6645-138">sys_user_grmember</span></span> | <span data-ttu-id="b6645-139">读取用户的组成员身份</span><span class="sxs-lookup"><span data-stu-id="b6645-139">Read group membership of users</span></span>
| | <span data-ttu-id="b6645-140">user_criteria</span><span class="sxs-lookup"><span data-stu-id="b6645-140">user_criteria</span></span> | <span data-ttu-id="b6645-141">读取用户条件权限</span><span class="sxs-lookup"><span data-stu-id="b6645-141">Read user criteria permissions</span></span>
| | <span data-ttu-id="b6645-142">kb_knowledge_base</span><span class="sxs-lookup"><span data-stu-id="b6645-142">kb_knowledge_base</span></span> | <span data-ttu-id="b6645-143">读取知识库信息</span><span class="sxs-lookup"><span data-stu-id="b6645-143">Read knowledge base information</span></span>

<span data-ttu-id="b6645-144">你可以 **为用于与** Microsoft 搜索连接的服务帐户创建和分配角色。</span><span class="sxs-lookup"><span data-stu-id="b6645-144">You can **create and assign a role** for the service account you use to connect with Microsoft Search.</span></span> <span data-ttu-id="b6645-145">[了解如何为 ServiceNow 帐户分配角色](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="b6645-145">[Learn how to assign role for ServiceNow accounts](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span> <span data-ttu-id="b6645-146">可以在已创建的角色上分配表的读取权限。</span><span class="sxs-lookup"><span data-stu-id="b6645-146">Read access to the tables can be assigned on the created role.</span></span> <span data-ttu-id="b6645-147">若要了解如何设置对表记录的读取访问权限，请参阅 [保护表记录](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)。</span><span class="sxs-lookup"><span data-stu-id="b6645-147">To learn about setting read access to table records, see [Securing Table Records](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls).</span></span> 


>[!NOTE]
> <span data-ttu-id="b6645-148">ServiceNow Graph 连接器可以在没有高级脚本的情况下对知识库文章和用户条件权限编制索引。</span><span class="sxs-lookup"><span data-stu-id="b6645-148">ServiceNow Graph Connector can index knowledge articles and user criteria permissions without advanced scripts.</span></span> <span data-ttu-id="b6645-149">如果用户条件包含高级脚本，将在搜索结果中隐藏所有相关的知识库文章。</span><span class="sxs-lookup"><span data-stu-id="b6645-149">If a user criteria contains advanced script all the related knowledge articles will be hidden from search results.</span></span>

<span data-ttu-id="b6645-150">若要对 ServiceNow 中的内容进行身份验证和同步，请选择 **以下三种受支持的方法** 之一：</span><span class="sxs-lookup"><span data-stu-id="b6645-150">To authenticate and sync content from ServiceNow, choose **one of three** supported methods:</span></span> 
 
- <span data-ttu-id="b6645-151">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="b6645-151">Basic authentication</span></span> 
- <span data-ttu-id="b6645-152">ServiceNow OAuth (推荐) </span><span class="sxs-lookup"><span data-stu-id="b6645-152">ServiceNow OAuth (recommended)</span></span>
- <span data-ttu-id="b6645-153">Azure AD OpenID 连接</span><span class="sxs-lookup"><span data-stu-id="b6645-153">Azure AD OpenID Connect</span></span>

## <a name="step-31-basic-authentication"></a><span data-ttu-id="b6645-154">步骤 3.1：基本身份验证</span><span class="sxs-lookup"><span data-stu-id="b6645-154">Step 3.1: Basic authentication</span></span>

<span data-ttu-id="b6645-155">输入具有知识角色的 ServiceNow 帐户 **的用户名和密码** ，以向实例进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b6645-155">Enter the username and password of ServiceNow account with **knowledge** role to authenticate to your instance.</span></span>

## <a name="step-32-servicenow-oauth"></a><span data-ttu-id="b6645-156">步骤 3.2：ServiceNow OAuth</span><span class="sxs-lookup"><span data-stu-id="b6645-156">Step 3.2: ServiceNow OAuth</span></span>

<span data-ttu-id="b6645-157">若要使用 ServiceNow OAuth 进行身份验证，ServiceNow 管理员需要在 ServiceNow 实例中设置终结点，以便 Microsoft 搜索应用可以访问它。</span><span class="sxs-lookup"><span data-stu-id="b6645-157">To use ServiceNow OAuth for authentication, a ServiceNow admin needs to provision an endpoint in your ServiceNow instance, so that the Microsoft Search app can access it.</span></span> <span data-ttu-id="b6645-158">若要了解更多信息，请参阅[](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html)ServiceNow 文档中的为客户端创建用于访问实例的终结点。</span><span class="sxs-lookup"><span data-stu-id="b6645-158">To learn more, see [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in the ServiceNow documentation.</span></span>

<span data-ttu-id="b6645-159">下表提供了有关如何填写终结点创建表单的指导：</span><span class="sxs-lookup"><span data-stu-id="b6645-159">The following table provides guidance on how to fill out the endpoint creation form:</span></span>

<span data-ttu-id="b6645-160">字段</span><span class="sxs-lookup"><span data-stu-id="b6645-160">Field</span></span> | <span data-ttu-id="b6645-161">说明</span><span class="sxs-lookup"><span data-stu-id="b6645-161">Description</span></span> | <span data-ttu-id="b6645-162">建议值</span><span class="sxs-lookup"><span data-stu-id="b6645-162">Recommended Value</span></span> 
--- | --- | ---
<span data-ttu-id="b6645-163">名称</span><span class="sxs-lookup"><span data-stu-id="b6645-163">Name</span></span> | <span data-ttu-id="b6645-164">标识需要 OAuth 访问的应用程序的唯一值。</span><span class="sxs-lookup"><span data-stu-id="b6645-164">Unique value that identifies the application that you require OAuth access for.</span></span> | <span data-ttu-id="b6645-165">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="b6645-165">Microsoft Search</span></span>
<span data-ttu-id="b6645-166">客户端 ID</span><span class="sxs-lookup"><span data-stu-id="b6645-166">Client ID</span></span> | <span data-ttu-id="b6645-167">应用程序的只读自动生成的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="b6645-167">A read-only, auto generated unique ID for the application.</span></span> <span data-ttu-id="b6645-168">实例在请求访问令牌时使用客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="b6645-168">The instance uses the client ID when it requests an access token.</span></span> | <span data-ttu-id="b6645-169">不适用</span><span class="sxs-lookup"><span data-stu-id="b6645-169">NA</span></span>
<span data-ttu-id="b6645-170">客户端密码</span><span class="sxs-lookup"><span data-stu-id="b6645-170">Client secret</span></span> | <span data-ttu-id="b6645-171">通过此共享密码字符串，ServiceNow 实例和 Microsoft 搜索可授权相互通信。</span><span class="sxs-lookup"><span data-stu-id="b6645-171">With this shared secret string, the ServiceNow instance and Microsoft Search authorize communications with each other.</span></span> | <span data-ttu-id="b6645-172">通过将密码视为密码来遵循安全性最佳做法。</span><span class="sxs-lookup"><span data-stu-id="b6645-172">Follow security best-practices by treating the secret as a password.</span></span>
<span data-ttu-id="b6645-173">重定向 URL</span><span class="sxs-lookup"><span data-stu-id="b6645-173">Redirect URL</span></span> | <span data-ttu-id="b6645-174">授权服务器重定向到的必需回调 URL。</span><span class="sxs-lookup"><span data-stu-id="b6645-174">A required callback URL that the authorization server redirects to.</span></span> | https://gcs.office.com/v1.0/admin/oauth/callback
<span data-ttu-id="b6645-175">徽标 URL</span><span class="sxs-lookup"><span data-stu-id="b6645-175">Logo URL</span></span> | <span data-ttu-id="b6645-176">包含应用程序徽标的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="b6645-176">A URL that contains the image for the application logo.</span></span> | <span data-ttu-id="b6645-177">不适用</span><span class="sxs-lookup"><span data-stu-id="b6645-177">NA</span></span>
<span data-ttu-id="b6645-178">活动</span><span class="sxs-lookup"><span data-stu-id="b6645-178">Active</span></span> | <span data-ttu-id="b6645-179">选中此复选框可以使应用程序注册表处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b6645-179">Select the check box to make the application registry active.</span></span> | <span data-ttu-id="b6645-180">设置为活动</span><span class="sxs-lookup"><span data-stu-id="b6645-180">Set to active</span></span>
<span data-ttu-id="b6645-181">刷新令牌有效期</span><span class="sxs-lookup"><span data-stu-id="b6645-181">Refresh token lifespan</span></span> | <span data-ttu-id="b6645-182">刷新令牌有效的秒数。</span><span class="sxs-lookup"><span data-stu-id="b6645-182">The number of seconds that a refresh token is valid.</span></span> <span data-ttu-id="b6645-183">默认情况下，刷新令牌在 100 天后过期 (8，640，000 秒) 。</span><span class="sxs-lookup"><span data-stu-id="b6645-183">By default, refresh tokens expire in 100 days (8,640,000 seconds).</span></span> | <span data-ttu-id="b6645-184">31，536，000 (年 1) </span><span class="sxs-lookup"><span data-stu-id="b6645-184">31,536,000 (1 year)</span></span>
<span data-ttu-id="b6645-185">访问令牌有效期</span><span class="sxs-lookup"><span data-stu-id="b6645-185">Access token lifespan</span></span> | <span data-ttu-id="b6645-186">访问令牌有效的秒数。</span><span class="sxs-lookup"><span data-stu-id="b6645-186">The number of seconds that an access token is valid.</span></span> | <span data-ttu-id="b6645-187">43，200 (12 小时) </span><span class="sxs-lookup"><span data-stu-id="b6645-187">43,200 (12 hours)</span></span>

<span data-ttu-id="b6645-188">输入客户端 ID 和客户端密码以连接到实例。</span><span class="sxs-lookup"><span data-stu-id="b6645-188">Enter the client id and client secret to connect to your instance.</span></span> <span data-ttu-id="b6645-189">连接后，使用 ServiceNow 帐户凭据对爬网权限进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b6645-189">After connecting, use a ServiceNow account credential to authenticate permission to crawl.</span></span> <span data-ttu-id="b6645-190">帐户应至少具有 **知识** 角色。</span><span class="sxs-lookup"><span data-stu-id="b6645-190">The account should at least have **knowledge** role.</span></span> <span data-ttu-id="b6645-191">参考步骤 [3：连接](#step-3-connection-settings) 设置开头的表，该表格提供对更多 ServiceNow 表记录和索引用户条件权限的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="b6645-191">Refer the table in the beginning of [step 3: connection settings](#step-3-connection-settings) for providing read access to more ServiceNow table records and index user criteria permissions.</span></span>

## <a name="step-33-azure-ad-openid-connect"></a><span data-ttu-id="b6645-192">步骤 3.3：Azure AD OpenID 连接</span><span class="sxs-lookup"><span data-stu-id="b6645-192">Step 3.3: Azure AD OpenID Connect</span></span>

<span data-ttu-id="b6645-193">若要使用 Azure AD OpenID 连接进行身份验证，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="b6645-193">To use Azure AD OpenID Connect for authentication, follow the steps below.</span></span>

### <a name="step-331-register-a-new-application-in-azure-active-directory"></a><span data-ttu-id="b6645-194">步骤 3.3.1：在 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b6645-194">Step 3.3.1: Register a new application in Azure Active Directory</span></span>

<span data-ttu-id="b6645-195">若要了解如何在应用程序中注册新Azure Active Directory，请参阅[注册应用程序](/azure/active-directory/develop/quickstart-register-app#register-an-application)。</span><span class="sxs-lookup"><span data-stu-id="b6645-195">To learn about registering a new application in Azure Active Directory, see [Register an application](/azure/active-directory/develop/quickstart-register-app#register-an-application).</span></span> <span data-ttu-id="b6645-196">选择单个租户组织目录。</span><span class="sxs-lookup"><span data-stu-id="b6645-196">Select single tenant organizational directory.</span></span> <span data-ttu-id="b6645-197">不需要重定向 URI。</span><span class="sxs-lookup"><span data-stu-id="b6645-197">Redirect URI isn't needed.</span></span> <span data-ttu-id="b6645-198">注册后，记下应用程序 (客户端) ID 和目录 (租户) ID。</span><span class="sxs-lookup"><span data-stu-id="b6645-198">After registration, note down the Application (client) ID and Directory (tenant) ID.</span></span>

### <a name="step-332-create-a-client-secret"></a><span data-ttu-id="b6645-199">步骤 3.3.2：创建客户端密码</span><span class="sxs-lookup"><span data-stu-id="b6645-199">Step 3.3.2: Create a client secret</span></span>

<span data-ttu-id="b6645-200">若要了解如何创建客户端密码，请参阅创建 [客户端密码](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。</span><span class="sxs-lookup"><span data-stu-id="b6645-200">To learn about creating a client secret, see [Creating a client secret](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).</span></span> <span data-ttu-id="b6645-201">记下客户端密码。</span><span class="sxs-lookup"><span data-stu-id="b6645-201">Take a note of client secret.</span></span>

### <a name="step-333-retrieve-service-principal-object-identifier"></a><span data-ttu-id="b6645-202">步骤 3.3.3：检索服务主体对象标识符</span><span class="sxs-lookup"><span data-stu-id="b6645-202">Step 3.3.3: Retrieve Service Principal Object Identifier</span></span>

<span data-ttu-id="b6645-203">按照步骤检索服务主体对象标识符</span><span class="sxs-lookup"><span data-stu-id="b6645-203">Follow the steps to retrieve Service Principal Object Identifier</span></span>

1. <span data-ttu-id="b6645-204">运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b6645-204">Run PowerShell.</span></span>

2. <span data-ttu-id="b6645-205">使用Azure PowerShell安装客户端。</span><span class="sxs-lookup"><span data-stu-id="b6645-205">Install Azure PowerShell using the following command.</span></span>

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. <span data-ttu-id="b6645-206">连接 Azure。</span><span class="sxs-lookup"><span data-stu-id="b6645-206">Connect to Azure.</span></span>

   ```powershell
   Connect-AzAccount
   ```

4. <span data-ttu-id="b6645-207">获取服务主体对象标识符。</span><span class="sxs-lookup"><span data-stu-id="b6645-207">Get Service Principal Object Identifier.</span></span>

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   <span data-ttu-id="b6645-208">将"Application-ID"替换为 Application (client) ID (，而不) 步骤 3.a 中注册的应用程序的引号。</span><span class="sxs-lookup"><span data-stu-id="b6645-208">Replace "Application-ID" with Application (client) ID (without quotes) of the application you registered in step 3.a.</span></span> <span data-ttu-id="b6645-209">请注意 PowerShell 输出中的 ID 对象的值。</span><span class="sxs-lookup"><span data-stu-id="b6645-209">Note the value of ID object from PowerShell output.</span></span> <span data-ttu-id="b6645-210">它是服务主体 ID。</span><span class="sxs-lookup"><span data-stu-id="b6645-210">It's the Service Principal ID.</span></span>

<span data-ttu-id="b6645-211">现在，你已拥有 Azure 门户中需要的所有信息。</span><span class="sxs-lookup"><span data-stu-id="b6645-211">Now you have all the information required from Azure portal.</span></span> <span data-ttu-id="b6645-212">下表提供了信息的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="b6645-212">A quick summary of the information is given in the table below.</span></span>

<span data-ttu-id="b6645-213">属性</span><span class="sxs-lookup"><span data-stu-id="b6645-213">Property</span></span> | <span data-ttu-id="b6645-214">说明</span><span class="sxs-lookup"><span data-stu-id="b6645-214">Description</span></span> 
--- | ---
<span data-ttu-id="b6645-215">租户 ID (的目录 ID) </span><span class="sxs-lookup"><span data-stu-id="b6645-215">Directory ID (Tenant ID)</span></span> | <span data-ttu-id="b6645-216">步骤 3.a Azure Active Directory租户的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="b6645-216">Unique ID of the Azure Active Directory tenant, from step 3.a.</span></span>
<span data-ttu-id="b6645-217">客户端 ID (应用程序 ID) </span><span class="sxs-lookup"><span data-stu-id="b6645-217">Application ID (Client ID)</span></span> | <span data-ttu-id="b6645-218">步骤 3.a 中注册的应用程序的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="b6645-218">Unique ID of the application registered in step 3.a.</span></span>
<span data-ttu-id="b6645-219">客户端密码</span><span class="sxs-lookup"><span data-stu-id="b6645-219">Client Secret</span></span> | <span data-ttu-id="b6645-220">应用程序的密钥从步骤 3.b (开始) 。</span><span class="sxs-lookup"><span data-stu-id="b6645-220">The secret key of the application (from step 3.b).</span></span> <span data-ttu-id="b6645-221">请像处理密码一样处理它。</span><span class="sxs-lookup"><span data-stu-id="b6645-221">Treat it like a password.</span></span>
<span data-ttu-id="b6645-222">服务主体 ID</span><span class="sxs-lookup"><span data-stu-id="b6645-222">Service Principal ID</span></span> | <span data-ttu-id="b6645-223">作为服务运行的应用程序的标识。</span><span class="sxs-lookup"><span data-stu-id="b6645-223">An identity for the application running as a service.</span></span> <span data-ttu-id="b6645-224"> (步骤 3.c) </span><span class="sxs-lookup"><span data-stu-id="b6645-224">(from step 3.c)</span></span>

### <a name="step-334-register-servicenow-application"></a><span data-ttu-id="b6645-225">步骤 3.3.4：注册 ServiceNow 应用程序</span><span class="sxs-lookup"><span data-stu-id="b6645-225">Step 3.3.4: Register ServiceNow Application</span></span>

<span data-ttu-id="b6645-226">ServiceNow 实例需要以下配置：</span><span class="sxs-lookup"><span data-stu-id="b6645-226">The ServiceNow instance needs the following configuration:</span></span>

1. <span data-ttu-id="b6645-227">注册新的 OAuth OIDC 实体。</span><span class="sxs-lookup"><span data-stu-id="b6645-227">Register a new OAuth OIDC entity.</span></span> <span data-ttu-id="b6645-228">若要了解，请参阅 [创建 OAuth OIDC 提供程序](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)。</span><span class="sxs-lookup"><span data-stu-id="b6645-228">To learn, see [Create an OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).</span></span>

2. <span data-ttu-id="b6645-229">下表提供了有关如何填写 OIDC 提供程序注册表单的指导</span><span class="sxs-lookup"><span data-stu-id="b6645-229">The following table provides guidance on how to fill out OIDC provider registration form</span></span>

   <span data-ttu-id="b6645-230">字段</span><span class="sxs-lookup"><span data-stu-id="b6645-230">Field</span></span> | <span data-ttu-id="b6645-231">说明</span><span class="sxs-lookup"><span data-stu-id="b6645-231">Description</span></span> | <span data-ttu-id="b6645-232">建议值</span><span class="sxs-lookup"><span data-stu-id="b6645-232">Recommended Value</span></span>
   --- | --- | ---
   <span data-ttu-id="b6645-233">名称</span><span class="sxs-lookup"><span data-stu-id="b6645-233">Name</span></span> | <span data-ttu-id="b6645-234">标识 OAuth OIDC 实体的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="b6645-234">A unique name that identifies the OAuth OIDC entity.</span></span> | <span data-ttu-id="b6645-235">Azure AD</span><span class="sxs-lookup"><span data-stu-id="b6645-235">Azure AD</span></span>
   <span data-ttu-id="b6645-236">客户端 ID</span><span class="sxs-lookup"><span data-stu-id="b6645-236">Client ID</span></span> | <span data-ttu-id="b6645-237">第三方 OAuth OIDC 服务器中注册的应用程序的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="b6645-237">The client ID of the application registered in the third-party OAuth OIDC server.</span></span> <span data-ttu-id="b6645-238">实例在请求访问令牌时使用客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="b6645-238">The instance uses the client ID when requesting an access token.</span></span> | <span data-ttu-id="b6645-239">步骤 3 (客户端) ID</span><span class="sxs-lookup"><span data-stu-id="b6645-239">Application (Client) ID from step 3.a</span></span>
   <span data-ttu-id="b6645-240">客户端密码</span><span class="sxs-lookup"><span data-stu-id="b6645-240">Client Secret</span></span> | <span data-ttu-id="b6645-241">第三方 OAuth OIDC 服务器中注册的应用程序的客户端密码。</span><span class="sxs-lookup"><span data-stu-id="b6645-241">The client secret of the application registered in the third-party OAuth OIDC server.</span></span> | <span data-ttu-id="b6645-242">步骤 3.b 中的客户端密码</span><span class="sxs-lookup"><span data-stu-id="b6645-242">Client Secret from step 3.b</span></span>

   <span data-ttu-id="b6645-243">所有其他值都可以为默认值。</span><span class="sxs-lookup"><span data-stu-id="b6645-243">All other values can be default.</span></span>

3. <span data-ttu-id="b6645-244">在 OIDC 提供程序注册表单中，需要添加新的 OIDC 提供程序配置。</span><span class="sxs-lookup"><span data-stu-id="b6645-244">In the OIDC provider registration form, you need to add a new OIDC provider configuration.</span></span> <span data-ttu-id="b6645-245">选择针对 *OAuth OIDC 提供程序配置字段的* 搜索图标以打开 OIDC 配置的记录。</span><span class="sxs-lookup"><span data-stu-id="b6645-245">Select the search icon against *OAuth OIDC Provider Configuration* field to open the records of OIDC configurations.</span></span> <span data-ttu-id="b6645-246">选择"新建"。</span><span class="sxs-lookup"><span data-stu-id="b6645-246">Select New.</span></span>

4. <span data-ttu-id="b6645-247">下表提供了有关如何填写 OIDC 提供程序配置表单的指南</span><span class="sxs-lookup"><span data-stu-id="b6645-247">The following table provides guidance on how to fill out OIDC provider configuration form</span></span>

   <span data-ttu-id="b6645-248">字段</span><span class="sxs-lookup"><span data-stu-id="b6645-248">Field</span></span> | <span data-ttu-id="b6645-249">建议值</span><span class="sxs-lookup"><span data-stu-id="b6645-249">Recommended Value</span></span>
   --- | ---
   <span data-ttu-id="b6645-250">OIDC 提供程序</span><span class="sxs-lookup"><span data-stu-id="b6645-250">OIDC Provider</span></span> |  <span data-ttu-id="b6645-251">Azure AD</span><span class="sxs-lookup"><span data-stu-id="b6645-251">Azure AD</span></span>
   <span data-ttu-id="b6645-252">OIDC 元数据 URL</span><span class="sxs-lookup"><span data-stu-id="b6645-252">OIDC Metadata URL</span></span> | <span data-ttu-id="b6645-253">URL 格式必须为 https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration</span><span class="sxs-lookup"><span data-stu-id="b6645-253">The URL must be in the form https\://login.microsoftonline.com/<tenandId">/.well-known/openid-configuration</span></span> <br/><span data-ttu-id="b6645-254">将"tenantID"替换为步骤 3.a 中的 (租户) ID。</span><span class="sxs-lookup"><span data-stu-id="b6645-254">Replace "tenantID" with Directory (tenant) ID from step 3.a.</span></span>
   <span data-ttu-id="b6645-255">OIDC 配置缓存生命周期</span><span class="sxs-lookup"><span data-stu-id="b6645-255">OIDC Configuration Cache Life Span</span></span> |  <span data-ttu-id="b6645-256">120</span><span class="sxs-lookup"><span data-stu-id="b6645-256">120</span></span>
   <span data-ttu-id="b6645-257">应用程序</span><span class="sxs-lookup"><span data-stu-id="b6645-257">Application</span></span> | <span data-ttu-id="b6645-258">全局</span><span class="sxs-lookup"><span data-stu-id="b6645-258">Global</span></span>
   <span data-ttu-id="b6645-259">用户声明</span><span class="sxs-lookup"><span data-stu-id="b6645-259">User Claim</span></span> | <span data-ttu-id="b6645-260">sub</span><span class="sxs-lookup"><span data-stu-id="b6645-260">sub</span></span>
   <span data-ttu-id="b6645-261">用户字段</span><span class="sxs-lookup"><span data-stu-id="b6645-261">User Field</span></span> | <span data-ttu-id="b6645-262">用户 ID</span><span class="sxs-lookup"><span data-stu-id="b6645-262">User ID</span></span>
   <span data-ttu-id="b6645-263">启用 JTI 声明验证</span><span class="sxs-lookup"><span data-stu-id="b6645-263">Enable JTI claim verification</span></span> | <span data-ttu-id="b6645-264">禁用</span><span class="sxs-lookup"><span data-stu-id="b6645-264">Disabled</span></span>

5. <span data-ttu-id="b6645-265">选择"提交并更新 OAuth OIDC 实体"表单。</span><span class="sxs-lookup"><span data-stu-id="b6645-265">Select Submit and Update the OAuth OIDC Entity form.</span></span>

### <a name="step-335-create-a-servicenow-account"></a><span data-ttu-id="b6645-266">步骤 3.3.5：创建 ServiceNow 帐户</span><span class="sxs-lookup"><span data-stu-id="b6645-266">Step 3.3.5: Create a ServiceNow account</span></span>

<span data-ttu-id="b6645-267">请参阅创建 ServiceNow 帐户、在 [ServiceNow 中创建用户的说明](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="b6645-267">Refer the instructions to create a ServiceNow account, [create a user in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).</span></span>

<span data-ttu-id="b6645-268">下表提供了有关如何填写 ServiceNow 用户帐户注册的指南</span><span class="sxs-lookup"><span data-stu-id="b6645-268">The following table provides guidance on how to fill out the ServiceNow user account registration</span></span>

<span data-ttu-id="b6645-269">字段</span><span class="sxs-lookup"><span data-stu-id="b6645-269">Field</span></span> | <span data-ttu-id="b6645-270">建议值</span><span class="sxs-lookup"><span data-stu-id="b6645-270">Recommended Value</span></span>
--- | ---
<span data-ttu-id="b6645-271">用户 ID</span><span class="sxs-lookup"><span data-stu-id="b6645-271">User ID</span></span> | <span data-ttu-id="b6645-272">步骤 3.c 中的服务主体 ID</span><span class="sxs-lookup"><span data-stu-id="b6645-272">Service Principal ID from step 3.c</span></span>
<span data-ttu-id="b6645-273">仅 Web 服务访问</span><span class="sxs-lookup"><span data-stu-id="b6645-273">Web service access only</span></span> | <span data-ttu-id="b6645-274">Checked</span><span class="sxs-lookup"><span data-stu-id="b6645-274">Checked</span></span>

<span data-ttu-id="b6645-275">所有其他值都可以留为默认值。</span><span class="sxs-lookup"><span data-stu-id="b6645-275">All other values can be left to default.</span></span>

### <a name="step-336-enable-knowledge-role-for-the-servicenow-account"></a><span data-ttu-id="b6645-276">步骤 3.3.6：为 ServiceNow 帐户启用知识角色</span><span class="sxs-lookup"><span data-stu-id="b6645-276">Step 3.3.6: Enable Knowledge role for the ServiceNow account</span></span>

<span data-ttu-id="b6645-277">访问使用 ServiceNow 主体 ID 作为用户 ID 创建的 ServiceNow 帐户，并分配知识角色。</span><span class="sxs-lookup"><span data-stu-id="b6645-277">Access the ServiceNow account you created with ServiceNow Principal ID as User ID and assign the knowledge role.</span></span> <span data-ttu-id="b6645-278">可以在此处找到将角色分配给 ServiceNow 帐户的说明，将角色 [分配给用户](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="b6645-278">Instructions to assigning a role to a ServiceNow account can be found here, [assign a role to a user](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span> <span data-ttu-id="b6645-279">参考步骤 [3：连接](#step-3-connection-settings) 设置开头的表，该表格提供对更多 ServiceNow 表记录和索引用户条件权限的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="b6645-279">Refer the table in the beginning of [step 3: connection settings](#step-3-connection-settings) for providing read access to more ServiceNow table records and index user criteria permissions.</span></span>

<span data-ttu-id="b6645-280">在管理中心配置向导中，将应用程序 ID 用作步骤 3.a) 中的客户端 ID (和步骤 3.b) 中的客户端密码 (，以使用 Azure AD OpenID 连接 向 ServiceNow 实例进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b6645-280">Use Application ID as Client ID (from step 3.a), and Client secret (from step 3.b) in admin center configuration wizard to authenticate to your ServiceNow instance using Azure AD OpenID Connect.</span></span>

## <a name="step-4-select-properties-and-filter-data"></a><span data-ttu-id="b6645-281">步骤 4：选择属性和筛选数据</span><span class="sxs-lookup"><span data-stu-id="b6645-281">Step 4: Select properties and filter data</span></span>

<span data-ttu-id="b6645-282">在此步骤中，可以从 ServiceNow 数据源中添加或删除可用属性。</span><span class="sxs-lookup"><span data-stu-id="b6645-282">In this step, you can add or remove available properties from your ServiceNow data source.</span></span> <span data-ttu-id="b6645-283">Microsoft 365已默认选择了几个属性。</span><span class="sxs-lookup"><span data-stu-id="b6645-283">Microsoft 365 has already selected few properties by default.</span></span>

<span data-ttu-id="b6645-284">使用 ServiceNow 查询字符串，可以指定用于同步文章的条件。</span><span class="sxs-lookup"><span data-stu-id="b6645-284">With a ServiceNow query string, you can specify conditions for syncing articles.</span></span> <span data-ttu-id="b6645-285">它就像 Select 语句中的 **Where** **SQL** 子句。</span><span class="sxs-lookup"><span data-stu-id="b6645-285">It's like a **Where** clause in a **SQL Select** statement.</span></span> <span data-ttu-id="b6645-286">例如，可以选择仅对已发布和处于活动状态的文章编制索引。</span><span class="sxs-lookup"><span data-stu-id="b6645-286">For example, you can choose to index only articles that are published and active.</span></span> <span data-ttu-id="b6645-287">若要了解如何创建自己的查询字符串，请参阅使用筛选器生成编码 [的查询字符串](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。</span><span class="sxs-lookup"><span data-stu-id="b6645-287">To learn about creating your own query string, see [Generate an encoded query string using a filter](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).</span></span>

<span data-ttu-id="b6645-288">使用"预览结果"按钮验证所选属性和查询筛选器的示例值。</span><span class="sxs-lookup"><span data-stu-id="b6645-288">Use the preview results button to verify the sample values of the selected properties and query filter.</span></span>

## <a name="step-5-manage-search-permissions"></a><span data-ttu-id="b6645-289">步骤 5：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="b6645-289">Step 5: Manage search permissions</span></span>

<span data-ttu-id="b6645-290">ServiceNow 连接器支持对"任何人"或"仅有权访问此数据源的人"**可见的搜索权限**。</span><span class="sxs-lookup"><span data-stu-id="b6645-290">The ServiceNow connector supports search permissions visible to **Everyone** or **Only people with access to this data source**.</span></span> <span data-ttu-id="b6645-291">索引数据显示在搜索结果中，并且对组织中所有用户或分别可通过用户条件权限访问它们的用户可见。</span><span class="sxs-lookup"><span data-stu-id="b6645-291">Indexed data appears in the search results and is visible to all users in the organization or users who have access to them via user criteria permission respectively.</span></span> <span data-ttu-id="b6645-292">如果未使用用户条件启用知识库文章，则它将出现在组织中所有人的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="b6645-292">If a knowledge article is not enabled with a user criteria, it will appear in search results of everyone in the organization.</span></span>

<span data-ttu-id="b6645-293">ServiceNow Graph 连接器支持不带高级脚本的默认用户条件权限。</span><span class="sxs-lookup"><span data-stu-id="b6645-293">ServiceNow Graph Connector supports default user criteria permissions without advanced scripts.</span></span> <span data-ttu-id="b6645-294">当连接器遇到具有高级脚本的用户条件时，使用该用户条件的所有数据将不会显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="b6645-294">When the connector encounters a user criteria with advanced script, all data using that user criteria will not appear in search results.</span></span>

>[!NOTE]
><span data-ttu-id="b6645-295">若要选择 **"仅有权访问此数据源的人"，** 请对租户启用定向发布更新。</span><span class="sxs-lookup"><span data-stu-id="b6645-295">To choose **Only people with access to this data source**, enable targeted release updates on your tenant.</span></span> <span data-ttu-id="b6645-296">若要了解如何设置定向发布，请参阅设置 [定向发布选项。](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="b6645-296">To learn about setting up targeted release, see [Setup Targeted release options.](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)</span></span>

<span data-ttu-id="b6645-297">如果选择"仅有权访问此数据源的用户 **"，** 则需要进一步选择 ServiceNow 实例是否Azure Active Directory (AAD) 用户或非 AAD 用户。</span><span class="sxs-lookup"><span data-stu-id="b6645-297">If you choose **Only people with access to this data source**, you need to further choose whether your ServiceNow instance has Azure Active Directory (AAD) provisioned users or Non-AAD users.</span></span>

>[!NOTE]
><span data-ttu-id="b6645-298">如果选择 AAD 作为标识源类型，请确保将 UserPrincipalName (UPN) 属性分配给 ServiceNow 中的电子邮件目标属性。</span><span class="sxs-lookup"><span data-stu-id="b6645-298">If you choose AAD as the type of identity source, make sure you are assigning UserPrincipalName (UPN) source property to email targeted property in ServiceNow.</span></span> <span data-ttu-id="b6645-299">若要验证或更改映射，请参阅自定义 SaaS 应用程序中的用户预配属性[Azure Active Directory。](/azure/active-directory/app-provisioning/customize-application-attributes)</span><span class="sxs-lookup"><span data-stu-id="b6645-299">To verify or change your mappings, see [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](/azure/active-directory/app-provisioning/customize-application-attributes).</span></span>

<span data-ttu-id="b6645-300">如果你为标识类型选择"非 AAD"，请参阅映射非 [Azure AD](map-non-aad.md) 标识，获取有关映射标识的说明。</span><span class="sxs-lookup"><span data-stu-id="b6645-300">If you have elected "non-AAD" for the identity type see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span> 

<span data-ttu-id="b6645-301">还可以参考以下视频，了解有关管理搜索权限的更多内容。</span><span class="sxs-lookup"><span data-stu-id="b6645-301">You can also refer the following video to learn more about managing search permissions.</span></span>

<span data-ttu-id="b6645-302">[![Managing Search Permissions in Microsoft Graph Connector for ServiceNow](https://img.youtube.com/vi/TVSkJpk1RiE/hqdefault.jpg)](https://www.youtube.com/watch?v=TVSkJpk1RiE)</span><span class="sxs-lookup"><span data-stu-id="b6645-302">[![Managing Search Permissions in Microsoft Graph Connector for ServiceNow](https://img.youtube.com/vi/TVSkJpk1RiE/hqdefault.jpg)](https://www.youtube.com/watch?v=TVSkJpk1RiE)</span></span>

## <a name="step-6-assign-property-labels"></a><span data-ttu-id="b6645-303">步骤 6：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="b6645-303">Step 6: Assign property labels</span></span>

<span data-ttu-id="b6645-304">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="b6645-304">Follow the general setup instructions.</span></span>

## <a name="step-7-manage-schema"></a><span data-ttu-id="b6645-305">步骤 7：管理架构</span><span class="sxs-lookup"><span data-stu-id="b6645-305">Step 7: Manage schema</span></span>

<span data-ttu-id="b6645-306">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="b6645-306">Follow the general setup instructions.</span></span>

## <a name="step-8-choose-refresh-settings"></a><span data-ttu-id="b6645-307">步骤 8：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="b6645-307">Step 8: Choose refresh settings</span></span>

<span data-ttu-id="b6645-308">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="b6645-308">Follow the general setup instructions.</span></span>

>[!NOTE]
><span data-ttu-id="b6645-309">对于标识，将仅应用计划的完全爬网。</span><span class="sxs-lookup"><span data-stu-id="b6645-309">For identities, only full crawl scheduled will be applied.</span></span>

## <a name="step-9-review-connection"></a><span data-ttu-id="b6645-310">步骤 9：查看连接</span><span class="sxs-lookup"><span data-stu-id="b6645-310">Step 9: Review Connection</span></span>

<span data-ttu-id="b6645-311">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="b6645-311">Follow the general [setup instructions](./configure-connector.md).</span></span>

<span data-ttu-id="b6645-312">ServiceNow Graph连接器在其最新版本中具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="b6645-312">ServiceNow Graph connector has the following limitations in its latest release:</span></span>

<span data-ttu-id="b6645-313">发布连接后，需要自定义搜索结果页面。</span><span class="sxs-lookup"><span data-stu-id="b6645-313">After publishing the connection, you need to customize the search results page.</span></span> <span data-ttu-id="b6645-314">若要了解如何自定义搜索结果，请参阅自定义 [搜索结果页面](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)。</span><span class="sxs-lookup"><span data-stu-id="b6645-314">To learn about customizing search results, see [Customize the search results page](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).</span></span>

## <a name="limitations"></a><span data-ttu-id="b6645-315">限制</span><span class="sxs-lookup"><span data-stu-id="b6645-315">Limitations</span></span>
<span data-ttu-id="b6645-316">ServiceNow Graph连接器在其最新版本中具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="b6645-316">ServiceNow Graph connector has the following limitations in its latest release:</span></span>
- <span data-ttu-id="b6645-317">对组织中每个人都可用的知识库文章编制索引是一项普遍可用的功能。</span><span class="sxs-lookup"><span data-stu-id="b6645-317">Indexing knowledge articles available to everyone in an organization is a generally available feature.</span></span>
- <span data-ttu-id="b6645-318">*只有具有"管理* 搜索权限"步骤下此数据源功能的访问权限的用户才位于目标发布频道中，并且仅处理 [用户条件](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) 权限。</span><span class="sxs-lookup"><span data-stu-id="b6645-318">*Only people with access to this data source* feature under Manage Search permissions step is in targeted release channel and processes only [user criteria](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) permissions.</span></span> <span data-ttu-id="b6645-319">任何任何类型的访问权限将不会在搜索结果中应用。</span><span class="sxs-lookup"><span data-stu-id="b6645-319">Any other type of access permissions will not be applied in the search results.</span></span>
- <span data-ttu-id="b6645-320">当前版本不支持具有高级脚本的用户条件。</span><span class="sxs-lookup"><span data-stu-id="b6645-320">User criteria with advanced scripts are not supported in the current version.</span></span> <span data-ttu-id="b6645-321">任何具有此类访问限制的知识文章都会编制索引，拒绝所有人访问，即，在我们支持它们之前，这些文章不会显示在任何用户的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="b6645-321">Any knowledge articles with such an access restriction will be indexed with deny everyone access i.e. they will not appear in search results to any user until we support them.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b6645-322">疑难解答</span><span class="sxs-lookup"><span data-stu-id="b6645-322">Troubleshooting</span></span>
<span data-ttu-id="b6645-323">发布连接后，自定义结果页后，可以在管理中心的"数据源 **"选项卡下** 查看 [状态](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b6645-323">After publishing your connection, customizing the results page, you can review the status under the **Data Sources** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="b6645-324">若要了解如何进行更新和删除，请参阅 [管理连接器](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="b6645-324">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>
<span data-ttu-id="b6645-325">在下面可以找到常见问题的疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="b6645-325">You can find troubleshooting steps for commonly seen issues below.</span></span>
### <a name="1-unable-to-login-due-to-single-sign-on-enabled-servicenow-instance"></a><span data-ttu-id="b6645-326">1. 无法登录，因为启用了单Sign-On ServiceNow 实例</span><span class="sxs-lookup"><span data-stu-id="b6645-326">1. Unable to login due to Single Sign-On enabled ServiceNow instance</span></span>

<span data-ttu-id="b6645-327">如果组织已启用单一Sign-On (SSO) ServiceNow，则使用服务帐户登录时可能遇到问题。</span><span class="sxs-lookup"><span data-stu-id="b6645-327">If your organization has enabled Single Sign-On (SSO) to ServiceNow, you may have trouble logging in with the service account.</span></span> <span data-ttu-id="b6645-328">可以通过添加到 ServiceNow 实例 URL<em> `login.do` </em>来显示基于用户名和密码的登录名。</span><span class="sxs-lookup"><span data-stu-id="b6645-328">You can bring up username and password based login by adding <em> `login.do`</em> to the ServiceNow instance URL.</span></span> <span data-ttu-id="b6645-329">示例。</span><span class="sxs-lookup"><span data-stu-id="b6645-329">Example.</span></span> `https://<your-organization-domain>.service-now.com./login.do` 

### <a name="2-unauthorized-or-forbidden-response-to-api-request"></a><span data-ttu-id="b6645-330">2. 未经授权或禁止响应 API 请求</span><span class="sxs-lookup"><span data-stu-id="b6645-330">2. Unauthorized or forbidden response to API request</span></span>

#### <a name="21-check-table-access-permissions"></a><span data-ttu-id="b6645-331">2.1.</span><span class="sxs-lookup"><span data-stu-id="b6645-331">2.1.</span></span> <span data-ttu-id="b6645-332">检查表访问权限</span><span class="sxs-lookup"><span data-stu-id="b6645-332">Check table access permissions</span></span>
<span data-ttu-id="b6645-333">如果在连接状态中看到禁止响应或未授权响应，请检查服务帐户是否具有对步骤 [3：](#step-3-connection-settings)连接设置 中提到的表所需的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b6645-333">If you see forbidden or unauthorized response in connection status, check if the service account has required access to the tables mentioned in [step 3: connection settings](#step-3-connection-settings).</span></span> <span data-ttu-id="b6645-334">请检查表中的所有列是否具有读取权限。</span><span class="sxs-lookup"><span data-stu-id="b6645-334">Please check whether all the columns in the tables have read access.</span></span>

#### <a name="22-check-if-servicenow-instance-behind-firewall"></a><span data-ttu-id="b6645-335">2.2.</span><span class="sxs-lookup"><span data-stu-id="b6645-335">2.2.</span></span> <span data-ttu-id="b6645-336">检查防火墙后的 ServiceNow 实例</span><span class="sxs-lookup"><span data-stu-id="b6645-336">Check if ServiceNow instance behind firewall</span></span>
<span data-ttu-id="b6645-337">Graph如果连接器位于网络防火墙后面，则可能无法访问 ServiceNow 实例。</span><span class="sxs-lookup"><span data-stu-id="b6645-337">Graph Connector may not be able to reach your ServiceNow instance if it is behind a network firewall.</span></span> <span data-ttu-id="b6645-338">您需要明确允许访问 Graph 连接器服务。</span><span class="sxs-lookup"><span data-stu-id="b6645-338">You will need explicitly allow access to Graph Connector service.</span></span> <span data-ttu-id="b6645-339">您可以在下表中查找 Graph 连接器服务的公用 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="b6645-339">You can find public IP address range of Graph Connector Service in the table below.</span></span> <span data-ttu-id="b6645-340">根据你的租户区域，将其添加到你的 ServiceNow 实例网络白名单。</span><span class="sxs-lookup"><span data-stu-id="b6645-340">Based on your tenant region, add it to your ServiceNow instance network whitelist.</span></span>

<span data-ttu-id="b6645-341">**环境**</span><span class="sxs-lookup"><span data-stu-id="b6645-341">**Environment**</span></span> | <span data-ttu-id="b6645-342">**Region**</span><span class="sxs-lookup"><span data-stu-id="b6645-342">**Region**</span></span> | <span data-ttu-id="b6645-343">**区域**</span><span class="sxs-lookup"><span data-stu-id="b6645-343">**Range**</span></span>
--- | --- | ---
<span data-ttu-id="b6645-344">PROD</span><span class="sxs-lookup"><span data-stu-id="b6645-344">PROD</span></span> | <span data-ttu-id="b6645-345">北美</span><span class="sxs-lookup"><span data-stu-id="b6645-345">North America</span></span> | <span data-ttu-id="b6645-346">52.250.92.252/30, 52.224.250.216/30</span><span class="sxs-lookup"><span data-stu-id="b6645-346">52.250.92.252/30, 52.224.250.216/30</span></span>
<span data-ttu-id="b6645-347">PROD</span><span class="sxs-lookup"><span data-stu-id="b6645-347">PROD</span></span> | <span data-ttu-id="b6645-348">欧洲</span><span class="sxs-lookup"><span data-stu-id="b6645-348">Europe</span></span> | <span data-ttu-id="b6645-349">20.54.41.208/30, 51.105.159.88/30</span><span class="sxs-lookup"><span data-stu-id="b6645-349">20.54.41.208/30, 51.105.159.88/30</span></span> 
<span data-ttu-id="b6645-350">PROD</span><span class="sxs-lookup"><span data-stu-id="b6645-350">PROD</span></span> | <span data-ttu-id="b6645-351">亚太地区</span><span class="sxs-lookup"><span data-stu-id="b6645-351">Asia Pacific</span></span> | <span data-ttu-id="b6645-352">52.139.188.212/30, 20.43.146.44/30</span><span class="sxs-lookup"><span data-stu-id="b6645-352">52.139.188.212/30, 20.43.146.44/30</span></span> 


<span data-ttu-id="b6645-353">如果你有任何其他问题或想要提供反馈，请告诉我们 aka.ms/TalkToGraphConnectors [](https://aka.ms/TalkToGraphConnectors)</span><span class="sxs-lookup"><span data-stu-id="b6645-353">If you have any other issues or want to provide feedback, write to us [aka.ms/TalkToGraphConnectors](https://aka.ms/TalkToGraphConnectors)</span></span>
