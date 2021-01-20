---
title: 管理 Microsoft 搜索的 Microsoft Graph 连接器
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 管理 Microsoft 搜索的 Microsoft Graph 连接器。
ms.openlocfilehash: 5258f26a5c97be4ee9f90c7a8b2b9bb8fec447bc
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905927"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="c0de6-103">监视连接</span><span class="sxs-lookup"><span data-stu-id="c0de6-103">Monitor your connections</span></span>

<span data-ttu-id="c0de6-104">若要访问和管理连接器，必须指定为租户的搜索管理员。</span><span class="sxs-lookup"><span data-stu-id="c0de6-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="c0de6-105">请与租户管理员联系，预配搜索管理员角色。</span><span class="sxs-lookup"><span data-stu-id="c0de6-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="c0de6-106">连接操作</span><span class="sxs-lookup"><span data-stu-id="c0de6-106">Connection Operations</span></span>

<span data-ttu-id="c0de6-107">导航 [到](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) Microsoft 365 管理中心中的 ["连接器"选项卡](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c0de6-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="c0de6-108">对于每种连接器类型 [，Microsoft 365 管理](https://admin.microsoft.com) 中心支持下表中所示的操作：</span><span class="sxs-lookup"><span data-stu-id="c0de6-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="c0de6-109">Operation</span><span class="sxs-lookup"><span data-stu-id="c0de6-109">Operation</span></span> | <span data-ttu-id="c0de6-110">Microsoft 构建的连接器</span><span class="sxs-lookup"><span data-stu-id="c0de6-110">Microsoft-built connector</span></span> | <span data-ttu-id="c0de6-111">合作伙伴或自定义生成连接器</span><span class="sxs-lookup"><span data-stu-id="c0de6-111">Partner or custom-built connector</span></span>
--- | --- | ---
<span data-ttu-id="c0de6-112">添加连接</span><span class="sxs-lookup"><span data-stu-id="c0de6-112">Add a connection</span></span> | <span data-ttu-id="c0de6-113">：heavy_check_mark： (请参阅[配置 Microsoft 构建的连接器) ](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="c0de6-113">:heavy_check_mark: (See [Configure your Microsoft-built connector](configure-connector.md))</span></span> | <span data-ttu-id="c0de6-114">：x： (参考合作伙伴或自定义生成连接器管理员 UX) </span><span class="sxs-lookup"><span data-stu-id="c0de6-114">:x: (Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="c0de6-115">删除连接</span><span class="sxs-lookup"><span data-stu-id="c0de6-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="c0de6-118">编辑已发布的连接</span><span class="sxs-lookup"><span data-stu-id="c0de6-118">Edit a published connection</span></span> | <span data-ttu-id="c0de6-119">：heavy_check_mark： Name</span><span class="sxs-lookup"><span data-stu-id="c0de6-119">:heavy_check_mark: Name</span></span><br></br> <span data-ttu-id="c0de6-120">：heavy_check_mark：说明</span><span class="sxs-lookup"><span data-stu-id="c0de6-120">:heavy_check_mark: Description</span></span><br></br> <span data-ttu-id="c0de6-121">：heavy_check_mark：外部数据源的身份验证凭据</span><span class="sxs-lookup"><span data-stu-id="c0de6-121">:heavy_check_mark: Authentication credentials for your external data source</span></span><br></br> <span data-ttu-id="c0de6-122">：heavy_check_mark：本地数据源的网关凭据</span><span class="sxs-lookup"><span data-stu-id="c0de6-122">:heavy_check_mark: Gateway credentials for your on-premises data source</span></span><br></br> <span data-ttu-id="c0de6-123">：heavy_check_mark：刷新计划</span><span class="sxs-lookup"><span data-stu-id="c0de6-123">:heavy_check_mark: Refresh schedule</span></span><br></br> | <span data-ttu-id="c0de6-124">：heavy_check_mark： Name</span><span class="sxs-lookup"><span data-stu-id="c0de6-124">:heavy_check_mark: Name</span></span><br></br> <span data-ttu-id="c0de6-125">：heavy_check_mark：说明</span><span class="sxs-lookup"><span data-stu-id="c0de6-125">:heavy_check_mark: Description</span></span>
<span data-ttu-id="c0de6-126">编辑草稿连接</span><span class="sxs-lookup"><span data-stu-id="c0de6-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a><span data-ttu-id="c0de6-129">监视连接状态</span><span class="sxs-lookup"><span data-stu-id="c0de6-129">Monitor your connection status</span></span>

<span data-ttu-id="c0de6-130">创建连接后，已处理项目的数量会显示在 Microsoft 搜索页上的"连接器"**选项卡** 上。</span><span class="sxs-lookup"><span data-stu-id="c0de6-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="c0de6-131">初始完全爬网成功完成后，将显示定期增量爬网的进度。</span><span class="sxs-lookup"><span data-stu-id="c0de6-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="c0de6-132">此页面提供有关连接器日常操作的信息以及日志和错误历史记录的概述。</span><span class="sxs-lookup"><span data-stu-id="c0de6-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="c0de6-133">"状态"列中针对每个 **连接显示** 四种状态：</span><span class="sxs-lookup"><span data-stu-id="c0de6-133">Four states show up in the **Status** column against each connection:</span></span>

* <span data-ttu-id="c0de6-134">**正在同步**。</span><span class="sxs-lookup"><span data-stu-id="c0de6-134">**Syncing**.</span></span> <span data-ttu-id="c0de6-135">连接器正在对源数据进行爬网，以对现有项目编制索引并进行更新。</span><span class="sxs-lookup"><span data-stu-id="c0de6-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="c0de6-136">**已启用**：连接已启用，并且没有针对它运行的活动爬网。</span><span class="sxs-lookup"><span data-stu-id="c0de6-136">**Enabled**: The connection is enabled, and there's no active crawl running against it.</span></span> <span data-ttu-id="c0de6-137">**上次同步** 时间指示上次成功爬网的时间。</span><span class="sxs-lookup"><span data-stu-id="c0de6-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="c0de6-138">连接与上次同步时间一样新鲜。</span><span class="sxs-lookup"><span data-stu-id="c0de6-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="c0de6-139">**已暂停**。</span><span class="sxs-lookup"><span data-stu-id="c0de6-139">**Paused**.</span></span> <span data-ttu-id="c0de6-140">管理员通过暂停选项暂停爬网。</span><span class="sxs-lookup"><span data-stu-id="c0de6-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="c0de6-141">下一次爬网仅在手动恢复时运行。</span><span class="sxs-lookup"><span data-stu-id="c0de6-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="c0de6-142">但是，此连接的数据仍然可搜索。</span><span class="sxs-lookup"><span data-stu-id="c0de6-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="c0de6-143">**失败**。</span><span class="sxs-lookup"><span data-stu-id="c0de6-143">**Failed**.</span></span> <span data-ttu-id="c0de6-144">连接出现严重故障。</span><span class="sxs-lookup"><span data-stu-id="c0de6-144">The connection had a critical failure.</span></span> <span data-ttu-id="c0de6-145">此错误需要手动干预。</span><span class="sxs-lookup"><span data-stu-id="c0de6-145">This error requires manual intervention.</span></span> <span data-ttu-id="c0de6-146">管理员需要根据显示的错误消息采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="c0de6-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="c0de6-147">在发生错误之前已编制索引的数据是可搜索的。</span><span class="sxs-lookup"><span data-stu-id="c0de6-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="c0de6-148">监视索引配额使用率</span><span class="sxs-lookup"><span data-stu-id="c0de6-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="c0de6-149">可用的索引配额和消耗显示在连接器登录页上。</span><span class="sxs-lookup"><span data-stu-id="c0de6-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![索引配额使用率栏](media/quota_utilization.png)

>[!NOTE]
><span data-ttu-id="c0de6-151">在预览期间，每个尝试使用 Graph 连接器的组织都获得一个免费的固定配额，在所有连接中最多包含 200 万个项目。</span><span class="sxs-lookup"><span data-stu-id="c0de6-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="c0de6-152">随着 Graph 连接器的发布，对于一直预览版使用 Graph 连接器的组织，免费配额将于 2021 年 2 月 1 日到期。</span><span class="sxs-lookup"><span data-stu-id="c0de6-152">With Graph connectors being generally available, the free quota will expire on Feb 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="c0de6-153">标记为"预览"的 Microsoft 构建[](connectors-preview.md)的 Graph 连接器不会包含在组织的总收费索引配额中。</span><span class="sxs-lookup"><span data-stu-id="c0de6-153">Microsoft-built Graph connectors labeled as ["Preview"](connectors-preview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="c0de6-154">但是，它算作可以为组织配置的最大 10 个连接数，以及组织可以跨连接编制索引的最大 700 万个项目数;每个连接限制为 700，000 个项目。</span><span class="sxs-lookup"><span data-stu-id="c0de6-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="c0de6-155">配额利用率栏将基于组织配额的使用情况指示各种状态：</span><span class="sxs-lookup"><span data-stu-id="c0de6-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="c0de6-156">状态</span><span class="sxs-lookup"><span data-stu-id="c0de6-156">State</span></span> | <span data-ttu-id="c0de6-157">配额消耗</span><span class="sxs-lookup"><span data-stu-id="c0de6-157">Quota consumption</span></span>
--- | ---
<span data-ttu-id="c0de6-158">一般</span><span class="sxs-lookup"><span data-stu-id="c0de6-158">Normal</span></span> | <span data-ttu-id="c0de6-159">1-69%</span><span class="sxs-lookup"><span data-stu-id="c0de6-159">1-69%</span></span>
<span data-ttu-id="c0de6-160">高</span><span class="sxs-lookup"><span data-stu-id="c0de6-160">High</span></span> | <span data-ttu-id="c0de6-161">70-89%</span><span class="sxs-lookup"><span data-stu-id="c0de6-161">70-89%</span></span>
<span data-ttu-id="c0de6-162">关键</span><span class="sxs-lookup"><span data-stu-id="c0de6-162">Critical</span></span> | <span data-ttu-id="c0de6-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="c0de6-163">90%-99%</span></span>
<span data-ttu-id="c0de6-164">完整</span><span class="sxs-lookup"><span data-stu-id="c0de6-164">Full</span></span> | <span data-ttu-id="c0de6-165">100%</span><span class="sxs-lookup"><span data-stu-id="c0de6-165">100%</span></span>

<span data-ttu-id="c0de6-166">索引的项目数也会随每个连接一起显示。</span><span class="sxs-lookup"><span data-stu-id="c0de6-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="c0de6-167">每个连接编制索引的项目数将影响可供组织使用的总配额。</span><span class="sxs-lookup"><span data-stu-id="c0de6-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="c0de6-168">当超出组织的索引配额时，所有活动连接都将受到影响，并且这些连接将超出 **限制状态** 。</span><span class="sxs-lookup"><span data-stu-id="c0de6-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="c0de6-169">在此状态中，活动连接</span><span class="sxs-lookup"><span data-stu-id="c0de6-169">In this state, your active connections</span></span>  

* <span data-ttu-id="c0de6-170">将无法添加新项。</span><span class="sxs-lookup"><span data-stu-id="c0de6-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="c0de6-171">将能够更新或删除现有项目。</span><span class="sxs-lookup"><span data-stu-id="c0de6-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="c0de6-172">若要解决此问题，可以执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="c0de6-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="c0de6-173">了解如何根据许可要求和定价为组织 [购买索引配额](licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="c0de6-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="c0de6-174">确定要包含过多内容的连接，并更新这些连接以索引较少的项目，以为配额提供空间。</span><span class="sxs-lookup"><span data-stu-id="c0de6-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="c0de6-175">若要更新连接，必须使用引入筛选器删除并创建一个新连接，该筛选器将引入较少的项目。</span><span class="sxs-lookup"><span data-stu-id="c0de6-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="c0de6-176">永久删除一个或多个连接</span><span class="sxs-lookup"><span data-stu-id="c0de6-176">Permanently delete one or more connections</span></span>