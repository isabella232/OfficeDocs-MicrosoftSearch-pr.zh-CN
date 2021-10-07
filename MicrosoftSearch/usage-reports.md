---
title: 搜索使用率报告
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.topic: article
ms.service: mssearch
audience: Admin
ms.audience: Admin
ms.date: 09/24/2021
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 查看Microsoft 搜索使用情况报告
ms.openlocfilehash: 1f2afa6e2c7691aa3284ae017913827761981529
ms.sourcegitcommit: ca6f0488b842e7fc0d98c7b84b2b8bc5817d3e7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2021
ms.locfileid: "60224864"
---
# <a name="microsoft-search-usage-reports"></a>Microsoft 搜索使用率报告

利用搜索使用率报告，您可以更好地了解搜索在组织中如何运行。 从这些报告生成的见解将有助于你采取一些操作，以便为用户提供更有用和令人愉悦的搜索体验。

> [!IMPORTANT]
> Microsoft 搜索使用情况报告当前处于预览阶段

Microsoft 搜索[使用情况](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights)报告包括从 SharePoint Home (网站执行的搜索生成的图形和表，URL 以 必应 搜索框中的 /SharePoint.aspx) 、Office.com 和 Microsoft 搜索 结尾。 你可以查看过去 31 天、每天或上一年每月的数据。 这些报告刚刚推出，因此需要一段时间来累算历史数据。

> [!div class="mx-imgBorder"]
> ![搜索使用率报告仪表板。](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>搜索报告概述

| 报告 | 说明 |
|:-----|:-----|
|查询量|此报告显示执行的搜索查询的数量。 使用此报告可确定搜索查询量趋势，并确定较高和较低搜索活动的时间段。|
|热门查询|此报告显示最热门的搜索查询。 当通过单击结果至少搜索此查询三次时，会向该报表添加查询。 使用此报告可了解用户要搜索的信息类型。|
|放弃的查询|此报告显示点击率较低的热门搜索查询。 使用此报告可确定可能导致用户不满意的搜索查询，并提高内容的可发现性。 然后，您可以确定创建答案（如书签）或通过 Graph 连接器来加入新内容是否是正确的操作。|
|无结果查询|此报告显示未返回结果的热门搜索查询。 使用此报告可确定可能导致用户不满意的搜索查询，并提高内容的可发现性。 然后，您可以确定创建答案（如书签）或通过 Graph 连接器来加入新内容是否是正确的操作。|

>[!NOTE]
>目前存在一个已知问题，例如书签等答案所满足的查询被视为放弃的查询。

## <a name="viewing-reports"></a>查看报告

当您导航到使用率报告页面时，所有报告都可供查看。 可以使用日期筛选器来选取要查看的特定日期或月份。

下载报告将允许您从更广泛的时间范围查看报告。 单击下载箭头并选择过去 **31 天** 或 **过去 12 个月**。 报告以电子表格Excel下载。 如果选择了过去 31 天，电子表格将每天具有一个单独选项卡。 过去 12 个月的下载每月都有一个选项卡。

## <a name="frequently-asked-questions"></a>常见问题解答

**当我选择过去 31 天或过去 12 个月时，为什么我随后必须选择特定日期或特定月份。**

目前，Microsoft 搜索使用情况报告中的日历视图是一个两步过程。 首先从下拉列表中选择过去 31 天 (过去 12 个月的日期范围) 然后选择开始日期或月份。

顶部、弃用和失败的查询表显示您选择的第一天或当月的结果。

**我何时会看到过去 7 天、过去 30 天等汇总数据...？**

我们正在考虑这种类型的聚合，并针对这些报告的未来版本简化数据范围筛选。

**为什么我无法按不同应用和源 (使用情况) ？**

目前，无法按源进行筛选。 报告将组合来自 SharePoint Home 和 Office.com 的搜索。 我们的下一版本将包括源筛选，以便你可以查看特定于每个应用程序的指标。

**即将对使用率报告进行哪些其他筛选？**

我们正在研究更多筛选器，这些筛选器有助于在更精细的组织级别了解搜索使用情况。 例如，您将能够查看特定地理位置或部门的查询量。
