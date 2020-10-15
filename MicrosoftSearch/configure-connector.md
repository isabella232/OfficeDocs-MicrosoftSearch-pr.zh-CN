---
title: 为 Microsoft Search 配置 Microsoft 构建的连接器
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 为 Microsoft Search 配置 Microsoft 构建的连接器
ms.openlocfilehash: ce2515b3eaa859a8fbb00d83c4727865ab55e174
ms.sourcegitcommit: 6aea7102c94855e9f80711c0f3d7bf5833ce8fb5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464473"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="set-up-your-microsoft-built-connector-for-microsoft-search"></a><span data-ttu-id="71f21-103">将 Microsoft 构建的连接器设置为 Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="71f21-103">Set up your Microsoft-built connector for Microsoft Search</span></span>

<span data-ttu-id="71f21-104">本文将指导您完成配置 Microsoft 构建的连接器的步骤。</span><span class="sxs-lookup"><span data-stu-id="71f21-104">This article guides you through the steps of configuring a Microsoft-built connector.</span></span> <span data-ttu-id="71f21-105">概述了在 Microsoft 365 [管理中心](https://admin.microsoft.com)中设置连接的流程。</span><span class="sxs-lookup"><span data-stu-id="71f21-105">It outlines the flow of setting up a connection in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="71f21-106">有关如何设置特定的 Microsoft 构建的连接器的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="71f21-106">For more information on how to set up specific Microsoft-built connectors, see these articles:</span></span>

* [<span data-ttu-id="71f21-107">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="71f21-107">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="71f21-108">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="71f21-108">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="71f21-109">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="71f21-109">Azure SQL</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="71f21-110">企业网站</span><span class="sxs-lookup"><span data-stu-id="71f21-110">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="71f21-111">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="71f21-111">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="71f21-112">Microsoft SQL server</span><span class="sxs-lookup"><span data-stu-id="71f21-112">Microsoft SQL server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="71f21-113">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="71f21-113">ServiceNow</span></span>](servicenow-connector.md)

## <a name="set-up"></a><span data-ttu-id="71f21-114">设置</span><span class="sxs-lookup"><span data-stu-id="71f21-114">Set up</span></span>

<span data-ttu-id="71f21-115">完成以下步骤以配置任何 Microsoft 构建的连接器。</span><span class="sxs-lookup"><span data-stu-id="71f21-115">Complete the following steps to configure any of the Microsoft-built connectors.</span></span>

1. <span data-ttu-id="71f21-116">转到[Microsoft 365 管理中心](https://admin.microsoft.com)中的 "[连接器" 选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。</span><span class="sxs-lookup"><span data-stu-id="71f21-116">Go to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="71f21-117">使用 [Microsoft 365](https://www.microsoft.com/microsoft-365) 租户的凭据登录你的帐户。</span><span class="sxs-lookup"><span data-stu-id="71f21-117">Sign in to your account with the credentials for your [Microsoft 365](https://www.microsoft.com/microsoft-365) tenant.</span></span>
3. <span data-ttu-id="71f21-118">选择 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="71f21-118">Select **Add a connector**.</span></span>
4. <span data-ttu-id="71f21-119">从可用连接器列表中，选择所选的连接器。</span><span class="sxs-lookup"><span data-stu-id="71f21-119">From the list of available connectors, select the connector of your choice.</span></span>

![可用的数据源包括： Azure DevOps Connector、ServiceNow、ADLS Gen2、Enterprise 网站、MediaWiki、Microsoft SQL server 和 Azure SQL。](media/add_connector.png)

### <a name="name-the-connector"></a><span data-ttu-id="71f21-121">命名连接器</span><span class="sxs-lookup"><span data-stu-id="71f21-121">Name the connector</span></span>

<span data-ttu-id="71f21-122">若要创建连接，请先指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="71f21-122">To create a connection, first specify these attributes:</span></span>

1. <span data-ttu-id="71f21-123">连接的名称</span><span class="sxs-lookup"><span data-stu-id="71f21-123">Name of the connection</span></span>
2. <span data-ttu-id="71f21-124">连接 ID</span><span class="sxs-lookup"><span data-stu-id="71f21-124">Connection ID</span></span>
3. <span data-ttu-id="71f21-125"> (可选) 的说明</span><span class="sxs-lookup"><span data-stu-id="71f21-125">Description (optional)</span></span>

<span data-ttu-id="71f21-126">连接 ID 为连接器创建隐式属性。</span><span class="sxs-lookup"><span data-stu-id="71f21-126">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="71f21-127">它必须仅包含字母数字字符，并且最多为32个字符。</span><span class="sxs-lookup"><span data-stu-id="71f21-127">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span>

### <a name="connect-to-a-data-source"></a><span data-ttu-id="71f21-128">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="71f21-128">Connect to a data source</span></span>

<span data-ttu-id="71f21-129">数据连接过程根据连接器的类型而有所不同。</span><span class="sxs-lookup"><span data-stu-id="71f21-129">The data connection process varies based on the type of connector.</span></span> <span data-ttu-id="71f21-130">若要了解有关连接到本地数据源的详细信息，请参阅 [安装本地 data gateway](https://aka.ms/configuregateway)。</span><span class="sxs-lookup"><span data-stu-id="71f21-130">To learn more about connecting to your on-premises data source, see [Install an on-premises data gateway](https://aka.ms/configuregateway).</span></span>

### <a name="select-source-properties"></a><span data-ttu-id="71f21-131">选择源属性</span><span class="sxs-lookup"><span data-stu-id="71f21-131">Select source properties</span></span>

<span data-ttu-id="71f21-132">由第三方数据源设置为源属性的数据字段被编入 Microsoft Search。</span><span class="sxs-lookup"><span data-stu-id="71f21-132">The data fields set by your third-party data source as source properties are indexed into Microsoft Search.</span></span> <span data-ttu-id="71f21-133">若要修改这些属性，请选择 "**连接器**" 页面右侧侧栏中的 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="71f21-133">To modify these properties, select **Edit properties** in the side bar on the right of the **Connectors** page.</span></span> <span data-ttu-id="71f21-134">**最高可选择64个源属性**。</span><span class="sxs-lookup"><span data-stu-id="71f21-134">You can select **up to 64 source properties**.</span></span>

### <a name="manage-the-search-schema"></a><span data-ttu-id="71f21-135">管理搜索架构</span><span class="sxs-lookup"><span data-stu-id="71f21-135">Manage the search schema</span></span>

#### <a name="content-property"></a><span data-ttu-id="71f21-136">Content 属性</span><span class="sxs-lookup"><span data-stu-id="71f21-136">Content property</span></span>

<span data-ttu-id="71f21-137">您可以从**content**属性下拉列表中选择任意字符串属性，以选择哪个源属性是 (项的全文索引) 项的**内容**属性。</span><span class="sxs-lookup"><span data-stu-id="71f21-137">You can select which source property is the **content** property (full-text index of the item) by selecting any string property from the **content** property dropdown.</span></span> <span data-ttu-id="71f21-138">或者，可以保留默认的选定属性（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="71f21-138">Alternatively, you can keep the default selected property if one is present.</span></span>

<span data-ttu-id="71f21-139">尤其重要的是，因为此属性用于内容的全文索引、搜索结果页面代码段生成、语言检测、HTML/文本支持、排名和相关性以及查询表述，所以选择正确的属性是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="71f21-139">It is especially important that the correct property is selected since this property used for full-text indexing of content, search results page snippet generation, language detection, HTML/text support, ranking and relevance, and query formulation.</span></span>

<span data-ttu-id="71f21-140">如果选择**内容**的属性，则可以选择在[创建结果类型](customize-results-layout.md)时使用系统生成的属性**ResultSnippet** 。</span><span class="sxs-lookup"><span data-stu-id="71f21-140">If you select a property for **content**, you will have the option of using the system-generated property **ResultSnippet** when you [create your result type](customize-results-layout.md).</span></span> <span data-ttu-id="71f21-141">此属性用作在查询时从 **content** 属性生成的动态代码段的占位符。</span><span class="sxs-lookup"><span data-stu-id="71f21-141">This property serves as a placeholder for the dynamic snippets that are generated from the **content** property at query time.</span></span> <span data-ttu-id="71f21-142">如果您的结果类型中使用此属性，则会在搜索结果中生成代码段。</span><span class="sxs-lookup"><span data-stu-id="71f21-142">If you use this property in your result type, snippets will be generated in your search results.</span></span>

#### <a name="search-schema-attributes"></a><span data-ttu-id="71f21-143">搜索架构属性</span><span class="sxs-lookup"><span data-stu-id="71f21-143">Search schema attributes</span></span>

<span data-ttu-id="71f21-144">您可以设置搜索架构属性，以控制每个 source 属性的搜索功能。</span><span class="sxs-lookup"><span data-stu-id="71f21-144">You can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="71f21-145">搜索架构可帮助确定搜索结果页面上显示的结果以及最终用户可以查看和访问的信息。</span><span class="sxs-lookup"><span data-stu-id="71f21-145">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="71f21-146">搜索架构属性包括可 **搜索**、可 **查询**和可 **检索**。</span><span class="sxs-lookup"><span data-stu-id="71f21-146">Search schema attributes include **searchable**, **queryable**, and **retrievable**.</span></span> <span data-ttu-id="71f21-147">下表列出了 Microsoft Graph 连接器支持和解释其功能的每个属性。</span><span class="sxs-lookup"><span data-stu-id="71f21-147">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="71f21-148">搜索架构属性</span><span class="sxs-lookup"><span data-stu-id="71f21-148">Search schema attribute</span></span> | <span data-ttu-id="71f21-149">函数</span><span class="sxs-lookup"><span data-stu-id="71f21-149">Function</span></span> | <span data-ttu-id="71f21-150">示例</span><span class="sxs-lookup"><span data-stu-id="71f21-150">Example</span></span>
--- | --- | ---
<span data-ttu-id="71f21-151">外面</span><span class="sxs-lookup"><span data-stu-id="71f21-151">SEARCHABLE</span></span> | <span data-ttu-id="71f21-152">将属性的文本内容设为可搜索的。</span><span class="sxs-lookup"><span data-stu-id="71f21-152">Makes the text content of a property searchable.</span></span> <span data-ttu-id="71f21-153">属性内容包含在全文本索引中。</span><span class="sxs-lookup"><span data-stu-id="71f21-153">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="71f21-154">如果属性为 **title**，则针对 **企业** 的查询返回包含任何文本或标题中的 word **Enterprise** 的答案。</span><span class="sxs-lookup"><span data-stu-id="71f21-154">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="71f21-155">可</span><span class="sxs-lookup"><span data-stu-id="71f21-155">QUERYABLE</span></span> | <span data-ttu-id="71f21-156">按查询搜索特定属性的匹配项。</span><span class="sxs-lookup"><span data-stu-id="71f21-156">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="71f21-157">然后可以通过编程方式或逐字方式在查询中指定属性名称。</span><span class="sxs-lookup"><span data-stu-id="71f21-157">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="71f21-158">如果 **Title** 属性是可查询的，则支持查询 **标题： Enterprise** 。</span><span class="sxs-lookup"><span data-stu-id="71f21-158">If the **Title** property is queryable, then the query **Title: Enterprise** is supported.</span></span>
<span data-ttu-id="71f21-159">可检索</span><span class="sxs-lookup"><span data-stu-id="71f21-159">RETRIEVABLE</span></span> | <span data-ttu-id="71f21-160">只能在结果类型中使用可检索的属性并显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="71f21-160">Only retrievable properties can be used in the result type and display in the search result.</span></span> |

<span data-ttu-id="71f21-161">对于所有连接器，必须手动设置自定义类型。</span><span class="sxs-lookup"><span data-stu-id="71f21-161">For all connectors, custom types must be set manually.</span></span> <span data-ttu-id="71f21-162">若要激活每个字段的搜索功能，您需要映射到属性列表的搜索架构。</span><span class="sxs-lookup"><span data-stu-id="71f21-162">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="71f21-163">"连接向导" 将根据您选择的源属性集自动选择搜索架构。</span><span class="sxs-lookup"><span data-stu-id="71f21-163">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="71f21-164">您可以通过选中 "搜索架构" 页中每个属性和属性的复选框来修改此架构。</span><span class="sxs-lookup"><span data-stu-id="71f21-164">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

![可以通过添加或删除查询、搜索和检索函数来自定义连接器的架构。](media/manageschema.png)

#### <a name="restrictions-and-recommendations-for-search-schema-settings"></a><span data-ttu-id="71f21-166">搜索架构设置的限制和建议</span><span class="sxs-lookup"><span data-stu-id="71f21-166">Restrictions and recommendations for search schema settings</span></span>

* <span data-ttu-id="71f21-167">**Content**属性仅可搜索。</span><span class="sxs-lookup"><span data-stu-id="71f21-167">The **content** property is searchable only.</span></span> <span data-ttu-id="71f21-168">在下拉列表中选择此属性后，将无法将此属性标记为可 **检索** 或可 **查询**。</span><span class="sxs-lookup"><span data-stu-id="71f21-168">Once selected in the dropdown, this property cannot be marked **retrievable** or **queryable**.</span></span> <span data-ttu-id="71f21-169">当使用 **content** 属性呈现搜索结果时，会出现重大性能问题。</span><span class="sxs-lookup"><span data-stu-id="71f21-169">Significant performance issues occur when search results render with the **content** property.</span></span> <span data-ttu-id="71f21-170">例如， [ServiceNow](https://www.servicenow.com)知识库文章的**文本**内容字段。</span><span class="sxs-lookup"><span data-stu-id="71f21-170">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>

* <span data-ttu-id="71f21-171">仅属性在搜索结果中标记为可检索的，并且可用于创建新式结果类型 (MRTs) 。</span><span class="sxs-lookup"><span data-stu-id="71f21-171">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>

* <span data-ttu-id="71f21-172">只能将字符串属性标记为可搜索。</span><span class="sxs-lookup"><span data-stu-id="71f21-172">Only string properties can be marked searchable.</span></span>


> [!Note]
> <span data-ttu-id="71f21-173">创建连接后， **不能** 修改架构。</span><span class="sxs-lookup"><span data-stu-id="71f21-173">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="71f21-174">若要执行此操作，您需要删除连接并创建一个新的连接。</span><span class="sxs-lookup"><span data-stu-id="71f21-174">To do that, you need to delete your connection and create a new one.</span></span>

### <a name="manage-search-permissions"></a><span data-ttu-id="71f21-175">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="71f21-175">Manage search permissions</span></span>

<span data-ttu-id="71f21-176">访问控制列表 (Acl) 确定组织中的哪些用户可以访问每个数据项。</span><span class="sxs-lookup"><span data-stu-id="71f21-176">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span> <span data-ttu-id="71f21-177">所有连接器都支持对所有用户都可见的搜索权限。</span><span class="sxs-lookup"><span data-stu-id="71f21-177">All the connectors support search permissions that are visible to all users.</span></span>

### <a name="set-the-refresh-schedule"></a><span data-ttu-id="71f21-178">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="71f21-178">Set the refresh schedule</span></span>

<span data-ttu-id="71f21-179">刷新计划确定数据与 Microsoft Graph 和 Microsoft Search 中的索引同步的频率。</span><span class="sxs-lookup"><span data-stu-id="71f21-179">The refresh schedule determines how often your data is synced with the index in Microsoft Graph and Microsoft Search.</span></span> <span data-ttu-id="71f21-180">您可以通过两种方式安排刷新：完全爬网或增量爬网。</span><span class="sxs-lookup"><span data-stu-id="71f21-180">You can schedule the refresh in two ways: full crawl or incremental crawl.</span></span>

<span data-ttu-id="71f21-181">通过 **完全爬网**，搜索引擎将处理内容源中的每个项目并对其进行索引，而不考虑以前的爬网。</span><span class="sxs-lookup"><span data-stu-id="71f21-181">With a **full crawl**, the search engine processes and indexes every item in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="71f21-182">在下列情况下，完全爬网的效果最佳：</span><span class="sxs-lookup"><span data-stu-id="71f21-182">Full crawl works best in these situations:</span></span>

* <span data-ttu-id="71f21-183">检测数据删除。</span><span class="sxs-lookup"><span data-stu-id="71f21-183">Detecting deletions of data.</span></span>
* <span data-ttu-id="71f21-184">增量爬网无法对内容进行爬网以对错误进行爬网。</span><span class="sxs-lookup"><span data-stu-id="71f21-184">The incremental crawl failed to crawl content for errors.</span></span>
* <span data-ttu-id="71f21-185">已修改 Acl。</span><span class="sxs-lookup"><span data-stu-id="71f21-185">ACLs were modified.</span></span>
* <span data-ttu-id="71f21-186">修改了爬网规则。</span><span class="sxs-lookup"><span data-stu-id="71f21-186">Crawl rules were modified.</span></span>
* <span data-ttu-id="71f21-187">需要 Microsoft Search 软件更新。</span><span class="sxs-lookup"><span data-stu-id="71f21-187">A software update for Microsoft Search is required.</span></span> <span data-ttu-id="71f21-188">更新将修改搜索架构。</span><span class="sxs-lookup"><span data-stu-id="71f21-188">Updates modify the search schema.</span></span>

<span data-ttu-id="71f21-189">使用 **增量爬网**时，搜索引擎可以仅处理自上次成功爬网后创建或修改的项，并对这些项编制索引。</span><span class="sxs-lookup"><span data-stu-id="71f21-189">With an **incremental crawl**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="71f21-190">因此，并不会对内容源中的所有数据重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="71f21-190">Therefore, not all the data in the content source is re-indexed.</span></span> <span data-ttu-id="71f21-191">增量爬网最适用于检测内容、元数据、权限和其他更新。</span><span class="sxs-lookup"><span data-stu-id="71f21-191">Incremental crawls work best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="71f21-192">增量爬网比完全爬网快得多，因为未处理未更改的项目。</span><span class="sxs-lookup"><span data-stu-id="71f21-192">Incremental crawls are much faster than full crawls because unchanged items aren’t processed.</span></span> <span data-ttu-id="71f21-193">若要保持内容源和搜索索引之间的准确数据同步，您需要定期运行这两个爬网。</span><span class="sxs-lookup"><span data-stu-id="71f21-193">To maintain an accurate data sync between the content source and the search index, you need to run both crawls periodically.</span></span>

<span data-ttu-id="71f21-194">每个连接器都具有一组不同的最佳刷新计划，具体取决于修改数据的频率和修改的类型。</span><span class="sxs-lookup"><span data-stu-id="71f21-194">Each connector will have a different optimal set of refresh schedules based on how often data is modified and the type of modifications.</span></span>

![增量爬网和完全爬网间隔设置，显示15分钟的增量和一周的完全爬网。](media/refreshschedule.png)

### <a name="review-connector-settings"></a><span data-ttu-id="71f21-196">查看连接器设置</span><span class="sxs-lookup"><span data-stu-id="71f21-196">Review connector settings</span></span>

<span data-ttu-id="71f21-197">配置连接器后， [管理员中心](https://admin.microsoft.com) 将转到可查看您的设置的页面。</span><span class="sxs-lookup"><span data-stu-id="71f21-197">After you configure your connector, the [admin center](https://admin.microsoft.com) takes you to a page where you can review your settings.</span></span> <span data-ttu-id="71f21-198">您可以在确认连接之前，通过配置过程来编辑任何设置。</span><span class="sxs-lookup"><span data-stu-id="71f21-198">You can go back through the configuration process to edit any setting before you confirm the connection.</span></span> <span data-ttu-id="71f21-199">若要了解详细信息，请参阅 [管理连接器](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="71f21-199">To learn more, see [Manage your connector](manage-connector.md).</span></span>

## <a name="next-steps-customize-the-search-results-page"></a><span data-ttu-id="71f21-200">后续步骤：自定义搜索结果页</span><span class="sxs-lookup"><span data-stu-id="71f21-200">Next steps: Customize the search results page</span></span>

<span data-ttu-id="71f21-201">通过 Microsoft Search 用户界面 (UI) ，最终用户可以从你的 [microsoft 365](https://www.microsoft.com/microsoft-365) 效率应用和更广泛的 microsoft 生态系统中搜索内容。</span><span class="sxs-lookup"><span data-stu-id="71f21-201">With the Microsoft Search user interface (UI), your end users can search content from your [Microsoft 365](https://www.microsoft.com/microsoft-365) productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="71f21-202">垂直搜索是指当用户在[Bing](https://Bing.com)中的[SharePoint](https://sharepoint.com/)、 [microsoft Office](https://Office.com)和 microsoft 搜索中查看搜索结果时显示的选项卡。</span><span class="sxs-lookup"><span data-stu-id="71f21-202">A search vertical refers to the tabs that are shown when a user views their search results in [SharePoint](https://sharepoint.com/), [Microsoft Office](https://Office.com), and Microsoft Search in [Bing](https://Bing.com).</span></span> <span data-ttu-id="71f21-203">您可以自定义搜索纵向以缩小结果范围，以便只显示特定类型的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="71f21-203">You can customize search verticals to narrow down results, so that only a certain type of search results is displayed.</span></span> <span data-ttu-id="71f21-204">这些纵向显示为搜索结果页顶部的选项卡。</span><span class="sxs-lookup"><span data-stu-id="71f21-204">These verticals appear as a tab on the top of the search results page.</span></span> <span data-ttu-id="71f21-205">MRT.LOG)  (新式结果类型是指定如何显示结果的 UI。</span><span class="sxs-lookup"><span data-stu-id="71f21-205">A modern result type (MRT) is the UI that designates how results are presented.</span></span>

<span data-ttu-id="71f21-206">创建您自己的纵向和结果类型，以便最终用户可以查看来自新连接的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="71f21-206">Create your own verticals and result types, so end users can view search results from new connections.</span></span> <span data-ttu-id="71f21-207">如果不执行此步骤，则连接中的数据不会显示在搜索结果页上。</span><span class="sxs-lookup"><span data-stu-id="71f21-207">Without this step, data from your connection won’t show up on the search results page.</span></span>

<span data-ttu-id="71f21-208">若要了解有关如何创建您的纵向和 MRTs 的详细信息，请参阅 [搜索结果页面自定义](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="71f21-208">To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).</span></span>

## <a name="how-do-i-know-the-connection-setup-worked"></a><span data-ttu-id="71f21-209">我如何知道连接设置正常工作？</span><span class="sxs-lookup"><span data-stu-id="71f21-209">How do I know the connection setup worked?</span></span>

<span data-ttu-id="71f21-210">转到 "[管理中心](https://admin.microsoft.com)" 的 "**连接器**" 选项卡下的已发布连接列表。</span><span class="sxs-lookup"><span data-stu-id="71f21-210">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="71f21-211">若要了解如何进行更新和删除，请参阅 [管理连接器](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="71f21-211">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>
