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
ms.openlocfilehash: 4bcfb871fabae07270611762d2112a6e72d4762b
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230886"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="e8205-103">Microsoft Graph 连接器概述</span><span class="sxs-lookup"><span data-stu-id="e8205-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="e8205-104">[Microsoft 搜索](./overview-microsoft-search.md)索引所有[Microsoft 365](https://www.microsoft.com/microsoft-365)数据，使其可搜索用户。</span><span class="sxs-lookup"><span data-stu-id="e8205-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="e8205-105">借助 Microsoft Graph连接器，你的组织可以索引第三方数据，以便数据显示在Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="e8205-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="e8205-106">此功能扩展了 Microsoft 365 生产力应用中可搜索的内容源类型以及 Microsoft 更广泛的数据源。</span><span class="sxs-lookup"><span data-stu-id="e8205-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="e8205-107">第三方数据可以本地托管，也可以托管在公有云或私有云中。</span><span class="sxs-lookup"><span data-stu-id="e8205-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="e8205-108">本文旨在帮助管理员Microsoft 365查找可用于回答以下问题的资源：</span><span class="sxs-lookup"><span data-stu-id="e8205-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="e8205-109">哪些数据源可以连接到Microsoft 搜索？</span><span class="sxs-lookup"><span data-stu-id="e8205-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="e8205-110">如何管理连接？</span><span class="sxs-lookup"><span data-stu-id="e8205-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="e8205-111">Microsoft 连接器的许可要求和使用条款是什么Graph？</span><span class="sxs-lookup"><span data-stu-id="e8205-111">What are the license requirements and terms of use for Microsoft Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [<span data-ttu-id="e8205-112">预览功能是什么？</span><span class="sxs-lookup"><span data-stu-id="e8205-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="e8205-113">如何自定义和配置搜索结果？</span><span class="sxs-lookup"><span data-stu-id="e8205-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="e8205-114">如何从自定义应用程序中搜索连接器数据？</span><span class="sxs-lookup"><span data-stu-id="e8205-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="e8205-115">如何自定义搜索结果？</span><span class="sxs-lookup"><span data-stu-id="e8205-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="e8205-116">连接器限制是什么</span><span class="sxs-lookup"><span data-stu-id="e8205-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="e8205-117">Microsoft Graph连接器Microsoft 搜索 API 现已普遍可用。</span><span class="sxs-lookup"><span data-stu-id="e8205-117">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="e8205-118">首次推出将面向针对定向版本配置的客户。</span><span class="sxs-lookup"><span data-stu-id="e8205-118">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="e8205-119">如果要在租户中Graph连接器，用户和管理员必须选择加入[定向发布](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="e8205-119">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide).</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="e8205-120">哪些数据源可以连接到Microsoft 搜索？</span><span class="sxs-lookup"><span data-stu-id="e8205-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="e8205-121">Microsoft 提供了 9 个连接器，我们的生态系统合作伙伴已创建 100 多个连接器。</span><span class="sxs-lookup"><span data-stu-id="e8205-121">Microsoft provides 9 connectors and our ecosystem partners have created over 100 more connectors.</span></span> <span data-ttu-id="e8205-122">您还可以构建您自己的连接器。</span><span class="sxs-lookup"><span data-stu-id="e8205-122">You can also build your own connector.</span></span>

### <a name="microsoft-graph-connectors-by-microsoft"></a><span data-ttu-id="e8205-123">Microsoft Graph连接器</span><span class="sxs-lookup"><span data-stu-id="e8205-123">Microsoft Graph connectors by Microsoft</span></span>

<span data-ttu-id="e8205-124">可以使用 Microsoft 创建的连接器连接到以下数据源：</span><span class="sxs-lookup"><span data-stu-id="e8205-124">You can connect to the following data sources using connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="e8205-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="e8205-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="e8205-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="e8205-126">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="e8205-127">Azure SQL 和 Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8205-127">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="e8205-128">企业网站</span><span class="sxs-lookup"><span data-stu-id="e8205-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="e8205-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="e8205-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="e8205-130">文件共享</span><span class="sxs-lookup"><span data-stu-id="e8205-130">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="e8205-131">Oracle SQL</span><span class="sxs-lookup"><span data-stu-id="e8205-131">Oracle SQL</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="e8205-132">Salesforce （预览版）</span><span class="sxs-lookup"><span data-stu-id="e8205-132">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="e8205-133">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e8205-133">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="e8205-134">[Microsoft Graph 连接器](https://www.microsoft.com/microsoft-search/connectors)库包含其中每个连接器的简要说明。</span><span class="sxs-lookup"><span data-stu-id="e8205-134">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) contains a brief description of each of these connectors.</span></span> <span data-ttu-id="e8205-135">如果已准备好将其中一个数据源连接到租户，请务必阅读安装程序概述以及 Microsoft 安装程序连接器中[](configure-connector.md)适用于数据源的其他任何文章。</span><span class="sxs-lookup"><span data-stu-id="e8205-135">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="microsoft-graph-connectors-by-our-partners"></a><span data-ttu-id="e8205-136">由Graph的 Microsoft 连接器</span><span class="sxs-lookup"><span data-stu-id="e8205-136">Microsoft Graph connectors by our partners</span></span>

<span data-ttu-id="e8205-137">[Microsoft Graph 连接器](https://www.microsoft.com/microsoft-search/connectors)库包括我们的合作伙伴创建的每个连接器的简要说明，以及指向每个合作伙伴网站的链接。</span><span class="sxs-lookup"><span data-stu-id="e8205-137">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) includes a brief description of each of the connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="e8205-138">若要了解更多信息，请直接与每个合作伙伴联系。</span><span class="sxs-lookup"><span data-stu-id="e8205-138">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-microsoft-graph-connector"></a><span data-ttu-id="e8205-139">生成你自己的 Microsoft Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="e8205-139">Build your own Microsoft Graph connector</span></span>

<span data-ttu-id="e8205-140">如果愿意，可以生成自己的连接器。</span><span class="sxs-lookup"><span data-stu-id="e8205-140">You can build your own connector if you prefer.</span></span> <span data-ttu-id="e8205-141">有关生成连接器的信息，请参阅生成首个自定义 Microsoft Graph[连接器](/graph/connecting-external-content-build-quickstart)。</span><span class="sxs-lookup"><span data-stu-id="e8205-141">For more information on building connectors, see  [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="e8205-142">如何管理连接？</span><span class="sxs-lookup"><span data-stu-id="e8205-142">How do I manage my connections?</span></span>

<span data-ttu-id="e8205-143">可以从"连接器"选项卡[中的"连接器"选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)[Microsoft 365 管理中心。](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="e8205-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="e8205-144">有关管理连接的信息，请参阅： [管理连接](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="e8205-144">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a><span data-ttu-id="e8205-145">连接器的许可证要求和使用条款是什么？</span><span class="sxs-lookup"><span data-stu-id="e8205-145">What are the license requirements and terms of use for connectors?</span></span>

<span data-ttu-id="e8205-146">您需要一个有效的Microsoft 365或Office 365许可证和足够的连接器配额，以便贵组织的用户能够查看搜索结果中的连接器数据。</span><span class="sxs-lookup"><span data-stu-id="e8205-146">You need a valid Microsoft 365 or Office 365 license and sufficient connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="e8205-147">若要了解更多信息，请参阅许可证[要求和定价](licensing.md)[和使用条款](terms-of-use.md)。</span><span class="sxs-lookup"><span data-stu-id="e8205-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="e8205-148">预览功能是什么？</span><span class="sxs-lookup"><span data-stu-id="e8205-148">What are the preview features?</span></span>

<span data-ttu-id="e8205-149">尽管 Microsoft Graph连接器和 Microsoft 搜索 API 现已普遍可用，但预览版中有几个功能。</span><span class="sxs-lookup"><span data-stu-id="e8205-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="e8205-150">预览版中的连接器和功能集包括：</span><span class="sxs-lookup"><span data-stu-id="e8205-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="e8205-151">Azure DevOps连接器</span><span class="sxs-lookup"><span data-stu-id="e8205-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="e8205-152">Salesforce 连接器</span><span class="sxs-lookup"><span data-stu-id="e8205-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="e8205-153">具有使用源 ACL 的搜索权限的[ServiceNow](servicenow-connector.md)连接器</span><span class="sxs-lookup"><span data-stu-id="e8205-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="e8205-154">管理结果群集</span><span class="sxs-lookup"><span data-stu-id="e8205-154">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="e8205-155">垂直连接中的多个连接</span><span class="sxs-lookup"><span data-stu-id="e8205-155">Multiple connections in a vertical</span></span>](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="e8205-156">如何自定义和配置搜索结果？</span><span class="sxs-lookup"><span data-stu-id="e8205-156">How do I customize and configure search results?</span></span>

<span data-ttu-id="e8205-157">有很多方法可以自定义和配置搜索结果。</span><span class="sxs-lookup"><span data-stu-id="e8205-157">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="e8205-158">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e8205-158">See the following articles to learn more:</span></span>

* [<span data-ttu-id="e8205-159">管理垂直领域和结果类型</span><span class="sxs-lookup"><span data-stu-id="e8205-159">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="e8205-160">管理搜索结果布局</span><span class="sxs-lookup"><span data-stu-id="e8205-160">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="e8205-161">管理结果群集</span><span class="sxs-lookup"><span data-stu-id="e8205-161">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="e8205-162">管理自定义筛选器</span><span class="sxs-lookup"><span data-stu-id="e8205-162">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="e8205-163">如何从自定义应用程序中搜索连接器数据？</span><span class="sxs-lookup"><span data-stu-id="e8205-163">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="e8205-164">对自定义数据编制索引后，开发人员 [可以查询此数据](/graph/search-concept-custom-types)。</span><span class="sxs-lookup"><span data-stu-id="e8205-164">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="e8205-165">可以在任何应用程序中查看数据。</span><span class="sxs-lookup"><span data-stu-id="e8205-165">You can view your data in any application.</span></span> <span data-ttu-id="e8205-166">有关详细信息，请参阅 Microsoft Graph[中的 Microsoft 搜索 API 概述](/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="e8205-166">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="e8205-167">如何自定义搜索结果？</span><span class="sxs-lookup"><span data-stu-id="e8205-167">How do I customize search results?</span></span>

<span data-ttu-id="e8205-168">下一步是按照本文中的建议自定义搜索结果，如何[自定义和配置搜索结果？。](#how-do-i-customize-and-configure-search-results)</span><span class="sxs-lookup"><span data-stu-id="e8205-168">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="e8205-169">若要了解有关自定义搜索结果的信息，请参阅自定义 [搜索结果页面](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e8205-169">To learn more about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="e8205-170">连接器限制是什么？</span><span class="sxs-lookup"><span data-stu-id="e8205-170">What are the connector limitations?</span></span>

* <span data-ttu-id="e8205-171">发布 **Microsoft** 构建的连接器时，可能需要几分钟时间才能创建连接。</span><span class="sxs-lookup"><span data-stu-id="e8205-171">When you **publish** a Microsoft-built connector, it can take a few minutes for the connection to be created.</span></span> <span data-ttu-id="e8205-172">在此期间，连接的状态将显示为"挂起"。</span><span class="sxs-lookup"><span data-stu-id="e8205-172">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="e8205-173">以大约每秒四个项目的速度限制 Ingestion 吞吐量。</span><span class="sxs-lookup"><span data-stu-id="e8205-173">Ingestion throughput is throttled at approximately four items per second.</span></span>

* <span data-ttu-id="e8205-174">不支持架构更新。</span><span class="sxs-lookup"><span data-stu-id="e8205-174">There is no support for schema updates.</span></span> <span data-ttu-id="e8205-175">创建连接设置后，无法更新架构。</span><span class="sxs-lookup"><span data-stu-id="e8205-175">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="e8205-176">只能删除并重新创建连接。</span><span class="sxs-lookup"><span data-stu-id="e8205-176">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="e8205-177">存在连接限制。</span><span class="sxs-lookup"><span data-stu-id="e8205-177">There is a connection limit.</span></span> <span data-ttu-id="e8205-178">每个租户可以创建最多 10 个连接。</span><span class="sxs-lookup"><span data-stu-id="e8205-178">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="e8205-179">创建连接后，不能编辑或更改连接。</span><span class="sxs-lookup"><span data-stu-id="e8205-179">You cannot edit or change a connection after it has been created.</span></span> <span data-ttu-id="e8205-180">如果需要更改任何详细信息，则必须删除并重新创建连接。</span><span class="sxs-lookup"><span data-stu-id="e8205-180">If you need to change any details, you must delete and recreate the connection.</span></span>
