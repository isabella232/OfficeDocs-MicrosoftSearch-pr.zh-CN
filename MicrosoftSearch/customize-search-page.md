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
ms.openlocfilehash: 87b394847281e43683f2ed9dfd42d19aa103d3e2
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949622"
---
# <a name="customize-the-microsoft-search-page"></a><span data-ttu-id="a65f6-103">自定义 Microsoft Search 页面</span><span class="sxs-lookup"><span data-stu-id="a65f6-103">Customize the Microsoft Search page</span></span>

<span data-ttu-id="a65f6-104">通过创建搜索纵向和结果类型，您可以自定义在 Bing 中的**SharePoint**、 **Office.com**和**Microsoft 搜索**中搜索时向用户显示的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="a65f6-104">By creating search verticals and result types you can customize the search results that are shown to users when they search in **SharePoint**, **Office.com** and **Microsoft Search in Bing** .</span></span> <span data-ttu-id="a65f6-105">纵向使用户能够更轻松地查找他们有权查看的信息。</span><span class="sxs-lookup"><span data-stu-id="a65f6-105">Verticals make it easier for users to find the information they’ve got permission to see.</span></span>  <span data-ttu-id="a65f6-106">例如，您可以为市场营销部门的用户从第三方软件为市场营销分析数据创建纵向搜索。</span><span class="sxs-lookup"><span data-stu-id="a65f6-106">For example, you can create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="a65f6-107">您还可以定义结果类型并自定义此数据的布局。</span><span class="sxs-lookup"><span data-stu-id="a65f6-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="a65f6-108">您可以在以下级别创建纵向和结果类型：</span><span class="sxs-lookup"><span data-stu-id="a65f6-108">You can create verticals and result types  at these levels:</span></span> 

- <span data-ttu-id="a65f6-109">组织级别–当用户在 "组织" 级别添加垂直时，当用户从 SharePoint 起始页搜索时，将显示在搜索结果页上的 "Office.com" 和 "Bing.com" 上。</span><span class="sxs-lookup"><span data-stu-id="a65f6-109">Organization level – When you add a vertical at the organization level, it appears on the search results page when users search from their SharePoint start page, on Office.com and on Bing.com.</span></span> 
- <span data-ttu-id="a65f6-110">网站级别–例如，您可能希望允许客户服务员工直接从其部门的 SharePoint 网站搜索 "严重度 1" 事件。</span><span class="sxs-lookup"><span data-stu-id="a65f6-110">Site level – For example, you might want to allow your customer service employees to search for “Severity 1” incidents directly from their department’s SharePoint site.</span></span> 

## <a name="whats-a-search-vertical"></a><span data-ttu-id="a65f6-111">垂直搜索是什么？</span><span class="sxs-lookup"><span data-stu-id="a65f6-111">What’s a search vertical?</span></span>

<span data-ttu-id="a65f6-112">在 Microsoft 搜索结果页面的顶部有一行选项卡，这些选项卡是搜索纵向。</span><span class="sxs-lookup"><span data-stu-id="a65f6-112">At the top of the Microsoft search results page there is a row of tabs, these are search verticals.</span></span> <span data-ttu-id="a65f6-113">垂直搜索仅显示特定类型或特定内容的结果，例如，仅文件或新闻。</span><span class="sxs-lookup"><span data-stu-id="a65f6-113">A search vertical only shows results of a certain type or from certain content, for example only files or news.</span></span> <span data-ttu-id="a65f6-114">默认情况下，Microsoft Search 显示所有行业、人员、文件、网站和新闻。</span><span class="sxs-lookup"><span data-stu-id="a65f6-114">By default Microsoft Search shows the verticals All, People, Files, Sites, and News.</span></span>  

<span data-ttu-id="a65f6-115">您可以添加与您的组织相关的搜索纵向。</span><span class="sxs-lookup"><span data-stu-id="a65f6-115">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="a65f6-116">这些将显示在 SharePoint、Office.com 和 Bing 中的 Microsoft 搜索结果页面上。</span><span class="sxs-lookup"><span data-stu-id="a65f6-116">These will appear on the Microsoft search results page in SharePoint, Office.com, and Bing.</span></span>  <span data-ttu-id="a65f6-117">例如，您可以为与市场营销相关的内容创建一个垂直的，并根据每个组要拥有的信息类型创建另一个销售。</span><span class="sxs-lookup"><span data-stu-id="a65f6-117">For example, you could create one vertical for  marketing related content and another for sales, based on the type of information that each group would want to have.</span></span> <span data-ttu-id="a65f6-118">您可以将纵向添加到仅显示通过连接器索引的内容中的结果。</span><span class="sxs-lookup"><span data-stu-id="a65f6-118">You can add verticals to show results only from content indexed via Connectors.</span></span>  

<span data-ttu-id="a65f6-119">**免责声明：** 在 Microsoft 连接器预览中，纵向和结果类型当前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="a65f6-119">**DISCLAIMER:** Verticals and result types are currently in preview as a part of Microsoft Connectors preview.</span></span> <span data-ttu-id="a65f6-120">您不能为驻留在 SharePoint 中的内容或由可共享的连接器编制索引的内容创建垂直。</span><span class="sxs-lookup"><span data-stu-id="a65f6-120">You cannot create a vertical for content residing in SharePoint or from content indexed by the FileShare connector.</span></span> <span data-ttu-id="a65f6-121">若要了解有关预览的详细信息，请参阅[连接器预览](connectors-preview.md)。</span><span class="sxs-lookup"><span data-stu-id="a65f6-121">To find out more about the preview, see [Connectors Preview](connectors-preview.md).</span></span> <span data-ttu-id="a65f6-122">若要参与预览，必须先提交[Microsoft Graph 连接器预览注册表单](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)。</span><span class="sxs-lookup"><span data-stu-id="a65f6-122">To participate in the preview, you must first submit the [Microsoft Graph Connectors Preview Signup form](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="a65f6-123">要考虑的事项 .。。</span><span class="sxs-lookup"><span data-stu-id="a65f6-123">Things to consider...</span></span>

<span data-ttu-id="a65f6-124">开始之前，请确保已对连接器编制索引。</span><span class="sxs-lookup"><span data-stu-id="a65f6-124">Before you start, make sure the connector has been indexed.</span></span> <span data-ttu-id="a65f6-125">它最长可能需要48个小时，具体取决于文件大小。</span><span class="sxs-lookup"><span data-stu-id="a65f6-125">It can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="a65f6-126">您不能为驻留在 SharePoint 中的内容或由可共享的连接器编制索引的内容创建垂直。</span><span class="sxs-lookup"><span data-stu-id="a65f6-126">You can’t create a vertical for content residing in SharePoint or from content indexed by the FileShare connector .</span></span> <span data-ttu-id="a65f6-127">了解如何索引内容（链接到连接器文档）。</span><span class="sxs-lookup"><span data-stu-id="a65f6-127">Learn how to index content(Link to Connector documentation).</span></span>

<span data-ttu-id="a65f6-128">在高级别上，添加垂直的主要步骤有三个。</span><span class="sxs-lookup"><span data-stu-id="a65f6-128">At a high-level, there are three main steps for adding a vertical.</span></span> 

1. <span data-ttu-id="a65f6-129">在此步骤中创建垂直–在此步骤中，将定义要搜索的内容的垂直名称、内容源和范围。</span><span class="sxs-lookup"><span data-stu-id="a65f6-129">Create the vertical – In this step you will define the vertical’s name, content source, and scope of the content to search.</span></span> 
2. <span data-ttu-id="a65f6-130">定义此垂直外观的效果。</span><span class="sxs-lookup"><span data-stu-id="a65f6-130">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="a65f6-131">启用垂直列表页中的垂直（显示）。</span><span class="sxs-lookup"><span data-stu-id="a65f6-131">Enable the vertical (to be displayed) from the vertical list page.</span></span>   

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="a65f6-132">步骤1：创建垂直搜索</span><span class="sxs-lookup"><span data-stu-id="a65f6-132">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="a65f6-133">启动该向导后，您将指导您完成定义其将搜索的内容的垂直名称、内容源和范围的步骤。</span><span class="sxs-lookup"><span data-stu-id="a65f6-133">Once you start the wizard, you'll be guided through the steps to define the vertical's name, content source and scope of the content that it will search.</span></span> <span data-ttu-id="a65f6-134">垂直在禁用状态中创建。</span><span class="sxs-lookup"><span data-stu-id="a65f6-134">The vertical is created in a disabled state.</span></span> <span data-ttu-id="a65f6-135">稍后将启用垂直。</span><span class="sxs-lookup"><span data-stu-id="a65f6-135">You will enable the vertical later.</span></span>

<span data-ttu-id="a65f6-136">您可以使用一组有限的[关键字查询语言（KQL）](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)来缩小范围，页面将显示列出可供您使用的属性。</span><span class="sxs-lookup"><span data-stu-id="a65f6-136">You can use a limited set of the [Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow down the scope, and the page shows lists the properties available to you.</span></span> <span data-ttu-id="a65f6-137">我们建议使用带有用于创建 KQL 的布尔运算符的自由文本关键字和属性限制。</span><span class="sxs-lookup"><span data-stu-id="a65f6-137">We recommend using free text-keywords and property restrictions with boolean operators for creating the KQL</span></span> 

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="a65f6-138">在组织级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="a65f6-138">Create a vertical at the organization level</span></span>

<span data-ttu-id="a65f6-139">若要在 SharePoint 主页、Bing 或 Office.com 中的 Microsoft Search 上创建垂直，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a65f6-139">To create the vertical on Microsoft Search in SharePoint home, Bing or Office.com, follow these steps:</span></span>

1. <span data-ttu-id="a65f6-140">在 microsoft 365 管理中心，请转到 \*\*\*\* > **microsoft Search** > **纵向**设置。</span><span class="sxs-lookup"><span data-stu-id="a65f6-140">In the Microsoft 365 admin center go to **Settings** > **Microsoft Search** > **Verticals**.</span></span>
1. <span data-ttu-id="a65f6-141">选择 " **添加**" 以开始。</span><span class="sxs-lookup"><span data-stu-id="a65f6-141">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="a65f6-142">在网站级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="a65f6-142">Create a vertical at the site level</span></span>

1. <span data-ttu-id="a65f6-143">在要创建垂直的 SharePoint 网站上，转到 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-143">On the SharePoint site where you want to create the vertical, go to **Settings**.</span></span>
1. <span data-ttu-id="a65f6-144">选择 "**网站信息**"，然后**查看所有 "网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-144">Select **Site information**, and then **View all site settings**.</span></span>
1. <span data-ttu-id="a65f6-145">查找 " **Microsoft search** " 部分，然后为**此网站集选择 "配置 Microsoft search**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-145">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="a65f6-146">在导航窗格中，转到 " **自定义体验**"，然后选择 "**纵向**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a65f6-146">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
1. <span data-ttu-id="a65f6-147">若要添加垂直，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-147">To add a vertical, select **Add**.</span></span> <br>
<span data-ttu-id="a65f6-148">或</span><span class="sxs-lookup"><span data-stu-id="a65f6-148">OR</span></span> <br><span data-ttu-id="a65f6-149">若要编辑垂直，请在列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="a65f6-149">To edit a vertical, select it in the list.</span></span>

<span data-ttu-id="a65f6-150">请记住，将在禁用状态下创建纵向。</span><span class="sxs-lookup"><span data-stu-id="a65f6-150">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="a65f6-151">您仍需要先启用它们，然后用户才能看到纵向。</span><span class="sxs-lookup"><span data-stu-id="a65f6-151">You'll still need to enable them before users can see the verticals.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="a65f6-152">步骤2：创建结果类型</span><span class="sxs-lookup"><span data-stu-id="a65f6-152">STEP 2: Create the result types</span></span>

<span data-ttu-id="a65f6-153">您可以通过使用结果类型设计布局来定义结果在垂直方向的显示方式。</span><span class="sxs-lookup"><span data-stu-id="a65f6-153">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="a65f6-154">结果布局使您可以直接在搜索结果中显示重要信息，以便用户无需单击每个结果即可查看他们是否找到了要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="a65f6-154">The result layout let you show important information directly in the search results, so that users don't have to click on each result to see if they've found what they're looking for.</span></span>

<span data-ttu-id="a65f6-p111">搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。它包含以下几个方面：</span><span class="sxs-lookup"><span data-stu-id="a65f6-p111">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways. It consists of the following:</span></span>

- <span data-ttu-id="a65f6-157">用于比较每个搜索结果的*一个或多个条件*，例如搜索结果的内容源。</span><span class="sxs-lookup"><span data-stu-id="a65f6-157">*One or more conditions* to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="a65f6-158">要用于满足条件的搜索结果的*结果布局*。</span><span class="sxs-lookup"><span data-stu-id="a65f6-158">A *result layout* to use for search results that meet the conditions.</span></span> <span data-ttu-id="a65f6-159">结果布局控制满足条件的所有结果在搜索结果页面上的显示和行为的方式。</span><span class="sxs-lookup"><span data-stu-id="a65f6-159">The result layout controls the way in which all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="a65f6-160">**必须至少创建一个结果类型，才能在垂直方向上显示。**</span><span class="sxs-lookup"><span data-stu-id="a65f6-160">**You must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="a65f6-161">您可以为每个垂直创建多个结果类型，这允许您对不同类型的结果使用不同的布局。</span><span class="sxs-lookup"><span data-stu-id="a65f6-161">You can create multiple result types for each vertical, this allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="a65f6-162">例如，您可以自定义 "严重度 1" 事件，使其具有更突出的颜色和与 "严重性 3" 事件相比更大的字体。</span><span class="sxs-lookup"><span data-stu-id="a65f6-162">For example, you can customize “Severity 1” incidents to have more prominent colors and a larger font compared to “Severity 3” incidents.</span></span> 

 <span data-ttu-id="a65f6-163">启动该向导后，您将指导您完成定义结果类型的名称、内容源和条件的步骤。</span><span class="sxs-lookup"><span data-stu-id="a65f6-163">Once you start the wizard, you will be guided through the steps to define the name, content source and conditions for the result type.</span></span> <span data-ttu-id="a65f6-164">您可以从列表视图定义结果类型的优先级。</span><span class="sxs-lookup"><span data-stu-id="a65f6-164">You can define the priority of the result type from the list view.</span></span> 
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="a65f6-165">在组织级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="a65f6-165">Create a result type at the organization level</span></span>

1. <span data-ttu-id="a65f6-166">在 Microsoft 365 管理中心，转到 "**设置** > **Microsoft Search**"，然后选择 "**结果类型**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-166">In the Microsoft 365 admin center, go to **Setting** > **Microsoft Search**, and then select **Result type**.</span></span>
1. <span data-ttu-id="a65f6-167">若要添加**结果类型**，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-167">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="a65f6-168">若要编辑结果类型，请选择相关列表中的 "结果类型"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-168">To edit a result type, select the result type in the relevant list.</span></span>
 
### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="a65f6-169">在网站级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="a65f6-169">Create a results type at the site level</span></span>

1. <span data-ttu-id="a65f6-170">在要创建结果类型的 SharePoint 网站上，转到 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-170">On the SharePoint site where you want to create the result type, go to **Settings**.</span></span>
1. <span data-ttu-id="a65f6-171">选择 "**网站信息**"，然后**查看所有 "网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-171">Select **Site information**, and then **View all site settings**.</span></span> 
1. <span data-ttu-id="a65f6-172">查找 "Microsoft Search" 部分，然后为**此网站集选择 "配置 Microsoft search**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-172">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="a65f6-173">在导航窗格中，转到 " **自定义体验**"，然后选择 "结果类型" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a65f6-173">In the navigation pane, go to **Custom experience**, and then select Result type tab.</span></span>
1. <span data-ttu-id="a65f6-174">若要添加结果类型，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-174">To add a result type, select **Add**.</span></span> <br> <span data-ttu-id="a65f6-175">或</span><span class="sxs-lookup"><span data-stu-id="a65f6-175">OR</span></span> <br><span data-ttu-id="a65f6-176">若要编辑结果类型，请在列表中选择 "结果类型"。</span><span class="sxs-lookup"><span data-stu-id="a65f6-176">To edit a result type, select the result type in the list.</span></span>

### <a name="view-the-vertical-after-enabling"></a><span data-ttu-id="a65f6-177">启用后查看垂直</span><span class="sxs-lookup"><span data-stu-id="a65f6-177">View the vertical after enabling</span></span>

<span data-ttu-id="a65f6-178">在启用垂直后，可能需要一段时间才能进行查看。</span><span class="sxs-lookup"><span data-stu-id="a65f6-178">After you enable the vertical, it might take a while before you can view it.</span></span>
<span data-ttu-id="a65f6-179">如果要在启用后等待，则可以将*cacheClear = true*追加到 SharePoint 和 Office.com 中的 URL，以立即查看垂直方向。</span><span class="sxs-lookup"><span data-stu-id="a65f6-179">If you want to wait after enabling it, you can append *cacheClear=true* to the URL in SharePoint and Office.com to view the vertical immediately.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a65f6-180">疑难解答</span><span class="sxs-lookup"><span data-stu-id="a65f6-180">Troubleshooting</span></span>

<span data-ttu-id="a65f6-181">下面列出了您可能遇到的常见问题和解决这些问题的操作。</span><span class="sxs-lookup"><span data-stu-id="a65f6-181">Here's a list of common issues you might encounter and actions for fixing them.</span></span>


|<span data-ttu-id="a65f6-182">Error</span><span class="sxs-lookup"><span data-stu-id="a65f6-182">Error</span></span>  |<span data-ttu-id="a65f6-183">Action</span><span class="sxs-lookup"><span data-stu-id="a65f6-183">Action</span></span>  |
|---------|---------|
|<span data-ttu-id="a65f6-184">我看到纵向出现 "发生错误" 错误</span><span class="sxs-lookup"><span data-stu-id="a65f6-184">I see a 'Something went wrong' error on the vertical</span></span>|   <span data-ttu-id="a65f6-185">需要直排和结果类型才能完成设置。</span><span class="sxs-lookup"><span data-stu-id="a65f6-185">Both vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="a65f6-186">请确保已为相同的内容源创建了这两个。</span><span class="sxs-lookup"><span data-stu-id="a65f6-186">Make sure you have created both for the same content source.</span></span>      |
|<span data-ttu-id="a65f6-187">为什么我看不到结果版式，尽管我已经创建了一个？</span><span class="sxs-lookup"><span data-stu-id="a65f6-187">Why don't I see my result layout although I have created one?</span></span> | <span data-ttu-id="a65f6-188">要使用的结果类型需要几分钟时间，通常会缓存这些设置。</span><span class="sxs-lookup"><span data-stu-id="a65f6-188">It takes a few minutes for result types to be used as these settings are generally cached.</span></span> <span data-ttu-id="a65f6-189">请等待几分钟，然后重试</span><span class="sxs-lookup"><span data-stu-id="a65f6-189">Wait for a few minutes and try again</span></span>        |
|<span data-ttu-id="a65f6-190">在 "垂直" 或 "结果类型" 页上看不到任何内容源</span><span class="sxs-lookup"><span data-stu-id="a65f6-190">I don't see any content sources on the vertical or result type page</span></span>     |      <span data-ttu-id="a65f6-191">请确保已配置连接器和索引数据</span><span class="sxs-lookup"><span data-stu-id="a65f6-191">Make sure you have configured connectors and indexed data</span></span>   |



## <a name="next-steps"></a><span data-ttu-id="a65f6-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a65f6-192">Next steps</span></span>
[<span data-ttu-id="a65f6-193">步骤3：自定义结果布局</span><span class="sxs-lookup"><span data-stu-id="a65f6-193">STEP 3: Customize the results layout</span></span>](customize-results-layout.md)
