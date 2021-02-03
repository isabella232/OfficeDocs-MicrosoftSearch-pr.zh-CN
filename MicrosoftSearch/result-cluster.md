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
ms.openlocfilehash: fb29fb9c14811698fb7c5d043853b57231c76a0b
ms.sourcegitcommit: d1bc6c41ecf47584373ce57543502bed55753d0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080834"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="a707b-103">图形连接器结果群集</span><span class="sxs-lookup"><span data-stu-id="a707b-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="a707b-104">Graph 连接器结果群集 (预览) </span><span class="sxs-lookup"><span data-stu-id="a707b-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="a707b-105">借助 Graph 连接器结果群集，企业可以在默认视图"所有"选项卡（SharePoint、Office.com 和必应中的 Microsoft 搜索）中搜索第三方数据源中的内容。</span><span class="sxs-lookup"><span data-stu-id="a707b-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="a707b-106">结果群集可帮助用户在一个地方发现所有第三方内容。</span><span class="sxs-lookup"><span data-stu-id="a707b-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="a707b-107">结果群集中显示的结果根据垂直搜索配置分组在一起。</span><span class="sxs-lookup"><span data-stu-id="a707b-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="a707b-108">如何选择和显示连接器结果</span><span class="sxs-lookup"><span data-stu-id="a707b-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="a707b-109">结果群集中提供的连接器结果派生自具有连接器内容的单个垂直搜索。</span><span class="sxs-lookup"><span data-stu-id="a707b-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="a707b-110">每个垂直搜索都提供一组成为候选结果群集的相关结果。</span><span class="sxs-lookup"><span data-stu-id="a707b-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="a707b-111">根据每个项目的"title"属性和"content"属性选择相关结果。</span><span class="sxs-lookup"><span data-stu-id="a707b-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="a707b-112">内容属性在架构上 *标记为 isContent=true。*</span><span class="sxs-lookup"><span data-stu-id="a707b-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="a707b-113">为了确保从垂直搜索发现内容，我们建议为项目提供有意义的标题。</span><span class="sxs-lookup"><span data-stu-id="a707b-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="a707b-114">这会对结果群集候选项的仲裁和内容在结果群集中出现的可能性产生积极的影响。</span><span class="sxs-lookup"><span data-stu-id="a707b-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="a707b-115">例如，避免将 ID 用作"title"属性的值，除非你的用户使用 ID 来查找内容。</span><span class="sxs-lookup"><span data-stu-id="a707b-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="a707b-116">显示结果群集的频繁程度因因素而异，例如配置垂直搜索的数量和内容类型。</span><span class="sxs-lookup"><span data-stu-id="a707b-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="a707b-117">通过交互或忽略结果群集，用户将隐式提供将随着时间的推移调整其触发的提示。</span><span class="sxs-lookup"><span data-stu-id="a707b-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="a707b-118">结果群集中显示的连接器项的搜索结果体验使用 [您定义](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) 的结果类型。</span><span class="sxs-lookup"><span data-stu-id="a707b-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="a707b-119">如果未配置结果类型，则使用 [系统生成的](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) 布局。</span><span class="sxs-lookup"><span data-stu-id="a707b-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="a707b-120">我们建议将"title"属性用作搜索结果标题，将"content"属性用作搜索说明。</span><span class="sxs-lookup"><span data-stu-id="a707b-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="a707b-121">这将通过准确触发结果群集和群集中最相关的结果为用户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="a707b-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="a707b-122">启用结果群集</span><span class="sxs-lookup"><span data-stu-id="a707b-122">Enable result clusters</span></span>
  
<span data-ttu-id="a707b-123">默认情况下，结果群集体验已关闭。</span><span class="sxs-lookup"><span data-stu-id="a707b-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="a707b-124">按照以下步骤在组织级别启用体验：</span><span class="sxs-lookup"><span data-stu-id="a707b-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="a707b-125">在 [Microsoft 365 管理中心](https://admin.microsoft.com)中，转到 [**"垂直"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)</span><span class="sxs-lookup"><span data-stu-id="a707b-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="a707b-126">选择"**全部** 垂直"，然后启用 **"显示连接器结果"。**</span><span class="sxs-lookup"><span data-stu-id="a707b-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="a707b-127">请按照以下步骤在 SharePoint 网站级别打开体验：</span><span class="sxs-lookup"><span data-stu-id="a707b-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="a707b-128">在想要获得结果群集体验的 SharePoint 网站上，转到"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="a707b-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="a707b-129">转到"**网站信息** > **查看所有网站设置"。**</span><span class="sxs-lookup"><span data-stu-id="a707b-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="a707b-130">转到"Microsoft 搜索"部分，然后为此 **网站集选择"配置 Microsoft 搜索"。**</span><span class="sxs-lookup"><span data-stu-id="a707b-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="a707b-131">在导航窗格中，转到"**自定义体验"，** 然后选择 **"垂直"。**</span><span class="sxs-lookup"><span data-stu-id="a707b-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="a707b-132">选择"**全部** 垂直"，然后启用 **"显示连接器结果"。**</span><span class="sxs-lookup"><span data-stu-id="a707b-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="a707b-133">启用后查看结果群集体验</span><span class="sxs-lookup"><span data-stu-id="a707b-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="a707b-134">打开结果群集体验后，可能需要 12 小时才能查看它。</span><span class="sxs-lookup"><span data-stu-id="a707b-134">After you turn on the result cluster experience, it can take up to 12 hours before you can view it.</span></span> <span data-ttu-id="a707b-135">如果您需要立即体验，可以将 *cacheClear=true* 追加到 SharePoint 和 Office 中的 URL。</span><span class="sxs-lookup"><span data-stu-id="a707b-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
