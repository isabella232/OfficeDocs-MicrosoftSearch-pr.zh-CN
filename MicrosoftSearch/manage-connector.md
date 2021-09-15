---
title: 管理 Microsoft Graph Connectors for Microsoft 搜索
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 管理 Microsoft Graph Connectors for Microsoft 搜索。
ms.openlocfilehash: dd82114ff6aa651b57ce1941685840906ecf7318
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334469"
---
# <a name="monitor-your-connections"></a>监视连接

若要访问和管理连接器，必须指定为租户的搜索管理员。 请与租户管理员联系，以预配搜索管理员角色。

## <a name="connection-operations"></a>连接操作

导航到"连接器["选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)中的"Microsoft 365 管理中心"。 [](https://admin.microsoft.com)

对于每个连接器类型[，Microsoft 365 管理中心支持](https://admin.microsoft.com)下表中所示的操作：

操作 | Microsoft 的图表连接器 | 合作伙伴或Graph连接器
--- | --- | ---
添加连接 | ：heavy_check_mark： (请参阅 [安装程序概述](configure-connector.md))  | ：x： (请参阅你的合作伙伴或自定义的连接器管理员 UX) 
删除连接 | :heavy_check_mark: | :heavy_check_mark:
编辑已发布的连接 | ：heavy_check_mark： 名称和说明<br></br> ：heavy_check_mark： 连接设置<br></br> ：heavy_check_mark：属性标签<br></br> ：heavy_check_mark： 架构<br></br> ：heavy_check_mark： 刷新计划<br></br> | ：heavy_check_mark： Name<br></br> ：heavy_check_mark： 说明
编辑草稿连接 | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>监视连接状态

创建连接后，已处理项目的数量会显示在"连接器"选项卡上的"Microsoft 搜索 **页上。** 初始完全爬网成功完成后，将显示定期增量爬网的进度。 此页面提供有关连接器日常操作的信息以及日志和错误历史记录的概述。

对于每个连接，"状态 **"** 列中会显示五种状态：

* **正在同步**。 连接器正在对源数据进行爬网，以对现有项目编制索引并进行更新。

* **就绪**：连接已准备就绪，并且没有针对它运行活动的爬网。 **上次同步** 时间指示上次成功爬网的时间。 连接与上次同步时间一样新鲜。

* **已暂停**。 管理员通过暂停选项暂停爬网。 下一次爬网仅在手动恢复时运行。 但是，此连接的数据仍然可搜索。

* **已失败**。 连接出现严重故障。 此错误需要手动干预。 管理员需要根据显示的错误消息采取相应的操作。 在发生错误之前已编制索引的数据是可搜索的。

* **删除失败**。 删除连接失败。 根据失败原因，可能仍对数据编制索引，仍可能会使用项目配额，并且可能仍对连接运行爬网。 建议在此状态中再次尝试删除连接。

## <a name="monitor-your-index-quota-utilization"></a>监视索引配额利用率

可用的索引配额和消耗显示在连接器登录页面上。

:::image type="content" alt-text="索引配额使用率栏。" source="media/quota_utilization.png" lightbox="media/quota_utilization.png":::

配额利用率栏将基于组织的配额消耗指示各种状态：

状态 | 配额利用率级别
--- | --- 
一般 | 0-79%
High | 80-89%
严重 | 90%-99%
完整 | 100%

还将随每个连接显示已编制索引的项目数。 每个连接编制索引的项目数将影响组织可用的总配额。

当超出组织的索引配额时，将影响所有活动连接，并且这些连接将在 **超出限制时** 运行。 在此状态中，活动连接  

* 无法添加新项。

* 将能够更新或删除现有项。

若要解决此问题，可以执行下列任一操作：

* 了解如何在许可要求和定价中为 [组织购买索引配额](licensing.md)。

* 确定要包含过多内容的连接，并更新这些连接以对较少的项目编制索引以为配额提供空间。 若要更新连接，必须删除新引入筛选器并创建一个新连接，该筛选器可引入较少的项目。

* 永久删除一个或多个连接。
