---
title: 搜索使用率报告
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.topic: article
ms.service: mssearch
audience: Admin
ms.audience: Admin
ms.date: 04/09/2021
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 查看 Microsoft 搜索使用率报告
ms.openlocfilehash: 17645d86e315538305a28bad51ea1a41dcc37dcb
ms.sourcegitcommit: d62849b00f2b65b493ab54be50c3e7c94430f057
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51754661"
---
# <a name="microsoft-search-usage-reports"></a><span data-ttu-id="23548-103">Microsoft 搜索使用率报告</span><span class="sxs-lookup"><span data-stu-id="23548-103">Microsoft Search Usage Reports</span></span>

<span data-ttu-id="23548-104">利用搜索使用率报告，您可以更好地了解搜索在组织中如何运行。</span><span class="sxs-lookup"><span data-stu-id="23548-104">Search usage reports enable you to gain more understanding of how search is functioning in your organization.</span></span> <span data-ttu-id="23548-105">从这些报告生成的见解将帮助您使内容易于查找，[](./make-content-easy-to-find.md)并采取措施，使搜索成为更有用且更令人愉悦的体验。</span><span class="sxs-lookup"><span data-stu-id="23548-105">The insights generated from these reports will help you [make content easy to find](./make-content-easy-to-find.md) and take actions that will make search a more useful and delightful experience for your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23548-106">Microsoft 搜索使用情况报告目前处于预览阶段</span><span class="sxs-lookup"><span data-stu-id="23548-106">Microsoft Search usage reports are currently in preview</span></span>

<span data-ttu-id="23548-107">[Microsoft 搜索使用情况报告](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights)包括从 SharePoint 主页和搜索框中执行的搜索 Office.com 表。</span><span class="sxs-lookup"><span data-stu-id="23548-107">The [Microsoft Search usage reports](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) include graphs and tables generated from searches that are executed from SharePoint Home and Office.com search boxes.</span></span> <span data-ttu-id="23548-108">你可以查看过去 31 天、每天或上一年每月的数据。</span><span class="sxs-lookup"><span data-stu-id="23548-108">You can see data from the past 31 days, per day, or monthly for the previous year.</span></span> <span data-ttu-id="23548-109">这些报告刚刚推出，因此需要一段时间来累算历史数据。</span><span class="sxs-lookup"><span data-stu-id="23548-109">These reports are just rolling out so it will take time to accrue the historical data.</span></span>

<span data-ttu-id="23548-110">此页面的以前版本包含针对必应必应中的 Microsoft 搜索执行的搜索 Bing.com。</span><span class="sxs-lookup"><span data-stu-id="23548-110">A previous version of this page included data from searches executed for Microsoft Search in Bing on Bing.com.</span></span> <span data-ttu-id="23548-111">这些数据将很快集成到这些报告中，但现在，你仍然可以通过单击页面底部的链接查看必应热门查询和印象分布来查看 **这些报告**。</span><span class="sxs-lookup"><span data-stu-id="23548-111">That data will be integrated into these reports soon, but for now, you can still see those reports by clicking the link at the bottom of the page to **View Bing's top queries and impression distribution**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23548-112">![搜索使用率报告仪表板](media/usage-reports/usage_reports_v2.png)</span><span class="sxs-lookup"><span data-stu-id="23548-112">![Search usage reports dashboard](media/usage-reports/usage_reports_v2.png)</span></span>

## <a name="overview-of-search-reports"></a><span data-ttu-id="23548-113">搜索报告概述</span><span class="sxs-lookup"><span data-stu-id="23548-113">Overview of search reports</span></span>

| <span data-ttu-id="23548-114">报告</span><span class="sxs-lookup"><span data-stu-id="23548-114">Report</span></span> | <span data-ttu-id="23548-115">说明</span><span class="sxs-lookup"><span data-stu-id="23548-115">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="23548-116">查询量</span><span class="sxs-lookup"><span data-stu-id="23548-116">Query Volume</span></span>|<span data-ttu-id="23548-117">此报告显示执行的搜索查询的数量。</span><span class="sxs-lookup"><span data-stu-id="23548-117">This report shows the number of search queries performed.</span></span> <span data-ttu-id="23548-118">使用此报告可确定搜索查询量趋势，并确定较高和较低搜索活动的时间段。</span><span class="sxs-lookup"><span data-stu-id="23548-118">Use this report to identify search query volume trends and to determine periods of high and low search activity.</span></span>|
|<span data-ttu-id="23548-119">热门查询</span><span class="sxs-lookup"><span data-stu-id="23548-119">Top Queries</span></span>|<span data-ttu-id="23548-120">此报告显示最热门的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="23548-120">This report shows the most popular search queries.</span></span> <span data-ttu-id="23548-121">当通过单击结果至少搜索此查询三次时，会向该报表添加查询。</span><span class="sxs-lookup"><span data-stu-id="23548-121">A query is added to this report when it is searched at least three times with a click on a result.</span></span> <span data-ttu-id="23548-122">使用此报告可了解用户要搜索的信息类型。</span><span class="sxs-lookup"><span data-stu-id="23548-122">Use this report to understand what types of information your users are searching for.</span></span>|
|<span data-ttu-id="23548-123">放弃的查询</span><span class="sxs-lookup"><span data-stu-id="23548-123">Abandoned Queries</span></span>|<span data-ttu-id="23548-124">此报告显示点击率较低的热门搜索查询。</span><span class="sxs-lookup"><span data-stu-id="23548-124">This report shows popular search queries that receive low click-through.</span></span> <span data-ttu-id="23548-125">使用此报告可确定可能导致用户不满意的搜索查询，并提高内容的可发现性。</span><span class="sxs-lookup"><span data-stu-id="23548-125">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="23548-126">然后，你可以确定创建答案（如书签）或通过 Graph 连接器插入新内容是否是正确的操作。</span><span class="sxs-lookup"><span data-stu-id="23548-126">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|
|<span data-ttu-id="23548-127">无结果查询</span><span class="sxs-lookup"><span data-stu-id="23548-127">No Results Queries</span></span>|<span data-ttu-id="23548-128">此报告显示未返回结果的热门搜索查询。</span><span class="sxs-lookup"><span data-stu-id="23548-128">This report shows popular search queries that returned no results.</span></span> <span data-ttu-id="23548-129">使用此报告可确定可能导致用户不满意的搜索查询，并提高内容的可发现性。</span><span class="sxs-lookup"><span data-stu-id="23548-129">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="23548-130">然后，你可以确定创建答案（如书签）或通过 Graph 连接器插入新内容是否是正确的操作。</span><span class="sxs-lookup"><span data-stu-id="23548-130">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|

>[!NOTE]
><span data-ttu-id="23548-131">目前存在一个已知问题，例如书签等答案所满足的查询被视为放弃的查询。</span><span class="sxs-lookup"><span data-stu-id="23548-131">There is currently a known issue where queries satisfied by an answer like a Bookmark are counted as an abandoned query.</span></span>

## <a name="viewing-reports"></a><span data-ttu-id="23548-132">查看报告</span><span class="sxs-lookup"><span data-stu-id="23548-132">Viewing reports</span></span>

<span data-ttu-id="23548-133">当您导航到使用率报告页面时，所有报告都可供查看。</span><span class="sxs-lookup"><span data-stu-id="23548-133">When you navigate to the usage reports page, all the reports are available to view.</span></span> <span data-ttu-id="23548-134">可以使用日期筛选器来选取要查看的特定日期或月份。</span><span class="sxs-lookup"><span data-stu-id="23548-134">You can use the date filter to pick a specific day or month to view.</span></span>

<span data-ttu-id="23548-135">下载报告将允许您从更广泛的时间范围查看报告。</span><span class="sxs-lookup"><span data-stu-id="23548-135">Downloading a report will allow you to see reports from a broader range of time.</span></span> <span data-ttu-id="23548-136">单击下载箭头并选择过去 **31 天** 或 **过去 12 个月**。</span><span class="sxs-lookup"><span data-stu-id="23548-136">Click on the download arrow and select **past 31 days** or **past 12 months**.</span></span> <span data-ttu-id="23548-137">报告下载为 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="23548-137">The report downloads as an Excel spreadsheet.</span></span> <span data-ttu-id="23548-138">如果选择了过去 31 天，电子表格将每天具有一个单独选项卡。</span><span class="sxs-lookup"><span data-stu-id="23548-138">If you selected past 31 days, the spreadsheet will have an individual tab for each day.</span></span> <span data-ttu-id="23548-139">过去 12 个月的下载每月都有一个选项卡。</span><span class="sxs-lookup"><span data-stu-id="23548-139">The past 12 months download will have a tab for each month.</span></span>

<span data-ttu-id="23548-140">若要查看必应热门查询和印象分布报告，请单击页面上的链接。</span><span class="sxs-lookup"><span data-stu-id="23548-140">To view Bing’s top queries and impression distribution reports click on the link on the page.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="23548-141">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="23548-141">Frequently asked questions</span></span>

<span data-ttu-id="23548-142">**当我选择过去 31 天或过去 12 个月时，为什么我随后必须选择特定日期或特定月份。**</span><span class="sxs-lookup"><span data-stu-id="23548-142">**When I select past 31 days or past 12 months, why do I then have to choose a specific day or specific month.**</span></span>

<span data-ttu-id="23548-143">目前，Microsoft 搜索使用情况报告中的日历视图是一个两步过程。</span><span class="sxs-lookup"><span data-stu-id="23548-143">The calendar view, today, in Microsoft search usage reports is a two-step process.</span></span> <span data-ttu-id="23548-144">首先从下拉列表中选择过去 31 天 (过去 12 个月的日期范围) 然后选择开始日期或月份。</span><span class="sxs-lookup"><span data-stu-id="23548-144">First select the date range from the dropdown (past 31 days or past 12 months) and then select the start day or month.</span></span>

<span data-ttu-id="23548-145">顶部、弃用和失败的查询表显示您选择的第一天或当月的结果。</span><span class="sxs-lookup"><span data-stu-id="23548-145">The top, abandoned, and failed query tables show results from either the day or the month you choose.</span></span>

<span data-ttu-id="23548-146">**我何时会看到过去 7 天、过去 30 天的聚合数据，等等...像必应热门查询报告一样？**</span><span class="sxs-lookup"><span data-stu-id="23548-146">**When will I see aggregate data for past 7 days, past 30 days, and so on...like Bing’s top queries reports?**</span></span>

<span data-ttu-id="23548-147">我们正在考虑这种类型的聚合，并针对这些报告的未来版本简化数据范围筛选。</span><span class="sxs-lookup"><span data-stu-id="23548-147">We are considering this type of aggregation and simplifying the data range filtering for future versions of these reports.</span></span>

<span data-ttu-id="23548-148">**为什么无法按不同应用和源 (使用情况) ？**</span><span class="sxs-lookup"><span data-stu-id="23548-148">**Why can’t I see a breakdown of usage reports by different apps (sources)?**</span></span>

<span data-ttu-id="23548-149">目前，无法按源进行筛选。</span><span class="sxs-lookup"><span data-stu-id="23548-149">Currently, filtering by source is not available.</span></span> <span data-ttu-id="23548-150">报告将 SharePoint 主页和 SharePoint Office.com。</span><span class="sxs-lookup"><span data-stu-id="23548-150">The reports combine searches from SharePoint Home and Office.com.</span></span> <span data-ttu-id="23548-151">我们的下一版本将包括源筛选，以便你可以查看特定于每个应用程序的指标。</span><span class="sxs-lookup"><span data-stu-id="23548-151">Our next release will include source filtering so you can see metrics specific to each application.</span></span>

<span data-ttu-id="23548-152">**即将对使用率报告进行哪些其他筛选？**</span><span class="sxs-lookup"><span data-stu-id="23548-152">**What other filtering for usage reports is coming?**</span></span>

<span data-ttu-id="23548-153">我们正在研究其他筛选器，这些筛选器有助于在更精细的组织级别了解搜索使用情况。</span><span class="sxs-lookup"><span data-stu-id="23548-153">We are working on additional filters that will help make sense of search usage at a more granular level of your organization.</span></span> <span data-ttu-id="23548-154">例如，您将能够查看特定地理位置或部门的查询量。</span><span class="sxs-lookup"><span data-stu-id="23548-154">For example, you will be able to see query volume for a specific geography or department.</span></span>

<span data-ttu-id="23548-155">**为什么必应中的 Microsoft 搜索报告位于单独的页面上？**</span><span class="sxs-lookup"><span data-stu-id="23548-155">**Why is the Microsoft Search in Bing reports on a separate page?**</span></span>

<span data-ttu-id="23548-156">将 Office 365 应用程序中的搜索功能现代化到 Microsoft 搜索需要我们加入以前不同的系统，包括报告生成。</span><span class="sxs-lookup"><span data-stu-id="23548-156">Modernizing search in Office 365 applications to Microsoft Search has required us to join previously disparate systems, including the reports generation.</span></span> <span data-ttu-id="23548-157">这需要花费一些时间，并且我们发现，现在让这些报告退出与等到我们可以完成 Bing 数据集成相比，这一点更加重要。</span><span class="sxs-lookup"><span data-stu-id="23548-157">This takes time and we felt it was more important to get these reports out now versus waiting until we could complete the integration of the Bing data.</span></span> <span data-ttu-id="23548-158">完成集成后，来自所有搜索终结点的数据将包含在同一个报告中。</span><span class="sxs-lookup"><span data-stu-id="23548-158">Once we complete the integration, the data from all search endpoints will be included in the same reports.</span></span>
