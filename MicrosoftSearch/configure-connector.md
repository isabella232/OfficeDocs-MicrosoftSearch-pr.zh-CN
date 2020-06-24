---
title: 为 Microsoft Search 配置 Microsoft 构建的连接器
ms.author: mounika.narayanan
author: monaray
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
ms.openlocfilehash: e5b40326bdd83f461e7ce9a45889ad82245e20aa
ms.sourcegitcommit: 68cd28a84df120473270f27e4eb62de9eae455f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "44850886"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="set-up-your-microsoft-built-connector-for-microsoft-search"></a><span data-ttu-id="44647-103">将 Microsoft 构建的连接器设置为 Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="44647-103">Set up your Microsoft-built connector for Microsoft Search</span></span>

<span data-ttu-id="44647-104">本文将指导您完成配置 Microsoft 构建的连接器的步骤。</span><span class="sxs-lookup"><span data-stu-id="44647-104">This article guides you through the steps of configuring a Microsoft-built connector.</span></span> <span data-ttu-id="44647-105">概述了在 Microsoft 365[管理中心](https://admin.microsoft.com)中设置连接的流程。</span><span class="sxs-lookup"><span data-stu-id="44647-105">It outlines the flow of setting up a connection in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="44647-106">有关如何设置特定 Microsoft 构建的连接器的更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="44647-106">For more details on how to set up specific Microsoft-built connectors, see these articles:</span></span>

* [<span data-ttu-id="44647-107">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="44647-107">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="44647-108">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="44647-108">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="44647-109">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="44647-109">Azure SQL</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="44647-110">企业网站</span><span class="sxs-lookup"><span data-stu-id="44647-110">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="44647-111">文件共享</span><span class="sxs-lookup"><span data-stu-id="44647-111">File share</span></span>](file-share-connector.md)
* [<span data-ttu-id="44647-112">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="44647-112">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="44647-113">Microsoft SQL server</span><span class="sxs-lookup"><span data-stu-id="44647-113">Microsoft SQL server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="44647-114">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="44647-114">ServiceNow</span></span>](servicenow-connector.md)

## <a name="set-up"></a><span data-ttu-id="44647-115">设置</span><span class="sxs-lookup"><span data-stu-id="44647-115">Set up</span></span>

<span data-ttu-id="44647-116">完成以下步骤以配置任何 Microsoft 构建的连接器。</span><span class="sxs-lookup"><span data-stu-id="44647-116">Complete the following steps to configure any of the Microsoft-built connectors.</span></span>

1. <span data-ttu-id="44647-117">转到[Microsoft 365 管理中心](https://admin.microsoft.com)中的 "[连接器" 选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。</span><span class="sxs-lookup"><span data-stu-id="44647-117">Go to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="44647-118">使用[Microsoft 365](https://www.microsoft.com/microsoft-365)租户的凭据登录你的帐户。</span><span class="sxs-lookup"><span data-stu-id="44647-118">Sign in to your account with the credentials for your [Microsoft 365](https://www.microsoft.com/microsoft-365) tenant.</span></span>
3. <span data-ttu-id="44647-119">选择 "**添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="44647-119">Select **Add a connector**.</span></span>
4. <span data-ttu-id="44647-120">从可用连接器列表中，选择所选的连接器。</span><span class="sxs-lookup"><span data-stu-id="44647-120">From the list of available connectors, select the connector of your choice.</span></span>

![可用的数据源包括： ADLS Gen2 连接器、企业网站、ServiceNow、文件共享、Microsoft SQL server 和 MediaWiki。](media/addconnector_final.png)

### <a name="name-the-connector"></a><span data-ttu-id="44647-122">命名连接器</span><span class="sxs-lookup"><span data-stu-id="44647-122">Name the connector</span></span>

<span data-ttu-id="44647-123">若要创建连接，请先指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="44647-123">To create a connection, first specify these attributes:</span></span>

1. <span data-ttu-id="44647-124">连接的名称</span><span class="sxs-lookup"><span data-stu-id="44647-124">Name of the connection</span></span>
2. <span data-ttu-id="44647-125">连接 ID</span><span class="sxs-lookup"><span data-stu-id="44647-125">Connection ID</span></span>
3. <span data-ttu-id="44647-126">Description （可选）</span><span class="sxs-lookup"><span data-stu-id="44647-126">Description (optional)</span></span>

<span data-ttu-id="44647-127">连接 ID 为连接器创建隐式属性。</span><span class="sxs-lookup"><span data-stu-id="44647-127">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="44647-128">它必须仅包含字母数字字符，并且最多为32个字符。</span><span class="sxs-lookup"><span data-stu-id="44647-128">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span>

### <a name="connect-to-a-data-source"></a><span data-ttu-id="44647-129">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="44647-129">Connect to a data source</span></span>

<span data-ttu-id="44647-130">数据连接过程根据连接器的类型而有所不同。</span><span class="sxs-lookup"><span data-stu-id="44647-130">The data connection process varies based on the type of connector.</span></span> <span data-ttu-id="44647-131">若要了解有关连接到本地数据源的详细信息，请参阅[安装本地 data gateway](https://aka.ms/configuregateway)。</span><span class="sxs-lookup"><span data-stu-id="44647-131">To learn more about connecting to your on-premises data source, see [Install an on-premises data gateway](https://aka.ms/configuregateway).</span></span>

### <a name="select-source-properties"></a><span data-ttu-id="44647-132">选择源属性</span><span class="sxs-lookup"><span data-stu-id="44647-132">Select source properties</span></span>

<span data-ttu-id="44647-133">由第三方数据源设置为源属性的数据字段被编入 Microsoft Search。</span><span class="sxs-lookup"><span data-stu-id="44647-133">The data fields set by your third-party data source as source properties are indexed into Microsoft Search.</span></span> <span data-ttu-id="44647-134">若要修改这些属性，请选择 "**连接器**" 页面右侧侧栏中的 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="44647-134">To modify these properties, select **Edit properties** in the side bar on the right of the **Connectors** page.</span></span> <span data-ttu-id="44647-135">**最高可选择64个源属性**。</span><span class="sxs-lookup"><span data-stu-id="44647-135">You can select **up to 64 source properties**.</span></span>

### <a name="manage-the-search-schema"></a><span data-ttu-id="44647-136">管理搜索架构</span><span class="sxs-lookup"><span data-stu-id="44647-136">Manage the search schema</span></span>

<span data-ttu-id="44647-137">管理员可以设置搜索架构属性，以控制每个 source 属性的搜索功能。</span><span class="sxs-lookup"><span data-stu-id="44647-137">Admins can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="44647-138">搜索架构可帮助确定搜索结果页面上显示的结果以及最终用户可以查看和访问的信息。</span><span class="sxs-lookup"><span data-stu-id="44647-138">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="44647-139">搜索架构属性包括可**搜索**、可**查询**和可**检索**。</span><span class="sxs-lookup"><span data-stu-id="44647-139">Search schema attributes include **searchable**, **queryable**, and **retrievable**.</span></span> <span data-ttu-id="44647-140">下表列出了 Microsoft Graph 连接器支持和解释其功能的每个属性。</span><span class="sxs-lookup"><span data-stu-id="44647-140">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="44647-141">搜索架构属性</span><span class="sxs-lookup"><span data-stu-id="44647-141">Search schema attribute</span></span> | <span data-ttu-id="44647-142">函数</span><span class="sxs-lookup"><span data-stu-id="44647-142">Function</span></span> | <span data-ttu-id="44647-143">示例</span><span class="sxs-lookup"><span data-stu-id="44647-143">Example</span></span>
--- | --- | ---
<span data-ttu-id="44647-144">外面</span><span class="sxs-lookup"><span data-stu-id="44647-144">SEARCHABLE</span></span> | <span data-ttu-id="44647-145">将属性的文本内容设为可搜索的。</span><span class="sxs-lookup"><span data-stu-id="44647-145">Makes the text content of a property searchable.</span></span> <span data-ttu-id="44647-146">属性内容包含在全文本索引中。</span><span class="sxs-lookup"><span data-stu-id="44647-146">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="44647-147">如果属性为**title**，则针对**企业**的查询返回包含任何文本或标题中的 word **Enterprise**的答案。</span><span class="sxs-lookup"><span data-stu-id="44647-147">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="44647-148">可</span><span class="sxs-lookup"><span data-stu-id="44647-148">QUERYABLE</span></span> | <span data-ttu-id="44647-149">按查询搜索特定属性的匹配项。</span><span class="sxs-lookup"><span data-stu-id="44647-149">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="44647-150">然后可以通过编程方式或逐字方式在查询中指定属性名称。</span><span class="sxs-lookup"><span data-stu-id="44647-150">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="44647-151">如果**Title**属性是可查询的，则支持查询**标题： Enterprise** 。</span><span class="sxs-lookup"><span data-stu-id="44647-151">If the **Title** property is queryable, then the query **Title: Enterprise** is supported.</span></span>
<span data-ttu-id="44647-152">可检索</span><span class="sxs-lookup"><span data-stu-id="44647-152">RETRIEVABLE</span></span> | <span data-ttu-id="44647-153">只能在结果类型中使用可检索的属性并显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="44647-153">Only retrievable properties can be used in the result type and display in the search result.</span></span> |

<span data-ttu-id="44647-154">对于除文件共享连接器之外的所有连接器，必须手动设置自定义类型。</span><span class="sxs-lookup"><span data-stu-id="44647-154">For all connectors except the file share connector, custom types must be set manually.</span></span> <span data-ttu-id="44647-155">若要激活每个字段的搜索功能，您需要映射到属性列表的搜索架构。</span><span class="sxs-lookup"><span data-stu-id="44647-155">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="44647-156">"连接向导" 将根据您选择的源属性集自动选择搜索架构。</span><span class="sxs-lookup"><span data-stu-id="44647-156">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="44647-157">您可以通过选中 "搜索架构" 页中每个属性和属性的复选框来修改此架构。</span><span class="sxs-lookup"><span data-stu-id="44647-157">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

![可以通过添加或删除查询、搜索和检索函数来自定义连接器的架构。](media/manageschema.png)

<span data-ttu-id="44647-159">这些限制和建议适用于搜索架构设置：</span><span class="sxs-lookup"><span data-stu-id="44647-159">These restrictions and recommendations apply to search schema settings:</span></span>

* <span data-ttu-id="44647-160">对于索引自定义类型的连接器，我们建议您**不要标记包含**主要内容可**检索**的字段。</span><span class="sxs-lookup"><span data-stu-id="44647-160">For connectors that index custom types, we recommend that you **do not** mark the field that contains the main content **retrievable**.</span></span> <span data-ttu-id="44647-161">使用该搜索属性呈现搜索结果时，会出现重大性能问题。</span><span class="sxs-lookup"><span data-stu-id="44647-161">Significant performance issues occur when search results render with that search attribute.</span></span> <span data-ttu-id="44647-162">例如， [ServiceNow](https://www.servicenow.com)知识库文章的**文本**内容字段。</span><span class="sxs-lookup"><span data-stu-id="44647-162">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>
* <span data-ttu-id="44647-163">仅属性在搜索结果中标记为可检索的，并可用于创建新式结果类型（MRTs）。</span><span class="sxs-lookup"><span data-stu-id="44647-163">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>
* <span data-ttu-id="44647-164">只能将字符串属性标记为可搜索。</span><span class="sxs-lookup"><span data-stu-id="44647-164">Only string properties can be marked searchable.</span></span>

> [!Note]
> <span data-ttu-id="44647-165">创建连接后，**不能**修改架构。</span><span class="sxs-lookup"><span data-stu-id="44647-165">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="44647-166">若要执行此操作，您需要删除连接并创建一个新的连接。</span><span class="sxs-lookup"><span data-stu-id="44647-166">To do that, you need to delete your connection and create a new one.</span></span>

### <a name="manage-search-permissions"></a><span data-ttu-id="44647-167">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="44647-167">Manage search permissions</span></span>

<span data-ttu-id="44647-168">访问控制列表（Acl）确定组织中的哪些用户可以访问每个数据项。</span><span class="sxs-lookup"><span data-stu-id="44647-168">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span> <span data-ttu-id="44647-169">文件共享连接器仅支持可映射到[Azure Active Directory （AZURE AD）](https://docs.microsoft.com/azure/active-directory/)的 acl。</span><span class="sxs-lookup"><span data-stu-id="44647-169">The file share connector supports only ACLs that can be mapped to [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).</span></span> <span data-ttu-id="44647-170">所有其他连接器都支持对所有用户都可见的搜索权限。</span><span class="sxs-lookup"><span data-stu-id="44647-170">All the other connectors support search permissions that are visible to all users.</span></span>

### <a name="set-the-refresh-schedule"></a><span data-ttu-id="44647-171">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="44647-171">Set the refresh schedule</span></span>

<span data-ttu-id="44647-172">刷新计划确定数据与 Microsoft Graph 和 Microsoft Search 中的索引同步的频率。</span><span class="sxs-lookup"><span data-stu-id="44647-172">The refresh schedule determines how often your data is synced with the index in Microsoft Graph and Microsoft Search.</span></span> <span data-ttu-id="44647-173">您可以通过两种方式安排刷新：完全爬网或增量爬网。</span><span class="sxs-lookup"><span data-stu-id="44647-173">You can schedule the refresh in two ways: full crawl or incremental crawl.</span></span>

<span data-ttu-id="44647-174">通过**完全爬网**，搜索引擎将处理内容源中的每个项目并对其进行索引，而不考虑以前的爬网。</span><span class="sxs-lookup"><span data-stu-id="44647-174">With a **full crawl**, the search engine processes and indexes every item in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="44647-175">在下列情况下，完全爬网的效果最佳：</span><span class="sxs-lookup"><span data-stu-id="44647-175">Full crawl works best in these situations:</span></span>

* <span data-ttu-id="44647-176">您需要检测数据的删除。</span><span class="sxs-lookup"><span data-stu-id="44647-176">You need to detect deletions of data.</span></span>
* <span data-ttu-id="44647-177">增量爬网无法对内容进行爬网以对错误进行爬网。</span><span class="sxs-lookup"><span data-stu-id="44647-177">The incremental crawl failed to crawl content for errors.</span></span>
* <span data-ttu-id="44647-178">需要 Microsoft Search 软件更新。</span><span class="sxs-lookup"><span data-stu-id="44647-178">A software update for Microsoft Search is required.</span></span> <span data-ttu-id="44647-179">更新将修改搜索架构。</span><span class="sxs-lookup"><span data-stu-id="44647-179">Updates modify the search schema.</span></span>
* <span data-ttu-id="44647-180">已修改 Acl。</span><span class="sxs-lookup"><span data-stu-id="44647-180">ACLs were modified.</span></span>
* <span data-ttu-id="44647-181">修改了爬网规则。</span><span class="sxs-lookup"><span data-stu-id="44647-181">Crawl rules were modified.</span></span>

<span data-ttu-id="44647-182">使用**增量爬网**时，搜索引擎可以仅处理自上次成功爬网后创建或修改的项，并对这些项编制索引。</span><span class="sxs-lookup"><span data-stu-id="44647-182">With an **incremental crawl**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="44647-183">因此，并不会对内容源中的所有数据重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="44647-183">Therefore, not all the data in the content source is re-indexed.</span></span> <span data-ttu-id="44647-184">增量爬网最适用于检测内容、元数据、权限和其他更新。</span><span class="sxs-lookup"><span data-stu-id="44647-184">Incremental crawls works best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="44647-185">增量爬网比完全爬网快得多，因为未处理未更改的项目。</span><span class="sxs-lookup"><span data-stu-id="44647-185">Incremental crawls are much faster than full crawls because unchanged items aren’t processed.</span></span> <span data-ttu-id="44647-186">若要保持内容源和搜索索引之间的准确数据同步，您需要定期运行这两个爬网。</span><span class="sxs-lookup"><span data-stu-id="44647-186">To maintain an accurate data sync between the content source and the search index, you need to run both crawls periodically.</span></span>

<span data-ttu-id="44647-187">每个连接器都具有一组不同的最佳刷新计划，具体取决于修改数据的频率和修改的类型。</span><span class="sxs-lookup"><span data-stu-id="44647-187">Each connector will have a different optimal set of refresh schedules based on how often data is modified and the type of modifications.</span></span>

![增量爬网和完全爬网间隔设置，显示15分钟的增量和一周的完全爬网。](media/refreshschedule.png)

### <a name="review-connector-settings"></a><span data-ttu-id="44647-189">查看连接器设置</span><span class="sxs-lookup"><span data-stu-id="44647-189">Review connector settings</span></span>

<span data-ttu-id="44647-190">配置连接器后，[管理员中心](https://admin.microsoft.com)将转到可查看您的设置的页面。</span><span class="sxs-lookup"><span data-stu-id="44647-190">After you configure your connector, the [admin center](https://admin.microsoft.com) takes you to a page where you can review your settings.</span></span> <span data-ttu-id="44647-191">您可以在确认连接之前，通过配置过程来编辑任何设置。</span><span class="sxs-lookup"><span data-stu-id="44647-191">You can go back through the configuration process to edit any setting before you confirm the connection.</span></span> <span data-ttu-id="44647-192">若要了解详细信息，请参阅[管理连接器](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="44647-192">To learn more, see [Manage your connector](manage-connector.md).</span></span>

## <a name="next-steps-customize-the-search-results-page"></a><span data-ttu-id="44647-193">后续步骤：自定义搜索结果页</span><span class="sxs-lookup"><span data-stu-id="44647-193">Next steps: Customize the search results page</span></span>

<span data-ttu-id="44647-194">通过 Microsoft Search 用户界面（UI），最终用户可以从你的[microsoft 365](https://www.microsoft.com/microsoft-365)生产力应用和更广泛的 microsoft 生态系统中搜索内容。</span><span class="sxs-lookup"><span data-stu-id="44647-194">With the Microsoft Search user interface (UI), your end users can search content from your [Microsoft 365](https://www.microsoft.com/microsoft-365) productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="44647-195">垂直搜索是指当用户在[Bing](https://Bing.com)中的[SharePoint](https://sharepoint.com/)、 [microsoft Office](https://Office.com)和 microsoft 搜索中查看搜索结果时显示的选项卡。</span><span class="sxs-lookup"><span data-stu-id="44647-195">A search vertical refers to the tabs that are shown when a user views their search results in [SharePoint](https://sharepoint.com/), [Microsoft Office](https://Office.com), and Microsoft Search in [Bing](https://Bing.com).</span></span> <span data-ttu-id="44647-196">您可以自定义搜索纵向以缩小结果范围，以便只显示特定类型的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="44647-196">You can customize search verticals to narrow down results, so that only a certain type of search results is displayed.</span></span> <span data-ttu-id="44647-197">这些纵向显示为搜索结果页顶部的选项卡。</span><span class="sxs-lookup"><span data-stu-id="44647-197">These verticals appear as a tab on the top of the search results page.</span></span> <span data-ttu-id="44647-198">新式结果类型（MRT.LOG）是指定如何显示结果的 UI。</span><span class="sxs-lookup"><span data-stu-id="44647-198">A modern result type (MRT) is the UI that designates how results are presented.</span></span>

<span data-ttu-id="44647-199">您必须创建自己的纵向和结果类型，以便最终用户可以查看来自新连接的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="44647-199">You must create your own verticals and result types, so end users can view search results from new connections.</span></span> <span data-ttu-id="44647-200">如果不执行此步骤，则连接中的数据不会显示在搜索结果页上。</span><span class="sxs-lookup"><span data-stu-id="44647-200">Without this step, data from your connection won’t show up on the search results page.</span></span>

<span data-ttu-id="44647-201">若要了解有关如何创建您的纵向和 MRTs 的详细信息，请参阅[搜索结果页面自定义](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="44647-201">To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).</span></span>

## <a name="how-do-i-know-this-worked"></a><span data-ttu-id="44647-202">我如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="44647-202">How do I know this worked?</span></span>

<span data-ttu-id="44647-203">转到 "[管理中心](https://admin.microsoft.com)" 的 "**连接器**" 选项卡下的已发布连接列表。</span><span class="sxs-lookup"><span data-stu-id="44647-203">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="44647-204">若要了解如何进行更新和删除，请参阅[管理连接器](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="44647-204">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>
