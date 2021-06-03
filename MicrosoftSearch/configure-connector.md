---
title: 配置 Microsoft 为 Microsoft 搜索Graph连接器
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
description: Microsoft Graph连接器的设置概述
ms.openlocfilehash: ef94d530af63d8b8b33dfae3c4b411164ef31feb
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720940"
---
<!-- Previous ms.author: monaray -->

<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a><span data-ttu-id="73a38-103">Microsoft Graph连接器的设置概述</span><span class="sxs-lookup"><span data-stu-id="73a38-103">Setup overview for Graph connectors by Microsoft</span></span> 

<span data-ttu-id="73a38-104">本文介绍了在管理中心中Graph **Microsoft** 设置 Microsoft 365 [连接器所需的基本过程](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="73a38-104">This article shows the basic process required to set up the Graph connectors **by Microsoft** in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="73a38-105">基本流程包括以下步骤:</span><span class="sxs-lookup"><span data-stu-id="73a38-105">The basic process includes the following steps:</span></span>  
<!---Add links to each section in the doc--->

1. [<span data-ttu-id="73a38-106">在 Graph 管理中心Microsoft 365连接器</span><span class="sxs-lookup"><span data-stu-id="73a38-106">Add a Graph connector in the Microsoft 365 admin center</span></span>](#step-1-add-a-graph-connector-in-the-microsoft-365-admin-center)
2. [<span data-ttu-id="73a38-107">命名连接</span><span class="sxs-lookup"><span data-stu-id="73a38-107">Name the connection</span></span>](#step-2-name-the-connection)
3. [<span data-ttu-id="73a38-108">配置连接设置</span><span class="sxs-lookup"><span data-stu-id="73a38-108">Configure the connection settings</span></span>](#step-3-configure-the-connection-settings)
4. [<span data-ttu-id="73a38-109">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="73a38-109">Manage search permissions</span></span>](#step-4-manage-search-permissions)
5. [<span data-ttu-id="73a38-110">分配属性标签</span><span class="sxs-lookup"><span data-stu-id="73a38-110">Assign property labels</span></span>](#step-5-assign-property-labels)
6. [<span data-ttu-id="73a38-111">管理架构</span><span class="sxs-lookup"><span data-stu-id="73a38-111">Manage schema</span></span>](#step-6-manage-schema)
7. [<span data-ttu-id="73a38-112">刷新设置</span><span class="sxs-lookup"><span data-stu-id="73a38-112">Refresh settings</span></span>](#step-7-refresh-settings)
8. [<span data-ttu-id="73a38-113">查看连接</span><span class="sxs-lookup"><span data-stu-id="73a38-113">Review connection</span></span>](#step-8-review-connection)

<span data-ttu-id="73a38-114">本文还包括有关疑难解答、限制和下一步步骤的信息：</span><span class="sxs-lookup"><span data-stu-id="73a38-114">This article also includes information about troubleshooting, limitations, and next steps:</span></span>

* [<span data-ttu-id="73a38-115">疑难解答</span><span class="sxs-lookup"><span data-stu-id="73a38-115">Troubleshooting</span></span>](#troubleshooting)
* [<span data-ttu-id="73a38-116">限制</span><span class="sxs-lookup"><span data-stu-id="73a38-116">Limitations</span></span>](#limitations)
* [<span data-ttu-id="73a38-117">后续步骤</span><span class="sxs-lookup"><span data-stu-id="73a38-117">Next steps</span></span>](#next-steps)

> [!NOTE]
> <span data-ttu-id="73a38-118">Microsoft 的所有连接器的安装过程Graph类似，但不完全相同。</span><span class="sxs-lookup"><span data-stu-id="73a38-118">The setup process is similar for all the Graph connectors by Microsoft but is not exactly the same.</span></span> <span data-ttu-id="73a38-119">**除了阅读本文之外，还请务必阅读数据源的连接器特定信息。**</span><span class="sxs-lookup"><span data-stu-id="73a38-119">**In addition to reading this article, be sure to read the connector-specific information for your data source.**</span></span>  

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="73a38-120">步骤 1：在Graph管理中心中添加Microsoft 365连接器</span><span class="sxs-lookup"><span data-stu-id="73a38-120">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="73a38-121">完成以下步骤以配置任何 Microsoft 构建Graph连接器：</span><span class="sxs-lookup"><span data-stu-id="73a38-121">Complete the following steps to configure any of the Microsoft-built Graph connectors:</span></span>

1. <span data-ttu-id="73a38-122">在管理中心 中Microsoft 365[管理员帐户](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="73a38-122">Sign into your admin account in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

2. <span data-ttu-id="73a38-123">在导航窗格中，**选择**"设置"，然后选择"搜索&**智能"。**</span><span class="sxs-lookup"><span data-stu-id="73a38-123">In the navigation pane, select **Settings**, and then select **Search & intelligence**.</span></span> <span data-ttu-id="73a38-124">选择" [连接器"选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。</span><span class="sxs-lookup"><span data-stu-id="73a38-124">Select the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).</span></span>

3. <span data-ttu-id="73a38-125">选择 **"+** 添加"，然后从可用选项的菜单中选择你选择的数据源。</span><span class="sxs-lookup"><span data-stu-id="73a38-125">Select **+Add**, and then select the data source of your choice from the menu of available options.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="73a38-126">![可用的数据源包括：ADLS Gen2、Enterprise 网站、Microsoft SQL 服务器、Azure SQL、Oracle SQL 数据库、ServiceNow、文件共享、Azure DevOps 和 MediaWiki。](media/add-connector.png)</span><span class="sxs-lookup"><span data-stu-id="73a38-126">![Data sources available include: ADLS Gen2, Enterprise websites, Microsoft SQL server, Azure SQL, Oracle SQL database, ServiceNow, File share, Azure DevOps, and MediaWiki.](media/add-connector.png)</span></span>

> [!NOTE]
> <span data-ttu-id="73a38-127">最多可以向每个租户添加 10 Graph连接。</span><span class="sxs-lookup"><span data-stu-id="73a38-127">You can add a maximum of ten Graph connections to each tenant.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="73a38-128">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="73a38-128">Step 2: Name the connection</span></span>

<span data-ttu-id="73a38-129">指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="73a38-129">Specify these attributes:</span></span>

* <span data-ttu-id="73a38-130">Name（必选）</span><span class="sxs-lookup"><span data-stu-id="73a38-130">Name (required)</span></span>
* <span data-ttu-id="73a38-131">连接 ID (是必需的) </span><span class="sxs-lookup"><span data-stu-id="73a38-131">Connection ID (required)</span></span>
* <span data-ttu-id="73a38-132">说明 (可选) </span><span class="sxs-lookup"><span data-stu-id="73a38-132">Description (optional)</span></span>

<span data-ttu-id="73a38-133">连接 ID 为连接器创建隐式属性。</span><span class="sxs-lookup"><span data-stu-id="73a38-133">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="73a38-134">它只能包含字母数字字符，并且最多包含 32 个字符。</span><span class="sxs-lookup"><span data-stu-id="73a38-134">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span>

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="73a38-135">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="73a38-135">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="73a38-136">配置连接设置的过程因数据源的类型而异。</span><span class="sxs-lookup"><span data-stu-id="73a38-136">The process to configure the connection settings varies based on the type of data source.</span></span> <span data-ttu-id="73a38-137">有关要添加到租户的数据源类型，请参阅特定于连接器的信息，以在设置过程中完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="73a38-137">See the Connector-specific information for the type of data source you want to add to your tenant to complete this step in the setup process.</span></span>  

<span data-ttu-id="73a38-138">若要了解有关连接到本地数据源的更多信息，请参阅安装 [本地数据网关](/data-integration/gateway/service-gateway-install)。</span><span class="sxs-lookup"><span data-stu-id="73a38-138">To learn more about connecting to an on-premises data source, see [Install an on-premises data gateway](/data-integration/gateway/service-gateway-install).</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="73a38-139">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="73a38-139">Step 4: Manage search permissions</span></span>

<span data-ttu-id="73a38-140">访问控制列表 (ACL) 确定组织中哪些用户可以访问每一项数据。</span><span class="sxs-lookup"><span data-stu-id="73a38-140">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span>  

<span data-ttu-id="73a38-141">一些连接器（如[Microsoft SQL](MSSQL-connector.md)和 Azure Data Lake[存储 Gen2）](azure-data-lake-connector.md)在本机Azure Active Directory ([Azure AD) ](/azure/active-directory/) ACL。</span><span class="sxs-lookup"><span data-stu-id="73a38-141">Some connectors like [Microsoft SQL](MSSQL-connector.md) and [Azure Data Lake Storage Gen2](azure-data-lake-connector.md) natively support [Azure Active Directory (Azure AD)](/azure/active-directory/) ACLs.</span></span>

<span data-ttu-id="73a38-142">其他连接器（如[ServiceNow、Azure DevOps](servicenow-connector.md)和[](azure-devops-connector.md)[Salesforce）](salesforce-connector.md)支持同步非 Azure AD 用户和组。</span><span class="sxs-lookup"><span data-stu-id="73a38-142">Other connectors like [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md), and [Salesforce](salesforce-connector.md) support syncing of non-Azure AD users and groups.</span></span>  

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="73a38-143">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="73a38-143">Step 5: Assign property labels</span></span>

<span data-ttu-id="73a38-144">可以在"分配属性标签"页上将语义标签分配给源属性。</span><span class="sxs-lookup"><span data-stu-id="73a38-144">You can assign semantic labels to your source properties on the "Assign property labels" page.</span></span> <span data-ttu-id="73a38-145">标签是 Microsoft 提供的已知标记，可提供语义含义。</span><span class="sxs-lookup"><span data-stu-id="73a38-145">Labels are well-known tags provided by Microsoft that provide semantic meaning.</span></span> <span data-ttu-id="73a38-146">它们允许 Microsoft 将连接器数据集成到Microsoft 365体验，如增强的搜索、人员卡片、智能发现等。</span><span class="sxs-lookup"><span data-stu-id="73a38-146">They allow Microsoft to integrate your connector data into Microsoft 365 experiences such as enhanced search, people cards, intelligent discovery, and more.</span></span>  

<span data-ttu-id="73a38-147">下表列出了当前支持的标签及其说明。</span><span class="sxs-lookup"><span data-stu-id="73a38-147">The following table lists the currently supported labels and their descriptions.</span></span>  

<span data-ttu-id="73a38-148">标签</span><span class="sxs-lookup"><span data-stu-id="73a38-148">Label</span></span> | <span data-ttu-id="73a38-149">说明</span><span class="sxs-lookup"><span data-stu-id="73a38-149">Description</span></span>
--- | ---  
<span data-ttu-id="73a38-150">**title**</span><span class="sxs-lookup"><span data-stu-id="73a38-150">**title**</span></span> | <span data-ttu-id="73a38-151">您希望在搜索和其他体验中显示的项目的标题</span><span class="sxs-lookup"><span data-stu-id="73a38-151">The title for the item that you want shown in search and other experiences</span></span>
<span data-ttu-id="73a38-152">**url**</span><span class="sxs-lookup"><span data-stu-id="73a38-152">**url**</span></span> | <span data-ttu-id="73a38-153">源系统中项的目标 URL</span><span class="sxs-lookup"><span data-stu-id="73a38-153">The target url of the item in the source system</span></span>
<span data-ttu-id="73a38-154">**createdBy**</span><span class="sxs-lookup"><span data-stu-id="73a38-154">**createdBy**</span></span> | <span data-ttu-id="73a38-155">创建项目的人的名称</span><span class="sxs-lookup"><span data-stu-id="73a38-155">Name of the person who created the item</span></span>
<span data-ttu-id="73a38-156">**lastModifiedBy**</span><span class="sxs-lookup"><span data-stu-id="73a38-156">**lastModifiedBy**</span></span> | <span data-ttu-id="73a38-157">最近编辑项目的人的姓名</span><span class="sxs-lookup"><span data-stu-id="73a38-157">Name of the person who most recently edited the item</span></span>
<span data-ttu-id="73a38-158">**authors**</span><span class="sxs-lookup"><span data-stu-id="73a38-158">**authors**</span></span> | <span data-ttu-id="73a38-159">参与/协作项目人员的姓名</span><span class="sxs-lookup"><span data-stu-id="73a38-159">Name of the people who participated/collaborated on the item</span></span>
<span data-ttu-id="73a38-160">**createdDateTime**</span><span class="sxs-lookup"><span data-stu-id="73a38-160">**createdDateTime**</span></span> | <span data-ttu-id="73a38-161">项目创建时间</span><span class="sxs-lookup"><span data-stu-id="73a38-161">When was the item created</span></span>
<span data-ttu-id="73a38-162">**lastModifiedDateTime**</span><span class="sxs-lookup"><span data-stu-id="73a38-162">**lastModifiedDateTime**</span></span> | <span data-ttu-id="73a38-163">最近编辑的项目何时</span><span class="sxs-lookup"><span data-stu-id="73a38-163">When was the item most recently edited</span></span>
<span data-ttu-id="73a38-164">**fileName**</span><span class="sxs-lookup"><span data-stu-id="73a38-164">**fileName**</span></span> | <span data-ttu-id="73a38-165">文件项的名称</span><span class="sxs-lookup"><span data-stu-id="73a38-165">Name of the file item</span></span>
<span data-ttu-id="73a38-166">**FileExtension**</span><span class="sxs-lookup"><span data-stu-id="73a38-166">**fileExtension**</span></span> | <span data-ttu-id="73a38-167">文件项的类型，如 .pdf 或 .word</span><span class="sxs-lookup"><span data-stu-id="73a38-167">Type of file item such as .pdf or .word</span></span>

<span data-ttu-id="73a38-168">此页上的属性根据数据源预先选择，但如果有更适合特定标签的不同属性，可以更改此选择。</span><span class="sxs-lookup"><span data-stu-id="73a38-168">The properties on this page are pre-selected based on your data source, but you can change this selection if there's a different property that is better suited for a particular label.</span></span>  

<span data-ttu-id="73a38-169">标签 **标题** 是最重要的标签。</span><span class="sxs-lookup"><span data-stu-id="73a38-169">The label **title** is the most important label.</span></span> <span data-ttu-id="73a38-170">强烈建议 **你为此** 标签分配一个属性，以便你的连接参与结果 [群集体验](result-cluster.md)。</span><span class="sxs-lookup"><span data-stu-id="73a38-170">It's **strongly recommended** you have a property assigned to this label in order for your connection to participate in the [result cluster experience](result-cluster.md).</span></span>

<span data-ttu-id="73a38-171">映射标签不正确会导致搜索体验下降。</span><span class="sxs-lookup"><span data-stu-id="73a38-171">Incorrectly mapping labels will cause a deteriorated search experience.</span></span> <span data-ttu-id="73a38-172">可以不为某些标签分配属性。</span><span class="sxs-lookup"><span data-stu-id="73a38-172">It's okay for some labels to not have a property assigned to it.</span></span>  

## <a name="step-6-manage-schema"></a><span data-ttu-id="73a38-173">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="73a38-173">Step 6: Manage schema</span></span>

### <a name="content-property"></a><span data-ttu-id="73a38-174">Content 属性</span><span class="sxs-lookup"><span data-stu-id="73a38-174">Content property</span></span>

<span data-ttu-id="73a38-175">建议从选项的下拉菜单中选择" **内容** 属性"，或保留默认值（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="73a38-175">It's recommended you select a **Content Property** from the drop-down menu of options, or keep the default if one is present.</span></span> <span data-ttu-id="73a38-176">此属性用于内容全文索引编制、搜索结果页面代码段生成、结果 [群集参与、](result-cluster.md) 语言检测、HTML/文本支持、排名和相关性以及查询整理。</span><span class="sxs-lookup"><span data-stu-id="73a38-176">This property is used for full-text indexing of content, search results page snippet generation, [result cluster](result-cluster.md) participation, language detection, HTML/text support, ranking and relevance, and query formulation.</span></span>

<span data-ttu-id="73a38-177">如果选择内容属性，则创建结果类型时，可以选择使用系统生成的属性 **ResultSnippet。** [](customize-results-layout.md)</span><span class="sxs-lookup"><span data-stu-id="73a38-177">If you select a content property, you will have the option of using the system-generated property **ResultSnippet** when you [create your result type](customize-results-layout.md).</span></span> <span data-ttu-id="73a38-178">此属性充当查询时从 content 属性生成的动态代码段的占位符。</span><span class="sxs-lookup"><span data-stu-id="73a38-178">This property serves as a placeholder for the dynamic snippets that are generated from the content property at query time.</span></span> <span data-ttu-id="73a38-179">如果在结果类型中使用此属性，将在搜索结果中生成代码段。</span><span class="sxs-lookup"><span data-stu-id="73a38-179">If you use this property in your result type, snippets will be generated in your search results.</span></span>

### <a name="creating-aliases-for-source-properties"></a><span data-ttu-id="73a38-180">为源属性创建别名</span><span class="sxs-lookup"><span data-stu-id="73a38-180">Creating aliases for source properties</span></span>

<span data-ttu-id="73a38-181">您可以在"管理架构"页上的"别名"列下向属性添加别名。</span><span class="sxs-lookup"><span data-stu-id="73a38-181">You can add aliases to your properties under the "Alias" column on the "Manage schema" page.</span></span> <span data-ttu-id="73a38-182">别名是属性的友好名称，也用于查询和筛选器创建。</span><span class="sxs-lookup"><span data-stu-id="73a38-182">Aliases are friendly names for your properties, and also used in queries and in the creation of filters.</span></span> <span data-ttu-id="73a38-183">它们还用于规范化来自多个连接的源属性，这样它们具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="73a38-183">They're also used to normalize source properties from multiple connections such that they have the same name.</span></span> <span data-ttu-id="73a38-184">这样，你可以为具有多个连接的垂直创建单个筛选器。</span><span class="sxs-lookup"><span data-stu-id="73a38-184">That way you can create a single filter for a vertical with multiple connections.</span></span> <span data-ttu-id="73a38-185">有关详细信息，请参阅 [自定义搜索结果页面](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="73a38-185">For more information, see [Customize the search results page](customize-search-page.md).</span></span>  

### <a name="search-schema-attributes"></a><span data-ttu-id="73a38-186">搜索架构属性</span><span class="sxs-lookup"><span data-stu-id="73a38-186">Search schema attributes</span></span>

<span data-ttu-id="73a38-187">您可以设置搜索架构属性来控制每个源属性的搜索功能。</span><span class="sxs-lookup"><span data-stu-id="73a38-187">You can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="73a38-188">搜索架构可帮助确定搜索结果页面上显示哪些结果，以及最终用户可以查看和访问的信息。</span><span class="sxs-lookup"><span data-stu-id="73a38-188">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="73a38-189">搜索架构属性包括查询、**搜索、\*\*\*\*检索和** 优化 **的选项**。</span><span class="sxs-lookup"><span data-stu-id="73a38-189">Search schema attributes include options to **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="73a38-190">下表列出了 Microsoft 连接器支持的每个Graph并解释了它们的功能。</span><span class="sxs-lookup"><span data-stu-id="73a38-190">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="73a38-191">搜索架构属性</span><span class="sxs-lookup"><span data-stu-id="73a38-191">Search schema attribute</span></span> | <span data-ttu-id="73a38-192">函数</span><span class="sxs-lookup"><span data-stu-id="73a38-192">Function</span></span> | <span data-ttu-id="73a38-193">示例</span><span class="sxs-lookup"><span data-stu-id="73a38-193">Example</span></span>
--- | --- | ---
<span data-ttu-id="73a38-194">SEARCH</span><span class="sxs-lookup"><span data-stu-id="73a38-194">SEARCH</span></span> | <span data-ttu-id="73a38-195">使属性的文本内容可搜索。</span><span class="sxs-lookup"><span data-stu-id="73a38-195">Makes the text content of a property searchable.</span></span> <span data-ttu-id="73a38-196">属性内容包含在全文索引中。</span><span class="sxs-lookup"><span data-stu-id="73a38-196">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="73a38-197">如果属性为 **title**，则查询Enterprise返回包含单词 **Enterprise文本** 或标题中的结果。</span><span class="sxs-lookup"><span data-stu-id="73a38-197">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="73a38-198">QUERY</span><span class="sxs-lookup"><span data-stu-id="73a38-198">QUERY</span></span> | <span data-ttu-id="73a38-199">通过查询来搜索特定属性的匹配项。</span><span class="sxs-lookup"><span data-stu-id="73a38-199">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="73a38-200">然后，可以在查询中以编程方式或详细方式指定属性名称。</span><span class="sxs-lookup"><span data-stu-id="73a38-200">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="73a38-201">如果可以查询 **Title** 属性，则支持查询 **Title： Enterprise。**</span><span class="sxs-lookup"><span data-stu-id="73a38-201">If the **Title** property can be queried, then the query **Title: Enterprise** is supported.</span></span>
<span data-ttu-id="73a38-202">检索</span><span class="sxs-lookup"><span data-stu-id="73a38-202">RETRIEVE</span></span> | <span data-ttu-id="73a38-203">结果类型中只能使用可检索属性，并显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="73a38-203">Only retrievable properties can be used in the result type and display in the search result.</span></span> |
<span data-ttu-id="73a38-204">优化</span><span class="sxs-lookup"><span data-stu-id="73a38-204">REFINE</span></span> | <span data-ttu-id="73a38-205">精简选项可在"Microsoft 搜索结果"页中一样使用。</span><span class="sxs-lookup"><span data-stu-id="73a38-205">The refine option can be used as in the Microsoft Search results page.</span></span> | <span data-ttu-id="73a38-206">如果在连接设置 [过程中](custom-filters.md) 标记了精简属性，则贵组织的用户可以在搜索结果页中按 **URL** 进行筛选</span><span class="sxs-lookup"><span data-stu-id="73a38-206">Users in your organization can [filter](custom-filters.md) by **URL** in the search results page if the refine property is marked during connection setup</span></span>

<span data-ttu-id="73a38-207">对于除文件共享连接器之外的所有连接器，必须手动设置自定义类型。</span><span class="sxs-lookup"><span data-stu-id="73a38-207">For all connectors except the File share connector, custom types must be set manually.</span></span> <span data-ttu-id="73a38-208">若要激活每个字段的搜索功能，您需要映射到属性列表的搜索架构。</span><span class="sxs-lookup"><span data-stu-id="73a38-208">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="73a38-209">连接向导根据选择的源属性集自动选择搜索架构。</span><span class="sxs-lookup"><span data-stu-id="73a38-209">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="73a38-210">您可以通过选中搜索架构页中每个属性和属性的复选框来修改此架构。</span><span class="sxs-lookup"><span data-stu-id="73a38-210">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="73a38-211">![连接器的架构可以通过添加或删除查询、搜索和检索功能来自定义。](media/manageschema.png)</span><span class="sxs-lookup"><span data-stu-id="73a38-211">![Schema for a connector can be customized by adding or removing Query, Search, and Retrieve functions.](media/manageschema.png)</span></span>

### <a name="restrictions-and-recommendations-for-search-schema-settings"></a><span data-ttu-id="73a38-212">搜索架构设置的限制和建议</span><span class="sxs-lookup"><span data-stu-id="73a38-212">Restrictions and recommendations for search schema settings</span></span>

* <span data-ttu-id="73a38-213">**content** 属性只能搜索。</span><span class="sxs-lookup"><span data-stu-id="73a38-213">The **content** property is searchable only.</span></span> <span data-ttu-id="73a38-214">在下拉列表中选中后，此属性不能与检索或查询 **选项\*\*\*\*一起使用**。</span><span class="sxs-lookup"><span data-stu-id="73a38-214">Once selected in the dropdown, this property cannot be used with the options **retrieve** or **query**.</span></span>

* <span data-ttu-id="73a38-215">当使用 content 属性呈现搜索结果时，会发生 **重大** 性能问题。</span><span class="sxs-lookup"><span data-stu-id="73a38-215">Significant performance issues occur when search results render with the **content** property.</span></span> <span data-ttu-id="73a38-216">例如 **，ServiceNow** 知识库文章的文本 [](https://www.servicenow.com)内容字段。</span><span class="sxs-lookup"><span data-stu-id="73a38-216">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>

* <span data-ttu-id="73a38-217">只有标记为可检索的属性才能呈现在搜索结果中，并可用于在 MRT 中 (新式) 。</span><span class="sxs-lookup"><span data-stu-id="73a38-217">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>

* <span data-ttu-id="73a38-218">只能将字符串属性标记为可搜索。</span><span class="sxs-lookup"><span data-stu-id="73a38-218">Only string properties can be marked searchable.</span></span>

> [!NOTE]
> <span data-ttu-id="73a38-219">创建连接后， **无法修改** 架构。</span><span class="sxs-lookup"><span data-stu-id="73a38-219">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="73a38-220">为此，需要删除连接并创建一个新连接。</span><span class="sxs-lookup"><span data-stu-id="73a38-220">To do that, you need to delete your connection and create a new one.</span></span>

## <a name="step-7-refresh-settings"></a><span data-ttu-id="73a38-221">步骤 7：刷新设置</span><span class="sxs-lookup"><span data-stu-id="73a38-221">Step 7: Refresh settings</span></span>

<span data-ttu-id="73a38-222">刷新间隔确定数据在数据源和 Microsoft 搜索之间同步频率。</span><span class="sxs-lookup"><span data-stu-id="73a38-222">The refresh interval determines how often your data is synced between the data source and Microsoft Search.</span></span> <span data-ttu-id="73a38-223">根据数据的修改频率和修改类型，每种类型的数据源都有一组不同的最佳刷新计划。</span><span class="sxs-lookup"><span data-stu-id="73a38-223">Each type of data source has a different set of optimal refresh schedules based on how often data is modified and the type of modifications.</span></span>

<span data-ttu-id="73a38-224">有两种类型的刷新间隔，即"完全刷新"和"增量刷新"，但增量刷新不适用于某些数据源。</span><span class="sxs-lookup"><span data-stu-id="73a38-224">There are two types of refresh intervals, which are **Full refresh** and **Incremental refresh**, but incremental refreshes aren't available for some data sources.</span></span>

<span data-ttu-id="73a38-225">在完全刷新后，搜索引擎将处理和索引内容源中已更改的项目，而不考虑以前的爬网。</span><span class="sxs-lookup"><span data-stu-id="73a38-225">With a full refresh, the search engine processes and indexes the items that have changed in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="73a38-226">完全刷新最适合以下情形：</span><span class="sxs-lookup"><span data-stu-id="73a38-226">A full refresh works best for these situations:</span></span>

* <span data-ttu-id="73a38-227">检测数据的删除。</span><span class="sxs-lookup"><span data-stu-id="73a38-227">Detecting deletions of data.</span></span>
* <span data-ttu-id="73a38-228">增量刷新发现错误，但失败。</span><span class="sxs-lookup"><span data-stu-id="73a38-228">The incremental refresh found errors, and failed.</span></span>
* <span data-ttu-id="73a38-229">ACL 已修改。</span><span class="sxs-lookup"><span data-stu-id="73a38-229">ACLs were modified.</span></span>
* <span data-ttu-id="73a38-230">已修改爬网规则。</span><span class="sxs-lookup"><span data-stu-id="73a38-230">Crawl rules were modified.</span></span>
* <span data-ttu-id="73a38-231">连接架构已更新， (架构更新不受支持) 。</span><span class="sxs-lookup"><span data-stu-id="73a38-231">The schema for the connection has been updated (schema updates aren't yet supported).</span></span>

<span data-ttu-id="73a38-232">使用 **增量刷新**，搜索引擎只能处理自上次成功爬网后创建或修改的项目并编制索引。</span><span class="sxs-lookup"><span data-stu-id="73a38-232">With an **Incremental refresh**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="73a38-233">因此，并非所有内容源中的数据都重新索引。</span><span class="sxs-lookup"><span data-stu-id="73a38-233">As a result, not all the data in the content source is reindexed.</span></span> <span data-ttu-id="73a38-234">增量刷新最能够检测内容、元数据、权限和其他更新。</span><span class="sxs-lookup"><span data-stu-id="73a38-234">Incremental refreshes work best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="73a38-235">增量刷新比完全刷新快得多，因为不会处理未更改的项目。</span><span class="sxs-lookup"><span data-stu-id="73a38-235">Incremental refreshes are much faster than full refreshes because unchanged items aren't processed.</span></span> <span data-ttu-id="73a38-236">但是，如果您选择运行增量刷新，您仍然需要定期运行完全刷新，以在内容源和搜索索引之间保持正确的数据同步。</span><span class="sxs-lookup"><span data-stu-id="73a38-236">However, if you choose to run incremental refreshes, you still need to run full refreshes periodically to maintain correct data sync between the content source and the search index.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="73a38-237">![增量爬网和完全爬网间隔设置显示"增量为 15 分钟"和"完全爬网为 1 周"。](media/refreshschedule.png)</span><span class="sxs-lookup"><span data-stu-id="73a38-237">![Incremental crawl and full crawl interval settings showing Incremental at 15 minutes and Full crawl at 1 week.](media/refreshschedule.png)</span></span>

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a><span data-ttu-id="73a38-238">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="73a38-238">Step 8: Review connection</span></span>

<span data-ttu-id="73a38-239">可以在完成连接前查看整个配置并根据需要编辑设置。</span><span class="sxs-lookup"><span data-stu-id="73a38-239">You can review your entire configuration and edit settings as needed before completing the connection.</span></span> <span data-ttu-id="73a38-240">**如果尚未阅读，请务必阅读数据源的连接器特定信息。**</span><span class="sxs-lookup"><span data-stu-id="73a38-240">**Be sure to read the connector-specific information for your data source if you haven't already done so.**</span></span> <span data-ttu-id="73a38-241">准备好 **完成连接** 后，选择"完成更新"。</span><span class="sxs-lookup"><span data-stu-id="73a38-241">Select **Finish updating** when you're ready to complete the connection.</span></span>

### <a name="confirm-if-the-connection-setup-worked"></a><span data-ttu-id="73a38-242">确认连接设置是否有效</span><span class="sxs-lookup"><span data-stu-id="73a38-242">Confirm if the connection setup worked</span></span>

<span data-ttu-id="73a38-243">转到管理中心中"连接器"选项卡下的已发布连接[列表](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="73a38-243">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="73a38-244">若要了解如何进行更新和删除，请参阅 [管理连接器](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="73a38-244">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="73a38-245">疑难解答</span><span class="sxs-lookup"><span data-stu-id="73a38-245">Troubleshooting</span></span>
<!---Insert troubleshooting recommendations for this data source-->
<span data-ttu-id="73a38-246">读取数据源的连接器特定信息。</span><span class="sxs-lookup"><span data-stu-id="73a38-246">Read the connector-specific information for your data source.</span></span> 

> [!NOTE]
> <span data-ttu-id="73a38-247">此时，并非所有特定于连接器的文章都包括疑难解答建议。</span><span class="sxs-lookup"><span data-stu-id="73a38-247">Not all connector-specific articles include troubleshooting recommendations at this point.</span></span>

## <a name="limitations"></a><span data-ttu-id="73a38-248">限制</span><span class="sxs-lookup"><span data-stu-id="73a38-248">Limitations</span></span>
<!---Insert limitations for this data source-->
<span data-ttu-id="73a38-249">若要了解适用于所有数据源的限制，请参阅 Microsoft Graph[概述](connectors-overview.md)文章。</span><span class="sxs-lookup"><span data-stu-id="73a38-249">To learn about limitations that apply to all data sources see the [Overview of Microsoft Graph connectors](connectors-overview.md) article.</span></span>

<span data-ttu-id="73a38-250">请参阅数据源的特定于连接器的信息，了解该特定连接器是否Graph限制。</span><span class="sxs-lookup"><span data-stu-id="73a38-250">See the connector-specific information for your data source to find out if other limitations apply to that  particular Graph connector.</span></span>

## <a name="next-steps"></a><span data-ttu-id="73a38-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="73a38-251">Next steps</span></span>

<span data-ttu-id="73a38-252">发布连接后，需要自定义搜索结果页面。</span><span class="sxs-lookup"><span data-stu-id="73a38-252">After publishing the connection, you need to customize the search results page.</span></span> <span data-ttu-id="73a38-253">若要了解如何自定义搜索结果，请参阅自定义 [搜索结果页面](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="73a38-253">To learn about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>