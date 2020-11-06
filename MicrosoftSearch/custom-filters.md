---
title: 管理自定义筛选器
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 管理自定义筛选器
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927377"
---
# <a name="create-custom-filters"></a><span data-ttu-id="8fc12-103">创建自定义筛选器</span><span class="sxs-lookup"><span data-stu-id="8fc12-103">Create custom Filters</span></span>

<span data-ttu-id="8fc12-104">您可以创建筛选器，以自定义用户在[Bing](https://bing.com)中的 microsoft [SharePoint](https://sharepoint.com/)、Microsoft [Office](https://office.com)和 microsoft 搜索中进行搜索时看到的搜索体验。</span><span class="sxs-lookup"><span data-stu-id="8fc12-104">You can create filters to customize the search experience that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="8fc12-105">通过筛选器，用户可以快速从搜索查询中优化结果集。</span><span class="sxs-lookup"><span data-stu-id="8fc12-105">Filters lets users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="8fc12-106">可以基于 connection 属性在垂直方向创建自定义筛选器。</span><span class="sxs-lookup"><span data-stu-id="8fc12-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="8fc12-107">例如，您可以在自定义垂直内为 ServiceNow 连接创建 **已发布的 On** 筛选器。</span><span class="sxs-lookup"><span data-stu-id="8fc12-107">For example, you can create a **Published On** filter for ServiceNow connection inside a custom vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="8fc12-108">注意事项</span><span class="sxs-lookup"><span data-stu-id="8fc12-108">Things to consider</span></span>

1. <span data-ttu-id="8fc12-109">对于在连接内容源上创建自定义筛选器，提供了一些附加功能：</span><span class="sxs-lookup"><span data-stu-id="8fc12-109">For creating custom filter on connection content source, some additional capabilities are provided:</span></span>
- <span data-ttu-id="8fc12-110">您还可以在 "连接器源" 属性的 "别名" 上创建筛选器</span><span class="sxs-lookup"><span data-stu-id="8fc12-110">You can also create filter on an alias to connector source properties</span></span>
- <span data-ttu-id="8fc12-111">如果垂直具有多个连接，则可以通过这些连接创建公用筛选器。</span><span class="sxs-lookup"><span data-stu-id="8fc12-111">In case your vertical has multiple connections then you can create a common filter across these connections.</span></span> <span data-ttu-id="8fc12-112">为此，可以通过在别名源属性在不同连接之间进行的通用别名创建筛选器来实现。</span><span class="sxs-lookup"><span data-stu-id="8fc12-112">This can be done by creating the filter on an common alias which aliases source properties across across different connections.</span></span> <span data-ttu-id="8fc12-113">例如，您可以通过创建别名，在 ServiceNow & Jira 连接中创建 **作者** 筛选器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fc12-113">For example you can create an **Author** filter across a ServiceNow & a Jira connection by creating aliases as follows:</span></span>

| <span data-ttu-id="8fc12-114">Connection</span><span class="sxs-lookup"><span data-stu-id="8fc12-114">Connection</span></span> | <span data-ttu-id="8fc12-115">属性</span><span class="sxs-lookup"><span data-stu-id="8fc12-115">Property</span></span> | <span data-ttu-id="8fc12-116">Alias</span><span class="sxs-lookup"><span data-stu-id="8fc12-116">Alias</span></span> |
| --- | --- | --- |
| <span data-ttu-id="8fc12-117">服务现在</span><span class="sxs-lookup"><span data-stu-id="8fc12-117">Service Now</span></span> | <span data-ttu-id="8fc12-118">所有者</span><span class="sxs-lookup"><span data-stu-id="8fc12-118">Owner</span></span> | <span data-ttu-id="8fc12-119">作者</span><span class="sxs-lookup"><span data-stu-id="8fc12-119">Author</span></span> |
| <span data-ttu-id="8fc12-120">Jira</span><span class="sxs-lookup"><span data-stu-id="8fc12-120">Jira</span></span> | <span data-ttu-id="8fc12-121">Publisher</span><span class="sxs-lookup"><span data-stu-id="8fc12-121">Publisher</span></span> | <span data-ttu-id="8fc12-122">作者</span><span class="sxs-lookup"><span data-stu-id="8fc12-122">Author</span></span> |

2. <span data-ttu-id="8fc12-123">筛选器位于垂直范围内。</span><span class="sxs-lookup"><span data-stu-id="8fc12-123">Filters exist within the scope of the vertical.</span></span> <span data-ttu-id="8fc12-124">由此</span><span class="sxs-lookup"><span data-stu-id="8fc12-124">Hence,</span></span>  
- <span data-ttu-id="8fc12-125">如果筛选器是以组织级别的垂直方式创建的，则筛选器将仅在组织级别可见</span><span class="sxs-lookup"><span data-stu-id="8fc12-125">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
- <span data-ttu-id="8fc12-126">如果在垂直位置创建了筛选器，该筛选器在网站级别，则筛选器仅在网站级别可见。</span><span class="sxs-lookup"><span data-stu-id="8fc12-126">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="steps-to-create-custom-filter"></a><span data-ttu-id="8fc12-127">创建自定义筛选器的步骤</span><span class="sxs-lookup"><span data-stu-id="8fc12-127">Steps to Create custom filter</span></span>

### <a name="create-filter-in-organizational-level-vertical"></a><span data-ttu-id="8fc12-128">在组织级别中创建筛选器垂直：</span><span class="sxs-lookup"><span data-stu-id="8fc12-128">Create filter in organizational level vertical:</span></span>

<span data-ttu-id="8fc12-129">若要在 Microsoft search 中创建筛选器，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8fc12-129">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="8fc12-130">在 Microsoft 365 管理中心，转到 " [纵向](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) " 页面。</span><span class="sxs-lookup"><span data-stu-id="8fc12-130">In the Microsoft 365 admin center, go to the [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) page.</span></span>
2. <span data-ttu-id="8fc12-131">创建/编辑要在其中创建筛选器的垂直</span><span class="sxs-lookup"><span data-stu-id="8fc12-131">Create/Edit the vertical in which you want to create the filter</span></span>
3. <span data-ttu-id="8fc12-132">导航到向导中的 "筛选器" 步骤</span><span class="sxs-lookup"><span data-stu-id="8fc12-132">Navigate to the 'Filters' step in the wizard</span></span>
4. <span data-ttu-id="8fc12-133">单击 "添加筛选器"，并在添加筛选器后开始，可以查看并保存垂直。</span><span class="sxs-lookup"><span data-stu-id="8fc12-133">Click on 'Add Filter' and get started After adding filters, you can review and save the vertical.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8fc12-134">已知限制</span><span class="sxs-lookup"><span data-stu-id="8fc12-134">Known Limitations</span></span>

1. <span data-ttu-id="8fc12-135">您当前可以仅在字符串 & 日期类型托管属性上创建筛选器。</span><span class="sxs-lookup"><span data-stu-id="8fc12-135">You can currently create filters only on String & Date type managed properties.</span></span>
2. <span data-ttu-id="8fc12-136">无法创建分层筛选器</span><span class="sxs-lookup"><span data-stu-id="8fc12-136">You cannot create hierarchical filters</span></span>

## <a name="resources"></a><span data-ttu-id="8fc12-137">资源</span><span class="sxs-lookup"><span data-stu-id="8fc12-137">Resources</span></span>

[<span data-ttu-id="8fc12-138">自定义搜索结果页面</span><span class="sxs-lookup"><span data-stu-id="8fc12-138">Customize search result page</span></span>](customize-search-page.md)