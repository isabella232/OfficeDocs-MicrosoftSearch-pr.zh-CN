---
title: 管理自定义筛选器
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 管理自定义筛选器
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927377"
---
# <a name="create-custom-filters"></a>创建自定义筛选器

您可以创建筛选器，以自定义用户在[Bing](https://bing.com)中的 microsoft [SharePoint](https://sharepoint.com/)、Microsoft [Office](https://office.com)和 microsoft 搜索中进行搜索时看到的搜索体验。 通过筛选器，用户可以快速从搜索查询中优化结果集。

可以基于 connection 属性在垂直方向创建自定义筛选器。 例如，您可以在自定义垂直内为 ServiceNow 连接创建 **已发布的 On** 筛选器。

## <a name="things-to-consider"></a>注意事项

1. 对于在连接内容源上创建自定义筛选器，提供了一些附加功能：
- 您还可以在 "连接器源" 属性的 "别名" 上创建筛选器
- 如果垂直具有多个连接，则可以通过这些连接创建公用筛选器。 为此，可以通过在别名源属性在不同连接之间进行的通用别名创建筛选器来实现。 例如，您可以通过创建别名，在 ServiceNow & Jira 连接中创建 **作者** 筛选器，如下所示：

| Connection | 属性 | Alias |
| --- | --- | --- |
| 服务现在 | 所有者 | 作者 |
| Jira | Publisher | 作者 |

2. 筛选器位于垂直范围内。 由此  
- 如果筛选器是以组织级别的垂直方式创建的，则筛选器将仅在组织级别可见
- 如果在垂直位置创建了筛选器，该筛选器在网站级别，则筛选器仅在网站级别可见。

## <a name="steps-to-create-custom-filter"></a>创建自定义筛选器的步骤

### <a name="create-filter-in-organizational-level-vertical"></a>在组织级别中创建筛选器垂直：

若要在 Microsoft search 中创建筛选器，请按照以下步骤操作：

1. 在 Microsoft 365 管理中心，转到 " [纵向](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) " 页面。
2. 创建/编辑要在其中创建筛选器的垂直
3. 导航到向导中的 "筛选器" 步骤
4. 单击 "添加筛选器"，并在添加筛选器后开始，可以查看并保存垂直。

## <a name="known-limitations"></a>已知限制

1. 您当前可以仅在字符串 & 日期类型托管属性上创建筛选器。
2. 无法创建分层筛选器

## <a name="resources"></a>资源

[自定义搜索结果页面](customize-search-page.md)