---
title: 管理 Microsoft 搜索的 Microsoft Graph 连接器
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
description: 管理 Microsoft 搜索的 Microsoft Graph 连接器。
ms.openlocfilehash: aa2e3db8c8dc9155c06f81fc0169dd4bda8f8343
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508829"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="a4a6e-103">监视连接</span><span class="sxs-lookup"><span data-stu-id="a4a6e-103">Monitor your connections</span></span>

<span data-ttu-id="a4a6e-104">若要访问和管理连接器，必须指定为租户的搜索管理员。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="a4a6e-105">请与租户管理员联系，以预配搜索管理员角色。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="a4a6e-106">连接操作</span><span class="sxs-lookup"><span data-stu-id="a4a6e-106">Connection Operations</span></span>

<span data-ttu-id="a4a6e-107">导航到[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)[Microsoft 365 管理中心中的"连接器"选项卡](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="a4a6e-108">对于每个连接器类型 [，Microsoft 365 管理](https://admin.microsoft.com) 中心支持下表中显示的操作：</span><span class="sxs-lookup"><span data-stu-id="a4a6e-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="a4a6e-109">Operation</span><span class="sxs-lookup"><span data-stu-id="a4a6e-109">Operation</span></span> | <span data-ttu-id="a4a6e-110">Microsoft 的图表连接器</span><span class="sxs-lookup"><span data-stu-id="a4a6e-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="a4a6e-111">合作伙伴或 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="a4a6e-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="a4a6e-112">添加连接</span><span class="sxs-lookup"><span data-stu-id="a4a6e-112">Add a connection</span></span> | <span data-ttu-id="a4a6e-113">：heavy_check_mark： ([安装程序概述) ](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="a4a6e-113">:heavy_check_mark: (See [Setup overview](configure-connector.md))</span></span> | <span data-ttu-id="a4a6e-114">：x： (参考合作伙伴或自定义生成连接器管理员 UX) </span><span class="sxs-lookup"><span data-stu-id="a4a6e-114">:x: (Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="a4a6e-115">删除连接</span><span class="sxs-lookup"><span data-stu-id="a4a6e-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="a4a6e-118">编辑已发布的连接</span><span class="sxs-lookup"><span data-stu-id="a4a6e-118">Edit a published connection</span></span> | <span data-ttu-id="a4a6e-119">：heavy_check_mark：名称和说明</span><span class="sxs-lookup"><span data-stu-id="a4a6e-119">:heavy_check_mark: Name and Description</span></span><br></br> <span data-ttu-id="a4a6e-120">：heavy_check_mark：连接设置</span><span class="sxs-lookup"><span data-stu-id="a4a6e-120">:heavy_check_mark: Connection settings</span></span><br></br> <span data-ttu-id="a4a6e-121">：heavy_check_mark：属性标签</span><span class="sxs-lookup"><span data-stu-id="a4a6e-121">:heavy_check_mark: Property labels</span></span><br></br> <span data-ttu-id="a4a6e-122">：heavy_check_mark：架构</span><span class="sxs-lookup"><span data-stu-id="a4a6e-122">:heavy_check_mark: Schema</span></span><br></br> <span data-ttu-id="a4a6e-123">：heavy_check_mark：刷新计划</span><span class="sxs-lookup"><span data-stu-id="a4a6e-123">:heavy_check_mark: Refresh schedule</span></span><br></br> | <span data-ttu-id="a4a6e-124">：heavy_check_mark： Name</span><span class="sxs-lookup"><span data-stu-id="a4a6e-124">:heavy_check_mark: Name</span></span><br></br> <span data-ttu-id="a4a6e-125">：heavy_check_mark：说明</span><span class="sxs-lookup"><span data-stu-id="a4a6e-125">:heavy_check_mark: Description</span></span>
<span data-ttu-id="a4a6e-126">编辑草稿连接</span><span class="sxs-lookup"><span data-stu-id="a4a6e-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a><span data-ttu-id="a4a6e-129">监视连接状态</span><span class="sxs-lookup"><span data-stu-id="a4a6e-129">Monitor your connection status</span></span>

<span data-ttu-id="a4a6e-130">创建连接后，已处理项目的数量会显示在 **"Microsoft** 搜索"页上的"连接器"选项卡上。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="a4a6e-131">初始完全爬网成功完成后，将显示定期增量爬网的进度。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="a4a6e-132">此页面提供有关连接器日常操作的信息以及日志和错误历史记录的概述。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="a4a6e-133">每个连接的"状态 **"列中显示** 四种状态：</span><span class="sxs-lookup"><span data-stu-id="a4a6e-133">Four states show up in the **Status** column against each connection:</span></span>

* <span data-ttu-id="a4a6e-134">**正在同步**。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-134">**Syncing**.</span></span> <span data-ttu-id="a4a6e-135">连接器正在对源数据进行爬网，以对现有项目编制索引并进行更新。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="a4a6e-136">**已启用**：连接已启用，并且没有针对它运行的活动爬网。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-136">**Enabled**: The connection is enabled, and there's no active crawl running against it.</span></span> <span data-ttu-id="a4a6e-137">**上次同步** 时间指示上次成功爬网发生的时间。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="a4a6e-138">连接与上次同步时间一样新鲜。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="a4a6e-139">**已暂停**。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-139">**Paused**.</span></span> <span data-ttu-id="a4a6e-140">管理员通过暂停选项暂停爬网。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="a4a6e-141">下一次爬网仅在手动恢复时运行。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="a4a6e-142">但是，此连接的数据仍然可搜索。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="a4a6e-143">**失败**。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-143">**Failed**.</span></span> <span data-ttu-id="a4a6e-144">连接发生严重失败。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-144">The connection had a critical failure.</span></span> <span data-ttu-id="a4a6e-145">此错误需要手动干预。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-145">This error requires manual intervention.</span></span> <span data-ttu-id="a4a6e-146">管理员需要根据显示的错误消息采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="a4a6e-147">在发生错误之前已编制索引的数据是可搜索的。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="a4a6e-148">监视索引配额利用率</span><span class="sxs-lookup"><span data-stu-id="a4a6e-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="a4a6e-149">可用索引配额和消耗显示在连接器登录页上。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![索引配额使用率栏](media/quota_utilization.png)

>[!NOTE]
><span data-ttu-id="a4a6e-151">在预览期间，每个尝试使用 Graph 连接器的组织都获得免费固定配额，所有连接中最多包含 200 万个项目。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="a4a6e-152">在 Graph 连接器正式发布后，对于预览版中一直使用 Graph 连接器的组织，免费配额将于 2021 年 4 月 1 日到期。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-152">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="a4a6e-153">标记为"预览"的 Microsoft 构建[](connectors-preview.md)的 Graph 连接器不会包含在组织的已收费总索引配额中。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-153">Microsoft-built Graph connectors labeled as ["Preview"](connectors-preview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="a4a6e-154">但是，它算作可以为组织配置的最大 10 个连接数，以及组织跨连接可编制索引的最大项目数（700 万个）;每个连接限制为 700，000 个项目。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="a4a6e-155">配额使用率栏将基于组织配额的使用情况指示各种状态：</span><span class="sxs-lookup"><span data-stu-id="a4a6e-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="a4a6e-156">状态</span><span class="sxs-lookup"><span data-stu-id="a4a6e-156">State</span></span> | <span data-ttu-id="a4a6e-157">配额消耗</span><span class="sxs-lookup"><span data-stu-id="a4a6e-157">Quota consumption</span></span>
--- | ---
<span data-ttu-id="a4a6e-158">一般</span><span class="sxs-lookup"><span data-stu-id="a4a6e-158">Normal</span></span> | <span data-ttu-id="a4a6e-159">1-69%</span><span class="sxs-lookup"><span data-stu-id="a4a6e-159">1-69%</span></span>
<span data-ttu-id="a4a6e-160">高</span><span class="sxs-lookup"><span data-stu-id="a4a6e-160">High</span></span> | <span data-ttu-id="a4a6e-161">70-89%</span><span class="sxs-lookup"><span data-stu-id="a4a6e-161">70-89%</span></span>
<span data-ttu-id="a4a6e-162">关键</span><span class="sxs-lookup"><span data-stu-id="a4a6e-162">Critical</span></span> | <span data-ttu-id="a4a6e-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="a4a6e-163">90%-99%</span></span>
<span data-ttu-id="a4a6e-164">完整</span><span class="sxs-lookup"><span data-stu-id="a4a6e-164">Full</span></span> | <span data-ttu-id="a4a6e-165">100%</span><span class="sxs-lookup"><span data-stu-id="a4a6e-165">100%</span></span>

<span data-ttu-id="a4a6e-166">索引的项目数也会随每个连接一起显示。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="a4a6e-167">每个连接索引的项目数将影响组织可用的总配额。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="a4a6e-168">当超出组织的索引配额时，所有活动连接都将受到影响，并且这些连接将超出 **限制** 。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="a4a6e-169">在此状态中，你的活动连接</span><span class="sxs-lookup"><span data-stu-id="a4a6e-169">In this state, your active connections</span></span>  

* <span data-ttu-id="a4a6e-170">将无法添加新项。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="a4a6e-171">将能够更新或删除现有项目。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="a4a6e-172">若要解决此问题，可以执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="a4a6e-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="a4a6e-173">了解如何根据许可要求和定价为组织 [购买索引配额](licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="a4a6e-174">确定要包含太多内容的连接，并更新这些连接以索引更少的项目，以为配额提供空间。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="a4a6e-175">若要更新连接，必须删除并创建具有新引入筛选器的新连接，该筛选器将引入较少的项目。</span><span class="sxs-lookup"><span data-stu-id="a4a6e-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="a4a6e-176">永久删除一个或多个连接</span><span class="sxs-lookup"><span data-stu-id="a4a6e-176">Permanently delete one or more connections</span></span>
