---
title: 搜索使用率报告
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 查看 Microsoft 搜索使用情况报告
ms.openlocfilehash: 04de0de08423eff1368bc2b77e48d3fc8add038d
ms.sourcegitcommit: 1d6fcf180f427abf3d8bfa4b8b6129e39f60ceb4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712608"
---
# <a name="microsoft-search-usage-reports"></a>Microsoft 搜索使用率报告

搜索使用率报告使您能够更好地了解搜索在组织中运行方式。 从这些报告生成的见解将帮助您使内容易于查找，[](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find)并采取措施，使搜索更有用且更令人愉悦。

> [!IMPORTANT]
> Microsoft 搜索使用情况报告目前处于预览阶段，正在向定向版本中的管理员推出。 确保你的管理员帐户位于定向发布圈中，以查看这些报告。

Microsoft [搜索使用情况报告](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) 包括从 SharePoint 主页和搜索框中执行的搜索生成的Office.com表。 你可以查看前一年过去 31 天、每天或每月的数据。 这些报告刚刚推出，因此需要一段时间来累算历史数据。

此页面的早期版本包含针对必应必应中的 Microsoft 搜索执行的搜索Bing.com。 这些数据将很快集成到这些报告中，但现在，你仍然可以通过单击页面底部的链接查看 **必应** 的顶部查询和印象分布来查看这些报告。

> [!div class="mx-imgBorder"]
> ![搜索使用率报告仪表板](media/usage-reports/usage_reports_v2.png)


## <a name="overview-of-search-reports"></a>搜索报告概述

| 报告 | 说明 |
|:-----|:-----|
|查询卷|此报告显示执行的搜索查询的数量。 使用此报告可确定搜索查询量趋势，并确定高搜索活动和低搜索活动的时间段。|
|热门查询|此报告显示最热门的搜索查询。 使用此报告可了解用户要搜索的信息类型。|
|放弃的查询|此报告显示点击率较低的热门搜索查询。 使用此报告可确定可能导致用户不满意的搜索查询，并提高内容的可发现性。 然后，你可以确定创建答案（如书签）或通过 Graph 连接器插入新内容是否是正确的操作。|
|无结果查询|此报告显示未返回结果的热门搜索查询。 使用此报告可确定可能导致用户不满意的搜索查询，并提高内容的可发现性。 然后，你可以确定创建答案（如书签）或通过 Graph 连接器插入新内容是否是正确的操作。|

## <a name="viewing-reports"></a>查看报告

当您导航到使用率报告页面时，所有报告都可供查看。 您可以使用日期筛选器来选取要查看的特定日期或月份。

下载报告将允许您在更广泛的时间范围内查看报告。 单击下载箭头并选择 **过去 31 天或****过去 12 个月**。 报告下载为 Excel 电子表格。 如果选择了过去 31 天，电子表格将包含每天的单个选项卡。 过去 12 个月的下载每月都有一个选项卡。

若要查看必应热门查询和印象分布报告，请单击页面上的链接。

## <a name="frequently-asked-questions"></a>常见问题解答

**当我选择过去 31 天或过去 12 个月时，为什么随后必须选择特定日期或特定月份。**

现在，Microsoft 搜索使用率报告中的日历视图是一个两步过程。 首先从下拉列表中选择过去 31 (过去 12 个月的日期范围) 然后选择开始日期或月份。

顶部、放弃和失败的查询表显示您选择的第一天或该月的结果。

**我何时会看到过去 7 天、过去 30 天等的聚合数据...像必应的热门查询报告一样？**

我们正在考虑这种类型的聚合，并针对这些报表的未来版本简化数据范围筛选。

**为什么我无法查看不同应用和源的使用情况 (细分) ？**

目前，无法按源进行筛选。 报告将 SharePoint 主页中的搜索与搜索Office.com。 我们的下一版本将包括源筛选，以便你可以查看特定于每个应用程序的指标。

**即将对使用情况报告进行哪些其他筛选？**

我们正在研究其他筛选器，这些筛选器有助于在更精细的组织级别了解搜索使用情况。 例如，您将能够查看特定地理位置或部门的查询量。

**为什么必应中的 Microsoft 搜索报告位于单独的页面上？**

将 Office 365 应用程序中的搜索现代化到 Microsoft 搜索需要我们加入以前不同的系统，包括报告生成。 这需要花费一些时间，并且我们认为现在让这些报告退出比等待完成 Bing 数据集成更加重要。 完成集成后，来自所有搜索终结点的数据将包含在同一报告中。
