---
title: 为 Microsoft 搜索配置 Microsoft 构建的连接器
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
description: 为 Microsoft 搜索配置 Microsoft 构建的连接器
ms.openlocfilehash: 61a7d444ddc4c290b5098c327faa8e70f0ef1049
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847543"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a><span data-ttu-id="b4110-103">Microsoft Graph 连接器的安装概述</span><span class="sxs-lookup"><span data-stu-id="b4110-103">Setup overview for Graph connectors by Microsoft</span></span> 

<span data-ttu-id="b4110-104">本文总结了使用 [Microsoft 365](https://admin.microsoft.com) 管理中心设置 Microsoft 的任何 Graph 连接器所需的基本过程。</span><span class="sxs-lookup"><span data-stu-id="b4110-104">This article summarizes the basic process required to use the [Microsoft 365 admin center](https://admin.microsoft.com) to setup any of the Graph connectors by Microsoft.</span></span> <span data-ttu-id="b4110-105">基本过程包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b4110-105">The basic process includes the following steps:</span></span>  
<!---Add links to each section in the doc--->

1. <span data-ttu-id="b4110-106">在 Microsoft 365 管理中心添加 Graph 连接器。</span><span class="sxs-lookup"><span data-stu-id="b4110-106">Add a Graph connector in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="b4110-107">命名连接。</span><span class="sxs-lookup"><span data-stu-id="b4110-107">Name the connection.</span></span>
3. <span data-ttu-id="b4110-108">配置连接设置。</span><span class="sxs-lookup"><span data-stu-id="b4110-108">Configure the connection settings.</span></span>
4. <span data-ttu-id="b4110-109">管理搜索权限。</span><span class="sxs-lookup"><span data-stu-id="b4110-109">Manage search permissions.</span></span>
5. <span data-ttu-id="b4110-110">分配属性标签。</span><span class="sxs-lookup"><span data-stu-id="b4110-110">Assign property labels.</span></span>
6. <span data-ttu-id="b4110-111">管理架构。</span><span class="sxs-lookup"><span data-stu-id="b4110-111">Manage schema.</span></span>
7. <span data-ttu-id="b4110-112">选择刷新设置。</span><span class="sxs-lookup"><span data-stu-id="b4110-112">Choose refresh settings.</span></span>
8. <span data-ttu-id="b4110-113">查看连接。</span><span class="sxs-lookup"><span data-stu-id="b4110-113">Review the connection.</span></span>

<span data-ttu-id="b4110-114">需要注意的是，Microsoft 的所有 Graph 连接器的安装过程非常相似，但不完全相同。</span><span class="sxs-lookup"><span data-stu-id="b4110-114">It is important to note that the setup process is very similar for all the Graph connectors by Microsoft but is not exactly the same.</span></span> <span data-ttu-id="b4110-115">**除了阅读本文之外，还请务必阅读数据源的连接器特定信息。**</span><span class="sxs-lookup"><span data-stu-id="b4110-115">**In addition to reading this article, be sure to read the connector-specific information for your data source.**</span></span>  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b4110-116">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="b4110-116">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b4110-117">完成以下步骤以配置任何 Microsoft 构建的连接器。</span><span class="sxs-lookup"><span data-stu-id="b4110-117">Complete the following steps to configure any of the Microsoft-built connectors.</span></span>

1. <span data-ttu-id="b4110-118">在[Microsoft 365](https://admin.microsoft.com)管理中心登录管理员帐户</span><span class="sxs-lookup"><span data-stu-id="b4110-118">Sign into your admin account in the [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
2. <span data-ttu-id="b4110-119">在导航窗格中 **，选择"** 设置"，然后选择"搜索 **&智能。**</span><span class="sxs-lookup"><span data-stu-id="b4110-119">In the navigation pane, select **Settings**, and then select **Search & intelligence**.</span></span> <span data-ttu-id="b4110-120">选择 ["连接器"选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。</span><span class="sxs-lookup"><span data-stu-id="b4110-120">Select the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).</span></span>
3. <span data-ttu-id="b4110-121">选择 **"+** 添加"，然后从可用选项的菜单中选择你选择的数据源。</span><span class="sxs-lookup"><span data-stu-id="b4110-121">Select **+Add**, and then select the data source of your choice from the menu of available options.</span></span>

![可用的数据源包括：ADLS Gen2、企业网站、Microsoft SQL 服务器、Azure SQL、Oracle SQL 数据库、ServiceNow、文件共享、Azure DevOps 和 MediaWiki。](media/add-connector.png)

><span data-ttu-id="b4110-123">[!注意：] 最多可以向每个租户添加 10 个 Graph 连接。</span><span class="sxs-lookup"><span data-stu-id="b4110-123">[!Note:] You can add a maximum of ten Graph connections to each tenant.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="b4110-124">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="b4110-124">Step 2: Name the connection</span></span>
<span data-ttu-id="b4110-125">需要指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="b4110-125">You will need to specify these attributes:</span></span> 

* <span data-ttu-id="b4110-126">名称</span><span class="sxs-lookup"><span data-stu-id="b4110-126">Name</span></span>  
* <span data-ttu-id="b4110-127">连接 ID</span><span class="sxs-lookup"><span data-stu-id="b4110-127">Connection ID</span></span> 
* <span data-ttu-id="b4110-128">说明 (可选) </span><span class="sxs-lookup"><span data-stu-id="b4110-128">Description (optional)</span></span> 

<span data-ttu-id="b4110-129">连接 ID 为连接器创建隐式属性。</span><span class="sxs-lookup"><span data-stu-id="b4110-129">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="b4110-130">它只能包含字母数字字符，并且最多包含 32 个字符。</span><span class="sxs-lookup"><span data-stu-id="b4110-130">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span> 

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="b4110-131">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="b4110-131">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="b4110-132">配置连接设置的过程因数据源的类型而异。</span><span class="sxs-lookup"><span data-stu-id="b4110-132">The process to configure the Connection settings varies based on the type of data source.</span></span> <span data-ttu-id="b4110-133">请参阅要添加到租户的数据源类型的连接器特定信息，以在设置过程中完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="b4110-133">See the Connector-specific information for the type of data source you want to add to your tenant to complete this step in the setup process.</span></span>  

<span data-ttu-id="b4110-134">若要了解有关连接到本地数据源的更多信息，请参阅"[安装本地数据网关"。](https://aka.ms/configuregateway)</span><span class="sxs-lookup"><span data-stu-id="b4110-134">To learn more about connecting to an on-premises data source, see [Install an on-premises data gateway](https://aka.ms/configuregateway).</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="b4110-135">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="b4110-135">Step 4: Manage search permissions</span></span>

<span data-ttu-id="b4110-136">访问控制列表 (ACL) 确定组织中哪些用户可以访问每一项数据。</span><span class="sxs-lookup"><span data-stu-id="b4110-136">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span>  

<span data-ttu-id="b4110-137">一些连接器（ [如 Microsoft SQL](MSSQL-connector.md) [和 Azure Data Lake Storage Gen2）](azure-data-lake-connector.md) 在本机支持 [Azure Active Directory (Azure AD) ](https://docs.microsoft.com/azure/active-directory/) ACL。</span><span class="sxs-lookup"><span data-stu-id="b4110-137">Some connectors like [Microsoft SQL](MSSQL-connector.md) and [Azure Data Lake Storage Gen2](azure-data-lake-connector.md) natively support [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) ACLs.</span></span>

<span data-ttu-id="b4110-138">其他连接器（ [如 ServiceNow、Azure](servicenow-connector.md) [DevOps](azure-devops-connector.md)和 [Salesforce）](salesforce-connector.md) 支持同步非 Azure AD 用户和组。</span><span class="sxs-lookup"><span data-stu-id="b4110-138">Other connectors like [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md), and [Salesforce](salesforce-connector.md) support syncing of non-Azure AD users and groups.</span></span>  

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="b4110-139">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="b4110-139">Step 5: Assign property labels</span></span>
<span data-ttu-id="b4110-140">可以在"分配属性标签"页上将语义标签分配给源属性。</span><span class="sxs-lookup"><span data-stu-id="b4110-140">You can assign semantic labels to your source properties on the "Assign property labels" page.</span></span> <span data-ttu-id="b4110-141">标签是 Microsoft 提供的已知标记，可提供语义含义。</span><span class="sxs-lookup"><span data-stu-id="b4110-141">Labels are well known tags provided by Microsoft that provide semantic meaning.</span></span> <span data-ttu-id="b4110-142">它们允许 Microsoft 将连接器数据集成到 Microsoft 365 体验，如增强搜索、人员卡片、智能发现等。</span><span class="sxs-lookup"><span data-stu-id="b4110-142">They allow Microsoft to integrate your connector data into Microsoft 365 experiences such as enhanced search, people cards, intelligent discovery, and more.</span></span>  

<span data-ttu-id="b4110-143">下表列出了当前支持的标签及其说明。</span><span class="sxs-lookup"><span data-stu-id="b4110-143">The following table lists the currently supported labels and their descriptions.</span></span>  

<span data-ttu-id="b4110-144">标签</span><span class="sxs-lookup"><span data-stu-id="b4110-144">Label</span></span> | <span data-ttu-id="b4110-145">说明</span><span class="sxs-lookup"><span data-stu-id="b4110-145">Description</span></span>
--- | ---  
<span data-ttu-id="b4110-146">**title**</span><span class="sxs-lookup"><span data-stu-id="b4110-146">**title**</span></span> | <span data-ttu-id="b4110-147">您希望在搜索和其他体验中显示的项目的标题</span><span class="sxs-lookup"><span data-stu-id="b4110-147">The title for the item that you want shown in search and other experiences</span></span> 
<span data-ttu-id="b4110-148">**url**</span><span class="sxs-lookup"><span data-stu-id="b4110-148">**url**</span></span> | <span data-ttu-id="b4110-149">源系统中项的目标 URL</span><span class="sxs-lookup"><span data-stu-id="b4110-149">The target url of the item in the source system</span></span> 
<span data-ttu-id="b4110-150">**createdBy**</span><span class="sxs-lookup"><span data-stu-id="b4110-150">**createdBy**</span></span> | <span data-ttu-id="b4110-151">创建项目的人的名称</span><span class="sxs-lookup"><span data-stu-id="b4110-151">Name of the person who created the item</span></span> 
<span data-ttu-id="b4110-152">**lastModifiedBy**</span><span class="sxs-lookup"><span data-stu-id="b4110-152">**lastModifiedBy**</span></span> | <span data-ttu-id="b4110-153">最近编辑项目的人的姓名</span><span class="sxs-lookup"><span data-stu-id="b4110-153">Name of the person who most recently edited the item</span></span> 
<span data-ttu-id="b4110-154">**authors**</span><span class="sxs-lookup"><span data-stu-id="b4110-154">**authors**</span></span> | <span data-ttu-id="b4110-155">参与/协作项目的人的名称</span><span class="sxs-lookup"><span data-stu-id="b4110-155">Name of the people who participated/collaborated on the item</span></span> 
<span data-ttu-id="b4110-156">**createdDateTime**</span><span class="sxs-lookup"><span data-stu-id="b4110-156">**createdDateTime**</span></span> | <span data-ttu-id="b4110-157">项目创建时间</span><span class="sxs-lookup"><span data-stu-id="b4110-157">When was the item created</span></span> 
<span data-ttu-id="b4110-158">**lastModifiedDateTime**</span><span class="sxs-lookup"><span data-stu-id="b4110-158">**lastModifiedDateTime**</span></span> | <span data-ttu-id="b4110-159">最近编辑的项目何时</span><span class="sxs-lookup"><span data-stu-id="b4110-159">When was the item most recently edited</span></span> 
<span data-ttu-id="b4110-160">**fileName**</span><span class="sxs-lookup"><span data-stu-id="b4110-160">**fileName**</span></span> | <span data-ttu-id="b4110-161">文件项的名称</span><span class="sxs-lookup"><span data-stu-id="b4110-161">Name of the file item</span></span> 
<span data-ttu-id="b4110-162">**FileExtension**</span><span class="sxs-lookup"><span data-stu-id="b4110-162">**fileExtension**</span></span> | <span data-ttu-id="b4110-163">文件项的类型，如 .pdf 或 .word</span><span class="sxs-lookup"><span data-stu-id="b4110-163">Type of file item such as .pdf or .word</span></span> 

<span data-ttu-id="b4110-164">此页上的属性是根据您的数据源预先选择的，但如果有更适合特定标签的不同属性，可以更改此选择。</span><span class="sxs-lookup"><span data-stu-id="b4110-164">The properties on this page are pre-selected based on your data source, but you can change this selection if there is a different property that is better suited for a particular label.</span></span>  

<span data-ttu-id="b4110-165">标签 **标题** 是最重要的标签。</span><span class="sxs-lookup"><span data-stu-id="b4110-165">The label **title** is the most important label.</span></span> <span data-ttu-id="b4110-166">强烈建议 **你为此** 标签分配一个属性，以便连接参与结果 [群集体验](result-cluster.md)。</span><span class="sxs-lookup"><span data-stu-id="b4110-166">It is **strongly recommended** that you have a property assigned to this label in order for your connection to participate in the [result cluster experience](result-cluster.md).</span></span>

<span data-ttu-id="b4110-167">映射标签不正确会导致搜索体验变错。</span><span class="sxs-lookup"><span data-stu-id="b4110-167">Incorrectly mapping labels will cause a deteriorated search experience.</span></span> <span data-ttu-id="b4110-168">一些标签可以没有为其分配属性。</span><span class="sxs-lookup"><span data-stu-id="b4110-168">It is okay for some labels to not have a property assigned to it.</span></span>  

## <a name="step-6-manage-schema"></a><span data-ttu-id="b4110-169">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="b4110-169">Step 6: Manage schema</span></span>

### <a name="content-property"></a><span data-ttu-id="b4110-170">Content 属性</span><span class="sxs-lookup"><span data-stu-id="b4110-170">Content property</span></span>

<span data-ttu-id="b4110-171">强烈建议您从选项的下拉菜单中选择一个 \*\*Content 属性，或保留默认值（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="b4110-171">It is strongly recommended that you select a \*\*Content Property" from the drop-down menu of options, or keep the default if one is present.</span></span> <span data-ttu-id="b4110-172">此属性用于内容全文索引、搜索结果页面代码段生成、结果 [群集](result-cluster.md) 参与、语言检测、HTML/文本支持、排名和相关性以及查询公式化。</span><span class="sxs-lookup"><span data-stu-id="b4110-172">This property is used for full-text indexing of content, search results page snippet generation, [result cluster](result-cluster.md) participation, language detection, HTML/text support, ranking and relevance, and query formulation.</span></span>

<span data-ttu-id="b4110-173">如果选择内容属性，则当您创建结果类型时，可以选择使用系统生成的属性 **ResultSnippet。** [](customize-results-layout.md)</span><span class="sxs-lookup"><span data-stu-id="b4110-173">If you select a content property, you will have the option of using the system-generated property **ResultSnippet** when you [create your result type](customize-results-layout.md).</span></span> <span data-ttu-id="b4110-174">此属性充当查询时从内容属性生成的动态代码段的占位符。</span><span class="sxs-lookup"><span data-stu-id="b4110-174">This property serves as a placeholder for the dynamic snippets that are generated from the content property at query time.</span></span> <span data-ttu-id="b4110-175">如果在结果类型中使用此属性，将在搜索结果中生成代码段。</span><span class="sxs-lookup"><span data-stu-id="b4110-175">If you use this property in your result type, snippets will be generated in your search results.</span></span>

### <a name="creating-aliases-for-source-properties"></a><span data-ttu-id="b4110-176">为源属性创建别名</span><span class="sxs-lookup"><span data-stu-id="b4110-176">Creating aliases for source properties</span></span>

<span data-ttu-id="b4110-177">您可以在"管理架构"页上的"别名"列下向属性添加别名。</span><span class="sxs-lookup"><span data-stu-id="b4110-177">You can add aliases to your properties under the "Alias" column on the "Manage schema" page.</span></span> <span data-ttu-id="b4110-178">别名是属性的友好名称。</span><span class="sxs-lookup"><span data-stu-id="b4110-178">Aliases are friendly names for your properties.</span></span> <span data-ttu-id="b4110-179">它们用于查询和筛选器创建。</span><span class="sxs-lookup"><span data-stu-id="b4110-179">They are used in queries and in the creation of filters.</span></span> <span data-ttu-id="b4110-180">它们还用于从多个连接规范化源属性，使这些属性具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="b4110-180">They are also used to normalize source properties from multiple connections such that they have the same name.</span></span> <span data-ttu-id="b4110-181">这样，你可以为具有多个连接的垂直创建单个筛选器。</span><span class="sxs-lookup"><span data-stu-id="b4110-181">That way you can create a single filter for a vertical with multiple connections.</span></span> <span data-ttu-id="b4110-182">有关详细信息 [，请参阅"自定义](customize-search-page.md) 搜索结果"页。</span><span class="sxs-lookup"><span data-stu-id="b4110-182">See [Customize the search results page](customize-search-page.md) for more information.</span></span>  

### <a name="search-schema-attributes"></a><span data-ttu-id="b4110-183">搜索架构属性</span><span class="sxs-lookup"><span data-stu-id="b4110-183">Search schema attributes</span></span>

<span data-ttu-id="b4110-184">您可以设置搜索架构属性来控制每个源属性的搜索功能。</span><span class="sxs-lookup"><span data-stu-id="b4110-184">You can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="b4110-185">搜索架构可帮助确定搜索结果页面上显示哪些结果以及最终用户可以查看和访问的信息。</span><span class="sxs-lookup"><span data-stu-id="b4110-185">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="b4110-186">搜索架构属性包括 **可搜索**、**可查询\*\*\*\*、可检索** 和 **可精简**。</span><span class="sxs-lookup"><span data-stu-id="b4110-186">Search schema attributes include **searchable**, **queryable**, **retrievable**, and **refinable**.</span></span> <span data-ttu-id="b4110-187">下表列出了 Microsoft Graph 连接器支持的每个属性并说明了其功能。</span><span class="sxs-lookup"><span data-stu-id="b4110-187">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="b4110-188">搜索架构属性</span><span class="sxs-lookup"><span data-stu-id="b4110-188">Search schema attribute</span></span> | <span data-ttu-id="b4110-189">函数</span><span class="sxs-lookup"><span data-stu-id="b4110-189">Function</span></span> | <span data-ttu-id="b4110-190">示例</span><span class="sxs-lookup"><span data-stu-id="b4110-190">Example</span></span>
--- | --- | ---
<span data-ttu-id="b4110-191">可搜索</span><span class="sxs-lookup"><span data-stu-id="b4110-191">SEARCHABLE</span></span> | <span data-ttu-id="b4110-192">使属性的文本内容可搜索。</span><span class="sxs-lookup"><span data-stu-id="b4110-192">Makes the text content of a property searchable.</span></span> <span data-ttu-id="b4110-193">属性内容包含在全文索引中。</span><span class="sxs-lookup"><span data-stu-id="b4110-193">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="b4110-194">如果该属性为 **标题**，则企业版查询将返回任何文本或标题中包含 **单词 Enterprise** 的答案。</span><span class="sxs-lookup"><span data-stu-id="b4110-194">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="b4110-195">可查询</span><span class="sxs-lookup"><span data-stu-id="b4110-195">QUERYABLE</span></span> | <span data-ttu-id="b4110-196">通过查询来搜索特定属性的匹配项。</span><span class="sxs-lookup"><span data-stu-id="b4110-196">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="b4110-197">然后，可以在查询中以编程方式或详细指定属性名称。</span><span class="sxs-lookup"><span data-stu-id="b4110-197">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="b4110-198">如果 **Title** 属性是可查询的，则支持查询 **Title： Enterprise。**</span><span class="sxs-lookup"><span data-stu-id="b4110-198">If the **Title** property is queryable, then the query **Title: Enterprise** is supported.</span></span> 
<span data-ttu-id="b4110-199">可检索</span><span class="sxs-lookup"><span data-stu-id="b4110-199">RETRIEVABLE</span></span> | <span data-ttu-id="b4110-200">结果类型中只能使用可检索属性，并显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="b4110-200">Only retrievable properties can be used in the result type and display in the search result.</span></span> |
<span data-ttu-id="b4110-201">可精简</span><span class="sxs-lookup"><span data-stu-id="b4110-201">REFINABLE</span></span> | <span data-ttu-id="b4110-202">可精简属性可以像在 Microsoft 搜索结果页一样使用。</span><span class="sxs-lookup"><span data-stu-id="b4110-202">Refinable properties can be used as in the Microsoft Search results page.</span></span> | <span data-ttu-id="b4110-203">如果属性在连接设置 [](custom-filters.md)过程中标记为可精简，则组织用户可以在搜索结果页中按 **lastModifiedDateTime** 进行筛选</span><span class="sxs-lookup"><span data-stu-id="b4110-203">Users in your organization can [filter](custom-filters.md) by **lastModifiedDateTime** in the search results page if the property is marked refinable during connection setup</span></span>

<span data-ttu-id="b4110-204">对于除文件共享连接器之外的所有连接器，必须手动设置自定义类型。</span><span class="sxs-lookup"><span data-stu-id="b4110-204">For all connectors except the File share connector, custom types must be set manually.</span></span> <span data-ttu-id="b4110-205">若要激活每个字段的搜索功能，您需要映射到属性列表的搜索架构。</span><span class="sxs-lookup"><span data-stu-id="b4110-205">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="b4110-206">连接向导根据选择的源属性集自动选择搜索架构。</span><span class="sxs-lookup"><span data-stu-id="b4110-206">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="b4110-207">您可以通过选中搜索架构页中每个属性和属性的复选框来修改此架构。</span><span class="sxs-lookup"><span data-stu-id="b4110-207">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

![通过添加或删除查询、搜索和检索功能，可以自定义连接器的架构。](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a><span data-ttu-id="b4110-209">搜索架构设置的限制和建议</span><span class="sxs-lookup"><span data-stu-id="b4110-209">Restrictions and recommendations for search schema settings</span></span>

* <span data-ttu-id="b4110-210">内容 **属性** 只能搜索。</span><span class="sxs-lookup"><span data-stu-id="b4110-210">The **content** property is searchable only.</span></span> <span data-ttu-id="b4110-211">在下拉列表中选中此属性后，无法将此属性 **标记为可检索** 或 **可查询**。</span><span class="sxs-lookup"><span data-stu-id="b4110-211">Once selected in the dropdown, this property cannot be marked **retrievable** or **queryable**.</span></span>

* <span data-ttu-id="b4110-212">当搜索结果使用内容属性呈现时，会发生 **重大** 性能问题。</span><span class="sxs-lookup"><span data-stu-id="b4110-212">Significant performance issues occur when search results render with the **content** property.</span></span> <span data-ttu-id="b4110-213">例如 **，ServiceNow** 知识库文章的文本 [](https://www.servicenow.com)内容字段。</span><span class="sxs-lookup"><span data-stu-id="b4110-213">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>

* <span data-ttu-id="b4110-214">只有标记为可检索的属性才能在搜索结果中呈现，并且可用于在 MRT 中 (新式) 。</span><span class="sxs-lookup"><span data-stu-id="b4110-214">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>

* <span data-ttu-id="b4110-215">只能将字符串属性标记为可搜索。</span><span class="sxs-lookup"><span data-stu-id="b4110-215">Only string properties can be marked searchable.</span></span>

> [!NOTE]
> <span data-ttu-id="b4110-216">创建连接后， **无法** 修改架构。</span><span class="sxs-lookup"><span data-stu-id="b4110-216">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="b4110-217">为此，需要删除连接并新建一个连接。</span><span class="sxs-lookup"><span data-stu-id="b4110-217">To do that, you need to delete your connection and create a new one.</span></span>

## <a name="step-7-refresh-settings"></a><span data-ttu-id="b4110-218">步骤 7：刷新设置</span><span class="sxs-lookup"><span data-stu-id="b4110-218">Step 7: Refresh settings</span></span>

<span data-ttu-id="b4110-219">刷新间隔确定数据在数据源和 Microsoft 搜索之间同步频率。</span><span class="sxs-lookup"><span data-stu-id="b4110-219">The refresh interval determines how often your data is synced between the data source and Microsoft Search.</span></span> <span data-ttu-id="b4110-220">根据数据的修改频率和修改类型，每种数据源类型都有一组不同的最佳刷新计划。</span><span class="sxs-lookup"><span data-stu-id="b4110-220">Each type of data source has a different set of optimal refresh schedules based on how often data is modified and the type of modifications.</span></span>

<span data-ttu-id="b4110-221">有两种类型的刷新间隔，即完全 **刷新** 和增量刷新，但增量刷新不适用于某些数据源。</span><span class="sxs-lookup"><span data-stu-id="b4110-221">There are two types of refresh intervals, which are **Full refresh** and **Incremental refresh**, but incremental refreshes are not available for some data sources.</span></span>

<span data-ttu-id="b4110-222">完全刷新后，无论之前进行何种爬网，搜索引擎都会处理和索引内容源中的每个项目。</span><span class="sxs-lookup"><span data-stu-id="b4110-222">With a full refresh, the search engine processes and indexes every item in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="b4110-223">完全刷新最适合这些情况：</span><span class="sxs-lookup"><span data-stu-id="b4110-223">A full refresh works best for these situations:</span></span>

* <span data-ttu-id="b4110-224">检测数据的删除。</span><span class="sxs-lookup"><span data-stu-id="b4110-224">Detecting deletions of data.</span></span>
* <span data-ttu-id="b4110-225">增量刷新由于错误而未能更新内容。</span><span class="sxs-lookup"><span data-stu-id="b4110-225">The incremental refresh failed to update content due to errors.</span></span>
* <span data-ttu-id="b4110-226">ACL 已修改。</span><span class="sxs-lookup"><span data-stu-id="b4110-226">ACLs were modified.</span></span>
* <span data-ttu-id="b4110-227">已修改爬网规则。</span><span class="sxs-lookup"><span data-stu-id="b4110-227">Crawl rules were modified.</span></span>
* <span data-ttu-id="b4110-228">更新连接架构后， (架构更新) </span><span class="sxs-lookup"><span data-stu-id="b4110-228">When schema for the connection has been updated (schema updates are not yet supported)</span></span>

<span data-ttu-id="b4110-229">使用 **增量刷新**，搜索引擎只能处理自上次成功爬网后创建或修改的项目并编制索引。</span><span class="sxs-lookup"><span data-stu-id="b4110-229">With an **Incremental refresh**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="b4110-230">因此，并非所有内容源中数据都重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="b4110-230">Therefore, not all the data in the content source is re-indexed.</span></span> <span data-ttu-id="b4110-231">增量刷新最适合检测内容、元数据、权限和其他更新。</span><span class="sxs-lookup"><span data-stu-id="b4110-231">Incremental refreshes work best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="b4110-232">增量刷新比完全刷新快得多，因为不会处理未更改的项目。</span><span class="sxs-lookup"><span data-stu-id="b4110-232">Incremental refreshes are much faster than full refreshes because unchanged items aren’t processed.</span></span> <span data-ttu-id="b4110-233">但是，如果您选择运行增量刷新，您仍然需要定期运行完全刷新，以在内容源和搜索索引之间保持准确的数据同步。</span><span class="sxs-lookup"><span data-stu-id="b4110-233">However, if you choose to run incremental refreshes, you will still need to run full refreshes periodically to maintain an accurate data sync between the content source and the search index.</span></span>

![增量爬网和完全爬网间隔设置显示增量爬网为 15 分钟，完全爬网为 1 周。](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a><span data-ttu-id="b4110-235">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="b4110-235">Step 8: Review connection</span></span>

<span data-ttu-id="b4110-236">在完成连接之前，可以检查整个配置并根据需要编辑设置。</span><span class="sxs-lookup"><span data-stu-id="b4110-236">You can review your entire configuration and edit settings as needed before completing the connection.</span></span> <span data-ttu-id="b4110-237">**如果尚未读取数据源的连接器特定信息，请务必阅读此信息。**</span><span class="sxs-lookup"><span data-stu-id="b4110-237">**Be sure to read the connector-specific information for your data source if you have not already done so.**</span></span> <span data-ttu-id="b4110-238">选择 **"准备好完成** 连接时完成更新"。</span><span class="sxs-lookup"><span data-stu-id="b4110-238">Select **Finish updating** when you are ready to complete the connection.</span></span>

## <a name="how-do-i-know-the-connection-setup-worked"></a><span data-ttu-id="b4110-239">我如何知道连接设置有效？</span><span class="sxs-lookup"><span data-stu-id="b4110-239">How do I know the connection setup worked?</span></span>

<span data-ttu-id="b4110-240">转到管理中心的"连接器"选项卡下的已发布[连接列表](https://admin.microsoft.com)。 </span><span class="sxs-lookup"><span data-stu-id="b4110-240">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="b4110-241">若要了解如何进行更新和删除，请参阅["管理连接器"。](manage-connector.md)</span><span class="sxs-lookup"><span data-stu-id="b4110-241">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>
