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
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367520"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Microsoft Graph 连接器概述

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) 将对所有 [Microsoft 365](https://www.microsoft.com/microsoft-365) 数据编制索引，使其可供用户搜索。 使用 Microsoft Graph 连接器，您的组织可以对第三方数据编制索引，使其显示在 Microsoft 搜索结果中。 这将扩展在 Microsoft 365 生产力应用和更广泛的 Microsoft 生态系统中可搜索的内容源的类型。 第三方数据可以在内部部署或公共或私有云承载。

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

本文的其余部分旨在帮助 Microsoft 365 管理员找到 avaiable 的资源，以回答以下问题：

* [哪些数据源可以连接到 Microsoft 搜索？](#what-data-sources-can-be-connected-to-microsoft-search)
* [如何管理我的连接？](#how-do-i-manage-my-connections)
* [图形连接器的许可证要求和使用期限是什么？](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [如何自定义和配置搜索结果？](#how-do-i-customize-and-configure-search-results)
* [如何从自定义应用程序中搜索我的连接器数据？](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> Microsoft Graph 连接器和 Microsoft Search Api 现已正式推出。 第一次部署将面向为目标版本配置的客户。 如果要在租户中使用 Graph 连接器，用户和管理员必须选择进入 [目标发行版](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)。

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

Microsoft 提供10个图形连接器，我们的生态系统合作伙伴创建了超过100个其他图形连接器。 您还可以生成自己的 Graph 连接器。 

### <a name="graph-connectors-by-microsoft"></a>Microsoft 的图形连接器

您可以使用由 Microsoft 创建的图形连接器连接到以下数据源：

<!---Need to add a few links below when docs exist--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* Azure SQL
* [企业网站](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [文件共享](fileshare-connector.md)
* Oracle (预览) 
* [Salesforce (预览) ](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

[Graph 连接器库](connectors-gallery.md)包含每个图形连接器的简短说明。 如果你已准备好将其中一个数据源连接到你的租户，请务必阅读安装程序 [概述](configure-connector.md) 以及 Microsoft 安装连接器中适用于您的数据源的任何其他文章。

### <a name="graph-connectors-by-our-partners"></a>合作伙伴的图形连接器

[Microsoft Graph 连接器库](connectors-gallery.md)包括合作伙伴创建的每个图形连接器的简短说明以及指向每个合作伙伴网站的链接。 请直接联系每个合作伙伴以了解详细信息。

### <a name="build-your-own-graph-connector"></a>生成自己的图形连接器

如果你计划构建自己的 Graph 连接器，请参阅 microsoft [Graph 中的 Microsoft SEARCH API 概述](https://docs.microsoft.com/graph/search-concept-overview) ，了解详细信息。

## <a name="how-do-i-manage-my-connections"></a>如何管理我的连接？

您可以从[Microsoft 365 管理中心](https://admin.microsoft.com/)的 "[连接器" 选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)管理连接。 有关详细信息，请参阅 [管理您的连接](manage-connector.md) 。

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>图形连接器的许可证要求和使用期限是什么？

你需要组织中的用户的有效 Microsoft 365 或 Office 365 许可证和足够的图形连接器配额，以便在搜索结果中查看连接器中的数据。

若要了解详细信息，请参阅 [许可证要求和定价](licensing.md) 和 [使用条款](terms-of-use.md)。

## <a name="how-do-i-customize-and-configure-search-results"></a>如何自定义和配置搜索结果？

有多种方法可用于自定义和配置搜索结果。 若要了解详细信息，请参阅以下文章：

* [管理垂直领域和结果类型](customize-search-page.md)
* [管理搜索结果布局](customize-results-layout.md)
* [管理结果群集](result-cluster.md)
* [管理自定义筛选器](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>如何从自定义应用程序中搜索我的连接器数据？

对自定义数据编制索引后，开发人员可以 [查询此数据](https://docs.microsoft.com/graph/search-concept-custom-types)。 您可以在任何应用程序中查看数据。 有关详细信息，请参阅 microsoft [Graph 中的 Microsoft SEARCH API 概述](https://docs.microsoft.com/graph/search-concept-overview)。
