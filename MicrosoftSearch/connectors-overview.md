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
ms.openlocfilehash: d20c576c92c0ec2d794fc6f8fd21c829e468c086
ms.sourcegitcommit: 995ce23d4e47a3456a02dba0ba7c9cd0de64528a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919480"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="71246-103">Microsoft Graph 连接器概述</span><span class="sxs-lookup"><span data-stu-id="71246-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="71246-104">Microsoft Search 将对所有 [Microsoft 365](https://www.microsoft.com/microsoft-365) 数据编制索引，使其可供用户搜索。</span><span class="sxs-lookup"><span data-stu-id="71246-104">Microsoft Search indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="71246-105">使用 Microsoft Graph 连接器，你的组织可以将第三方数据编入索引，以显示在 Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="71246-105">With Microsoft Graph connectors, your organization can index third-party data to appear in Microsoft Search results.</span></span> <span data-ttu-id="71246-106">第三方数据可以在内部部署或公共或私有云承载。</span><span class="sxs-lookup"><span data-stu-id="71246-106">The third-party data can be hosted on-premises or in the public or private clouds.</span></span> <span data-ttu-id="71246-107">连接器扩展了可在 Microsoft 365 生产力应用和更广泛的 Microsoft 生态系统中搜索的内容源的类型。</span><span class="sxs-lookup"><span data-stu-id="71246-107">Connectors expand the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71246-108">**免责声明** ： microsoft Graph 连接器和 Microsoft Search api (查询和索引) 当前处于预览状态，可用于租户在目标版本中。</span><span class="sxs-lookup"><span data-stu-id="71246-108">**DISCLAIMER** : Microsoft Graph connectors and Microsoft Search APIs (query and index) are currently in preview status available for tenants in Targeted release.</span></span> <span data-ttu-id="71246-109">若要将连接器与 Microsoft 搜索配合使用或构建连接器，请选择进入 [目标版本](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="71246-109">To use connectors with Microsoft Search or to build connectors, opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span> <span data-ttu-id="71246-110">若要了解有关预览的详细信息，请参阅 [连接器预览计划](connectors-preview.md)。</span><span class="sxs-lookup"><span data-stu-id="71246-110">To learn more about the preview, see [connectors preview program](connectors-preview.md).</span></span>

## <a name="architecture"></a><span data-ttu-id="71246-111">体系结构</span><span class="sxs-lookup"><span data-stu-id="71246-111">Architecture</span></span>

<span data-ttu-id="71246-112">下面的 Microsoft Graph 平台体系结构图表显示了连接器内容如何通过内容索引传递到 [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) 客户端中的用户结果。</span><span class="sxs-lookup"><span data-stu-id="71246-112">The following architectural diagram of the Microsoft Graph platform shows how connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients.</span></span> <span data-ttu-id="71246-113">本文介绍 Microsoft Graph 连接器数据流过程中的每个关键构建基块。</span><span class="sxs-lookup"><span data-stu-id="71246-113">This article explains each of the key building blocks in the Microsoft Graph connectors data flow process.</span></span>

![图：本地和基于云的数据由 Microsoft Search API 通过连接器进行索引，然后 Microsoft Search service 将结果传递给用户。](media/highlevel-connectors_FINAL.png)

<span data-ttu-id="71246-115">API 为每个数据源实例化一个连接。</span><span class="sxs-lookup"><span data-stu-id="71246-115">The API instantiates one connection per data source.</span></span> <span data-ttu-id="71246-116">然后，API 将对数据进行索引和存储。</span><span class="sxs-lookup"><span data-stu-id="71246-116">Then the API indexes and stores the data.</span></span> <span data-ttu-id="71246-117">已建立的连接将与 Microsoft 搜索进行交互，以便用户可以获取搜索结果。</span><span class="sxs-lookup"><span data-stu-id="71246-117">Established connections interact with Microsoft Search, so users can get search results.</span></span>

<span data-ttu-id="71246-118">您可以在 Microsoft 365 [管理中心](https://admin.microsoft.com)中配置所有 microsoft 构建的连接器。</span><span class="sxs-lookup"><span data-stu-id="71246-118">You can configure all the Microsoft-built connectors in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="71246-119">管理中心简化了使用简单用户界面配置连接器的工作。</span><span class="sxs-lookup"><span data-stu-id="71246-119">The admin center simplifies configuring your connector with a simple user interface.</span></span>

<span data-ttu-id="71246-120">若要创建与数据源的 **连接** ，管理员需要对数据和整个内容存储库的经过身份验证的访问权限。</span><span class="sxs-lookup"><span data-stu-id="71246-120">To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository.</span></span> <span data-ttu-id="71246-121">数据将送到 graph 连接器服务以进行索引。</span><span class="sxs-lookup"><span data-stu-id="71246-121">The data is fed to the graph connector service for indexing.</span></span>

## <a name="available-connectors"></a><span data-ttu-id="71246-122">可用连接器</span><span class="sxs-lookup"><span data-stu-id="71246-122">Available connectors</span></span>

<span data-ttu-id="71246-123">目前有6个 Microsoft 构建的连接器，我们的生态系统合作伙伴提供了超过100的连接器。</span><span class="sxs-lookup"><span data-stu-id="71246-123">There are currently 6 Microsoft-built connectors, and over 100 connectors are available from our ecosystem partners.</span></span>

<span data-ttu-id="71246-124">若要从我们的生态系统合作伙伴之一预览连接器，请直接与他们联系。</span><span class="sxs-lookup"><span data-stu-id="71246-124">To preview connectors from one of our ecosystem partners, contact them directly.</span></span> <span data-ttu-id="71246-125">有关详细信息，请参阅 [Microsoft Graph 连接器库](connectors-gallery.md)。</span><span class="sxs-lookup"><span data-stu-id="71246-125">For more information, see the [Microsoft Graph connectors gallery](connectors-gallery.md).</span></span>

<span data-ttu-id="71246-126">您还可以 [生成自己的连接器](https://docs.microsoft.com/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="71246-126">You can also [build your own connector](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

### <a name="connectors-by-microsoft"></a><span data-ttu-id="71246-127">由 Microsoft 提供的连接器</span><span class="sxs-lookup"><span data-stu-id="71246-127">Connectors by Microsoft</span></span>

<span data-ttu-id="71246-128">Microsoft Graph 连接器预览版本包含6个 Microsoft 构建的连接器。</span><span class="sxs-lookup"><span data-stu-id="71246-128">The Microsoft Graph connectors preview release includes 6 Microsoft-built connectors.</span></span> <span data-ttu-id="71246-129">您可以在 [管理中心](https://admin.microsoft.com) 中进行设置，并了解如何 [设置 Microsoft 构建的连接器](configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="71246-129">You can set them up in the [admin center](https://admin.microsoft.com) and learn how to [Set up your Microsoft-built connector](configure-connector.md).</span></span>

<span data-ttu-id="71246-130">以下各节提供了这些 Microsoft 构建的连接器的简要说明。</span><span class="sxs-lookup"><span data-stu-id="71246-130">The following sections provide brief descriptions for these Microsoft-built connectors.</span></span> <span data-ttu-id="71246-131">您可以在链接的文章中获取每个连接器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71246-131">You can get more information in the linked articles for each connector.</span></span>

- <span data-ttu-id="71246-132">**[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)** 。</span><span class="sxs-lookup"><span data-stu-id="71246-132">**[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**.</span></span> <span data-ttu-id="71246-133">使用此 Microsoft Graph 连接器，组织中的用户可以搜索存储在 Azure Blob 容器中的文件和内容。</span><span class="sxs-lookup"><span data-stu-id="71246-133">With this Microsoft Graph connector, users in your organization can search for files and content stored in Azure Blob containers.</span></span> <span data-ttu-id="71246-134">Azure Data Lake Storage Gen2 连接器还会在指定的 Azure Data Lake 存储 Gen2 帐户中为已启用层次结构的文件夹编制索引。</span><span class="sxs-lookup"><span data-stu-id="71246-134">The Azure Data Lake Storage Gen2 connector also indexes hierarchy-enabled folders in Azure Data Lake Storage Gen2 accounts that you specify.</span></span>
<span data-ttu-id="71246-135">了解有关 [Azure Data Lake Storage Gen2 连接器](azure-data-lake-connector.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71246-135">Learn more about the [Azure Data Lake Storage Gen2 connector](azure-data-lake-connector.md).</span></span>

- <span data-ttu-id="71246-136">**[Azure DevOps](https://azure.microsoft.com/services/devops)** 。</span><span class="sxs-lookup"><span data-stu-id="71246-136">**[Azure DevOps](https://azure.microsoft.com/services/devops)**.</span></span> <span data-ttu-id="71246-137">使用此 Microsoft Graph 连接器，组织中的用户可以从 Azure DevOps 实例中搜索工作项。</span><span class="sxs-lookup"><span data-stu-id="71246-137">With this Microsoft Graph connector, users in your organization can search for work items from your Azure DevOps instance.</span></span>
<span data-ttu-id="71246-138">了解有关 [Azure DevOps 连接器](azure-devops-connector.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71246-138">Learn more about the [Azure DevOps connector](azure-devops-connector.md).</span></span>

- <span data-ttu-id="71246-139">**[AZURE SQL](https://azure.microsoft.com/services/sql-database)** 。</span><span class="sxs-lookup"><span data-stu-id="71246-139">**[Azure SQL](https://azure.microsoft.com/services/sql-database)**.</span></span> <span data-ttu-id="71246-140">使用此 Microsoft Graph 连接器，组织中的用户可以从 Azure SQL 数据库中搜索数据。</span><span class="sxs-lookup"><span data-stu-id="71246-140">With this Microsoft Graph connector, users in your organization can search for data from your Azure SQL database.</span></span>
<span data-ttu-id="71246-141">了解有关 [AZURE SQL 连接器](MSSQL-connector.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71246-141">Learn more about the [Azure SQL connector](MSSQL-connector.md).</span></span>

- <span data-ttu-id="71246-142">**企业网站** 。</span><span class="sxs-lookup"><span data-stu-id="71246-142">**Enterprise websites**.</span></span> <span data-ttu-id="71246-143">使用此 Microsoft Graph 连接器，组织中的用户可以在任何非 SharePoint 企业网站中搜索页面。</span><span class="sxs-lookup"><span data-stu-id="71246-143">With this Microsoft Graph connector, users in your organization can search over pages in any non-SharePoint enterprise website.</span></span>
<span data-ttu-id="71246-144">了解有关 [企业网站连接器](enterprise-web-connector.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71246-144">Learn more about the [Enterprise websites connector](enterprise-web-connector.md).</span></span>

- <span data-ttu-id="71246-145">**[MediaWiki](https://www.mediawiki.org/wiki/MediaWiki)** 。</span><span class="sxs-lookup"><span data-stu-id="71246-145">**[MediaWiki](https://www.mediawiki.org/wiki/MediaWiki)**.</span></span> <span data-ttu-id="71246-146">使用此 Microsoft Graph 连接器，用户可以在您的组织使用 MediaWiki 创建的 wiki 网站上搜索知识库文章。</span><span class="sxs-lookup"><span data-stu-id="71246-146">With this Microsoft Graph connector, users can search for knowledge-base articles on wiki sites your organization creates with MediaWiki.</span></span>
<span data-ttu-id="71246-147">了解有关 [MediaWiki 连接器](mediawiki-connector.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71246-147">Learn more about the [MediaWiki connector](mediawiki-connector.md).</span></span>

- <span data-ttu-id="71246-148">**[MICROSOFT SQL server](https://www.microsoft.com/sql-server/sql-server-2017)** 。</span><span class="sxs-lookup"><span data-stu-id="71246-148">**[Microsoft SQL server](https://www.microsoft.com/sql-server/sql-server-2017)**.</span></span> <span data-ttu-id="71246-149">使用此 Microsoft Graph 连接器，组织中的用户可以搜索本地 SQL server 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="71246-149">With this Microsoft Graph connector, users in your organization can search for data in on-premises SQL server databases.</span></span>
<span data-ttu-id="71246-150">了解有关 [MICROSOFT SQL server 连接器](MSSQL-connector.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71246-150">Learn more about the [Microsoft SQL server connector](MSSQL-connector.md).</span></span>

- <span data-ttu-id="71246-151">**[ServiceNow](https://www.servicenow.com)** 。</span><span class="sxs-lookup"><span data-stu-id="71246-151">**[ServiceNow](https://www.servicenow.com)**.</span></span> <span data-ttu-id="71246-152">使用此 Microsoft Graph 连接器，组织中的用户可以从你的 ServiceNow 实例搜索知识库文章。</span><span class="sxs-lookup"><span data-stu-id="71246-152">With this Microsoft Graph connector, users in your organization can search for knowledge-base articles from your ServiceNow instance.</span></span>
<span data-ttu-id="71246-153">了解有关 [ServiceNow 连接器](servicenow-connector.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71246-153">Learn more about the [ServiceNow connector](servicenow-connector.md).</span></span>

### <a name="connectors-from-our-partners"></a><span data-ttu-id="71246-154">合作伙伴的连接器</span><span class="sxs-lookup"><span data-stu-id="71246-154">Connectors from our partners</span></span>

<span data-ttu-id="71246-155">我们的生态系统合作伙伴提供了超过100的连接器供预览。</span><span class="sxs-lookup"><span data-stu-id="71246-155">There are over 100 connectors available for preview from our ecosystem partners.</span></span> <span data-ttu-id="71246-156">若要从我们的生态系统合作伙伴之一预览连接器，请直接与他们联系。</span><span class="sxs-lookup"><span data-stu-id="71246-156">To preview connectors from one of our ecosystem partners, contact them directly.</span></span>
<span data-ttu-id="71246-157">了解有关来自 [Microsoft Graph 连接器库](connectors-gallery.md)中合作伙伴的连接器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71246-157">Learn more about connectors from our partners in the [Microsoft Graph connectors gallery](connectors-gallery.md).</span></span>

### <a name="build-your-own-connector"></a><span data-ttu-id="71246-158">生成自己的连接器</span><span class="sxs-lookup"><span data-stu-id="71246-158">Build your own connector</span></span>

<span data-ttu-id="71246-159">若要对自定义数据类型或文件编制索引，开发人员可以在 [Microsoft Graph](https://developer.microsoft.com/graph/)中创建连接器。</span><span class="sxs-lookup"><span data-stu-id="71246-159">To index custom data types or files, developers can create connectors in [Microsoft Graph](https://developer.microsoft.com/graph/).</span></span> <span data-ttu-id="71246-160">连接器是 [创建连接](https://docs.microsoft.com/graph/search-index-manage-connections) 并将项目推送到 Microsoft 搜索索引的应用程序。</span><span class="sxs-lookup"><span data-stu-id="71246-160">A connector is an application that [creates a connection](https://docs.microsoft.com/graph/search-index-manage-connections) and pushes items into the Microsoft Search index.</span></span> <span data-ttu-id="71246-161">有关详细信息，请参阅 [为 Microsoft Graph 中的应用程序扩展 Microsoft 搜索体验的概述](https://docs.microsoft.com/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="71246-161">For more information, see the [Overview for extending the Microsoft Search experience for apps on Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

### <a name="search-results-with-your-custom-built-connector"></a><span data-ttu-id="71246-162">使用自定义内置连接器的搜索结果</span><span class="sxs-lookup"><span data-stu-id="71246-162">Search results with your custom-built connector</span></span>

<span data-ttu-id="71246-163">对自定义数据编制索引后，开发人员可以 [查询此数据](https://docs.microsoft.com/graph/search-concept-custom-types)。</span><span class="sxs-lookup"><span data-stu-id="71246-163">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="71246-164">您可以在任何应用程序中查看数据。</span><span class="sxs-lookup"><span data-stu-id="71246-164">You can view your data in any application.</span></span> <span data-ttu-id="71246-165">有关详细信息，请参阅 [为 Microsoft Graph 中的应用程序扩展 Microsoft 搜索体验的概述](https://docs.microsoft.com/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="71246-165">For more information, see the [Overview for extending the Microsoft Search experience for apps on Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="license-requirements"></a><span data-ttu-id="71246-166">许可要求</span><span class="sxs-lookup"><span data-stu-id="71246-166">License requirements</span></span>

<span data-ttu-id="71246-167">你需要组织中的用户的有效 Microsoft 365 或 Office 365 许可证和足够的图形连接器配额，以便在搜索结果中查看连接器中的数据。</span><span class="sxs-lookup"><span data-stu-id="71246-167">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="71246-168">若要了解详细信息，请参阅 [许可证要求和定价](licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="71246-168">To learn more, see [License requirements and pricing](licensing.md).</span></span>