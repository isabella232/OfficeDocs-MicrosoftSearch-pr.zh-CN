---
title: 连接器概述
ms.author: mounika.narayanan
author: monaray
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
ms.openlocfilehash: 8b02eadac099d75174fe849f7f2f97c26bf6c3af
ms.sourcegitcommit: ef1eb2bdf31dccd34f0fdc4aa7a0841ebd44f211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2019
ms.locfileid: "39663132"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Microsoft Graph 连接器概述

Microsoft Search 将对所有[Microsoft 365](https://www.microsoft.com/microsoft-365)数据编制索引，使其可供用户搜索。 使用 Microsoft Graph 连接器，您的组织可以将第三方数据编入索引，以显示在 Microsoft 搜索结果中。 第三方数据可以在内部部署或公共或私有云承载。 连接器扩展了可在 Microsoft 365 生产力应用和更广泛的 Microsoft 生态系统中搜索的内容源的类型。

> [!IMPORTANT]
> **免责声明**： microsoft Graph 连接器和 Microsoft 搜索 api （查询和索引）当前处于预览状态。 若要将连接器与 Microsoft 搜索结合使用或构建连接器，必须注册[连接器预览计划](connectors-preview.md)。 若要加入预览计划，请提交[Microsoft Graph 连接器预览注册表单](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)。

## <a name="architecture"></a>体系结构
下面的 Microsoft Graph 平台体系结构图表显示了连接器内容如何通过内容索引传递到[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search)客户端中的用户结果。 本文介绍 Microsoft Graph 连接器数据流过程中的每个关键构建基块。

![图：本地和基于云的数据由 Microsoft Search API 通过连接器进行索引，然后 Microsoft Search service 将结果传递给用户。](media/highlevel-connectors_FINAL.png)

API 为每个数据源实例化一个连接。 然后，API 将对数据进行索引和存储。 已建立的连接将与 Microsoft 搜索进行交互，以便用户可以获取搜索结果。

您可以在 Microsoft 365[管理中心](https://admin.microsoft.com)中配置所有 microsoft 构建的连接器。 管理中心简化了使用简单用户界面配置连接器的工作。

若要创建与数据源的**连接**，管理员需要对数据和整个内容存储库的经过身份验证的访问权限。 数据将送到 graph 连接器服务以进行索引。

## <a name="available-connectors"></a>可用连接器
目前有6个 Microsoft 构建的连接器，我们的生态系统合作伙伴提供了超过100的连接器。

若要从我们的生态系统合作伙伴之一预览连接器，请直接与他们联系。 有关详细信息，请参阅[Microsoft Graph 连接器库](connectors-gallery.md)。

您还可以[生成自己的连接器](https://docs.microsoft.com/graph/search-concept-overview)。

### <a name="connectors-by-microsoft"></a>Microsoft 连接器
Microsoft Graph 连接器预览版本包含6个 Microsoft 构建的连接器。 您可以在[管理中心](https://admin.microsoft.com)中进行设置，并了解如何[设置 Microsoft 构建的连接器](configure-connector.md)。

以下各节提供了这些 Microsoft 构建的连接器的简要说明。 您可以在链接的文章中获取每个连接器的详细信息。

- **[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**。 使用此 Microsoft Graph 连接器，组织中的用户可以搜索存储在 Azure Blob 容器中的文件和内容。 Azure Data Lake Storage Gen2 连接器还会在指定的 Azure Data Lake 存储 Gen2 帐户中为已启用层次结构的文件夹编制索引。
了解有关[Azure Data Lake Storage Gen2 连接器](azure-data-lake-connector.md)的详细信息。

- **企业网站**。 使用此 Microsoft Graph 连接器，组织中的用户可以在任何非 SharePoint 企业网站中搜索页面。
了解有关[企业网站连接器](enterprise-web-connector.md)的详细信息。

- **文件共享**。 使用此 Microsoft Graph 连接器，组织中的用户可以搜索存储在本地 Windows 文件共享上的文件。
了解有关[文件共享连接器](file-share-connector.md)的详细信息。

- **[MediaWiki](https://www.mediawiki.org/wiki/MediaWiki)**。 使用此 Microsoft Graph 连接器，用户可以在您的组织使用 MediaWiki 创建的 wiki 网站上搜索知识库文章。
了解有关[MediaWiki 连接器](mediawiki-connector.md)的详细信息。

- **[MICROSOFT SQL server](https://www.microsoft.com/sql-server/sql-server-2017)**。 使用此 Microsoft Graph 连接器，组织中的用户可以搜索本地 SQL server 数据库中的数据。
了解有关[MICROSOFT SQL server 连接器](MSSQL-connector.md)的详细信息。

- **[ServiceNow](https://www.servicenow.com)**。 使用此 Microsoft Graph 连接器，组织中的用户可以从你的 ServiceNow 实例搜索知识库文章。
了解有关[ServiceNow 连接器](servicenow-connector.md)的详细信息。

### <a name="connectors-from-our-partners"></a>合作伙伴的连接器
我们的生态系统合作伙伴提供了超过100的连接器供预览。 若要从我们的生态系统合作伙伴之一预览连接器，请直接与他们联系。
了解有关来自[Microsoft Graph 连接器库](connectors-gallery.md)中合作伙伴的连接器的详细信息。

### <a name="build-your-own-connector"></a>生成自己的连接器
若要对自定义数据类型或文件编制索引，开发人员可以在[Microsoft Graph](https://developer.microsoft.com/graph/)中创建连接器。 连接器是[创建连接](https://docs.microsoft.com/graph/search-index-manage-connections)并将项目推送到 Microsoft 搜索索引的应用程序。 有关详细信息，请参阅[为 Microsoft Graph 中的应用程序扩展 Microsoft 搜索体验的概述](https://docs.microsoft.com/graph/search-concept-overview)。

### <a name="search-results-with-your-custom-built-connector"></a>使用自定义内置连接器的搜索结果
对自定义数据编制索引后，开发人员可以[查询此数据](https://docs.microsoft.com/graph/search-concept-custom-types)。 您可以在任何应用程序中查看数据。 有关详细信息，请参阅[为 Microsoft Graph 中的应用程序扩展 Microsoft 搜索体验的概述](https://docs.microsoft.com/graph/search-concept-overview)。

## <a name="license-requirements"></a>许可要求
若要在搜索结果中查看连接器中的数据，用户必须具有以下 Microsoft 365 订阅之一：
- <a href="https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans" target="_blank">适用于企业版 E3 或 E5 的 Microsoft 365</a>
- <a href="https://www.microsoft.com/microsoft-365/academic/compare-office-365-education-plans?activetab=tab:primaryr1" target="_blank">Microsoft 365 教育版 A3 或 A5</a>
