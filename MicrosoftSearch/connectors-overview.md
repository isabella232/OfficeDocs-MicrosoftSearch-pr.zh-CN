---
title: Microsoft Graph 连接器概述
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Graph 连接器概述Microsoft 搜索
ms.openlocfilehash: 8b7c4545022765a5e903f2ba98490dae0cd40e85
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235863"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Microsoft Graph 连接器概述

[Microsoft 搜索](./overview-microsoft-search.md)索引所有[Microsoft 365](https://www.microsoft.com/microsoft-365)数据，使其可搜索用户。 借助 Microsoft Graph连接器，组织可以索引第三方数据，以便数据显示在Microsoft 搜索结果中。 此功能扩展了 Microsoft 365 生产力应用中可搜索的内容源类型以及 Microsoft 更广泛的数据源。 第三方数据可以本地托管，也可以托管在公有云或私有云中。

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

本文旨在帮助管理员Microsoft 365查找可用于回答以下问题的资源：

* [哪些数据源可以连接到Microsoft 搜索？](#what-data-sources-can-be-connected-to-microsoft-search)
* [如何管理连接？](#how-do-i-manage-my-connections)
* [Microsoft 连接器的许可要求和使用条款是什么Graph？](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [预览功能是什么？](#what-are-the-preview-features)
* [如何自定义和配置搜索结果？](#how-do-i-customize-and-configure-search-results)
* [如何从自定义应用程序中搜索连接器数据？](#how-do-i-search-my-connector-data-from-a-custom-application)
* [如何自定义搜索结果？](#how-do-i-customize-search-results)
* [连接器限制是什么](#what-are-the-connector-limitations)

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>哪些数据源可以连接到Microsoft 搜索？

Microsoft 提供了 9 个连接器，我们的生态系统合作伙伴已创建 100 多个连接器。 您还可以构建您自己的连接器。

### <a name="microsoft-graph-connectors-by-microsoft"></a>Microsoft Graph连接器

可以使用 Microsoft 创建的连接器连接到以下数据源：

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL 和 Microsoft SQL Server](MSSQL-connector.md)
* [企业网站](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [文件共享](fileshare-connector.md)
* [Oracle SQL](OracleSQL-connector.md)
* [Salesforce （预览版）](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

[Microsoft Graph 连接器](https://www.microsoft.com/microsoft-search/connectors)库包含每个连接器的简短说明。 如果已准备好将其中一个数据源连接到租户，请务必阅读安装程序概述以及适用于数据源的"Microsoft[](configure-connector.md)安装连接器"部分中的其他任何文章。

### <a name="microsoft-graph-connectors-by-our-partners"></a>由Graph的 Microsoft 连接器

[Microsoft Graph 连接器](https://www.microsoft.com/microsoft-search/connectors)库包括我们的合作伙伴创建的每个连接器的简短说明，以及指向每个合作伙伴网站的链接。 若要了解更多信息，请直接与每个合作伙伴联系。

### <a name="build-your-own-microsoft-graph-connector"></a>生成你自己的 Microsoft Graph 连接器

如果愿意，可以生成自己的连接器。 有关生成连接器详细信息，请参阅生成首个自定义[Microsoft Graph 连接器](/graph/connecting-external-content-build-quickstart)。

## <a name="how-do-i-manage-my-connections"></a>如何管理连接？

可以从"连接器"选项卡[中的"连接器"选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)[Microsoft 365 管理中心。](https://admin.microsoft.com/) 有关管理连接的信息，请参阅： [管理连接](manage-connector.md)。

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a>连接器的许可证要求和使用条款是什么？

您需要一个有效的Microsoft 365或Office 365许可证和足够的连接器配额，以便贵组织的用户能够查看搜索结果中来自连接器的数据。

若要了解更多信息，请参阅许可证[要求和定价](licensing.md)[和使用条款](terms-of-use.md)。

## <a name="what-are-the-preview-features"></a>预览功能是什么？

尽管 Microsoft Graph连接器Microsoft 搜索 API 现已普遍可用，但预览版中有几个功能。

预览版中的连接器和功能集包括：

* [Azure DevOps连接器](azure-devops-connector.md)
* [Salesforce 连接器](salesforce-connector.md)
* 具有使用源 ACL 的搜索权限的[ServiceNow](servicenow-connector.md)连接器
* [管理自定义筛选器](custom-filters.md)
* [垂直连接中的多个连接](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a>如何自定义和配置搜索结果？

有很多方法可以自定义和配置搜索结果。 有关详细信息，请参阅以下文章：

* [管理垂直领域和结果类型](customize-search-page.md)
* [管理搜索结果布局](customize-results-layout.md)
* [管理结果群集](result-cluster.md)
* [管理自定义筛选器](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>如何从自定义应用程序中搜索连接器数据？

对自定义数据编制索引后，开发人员 [可以查询此数据](/graph/search-concept-custom-types)。 可以在任何应用程序中查看数据。 有关详细信息，请参阅 Microsoft Microsoft 搜索[中的 Graph API 概述](/graph/search-concept-overview)。

## <a name="how-do-i-customize-search-results"></a>如何自定义搜索结果？

下一步是按照本文中的建议自定义搜索结果，如何[自定义和配置搜索结果？。](#how-do-i-customize-and-configure-search-results) 若要了解有关自定义搜索结果的信息，请参阅自定义 [搜索结果页面](customize-search-page.md)。

## <a name="what-are-the-connector-limitations"></a>连接器限制是什么？

* 发布 **Microsoft** 构建的连接器时，可能需要几分钟时间才能创建连接。 在此期间，连接的状态将显示为"挂起"。

* 以大约每秒四个项目的速度限制 Ingestion 吞吐量。

* 不支持架构更新。 创建连接设置后，无法更新架构。 只能删除并重新创建连接。

* 存在连接限制。 每个租户可以创建最多 10 个连接。

* 创建连接后，不能编辑或更改连接。 如果需要更改任何详细信息，则必须删除并重新创建连接。
