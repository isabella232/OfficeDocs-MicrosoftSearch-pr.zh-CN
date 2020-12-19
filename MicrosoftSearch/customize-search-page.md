---
title: 自定义 Microsoft 搜索页
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 添加垂直搜索并自定义搜索结果
ms.openlocfilehash: edc541e902965472295a835906ef36fcd7fba730
ms.sourcegitcommit: e1215758fd1325526e4b7b1612c3349137c6fbc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/18/2020
ms.locfileid: "49716982"
---
# <a name="customize-the-search-results-page"></a><span data-ttu-id="cf753-103">自定义搜索结果页面</span><span class="sxs-lookup"><span data-stu-id="cf753-103">Customize the search results page</span></span>

<span data-ttu-id="cf753-104">可以创建垂直搜索和结果类型，以自定义用户在必应中搜索 Microsoft [SharePoint、Microsoft Office](https://sharepoint.com/)和 Microsoft 搜索 [时](https://office.com)看到的 [搜索结果](https://bing.com)。</span><span class="sxs-lookup"><span data-stu-id="cf753-104">You can create search verticals and result types to customize the search results that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="cf753-105">垂直搜索使用户可以更轻松地找到他们有权查看的信息。</span><span class="sxs-lookup"><span data-stu-id="cf753-105">Verticals make it easier for users to find the information that they have permission to see.</span></span> <span data-ttu-id="cf753-106">例如，您可以为市场营销部门中的用户创建第三方软件中的营销分析数据的垂直搜索。</span><span class="sxs-lookup"><span data-stu-id="cf753-106">For example, you could create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="cf753-107">还可以定义结果类型并自定义此数据的布局。</span><span class="sxs-lookup"><span data-stu-id="cf753-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="cf753-108">您可以在以下级别创建垂直和结果类型：</span><span class="sxs-lookup"><span data-stu-id="cf753-108">You can create verticals and result types at these levels:</span></span>

- <span data-ttu-id="cf753-109">**组织级别** – 在组织级别添加垂直时，当用户从 [SharePoint](https://sharepoint.com/) 起始页 [、Office](https://office.com)或必应进行搜索时，它将显示在 [搜索结果页面上](https://bing.com)。</span><span class="sxs-lookup"><span data-stu-id="cf753-109">**Organization level** – When you add a vertical at the organization level, it appears on the search results page when users search from their [SharePoint](https://sharepoint.com/) start page, on [Office](https://office.com), or on [Bing](https://bing.com).</span></span>
- <span data-ttu-id="cf753-110">**网站** 级别 – 例如，您可能希望让客户服务员工直接从其部门的 SharePoint 网站搜索严重性 *1* 事件。</span><span class="sxs-lookup"><span data-stu-id="cf753-110">**Site level** – For example, you might want to enable your customer service employees to search for *Severity 1* incidents directly from their department’s SharePoint site.</span></span>

## <a name="search-verticals-explained"></a><span data-ttu-id="cf753-111">说明的垂直搜索</span><span class="sxs-lookup"><span data-stu-id="cf753-111">Search verticals explained</span></span>

<span data-ttu-id="cf753-112">在 Microsoft 搜索结果页的顶部，有一行选项卡。</span><span class="sxs-lookup"><span data-stu-id="cf753-112">At the top of the Microsoft Search results page, there's a row of tabs.</span></span> <span data-ttu-id="cf753-113">这些是垂直搜索。</span><span class="sxs-lookup"><span data-stu-id="cf753-113">These are the search verticals.</span></span> <span data-ttu-id="cf753-114">垂直搜索只显示某种类型或特定内容的结果。</span><span class="sxs-lookup"><span data-stu-id="cf753-114">A search vertical only shows results of a certain type or from certain content.</span></span> <span data-ttu-id="cf753-115">示例是 **文件或\*\*\*\*新闻**。</span><span class="sxs-lookup"><span data-stu-id="cf753-115">Examples are **Files** or **News**.</span></span> <span data-ttu-id="cf753-116">默认情况下，Microsoft 搜索显示垂直全部 **、\*\*\*\*人员** **、** 文件 、**网站** 和 **新闻**。</span><span class="sxs-lookup"><span data-stu-id="cf753-116">By default, Microsoft Search shows the verticals **All**, **People**, **Files**, **Sites**, and **News**.</span></span>  

<span data-ttu-id="cf753-117">您可以添加与组织相关的垂直搜索。</span><span class="sxs-lookup"><span data-stu-id="cf753-117">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="cf753-118">这些将出现在[SharePoint、Office](https://sharepoint.com/)和必应中的[](https://Office.com)Microsoft 搜索结果[页面上](https://bing.com)。</span><span class="sxs-lookup"><span data-stu-id="cf753-118">These will appear on the Microsoft Search results page in [SharePoint](https://sharepoint.com/), [Office](https://Office.com), and [Bing](https://bing.com).</span></span> <span data-ttu-id="cf753-119">例如，您可以根据每个组需要的信息类型为与营销相关的内容创建一个垂直搜索，为销售创建另一个垂直内容。</span><span class="sxs-lookup"><span data-stu-id="cf753-119">For example, you could create a vertical for marketing-related content and another for sales, based on the type of information that each group needs.</span></span> <span data-ttu-id="cf753-120">您可以添加垂直线来显示仅来自通过连接器编制索引的内容的结果。</span><span class="sxs-lookup"><span data-stu-id="cf753-120">You can add verticals to show results only from content indexed via connectors.</span></span>  

### <a name="multiple-connections-in-a-vertical"></a><span data-ttu-id="cf753-121">垂直连接中的多个连接</span><span class="sxs-lookup"><span data-stu-id="cf753-121">Multiple connections in a vertical</span></span>

<span data-ttu-id="cf753-122">垂直搜索现在可以显示来自多个连接器源的结果。</span><span class="sxs-lookup"><span data-stu-id="cf753-122">A search vertical can now surface results from multiple connector sources.</span></span> <span data-ttu-id="cf753-123">这为设计搜索结果页面提供了更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="cf753-123">This provides greater flexibility in designing your search result page.</span></span> <span data-ttu-id="cf753-124">通过垂直设置的现有管理体验，您可以在"内容源"步骤中选择多个连接。</span><span class="sxs-lookup"><span data-stu-id="cf753-124">The existing administrative experience of vertical setup allows you to select multiple connections in the "Content Source" step.</span></span>
<span data-ttu-id="cf753-125">如果准确指定尽可能多的语义标签，将会增强此体验。</span><span class="sxs-lookup"><span data-stu-id="cf753-125">If you accurately appoint as many semantic labels as possible, this experience will be enhanced.</span></span> <span data-ttu-id="cf753-126">可以在架构定义和加入时添加语义标签。</span><span class="sxs-lookup"><span data-stu-id="cf753-126">You can add semantic labels upon schema definition and ingestion.</span></span>

<span data-ttu-id="cf753-127">[下面是](#configure-connector-step-5-assign-property-labels) 有关如何创建和管理语义标签的其他信息。</span><span class="sxs-lookup"><span data-stu-id="cf753-127">[Here](#configure-connector-step-5-assign-property-labels) is additional information on how to create and manage semantic labels.</span></span>

### <a name="things-you-should-know"></a><span data-ttu-id="cf753-128">你应了解的一些内容</span><span class="sxs-lookup"><span data-stu-id="cf753-128">Things you should know</span></span>

1. <span data-ttu-id="cf753-129">连接只能添加为一个垂直下的内容源。</span><span class="sxs-lookup"><span data-stu-id="cf753-129">A connection can be added as a content source only under one vertical.</span></span> <span data-ttu-id="cf753-130">不允许在多个垂直线下重新使用连接。</span><span class="sxs-lookup"><span data-stu-id="cf753-130">Reusing connections under multiple verticals is not allowed.</span></span>
2. <span data-ttu-id="cf753-131">如果需要为已添加多个连接源的垂直搜索设置查询，则应该使用公共源属性创建此类查询。</span><span class="sxs-lookup"><span data-stu-id="cf753-131">If you need to setup a query for a search vertical where multiple connection sources have been added, common source properties should be used to create a such a query.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="cf753-132">注意事项</span><span class="sxs-lookup"><span data-stu-id="cf753-132">Things to consider</span></span>

<span data-ttu-id="cf753-133">在启动之前，请确保连接器已编制索引。</span><span class="sxs-lookup"><span data-stu-id="cf753-133">Before you start, make sure that the connector has been indexed.</span></span> <span data-ttu-id="cf753-134">这最多可能需要 48 小时，具体取决于文件大小。</span><span class="sxs-lookup"><span data-stu-id="cf753-134">This can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="cf753-135">无法为驻留在 SharePoint 中的内容创建[垂直。](https://sharepoint.com/)</span><span class="sxs-lookup"><span data-stu-id="cf753-135">You can’t create a vertical for content that resides in [SharePoint](https://sharepoint.com/).</span></span>

<span data-ttu-id="cf753-136">添加垂直方向有三个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="cf753-136">There are three basic steps to add a vertical:</span></span>

1. <span data-ttu-id="cf753-137">创建垂直。</span><span class="sxs-lookup"><span data-stu-id="cf753-137">Create the vertical.</span></span> <span data-ttu-id="cf753-138">在此步骤中，定义要搜索的内容的垂直名称、内容源和范围。</span><span class="sxs-lookup"><span data-stu-id="cf753-138">In this step, you define the vertical’s name, content source, and scope of the content to search.</span></span>
2. <span data-ttu-id="cf753-139">定义此垂直方向的结果。</span><span class="sxs-lookup"><span data-stu-id="cf753-139">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="cf753-140">允许从 (页面) 垂直列表。</span><span class="sxs-lookup"><span data-stu-id="cf753-140">Enable the vertical (to be displayed) from the vertical list page.</span></span>

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="cf753-141">步骤 1：创建垂直搜索</span><span class="sxs-lookup"><span data-stu-id="cf753-141">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="cf753-142">启动向导后，将指导您完成定义要搜索的内容的垂直名称、内容源和范围的步骤。</span><span class="sxs-lookup"><span data-stu-id="cf753-142">After you start the wizard, you're guided through the steps to define the vertical's name, content source, and scope of the content to search.</span></span> <span data-ttu-id="cf753-143">垂直线处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="cf753-143">The vertical is created in a disabled state.</span></span> <span data-ttu-id="cf753-144">稍后将启用它。</span><span class="sxs-lookup"><span data-stu-id="cf753-144">You'll enable it later.</span></span>

<span data-ttu-id="cf753-145">您可以使用一组有限的关键字查询语言 [ (KQL) ](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) 缩小范围。</span><span class="sxs-lookup"><span data-stu-id="cf753-145">You can use a limited set of [Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow the scope.</span></span> <span data-ttu-id="cf753-146">此页面列出了可用的属性。</span><span class="sxs-lookup"><span data-stu-id="cf753-146">This page lists the properties that are available.</span></span> <span data-ttu-id="cf753-147">建议您将自由文本关键字和属性限制与布尔运算符一起用于创建 KQL。</span><span class="sxs-lookup"><span data-stu-id="cf753-147">We recommend that you use freetext keywords and property restrictions with boolean operators for creating the KQL.</span></span>

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="cf753-148">在组织级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="cf753-148">Create a vertical at the organization level</span></span>

<span data-ttu-id="cf753-149">若要在 [SharePoint](https://sharepoint.com/) 主页 [、Office](https://office.com)或 [必应](https://bing.com)Microsoft 搜索上创建垂直搜索，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="cf753-149">To create the vertical on Microsoft Search in [SharePoint](https://sharepoint.com/) home, [Office](https://office.com), or [Bing](https://bing.com), follow these steps:</span></span>

1. <span data-ttu-id="cf753-150">在 [Microsoft 365 管理中心](https://admin.microsoft.com)，转到 [**"垂直"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)</span><span class="sxs-lookup"><span data-stu-id="cf753-150">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="cf753-151">选择 **"添加** "开始。</span><span class="sxs-lookup"><span data-stu-id="cf753-151">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="cf753-152">在网站级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="cf753-152">Create a vertical at the site level</span></span>

1. <span data-ttu-id="cf753-153">在要垂直搜索的 [SharePoint](https://sharepoint.com/)网站上，转到"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="cf753-153">On the [SharePoint](https://sharepoint.com/) site where you want the vertical, go to **Settings**.</span></span>
2. <span data-ttu-id="cf753-154">选择 **"网站信息** "， **然后查看所有网站设置**。</span><span class="sxs-lookup"><span data-stu-id="cf753-154">Select **Site information** and then **View all site settings**.</span></span>
3. <span data-ttu-id="cf753-155">查找 **"Microsoft 搜索"** 部分，然后选择"**为此网站集配置 Microsoft 搜索"。**</span><span class="sxs-lookup"><span data-stu-id="cf753-155">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="cf753-156">在导航窗格中，转到" **自定义体验**"，然后选择" **垂直"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cf753-156">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
5. <span data-ttu-id="cf753-157">若要添加垂直，请选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf753-157">To add a vertical, select **Add**.</span></span>
  <span data-ttu-id="cf753-158">或者，若要编辑垂直方向，请在列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="cf753-158">Or, to edit a vertical, select it in the list.</span></span>

<span data-ttu-id="cf753-159">请记住，垂直线处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="cf753-159">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="cf753-160">必须先启用它们，用户才能看到它们。</span><span class="sxs-lookup"><span data-stu-id="cf753-160">They must be enabled before users can see them.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="cf753-161">步骤 2：创建结果类型</span><span class="sxs-lookup"><span data-stu-id="cf753-161">STEP 2: Create the result types</span></span>

<span data-ttu-id="cf753-162">您可以通过使用结果类型设计布局来定义结果在垂直方向上的显示方式。</span><span class="sxs-lookup"><span data-stu-id="cf753-162">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="cf753-163">结果布局允许您直接在搜索结果中显示重要信息，因此用户不必选择每个结果来查看他们是否找到要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="cf753-163">The result layout lets you show important information directly in the search results, so users don't have to select each result to see if they found what they're looking for.</span></span>

### <a name="default-search-result-layout"></a><span data-ttu-id="cf753-164">默认搜索结果布局</span><span class="sxs-lookup"><span data-stu-id="cf753-164">Default search result layout</span></span>

<span data-ttu-id="cf753-165">如果在配置连接器时标签和内容属性已正确映射到源属性，将为连接器内容显示默认搜索结果布局。</span><span class="sxs-lookup"><span data-stu-id="cf753-165">A default search result layout will be shown for Connector content if **labels** and **content** property have been mapped correctly to the source properties at the time of configuring the connector.</span></span> <span data-ttu-id="cf753-166">标签 **标题** 是最重要的标签。</span><span class="sxs-lookup"><span data-stu-id="cf753-166">The label **title** is the most important label.</span></span> <span data-ttu-id="cf753-167">强烈建议 **你为此** 标签分配一个属性以使用默认搜索结果布局。</span><span class="sxs-lookup"><span data-stu-id="cf753-167">It is **strongly recommended** that you have a property assigned to this label to use default search result layout.</span></span>

### <a name="create-your-own-result-type"></a><span data-ttu-id="cf753-168">创建自己的结果类型</span><span class="sxs-lookup"><span data-stu-id="cf753-168">Create your own result type</span></span>

<span data-ttu-id="cf753-169">您可以决定创建自己的搜索结果布局，并覆盖默认搜索结果布局通过创建一个 **结果类型**。</span><span class="sxs-lookup"><span data-stu-id="cf753-169">You can decide to create your own search result layout and override the default search result layout by creating a **result type**.</span></span> <span data-ttu-id="cf753-170">搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。</span><span class="sxs-lookup"><span data-stu-id="cf753-170">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways.</span></span> <span data-ttu-id="cf753-171">它包含以下几个方面：</span><span class="sxs-lookup"><span data-stu-id="cf753-171">It consists of the following:</span></span>

- <span data-ttu-id="cf753-172">**要比较每个** 搜索结果的一个或多个条件，例如搜索结果的内容源。</span><span class="sxs-lookup"><span data-stu-id="cf753-172">**One or more conditions** to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="cf753-173">**用于满足** 条件的搜索结果的结果布局。</span><span class="sxs-lookup"><span data-stu-id="cf753-173">A **result layout** to use for search results that meet the conditions.</span></span> <span data-ttu-id="cf753-174">结果布局控制满足条件的所有结果在搜索结果页上的显示和行为方式。</span><span class="sxs-lookup"><span data-stu-id="cf753-174">The result layout controls the way that all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="cf753-175">**如果未执行适当的映射以显示默认搜索结果布局，则 Yyou 必须创建至少一个结果类型，以在垂直方向显示结果。**</span><span class="sxs-lookup"><span data-stu-id="cf753-175">**If appropriate mapping is not done to show default search result layout, Yyou must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="cf753-176">您可以为每个垂直结果类型创建多个结果类型，这允许您对不同类型的结果使用不同的布局。</span><span class="sxs-lookup"><span data-stu-id="cf753-176">You can create multiple result types for each vertical, which allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="cf753-177">例如，你可以自定义"严重性 *1"* 事件，以比"严重性 *3"事件具有更醒目的颜色和更大的* 字体。</span><span class="sxs-lookup"><span data-stu-id="cf753-177">For example, you can customize *Severity 1* incidents to have more prominent colors and a larger font compared to *Severity 3* incidents.</span></span>

<span data-ttu-id="cf753-178">启动向导后，将指导您完成定义结果类型的名称、内容源和条件的步骤。</span><span class="sxs-lookup"><span data-stu-id="cf753-178">After you start the wizard, you're guided through the steps to define the name, content source, and conditions for the result type.</span></span> <span data-ttu-id="cf753-179">可以从列表视图定义结果类型的优先级。</span><span class="sxs-lookup"><span data-stu-id="cf753-179">You can define the priority of the result type from the list view.</span></span>
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="cf753-180">在组织级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="cf753-180">Create a result type at the organization level</span></span>

1. <span data-ttu-id="cf753-181">在 [Microsoft 365 管理中心](https://admin.microsoft.com)中，转到"[**结果类型"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)</span><span class="sxs-lookup"><span data-stu-id="cf753-181">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).</span></span>
2. <span data-ttu-id="cf753-182">若要添加结果 **类型，请选择**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf753-182">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="cf753-183">若要编辑结果类型，请在相关列表中选择结果类型。</span><span class="sxs-lookup"><span data-stu-id="cf753-183">To edit a result type, select the result type in the relevant list.</span></span>

### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="cf753-184">在网站级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="cf753-184">Create a results type at the site level</span></span>

1. <span data-ttu-id="cf753-185">在要创建结果类型的 [SharePoint](https://sharepoint.com/)网站上，转到"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="cf753-185">On the [SharePoint](https://sharepoint.com/) site where you want to create the result type, go to **Settings**.</span></span>
2. <span data-ttu-id="cf753-186">选择 **"网站信息** "， **然后查看所有网站设置**。</span><span class="sxs-lookup"><span data-stu-id="cf753-186">Select **Site information** and then **View all site settings**.</span></span>
3. <span data-ttu-id="cf753-187">查找"Microsoft 搜索"部分，然后选择"**为此网站集配置 Microsoft 搜索"。**</span><span class="sxs-lookup"><span data-stu-id="cf753-187">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="cf753-188">在导航窗格中，转到" **自定义体验**"，然后选择" **结果类型"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cf753-188">In the navigation pane, go to **Custom experience**, and select **Result type** tab.</span></span>
5. <span data-ttu-id="cf753-189">若要添加结果类型，请选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf753-189">To add a result type, select **Add**.</span></span>  <span data-ttu-id="cf753-190">或者，若要编辑结果类型，请在列表中选择结果类型。</span><span class="sxs-lookup"><span data-stu-id="cf753-190">Or, to edit a result type, select the result type in the list.</span></span>

## <a name="step-3-view-the-vertical-after-its-enabled"></a><span data-ttu-id="cf753-191">步骤 3：启用后查看垂直方向</span><span class="sxs-lookup"><span data-stu-id="cf753-191">STEP 3: View the vertical after it's enabled</span></span>

<span data-ttu-id="cf753-192">启用垂直搜索后，可能需要一段时间才能查看它。</span><span class="sxs-lookup"><span data-stu-id="cf753-192">After you enable the vertical, it might take a while before you can view it.</span></span> <span data-ttu-id="cf753-193">如果不想在启用后等待，可以将 **cacheClear=true** 追加到 [SharePoint](https://sharepoint.com/) 和 [Office](https://office.com) 中的 URL 以立即查看垂直方向。</span><span class="sxs-lookup"><span data-stu-id="cf753-193">If you don't want to wait after enabling it, you can append **cacheClear=true** to the URL in [SharePoint](https://sharepoint.com/) and [Office](https://office.com) to view the vertical immediately.</span></span> <span data-ttu-id="cf753-194">对于 [必应](https://bing.com)，将 **&features=uncachedVerticals** 追加到工作垂直 URL 以立即查看垂直方向。</span><span class="sxs-lookup"><span data-stu-id="cf753-194">For [Bing](https://bing.com), append **&features=uncachedVerticals** to the Work vertical URL to view the verticals immediately.</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="cf753-195">疑难解答</span><span class="sxs-lookup"><span data-stu-id="cf753-195">Troubleshooting</span></span>

<span data-ttu-id="cf753-196">下面列出了可能会遇到的常见问题以及解决这些问题的操作。</span><span class="sxs-lookup"><span data-stu-id="cf753-196">Here's a list of common issues you might encounter and actions to fix them.</span></span>

|<span data-ttu-id="cf753-197">错误</span><span class="sxs-lookup"><span data-stu-id="cf753-197">Error</span></span>  |<span data-ttu-id="cf753-198">操作</span><span class="sxs-lookup"><span data-stu-id="cf753-198">Action</span></span>  |
|---------|---------|
| <span data-ttu-id="cf753-199">我在垂直方向看到"出错"错误消息。</span><span class="sxs-lookup"><span data-stu-id="cf753-199">I see a "Something went wrong" error message on the vertical.</span></span> | <span data-ttu-id="cf753-200">完成设置需要垂直类型和结果类型。</span><span class="sxs-lookup"><span data-stu-id="cf753-200">Both the vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="cf753-201">确保为同一内容源创建了两者。</span><span class="sxs-lookup"><span data-stu-id="cf753-201">Make sure you have created both for the same content source.</span></span> |
| <span data-ttu-id="cf753-202">我看不到我的结果布局，尽管我创建了一个结果布局。</span><span class="sxs-lookup"><span data-stu-id="cf753-202">I don't see my result layout, although I created one.</span></span> | <span data-ttu-id="cf753-203">由于这些设置通常是缓存的，因此需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="cf753-203">It takes a few minutes because these settings are generally cached.</span></span> <span data-ttu-id="cf753-204">请等待几分钟，然后重试。</span><span class="sxs-lookup"><span data-stu-id="cf753-204">Wait for a few minutes and try again.</span></span>        |
| <span data-ttu-id="cf753-205">我在垂直或结果类型页面上看不到任何内容源。</span><span class="sxs-lookup"><span data-stu-id="cf753-205">I don't see any content sources on the vertical or result type page.</span></span> | <span data-ttu-id="cf753-206">确保已配置连接器和索引数据。</span><span class="sxs-lookup"><span data-stu-id="cf753-206">Make sure you have configured connectors and indexed data.</span></span>   |

## <a name="next-steps"></a><span data-ttu-id="cf753-207">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cf753-207">Next steps</span></span>

[<span data-ttu-id="cf753-208">步骤 3：自定义结果布局</span><span class="sxs-lookup"><span data-stu-id="cf753-208">STEP 3: Customize the results layout</span></span>](customize-results-layout.md)
