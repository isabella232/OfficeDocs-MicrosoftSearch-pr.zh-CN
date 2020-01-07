---
title: 自定义 Microsoft Search 页面
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 添加搜索纵向和自定义搜索结果
ms.openlocfilehash: 852622c0c66afb996f941c609980a0d792af7364
ms.sourcegitcommit: c41334350654daef3a4cd45b5b18ea4401286997
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2020
ms.locfileid: "40947023"
---
# <a name="customize-the-search-results-page"></a><span data-ttu-id="2f681-103">自定义搜索结果页</span><span class="sxs-lookup"><span data-stu-id="2f681-103">Customize the search results page</span></span>

<span data-ttu-id="2f681-104">通过创建搜索纵向和结果类型，可以自定义在[Bing](https://Bing.com)中的[SharePoint](http://sharepoint.com/)、 [microsoft Office](https://Office.com)和 microsoft 搜索中搜索时向用户显示的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="2f681-104">By creating search verticals and result types, you can customize the search results that are shown to users when they search in [SharePoint](http://sharepoint.com/), [Microsoft Office](https://Office.com), and Microsoft Search in [Bing](https://Bing.com).</span></span> <span data-ttu-id="2f681-105">纵向使用户能够更轻松地查找他们有权查看的信息。</span><span class="sxs-lookup"><span data-stu-id="2f681-105">Verticals make it easier for users to find the information they’ve got permission to see.</span></span> <span data-ttu-id="2f681-106">例如，您可以为市场营销部门的用户从第三方软件为市场营销分析数据创建纵向搜索。</span><span class="sxs-lookup"><span data-stu-id="2f681-106">For example, you can create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="2f681-107">您还可以定义结果类型并自定义此数据的布局。</span><span class="sxs-lookup"><span data-stu-id="2f681-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="2f681-108">您可以在以下级别创建纵向和结果类型：</span><span class="sxs-lookup"><span data-stu-id="2f681-108">You can create verticals and result types at these levels:</span></span> 

- <span data-ttu-id="2f681-109">**组织级别**–如果您在组织级别添加垂直，则当用户从[SharePoint](http://sharepoint.com/)起始页、 [Office](https://Office.com)和[Bing](https://Bing.com)搜索时，它将显示在搜索结果页上。</span><span class="sxs-lookup"><span data-stu-id="2f681-109">**Organization level** – When you add a vertical at the organization level, it appears on the search results page when users search from their [SharePoint](http://sharepoint.com/) start page, on [Office](https://Office.com), and on [Bing](https://Bing.com).</span></span> 
- <span data-ttu-id="2f681-110">**网站级别**–例如，您可能希望允许客户服务员工直接从其部门的 SharePoint 网站搜索**严重级别为 1**的事件。</span><span class="sxs-lookup"><span data-stu-id="2f681-110">**Site level** – For example, you might want to allow your customer service employees to search for **Severity 1** incidents directly from their department’s SharePoint site.</span></span> 

## <a name="whats-a-search-vertical"></a><span data-ttu-id="2f681-111">垂直搜索是什么？</span><span class="sxs-lookup"><span data-stu-id="2f681-111">What’s a search vertical?</span></span>

<span data-ttu-id="2f681-112">在 Microsoft 搜索结果页面的顶部是搜索纵向的一排选项卡。</span><span class="sxs-lookup"><span data-stu-id="2f681-112">At the top of the Microsoft Search results page is a row of tabs that are the search verticals.</span></span> <span data-ttu-id="2f681-113">垂直搜索仅显示特定类型或特定内容的结果。</span><span class="sxs-lookup"><span data-stu-id="2f681-113">A search vertical only shows results of a certain type or from certain content.</span></span> <span data-ttu-id="2f681-114">例如，仅文件或新闻。</span><span class="sxs-lookup"><span data-stu-id="2f681-114">An example is only files or news.</span></span> <span data-ttu-id="2f681-115">默认情况下，Microsoft Search 将显示**所有**行业、**人员**、**文件**、**网站**和**新闻**。</span><span class="sxs-lookup"><span data-stu-id="2f681-115">By default, Microsoft Search shows the verticals **All**, **People**, **Files**, **Sites**, and **News**.</span></span>  

<span data-ttu-id="2f681-116">您可以添加与您的组织相关的搜索纵向。</span><span class="sxs-lookup"><span data-stu-id="2f681-116">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="2f681-117">这些将显示在[SharePoint](http://sharepoint.com/)、 [Office](https://Office.com)和[Bing](https://Bing.com)中的 Microsoft 搜索结果页面上。</span><span class="sxs-lookup"><span data-stu-id="2f681-117">These will appear on the Microsoft Search results page in [SharePoint](http://sharepoint.com/), [Office](https://Office.com), and [Bing](https://Bing.com).</span></span> <span data-ttu-id="2f681-118">例如，您可以为与市场营销相关的内容创建一个垂直的，并根据每个组要拥有的信息类型创建另一个销售。</span><span class="sxs-lookup"><span data-stu-id="2f681-118">For example, you could create one vertical for marketing-related content and another for sales, based on the type of information that each group would want to have.</span></span> <span data-ttu-id="2f681-119">您可以将纵向添加到仅显示通过连接器索引的内容中的结果。</span><span class="sxs-lookup"><span data-stu-id="2f681-119">You can add verticals to show results only from content indexed via connectors.</span></span>  

<span data-ttu-id="2f681-120">**免责声明：** 在 Microsoft Graph 连接器预览中，纵向和结果类型当前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="2f681-120">**DISCLAIMER:** Verticals and result types are currently in preview as a part of the Microsoft Graph connectors preview.</span></span> <span data-ttu-id="2f681-121">无法为驻留在[SharePoint](http://sharepoint.com/)中的内容或由[文件共享连接器](file-share-connector.md)编制索引的内容创建垂直。</span><span class="sxs-lookup"><span data-stu-id="2f681-121">You can't create a vertical for content residing in [SharePoint](http://sharepoint.com/) or from content indexed by the [file share connector](file-share-connector.md).</span></span> <span data-ttu-id="2f681-122">若要了解有关预览的详细信息，请参阅[连接器预览](connectors-preview.md)。</span><span class="sxs-lookup"><span data-stu-id="2f681-122">To find out more about the preview, see [Connectors Preview](connectors-preview.md).</span></span> <span data-ttu-id="2f681-123">若要参与预览，必须先提交[Microsoft Graph 连接器预览注册表单](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)。</span><span class="sxs-lookup"><span data-stu-id="2f681-123">To participate in the preview, you must first submit the [Microsoft Graph Connectors Preview Signup form](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="2f681-124">要考虑的事项 .。。</span><span class="sxs-lookup"><span data-stu-id="2f681-124">Things to consider...</span></span>

<span data-ttu-id="2f681-125">开始之前，请确保已对连接器编制索引。</span><span class="sxs-lookup"><span data-stu-id="2f681-125">Before you start, make sure the connector has been indexed.</span></span> <span data-ttu-id="2f681-126">它最长可能需要48个小时，具体取决于文件大小。</span><span class="sxs-lookup"><span data-stu-id="2f681-126">It can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="2f681-127">无法为驻留在[SharePoint](http://sharepoint.com/)中的内容或由[文件共享连接器](file-share-connector.md)编制索引的内容创建垂直。</span><span class="sxs-lookup"><span data-stu-id="2f681-127">You can’t create a vertical for content residing in [SharePoint](http://sharepoint.com/) or from content indexed by the [file share connector](file-share-connector.md).</span></span> <span data-ttu-id="2f681-128">了解如何为[内容编制索引](configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="2f681-128">Learn how to [index content](configure-connector.md).</span></span>

<span data-ttu-id="2f681-129">在高级别中，添加垂直的主要步骤有三个：</span><span class="sxs-lookup"><span data-stu-id="2f681-129">At a high level, there are three main steps for adding a vertical:</span></span> 

1. <span data-ttu-id="2f681-130">创建垂直。</span><span class="sxs-lookup"><span data-stu-id="2f681-130">Create the vertical.</span></span> <span data-ttu-id="2f681-131">在此步骤中，您将定义要搜索的内容的垂直名称、内容源和范围。</span><span class="sxs-lookup"><span data-stu-id="2f681-131">In this step, you define the vertical’s name, content source, and scope of the content to search.</span></span> 
2. <span data-ttu-id="2f681-132">定义此垂直外观的效果。</span><span class="sxs-lookup"><span data-stu-id="2f681-132">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="2f681-133">启用垂直列表页中的垂直（显示）。</span><span class="sxs-lookup"><span data-stu-id="2f681-133">Enable the vertical (to be displayed) from the vertical list page.</span></span>   

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="2f681-134">步骤1：创建垂直搜索</span><span class="sxs-lookup"><span data-stu-id="2f681-134">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="2f681-135">启动向导后，您将通过这些步骤来定义要搜索的内容的垂直名称、内容源和范围。</span><span class="sxs-lookup"><span data-stu-id="2f681-135">After you start the wizard, you're guided through the steps to define the vertical's name, content source, and scope of the content that it will search.</span></span> <span data-ttu-id="2f681-136">垂直在禁用状态中创建。</span><span class="sxs-lookup"><span data-stu-id="2f681-136">The vertical is created in a disabled state.</span></span> <span data-ttu-id="2f681-137">稍后将启用垂直。</span><span class="sxs-lookup"><span data-stu-id="2f681-137">You'll enable the vertical later.</span></span>

<span data-ttu-id="2f681-138">您可以使用一组有限的[关键字查询语言（KQL）](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)来缩小范围，并在页面中列出可供您使用的属性。</span><span class="sxs-lookup"><span data-stu-id="2f681-138">You can use a limited set of the [Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow down the scope, and the page lists the properties available to you.</span></span> <span data-ttu-id="2f681-139">建议使用带有用于创建 KQL 的布尔运算符的自由文本关键字和属性限制。</span><span class="sxs-lookup"><span data-stu-id="2f681-139">We recommend using free text-keywords and property restrictions with boolean operators for creating the KQL.</span></span> 

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="2f681-140">在组织级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="2f681-140">Create a vertical at the organization level</span></span>

<span data-ttu-id="2f681-141">若要在[SharePoint](http://sharepoint.com/)主页、 [Office](https://Office.com)或[Bing](https://Bing.com)中的 Microsoft 搜索上创建垂直，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="2f681-141">To create the vertical on Microsoft Search in [SharePoint](http://sharepoint.com/) home, [Office](https://Office.com), or [Bing](https://Bing.com), follow these steps:</span></span>

1. <span data-ttu-id="2f681-142">在 microsoft 365 [管理中心](https://admin.microsoft.com)，转到 " **设置** > **Microsoft Search** > **纵向**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-142">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Verticals**.</span></span>
1. <span data-ttu-id="2f681-143">选择 " **添加**" 以开始。</span><span class="sxs-lookup"><span data-stu-id="2f681-143">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="2f681-144">在网站级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="2f681-144">Create a vertical at the site level</span></span>

1. <span data-ttu-id="2f681-145">在要创建垂直的[SharePoint](http://sharepoint.com/)网站上，转到 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-145">On the [SharePoint](http://sharepoint.com/) site where you want to create the vertical, go to **Settings**.</span></span>
1. <span data-ttu-id="2f681-146">选择 "**网站信息**"，然后**查看 "所有网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-146">Select **Site information** and then **View all site settings**.</span></span>
1. <span data-ttu-id="2f681-147">查找 " **Microsoft search** " 部分，然后为**此网站集选择 "配置 Microsoft search**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-147">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="2f681-148">在导航窗格中，转到 " **自定义体验**"，然后选择 "**纵向**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2f681-148">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
1. <span data-ttu-id="2f681-149">若要添加垂直，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-149">To add a vertical, select **Add**.</span></span> <br>
<span data-ttu-id="2f681-150">或</span><span class="sxs-lookup"><span data-stu-id="2f681-150">OR</span></span> <br><span data-ttu-id="2f681-151">若要编辑垂直，请在列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="2f681-151">To edit a vertical, select it in the list.</span></span>

<span data-ttu-id="2f681-152">请记住，将在禁用状态下创建纵向。</span><span class="sxs-lookup"><span data-stu-id="2f681-152">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="2f681-153">您仍需要先启用它们，然后用户才能看到纵向。</span><span class="sxs-lookup"><span data-stu-id="2f681-153">You still need to enable them before users can see the verticals.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="2f681-154">步骤2：创建结果类型</span><span class="sxs-lookup"><span data-stu-id="2f681-154">STEP 2: Create the result types</span></span>

<span data-ttu-id="2f681-155">您可以通过使用结果类型设计布局来定义结果在垂直方向的显示方式。</span><span class="sxs-lookup"><span data-stu-id="2f681-155">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="2f681-156">结果布局使您可以直接在搜索结果中显示重要信息，以便用户无需选择每个结果即可查看他们是否找到了要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="2f681-156">The result layout lets you show important information directly in the search results, so that users don't have to select each result to see if they've found what they're looking for.</span></span>

<span data-ttu-id="2f681-p112">搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。它包含以下几个方面：</span><span class="sxs-lookup"><span data-stu-id="2f681-p112">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways. It consists of the following:</span></span>

- <span data-ttu-id="2f681-159">用于比较每个搜索结果的**一个或多个条件**，例如搜索结果的内容源。</span><span class="sxs-lookup"><span data-stu-id="2f681-159">**One or more conditions** to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="2f681-160">要用于满足条件的搜索结果的**结果布局**。</span><span class="sxs-lookup"><span data-stu-id="2f681-160">A **result layout** to use for search results that meet the conditions.</span></span> <span data-ttu-id="2f681-161">结果布局控制满足条件的所有结果在搜索结果页面上的显示和行为的方式。</span><span class="sxs-lookup"><span data-stu-id="2f681-161">The result layout controls the way in which all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="2f681-162">**必须至少创建一个结果类型，才能在垂直方向上显示。**</span><span class="sxs-lookup"><span data-stu-id="2f681-162">**You must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="2f681-163">您可以为每个垂直创建多个结果类型，从而允许您对不同类型的结果使用不同的布局。</span><span class="sxs-lookup"><span data-stu-id="2f681-163">You can create multiple result types for each vertical, which allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="2f681-164">例如，您可以自定义**严重级别 1**事件，使其具有更突出的颜色和与**严重级别 3**事件相比较大的字体。</span><span class="sxs-lookup"><span data-stu-id="2f681-164">For example, you can customize **Severity 1** incidents to have more prominent colors and a larger font compared to **Severity 3** incidents.</span></span> 

<span data-ttu-id="2f681-165">启动向导后，您可以通过步骤来定义结果类型的名称、内容源和条件。</span><span class="sxs-lookup"><span data-stu-id="2f681-165">After you start the wizard, you're guided through the steps to define the name, content source, and conditions for the result type.</span></span> <span data-ttu-id="2f681-166">您可以从列表视图定义结果类型的优先级。</span><span class="sxs-lookup"><span data-stu-id="2f681-166">You can define the priority of the result type from the list view.</span></span> 
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="2f681-167">在组织级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="2f681-167">Create a result type at the organization level</span></span>

1. <span data-ttu-id="2f681-168">在[管理中心](https://admin.microsoft.com)中，转到 "**设置** > **Microsoft Search**"，然后选择 "**结果类型**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-168">In the [admin center](https://admin.microsoft.com), go to **Setting** > **Microsoft Search**, and then select **Result type**.</span></span>
1. <span data-ttu-id="2f681-169">若要添加**结果类型**，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-169">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="2f681-170">若要编辑结果类型，请选择相关列表中的 "结果类型"。</span><span class="sxs-lookup"><span data-stu-id="2f681-170">To edit a result type, select the result type in the relevant list.</span></span>
 
### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="2f681-171">在网站级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="2f681-171">Create a results type at the site level</span></span>

1. <span data-ttu-id="2f681-172">在要创建结果类型的[SharePoint](http://sharepoint.com/)网站上，转到 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-172">On the [SharePoint](http://sharepoint.com/) site where you want to create the result type, go to **Settings**.</span></span>
1. <span data-ttu-id="2f681-173">选择 "**网站信息**"，然后**查看 "所有网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-173">Select **Site information** and then **View all site settings**.</span></span> 
1. <span data-ttu-id="2f681-174">查找 "Microsoft Search" 部分，然后为**此网站集选择 "配置 Microsoft search**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-174">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="2f681-175">在导航窗格中，转到 " **自定义体验**"，然后选择 "**结果类型**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2f681-175">In the navigation pane, go to **Custom experience**, and then select **Result type** tab.</span></span>
1. <span data-ttu-id="2f681-176">若要添加结果类型，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="2f681-176">To add a result type, select **Add**.</span></span> <br> <span data-ttu-id="2f681-177">或</span><span class="sxs-lookup"><span data-stu-id="2f681-177">OR</span></span> <br><span data-ttu-id="2f681-178">若要编辑结果类型，请在列表中选择 "结果类型"。</span><span class="sxs-lookup"><span data-stu-id="2f681-178">To edit a result type, select the result type in the list.</span></span>

### <a name="view-the-vertical-after-enabling"></a><span data-ttu-id="2f681-179">启用后查看垂直</span><span class="sxs-lookup"><span data-stu-id="2f681-179">View the vertical after enabling</span></span>

<span data-ttu-id="2f681-180">在启用垂直后，可能需要一段时间才能进行查看。</span><span class="sxs-lookup"><span data-stu-id="2f681-180">After you enable the vertical, it might take a while before you can view it.</span></span>
<span data-ttu-id="2f681-181">如果要在启用后等待，请将**cacheClear = true**追加到[SharePoint](http://sharepoint.com/)和[Office](https://Office.com)中的 URL，以便立即查看垂直方向。</span><span class="sxs-lookup"><span data-stu-id="2f681-181">If you want to wait after enabling it, you can append **cacheClear=true** to the URL in [SharePoint](http://sharepoint.com/) and [Office](https://Office.com) to view the vertical immediately.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2f681-182">故障排除</span><span class="sxs-lookup"><span data-stu-id="2f681-182">Troubleshooting</span></span>

<span data-ttu-id="2f681-183">下面列出了您可能遇到的常见问题和解决这些问题的操作。</span><span class="sxs-lookup"><span data-stu-id="2f681-183">Here's a list of common issues you might encounter and actions for fixing them.</span></span>


|<span data-ttu-id="2f681-184">Error</span><span class="sxs-lookup"><span data-stu-id="2f681-184">Error</span></span>  |<span data-ttu-id="2f681-185">Action</span><span class="sxs-lookup"><span data-stu-id="2f681-185">Action</span></span>  |
|---------|---------|
|<span data-ttu-id="2f681-186">我看到在垂直方向上*出现了错误的错误*。</span><span class="sxs-lookup"><span data-stu-id="2f681-186">I see a *Something went wrong* error on the vertical.</span></span> |   <span data-ttu-id="2f681-187">需要直排和结果类型才能完成设置。</span><span class="sxs-lookup"><span data-stu-id="2f681-187">Both vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="2f681-188">请确保已为相同的内容源创建了这两个。</span><span class="sxs-lookup"><span data-stu-id="2f681-188">Make sure you have created both for the same content source.</span></span>      |
|<span data-ttu-id="2f681-189">为什么我看不到结果布局，尽管我已经创建了一个？</span><span class="sxs-lookup"><span data-stu-id="2f681-189">Why don't I see my result layout, although I have created one?</span></span> | <span data-ttu-id="2f681-190">要使用的结果类型需要几分钟时间，通常会缓存这些设置。</span><span class="sxs-lookup"><span data-stu-id="2f681-190">It takes a few minutes for result types to be used as these settings are generally cached.</span></span> <span data-ttu-id="2f681-191">请等待几分钟，然后重试。</span><span class="sxs-lookup"><span data-stu-id="2f681-191">Wait for a few minutes and try again.</span></span>        |
|<span data-ttu-id="2f681-192">在 "垂直" 或 "结果类型" 页上看不到任何内容源。</span><span class="sxs-lookup"><span data-stu-id="2f681-192">I don't see any content sources on the vertical or result type page.</span></span>     |      <span data-ttu-id="2f681-193">请确保已配置连接器和索引数据。</span><span class="sxs-lookup"><span data-stu-id="2f681-193">Make sure you have configured connectors and indexed data.</span></span>   |



## <a name="next-steps"></a><span data-ttu-id="2f681-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2f681-194">Next steps</span></span>
[<span data-ttu-id="2f681-195">步骤3：自定义结果布局</span><span class="sxs-lookup"><span data-stu-id="2f681-195">STEP 3: Customize the results layout</span></span>](customize-results-layout.md)
