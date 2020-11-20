---
title: 连接器结果群集
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 连接器结果群集体验的详细信息
ms.openlocfilehash: eac4180a247fe17b4e86b57a69f2b7bdb79e56bb
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367716"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="b1166-103">图形连接器结果群集</span><span class="sxs-lookup"><span data-stu-id="b1166-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="b1166-104">图形连接器结果群集 (预览的概述) </span><span class="sxs-lookup"><span data-stu-id="b1166-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

 <span data-ttu-id="b1166-105">通过 Graph 连接器的结果群集，企业可以在其默认视图中搜索第三方数据源中的内容， (SharePoint 和 Office.com 中的所有选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="b1166-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view (the All tab) in SharePoint and Office.com.</span></span>

<span data-ttu-id="b1166-106">结果群集可帮助用户发现所有第三方内容 (previoulsy 绑定到一个位置中的单个连接器和垂直) 。</span><span class="sxs-lookup"><span data-stu-id="b1166-106">Result clusters help users discover all third party content (previoulsy tied to a single connector and vertical) in one place.</span></span> <span data-ttu-id="b1166-107">结果群集中显示的结果根据租户管理员在垂直搜索中配置它们的方式分组在一起。</span><span class="sxs-lookup"><span data-stu-id="b1166-107">The results shown in a result cluster are grouped together based on how the tenant administrator configures them in a search vertical.</span></span>  

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="b1166-108">如何选择和显示连接器结果</span><span class="sxs-lookup"><span data-stu-id="b1166-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="b1166-109">结果群集中提供的连接器结果派生自各个搜索带连接器内容的纵向。</span><span class="sxs-lookup"><span data-stu-id="b1166-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="b1166-110">每个垂直搜索提供一组相关结果，这些结果将成为候选结果群集。</span><span class="sxs-lookup"><span data-stu-id="b1166-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="b1166-111">根据每个项目的 "title" 属性、结果代码段和内容组件选择相关结果。</span><span class="sxs-lookup"><span data-stu-id="b1166-111">Relevant results are chosen based on the "title" property, result snippet, and content component of each item.</span></span>

<span data-ttu-id="b1166-112">为确保从搜索纵向发现内容，我们建议为您的项目提供有意义的标题。</span><span class="sxs-lookup"><span data-stu-id="b1166-112">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="b1166-113">这将影响结果群集候选人的仲裁，以及你的内容在结果群集中显示的可能性。</span><span class="sxs-lookup"><span data-stu-id="b1166-113">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="b1166-114">例如，除非用户使用 Id 查找内容，否则请避免使用 Id 作为属性 "title" 的值。</span><span class="sxs-lookup"><span data-stu-id="b1166-114">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="b1166-115">结果群集显示的频率因各种因素（如您配置的搜索纵向数量和内容类型）而异。</span><span class="sxs-lookup"><span data-stu-id="b1166-115">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="b1166-116">通过选择或忽略结果群集结果，您将隐式提供一些提示，这些提示将调整对结果群集触发的时间。</span><span class="sxs-lookup"><span data-stu-id="b1166-116">By either selecting or ignoring result cluster results, you will implicitly provide hints that will adjust the triggering of result clusters over time.</span></span>

<span data-ttu-id="b1166-117">结果群集中显示的连接器项目的搜索结果体验是系统生成的，不使用自定义的结果布局。</span><span class="sxs-lookup"><span data-stu-id="b1166-117">The search result experience for connector items shown in your result cluster is system generated and does not use custom result layouts.</span></span> <span data-ttu-id="b1166-118">如果希望结果群集中显示结果，则必须在连接注册过程中声明 "title" 属性和项目内容。</span><span class="sxs-lookup"><span data-stu-id="b1166-118">You must declare the "title" property and item content during connection registration if you want results to appear in your result cluster.</span></span>

## <a name="enable-result-clusters"></a><span data-ttu-id="b1166-119">启用结果群集</span><span class="sxs-lookup"><span data-stu-id="b1166-119">Enable result clusters</span></span>
  
<span data-ttu-id="b1166-120">默认情况下，结果群集体验处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="b1166-120">The result cluster experience is turned off by default.</span></span>  
<span data-ttu-id="b1166-121">按照以下步骤在组织级别启用体验：</span><span class="sxs-lookup"><span data-stu-id="b1166-121">Follow these steps to turn on the experience at the organization level:</span></span>

<span data-ttu-id="b1166-122">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="b1166-122">Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="b1166-123">在 [Microsoft 365 管理中心](https://admin.microsoft.com/)，转到 "**设置**  >  **搜索 & 智能**  >  **自定义**  >  **纵向**"。</span><span class="sxs-lookup"><span data-stu-id="b1166-123">In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to **Settings** > **Search & intelligence** > **Customization** > **Verticals**.</span></span>  
2. <span data-ttu-id="b1166-124">选择 " **全部** 垂直"，然后转到 " **显示连接器结果** " 部分。</span><span class="sxs-lookup"><span data-stu-id="b1166-124">Select  the **All** vertical and go to the **Show connector results** section.</span></span> <span data-ttu-id="b1166-125">在网站级别启用体验。</span><span class="sxs-lookup"><span data-stu-id="b1166-125">Turn on the experience at the site level.</span></span>

<span data-ttu-id="b1166-126">Sharepoint</span><span class="sxs-lookup"><span data-stu-id="b1166-126">Sharepoint</span></span>

1. <span data-ttu-id="b1166-127">在您希望结果群集体验的 SharePoint 网站上，转到 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="b1166-127">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="b1166-128">转到 "**网站信息**" > **查看所有网站设置**。</span><span class="sxs-lookup"><span data-stu-id="b1166-128">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="b1166-129">转到 "Microsoft Search" 部分，然后为 **此网站集选择 "配置 Microsoft search**"。</span><span class="sxs-lookup"><span data-stu-id="b1166-129">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="b1166-130">在导航窗格中，转到 " **自定义体验**"，然后选择 " **纵向**"。</span><span class="sxs-lookup"><span data-stu-id="b1166-130">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="b1166-131">选择 " **全部** 垂直"，然后按 "启用 **显示连接器结果**"。</span><span class="sxs-lookup"><span data-stu-id="b1166-131">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="b1166-132">启用后查看结果群集体验</span><span class="sxs-lookup"><span data-stu-id="b1166-132">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="b1166-133">打开结果群集体验后，可能需要几分钟的时间才能查看。</span><span class="sxs-lookup"><span data-stu-id="b1166-133">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="b1166-134">如果你想要立即体验，可以将 *cacheClear = true* 追加到 SharePoint 和 Office 中的 URL。</span><span class="sxs-lookup"><span data-stu-id="b1166-134">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
