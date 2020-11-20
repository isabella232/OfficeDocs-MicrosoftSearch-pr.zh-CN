---
title: 自定义 Microsoft Search 页面
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
description: 添加搜索纵向和自定义搜索结果
ms.openlocfilehash: 8522a6daf05b718ee6a066272da181be6e95905e
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367484"
---
# <a name="customize-the-search-results-page"></a><span data-ttu-id="24935-103">自定义搜索结果页</span><span class="sxs-lookup"><span data-stu-id="24935-103">Customize the search results page</span></span>

<span data-ttu-id="24935-104">您可以创建搜索纵向和结果类型，以自定义用户在[Bing](https://bing.com)中的 microsoft [SharePoint](https://sharepoint.com/)、 [microsoft Office](https://office.com)和 microsoft 搜索中进行搜索时看到的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="24935-104">You can create search verticals and result types to customize the search results that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="24935-105">纵向使用户能够更轻松地查找他们有权查看的信息。</span><span class="sxs-lookup"><span data-stu-id="24935-105">Verticals make it easier for users to find the information that they have permission to see.</span></span> <span data-ttu-id="24935-106">例如，可以为市场营销部门中的用户创建从第三方软件到第三方软件的市场营销分析数据的垂直搜索。</span><span class="sxs-lookup"><span data-stu-id="24935-106">For example, you could create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="24935-107">您还可以定义结果类型并自定义此数据的布局。</span><span class="sxs-lookup"><span data-stu-id="24935-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="24935-108">您可以在以下级别创建纵向和结果类型：</span><span class="sxs-lookup"><span data-stu-id="24935-108">You can create verticals and result types at these levels:</span></span>

- <span data-ttu-id="24935-109">**组织级别** –如果在组织级别添加垂直，则当用户从 [SharePoint](https://sharepoint.com/) 起始页、 [Office](https://office.com)或 [Bing](https://bing.com)进行搜索时，它将显示在搜索结果页上。</span><span class="sxs-lookup"><span data-stu-id="24935-109">**Organization level** – When you add a vertical at the organization level, it appears on the search results page when users search from their [SharePoint](https://sharepoint.com/) start page, on [Office](https://office.com), or on [Bing](https://bing.com).</span></span>
- <span data-ttu-id="24935-110">**网站级别** –例如，您可能希望使客户服务员工能够直接从其部门的 SharePoint 网站搜索 *严重级别为 1* 的事件。</span><span class="sxs-lookup"><span data-stu-id="24935-110">**Site level** – For example, you might want to enable your customer service employees to search for *Severity 1* incidents directly from their department’s SharePoint site.</span></span>

## <a name="search-verticals-explained"></a><span data-ttu-id="24935-111">介绍的搜索纵向</span><span class="sxs-lookup"><span data-stu-id="24935-111">Search verticals explained</span></span>

<span data-ttu-id="24935-112">在 Microsoft 搜索结果页面的顶部有一排选项卡。</span><span class="sxs-lookup"><span data-stu-id="24935-112">At the top of the Microsoft Search results page, there's a row of tabs.</span></span> <span data-ttu-id="24935-113">这些是搜索纵向。</span><span class="sxs-lookup"><span data-stu-id="24935-113">These are the search verticals.</span></span> <span data-ttu-id="24935-114">垂直搜索仅显示特定类型或特定内容的结果。</span><span class="sxs-lookup"><span data-stu-id="24935-114">A search vertical only shows results of a certain type or from certain content.</span></span> <span data-ttu-id="24935-115">例如， **文件** 或 **新闻**。</span><span class="sxs-lookup"><span data-stu-id="24935-115">Examples are **Files** or **News**.</span></span> <span data-ttu-id="24935-116">默认情况下，Microsoft Search 将显示 **所有** 行业、 **人员**、 **文件**、 **网站** 和 **新闻**。</span><span class="sxs-lookup"><span data-stu-id="24935-116">By default, Microsoft Search shows the verticals **All**, **People**, **Files**, **Sites**, and **News**.</span></span>  

<span data-ttu-id="24935-117">您可以添加与您的组织相关的搜索纵向。</span><span class="sxs-lookup"><span data-stu-id="24935-117">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="24935-118">这些将显示在 [SharePoint](https://sharepoint.com/)、 [Office](https://Office.com)和 [Bing](https://bing.com)中的 Microsoft 搜索结果页面上。</span><span class="sxs-lookup"><span data-stu-id="24935-118">These will appear on the Microsoft Search results page in [SharePoint](https://sharepoint.com/), [Office](https://Office.com), and [Bing](https://bing.com).</span></span> <span data-ttu-id="24935-119">例如，您可以为与市场营销相关的内容创建一个垂直的，并根据每个组需要的信息类型创建另一个销售。</span><span class="sxs-lookup"><span data-stu-id="24935-119">For example, you could create a vertical for marketing-related content and another for sales, based on the type of information that each group needs.</span></span> <span data-ttu-id="24935-120">您可以将纵向添加到仅显示通过连接器索引的内容中的结果。</span><span class="sxs-lookup"><span data-stu-id="24935-120">You can add verticals to show results only from content indexed via connectors.</span></span>  

### <a name="multiple-connections-in-a-vertical"></a><span data-ttu-id="24935-121">垂直中的多个连接</span><span class="sxs-lookup"><span data-stu-id="24935-121">Multiple connections in a vertical</span></span>

<span data-ttu-id="24935-122">现在，垂直搜索可以从多个连接器源呈现结果。</span><span class="sxs-lookup"><span data-stu-id="24935-122">A search vertical can now surface results from multiple connector sources.</span></span> <span data-ttu-id="24935-123">这为设计搜索结果页提供了更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="24935-123">This provides greater flexibility in designing your search result page.</span></span> <span data-ttu-id="24935-124">现有的垂直安装管理体验允许您选择 "内容源" 步骤中的多个连接。</span><span class="sxs-lookup"><span data-stu-id="24935-124">The existing administrative experience of vertical setup allows you to select multiple connections in the "Content Source" step.</span></span>
<span data-ttu-id="24935-125">如果您准确地指派了尽可能多的语义标签，则会增强此体验。</span><span class="sxs-lookup"><span data-stu-id="24935-125">If you accurately appoint as many semantic labels as possible, this experience will be enhanced.</span></span> <span data-ttu-id="24935-126">可以在架构定义和摄取时添加语义标签。</span><span class="sxs-lookup"><span data-stu-id="24935-126">You can add semantic labels upon schema definition and ingestion.</span></span>

<span data-ttu-id="24935-127">[以下](#configure-connector-step-5-assign-property-labels) 是有关如何创建和管理语义标签的其他信息。</span><span class="sxs-lookup"><span data-stu-id="24935-127">[Here](#configure-connector-step-5-assign-property-labels) is additional information on how to create and manage semantic labels.</span></span>

### <a name="things-you-should-know"></a><span data-ttu-id="24935-128">您应了解的事项</span><span class="sxs-lookup"><span data-stu-id="24935-128">Things you should know</span></span>

1. <span data-ttu-id="24935-129">只能将连接添加为一个垂直下方的内容源。</span><span class="sxs-lookup"><span data-stu-id="24935-129">A connection can be added as a content source only under one vertical.</span></span> <span data-ttu-id="24935-130">不允许在多个行业中重用连接。</span><span class="sxs-lookup"><span data-stu-id="24935-130">Reusing connections under multiple verticals is not allowed.</span></span>
2. <span data-ttu-id="24935-131">如果需要在添加了多个连接源的情况下，为垂直搜索设置查询，应使用常用的源属性来创建此类查询。</span><span class="sxs-lookup"><span data-stu-id="24935-131">If you need to setup a query for a search vertical where multiple connection sources have been added, common source properties should be used to create a such a query.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="24935-132">注意事项</span><span class="sxs-lookup"><span data-stu-id="24935-132">Things to consider</span></span>

<span data-ttu-id="24935-133">开始之前，请确保已对连接器编制索引。</span><span class="sxs-lookup"><span data-stu-id="24935-133">Before you start, make sure that the connector has been indexed.</span></span> <span data-ttu-id="24935-134">这可能最长为48个小时，具体取决于文件大小。</span><span class="sxs-lookup"><span data-stu-id="24935-134">This can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="24935-135">无法为驻留在 [SharePoint](https://sharepoint.com/)中的内容创建垂直。</span><span class="sxs-lookup"><span data-stu-id="24935-135">You can’t create a vertical for content that resides in [SharePoint](https://sharepoint.com/).</span></span>

<span data-ttu-id="24935-136">有三个基本步骤可添加垂直：</span><span class="sxs-lookup"><span data-stu-id="24935-136">There are three basic steps to add a vertical:</span></span>

1. <span data-ttu-id="24935-137">创建垂直。</span><span class="sxs-lookup"><span data-stu-id="24935-137">Create the vertical.</span></span> <span data-ttu-id="24935-138">在此步骤中，您将定义要搜索的内容的垂直名称、内容源和范围。</span><span class="sxs-lookup"><span data-stu-id="24935-138">In this step, you define the vertical’s name, content source, and scope of the content to search.</span></span>
2. <span data-ttu-id="24935-139">定义此垂直外观的效果。</span><span class="sxs-lookup"><span data-stu-id="24935-139">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="24935-140">启用垂直 (显示从垂直列表页面) 。</span><span class="sxs-lookup"><span data-stu-id="24935-140">Enable the vertical (to be displayed) from the vertical list page.</span></span>

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="24935-141">步骤1：创建垂直搜索</span><span class="sxs-lookup"><span data-stu-id="24935-141">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="24935-142">启动向导后，您可以通过步骤来定义要搜索的内容的垂直名称、内容源和范围。</span><span class="sxs-lookup"><span data-stu-id="24935-142">After you start the wizard, you're guided through the steps to define the vertical's name, content source, and scope of the content to search.</span></span> <span data-ttu-id="24935-143">垂直在禁用状态中创建。</span><span class="sxs-lookup"><span data-stu-id="24935-143">The vertical is created in a disabled state.</span></span> <span data-ttu-id="24935-144">你将在稍后启用它。</span><span class="sxs-lookup"><span data-stu-id="24935-144">You'll enable it later.</span></span>

<span data-ttu-id="24935-145">您可以使用一组有限的 [关键字查询语言 (KQL) ](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) 来缩小范围。</span><span class="sxs-lookup"><span data-stu-id="24935-145">You can use a limited set of [Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow the scope.</span></span> <span data-ttu-id="24935-146">此页列出了可用的属性。</span><span class="sxs-lookup"><span data-stu-id="24935-146">This page lists the properties that are available.</span></span> <span data-ttu-id="24935-147">我们建议您将 freetext 关键字和属性限制用于用于创建 KQL 的布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="24935-147">We recommend that you use freetext keywords and property restrictions with boolean operators for creating the KQL.</span></span>

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="24935-148">在组织级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="24935-148">Create a vertical at the organization level</span></span>

<span data-ttu-id="24935-149">若要在 [SharePoint](https://sharepoint.com/) 主页、 [Office](https://office.com)或 [Bing](https://bing.com)中的 Microsoft 搜索上创建垂直，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="24935-149">To create the vertical on Microsoft Search in [SharePoint](https://sharepoint.com/) home, [Office](https://office.com), or [Bing](https://bing.com), follow these steps:</span></span>

1. <span data-ttu-id="24935-150">在 [Microsoft 365 管理中心](https://admin.microsoft.com)，转到 " [**纵向**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)"。</span><span class="sxs-lookup"><span data-stu-id="24935-150">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="24935-151">选择 " **添加** " 以开始。</span><span class="sxs-lookup"><span data-stu-id="24935-151">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="24935-152">在网站级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="24935-152">Create a vertical at the site level</span></span>

1. <span data-ttu-id="24935-153">在您希望垂直的 [SharePoint](https://sharepoint.com/) 网站上，转到 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="24935-153">On the [SharePoint](https://sharepoint.com/) site where you want the vertical, go to **Settings**.</span></span>
2. <span data-ttu-id="24935-154">选择 " **网站信息** "，然后 **查看 "所有网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="24935-154">Select **Site information** and then **View all site settings**.</span></span>
3. <span data-ttu-id="24935-155">查找 " **Microsoft search** " 部分，然后为 **此网站集选择 "配置 Microsoft search**"。</span><span class="sxs-lookup"><span data-stu-id="24935-155">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="24935-156">在导航窗格中，转到 " **自定义体验**"，然后选择 " **纵向** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24935-156">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
5. <span data-ttu-id="24935-157">若要添加垂直，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="24935-157">To add a vertical, select **Add**.</span></span>
  <span data-ttu-id="24935-158">或者，若要编辑垂直，请在列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="24935-158">Or, to edit a vertical, select it in the list.</span></span>

<span data-ttu-id="24935-159">请记住，将在禁用状态下创建纵向。</span><span class="sxs-lookup"><span data-stu-id="24935-159">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="24935-160">必须先启用它们，然后用户才能看到它们。</span><span class="sxs-lookup"><span data-stu-id="24935-160">They must be enabled before users can see them.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="24935-161">步骤2：创建结果类型</span><span class="sxs-lookup"><span data-stu-id="24935-161">STEP 2: Create the result types</span></span>

<span data-ttu-id="24935-162">您可以通过使用结果类型设计布局来定义结果在垂直方向的显示方式。</span><span class="sxs-lookup"><span data-stu-id="24935-162">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="24935-163">结果布局可让您直接在搜索结果中显示重要信息，因此用户无需选择每个结果即可查看他们是否找到了要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="24935-163">The result layout lets you show important information directly in the search results, so users don't have to select each result to see if they found what they're looking for.</span></span>

### <a name="default-search-result-layout"></a><span data-ttu-id="24935-164">默认搜索结果布局</span><span class="sxs-lookup"><span data-stu-id="24935-164">Default search result layout</span></span>

<span data-ttu-id="24935-165">如果在配置连接器时 **标签** 和 **内容** 属性已正确映射到源属性，则将为连接器内容显示默认搜索结果布局。</span><span class="sxs-lookup"><span data-stu-id="24935-165">A default search result layout will be shown for Connector content if **labels** and **content** property have been mapped correctly to the source properties at the time of configuring the connector.</span></span> <span data-ttu-id="24935-166">标签 **标题** 是最重要的标签。</span><span class="sxs-lookup"><span data-stu-id="24935-166">The label **title** is the most important label.</span></span> <span data-ttu-id="24935-167">**强烈建议** 将属性分配给此标签以使用默认搜索结果布局。</span><span class="sxs-lookup"><span data-stu-id="24935-167">It is **strongly recommended** that you have a property assigned to this label to use default search result layout.</span></span>

### <a name="create-your-own-result-type"></a><span data-ttu-id="24935-168">创建您自己的结果类型</span><span class="sxs-lookup"><span data-stu-id="24935-168">Create your own result type</span></span>

<span data-ttu-id="24935-169">您可以决定创建自己的搜索结果布局，并通过创建 **结果类型** 来重写默认搜索结果布局。</span><span class="sxs-lookup"><span data-stu-id="24935-169">You can decide to create your own search result layout and override the default search result layout by creating a **result type**.</span></span> <span data-ttu-id="24935-170">搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。</span><span class="sxs-lookup"><span data-stu-id="24935-170">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways.</span></span> <span data-ttu-id="24935-171">它包含以下几个方面：</span><span class="sxs-lookup"><span data-stu-id="24935-171">It consists of the following:</span></span>

- <span data-ttu-id="24935-172">用于比较每个搜索结果的 **一个或多个条件**，例如搜索结果的内容源。</span><span class="sxs-lookup"><span data-stu-id="24935-172">**One or more conditions** to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="24935-173">要用于满足条件的搜索结果的 **结果布局** 。</span><span class="sxs-lookup"><span data-stu-id="24935-173">A **result layout** to use for search results that meet the conditions.</span></span> <span data-ttu-id="24935-174">结果布局控制满足条件的所有结果在搜索结果页面上的显示和行为方式。</span><span class="sxs-lookup"><span data-stu-id="24935-174">The result layout controls the way that all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="24935-175">**如果没有执行合适的映射来显示默认搜索结果布局，则 Yyou 必须至少创建一个结果类型，才能在垂直方向上显示。**</span><span class="sxs-lookup"><span data-stu-id="24935-175">**If appropriate mapping is not done to show default search result layout, Yyou must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="24935-176">您可以为每个垂直创建多个结果类型，从而允许您对不同类型的结果使用不同的布局。</span><span class="sxs-lookup"><span data-stu-id="24935-176">You can create multiple result types for each vertical, which allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="24935-177">例如，您可以自定义 *严重级别 1* 事件，使其具有更突出的颜色和与 *严重级别 3* 事件相比较大的字体。</span><span class="sxs-lookup"><span data-stu-id="24935-177">For example, you can customize *Severity 1* incidents to have more prominent colors and a larger font compared to *Severity 3* incidents.</span></span>

<span data-ttu-id="24935-178">启动向导后，您可以通过步骤来定义结果类型的名称、内容源和条件。</span><span class="sxs-lookup"><span data-stu-id="24935-178">After you start the wizard, you're guided through the steps to define the name, content source, and conditions for the result type.</span></span> <span data-ttu-id="24935-179">您可以从列表视图定义结果类型的优先级。</span><span class="sxs-lookup"><span data-stu-id="24935-179">You can define the priority of the result type from the list view.</span></span>
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="24935-180">在组织级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="24935-180">Create a result type at the organization level</span></span>

1. <span data-ttu-id="24935-181">在 [Microsoft 365 管理中心](https://admin.microsoft.com)，转到 " [**结果类型**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)"。</span><span class="sxs-lookup"><span data-stu-id="24935-181">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).</span></span>
2. <span data-ttu-id="24935-182">若要添加 **结果类型**，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="24935-182">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="24935-183">若要编辑结果类型，请选择相关列表中的 "结果类型"。</span><span class="sxs-lookup"><span data-stu-id="24935-183">To edit a result type, select the result type in the relevant list.</span></span>

### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="24935-184">在网站级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="24935-184">Create a results type at the site level</span></span>

1. <span data-ttu-id="24935-185">在要创建结果类型的 [SharePoint](https://sharepoint.com/) 网站上，转到 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="24935-185">On the [SharePoint](https://sharepoint.com/) site where you want to create the result type, go to **Settings**.</span></span>
2. <span data-ttu-id="24935-186">选择 " **网站信息** "，然后 **查看 "所有网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="24935-186">Select **Site information** and then **View all site settings**.</span></span>
3. <span data-ttu-id="24935-187">查找 "Microsoft Search" 部分，然后为 **此网站集选择 "配置 Microsoft search**"。</span><span class="sxs-lookup"><span data-stu-id="24935-187">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="24935-188">在导航窗格中，转到 " **自定义体验**"，然后选择 " **结果类型** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24935-188">In the navigation pane, go to **Custom experience**, and select **Result type** tab.</span></span>
5. <span data-ttu-id="24935-189">若要添加结果类型，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="24935-189">To add a result type, select **Add**.</span></span>  <span data-ttu-id="24935-190">或者，若要编辑结果类型，请在列表中选择 "结果类型"。</span><span class="sxs-lookup"><span data-stu-id="24935-190">Or, to edit a result type, select the result type in the list.</span></span>

## <a name="step-3-view-the-vertical-after-its-enabled"></a><span data-ttu-id="24935-191">步骤3：在启用垂直后查看</span><span class="sxs-lookup"><span data-stu-id="24935-191">STEP 3: View the vertical after it's enabled</span></span>

<span data-ttu-id="24935-192">在启用垂直后，可能需要一段时间才能进行查看。</span><span class="sxs-lookup"><span data-stu-id="24935-192">After you enable the vertical, it might take a while before you can view it.</span></span> <span data-ttu-id="24935-193">如果您不希望在启用后等待，则可以将 **cacheClear = true** 追加到 [SharePoint](https://sharepoint.com/) 和 [Office](https://office.com) 中的 URL，以便立即查看垂直方向。</span><span class="sxs-lookup"><span data-stu-id="24935-193">If you don't want to wait after enabling it, you can append **cacheClear=true** to the URL in [SharePoint](https://sharepoint.com/) and [Office](https://office.com) to view the vertical immediately.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="24935-194">疑难解答</span><span class="sxs-lookup"><span data-stu-id="24935-194">Troubleshooting</span></span>

<span data-ttu-id="24935-195">下面列出了你可能遇到的常见问题和解决这些问题的措施。</span><span class="sxs-lookup"><span data-stu-id="24935-195">Here's a list of common issues you might encounter and actions to fix them.</span></span>

|<span data-ttu-id="24935-196">错误</span><span class="sxs-lookup"><span data-stu-id="24935-196">Error</span></span>  |<span data-ttu-id="24935-197">Action</span><span class="sxs-lookup"><span data-stu-id="24935-197">Action</span></span>  |
|---------|---------|
| <span data-ttu-id="24935-198">我在垂直处看到 "出现了错误" 错误消息。</span><span class="sxs-lookup"><span data-stu-id="24935-198">I see a "Something went wrong" error message on the vertical.</span></span> | <span data-ttu-id="24935-199">需要垂直和结果类型才能完成设置。</span><span class="sxs-lookup"><span data-stu-id="24935-199">Both the vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="24935-200">请确保已为相同的内容源创建了这两个。</span><span class="sxs-lookup"><span data-stu-id="24935-200">Make sure you have created both for the same content source.</span></span> |
| <span data-ttu-id="24935-201">我看不到结果布局，尽管我创建了它。</span><span class="sxs-lookup"><span data-stu-id="24935-201">I don't see my result layout, although I created one.</span></span> | <span data-ttu-id="24935-202">此过程需要几分钟时间，因为通常会缓存这些设置。</span><span class="sxs-lookup"><span data-stu-id="24935-202">It takes a few minutes because these settings are generally cached.</span></span> <span data-ttu-id="24935-203">请等待几分钟，然后重试。</span><span class="sxs-lookup"><span data-stu-id="24935-203">Wait for a few minutes and try again.</span></span>        |
| <span data-ttu-id="24935-204">在 "垂直" 或 "结果类型" 页上看不到任何内容源。</span><span class="sxs-lookup"><span data-stu-id="24935-204">I don't see any content sources on the vertical or result type page.</span></span> | <span data-ttu-id="24935-205">请确保已配置连接器和索引数据。</span><span class="sxs-lookup"><span data-stu-id="24935-205">Make sure you have configured connectors and indexed data.</span></span>   |

## <a name="next-steps"></a><span data-ttu-id="24935-206">后续步骤</span><span class="sxs-lookup"><span data-stu-id="24935-206">Next steps</span></span>

[<span data-ttu-id="24935-207">步骤3：自定义结果布局</span><span class="sxs-lookup"><span data-stu-id="24935-207">STEP 3: Customize the results layout</span></span>](customize-results-layout.md)
