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
ms.openlocfilehash: a45a007bbb2774caaaac90fc1549c8ba634b0580
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905947"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="5b0fd-103">Microsoft Graph 连接器概述</span><span class="sxs-lookup"><span data-stu-id="5b0fd-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="5b0fd-104">[Microsoft 搜索](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) 会索引 [所有 Microsoft 365](https://www.microsoft.com/microsoft-365) 数据，使其可搜索用户。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="5b0fd-105">借助 Microsoft Graph 连接器，组织可以索引第三方数据，以便数据显示在 Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="5b0fd-106">这扩展了在 Microsoft 365 生产力应用和更广泛的 Microsoft 生态系统中可搜索的内容源类型。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="5b0fd-107">第三方数据可以托管在本地或公有云或私有云中。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="5b0fd-108">本文的其余部分旨在帮助 Microsoft 365 管理员找到可用于回答以下问题的资源：</span><span class="sxs-lookup"><span data-stu-id="5b0fd-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="5b0fd-109">哪些数据源可以连接到 Microsoft 搜索？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="5b0fd-110">如何管理连接？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="5b0fd-111">Graph 连接器的许可证要求和使用条款是什么？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="5b0fd-112">预览功能是什么？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="5b0fd-113">如何自定义和配置搜索结果？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="5b0fd-114">如何从自定义应用程序中搜索连接器数据？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="5b0fd-115">Microsoft Graph 连接器和 Microsoft 搜索 API 现已普遍可用。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-115">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="5b0fd-116">第一次推出计划持续到 2021 年 2 月。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-116">The first rollout is scheduled to last until February 2021.</span></span> <span data-ttu-id="5b0fd-117">在此之前，只有已选择加入定向发布的租户和用户才能使用[](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)Graph 连接器。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-117">Until then, only tenants and users who have opted into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) will be able to use Graph connectors.</span></span> <span data-ttu-id="5b0fd-118">在向所有租户推出完成后，连接器内容的索引配额使用率将受计费限制。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-118">Upon rollout completion to all tenants, index quota utilization from connectors content will become subject to billing.</span></span> <span data-ttu-id="5b0fd-119">有关详细信息 [，请参阅许可要求和](licensing.md) 定价。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-119">See [Licensing requirements and pricing](licensing.md) for more information.</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="5b0fd-120">哪些数据源可以连接到 Microsoft 搜索？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="5b0fd-121">Microsoft 提供了 10 个 Graph 连接器，我们的生态系统合作伙伴已创建 100 多个其他 Graph 连接器。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-121">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="5b0fd-122">还可以生成自己的 Graph 连接器。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-122">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="5b0fd-123">Microsoft 的图表连接器</span><span class="sxs-lookup"><span data-stu-id="5b0fd-123">Graph connectors by Microsoft</span></span>

<span data-ttu-id="5b0fd-124">可以使用 Microsoft 创建的 Graph 连接器连接到以下数据源：</span><span class="sxs-lookup"><span data-stu-id="5b0fd-124">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="5b0fd-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="5b0fd-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="5b0fd-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="5b0fd-126">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="5b0fd-127">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="5b0fd-127">Azure SQL</span></span>
* [<span data-ttu-id="5b0fd-128">企业网站</span><span class="sxs-lookup"><span data-stu-id="5b0fd-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="5b0fd-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="5b0fd-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="5b0fd-130">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b0fd-130">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="5b0fd-131">文件共享</span><span class="sxs-lookup"><span data-stu-id="5b0fd-131">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="5b0fd-132">Oracle (预览) </span><span class="sxs-lookup"><span data-stu-id="5b0fd-132">Oracle (preview)</span></span>
* [<span data-ttu-id="5b0fd-133">Salesforce （预览版）</span><span class="sxs-lookup"><span data-stu-id="5b0fd-133">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="5b0fd-134">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="5b0fd-134">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="5b0fd-135">[Graph 连接器库](connectors-gallery.md)包含每个 Graph 连接器的简短说明。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-135">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="5b0fd-136">如果已准备好将其中一个数据源连接到租户，请务必阅读安装程序概述以及 Microsoft 安装程序连接器[](configure-connector.md)中适用于数据源的其他任何文章。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-136">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="5b0fd-137">合作伙伴的图形连接器</span><span class="sxs-lookup"><span data-stu-id="5b0fd-137">Graph connectors by our partners</span></span>

<span data-ttu-id="5b0fd-138">[Microsoft Graph 连接器库](connectors-gallery.md)包括合作伙伴创建的每个 Graph 连接器的简要说明以及指向每个合作伙伴网站的链接。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-138">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="5b0fd-139">请直接与每个合作伙伴联系以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-139">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="5b0fd-140">生成你自己的 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="5b0fd-140">Build your own Graph connector</span></span>

<span data-ttu-id="5b0fd-141">如果计划构建自己的 Graph 连接器，请参阅 Microsoft Graph 中的 [Microsoft 搜索 API](https://docs.microsoft.com/graph/search-concept-overview) 概述，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-141">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="5b0fd-142">如何管理连接？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-142">How do I manage my connections?</span></span>

<span data-ttu-id="5b0fd-143">可以从[Microsoft 365](https://admin.microsoft.com/)管理中心中的"连接器"选项卡管理连接。 [](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)</span><span class="sxs-lookup"><span data-stu-id="5b0fd-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="5b0fd-144">有关详细信息 [，请参阅"管理](manage-connector.md) 连接"。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-144">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="5b0fd-145">Graph 连接器的许可证要求和使用条款是什么？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-145">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="5b0fd-146">你需要有效的 Microsoft 365 或 Office 365 许可证和足够的 Graph 连接器配额，以便贵组织的用户能够查看搜索结果中连接器的数据。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-146">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="5b0fd-147">若要了解更多信息，请参阅[许可证要求、定价](licensing.md)[和使用条款](terms-of-use.md)。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="5b0fd-148">预览功能是什么？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-148">What are the preview features?</span></span>

<span data-ttu-id="5b0fd-149">尽管 Microsoft Graph 连接器和 Microsoft 搜索 API 现已普遍可用，但有几个功能是预览版。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="5b0fd-150">预览版中的连接器和功能集包括：</span><span class="sxs-lookup"><span data-stu-id="5b0fd-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="5b0fd-151">Azure DevOps 连接器</span><span class="sxs-lookup"><span data-stu-id="5b0fd-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="5b0fd-152">Salesforce 连接器</span><span class="sxs-lookup"><span data-stu-id="5b0fd-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="5b0fd-153">具有使用源 ACL 的搜索权限的[ServiceNow](servicenow-connector.md)连接器</span><span class="sxs-lookup"><span data-stu-id="5b0fd-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="5b0fd-154">管理结果群集</span><span class="sxs-lookup"><span data-stu-id="5b0fd-154">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="5b0fd-155">如何自定义和配置搜索结果？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-155">How do I customize and configure search results?</span></span>

<span data-ttu-id="5b0fd-156">有许多方法可以自定义和配置搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-156">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="5b0fd-157">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="5b0fd-157">See the following articles to learn more:</span></span>

* [<span data-ttu-id="5b0fd-158">管理垂直领域和结果类型</span><span class="sxs-lookup"><span data-stu-id="5b0fd-158">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="5b0fd-159">管理搜索结果布局</span><span class="sxs-lookup"><span data-stu-id="5b0fd-159">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="5b0fd-160">管理结果群集</span><span class="sxs-lookup"><span data-stu-id="5b0fd-160">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="5b0fd-161">管理自定义筛选器</span><span class="sxs-lookup"><span data-stu-id="5b0fd-161">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="5b0fd-162">如何从自定义应用程序中搜索连接器数据？</span><span class="sxs-lookup"><span data-stu-id="5b0fd-162">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="5b0fd-163">对自定义数据编制索引后，开发人员 [可以查询此数据](https://docs.microsoft.com/graph/search-concept-custom-types)。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-163">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="5b0fd-164">可以在任何应用程序中查看数据。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-164">You can view your data in any application.</span></span> <span data-ttu-id="5b0fd-165">有关详细信息，请参阅 Microsoft [Graph 中的 Microsoft 搜索 API 概述](https://docs.microsoft.com/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-165">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="limitations"></a><span data-ttu-id="5b0fd-166">限制</span><span class="sxs-lookup"><span data-stu-id="5b0fd-166">Limitations</span></span>

* <span data-ttu-id="5b0fd-167">**发布** Microsoft 构建的连接器时，可能需要几分钟时间才能创建连接。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-167">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="5b0fd-168">在此期间，连接的状态将显示为"挂起"。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-168">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="5b0fd-169">[Microsoft 365 管理](https://admin.microsoft.com)中心不支持在连接发布后编辑搜索架构。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-169">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="5b0fd-170">若要编辑搜索架构，请删除连接，然后创建一个新连接。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-170">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="5b0fd-171">以大约每秒四个项目的速度限制 Ingestion 吞吐量。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-171">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="5b0fd-172">不支持架构更新。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-172">There is no support for schema updates.</span></span> <span data-ttu-id="5b0fd-173">创建连接设置后，无法更新架构。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-173">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="5b0fd-174">只能删除并重新创建连接。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-174">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="5b0fd-175">存在连接限制。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-175">There is a connections limit.</span></span> <span data-ttu-id="5b0fd-176">每个租户可以创建最多 10 个连接。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-176">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="5b0fd-177">不支持编辑连接。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-177">Edit support for connection is not available.</span></span> <span data-ttu-id="5b0fd-178">创建连接后，无法编辑或更改它。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-178">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="5b0fd-179">如果需要更改任何详细信息，则必须删除并重新创建连接。</span><span class="sxs-lookup"><span data-stu-id="5b0fd-179">If you need to change any details, you must delete and recreate the connection.</span></span>
