---
title: 搜索使用率报告
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.topic: article
ms.service: mssearch
audience: Admin
ms.audience: Admin
ms.date: 07/02/2021
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 查看Microsoft 搜索使用情况报告
ms.openlocfilehash: 9de48331efbc956ee7d980b919d9bd2f025fc8aa
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375783"
---
# <a name="microsoft-search-usage-reports"></a>Microsoft 搜索使用率报告

利用搜索使用率报告，您可以更好地了解搜索在组织中如何运行。 从这些报告生成的见解将帮助您使内容易于查找，[](./make-content-easy-to-find.md)并采取措施，使搜索成为更有用且更令人愉悦的体验。

> [!IMPORTANT]
> Microsoft 搜索使用情况报告当前处于预览阶段

此[Microsoft 搜索使用情况](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights)报告包括从 SharePoint Home、Office.com 和 必应 搜索框中执行的搜索Microsoft 搜索图表和表。 你可以查看过去 31 天、每天或上一年每月的数据。 这些报告刚刚推出，因此需要一段时间来累算历史数据。

此页面的早期版本包含仅针对 Microsoft 搜索.com 上必应搜索必应数据。 该数据现已集成到这些报告;你仍然可以通过单击页面底部的链接来查看旧页面，必应热门查询和印象 **分布**。 此链接和旧页面将很快删除。

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

下载报告将允许您从更广泛的时间范围查看报告。 单击下载箭头并选择过去 **31 天** 或 **过去 12 个月**。 报告下载为Excel电子表格。 如果选择了过去 31 天，电子表格将每天具有一个单独选项卡。 过去 12 个月的下载每月都有一个选项卡。

若要查看必应热门查询和印象分布报告，请单击页面上的链接。

## <a name="frequently-asked-questions"></a>常见问题解答

**当我选择过去 31 天或过去 12 个月时，为什么我随后必须选择特定日期或特定月份。**

目前，Microsoft 搜索使用情况报告中的日历视图是一个两步过程。 首先从下拉列表中选择过去 31 天 (过去 12 个月的日期范围) 然后选择开始日期或月份。

顶部、弃用和失败的查询表显示您选择的第一天或当月的结果。

**我何时会看到过去 7 天、过去 30 天的聚合数据，等等...就像必应热门查询报告一样？**

我们正在考虑这种类型的聚合，并针对这些报告的未来版本简化数据范围筛选。

**为什么我看不到按不同应用和源 (使用情况) ？**

目前，无法按源进行筛选。 报告将组合来自 SharePoint Home 和 Office.com 的搜索。 我们的下一版本将包括源筛选，以便你可以查看特定于每个应用程序的指标。

**即将对使用率报告进行哪些其他筛选？**

我们正在研究其他筛选器，这些筛选器有助于在更精细的组织级别了解搜索使用情况。 例如，您将能够查看特定地理位置或部门的查询量。
