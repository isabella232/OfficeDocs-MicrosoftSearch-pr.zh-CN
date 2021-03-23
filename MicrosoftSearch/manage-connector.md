---
title: 管理 Microsoft Graph 连接器以用于 Microsoft 搜索
ms.author: monaray
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 管理 Microsoft Graph 连接器以用于 Microsoft 搜索。
ms.openlocfilehash: cba50d8eb558b4d74ed46554dc155d4f275b1332
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031716"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="38f05-103">监视连接</span><span class="sxs-lookup"><span data-stu-id="38f05-103">Monitor your connections</span></span>

<span data-ttu-id="38f05-104">若要访问和管理连接器，必须指定为租户的搜索管理员。</span><span class="sxs-lookup"><span data-stu-id="38f05-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="38f05-105">请与租户管理员联系，以预配搜索管理员角色。</span><span class="sxs-lookup"><span data-stu-id="38f05-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="38f05-106">连接操作</span><span class="sxs-lookup"><span data-stu-id="38f05-106">Connection Operations</span></span>

<span data-ttu-id="38f05-107">导航到[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)[Microsoft 365](https://admin.microsoft.com)管理中心中的"连接器"选项卡。</span><span class="sxs-lookup"><span data-stu-id="38f05-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="38f05-108">对于每种连接器类型 [，Microsoft 365](https://admin.microsoft.com) 管理中心支持下表中显示的操作：</span><span class="sxs-lookup"><span data-stu-id="38f05-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="38f05-109">Operation</span><span class="sxs-lookup"><span data-stu-id="38f05-109">Operation</span></span> | <span data-ttu-id="38f05-110">Microsoft 的图表连接器</span><span class="sxs-lookup"><span data-stu-id="38f05-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="38f05-111">合作伙伴或图形连接器</span><span class="sxs-lookup"><span data-stu-id="38f05-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="38f05-112">添加连接</span><span class="sxs-lookup"><span data-stu-id="38f05-112">Add a connection</span></span> | <span data-ttu-id="38f05-113">：heavy_check_mark： ([请参阅安装程序概述](configure-connector.md)) </span><span class="sxs-lookup"><span data-stu-id="38f05-113">:heavy_check_mark: (See [Setup overview](configure-connector.md))</span></span> | <span data-ttu-id="38f05-114">：x： (请参阅你的合作伙伴或自定义的连接器管理员 UX) </span><span class="sxs-lookup"><span data-stu-id="38f05-114">:x: (Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="38f05-115">删除连接</span><span class="sxs-lookup"><span data-stu-id="38f05-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="38f05-118">编辑已发布的连接</span><span class="sxs-lookup"><span data-stu-id="38f05-118">Edit a published connection</span></span> | <span data-ttu-id="38f05-119">：heavy_check_mark：名称和说明</span><span class="sxs-lookup"><span data-stu-id="38f05-119">:heavy_check_mark: Name and Description</span></span><br></br> <span data-ttu-id="38f05-120">：heavy_check_mark：连接设置</span><span class="sxs-lookup"><span data-stu-id="38f05-120">:heavy_check_mark: Connection settings</span></span><br></br> <span data-ttu-id="38f05-121">：heavy_check_mark：属性标签</span><span class="sxs-lookup"><span data-stu-id="38f05-121">:heavy_check_mark: Property labels</span></span><br></br> <span data-ttu-id="38f05-122">：heavy_check_mark： 架构</span><span class="sxs-lookup"><span data-stu-id="38f05-122">:heavy_check_mark: Schema</span></span><br></br> <span data-ttu-id="38f05-123">：heavy_check_mark：刷新计划</span><span class="sxs-lookup"><span data-stu-id="38f05-123">:heavy_check_mark: Refresh schedule</span></span><br></br> | <span data-ttu-id="38f05-124">：heavy_check_mark： Name</span><span class="sxs-lookup"><span data-stu-id="38f05-124">:heavy_check_mark: Name</span></span><br></br> <span data-ttu-id="38f05-125">：heavy_check_mark： 说明</span><span class="sxs-lookup"><span data-stu-id="38f05-125">:heavy_check_mark: Description</span></span>
<span data-ttu-id="38f05-126">编辑草稿连接</span><span class="sxs-lookup"><span data-stu-id="38f05-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a><span data-ttu-id="38f05-129">监视连接状态</span><span class="sxs-lookup"><span data-stu-id="38f05-129">Monitor your connection state</span></span>

<span data-ttu-id="38f05-130">创建连接后，已处理项目的数量会显示在 **"Microsoft** 搜索"页上的"连接器"选项卡上。</span><span class="sxs-lookup"><span data-stu-id="38f05-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="38f05-131">初始完全爬网成功完成后，将显示定期增量爬网的进度。</span><span class="sxs-lookup"><span data-stu-id="38f05-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="38f05-132">此页面提供有关连接器日常操作的信息以及日志和错误历史记录的概述。</span><span class="sxs-lookup"><span data-stu-id="38f05-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="38f05-133">状态列中针对 **每个连接显示** 四种状态：</span><span class="sxs-lookup"><span data-stu-id="38f05-133">Four states show up in the **State** column against each connection:</span></span>

* <span data-ttu-id="38f05-134">**正在同步**。</span><span class="sxs-lookup"><span data-stu-id="38f05-134">**Syncing**.</span></span> <span data-ttu-id="38f05-135">连接器正在对源数据进行爬网，以对现有项目编制索引并进行更新。</span><span class="sxs-lookup"><span data-stu-id="38f05-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="38f05-136">**就绪**：连接已准备就绪，并且没有针对它运行活动爬网。</span><span class="sxs-lookup"><span data-stu-id="38f05-136">**Ready**: The connection is ready, and there's no active crawl running against it.</span></span> <span data-ttu-id="38f05-137">**上次同步** 时间指示上次成功爬网的时间。</span><span class="sxs-lookup"><span data-stu-id="38f05-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="38f05-138">连接与上次同步时间一样新鲜。</span><span class="sxs-lookup"><span data-stu-id="38f05-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="38f05-139">**已暂停**。</span><span class="sxs-lookup"><span data-stu-id="38f05-139">**Paused**.</span></span> <span data-ttu-id="38f05-140">管理员通过暂停选项暂停爬网。</span><span class="sxs-lookup"><span data-stu-id="38f05-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="38f05-141">下一次爬网仅在手动恢复时运行。</span><span class="sxs-lookup"><span data-stu-id="38f05-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="38f05-142">但是，此连接的数据仍然可搜索。</span><span class="sxs-lookup"><span data-stu-id="38f05-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="38f05-143">**失败**。</span><span class="sxs-lookup"><span data-stu-id="38f05-143">**Failed**.</span></span> <span data-ttu-id="38f05-144">连接出现严重故障。</span><span class="sxs-lookup"><span data-stu-id="38f05-144">The connection had a critical failure.</span></span> <span data-ttu-id="38f05-145">此错误需要手动干预。</span><span class="sxs-lookup"><span data-stu-id="38f05-145">This error requires manual intervention.</span></span> <span data-ttu-id="38f05-146">管理员需要根据显示的错误消息采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="38f05-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="38f05-147">在发生错误之前已编制索引的数据是可搜索的。</span><span class="sxs-lookup"><span data-stu-id="38f05-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="38f05-148">监视索引配额利用率</span><span class="sxs-lookup"><span data-stu-id="38f05-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="38f05-149">可用的索引配额和消耗显示在连接器登录页面上。</span><span class="sxs-lookup"><span data-stu-id="38f05-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![索引配额使用率栏](media/quota_utilization.png)
 
>[!NOTE]
><span data-ttu-id="38f05-151">在预览期间，每个尝试 Graph 连接器的组织都获得一个免费的固定配额，在所有连接中最多包含 200 万个项目。</span><span class="sxs-lookup"><span data-stu-id="38f05-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="38f05-152">随着 Graph 连接器正式发布，对于预览版中一直使用 Graph 连接器的组织，免费配额将于 2021 年 4 月 1 日到期。</span><span class="sxs-lookup"><span data-stu-id="38f05-152">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="38f05-153">标记为"预览"的 Microsoft 构建[](./connectors-overview.md)的 Graph 连接器不会包含在组织的已收费总索引配额中。</span><span class="sxs-lookup"><span data-stu-id="38f05-153">Microsoft-built Graph connectors labeled as ["Preview"](./connectors-overview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="38f05-154">但是，它算作可以为组织配置的最多 10 个连接数，以及组织可以跨连接编制索引的最大 700 万个项目;每个连接限制为 700，000 个项目。</span><span class="sxs-lookup"><span data-stu-id="38f05-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="38f05-155">配额利用率栏将基于组织的配额消耗指示各种状态：</span><span class="sxs-lookup"><span data-stu-id="38f05-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="38f05-156">状态</span><span class="sxs-lookup"><span data-stu-id="38f05-156">State</span></span> | <span data-ttu-id="38f05-157">配额利用率级别</span><span class="sxs-lookup"><span data-stu-id="38f05-157">Quota utilization levels</span></span>
--- | --- 
<span data-ttu-id="38f05-158">一般</span><span class="sxs-lookup"><span data-stu-id="38f05-158">Normal</span></span> | <span data-ttu-id="38f05-159">0-79%</span><span class="sxs-lookup"><span data-stu-id="38f05-159">0-79%</span></span>
<span data-ttu-id="38f05-160">高</span><span class="sxs-lookup"><span data-stu-id="38f05-160">High</span></span> | <span data-ttu-id="38f05-161">80-89%</span><span class="sxs-lookup"><span data-stu-id="38f05-161">80-89%</span></span>
<span data-ttu-id="38f05-162">关键</span><span class="sxs-lookup"><span data-stu-id="38f05-162">Critical</span></span> | <span data-ttu-id="38f05-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="38f05-163">90%-99%</span></span>
<span data-ttu-id="38f05-164">完整</span><span class="sxs-lookup"><span data-stu-id="38f05-164">Full</span></span> | <span data-ttu-id="38f05-165">100%</span><span class="sxs-lookup"><span data-stu-id="38f05-165">100%</span></span>

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

<span data-ttu-id="38f05-166">还将随每个连接显示已编制索引的项目数。</span><span class="sxs-lookup"><span data-stu-id="38f05-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="38f05-167">每个连接编制索引的项目数将影响组织可用的总配额。</span><span class="sxs-lookup"><span data-stu-id="38f05-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="38f05-168">当超出组织的索引配额时，所有活动连接都将受到影响，并且这些连接将在 **超出限制时** 运行。</span><span class="sxs-lookup"><span data-stu-id="38f05-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="38f05-169">在此状态中，活动连接</span><span class="sxs-lookup"><span data-stu-id="38f05-169">In this state, your active connections</span></span>  

* <span data-ttu-id="38f05-170">无法添加新项。</span><span class="sxs-lookup"><span data-stu-id="38f05-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="38f05-171">将能够更新或删除现有项目。</span><span class="sxs-lookup"><span data-stu-id="38f05-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="38f05-172">若要解决此问题，可以执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="38f05-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="38f05-173">了解如何在许可要求和定价中为 [组织购买索引配额](licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="38f05-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="38f05-174">确定要包含过多内容的连接，并更新这些连接以对较少的项目编制索引以为配额提供空间。</span><span class="sxs-lookup"><span data-stu-id="38f05-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="38f05-175">若要更新连接，必须删除新引入筛选器并创建一个新连接，该筛选器可引入较少的项目。</span><span class="sxs-lookup"><span data-stu-id="38f05-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="38f05-176">永久删除一个或多个连接</span><span class="sxs-lookup"><span data-stu-id="38f05-176">Permanently delete one or more connections</span></span>