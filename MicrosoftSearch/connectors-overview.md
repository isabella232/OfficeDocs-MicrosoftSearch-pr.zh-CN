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
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="584a7-103">Microsoft Graph 连接器概述</span><span class="sxs-lookup"><span data-stu-id="584a7-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="584a7-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) 将对所有 [Microsoft 365](https://www.microsoft.com/microsoft-365) 数据编制索引，使其可供用户搜索。</span><span class="sxs-lookup"><span data-stu-id="584a7-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="584a7-105">使用 Microsoft Graph 连接器，您的组织可以对第三方数据编制索引，使其显示在 Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="584a7-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="584a7-106">这将扩展在 Microsoft 365 生产力应用和更广泛的 Microsoft 生态系统中可搜索的内容源的类型。</span><span class="sxs-lookup"><span data-stu-id="584a7-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="584a7-107">第三方数据可以在内部部署或公共或私有云承载。</span><span class="sxs-lookup"><span data-stu-id="584a7-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="584a7-108">本文的其余部分旨在帮助 Microsoft 365 管理员找到 avaiable 的资源，以回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="584a7-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are avaiable to answer the following questions:</span></span>

* [<span data-ttu-id="584a7-109">哪些数据源可以连接到 Microsoft 搜索？</span><span class="sxs-lookup"><span data-stu-id="584a7-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="584a7-110">如何管理我的连接？</span><span class="sxs-lookup"><span data-stu-id="584a7-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="584a7-111">图形连接器的许可证要求和使用期限是什么？</span><span class="sxs-lookup"><span data-stu-id="584a7-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="584a7-112">如何自定义和配置搜索结果？</span><span class="sxs-lookup"><span data-stu-id="584a7-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="584a7-113">如何从自定义应用程序中搜索我的连接器数据？</span><span class="sxs-lookup"><span data-stu-id="584a7-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="584a7-114">Microsoft Graph 连接器和 Microsoft Search Api 现已正式推出。</span><span class="sxs-lookup"><span data-stu-id="584a7-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="584a7-115">第一次部署将面向为目标版本配置的客户。</span><span class="sxs-lookup"><span data-stu-id="584a7-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="584a7-116">如果要在租户中使用 Graph 连接器，用户和管理员必须选择进入 [目标发行版](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="584a7-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="584a7-117">哪些数据源可以连接到 Microsoft 搜索？</span><span class="sxs-lookup"><span data-stu-id="584a7-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="584a7-118">Microsoft 提供10个图形连接器，我们的生态系统合作伙伴创建了超过100个其他图形连接器。</span><span class="sxs-lookup"><span data-stu-id="584a7-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="584a7-119">您还可以生成自己的 Graph 连接器。</span><span class="sxs-lookup"><span data-stu-id="584a7-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="584a7-120">Microsoft 的图形连接器</span><span class="sxs-lookup"><span data-stu-id="584a7-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="584a7-121">您可以使用由 Microsoft 创建的图形连接器连接到以下数据源：</span><span class="sxs-lookup"><span data-stu-id="584a7-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="584a7-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="584a7-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="584a7-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="584a7-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="584a7-124">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="584a7-124">Azure SQL</span></span>
* [<span data-ttu-id="584a7-125">企业网站</span><span class="sxs-lookup"><span data-stu-id="584a7-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="584a7-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="584a7-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="584a7-127">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="584a7-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="584a7-128">文件共享</span><span class="sxs-lookup"><span data-stu-id="584a7-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="584a7-129">Oracle (预览) </span><span class="sxs-lookup"><span data-stu-id="584a7-129">Oracle (preview)</span></span>
* [<span data-ttu-id="584a7-130">Salesforce (预览) </span><span class="sxs-lookup"><span data-stu-id="584a7-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="584a7-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="584a7-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="584a7-132">[Graph 连接器库](connectors-gallery.md)包含每个图形连接器的简短说明。</span><span class="sxs-lookup"><span data-stu-id="584a7-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="584a7-133">如果你已准备好将其中一个数据源连接到你的租户，请务必阅读安装程序 [概述](configure-connector.md) 以及 Microsoft 安装连接器中适用于您的数据源的任何其他文章。</span><span class="sxs-lookup"><span data-stu-id="584a7-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="584a7-134">合作伙伴的图形连接器</span><span class="sxs-lookup"><span data-stu-id="584a7-134">Graph connectors by our partners</span></span>

<span data-ttu-id="584a7-135">[Microsoft Graph 连接器库](connectors-gallery.md)包括合作伙伴创建的每个图形连接器的简短说明以及指向每个合作伙伴网站的链接。</span><span class="sxs-lookup"><span data-stu-id="584a7-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="584a7-136">请直接联系每个合作伙伴以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="584a7-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="584a7-137">生成自己的图形连接器</span><span class="sxs-lookup"><span data-stu-id="584a7-137">Build your own Graph connector</span></span>

<span data-ttu-id="584a7-138">如果你计划构建自己的 Graph 连接器，请参阅 microsoft [Graph 中的 Microsoft SEARCH API 概述](https://docs.microsoft.com/graph/search-concept-overview) ，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="584a7-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="584a7-139">如何管理我的连接？</span><span class="sxs-lookup"><span data-stu-id="584a7-139">How do I manage my connections?</span></span>

<span data-ttu-id="584a7-140">您可以从[Microsoft 365 管理中心](https://admin.microsoft.com/)的 "[连接器" 选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)管理连接。</span><span class="sxs-lookup"><span data-stu-id="584a7-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="584a7-141">有关详细信息，请参阅 [管理您的连接](manage-connector.md) 。</span><span class="sxs-lookup"><span data-stu-id="584a7-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="584a7-142">图形连接器的许可证要求和使用期限是什么？</span><span class="sxs-lookup"><span data-stu-id="584a7-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="584a7-143">你需要组织中的用户的有效 Microsoft 365 或 Office 365 许可证和足够的图形连接器配额，以便在搜索结果中查看连接器中的数据。</span><span class="sxs-lookup"><span data-stu-id="584a7-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="584a7-144">若要了解详细信息，请参阅 [许可证要求和定价](licensing.md) 和 [使用条款](terms-of-use.md)。</span><span class="sxs-lookup"><span data-stu-id="584a7-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="584a7-145">如何自定义和配置搜索结果？</span><span class="sxs-lookup"><span data-stu-id="584a7-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="584a7-146">有多种方法可用于自定义和配置搜索结果。</span><span class="sxs-lookup"><span data-stu-id="584a7-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="584a7-147">若要了解详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="584a7-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="584a7-148">管理垂直领域和结果类型</span><span class="sxs-lookup"><span data-stu-id="584a7-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="584a7-149">管理搜索结果布局</span><span class="sxs-lookup"><span data-stu-id="584a7-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="584a7-150">管理结果群集</span><span class="sxs-lookup"><span data-stu-id="584a7-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="584a7-151">管理自定义筛选器</span><span class="sxs-lookup"><span data-stu-id="584a7-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="584a7-152">如何从自定义应用程序中搜索我的连接器数据？</span><span class="sxs-lookup"><span data-stu-id="584a7-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="584a7-153">对自定义数据编制索引后，开发人员可以 [查询此数据](https://docs.microsoft.com/graph/search-concept-custom-types)。</span><span class="sxs-lookup"><span data-stu-id="584a7-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="584a7-154">您可以在任何应用程序中查看数据。</span><span class="sxs-lookup"><span data-stu-id="584a7-154">You can view your data in any application.</span></span> <span data-ttu-id="584a7-155">有关详细信息，请参阅 microsoft [Graph 中的 Microsoft SEARCH API 概述](https://docs.microsoft.com/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="584a7-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>
