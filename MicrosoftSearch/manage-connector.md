---
title: 为 Microsoft Search 管理 Microsoft Graph 连接器
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 为 Microsoft Search 管理 Microsoft Graph 连接器。
ms.openlocfilehash: 3e652b9afad78f784ff4c726ecab34bef883d4c3
ms.sourcegitcommit: a8a6c949f249d106f37103e127d2ea7df730f7a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702764"
---
# <a name="manage-your-connector-for-microsoft-search"></a>管理你的连接器以进行 Microsoft Search

若要访问和管理连接器，必须将其指定为租户的搜索管理员。 请联系你的租户管理员，为你提供搜索管理员角色。

## <a name="get-started"></a>入门

导航到[Microsoft 365 管理中心](https://admin.microsoft.com)中的 "[连接器" 选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。

对于每种连接器类型， [Microsoft 365 管理中心](https://admin.microsoft.com)支持下表中所示的操作：

操作 | Microsoft 构建的连接器 | 合作伙伴或自定义生成的连接器
--- | --- | ---
添加连接 | ： heavy_check_mark：（请参阅[配置 Microsoft 构建的连接器](configure-connector.md)） | ： x：（请参阅合作伙伴或自定义内置连接器管理员 UX）
删除连接 | ： heavy_check_mark： | ： heavy_check_mark：
编辑已发布的连接 | ： heavy_check_mark： Name<br></br> ： heavy_check_mark：说明<br></br> ： heavy_check_mark：外部数据源的身份验证凭据<br></br> ： heavy_check_mark：本地数据源的网关凭据<br></br> ： heavy_check_mark：刷新计划<br></br> | ： heavy_check_mark： Name<br></br> ： heavy_check_mark：说明
编辑拔模连接 | ： heavy_check_mark： | 版

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

下面列出了可针对任何连接显示的不同错误。 如果这些解决方案不起作用，请联系支持部门或向我们发送[反馈](connectors-feedback.md)。

错误代码 | 错误消息 | 解决方案
--- | --- | ---
1000 | 数据源不可用。 请检查 internet 连接或确保该连接器仍可访问该数据源。 | 当数据源由于网络问题或数据源本身被删除、移动或重命名而无法访问时，将发生此错误。 检查提供的数据源详细信息是否仍然有效。
1001 | 无法更新数据，因为数据源正在限制连接器。 | 若要 unthrottle 数据源，请检查其规模限制是否可以增加，或等待一天内的流量较长的时间。
1002 | 无法对数据源进行身份验证。 验证与此数据源关联的凭据是否正确。 | 单击 "**编辑**" 以更新身份验证凭据。
1003 | 与连接器关联的帐户无权访问该项目。 |  确保正确的帐户具有对要编制索引的项目的访问权限。
1004 | 无法访问本地数据网关。 请确保网关服务正在运行，并且在连接配置中更新了网关详细信息。 | 使用网关检查计算机，打开 Power BI 网关应用程序，并确保网关正在运行。 验证网关使用的是与 Microsoft 搜索相同的管理员帐户，然后确保连接配置中的所有网关详细信息都已更新。
1005 | 与此数据源关联的凭据已过期。 续订凭据并更新连接。 | 单击 "**编辑**" 以更新身份验证凭据。
1006 | 您的网关版本已过期，不会再支持此连接器。 你将需要更新网关。 | 请访问[安装本地 data gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) ，以在包含网关的计算机上下载并安装最新版本的 Power BI 网关。
1007 | 未检测到有效的 Power BI 许可证。 您需要有效的 Power BI 许可证来执行此爬网。 | 您需要有效的 Power BI 许可证来执行此爬网。 请检查您的组织是否具有有效的许可证。 如果是，请再试一次。 如果不是，请获取许可证，然后重试。
1008 | 租户的总配额使用率已达到其限制。 尝试删除连接以释放一些配额，或调整摄取筛选器以引入较少的数据。 | 尝试删除连接以释放一些配额，或调整摄取筛选器以引入较少的数据。 如果不能解决问题，请联系 Microsoft 支持部门。
2001 | 由于队列中的更新数过多，索引被限制。 根据队列的不同，可能需要一段时间才能完成更新。 | 请等待队列被清除。
2002 | 由于不受支持的项格式设置而导致索引失败。 | 有关详细信息，请参阅连接器特定文档。
2003 | 由于不受支持的项目内容而导致索引失败。 | 有关详细信息，请参阅连接器特定文档。
2004 | [文件大小](https://docs.microsoft.com/microsoftsearch/file-share-connector#content-requirements)太大，无法编制索引。 在处理之前，它必须小于或等于 100 MB，且处理后不大于 4 MB。 在这种情况下，将对文件编制部分索引。 文件中存在的短语数可能不会返回搜索结果。 | 有关详细信息，请参阅[文件共享特定文档](https://docs.microsoft.com/MicrosoftSearch/file-share-connector#content-requirements)。
5000 | 出现问题。 如果这种情况继续存在，请与支持人员联系。 |

## <a name="preview-limitations"></a>预览限制

* **发布**Microsoft 构建的连接器时，可能需要几分钟的时间才能创建连接。 在这段时间内，连接会将其状态显示为 "挂起"。 此外，也不会进行自动刷新，因此需要手动刷新。

* [Microsoft 365 管理中心](https://admin.microsoft.com)不支持在连接发布后查看和编辑**搜索架构**。 若要编辑搜索架构，请删除您的连接，然后创建一个新的连接。

* 在管理连接的**刷新计划**时，将显示在每个会话期间同步的项目数。 但是，同步历史记录不可用。
