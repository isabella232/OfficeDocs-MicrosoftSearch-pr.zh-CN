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
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790326"
---
# <a name="manage-custom-filters"></a>管理自定义筛选器

可以使用筛选器自定义 Microsoft 搜索体验。 通过筛选器，用户可以快速优化其搜索查询中的结果集。

可以基于连接属性在垂直方向上创建自定义筛选器。 例如，可以在垂直方向上为 ServiceNow 连接创建" **发布** 时间"筛选器。

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>在组织级别垂直创建筛选器

若要在 Microsoft 搜索上创建筛选器，请按照以下步骤操作：

1. 在 Microsoft 365 管理中心中，转到["垂直"。](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
1. 创建/编辑要创建筛选器的垂直方向
1. 导航到向导中的"筛选器"步骤
1. 单击"添加筛选器"并开始操作
1. 添加筛选器后，你可以查看并保存垂直。

## <a name="things-to-consider"></a>注意事项

1. 连接内容上存在其他筛选器功能。

    - 还可以在别名上创建连接器源属性的筛选器
    - 如果垂直连接有多个连接，可以在这些连接之间创建一个公用筛选器。 为此，可以在常见别名上创建筛选器，该筛选器将跨不同连接对源属性进行别名设置。 例如，可以通过创建别名跨ServiceNow 和 Jira 连接创建作者筛选器，如下所示：

    | Connection | 属性 | 别名 |
    | --- | --- | --- |
    | 服务现在 | 所有者 | 作者 |
    | Jira | Publisher | 作者 |

1. 筛选器存在于垂直范围内。

    - 如果在组织级别以垂直方向创建筛选器，则筛选器将仅在组织级别可见
    - 如果在网站级别以垂直方式创建筛选器，则筛选器将仅在网站级别可见。

## <a name="known-limitations"></a>已知限制

1. 当前只能对字符串类型托管&创建筛选器。
1. 无法创建分层筛选器。

## <a name="resources"></a>资源

[管理垂直领域和结果类型](customize-search-page.md)
