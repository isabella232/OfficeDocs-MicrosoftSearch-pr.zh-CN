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
ms.openlocfilehash: 8b212f385d126b4f6c3513b066936db28387377f
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206965"
---
# <a name="customize-the-search-results-page"></a><span data-ttu-id="533f1-103">自定义搜索结果页</span><span class="sxs-lookup"><span data-stu-id="533f1-103">Customize the search results page</span></span>

<span data-ttu-id="533f1-104">您可以创建搜索纵向和结果类型，以自定义用户在[Bing](https://bing.com)中的 microsoft [SharePoint](https://sharepoint.com/)、 [microsoft Office](https://office.com)和 microsoft 搜索中进行搜索时看到的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="533f1-104">You can create search verticals and result types to customize the search results that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="533f1-105">纵向使用户能够更轻松地查找他们有权查看的信息。</span><span class="sxs-lookup"><span data-stu-id="533f1-105">Verticals make it easier for users to find the information that they have permission to see.</span></span> <span data-ttu-id="533f1-106">例如，可以为市场营销部门中的用户创建从第三方软件到第三方软件的市场营销分析数据的垂直搜索。</span><span class="sxs-lookup"><span data-stu-id="533f1-106">For example, you could create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="533f1-107">您还可以定义结果类型并自定义此数据的布局。</span><span class="sxs-lookup"><span data-stu-id="533f1-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="533f1-108">您可以在以下级别创建纵向和结果类型：</span><span class="sxs-lookup"><span data-stu-id="533f1-108">You can create verticals and result types at these levels:</span></span>

- <span data-ttu-id="533f1-109">**组织级别** –如果在组织级别添加垂直，则当用户从 [SharePoint](https://sharepoint.com/) 起始页、 [Office](https://office.com)或 [Bing](https://bing.com)进行搜索时，它将显示在搜索结果页上。</span><span class="sxs-lookup"><span data-stu-id="533f1-109">**Organization level** – When you add a vertical at the organization level, it appears on the search results page when users search from their [SharePoint](https://sharepoint.com/) start page, on [Office](https://office.com), or on [Bing](https://bing.com).</span></span>
- <span data-ttu-id="533f1-110">**网站级别** –例如，您可能希望使客户服务员工能够直接从其部门的 SharePoint 网站搜索 *严重级别为 1* 的事件。</span><span class="sxs-lookup"><span data-stu-id="533f1-110">**Site level** – For example, you might want to enable your customer service employees to search for *Severity 1* incidents directly from their department’s SharePoint site.</span></span>

## <a name="search-verticals-explained"></a><span data-ttu-id="533f1-111">介绍的搜索纵向</span><span class="sxs-lookup"><span data-stu-id="533f1-111">Search verticals explained</span></span>

<span data-ttu-id="533f1-112">在 Microsoft 搜索结果页面的顶部有一排选项卡。</span><span class="sxs-lookup"><span data-stu-id="533f1-112">At the top of the Microsoft Search results page, there's a row of tabs.</span></span> <span data-ttu-id="533f1-113">这些是搜索纵向。</span><span class="sxs-lookup"><span data-stu-id="533f1-113">These are the search verticals.</span></span> <span data-ttu-id="533f1-114">垂直搜索仅显示特定类型或特定内容的结果。</span><span class="sxs-lookup"><span data-stu-id="533f1-114">A search vertical only shows results of a certain type or from certain content.</span></span> <span data-ttu-id="533f1-115">例如， **文件** 或 **新闻**。</span><span class="sxs-lookup"><span data-stu-id="533f1-115">Examples are **Files** or **News**.</span></span> <span data-ttu-id="533f1-116">默认情况下，Microsoft Search 将显示 **所有**行业、 **人员**、 **文件**、 **网站**和 **新闻**。</span><span class="sxs-lookup"><span data-stu-id="533f1-116">By default, Microsoft Search shows the verticals **All**, **People**, **Files**, **Sites**, and **News**.</span></span>  

<span data-ttu-id="533f1-117">您可以添加与您的组织相关的搜索纵向。</span><span class="sxs-lookup"><span data-stu-id="533f1-117">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="533f1-118">这些将显示在 [SharePoint](https://sharepoint.com/)、 [Office](https://Office.com)和 [Bing](https://bing.com)中的 Microsoft 搜索结果页面上。</span><span class="sxs-lookup"><span data-stu-id="533f1-118">These will appear on the Microsoft Search results page in [SharePoint](https://sharepoint.com/), [Office](https://Office.com), and [Bing](https://bing.com).</span></span> <span data-ttu-id="533f1-119">例如，您可以为与市场营销相关的内容创建一个垂直的，并根据每个组需要的信息类型创建另一个销售。</span><span class="sxs-lookup"><span data-stu-id="533f1-119">For example, you could create a vertical for marketing-related content and another for sales, based on the type of information that each group needs.</span></span> <span data-ttu-id="533f1-120">您可以将纵向添加到仅显示通过连接器索引的内容中的结果。</span><span class="sxs-lookup"><span data-stu-id="533f1-120">You can add verticals to show results only from content indexed via connectors.</span></span>  

>[!NOTE]
> <span data-ttu-id="533f1-121">在 Microsoft Graph 连接器预览中，纵向和结果类型当前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="533f1-121">Verticals and result types are currently in preview as a part of the Microsoft Graph connectors preview.</span></span> <span data-ttu-id="533f1-122">有关预览的详细信息，请参阅 [连接器预览](connectors-preview.md)。</span><span class="sxs-lookup"><span data-stu-id="533f1-122">For more about the preview, see [Connectors preview](connectors-preview.md).</span></span> <span data-ttu-id="533f1-123">若要参与预览，必须先提交 [Microsoft Graph 连接器预览注册表单](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)。</span><span class="sxs-lookup"><span data-stu-id="533f1-123">To participate in the preview, you must first submit the [Microsoft Graph Connectors Preview Signup form](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="533f1-124">注意事项</span><span class="sxs-lookup"><span data-stu-id="533f1-124">Things to consider</span></span>

<span data-ttu-id="533f1-125">开始之前，请确保已对连接器编制索引。</span><span class="sxs-lookup"><span data-stu-id="533f1-125">Before you start, make sure that the connector has been indexed.</span></span> <span data-ttu-id="533f1-126">这可能最长为48个小时，具体取决于文件大小。</span><span class="sxs-lookup"><span data-stu-id="533f1-126">This can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="533f1-127">无法为驻留在 [SharePoint](https://sharepoint.com/)中的内容创建垂直。</span><span class="sxs-lookup"><span data-stu-id="533f1-127">You can’t create a vertical for content that resides in [SharePoint](https://sharepoint.com/).</span></span>

<span data-ttu-id="533f1-128">有三个基本步骤可添加垂直：</span><span class="sxs-lookup"><span data-stu-id="533f1-128">There are three basic steps to add a vertical:</span></span>

1. <span data-ttu-id="533f1-129">创建垂直。</span><span class="sxs-lookup"><span data-stu-id="533f1-129">Create the vertical.</span></span> <span data-ttu-id="533f1-130">在此步骤中，您将定义要搜索的内容的垂直名称、内容源和范围。</span><span class="sxs-lookup"><span data-stu-id="533f1-130">In this step, you define the vertical’s name, content source, and scope of the content to search.</span></span>
2. <span data-ttu-id="533f1-131">定义此垂直外观的效果。</span><span class="sxs-lookup"><span data-stu-id="533f1-131">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="533f1-132">启用垂直 (显示从垂直列表页面) 。</span><span class="sxs-lookup"><span data-stu-id="533f1-132">Enable the vertical (to be displayed) from the vertical list page.</span></span>

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="533f1-133">步骤1：创建垂直搜索</span><span class="sxs-lookup"><span data-stu-id="533f1-133">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="533f1-134">启动向导后，您可以通过步骤来定义要搜索的内容的垂直名称、内容源和范围。</span><span class="sxs-lookup"><span data-stu-id="533f1-134">After you start the wizard, you're guided through the steps to define the vertical's name, content source, and scope of the content to search.</span></span> <span data-ttu-id="533f1-135">垂直在禁用状态中创建。</span><span class="sxs-lookup"><span data-stu-id="533f1-135">The vertical is created in a disabled state.</span></span> <span data-ttu-id="533f1-136">你将在稍后启用它。</span><span class="sxs-lookup"><span data-stu-id="533f1-136">You'll enable it later.</span></span>

<span data-ttu-id="533f1-137">您可以使用一组有限的 [关键字查询语言 (KQL) ](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) 来缩小范围。</span><span class="sxs-lookup"><span data-stu-id="533f1-137">You can use a limited set of [Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow the scope.</span></span> <span data-ttu-id="533f1-138">此页列出了可用的属性。</span><span class="sxs-lookup"><span data-stu-id="533f1-138">This page lists the properties that are available.</span></span> <span data-ttu-id="533f1-139">我们建议您将 freetext 关键字和属性限制用于用于创建 KQL 的布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="533f1-139">We recommend that you use freetext keywords and property restrictions with boolean operators for creating the KQL.</span></span>

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="533f1-140">在组织级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="533f1-140">Create a vertical at the organization level</span></span>

<span data-ttu-id="533f1-141">若要在 [SharePoint](https://sharepoint.com/) 主页、 [Office](https://office.com)或 [Bing](https://bing.com)中的 Microsoft 搜索上创建垂直，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="533f1-141">To create the vertical on Microsoft Search in [SharePoint](https://sharepoint.com/) home, [Office](https://office.com), or [Bing](https://bing.com), follow these steps:</span></span>

1. <span data-ttu-id="533f1-142">在 [Microsoft 365 管理中心](https://admin.microsoft.com)，转到 " [**纵向**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)"。</span><span class="sxs-lookup"><span data-stu-id="533f1-142">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
1. <span data-ttu-id="533f1-143">选择 " **添加** " 以开始。</span><span class="sxs-lookup"><span data-stu-id="533f1-143">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="533f1-144">在网站级别创建垂直</span><span class="sxs-lookup"><span data-stu-id="533f1-144">Create a vertical at the site level</span></span>

1. <span data-ttu-id="533f1-145">在您希望垂直的 [SharePoint](https://sharepoint.com/) 网站上，转到 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="533f1-145">On the [SharePoint](https://sharepoint.com/) site where you want the vertical, go to **Settings**.</span></span>
1. <span data-ttu-id="533f1-146">选择 " **网站信息** "，然后 **查看 "所有网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="533f1-146">Select **Site information** and then **View all site settings**.</span></span>
1. <span data-ttu-id="533f1-147">查找 " **Microsoft search** " 部分，然后为 **此网站集选择 "配置 Microsoft search**"。</span><span class="sxs-lookup"><span data-stu-id="533f1-147">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="533f1-148">在导航窗格中，转到 " **自定义体验**"，然后选择 " **纵向** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="533f1-148">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
1. <span data-ttu-id="533f1-149">若要添加垂直，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="533f1-149">To add a vertical, select **Add**.</span></span>
  <span data-ttu-id="533f1-150">或者，若要编辑垂直，请在列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="533f1-150">Or, to edit a vertical, select it in the list.</span></span>

<span data-ttu-id="533f1-151">请记住，将在禁用状态下创建纵向。</span><span class="sxs-lookup"><span data-stu-id="533f1-151">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="533f1-152">必须先启用它们，然后用户才能看到它们。</span><span class="sxs-lookup"><span data-stu-id="533f1-152">They must be enabled before users can see them.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="533f1-153">步骤2：创建结果类型</span><span class="sxs-lookup"><span data-stu-id="533f1-153">STEP 2: Create the result types</span></span>

<span data-ttu-id="533f1-154">您可以通过使用结果类型设计布局来定义结果在垂直方向的显示方式。</span><span class="sxs-lookup"><span data-stu-id="533f1-154">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="533f1-155">结果布局可让您直接在搜索结果中显示重要信息，因此用户无需选择每个结果即可查看他们是否找到了要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="533f1-155">The result layout lets you show important information directly in the search results, so users don't have to select each result to see if they found what they're looking for.</span></span>

<span data-ttu-id="533f1-p112">搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。它包含以下几个方面：</span><span class="sxs-lookup"><span data-stu-id="533f1-p112">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways. It consists of the following:</span></span>

- <span data-ttu-id="533f1-158">用于比较每个搜索结果的**一个或多个条件**，例如搜索结果的内容源。</span><span class="sxs-lookup"><span data-stu-id="533f1-158">**One or more conditions** to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="533f1-159">要用于满足条件的搜索结果的 **结果布局** 。</span><span class="sxs-lookup"><span data-stu-id="533f1-159">A **result layout** to use for search results that meet the conditions.</span></span> <span data-ttu-id="533f1-160">结果布局控制满足条件的所有结果在搜索结果页面上的显示和行为方式。</span><span class="sxs-lookup"><span data-stu-id="533f1-160">The result layout controls the way that all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="533f1-161">**必须至少创建一个结果类型，才能在垂直方向上显示。**</span><span class="sxs-lookup"><span data-stu-id="533f1-161">**You must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="533f1-162">您可以为每个垂直创建多个结果类型，从而允许您对不同类型的结果使用不同的布局。</span><span class="sxs-lookup"><span data-stu-id="533f1-162">You can create multiple result types for each vertical, which allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="533f1-163">例如，您可以自定义 *严重级别 1* 事件，使其具有更突出的颜色和与 *严重级别 3* 事件相比较大的字体。</span><span class="sxs-lookup"><span data-stu-id="533f1-163">For example, you can customize *Severity 1* incidents to have more prominent colors and a larger font compared to *Severity 3* incidents.</span></span>

<span data-ttu-id="533f1-164">启动向导后，您可以通过步骤来定义结果类型的名称、内容源和条件。</span><span class="sxs-lookup"><span data-stu-id="533f1-164">After you start the wizard, you're guided through the steps to define the name, content source, and conditions for the result type.</span></span> <span data-ttu-id="533f1-165">您可以从列表视图定义结果类型的优先级。</span><span class="sxs-lookup"><span data-stu-id="533f1-165">You can define the priority of the result type from the list view.</span></span>
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="533f1-166">在组织级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="533f1-166">Create a result type at the organization level</span></span>

1. <span data-ttu-id="533f1-167">在 [Microsoft 365 管理中心](https://admin.microsoft.com)，转到 " [**结果类型**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)"。</span><span class="sxs-lookup"><span data-stu-id="533f1-167">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).</span></span>
1. <span data-ttu-id="533f1-168">若要添加 **结果类型**，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="533f1-168">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="533f1-169">若要编辑结果类型，请选择相关列表中的 "结果类型"。</span><span class="sxs-lookup"><span data-stu-id="533f1-169">To edit a result type, select the result type in the relevant list.</span></span>

### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="533f1-170">在网站级别创建结果类型</span><span class="sxs-lookup"><span data-stu-id="533f1-170">Create a results type at the site level</span></span>

1. <span data-ttu-id="533f1-171">在要创建结果类型的 [SharePoint](https://sharepoint.com/) 网站上，转到 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="533f1-171">On the [SharePoint](https://sharepoint.com/) site where you want to create the result type, go to **Settings**.</span></span>
1. <span data-ttu-id="533f1-172">选择 " **网站信息** "，然后 **查看 "所有网站设置**"。</span><span class="sxs-lookup"><span data-stu-id="533f1-172">Select **Site information** and then **View all site settings**.</span></span>
1. <span data-ttu-id="533f1-173">查找 "Microsoft Search" 部分，然后为 **此网站集选择 "配置 Microsoft search**"。</span><span class="sxs-lookup"><span data-stu-id="533f1-173">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="533f1-174">在导航窗格中，转到 " **自定义体验**"，然后选择 " **结果类型** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="533f1-174">In the navigation pane, go to **Custom experience**, and select **Result type** tab.</span></span>
1. <span data-ttu-id="533f1-175">若要添加结果类型，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="533f1-175">To add a result type, select **Add**.</span></span>  <span data-ttu-id="533f1-176">或者，若要编辑结果类型，请在列表中选择 "结果类型"。</span><span class="sxs-lookup"><span data-stu-id="533f1-176">Or, to edit a result type, select the result type in the list.</span></span>

### <a name="view-the-vertical-after-its-enabled"></a><span data-ttu-id="533f1-177">在已启用时查看垂直</span><span class="sxs-lookup"><span data-stu-id="533f1-177">View the vertical after it's enabled</span></span>

<span data-ttu-id="533f1-178">在启用垂直后，可能需要一段时间才能进行查看。</span><span class="sxs-lookup"><span data-stu-id="533f1-178">After you enable the vertical, it might take a while before you can view it.</span></span> <span data-ttu-id="533f1-179">如果您不希望在启用后等待，则可以将 **cacheClear = true** 追加到 [SharePoint](https://sharepoint.com/) 和 [Office](https://office.com) 中的 URL，以便立即查看垂直方向。</span><span class="sxs-lookup"><span data-stu-id="533f1-179">If you don't want to wait after enabling it, you can append **cacheClear=true** to the URL in [SharePoint](https://sharepoint.com/) and [Office](https://office.com) to view the vertical immediately.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="533f1-180">故障排除</span><span class="sxs-lookup"><span data-stu-id="533f1-180">Troubleshooting</span></span>

<span data-ttu-id="533f1-181">下面列出了你可能遇到的常见问题和解决这些问题的措施。</span><span class="sxs-lookup"><span data-stu-id="533f1-181">Here's a list of common issues you might encounter and actions to fix them.</span></span>

|<span data-ttu-id="533f1-182">错误</span><span class="sxs-lookup"><span data-stu-id="533f1-182">Error</span></span>  |<span data-ttu-id="533f1-183">Action</span><span class="sxs-lookup"><span data-stu-id="533f1-183">Action</span></span>  |
|---------|---------|
| <span data-ttu-id="533f1-184">我在垂直处看到 "出现了错误" 错误消息。</span><span class="sxs-lookup"><span data-stu-id="533f1-184">I see a "Something went wrong" error message on the vertical.</span></span> | <span data-ttu-id="533f1-185">需要垂直和结果类型才能完成设置。</span><span class="sxs-lookup"><span data-stu-id="533f1-185">Both the vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="533f1-186">请确保已为相同的内容源创建了这两个。</span><span class="sxs-lookup"><span data-stu-id="533f1-186">Make sure you have created both for the same content source.</span></span> |
| <span data-ttu-id="533f1-187">我看不到结果布局，尽管我创建了它。</span><span class="sxs-lookup"><span data-stu-id="533f1-187">I don't see my result layout, although I created one.</span></span> | <span data-ttu-id="533f1-188">此过程需要几分钟时间，因为通常会缓存这些设置。</span><span class="sxs-lookup"><span data-stu-id="533f1-188">It takes a few minutes because these settings are generally cached.</span></span> <span data-ttu-id="533f1-189">请等待几分钟，然后重试。</span><span class="sxs-lookup"><span data-stu-id="533f1-189">Wait for a few minutes and try again.</span></span>        |
| <span data-ttu-id="533f1-190">在 "垂直" 或 "结果类型" 页上看不到任何内容源。</span><span class="sxs-lookup"><span data-stu-id="533f1-190">I don't see any content sources on the vertical or result type page.</span></span> | <span data-ttu-id="533f1-191">请确保已配置连接器和索引数据。</span><span class="sxs-lookup"><span data-stu-id="533f1-191">Make sure you have configured connectors and indexed data.</span></span>   |

## <a name="next-steps"></a><span data-ttu-id="533f1-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="533f1-192">Next steps</span></span>

[<span data-ttu-id="533f1-193">步骤3：自定义结果布局</span><span class="sxs-lookup"><span data-stu-id="533f1-193">STEP 3: Customize the results layout</span></span>](customize-results-layout.md)
