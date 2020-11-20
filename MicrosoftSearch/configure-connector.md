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
ms.openlocfilehash: 86ddf0387e3d00a005f25207a322c8470799b76b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367602"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a><span data-ttu-id="cd39b-103">Microsoft 的图形连接器的安装概述</span><span class="sxs-lookup"><span data-stu-id="cd39b-103">Setup overview for Graph connectors by Microsoft</span></span> 

<span data-ttu-id="cd39b-104">本文总结了使用 [microsoft 365 管理中心](https://admin.microsoft.com) 设置 microsoft 的任何图形连接器所需的基本过程。</span><span class="sxs-lookup"><span data-stu-id="cd39b-104">This article summarizes the basic process required to use the [Microsoft 365 admin center](https://admin.microsoft.com) to setup any of the Graph connectors by Microsoft.</span></span> <span data-ttu-id="cd39b-105">基本过程包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cd39b-105">The basic process includes the following steps:</span></span>  
<!---Add links to each section in the doc--->

1. <span data-ttu-id="cd39b-106">在 Microsoft 365 管理中心中添加图形连接器。</span><span class="sxs-lookup"><span data-stu-id="cd39b-106">Add a Graph connector in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="cd39b-107">命名连接。</span><span class="sxs-lookup"><span data-stu-id="cd39b-107">Name the connection.</span></span>
3. <span data-ttu-id="cd39b-108">配置连接设置。</span><span class="sxs-lookup"><span data-stu-id="cd39b-108">Configure the connection settings.</span></span>
4. <span data-ttu-id="cd39b-109">管理搜索权限。</span><span class="sxs-lookup"><span data-stu-id="cd39b-109">Manage search permissions.</span></span>
5. <span data-ttu-id="cd39b-110">分配属性标签。</span><span class="sxs-lookup"><span data-stu-id="cd39b-110">Assign property labels.</span></span>
6. <span data-ttu-id="cd39b-111">管理架构。</span><span class="sxs-lookup"><span data-stu-id="cd39b-111">Manage schema.</span></span>
7. <span data-ttu-id="cd39b-112">选择 "刷新设置"。</span><span class="sxs-lookup"><span data-stu-id="cd39b-112">Choose refresh settings.</span></span>
8. <span data-ttu-id="cd39b-113">查看连接。</span><span class="sxs-lookup"><span data-stu-id="cd39b-113">Review the connection.</span></span>

<span data-ttu-id="cd39b-114">请务必注意，安装过程与 Microsoft 的所有图形连接器非常相似，但不完全相同。</span><span class="sxs-lookup"><span data-stu-id="cd39b-114">It is important to note that the setup process is very similar for all the Graph connectors by Microsoft but is not exactly the same.</span></span> <span data-ttu-id="cd39b-115">**除了阅读本文，请务必阅读特定于连接器的数据源。**</span><span class="sxs-lookup"><span data-stu-id="cd39b-115">**In addition to reading this article, be sure to read the connector-specific for your data source.**</span></span>  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="cd39b-116">步骤1：在 Microsoft 365 管理中心中添加图形连接器</span><span class="sxs-lookup"><span data-stu-id="cd39b-116">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="cd39b-117">完成以下步骤以配置任何 Microsoft 构建的连接器。</span><span class="sxs-lookup"><span data-stu-id="cd39b-117">Complete the following steps to configure any of the Microsoft-built connectors.</span></span>

1. <span data-ttu-id="cd39b-118">登录到您在[Microsoft 365 管理中心](https://admin.microsoft.com)的管理员帐户</span><span class="sxs-lookup"><span data-stu-id="cd39b-118">Sign into your admin account in the [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
2. <span data-ttu-id="cd39b-119">在导航窗格中，选择 " **设置**"，然后选择 " **搜索 & 智能**"。</span><span class="sxs-lookup"><span data-stu-id="cd39b-119">In the navigation pane, select **Settings**, and then select **Search & intelligence**.</span></span> <span data-ttu-id="cd39b-120">选择 " [连接器" 选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。</span><span class="sxs-lookup"><span data-stu-id="cd39b-120">Select the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).</span></span>
3.  <span data-ttu-id="cd39b-121">选择 " **+ 添加**"，然后从可用选项菜单中选择您选择的数据源。</span><span class="sxs-lookup"><span data-stu-id="cd39b-121">Select **+Add**, and then select the data source of your choice from the menu of available options.</span></span>

![可用的数据源包括： ADLS Gen2、Enterprise 网站、Microsoft SQL server、Azure SQL、Oracle SQL 数据库、ServiceNow、文件共享、Azure DevOps 和 MediaWiki。](media/add-connector.png)

><span data-ttu-id="cd39b-123">[!注意：] 最多可以向每个租户添加10个图形连接。</span><span class="sxs-lookup"><span data-stu-id="cd39b-123">[!Note:] You can add a maximum of ten Graph connections to each tenant.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="cd39b-124">步骤2：为连接命名</span><span class="sxs-lookup"><span data-stu-id="cd39b-124">Step 2: Name the connection</span></span>
<span data-ttu-id="cd39b-125">您将需要指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="cd39b-125">You will need to specify these attributes:</span></span> 

* <span data-ttu-id="cd39b-126">名称</span><span class="sxs-lookup"><span data-stu-id="cd39b-126">Name</span></span>  
* <span data-ttu-id="cd39b-127">连接 ID</span><span class="sxs-lookup"><span data-stu-id="cd39b-127">Connection ID</span></span> 
* <span data-ttu-id="cd39b-128"> (可选) 的说明</span><span class="sxs-lookup"><span data-stu-id="cd39b-128">Description (optional)</span></span> 

<span data-ttu-id="cd39b-129">连接 ID 为连接器创建隐式属性。</span><span class="sxs-lookup"><span data-stu-id="cd39b-129">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="cd39b-130">它必须仅包含字母数字字符，并且最多为32个字符。</span><span class="sxs-lookup"><span data-stu-id="cd39b-130">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span> 

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="cd39b-131">步骤3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="cd39b-131">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="cd39b-132">根据数据源的类型，配置连接设置的过程会有所不同。</span><span class="sxs-lookup"><span data-stu-id="cd39b-132">The process to configure the Connection settings varies based on the type of data source.</span></span> <span data-ttu-id="cd39b-133">若要添加到租户中的数据源类型的连接器特定信息，请参阅安装过程中完成此步骤的类型。</span><span class="sxs-lookup"><span data-stu-id="cd39b-133">See the Connector-specific information for the type of data source you want to add to your tenant to complete this step in the setup process.</span></span>  

<span data-ttu-id="cd39b-134">若要了解有关连接到本地数据源的详细信息，请参阅 [安装本地 data gateway](https://aka.ms/configuregateway)。</span><span class="sxs-lookup"><span data-stu-id="cd39b-134">To learn more about connecting to an on-premises data source, see [Install an on-premises data gateway](https://aka.ms/configuregateway).</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="cd39b-135">步骤4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="cd39b-135">Step 4: Manage search permissions</span></span>

<span data-ttu-id="cd39b-136">访问控制列表 (Acl) 确定组织中的哪些用户可以访问每个数据项。</span><span class="sxs-lookup"><span data-stu-id="cd39b-136">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span>  

<span data-ttu-id="cd39b-137">一些连接器（如 [MICROSOFT SQL](MSSQL-connector.md) 和 [Azure Data Lake Storage Gen2](azure-data-lake-connector.md) ）在 Azure [Active Directory (azure AD) ](https://docs.microsoft.com/azure/active-directory/) acl 中提供支持。</span><span class="sxs-lookup"><span data-stu-id="cd39b-137">Some connectors like [Microsoft SQL](MSSQL-connector.md) and [Azure Data Lake Storage Gen2](azure-data-lake-connector.md) natively support [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) ACLs.</span></span>

<span data-ttu-id="cd39b-138">其他连接器（如 [ServiceNow](servicenow-connector.md)、 [Azure DevOps](azure-devops-connector.md)和 [SALESFORCE](salesforce-connector.md) ）支持非 Azure AD 用户和组的同步。</span><span class="sxs-lookup"><span data-stu-id="cd39b-138">Other connectors like [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md), and [Salesforce](salesforce-connector.md) support syncing of non-Azure AD users and groups.</span></span>  

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="cd39b-139">步骤5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="cd39b-139">Step 5: Assign property labels</span></span>
<span data-ttu-id="cd39b-140">您可以在 "分配属性标签" 页上将语义标签分配给源属性。</span><span class="sxs-lookup"><span data-stu-id="cd39b-140">You can assign semantic labels to your source properties on the "Assign property labels" page.</span></span> <span data-ttu-id="cd39b-141">标签是 Microsoft 提供的已知的已知标记，提供语义含义。</span><span class="sxs-lookup"><span data-stu-id="cd39b-141">Labels are well known tags provided by Microsoft that provide semantic meaning.</span></span> <span data-ttu-id="cd39b-142">它们允许 Microsoft 将连接器数据集成到 Microsoft 365 体验中，例如增强的搜索、人员卡片、智能发现等。</span><span class="sxs-lookup"><span data-stu-id="cd39b-142">They allow Microsoft to integrate your connector data into Microsoft 365 experiences such as enhanced search, people cards, intelligent discovery, and more.</span></span>  

<span data-ttu-id="cd39b-143">下表列出了当前支持的标签及其说明。</span><span class="sxs-lookup"><span data-stu-id="cd39b-143">The following table lists the currently supported labels and their descriptions.</span></span>  

<span data-ttu-id="cd39b-144">标签</span><span class="sxs-lookup"><span data-stu-id="cd39b-144">Label</span></span> | <span data-ttu-id="cd39b-145">说明</span><span class="sxs-lookup"><span data-stu-id="cd39b-145">Description</span></span>
--- | ---  
<span data-ttu-id="cd39b-146">**title**</span><span class="sxs-lookup"><span data-stu-id="cd39b-146">**title**</span></span> | <span data-ttu-id="cd39b-147">要在搜索和其他体验中显示的项目的标题</span><span class="sxs-lookup"><span data-stu-id="cd39b-147">The title for the item that you want shown in search and other experiences</span></span> 
<span data-ttu-id="cd39b-148">**url**</span><span class="sxs-lookup"><span data-stu-id="cd39b-148">**url**</span></span> | <span data-ttu-id="cd39b-149">源系统中项的目标 url</span><span class="sxs-lookup"><span data-stu-id="cd39b-149">The target url of the item in the source system</span></span> 
<span data-ttu-id="cd39b-150">**createdBy**</span><span class="sxs-lookup"><span data-stu-id="cd39b-150">**createdBy**</span></span> | <span data-ttu-id="cd39b-151">创建项目的人员的姓名</span><span class="sxs-lookup"><span data-stu-id="cd39b-151">Name of the person who created the item</span></span> 
<span data-ttu-id="cd39b-152">**lastModifiedBy**</span><span class="sxs-lookup"><span data-stu-id="cd39b-152">**lastModifiedBy**</span></span> | <span data-ttu-id="cd39b-153">最近编辑项目的人员的姓名</span><span class="sxs-lookup"><span data-stu-id="cd39b-153">Name of the person who most recently edited the item</span></span> 
<span data-ttu-id="cd39b-154">**authors**</span><span class="sxs-lookup"><span data-stu-id="cd39b-154">**authors**</span></span> | <span data-ttu-id="cd39b-155">参与/合作项目的人员的姓名</span><span class="sxs-lookup"><span data-stu-id="cd39b-155">Name of the people who participated/collaborated on the item</span></span> 
<span data-ttu-id="cd39b-156">**createdDateTime**</span><span class="sxs-lookup"><span data-stu-id="cd39b-156">**createdDateTime**</span></span> | <span data-ttu-id="cd39b-157">项目创建时间</span><span class="sxs-lookup"><span data-stu-id="cd39b-157">When was the item created</span></span> 
<span data-ttu-id="cd39b-158">**lastModifiedDateTime**</span><span class="sxs-lookup"><span data-stu-id="cd39b-158">**lastModifiedDateTime**</span></span> | <span data-ttu-id="cd39b-159">最近编辑项目的时间</span><span class="sxs-lookup"><span data-stu-id="cd39b-159">When was the item most recently edited</span></span> 
<span data-ttu-id="cd39b-160">**fileName**</span><span class="sxs-lookup"><span data-stu-id="cd39b-160">**fileName**</span></span> | <span data-ttu-id="cd39b-161">文件项目的名称</span><span class="sxs-lookup"><span data-stu-id="cd39b-161">Name of the file item</span></span> 
<span data-ttu-id="cd39b-162">**FileExtension**</span><span class="sxs-lookup"><span data-stu-id="cd39b-162">**fileExtension**</span></span> | <span data-ttu-id="cd39b-163">文件项（如 .pdf 或 word）的类型</span><span class="sxs-lookup"><span data-stu-id="cd39b-163">Type of file item such as .pdf or .word</span></span> 

<span data-ttu-id="cd39b-164">此页面上的属性基于您的数据源预先选择，但如果存在更适合特定标签的其他属性，则可以更改此选择。</span><span class="sxs-lookup"><span data-stu-id="cd39b-164">The properties on this page are pre-selected based on your data source, but you can change this selection if there is a different property that is better suited for a particular label.</span></span>  

<span data-ttu-id="cd39b-165">标签 **标题** 是最重要的标签。</span><span class="sxs-lookup"><span data-stu-id="cd39b-165">The label **title** is the most important label.</span></span> <span data-ttu-id="cd39b-166">**强烈建议** 您为此标签分配一个属性，以便您的连接参与 [结果群集体验](result-cluster.md)。</span><span class="sxs-lookup"><span data-stu-id="cd39b-166">It is **strongly recommended** that you have a property assigned to this label in order for your connection to participate in the [result cluster experience](result-cluster.md).</span></span>

<span data-ttu-id="cd39b-167">错误映射标签将导致 deteriorated 搜索体验。</span><span class="sxs-lookup"><span data-stu-id="cd39b-167">Incorrectly mapping labels will cause a deteriorated search experience.</span></span> <span data-ttu-id="cd39b-168">对于某些标签，没有为其分配属性。</span><span class="sxs-lookup"><span data-stu-id="cd39b-168">It is okay for some labels to not have a property assigned to it.</span></span>  

## <a name="step-6-manage-schema"></a><span data-ttu-id="cd39b-169">步骤6：管理架构</span><span class="sxs-lookup"><span data-stu-id="cd39b-169">Step 6: Manage schema</span></span>

### <a name="content-property"></a><span data-ttu-id="cd39b-170">Content 属性</span><span class="sxs-lookup"><span data-stu-id="cd39b-170">Content property</span></span>

<span data-ttu-id="cd39b-171">强烈建议您从 "选项" 的下拉菜单中选择 "\* \* 内容" 属性，或保留默认值（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="cd39b-171">It is strongly recommended that you select a \*\*Content Property" from the drop-down menu of options, or keep the default if one is present.</span></span> <span data-ttu-id="cd39b-172">此属性用于对内容进行全文本索引、搜索结果页面代码段生成、 [结果群集](result-cluster.md) 参与、语言检测、HTML/文本支持、排名和相关性以及查询表述。</span><span class="sxs-lookup"><span data-stu-id="cd39b-172">This property is used for full-text indexing of content, search results page snippet generation, [result cluster](result-cluster.md) participation, language detection, HTML/text support, ranking and relevance, and query formulation.</span></span>

<span data-ttu-id="cd39b-173">如果选择内容属性，您将可以选择在 [创建结果类型](customize-results-layout.md)时使用系统生成的属性 **ResultSnippet** 。</span><span class="sxs-lookup"><span data-stu-id="cd39b-173">If you select a content property, you will have the option of using the system-generated property **ResultSnippet** when you [create your result type](customize-results-layout.md).</span></span> <span data-ttu-id="cd39b-174">此属性用作在查询时从 content 属性生成的动态代码段的占位符。</span><span class="sxs-lookup"><span data-stu-id="cd39b-174">This property serves as a placeholder for the dynamic snippets that are generated from the content property at query time.</span></span> <span data-ttu-id="cd39b-175">如果您的结果类型中使用此属性，则会在搜索结果中生成代码段。</span><span class="sxs-lookup"><span data-stu-id="cd39b-175">If you use this property in your result type, snippets will be generated in your search results.</span></span>

### <a name="creating-aliases-for-source-properties"></a><span data-ttu-id="cd39b-176">为源属性创建别名</span><span class="sxs-lookup"><span data-stu-id="cd39b-176">Creating aliases for source properties</span></span>

<span data-ttu-id="cd39b-177">可以在 "管理架构" 页上的 "别名" 列下将别名添加到属性中。</span><span class="sxs-lookup"><span data-stu-id="cd39b-177">You can add aliases to your properties under the "Alias" column on the "Manage schema" page.</span></span> <span data-ttu-id="cd39b-178">别名是属性的友好名称。</span><span class="sxs-lookup"><span data-stu-id="cd39b-178">Aliases are friendly names for your properties.</span></span> <span data-ttu-id="cd39b-179">它们在查询和创建筛选器中使用。</span><span class="sxs-lookup"><span data-stu-id="cd39b-179">They are used in queries and in the creation of filters.</span></span> <span data-ttu-id="cd39b-180">它们还可用于从多个连接中规范化源属性，以使其具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="cd39b-180">They are also used to normalize source properties from multiple connections such that they have the same name.</span></span> <span data-ttu-id="cd39b-181">通过这种方式，您可以为具有多个连接的垂直创建一个筛选器。</span><span class="sxs-lookup"><span data-stu-id="cd39b-181">That way you can create a single filter for a vertical with multiple connections.</span></span> <span data-ttu-id="cd39b-182">有关详细信息，请参阅 [自定义搜索结果页](customize-search-page.md) 。</span><span class="sxs-lookup"><span data-stu-id="cd39b-182">See [Customize the search results page](customize-search-page.md) for more information.</span></span>  

### <a name="search-schema-attributes"></a><span data-ttu-id="cd39b-183">搜索架构属性</span><span class="sxs-lookup"><span data-stu-id="cd39b-183">Search schema attributes</span></span>

<span data-ttu-id="cd39b-184">您可以设置搜索架构属性，以控制每个 source 属性的搜索功能。</span><span class="sxs-lookup"><span data-stu-id="cd39b-184">You can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="cd39b-185">搜索架构可帮助确定搜索结果页面上显示的结果以及最终用户可以查看和访问的信息。</span><span class="sxs-lookup"><span data-stu-id="cd39b-185">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="cd39b-186">搜索架构属性包括可 **搜索**、可 **查询**、可 **检索** 和 **可精简**。</span><span class="sxs-lookup"><span data-stu-id="cd39b-186">Search schema attributes include **searchable**, **queryable**, **retrievable**, and **refinable**.</span></span> <span data-ttu-id="cd39b-187">下表列出了 Microsoft Graph 连接器支持和解释其功能的每个属性。</span><span class="sxs-lookup"><span data-stu-id="cd39b-187">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="cd39b-188">搜索架构属性</span><span class="sxs-lookup"><span data-stu-id="cd39b-188">Search schema attribute</span></span> | <span data-ttu-id="cd39b-189">函数</span><span class="sxs-lookup"><span data-stu-id="cd39b-189">Function</span></span> | <span data-ttu-id="cd39b-190">示例</span><span class="sxs-lookup"><span data-stu-id="cd39b-190">Example</span></span>
--- | --- | ---
<span data-ttu-id="cd39b-191">外面</span><span class="sxs-lookup"><span data-stu-id="cd39b-191">SEARCHABLE</span></span> | <span data-ttu-id="cd39b-192">将属性的文本内容设为可搜索的。</span><span class="sxs-lookup"><span data-stu-id="cd39b-192">Makes the text content of a property searchable.</span></span> <span data-ttu-id="cd39b-193">属性内容包含在全文本索引中。</span><span class="sxs-lookup"><span data-stu-id="cd39b-193">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="cd39b-194">如果属性为 **title**，则针对 **企业** 的查询返回包含任何文本或标题中的 word **Enterprise** 的答案。</span><span class="sxs-lookup"><span data-stu-id="cd39b-194">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="cd39b-195">可</span><span class="sxs-lookup"><span data-stu-id="cd39b-195">QUERYABLE</span></span> | <span data-ttu-id="cd39b-196">按查询搜索特定属性的匹配项。</span><span class="sxs-lookup"><span data-stu-id="cd39b-196">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="cd39b-197">然后可以通过编程方式或逐字方式在查询中指定属性名称。</span><span class="sxs-lookup"><span data-stu-id="cd39b-197">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="cd39b-198">如果 **Title** 属性是可查询的，则支持查询 **标题： Enterprise** 。</span><span class="sxs-lookup"><span data-stu-id="cd39b-198">If the **Title** property is queryable, then the query **Title: Enterprise** is supported.</span></span> 
<span data-ttu-id="cd39b-199">可检索</span><span class="sxs-lookup"><span data-stu-id="cd39b-199">RETRIEVABLE</span></span> | <span data-ttu-id="cd39b-200">只能在结果类型中使用可检索的属性并显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="cd39b-200">Only retrievable properties can be used in the result type and display in the search result.</span></span> |
<span data-ttu-id="cd39b-201">可精简</span><span class="sxs-lookup"><span data-stu-id="cd39b-201">REFINABLE</span></span> | <span data-ttu-id="cd39b-202">在 Microsoft 搜索结果页中，可以使用可精简属性。</span><span class="sxs-lookup"><span data-stu-id="cd39b-202">Refinable properties can be used as in the Microsoft Search results page.</span></span> | <span data-ttu-id="cd39b-203">如果在连接设置过程中将该属性标记为可精简，则组织中的用户可以在搜索结果页中按 **lastModifiedDateTime** [筛选](custom-filters.md)。</span><span class="sxs-lookup"><span data-stu-id="cd39b-203">Users in your organization can [filter](custom-filters.md) by **lastModifiedDateTime** in the search results page if the property is marked refinable during connection setup</span></span>

<span data-ttu-id="cd39b-204">对于除文件共享连接器之外的所有连接器，必须手动设置自定义类型。</span><span class="sxs-lookup"><span data-stu-id="cd39b-204">For all connectors except the File share connector, custom types must be set manually.</span></span> <span data-ttu-id="cd39b-205">若要激活每个字段的搜索功能，您需要映射到属性列表的搜索架构。</span><span class="sxs-lookup"><span data-stu-id="cd39b-205">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="cd39b-206">"连接向导" 将根据您选择的源属性集自动选择搜索架构。</span><span class="sxs-lookup"><span data-stu-id="cd39b-206">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="cd39b-207">您可以通过选中 "搜索架构" 页中每个属性和属性的复选框来修改此架构。</span><span class="sxs-lookup"><span data-stu-id="cd39b-207">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

![可以通过添加或删除查询、搜索和检索函数来自定义连接器的架构。](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a><span data-ttu-id="cd39b-209">搜索架构设置的限制和建议</span><span class="sxs-lookup"><span data-stu-id="cd39b-209">Restrictions and recommendations for search schema settings</span></span>

* <span data-ttu-id="cd39b-210">**Content** 属性仅可搜索。</span><span class="sxs-lookup"><span data-stu-id="cd39b-210">The **content** property is searchable only.</span></span> <span data-ttu-id="cd39b-211">在下拉列表中选择此属性后，将无法将此属性标记为可 **检索** 或可 **查询**。</span><span class="sxs-lookup"><span data-stu-id="cd39b-211">Once selected in the dropdown, this property cannot be marked **retrievable** or **queryable**.</span></span>

* <span data-ttu-id="cd39b-212">当使用 **content** 属性呈现搜索结果时，会出现重大性能问题。</span><span class="sxs-lookup"><span data-stu-id="cd39b-212">Significant performance issues occur when search results render with the **content** property.</span></span> <span data-ttu-id="cd39b-213">例如， [ServiceNow](https://www.servicenow.com)知识库文章的 **文本** 内容字段。</span><span class="sxs-lookup"><span data-stu-id="cd39b-213">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>

* <span data-ttu-id="cd39b-214">仅属性在搜索结果中标记为可检索的，并且可用于创建新式结果类型 (MRTs) 。</span><span class="sxs-lookup"><span data-stu-id="cd39b-214">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>

* <span data-ttu-id="cd39b-215">只能将字符串属性标记为可搜索。</span><span class="sxs-lookup"><span data-stu-id="cd39b-215">Only string properties can be marked searchable.</span></span>

> [!NOTE]
> <span data-ttu-id="cd39b-216">创建连接后， **不能** 修改架构。</span><span class="sxs-lookup"><span data-stu-id="cd39b-216">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="cd39b-217">若要执行此操作，您需要删除连接并创建一个新的连接。</span><span class="sxs-lookup"><span data-stu-id="cd39b-217">To do that, you need to delete your connection and create a new one.</span></span>

## <a name="step-7-refresh-settings"></a><span data-ttu-id="cd39b-218">第7步：刷新设置</span><span class="sxs-lookup"><span data-stu-id="cd39b-218">Step 7: Refresh settings</span></span>

<span data-ttu-id="cd39b-219">刷新间隔决定数据在数据源和 Microsoft 搜索之间的同步频率。</span><span class="sxs-lookup"><span data-stu-id="cd39b-219">The refresh interval determines how often your data is synced between the data source and Microsoft Search.</span></span> <span data-ttu-id="cd39b-220">每种类型的数据源都有一组不同的最佳刷新计划，具体取决于修改数据的频率和修改的类型。</span><span class="sxs-lookup"><span data-stu-id="cd39b-220">Each type of data source has a different set of optimal refresh schedules based on how often data is modified and the type of modifications.</span></span>

<span data-ttu-id="cd39b-221">有两种类型的刷新间隔，即 **完全刷新** 和 **增量刷新**，但增量刷新对某些数据源不可用。</span><span class="sxs-lookup"><span data-stu-id="cd39b-221">There are two types of refresh intervals, which are **Full refresh** and **Incremental refresh**, but incremental refreshes are not available for some data sources.</span></span>

<span data-ttu-id="cd39b-222">通过完全刷新，搜索引擎将处理内容源中的每个项目并对其进行索引，而不考虑以前的爬网。</span><span class="sxs-lookup"><span data-stu-id="cd39b-222">With a full refresh, the search engine processes and indexes every item in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="cd39b-223">完全刷新最适用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="cd39b-223">A full refresh works best for these situations:</span></span>

* <span data-ttu-id="cd39b-224">检测数据删除。</span><span class="sxs-lookup"><span data-stu-id="cd39b-224">Detecting deletions of data.</span></span>
* <span data-ttu-id="cd39b-225">由于错误，增量刷新无法更新内容。</span><span class="sxs-lookup"><span data-stu-id="cd39b-225">The incremental refresh failed to update content due to errors.</span></span>
* <span data-ttu-id="cd39b-226">已修改 Acl。</span><span class="sxs-lookup"><span data-stu-id="cd39b-226">ACLs were modified.</span></span>
* <span data-ttu-id="cd39b-227">修改了爬网规则。</span><span class="sxs-lookup"><span data-stu-id="cd39b-227">Crawl rules were modified.</span></span>
* <span data-ttu-id="cd39b-228">如果已更新连接的架构 (尚不支持架构更新) </span><span class="sxs-lookup"><span data-stu-id="cd39b-228">When schema for the connection has been updated (schema updates are not yet supported)</span></span>

<span data-ttu-id="cd39b-229">使用 **增量刷新** 时，搜索引擎只能处理自上次成功爬网后创建或修改的项目，并对其编制索引。</span><span class="sxs-lookup"><span data-stu-id="cd39b-229">With an **Incremental refresh**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="cd39b-230">因此，并不会对内容源中的所有数据重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="cd39b-230">Therefore, not all the data in the content source is re-indexed.</span></span> <span data-ttu-id="cd39b-231">增量刷新最佳工作以检测内容、元数据、权限和其他更新。</span><span class="sxs-lookup"><span data-stu-id="cd39b-231">Incremental refreshes work best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="cd39b-232">增量刷新比完全刷新速度快得多，因为未处理未更改的项目。</span><span class="sxs-lookup"><span data-stu-id="cd39b-232">Incremental refreshes are much faster than full refreshes because unchanged items aren’t processed.</span></span> <span data-ttu-id="cd39b-233">但是，如果您选择运行增量刷新，您仍需要定期运行完全刷新，以保持内容源与搜索索引之间的准确数据同步。</span><span class="sxs-lookup"><span data-stu-id="cd39b-233">However, if you choose to run incremental refreshes, you will still need to run full refreshes periodically to maintain an accurate data sync between the content source and the search index.</span></span>

![增量爬网和完全爬网间隔设置，显示15分钟的增量和一周的完全爬网。](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a><span data-ttu-id="cd39b-235">步骤8：查看连接</span><span class="sxs-lookup"><span data-stu-id="cd39b-235">Step 8: Review connection</span></span>

<span data-ttu-id="cd39b-236">您可以根据需要查看整个配置并编辑设置，然后再完成连接。</span><span class="sxs-lookup"><span data-stu-id="cd39b-236">You can review your entire configuration and edit settings as needed before completing the connection.</span></span> <span data-ttu-id="cd39b-237">**如果尚未阅读数据源连接器的特定信息，请务必阅读。**</span><span class="sxs-lookup"><span data-stu-id="cd39b-237">**Be sure to read the connector-specific information for your data source if you have not already done so.**</span></span> <span data-ttu-id="cd39b-238">准备好完成连接后，选择 " **完成更新** "。</span><span class="sxs-lookup"><span data-stu-id="cd39b-238">Select **Finish updating** when you are ready to complete the connection.</span></span>

## <a name="how-do-i-know-the-connection-setup-worked"></a><span data-ttu-id="cd39b-239">我如何知道连接设置正常工作？</span><span class="sxs-lookup"><span data-stu-id="cd39b-239">How do I know the connection setup worked?</span></span>

<span data-ttu-id="cd39b-240">转到 "[管理中心](https://admin.microsoft.com)" 的 "**连接器**" 选项卡下的已发布连接列表。</span><span class="sxs-lookup"><span data-stu-id="cd39b-240">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="cd39b-241">若要了解如何进行更新和删除，请参阅 [管理连接器](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="cd39b-241">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>
