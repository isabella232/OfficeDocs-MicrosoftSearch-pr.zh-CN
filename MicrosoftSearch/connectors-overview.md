---
title: 连接器概述
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft 搜索的 Microsoft Graph 连接器概述
ms.openlocfilehash: 677c91f121185faa6dc96f80c517917f429a3ab0
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847516"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Microsoft Graph 连接器概述

[Microsoft 搜索](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) 会索引 [所有 Microsoft 365](https://www.microsoft.com/microsoft-365) 数据，使其可搜索用户。 借助 Microsoft Graph 连接器，你的组织可以索引第三方数据，以便数据显示在 Microsoft 搜索结果中。 这扩展了在 Microsoft 365 生产力应用和更广泛的 Microsoft 生态系统中可搜索的内容源类型。 第三方数据可以托管在本地或公有云或私有云中。

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

本文的其余部分旨在帮助 Microsoft 365 管理员找到可用于回答以下问题的资源：

* [哪些数据源可以连接到 Microsoft 搜索？](#what-data-sources-can-be-connected-to-microsoft-search)
* [如何管理连接？](#how-do-i-manage-my-connections)
* [Graph 连接器的许可证要求和使用条款是什么？](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [如何自定义和配置搜索结果？](#how-do-i-customize-and-configure-search-results)
* [如何从自定义应用程序中搜索连接器数据？](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> Microsoft Graph 连接器和 Microsoft 搜索 API 现已普遍可用。 第一次推出将面向为定向版本配置的客户。 如果要在租户中使用 Graph 连接器，用户和管理员必须选择加入 [定向发布](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)。

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>哪些数据源可以连接到 Microsoft 搜索？

Microsoft 提供了 10 个 Graph 连接器，我们的生态系统合作伙伴已创建 100 多个其他 Graph 连接器。 还可以生成自己的 Graph 连接器。 

### <a name="graph-connectors-by-microsoft"></a>Microsoft 的图表连接器

可以使用 Microsoft 创建的 Graph 连接器连接到以下数据源：

<!---Need to add a few links below when docs exist--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* Azure SQL
* [企业网站](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [文件共享](fileshare-connector.md)
* Oracle (预览) 
* [Salesforce （预览版）](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

[Graph 连接器库](connectors-gallery.md)包含每个 Graph 连接器的简短说明。 如果已准备好将其中一个数据源连接到租户，请务必阅读安装程序概述以及 Microsoft 安装程序连接器[](configure-connector.md)中适用于数据源的其他任何文章。

### <a name="graph-connectors-by-our-partners"></a>合作伙伴的图形连接器

[Microsoft Graph 连接器库](connectors-gallery.md)包括合作伙伴创建的每个 Graph 连接器的简要说明以及指向每个合作伙伴网站的链接。 请直接与每个合作伙伴联系以了解更多信息。

### <a name="build-your-own-graph-connector"></a>生成你自己的 Graph 连接器

如果计划构建自己的 Graph 连接器，请参阅 Microsoft Graph 中的 [Microsoft 搜索 API](https://docs.microsoft.com/graph/search-concept-overview) 概述，了解详细信息。

## <a name="how-do-i-manage-my-connections"></a>如何管理连接？

可以从[Microsoft 365](https://admin.microsoft.com/)管理中心[中的](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)"连接器"选项卡管理连接。 有关详细信息 [，请参阅"管理](manage-connector.md) 连接"。

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Graph 连接器的许可证要求和使用条款是什么？

你需要有效的 Microsoft 365 或 Office 365 许可证和足够的 Graph 连接器配额，以便贵组织的用户能够查看搜索结果中连接器的数据。

若要了解更多信息，请参阅[许可证要求、定价](licensing.md)[和使用条款](terms-of-use.md)。

## <a name="how-do-i-customize-and-configure-search-results"></a>如何自定义和配置搜索结果？

有许多方法可以自定义和配置搜索结果。 有关详细信息，请参阅以下文章：

* [管理垂直领域和结果类型](customize-search-page.md)
* [管理搜索结果布局](customize-results-layout.md)
* [管理结果群集](result-cluster.md)
* [管理自定义筛选器](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>如何从自定义应用程序中搜索连接器数据？

对自定义数据编制索引后，开发人员 [可以查询此数据](https://docs.microsoft.com/graph/search-concept-custom-types)。 可以在任何应用程序中查看数据。 有关详细信息，请参阅 Microsoft [Graph 中的 Microsoft 搜索 API 概述](https://docs.microsoft.com/graph/search-concept-overview)。

## <a name="limitations"></a>限制

* **发布** Microsoft 构建的连接器时，可能需要几分钟时间才能创建连接。 在此期间，连接的状态将显示为"挂起"。

* [Microsoft 365 管理](https://admin.microsoft.com)中心不支持在连接发布后编辑搜索架构。 若要编辑搜索架构，请删除连接，然后创建一个新连接。

* 以大约每秒四个项目的速度限制 Ingestion 吞吐量。

* 不支持架构更新。 创建连接设置后，无法更新架构。 只能删除并重新创建连接。

* 存在连接限制。 每个租户可以创建最多 10 个连接。

* 不支持编辑连接。 创建连接后，无法编辑或更改它。 如果需要更改任何详细信息，则必须删除并重新创建连接。
