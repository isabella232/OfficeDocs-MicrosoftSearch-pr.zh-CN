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
ROBOTS: NoIndex
description: 查看 Microsoft Search 使用率报告
ms.openlocfilehash: 5bb2ff5a7821e5772e9fb54f60e5e70508194929
ms.sourcegitcommit: ac4e261c01262be747341f810d2d1faf220d3961
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "49382663"
---
# <a name="microsoft-search-usage-reports"></a>Microsoft Search 使用率报告

利用搜索使用率报告，您可以更好地了解搜索在您的组织中的工作方式。 通过这些报告生成的见解可帮助您 [轻松查找内容](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find) ，并采取行动，将使搜索对用户的体验更有用和 delightful。

> [!IMPORTANT]
> Microsoft Search 使用率报告当前处于预览阶段。

[Microsoft 搜索使用情况报告](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights)包括从在 SharePoint 主页和 Office.com 搜索框中执行的搜索生成的图形和表。 您可以查看过去31天、每天或上一年的每月的数据。 这些报告即将推出，因此需要花费一些时间来累积历史数据。

此页面的早期版本包含来自在 Bing 中对 Bing.com 执行 Microsoft 搜索的搜索中的数据。 该数据不久将集成到这些报告中，但现在，您仍可以通过单击页面底部的链接 **查看 Bing 的最前面的查询和印象分布**，以查看这些报告。

![搜索使用率报告仪表板](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>搜索报告概述

|**报告**|**说明**|
|:-----|:-----|
|查询量|此报告显示执行的搜索查询的数量。 使用此报告可确定搜索查询量趋势，并确定搜索活动量较高和较低的时段。|
|热门查询|此报告显示最热门的搜索查询。 使用此报告可了解您的用户搜索的信息类型。|
|放弃的查询|此报告显示最常用的搜索查询，这些查询接收的点击率较低。 使用此报告可确定可能导致用户不满意的搜索查询，并提高内容的可发现性。 然后，您可以确定创建答案（如书签），还是通过 Graph 连接器 ingesting 新内容是正确的操作。|
|无结果查询|此报告显示未返回结果的热门搜索查询。 使用此报告可确定可能导致用户不满意的搜索查询，并提高内容的可发现性。 然后，您可以确定创建答案（如书签），还是通过 Graph 连接器 ingesting 新内容是正确的操作。|

## <a name="viewing-reports"></a>查看报告

当您导航到 "使用率报告" 页时，可以查看所有报告。 您可以使用日期筛选器选取要查看的特定日期或月份。

通过下载报告，可以在更广泛的时间范围内查看报告。 单击 "下载" 箭头，然后选择 " **过去31天** " 或 " **过去12个月**"。 该报告将下载为 Excel 电子表格。 如果您选择了31天，电子表格将为每个工作日的 "每个" 选项卡。 过去12个月的下载内容将每月包含一个选项卡。

若要查看必应的热门查询和印记分布报告，请单击页面上的链接。

## <a name="frequently-asked-questions"></a>常见问题解答

**当我选择 "过去31天" 或 "过去12个月" 时，为什么必须分别选择特定日期或特定月份。**

Microsoft search 使用率报告中今天的日历视图分为两个步骤。 先从下拉列表 (过去31天或最近12个月) 中选择日期范围，然后选择 "开始日" 或 "月"。

顶部、已放弃和失败的查询表显示从所选日或月的结果。

**何时，我将看到过去7天的聚合数据（过去30天），如 Bing 的首要查询报告？**

我们正在考虑此类聚合，并简化了这些报告的未来版本的数据范围筛选。

**为什么我无法查看不同应用 (源) 的使用率报告细目？**

当前，按源筛选不可用。 这些报告将搜索与 SharePoint 主页和 Office.com 合并在一起。 我们的下一个版本将包含源筛选，以便您可以查看特定于每个应用程序的指标。

**其他使用情况报告的筛选功能即将推出？**

我们正在努力处理更多的筛选器，以帮助您在组织的更精细级别上了解搜索的使用情况。 例如，你将能够查看特定地理位置或部门的查询量。

**为什么在 Bing 报告中的 Microsoft 搜索位于单独的页面上？**

新式化 in Office 365 应用程序中的搜索要求我们加入以前完全不同的系统，包括报告生成。 这需要很长时间，我们认为，立即获取这些报告和等待，直到我们能够完成 Bing 数据的集成，这一点也非常重要。 完成集成后，来自所有搜索终结点的数据将包含在同一个报告中。
