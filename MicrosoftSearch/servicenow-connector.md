---
title: 用于 Microsoft 搜索的 ServiceNow 连接器
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.date: 10/08/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置用于 Microsoft 搜索的 ServiceNow 连接器
ms.openlocfilehash: b83bf04dc06ffab26a0067d15b36a99496c199a8
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949650"
---
# <a name="servicenow-connector"></a><span data-ttu-id="9b2d4-103">ServiceNow 连接器</span><span class="sxs-lookup"><span data-stu-id="9b2d4-103">ServiceNow connector</span></span>

<span data-ttu-id="9b2d4-104">使用 ServiceNow 连接器，组织可以对组织中的所有用户可见的知识库文章编制索引。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-104">With the ServiceNow connector, your organization can index knowledge-base articles that are visible to all users within your organization.</span></span> <span data-ttu-id="9b2d4-105">在从 ServiceNow 配置连接器和索引内容之后，最终用户可以从任何 Microsoft Search client 中搜索这些文章。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-105">After you configure the connector and index content from ServiceNow, end users can search for those articles from any Microsoft Search client.</span></span>  

<span data-ttu-id="9b2d4-106">本文适用于 Microsoft 365 管理员或任何配置、运行和监视 ServiceNow 连接器的人。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a ServiceNow connector.</span></span> <span data-ttu-id="9b2d4-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="9b2d4-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="9b2d4-108">Connect to a data source</span></span>
<span data-ttu-id="9b2d4-109">若要连接到你的 ServiceNow 数据，你需要组织的**servicenow 实例 URL**、此帐户的凭据以及用于 OAuth 身份验证的客户端 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-109">To connect to your ServiceNow data, you need your organization's **ServiceNow instance URL**, credentials for this account, and the Client ID and Client Secret for OAuth authentication.</span></span>  

<span data-ttu-id="9b2d4-110">您的组织的**ServiceNow 实例 URL**的外观通常如下所示**&lt;https://您的组织域> service-now.com**。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-110">Your organization’s **ServiceNow instance URL** typically looks like **https://&lt;your-organization-domain>.service-now.com**.</span></span> <span data-ttu-id="9b2d4-111">除了此 URL，您还需要一个帐户，用于设置与 ServiceNow 的连接，以及允许 Microsoft Search 根据刷新计划定期更新 ServiceNow 中的文章。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-111">Along with this URL, you will need an account for setting up the connection to ServiceNow as well as for allowing Microsoft Search to periodically update the articles from ServiceNow based on the refresh schedule.</span></span>

<span data-ttu-id="9b2d4-112">若要从 ServiceNow 对内容进行身份验证和同步，请选择以下两个受支持的方法之一：</span><span class="sxs-lookup"><span data-stu-id="9b2d4-112">To authenticate and sync content from ServiceNow, choose one of two supported methods:</span></span> 
1. <span data-ttu-id="9b2d4-113">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="9b2d4-113">Basic authentication</span></span> 
2. <span data-ttu-id="9b2d4-114">OAuth （推荐）</span><span class="sxs-lookup"><span data-stu-id="9b2d4-114">OAuth (recommended)</span></span>

> [!Note]
> <span data-ttu-id="9b2d4-115">若要使用 OAuth 进行身份验证，ServiceNow 管理员需要在你的 ServiceNow 实例中预配终结点，以便 Microsoft Search 应用可以访问该实例。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-115">To use OAuth for authentication, a ServiceNow admin needs to provision an endpoint in your ServiceNow instance, so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="9b2d4-116">若要了解详细信息，请参阅在 ServiceNow 文档中[创建客户端以访问实例的终结点](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html)。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-116">To learn more, see [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in the ServiceNow documentation.</span></span>

<span data-ttu-id="9b2d4-117">下表提供了有关如何填写终结点创建表单的指导：</span><span class="sxs-lookup"><span data-stu-id="9b2d4-117">The following table provides guidance on how to fill out the endpoint creation form:</span></span>

<span data-ttu-id="9b2d4-118">**Field**</span><span class="sxs-lookup"><span data-stu-id="9b2d4-118">**Field**</span></span> | <span data-ttu-id="9b2d4-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9b2d4-119">**Description**</span></span> | <span data-ttu-id="9b2d4-120">**推荐值**</span><span class="sxs-lookup"><span data-stu-id="9b2d4-120">**Recommended Value**</span></span>
--- | --- | ---
<span data-ttu-id="9b2d4-121">名称</span><span class="sxs-lookup"><span data-stu-id="9b2d4-121">Name</span></span> | <span data-ttu-id="9b2d4-122">此唯一值标识您需要 OAuth 访问的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-122">This unique value identifies the application that you require OAuth access for.</span></span> | <span data-ttu-id="9b2d4-123">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="9b2d4-123">Microsoft Search</span></span>
<span data-ttu-id="9b2d4-124">客户端 ID</span><span class="sxs-lookup"><span data-stu-id="9b2d4-124">Client ID</span></span> | <span data-ttu-id="9b2d4-125">应用程序的只读、自动生成的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-125">A read-only, auto-generated unique ID for the application.</span></span> <span data-ttu-id="9b2d4-126">实例在请求访问令牌时使用客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-126">The instance uses the client ID when it requests an access token.</span></span> | <span data-ttu-id="9b2d4-127">NA</span><span class="sxs-lookup"><span data-stu-id="9b2d4-127">NA</span></span>
<span data-ttu-id="9b2d4-128">客户端密码</span><span class="sxs-lookup"><span data-stu-id="9b2d4-128">Client secret</span></span> | <span data-ttu-id="9b2d4-129">使用此共享机密字符串，ServiceNow 实例和 Microsoft Search 授权相互之间的通信。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-129">With this shared secret string, the ServiceNow instance and Microsoft Search authorize communications with each another.</span></span> | <span data-ttu-id="9b2d4-130">将此视为密码，以遵循安全性最佳实践。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-130">Follow security best-practices by treating this as a password.</span></span>
<span data-ttu-id="9b2d4-131">重定向 URL</span><span class="sxs-lookup"><span data-stu-id="9b2d4-131">Redirect URL</span></span> | <span data-ttu-id="9b2d4-132">授权服务器重定向到的必需回调 URL。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-132">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="9b2d4-133">请参阅[OAuth 回调](https://gcs.office.com/v1.0/admin/oauth/callback)。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-133">See [OAuth callback](https://gcs.office.com/v1.0/admin/oauth/callback).</span></span>
<span data-ttu-id="9b2d4-134">徽标 URL</span><span class="sxs-lookup"><span data-stu-id="9b2d4-134">Logo URL</span></span> | <span data-ttu-id="9b2d4-135">包含应用程序徽标的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-135">A URL that contains the image for the application logo.</span></span> | <span data-ttu-id="9b2d4-136">NA</span><span class="sxs-lookup"><span data-stu-id="9b2d4-136">NA</span></span>
<span data-ttu-id="9b2d4-137">活动</span><span class="sxs-lookup"><span data-stu-id="9b2d4-137">Active</span></span> | <span data-ttu-id="9b2d4-138">选中此复选框可使应用程序注册表处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-138">Select the check box to make the application registry active.</span></span> | <span data-ttu-id="9b2d4-139">设置为活动</span><span class="sxs-lookup"><span data-stu-id="9b2d4-139">Set to active</span></span>
<span data-ttu-id="9b2d4-140">刷新令牌生命期</span><span class="sxs-lookup"><span data-stu-id="9b2d4-140">Refresh token lifespan</span></span> | <span data-ttu-id="9b2d4-141">刷新令牌有效的秒数。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-141">The number of seconds that a refresh token is valid.</span></span> <span data-ttu-id="9b2d4-142">默认情况下，刷新令牌在100天后过期（8640000秒）。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-142">By default, refresh tokens expire in 100 days (8640000 seconds).</span></span> | <span data-ttu-id="9b2d4-143">31536000（1年）</span><span class="sxs-lookup"><span data-stu-id="9b2d4-143">31,536,000 (1 year)</span></span>
<span data-ttu-id="9b2d4-144">访问令牌生命周期</span><span class="sxs-lookup"><span data-stu-id="9b2d4-144">Access token lifespan</span></span> | <span data-ttu-id="9b2d4-145">访问令牌有效的秒数。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-145">The number of seconds that an access token is valid.</span></span> | <span data-ttu-id="9b2d4-146">43200（12个小时）</span><span class="sxs-lookup"><span data-stu-id="9b2d4-146">43,200 (12 hours)</span></span>

## <a name="set-a-sync-filter"></a><span data-ttu-id="9b2d4-147">设置同步筛选器</span><span class="sxs-lookup"><span data-stu-id="9b2d4-147">Set a sync filter</span></span> 
<span data-ttu-id="9b2d4-148">使用同步筛选器，可以指定用于同步文章的条件。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-148">With a sync filter, you can specify conditions for syncing articles.</span></span> <span data-ttu-id="9b2d4-149">它类似于**SQL Select**语句中的**Where**子句。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-149">It's like a **Where** clause in a **SQL Select** statement.</span></span> <span data-ttu-id="9b2d4-150">例如，您可以选择仅对已发布和活动的文章编制索引。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-150">For example, you can choose to index only articles that are published and active.</span></span> <span data-ttu-id="9b2d4-151">SyncNow 配置页介绍如何捕获和设置同步筛选器。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-151">The SyncNow configuration page describes how to capture and set a sync filter.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="9b2d4-152">管理搜索架构</span><span class="sxs-lookup"><span data-stu-id="9b2d4-152">Manage the search schema</span></span>
<span data-ttu-id="9b2d4-153">成功连接后，配置搜索架构映射。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-153">After successful connection, configure the search schema mapping.</span></span> <span data-ttu-id="9b2d4-154">您可以选择哪些属性可供**查询**、**搜索**和**检索**。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-154">You can choose which properties to make **queryable**, **searchable**, and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="9b2d4-155">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="9b2d4-155">Manage search permissions</span></span>
<span data-ttu-id="9b2d4-156">ServiceNow 连接器仅支持**所有人都**能看到的搜索权限。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-156">The ServiceNow connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="9b2d4-157">索引数据显示在搜索结果中，并对组织中的所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-157">Indexed data appears in the search results and is visible to all users in the organization.</span></span>
 
## <a name="set-the-refresh-schedule"></a><span data-ttu-id="9b2d4-158">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="9b2d4-158">Set the refresh schedule</span></span> 
<span data-ttu-id="9b2d4-159">ServiceNow 连接器支持完全爬网和增量爬网的刷新计划。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-159">The ServiceNow connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="9b2d4-160">我们建议您同时设置这两个。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-160">We recommend that you set both.</span></span>

<span data-ttu-id="9b2d4-161">完全爬网计划可查找以前同步到 Microsoft 搜索索引的已删除文章以及从同步筛选器中移出的所有文章。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-161">A full crawl schedule finds deleted articles that were previously synced to the Microsoft Search index and any articles that moved out of the sync filter.</span></span> <span data-ttu-id="9b2d4-162">首次连接到 ServiceNow 时，将运行完全爬网以同步所有知识库文章。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-162">When you first connect to ServiceNow, a full crawl runs to sync all the knowledge-base articles.</span></span> <span data-ttu-id="9b2d4-163">若要同步新项目并进行更新，需要安排增量爬网。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-163">To sync new items and make updates, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="9b2d4-164">对于完全爬网，建议默认值为一天，对于增量爬网，建议默认值为4小时。</span><span class="sxs-lookup"><span data-stu-id="9b2d4-164">The recommended default is one day for a full crawl and four hours for an incremental crawl.</span></span>
