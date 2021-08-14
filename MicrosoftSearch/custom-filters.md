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
ms.openlocfilehash: 256cf9748aa3050aacf48c3562f6f84b4ba2e460
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235922"
---
# <a name="manage-custom-filters"></a>管理自定义筛选器

可以使用筛选器自定义自定义Microsoft 搜索体验。 通过筛选器，用户可以快速优化其搜索查询中的结果集。

可以在垂直方向基于连接属性创建自定义筛选器。 例如，可以在垂直方向 **为** ServiceNow 连接创建"发布时间"筛选器。

> [!NOTE]
> 自定义筛选器当前在定向发布中对管理员和最终用户处于预览阶段。 有关预览的详细信息，请参阅 [连接器预览功能](connectors-overview.md#what-are-the-preview-features)。

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>在组织级别垂直创建筛选器

若要在 Microsoft 搜索上创建筛选器，请按照以下步骤操作：

1. In the Microsoft 365 管理中心， go to [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
1. 创建/编辑要创建筛选器的垂直方向
1. 导航到向导中的"筛选器"步骤
1. 单击"添加筛选器"并开始使用
1. 添加筛选器后，你可以查看并保存垂直。

## <a name="things-to-consider"></a>注意事项

1. 连接内容上存在其他筛选器功能。

    - 还可以对连接器源属性的别名创建筛选器
    - 如果垂直连接有多个连接，可以在这些连接之间创建一个通用筛选器。 为此，可以在常见别名上创建筛选器，以跨不同连接对源属性进行别名设置。 例如，可以通过创建别名跨ServiceNow 和 Jira 连接创建 Author 筛选器，如下所示：

    | Connection | 属性 | 别名 |
    | --- | --- | --- |
    | 服务现在 | 所有者 | 作者 |
    | Jira | Publisher | 作者 |

1. 筛选器存在于垂直范围内。

    - 如果在组织级别垂直创建筛选器，则筛选器将仅在组织级别可见
    - 如果在网站级别的垂直方向创建筛选器，则筛选器将仅在网站级别可见。

## <a name="known-limitations"></a>已知限制

1. 当前只能对字符串或日期类型托管&创建筛选器。
1. 无法创建分层筛选器。

## <a name="resources"></a>资源

[管理垂直领域和结果类型](customize-search-page.md)
