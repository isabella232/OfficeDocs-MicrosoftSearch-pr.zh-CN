---
title: 管理 Microsoft 搜索的 Microsoft Graph 连接器
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 管理 Microsoft 搜索的 Microsoft Graph 连接器。
ms.openlocfilehash: 488b6e9452e381f8fc64ad06c6f063aa170ca7f5
ms.sourcegitcommit: 3ed4d21510020045d25e8c5b7e168013d96c1b7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50464037"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>监视连接

若要访问和管理连接器，必须指定为租户的搜索管理员。 请与租户管理员联系，以预配搜索管理员角色。

## <a name="connection-operations"></a>连接操作

导航到[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)[Microsoft 365 管理中心中的"连接器"选项卡](https://admin.microsoft.com)。

对于每个连接器类型 [，Microsoft 365 管理](https://admin.microsoft.com) 中心支持下表中显示的操作：

Operation | Microsoft 构建的连接器 | 合作伙伴或自定义生成连接器
--- | --- | ---
添加连接 | ：heavy_check_mark： (请参阅[配置 Microsoft 构建的连接器) ](configure-connector.md) | ：x： (参考合作伙伴或自定义生成连接器管理员 UX) 
删除连接 | :heavy_check_mark: | :heavy_check_mark:
编辑已发布的连接 | ：heavy_check_mark： Name<br></br> ：heavy_check_mark：说明<br></br> ：heavy_check_mark：外部数据源的身份验证凭据<br></br> ：heavy_check_mark：本地数据源的网关凭据<br></br> ：heavy_check_mark：刷新计划<br></br> | ：heavy_check_mark： Name<br></br> ：heavy_check_mark：说明
编辑草稿连接 | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>监视连接状态

创建连接后，已处理项目的数量会显示在 Microsoft 搜索页上的"连接器"**选项卡** 上。 初始完全爬网成功完成后，将显示定期增量爬网的进度。 此页面提供有关连接器日常操作的信息以及日志和错误历史记录的概述。

每个连接的"状态 **"列中显示** 四种状态：

* **正在同步**。 连接器正在对源数据进行爬网，以对现有项目编制索引并进行更新。

* **已启用**：连接已启用，并且没有针对它运行的活动爬网。 **上次同步** 时间指示上次成功爬网发生的时间。 连接与上次同步时间一样新鲜。

* **已暂停**。 管理员通过暂停选项暂停爬网。 下一次爬网仅在手动恢复时运行。 但是，此连接的数据仍然可搜索。

* **失败**。 连接发生严重失败。 此错误需要手动干预。 管理员需要根据显示的错误消息采取相应的操作。 在发生错误之前已编制索引的数据是可搜索的。

## <a name="monitor-your-index-quota-utilization"></a>监视索引配额利用率

可用索引配额和消耗显示在连接器登录页上。

![索引配额使用率栏](media/quota_utilization.png)

>[!NOTE]
>在预览期间，每个尝试使用 Graph 连接器的组织都获得免费固定配额，所有连接中最多包含 200 万个项目。 在 Graph 连接器正式发布后，对于预览版中一直使用 Graph 连接器的组织，免费配额将于 2021 年 4 月 1 日到期。
>标记为"预览"的 Microsoft 构建[](connectors-preview.md)的 Graph 连接器不会包含在组织的已收费总索引配额中。 但是，它算作可以为组织配置的最多 10 个连接数，以及组织跨连接可编制索引的最大项目数为 700 万个;每个连接限制为 700，000 个项目。 

配额使用率栏将基于组织配额的使用情况指示各种状态：

状态 | 配额消耗
--- | ---
一般 | 1-69%
高 | 70-89%
关键 | 90%-99%
完整 | 100%

索引的项目数也会随每个连接一起显示。 每个连接索引的项目数将影响组织可用的总配额。

当超出组织的索引配额时，所有活动连接都将受到影响，并且这些连接将超出 **限制** 。 在此状态中，活动连接  

* 将无法添加新项。

* 将能够更新或删除现有项目。

若要解决此问题，可以执行下列任一操作：

* 了解如何根据许可要求和定价为组织 [购买索引配额](licensing.md)。

* 确定要包含太多内容的连接，并更新这些连接以索引更少的项目，以为配额提供空间。 若要更新连接，必须删除并创建具有新引入筛选器的新连接，该筛选器将引入较少的项目。

* 永久删除一个或多个连接
