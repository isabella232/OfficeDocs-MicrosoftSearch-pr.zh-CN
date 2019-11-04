---
title: 为 Microsoft Search 管理 Microsoft Graph 连接器
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 为 Microsoft Search 管理 Microsoft Graph 连接器。
ms.openlocfilehash: 5aab310a05d073221918a8aaa80ea1e06c818e51
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949637"
---
# <a name="manage-your-connector-for-microsoft-search"></a>管理你的连接器以进行 Microsoft Search

若要访问和管理连接器，必须将其指定为租户的搜索管理员。 请联系你的租户管理员，为你提供搜索管理员角色。

## <a name="get-started"></a>入门

1. 登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。
2. 转到 "**设置** > **Microsoft Search** > **连接器**"。

对于每种连接器类型， [Microsoft 365 管理中心](https://admin.microsoft.com)支持下表中所示的操作：

**操作** | **Microsoft 构建的连接器** | **合作伙伴或自定义生成的连接器**
--- | --- | ---
添加连接 | ： heavy_check_mark：（请参阅[Configure a Microsoft 内置的连接器](configure-connector.md)） | ： x：（请参阅合作伙伴或自定义内置连接器管理员 UX）
删除连接 | :heavy_check_mark: | :heavy_check_mark:
编辑已发布的连接 | ： heavy_check_mark： Name<br></br> ： heavy_check_mark： Description<br></br> ： heavy_check_mark：外部数据源的身份验证凭据<br></br> ： heavy_check_mark：本地数据源的网关凭据<br></br> ： heavy_check_mark： Refresh schedule<br></br> | ： heavy_check_mark： Name<br></br> ： heavy_check_mark： Description
编辑拔模连接 | :heavy_check_mark: | 版

## <a name="monitor-your-connection-status"></a>监视连接状态
创建连接后，已处理的项目数显示在**Microsoft 搜索**页面上的 "**连接器**" 选项卡上。 成功完成初始完全爬网后，会显示定期增量爬网的进度。 此页面提供有关连接器的日常操作的信息，以及日志和错误历史记录的概述。

"**状态**" 列中显示的四种状态针对每个连接：
* **同步**。 连接器将对源中的数据进行爬网，以对现有项目编制索引并进行任何更新。
* **已启用**：连接已启用，并且没有对其运行的活动爬网。 **上次同步时间**表示上次成功爬网发生的时间。 连接与上次同步时间一样新。
* **暂停**。 管理员通过 "暂停" 选项暂停爬网。 下一次爬网仅在手动恢复时运行。 但是，此连接中的数据将继续可搜索。
* **失败**。 连接发生严重故障。 此错误需要手动干预。 管理员需要根据所显示的错误消息采取适当的操作。 在出现错误之前编制索引的数据是可搜索的。

### <a name="monitor-errors"></a>监视错误
对于 "**连接器**" 选项卡上的每个**活动连接器**，"**错误**" 选项卡下将显示任何现有的爬网错误。该选项卡列出错误代码、每个错误的计数以及错误日志下载选项。 请参阅下图中的示例。 选择**错误代码**以查看错误的详细信息。

![选择了连接器的连接器列表，详细信息窗格显示了此连接器的3个错误。](media/errormonitoring1.png)

若要查看错误的特定详细信息，请选择其错误代码。 屏幕上会显示错误详细信息和链接。 最新错误显示在顶部。 请参阅下表中的示例。

![连接器列表，选择了一个连接器，详细信息窗格显示了连接器的错误列表。 ](media/errormonitoring2.png)

## <a name="preview-limitations"></a>预览限制
* **发布**Microsoft 构建的连接器时，可能需要几分钟的时间才能创建连接。 在这段时间内，连接会将其状态显示为 "挂起"。 此外，也不会进行自动刷新，因此需要手动刷新。
* [Microsoft 365 管理中心](https://admin.microsoft.com)不支持在连接发布后查看和编辑**搜索架构**。 若要编辑搜索架构，请删除您的连接，然后创建一个新的连接。
* 在管理连接的**刷新计划**时，将显示在每个会话期间同步的项目数。 但是，同步历史记录不可用。
