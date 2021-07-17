---
title: 自定义Microsoft 搜索页面
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
ms.openlocfilehash: 4dd3f08f6d7e3df0aa983684eb0d4f649bc409a1
ms.sourcegitcommit: 1e766e1f549c46882f47df6679f5a3cdf48d70d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53463223"
---
# <a name="customize-the-search-results-page"></a><span data-ttu-id="4522e-103">自定义搜索结果页面</span><span class="sxs-lookup"><span data-stu-id="4522e-103">Customize the search results page</span></span>

<span data-ttu-id="4522e-104">您可以创建垂直搜索和结果类型，以自定义用户在 Microsoft [SharePoint、Microsoft Office](https://office.com)和 必应 中[](https://sharepoint.com/)搜索时Microsoft 搜索[看到的必应。](https://bing.com)</span><span class="sxs-lookup"><span data-stu-id="4522e-104">You can create search verticals and result types to customize the search results that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="4522e-105">通过垂直方向，用户可以更轻松地找到他们有权查看的信息。</span><span class="sxs-lookup"><span data-stu-id="4522e-105">Verticals make it easier for users to find the information that they have permission to see.</span></span> <span data-ttu-id="4522e-106">例如，您可以为市场营销部门用户的第三方软件中的营销分析数据创建垂直搜索。</span><span class="sxs-lookup"><span data-stu-id="4522e-106">For example, you could create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="4522e-107">还可以定义结果类型并为此数据自定义布局。</span><span class="sxs-lookup"><span data-stu-id="4522e-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="4522e-108">您可以在以下级别创建垂直和结果类型：</span><span class="sxs-lookup"><span data-stu-id="4522e-108">You can create verticals and result types at these levels:</span></span>

- <span data-ttu-id="4522e-109">**组织级别**– 当您在组织级别添加垂直搜索时，当用户从 SharePoint 起始页、Office 或 [](https://sharepoint.com/)必应 中搜索时，[](https://office.com)它将显示在 [搜索结果必应。](https://bing.com)</span><span class="sxs-lookup"><span data-stu-id="4522e-109">**Organization level** – When you add a vertical at the organization level, it appears on the search results page when users search from their [SharePoint](https://sharepoint.com/) start page, on [Office](https://office.com), or on [Bing](https://bing.com).</span></span>
- <span data-ttu-id="4522e-110">**网站** 级别 – 例如，您可能希望允许客户服务员工直接从其部门的网站搜索严重性 *1* SharePoint事件。</span><span class="sxs-lookup"><span data-stu-id="4522e-110">**Site level** – For example, you might want to enable your customer service employees to search for *Severity 1* incidents directly from their department’s SharePoint site.</span></span>

## <a name="search-verticals-explained"></a><span data-ttu-id="4522e-111">说明的垂直搜索</span><span class="sxs-lookup"><span data-stu-id="4522e-111">Search verticals explained</span></span>

<span data-ttu-id="4522e-112">在结果Microsoft 搜索顶部，有一行选项卡。</span><span class="sxs-lookup"><span data-stu-id="4522e-112">At the top of the Microsoft Search results page, there's a row of tabs.</span></span> <span data-ttu-id="4522e-113">这些是垂直搜索。</span><span class="sxs-lookup"><span data-stu-id="4522e-113">These are the search verticals.</span></span> <span data-ttu-id="4522e-114">垂直搜索只显示某种类型或特定内容的结果。</span><span class="sxs-lookup"><span data-stu-id="4522e-114">A search vertical only shows results of a certain type or from certain content.</span></span> <span data-ttu-id="4522e-115">例如 **，Files** 或 **News**。</span><span class="sxs-lookup"><span data-stu-id="4522e-115">Examples are **Files** or **News**.</span></span> <span data-ttu-id="4522e-116">默认情况下，Microsoft 搜索显示"全部"、"人员"、"**文件**"、"**网站**"和"**新闻"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-116">By default, Microsoft Search shows the verticals **All**, **People**, **Files**, **Sites**, and **News**.</span></span>  

<span data-ttu-id="4522e-117">您可以添加与组织相关的垂直搜索。</span><span class="sxs-lookup"><span data-stu-id="4522e-117">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="4522e-118">这些将显示在Microsoft 搜索、SharePoint、Office 和 必应[](https://sharepoint.com/)[中的结果必应。](https://bing.com) [](https://Office.com)</span><span class="sxs-lookup"><span data-stu-id="4522e-118">These will appear on the Microsoft Search results page in [SharePoint](https://sharepoint.com/), [Office](https://Office.com), and [Bing](https://bing.com).</span></span> <span data-ttu-id="4522e-119">例如，您可以根据每个组需要的信息类型，为与市场营销相关的内容创建一个垂直目录，为销售创建另一个垂直目录。</span><span class="sxs-lookup"><span data-stu-id="4522e-119">For example, you could create a vertical for marketing-related content and another for sales, based on the type of information that each group needs.</span></span> <span data-ttu-id="4522e-120">您可以添加垂直线来显示仅来自通过连接器编制索引的内容的结果。</span><span class="sxs-lookup"><span data-stu-id="4522e-120">You can add verticals to show results only from content indexed via connectors.</span></span>  

### <a name="multiple-connections-in-a-vertical"></a><span data-ttu-id="4522e-121">垂直连接中的多个连接</span><span class="sxs-lookup"><span data-stu-id="4522e-121">Multiple connections in a vertical</span></span>

<span data-ttu-id="4522e-122">垂直搜索现在可以显示来自多个连接器源的结果。</span><span class="sxs-lookup"><span data-stu-id="4522e-122">A search vertical can now surface results from multiple connector sources.</span></span> <span data-ttu-id="4522e-123">这样可更灵活地设计搜索结果页面。</span><span class="sxs-lookup"><span data-stu-id="4522e-123">This provides greater flexibility in designing your search result page.</span></span> <span data-ttu-id="4522e-124">通过垂直设置的现有管理体验，您可以在"内容源"步骤中选择多个连接。</span><span class="sxs-lookup"><span data-stu-id="4522e-124">The existing administrative experience of vertical setup allows you to select multiple connections in the "Content Source" step.</span></span>
<span data-ttu-id="4522e-125">如果准确指定尽可能多的语义标签，将会增强此体验。</span><span class="sxs-lookup"><span data-stu-id="4522e-125">If you accurately appoint as many semantic labels as possible, this experience will be enhanced.</span></span> <span data-ttu-id="4522e-126">你可以根据架构定义和引用添加语义标签。</span><span class="sxs-lookup"><span data-stu-id="4522e-126">You can add semantic labels upon schema definition and ingestion.</span></span>

<span data-ttu-id="4522e-127">[下面是](configure-connector.md#step-5-assign-property-labels) 有关创建和管理语义标签的其他信息。</span><span class="sxs-lookup"><span data-stu-id="4522e-127">[Here](configure-connector.md#step-5-assign-property-labels) is additional information on how to create and manage semantic labels.</span></span>

> [!NOTE]
> <span data-ttu-id="4522e-128">垂直连接中的多个连接当前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="4522e-128">Multiple connections in a vertical is currently in preview.</span></span> <span data-ttu-id="4522e-129">有关预览的详细信息，请参阅 [连接器预览功能](connectors-overview.md#what-are-the-preview-features)。</span><span class="sxs-lookup"><span data-stu-id="4522e-129">For more information about preview, see [Connectors preview features](connectors-overview.md#what-are-the-preview-features).</span></span>

### <a name="things-you-should-know"></a><span data-ttu-id="4522e-130">你应了解的一些内容</span><span class="sxs-lookup"><span data-stu-id="4522e-130">Things you should know</span></span>

1. <span data-ttu-id="4522e-131">连接只能在一个垂直方向添加为内容源。</span><span class="sxs-lookup"><span data-stu-id="4522e-131">A connection can be added as a content source only under one vertical.</span></span> <span data-ttu-id="4522e-132">不允许在多个垂直方向下重新使用连接。</span><span class="sxs-lookup"><span data-stu-id="4522e-132">Reusing connections under multiple verticals is not allowed.</span></span>
2. <span data-ttu-id="4522e-133">如果需要为添加了多个连接源的垂直搜索设置查询，则应当使用公共源属性创建此类查询。</span><span class="sxs-lookup"><span data-stu-id="4522e-133">If you need to set up a query for a search vertical where multiple connection sources have been added, common source properties should be used to create a such a query.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="4522e-134">注意事项</span><span class="sxs-lookup"><span data-stu-id="4522e-134">Things to consider</span></span>

<span data-ttu-id="4522e-135">在启动之前，请确保连接器已编制索引。</span><span class="sxs-lookup"><span data-stu-id="4522e-135">Before you start, make sure that the connector has been indexed.</span></span> <span data-ttu-id="4522e-136">这最多可能需要 48 小时，具体取决于文件大小。</span><span class="sxs-lookup"><span data-stu-id="4522e-136">This can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="4522e-137">无法为驻留在 SharePoint 中的内容[创建SharePoint。](https://sharepoint.com/)</span><span class="sxs-lookup"><span data-stu-id="4522e-137">You can’t create a vertical for content that resides in [SharePoint](https://sharepoint.com/).</span></span>

<span data-ttu-id="4522e-138">添加垂直方向有三个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="4522e-138">There are three basic steps to add a vertical:</span></span>

1. <span data-ttu-id="4522e-139">创建垂直。</span><span class="sxs-lookup"><span data-stu-id="4522e-139">Create the vertical.</span></span> <span data-ttu-id="4522e-140">在此步骤中，定义要搜索的内容的垂直名称、内容源和范围。</span><span class="sxs-lookup"><span data-stu-id="4522e-140">In this step, you define the vertical’s name, content source, and scope of the content to search.</span></span>
2. <span data-ttu-id="4522e-141">定义此垂直方向的结果。</span><span class="sxs-lookup"><span data-stu-id="4522e-141">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="4522e-142">启用垂直 (从垂直) 显示垂直列表。</span><span class="sxs-lookup"><span data-stu-id="4522e-142">Enable the vertical (to be displayed) from the vertical list page.</span></span>

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="4522e-143">步骤 1：创建垂直搜索</span><span class="sxs-lookup"><span data-stu-id="4522e-143">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="4522e-144">启动向导后，将指导您完成定义要搜索的内容的垂直名称、内容源和范围的步骤。</span><span class="sxs-lookup"><span data-stu-id="4522e-144">After you start the wizard, you're guided through the steps to define the vertical's name, content source, and scope of the content to search.</span></span> <span data-ttu-id="4522e-145">垂直线处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="4522e-145">The vertical is created in a disabled state.</span></span> <span data-ttu-id="4522e-146">稍后将启用它。</span><span class="sxs-lookup"><span data-stu-id="4522e-146">You'll enable it later.</span></span>

<span data-ttu-id="4522e-147">您可以使用一组有限的关键字查询语言 [ (KQL) ](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) 范围。</span><span class="sxs-lookup"><span data-stu-id="4522e-147">You can use a limited set of [Keyword Query Language (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow the scope.</span></span> <span data-ttu-id="4522e-148">此页面列出了可用的属性。</span><span class="sxs-lookup"><span data-stu-id="4522e-148">This page lists the properties that are available.</span></span> <span data-ttu-id="4522e-149">建议您将自由文本关键字和属性限制与布尔运算符一起用于创建 KQL。</span><span class="sxs-lookup"><span data-stu-id="4522e-149">We recommend that you use free-text keywords and property restrictions with boolean operators for creating the KQL.</span></span>
<span data-ttu-id="4522e-150">KQL 还支持使用 [配置文件查询变量](#profile-query-variables) 对垂直方向的结果进行微调。</span><span class="sxs-lookup"><span data-stu-id="4522e-150">KQL also supports the use of [profile query variables](#profile-query-variables) to fine-tune results under the vertical.</span></span>

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="4522e-151">在组织级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="4522e-151">Create a vertical at the organization level</span></span>

<span data-ttu-id="4522e-152">若要在家庭Microsoft 搜索、SharePoint或Office创建[](https://sharepoint.com/)[必应，请按照](https://office.com)以下步骤操作： [](https://bing.com)</span><span class="sxs-lookup"><span data-stu-id="4522e-152">To create the vertical on Microsoft Search in [SharePoint](https://sharepoint.com/) home, [Office](https://office.com), or [Bing](https://bing.com), follow these steps:</span></span>

1. <span data-ttu-id="4522e-153">In the [Microsoft 365 管理中心，](https://admin.microsoft.com)go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="4522e-153">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="4522e-154">选择 **"添加** "开始。</span><span class="sxs-lookup"><span data-stu-id="4522e-154">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="4522e-155">在网站级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="4522e-155">Create a vertical at the site level</span></span>

1. <span data-ttu-id="4522e-156">在 [SharePoint](https://sharepoint.com/)垂直搜索的网站中，转到 **"设置"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-156">On the [SharePoint](https://sharepoint.com/) site where you want the vertical, go to **Settings**.</span></span>
2. <span data-ttu-id="4522e-157">选择 **"网站信息**"，然后选择 **"查看所有网站设置"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-157">Select **Site information** and then **View all site settings**.</span></span>
3. <span data-ttu-id="4522e-158">查找 **"Microsoft 搜索"** 部分，然后选择"为此 **Microsoft 搜索配置网站集"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-158">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="4522e-159">在导航窗格中，转到" **自定义体验**"，然后选择" **垂直"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4522e-159">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
5. <span data-ttu-id="4522e-160">若要添加垂直，请选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-160">To add a vertical, select **Add**.</span></span>
  <span data-ttu-id="4522e-161">或者，若要编辑垂直方向，请在列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="4522e-161">Or, to edit a vertical, select it in the list.</span></span>

<span data-ttu-id="4522e-162">请记住，垂直是在禁用状态中创建的。</span><span class="sxs-lookup"><span data-stu-id="4522e-162">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="4522e-163">必须启用它们，用户才能看到它们。</span><span class="sxs-lookup"><span data-stu-id="4522e-163">They must be enabled before users can see them.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="4522e-164">步骤 2：创建结果类型</span><span class="sxs-lookup"><span data-stu-id="4522e-164">STEP 2: Create the result types</span></span>

<span data-ttu-id="4522e-165">您可以通过使用结果类型设计布局来定义结果在垂直方向上的显示方式。</span><span class="sxs-lookup"><span data-stu-id="4522e-165">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="4522e-166">结果布局使你可以直接在搜索结果中显示重要信息，因此用户不必选择每个结果来查看他们是否找到了要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="4522e-166">The result layout lets you show important information directly in the search results, so users don't have to select each result to see if they found what they're looking for.</span></span>

### <a name="default-search-result-layout"></a><span data-ttu-id="4522e-167">默认搜索结果布局</span><span class="sxs-lookup"><span data-stu-id="4522e-167">Default search result layout</span></span>

<span data-ttu-id="4522e-168">如果在配置连接器时标签和 **内容** 属性已正确映射到源属性，将为连接器内容显示默认搜索结果布局。</span><span class="sxs-lookup"><span data-stu-id="4522e-168">A default search result layout will be shown for Connector content if **labels** and **content** property have been mapped correctly to the source properties at the time of configuring the connector.</span></span> <span data-ttu-id="4522e-169">标签 **标题** 是最重要的标签。</span><span class="sxs-lookup"><span data-stu-id="4522e-169">The label **title** is the most important label.</span></span> <span data-ttu-id="4522e-170">强烈建议 **您为此** 标签分配一个属性，以使用默认搜索结果布局。</span><span class="sxs-lookup"><span data-stu-id="4522e-170">It is **strongly recommended** that you have a property assigned to this label to use default search result layout.</span></span>

### <a name="create-your-own-result-type"></a><span data-ttu-id="4522e-171">创建自己的结果类型</span><span class="sxs-lookup"><span data-stu-id="4522e-171">Create your own result type</span></span>

<span data-ttu-id="4522e-172">您可以决定创建自己的搜索结果布局，然后通过创建结果类型覆盖默认 **搜索结果布局**。</span><span class="sxs-lookup"><span data-stu-id="4522e-172">You can decide to create your own search result layout and override the default search result layout by creating a **result type**.</span></span> <span data-ttu-id="4522e-173">搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。</span><span class="sxs-lookup"><span data-stu-id="4522e-173">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways.</span></span> <span data-ttu-id="4522e-174">它包含以下几个方面：</span><span class="sxs-lookup"><span data-stu-id="4522e-174">It consists of the following:</span></span>

- <span data-ttu-id="4522e-175">**要比较每个** 搜索结果的一个或多个条件，例如搜索结果的内容源。</span><span class="sxs-lookup"><span data-stu-id="4522e-175">**One or more conditions** to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="4522e-176">**用于满足** 条件的搜索结果的结果布局。</span><span class="sxs-lookup"><span data-stu-id="4522e-176">A **result layout** to use for search results that meet the conditions.</span></span> <span data-ttu-id="4522e-177">生成的布局控制满足条件的所有结果在搜索结果页面上的显示和行为方式。</span><span class="sxs-lookup"><span data-stu-id="4522e-177">The resulting layout controls the way that all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="4522e-178">**如果未进行适当的映射以显示默认搜索结果布局，则必须为结果至少创建一个结果类型，以在垂直方向显示。**</span><span class="sxs-lookup"><span data-stu-id="4522e-178">**If appropriate mapping is not done to show default search result layout, You must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="4522e-179">您可以为每个垂直类型创建多个结果类型，这允许您对不同类型的结果使用不同的布局。</span><span class="sxs-lookup"><span data-stu-id="4522e-179">You can create multiple result types for each vertical, which allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="4522e-180">例如，你可以自定义"严重性 *1"* 事件，以比"严重性 *3"* 事件具有更醒目的颜色和更大的字体。</span><span class="sxs-lookup"><span data-stu-id="4522e-180">For example, you can customize *Severity 1* incidents to have more prominent colors and a larger font compared to *Severity 3* incidents.</span></span>

<span data-ttu-id="4522e-181">启动向导后，将指导您完成定义结果类型的名称、内容源和条件的步骤。</span><span class="sxs-lookup"><span data-stu-id="4522e-181">After you start the wizard, you're guided through the steps to define the name, content source, and conditions for the result type.</span></span> <span data-ttu-id="4522e-182">可以从列表视图定义结果类型的优先级。</span><span class="sxs-lookup"><span data-stu-id="4522e-182">You can define the priority of the result type from the list view.</span></span>
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="4522e-183">在组织级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="4522e-183">Create a result type at the organization level</span></span>

1. <span data-ttu-id="4522e-184">在 ["Microsoft 365 管理中心"](https://admin.microsoft.com)中，转到"[**结果类型"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)</span><span class="sxs-lookup"><span data-stu-id="4522e-184">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).</span></span>
2. <span data-ttu-id="4522e-185">若要添加结果 **类型，请选择**"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-185">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="4522e-186">若要编辑结果类型，请在相关列表中选择结果类型。</span><span class="sxs-lookup"><span data-stu-id="4522e-186">To edit a result type, select the result type in the relevant list.</span></span>

### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="4522e-187">在网站级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="4522e-187">Create a results type at the site level</span></span>

1. <span data-ttu-id="4522e-188">在 [SharePoint](https://sharepoint.com/)要创建结果类型的网站中，转到 **"设置"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-188">On the [SharePoint](https://sharepoint.com/) site where you want to create the result type, go to **Settings**.</span></span>
2. <span data-ttu-id="4522e-189">选择 **"网站信息**"，然后选择 **"查看所有网站设置"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-189">Select **Site information** and then **View all site settings**.</span></span>
3. <span data-ttu-id="4522e-190">查找"Microsoft 搜索"部分，然后选择"**为此Microsoft 搜索配置网站集"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-190">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="4522e-191">在导航窗格中，转到"自定义 **体验"，** 然后选择" **结果类型"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4522e-191">In the navigation pane, go to **Custom experience**, and select **Result type** tab.</span></span>
5. <span data-ttu-id="4522e-192">若要添加结果类型，请选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="4522e-192">To add a result type, select **Add**.</span></span>  <span data-ttu-id="4522e-193">或者，若要编辑结果类型，请在列表中选择结果类型。</span><span class="sxs-lookup"><span data-stu-id="4522e-193">Or, to edit a result type, select the result type in the list.</span></span>

## <a name="step-3-view-the-vertical-after-its-enabled"></a><span data-ttu-id="4522e-194">步骤 3：启用后查看垂直方向</span><span class="sxs-lookup"><span data-stu-id="4522e-194">STEP 3: View the vertical after it's enabled</span></span>

<span data-ttu-id="4522e-195">启用垂直方向后，需要几个小时才能查看。</span><span class="sxs-lookup"><span data-stu-id="4522e-195">After you enable the vertical, it will take a few hours before you can view it.</span></span> <span data-ttu-id="4522e-196">如果不想在启用后等待，可以将 **cacheClear=true** 追加到 [SharePoint](https://sharepoint.com/)中的 URL，Office立即查看垂直方向。 [](https://office.com)</span><span class="sxs-lookup"><span data-stu-id="4522e-196">If you don't want to wait after enabling it, you can append **cacheClear=true** to the URL in [SharePoint](https://sharepoint.com/) and [Office](https://office.com) to view the vertical immediately.</span></span> <span data-ttu-id="4522e-197">例如 [必应，](https://bing.com)将&**features=uncachedVerticals** 追加到"工作"垂直 URL 以立即查看垂直方向。</span><span class="sxs-lookup"><span data-stu-id="4522e-197">For [Bing](https://bing.com), append **&features=uncachedVerticals** to the Work vertical URL to view the verticals immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="4522e-198">从移动 Web 浏览器查看时[，SharePoint和](https://sharepoint.com/)Office[垂直显示](https://office.com)。</span><span class="sxs-lookup"><span data-stu-id="4522e-198">Added verticals will not be visible on [SharePoint](https://sharepoint.com/) and [Office](https://office.com) when viewed from mobile web browsers.</span></span>

## <a name="profile-query-variables"></a><span data-ttu-id="4522e-199">配置文件查询变量</span><span class="sxs-lookup"><span data-stu-id="4522e-199">Profile query variables</span></span>

<span data-ttu-id="4522e-200">查询变量用于垂直查询的 KQL 查询部分，以提供动态数据作为垂直查询的输入。</span><span class="sxs-lookup"><span data-stu-id="4522e-200">Query variables are used in the KQL query section of a vertical to provide dynamic data as an input to the query of a vertical.</span></span> <span data-ttu-id="4522e-201">您可以使用配置文件查询变量使搜索结果与登录用户上下文相关。</span><span class="sxs-lookup"><span data-stu-id="4522e-201">You can use profile query variables to make the search results contextual to the signed-in user.</span></span> <span data-ttu-id="4522e-202">配置文件查询变量从已登录用户的配置文件提取 [值](/graph/api/resources/profile?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="4522e-202">Profile query variables fetch values from the signed-in user’s [profile](/graph/api/resources/profile?view=graph-rest-beta).</span></span>

<span data-ttu-id="4522e-203">例如，如果要创建登录用户可以搜索分配给他们的支持票证的垂直"票证"，可以在管理页的垂直创建期间在"查询"部分下指定以下查询。</span><span class="sxs-lookup"><span data-stu-id="4522e-203">For example, if you want to create a “Tickets” vertical where a signed-in user can search for support tickets assigned to them, you can specify the following query under the "Query" section during the vertical creation in the administration page.</span></span>  

<span data-ttu-id="4522e-204">**AssignedTo：{Profile.accounts.userPrincipalName}**</span><span class="sxs-lookup"><span data-stu-id="4522e-204">**AssignedTo:{Profile.accounts.userPrincipalName}**</span></span>

<span data-ttu-id="4522e-205">这将缩小搜索结果范围，以只显示被分派人是执行搜索的用户的项目。</span><span class="sxs-lookup"><span data-stu-id="4522e-205">This will narrow down the search results to show only those items where the assignee is the user performing the search.</span></span>

<span data-ttu-id="4522e-206">[配置文件资源](/graph/api/resources/profile?view=graph-rest-beta) 将属性公开为集合。</span><span class="sxs-lookup"><span data-stu-id="4522e-206">[Profile resource](/graph/api/resources/profile?view=graph-rest-beta) exposes properties as collections.</span></span> <span data-ttu-id="4522e-207">例如，与电子邮件地址有关的信息通过电子邮件集合公开，工作职位作为职位集合，等等。</span><span class="sxs-lookup"><span data-stu-id="4522e-207">For example, information related to email addresses is exposed through email collection, work positions as positions collection, and so on.</span></span> <span data-ttu-id="4522e-208">用户配置文件中提供的所有属性（将 AAD 作为源类型）都作为查询变量公开。</span><span class="sxs-lookup"><span data-stu-id="4522e-208">All properties available in the user profile, which have AAD as the source type, are exposed as Query variables.</span></span>

<span data-ttu-id="4522e-209">请考虑电子邮件集合中具有 3 个可用电子邮件地址的用户，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4522e-209">Consider a user who has 3 email addresses available in the email collection, as shown below.</span></span>

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- <span data-ttu-id="4522e-210">查询 **MyProperty： {Profile.emails.address}** 将解析为 MyProperty："Megan.Bowen@contoso.com"。</span><span class="sxs-lookup"><span data-stu-id="4522e-210">The query **MyProperty: {Profile.emails.address}** will resolve to MyProperty: “Megan.Bowen@contoso.com”.</span></span>  

- <span data-ttu-id="4522e-211">如果要解析 address 属性的所有值，您必须使用多值扩展语法。</span><span class="sxs-lookup"><span data-stu-id="4522e-211">If you wish to resolve all the values of the address attribute, you have to use the multi-value expansion syntax.</span></span> <span data-ttu-id="4522e-212">查询 **{|MyProperty：{Profile.emails.address}}** 将解析为 ( (MyProperty："Megan.Bowen@contoso.com") OR (MyProperty：" "meganb@hotmail.com") OR (MyProperty："meganb@outlook.com") ) </span><span class="sxs-lookup"><span data-stu-id="4522e-212">The query **{|MyProperty:{Profile.emails.address}}** will resolve to ((MyProperty:"Megan.Bowen@contoso.com") OR (MyProperty: "meganb@hotmail.com") OR (MyProperty:"meganb@outlook.com"))</span></span>  

<span data-ttu-id="4522e-213">"|"运算符应该用于解析多值变量。</span><span class="sxs-lookup"><span data-stu-id="4522e-213">The “|” operator should be used for resolving multi-value variables.</span></span> <span data-ttu-id="4522e-214">有关配置文件扩展的更多示例，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="4522e-214">For more examples on profile expansion refer to the table below.</span></span>

| #         | <span data-ttu-id="4522e-215">语法</span><span class="sxs-lookup"><span data-stu-id="4522e-215">Syntax</span></span> |  <span data-ttu-id="4522e-216">返回的值</span><span class="sxs-lookup"><span data-stu-id="4522e-216">Value returned</span></span>  |
| --------- | ------ | --- |
| <span data-ttu-id="4522e-217">1</span><span class="sxs-lookup"><span data-stu-id="4522e-217">1</span></span>    | <span data-ttu-id="4522e-218">MyProperty：{Profile.emails.address}</span><span class="sxs-lookup"><span data-stu-id="4522e-218">MyProperty:{Profile.emails.address}</span></span>  |   <span data-ttu-id="4522e-219">"Megan.Bowen@contoso.com"</span><span class="sxs-lookup"><span data-stu-id="4522e-219">"Megan.Bowen@contoso.com"</span></span>  |
| <span data-ttu-id="4522e-220">2</span><span class="sxs-lookup"><span data-stu-id="4522e-220">2</span></span> | <span data-ttu-id="4522e-221">MyProperty：{Profile.emails}</span><span class="sxs-lookup"><span data-stu-id="4522e-221">MyProperty:{Profile.emails}</span></span>   |    <span data-ttu-id="4522e-222">{Profile.emails} 这无法解析，因为电子邮件是对象。</span><span class="sxs-lookup"><span data-stu-id="4522e-222">{Profile.emails} This will not resolve because emails are an object.</span></span>|
| <span data-ttu-id="4522e-223">3</span><span class="sxs-lookup"><span data-stu-id="4522e-223">3</span></span>    | <span data-ttu-id="4522e-224">{?MyProperty：{Profile.emails}}</span><span class="sxs-lookup"><span data-stu-id="4522e-224">{?MyProperty:{Profile.emails}}</span></span>  |  <span data-ttu-id="4522e-225">这无法解决，因为电子邮件是对象。</span><span class="sxs-lookup"><span data-stu-id="4522e-225">This will not resolve because emails is an object.</span></span> <span data-ttu-id="4522e-226">"？"</span><span class="sxs-lookup"><span data-stu-id="4522e-226">The “?”</span></span> <span data-ttu-id="4522e-227">运算符忽略未解析的查询变量。</span><span class="sxs-lookup"><span data-stu-id="4522e-227">operator ignores query variables that do not resolve.</span></span> <span data-ttu-id="4522e-228">当进一步向下传递查询堆栈时，将删除此变量。</span><span class="sxs-lookup"><span data-stu-id="4522e-228">This variable will be removed when passed further down the query stack.</span></span>   |
| <span data-ttu-id="4522e-229">4 </span><span class="sxs-lookup"><span data-stu-id="4522e-229">4</span></span> | <span data-ttu-id="4522e-230">{&#124;MyProperty： {Profile.emails.source.Type}}</span><span class="sxs-lookup"><span data-stu-id="4522e-230">{&#124;MyProperty: {Profile.emails.source.Type}}</span></span>    |  <span data-ttu-id="4522e-231"> ( (MyProperty："official") OR (MyProperty："non-official") OR (MyProperty："personal") ) </span><span class="sxs-lookup"><span data-stu-id="4522e-231">((MyProperty:"official") OR (MyProperty:"non-official") OR (MyProperty:"personal"))</span></span>    |

> [!NOTE]
>
> - <span data-ttu-id="4522e-232">配置文件查询变量仅支持将连接器用作内容源的自定义垂直[](connectors-overview.md)搜索。</span><span class="sxs-lookup"><span data-stu-id="4522e-232">Profile query variables are only supported for custom verticals using a [connector](connectors-overview.md) as a content source.</span></span>
> - <span data-ttu-id="4522e-233">配置文件查询变量在垂直设置过程的"查询 ["部分定义](customize-search-page.md#step-1-create-the-search-vertical)。</span><span class="sxs-lookup"><span data-stu-id="4522e-233">Profile query variables are defined on the “Query” section of the [vertical set up process](customize-search-page.md#step-1-create-the-search-vertical).</span></span>
> - <span data-ttu-id="4522e-234">配置文件查询变量当前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="4522e-234">Profile query variables is currently in preview.</span></span> <span data-ttu-id="4522e-235">有关预览的详细信息，请参阅 [连接器预览功能](connectors-overview.md#what-are-the-preview-features)。</span><span class="sxs-lookup"><span data-stu-id="4522e-235">For more information about preview, see [Connectors preview features](connectors-overview.md#what-are-the-preview-features).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4522e-236">疑难解答</span><span class="sxs-lookup"><span data-stu-id="4522e-236">Troubleshooting</span></span>

<span data-ttu-id="4522e-237">下面列出了可能会遇到的常见问题以及解决这些问题的操作。</span><span class="sxs-lookup"><span data-stu-id="4522e-237">Here's a list of common issues you might encounter and actions to fix them.</span></span>

|<span data-ttu-id="4522e-238">错误</span><span class="sxs-lookup"><span data-stu-id="4522e-238">Error</span></span>  |<span data-ttu-id="4522e-239">操作</span><span class="sxs-lookup"><span data-stu-id="4522e-239">Action</span></span>  |
|---------|---------|
| <span data-ttu-id="4522e-240">我在垂直方向看到一条"出错"错误消息。</span><span class="sxs-lookup"><span data-stu-id="4522e-240">I see a "Something went wrong" error message on the vertical.</span></span> | <span data-ttu-id="4522e-241">完成设置需要垂直类型和结果类型。</span><span class="sxs-lookup"><span data-stu-id="4522e-241">Both the vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="4522e-242">确保为同一内容源创建了两者。</span><span class="sxs-lookup"><span data-stu-id="4522e-242">Make sure you have created both for the same content source.</span></span> |
| <span data-ttu-id="4522e-243">我看不到我的结果布局，尽管我创建了一个结果布局。</span><span class="sxs-lookup"><span data-stu-id="4522e-243">I don't see my result layout, although I created one.</span></span> | <span data-ttu-id="4522e-244">由于通常缓存这些设置，因此需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="4522e-244">It takes a few minutes because these settings are generally cached.</span></span> <span data-ttu-id="4522e-245">请等待几分钟，然后重试。</span><span class="sxs-lookup"><span data-stu-id="4522e-245">Wait for a few minutes and try again.</span></span>        |
| <span data-ttu-id="4522e-246">在垂直或结果类型页面上，我看不到任何内容源。</span><span class="sxs-lookup"><span data-stu-id="4522e-246">I don't see any content sources on the vertical or result type page.</span></span> | <span data-ttu-id="4522e-247">确保已配置连接器和索引数据。</span><span class="sxs-lookup"><span data-stu-id="4522e-247">Make sure you have configured connectors and indexed data.</span></span>   |

## <a name="next-steps"></a><span data-ttu-id="4522e-248">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4522e-248">Next steps</span></span>

[<span data-ttu-id="4522e-249">自定义结果布局</span><span class="sxs-lookup"><span data-stu-id="4522e-249">Customize the results layout</span></span>](customize-results-layout.md)
