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
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790326"
---
# <a name="manage-custom-filters"></a><span data-ttu-id="8e4ca-103">管理自定义筛选器</span><span class="sxs-lookup"><span data-stu-id="8e4ca-103">Manage custom filters</span></span>

<span data-ttu-id="8e4ca-104">可以使用筛选器自定义 Microsoft 搜索体验。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-104">You can use filters to customize the Microsoft Search experience.</span></span> <span data-ttu-id="8e4ca-105">通过筛选器，用户可以快速优化其搜索查询中的结果集。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-105">Filters let users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="8e4ca-106">可以基于连接属性在垂直方向上创建自定义筛选器。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="8e4ca-107">例如，可以在垂直方向上为 ServiceNow 连接创建" **发布** 时间"筛选器。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-107">For example, you can create a **Published On** filter for ServiceNow connection inside a vertical.</span></span>

## <a name="create-a-filter-in-an-organizational-level-vertical"></a><span data-ttu-id="8e4ca-108">在组织级别垂直创建筛选器</span><span class="sxs-lookup"><span data-stu-id="8e4ca-108">Create a filter in an organizational level vertical</span></span>

<span data-ttu-id="8e4ca-109">若要在 Microsoft 搜索上创建筛选器，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8e4ca-109">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="8e4ca-110">在 Microsoft 365 管理中心中，转到["垂直"。](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)</span><span class="sxs-lookup"><span data-stu-id="8e4ca-110">In the Microsoft 365 admin center, go to [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
1. <span data-ttu-id="8e4ca-111">创建/编辑要创建筛选器的垂直方向</span><span class="sxs-lookup"><span data-stu-id="8e4ca-111">Create/Edit the vertical in which you want to create the filter</span></span>
1. <span data-ttu-id="8e4ca-112">导航到向导中的"筛选器"步骤</span><span class="sxs-lookup"><span data-stu-id="8e4ca-112">Navigate to the 'Filters' step in the wizard</span></span>
1. <span data-ttu-id="8e4ca-113">单击"添加筛选器"并开始操作</span><span class="sxs-lookup"><span data-stu-id="8e4ca-113">Click on 'Add Filter' and get started</span></span>
1. <span data-ttu-id="8e4ca-114">添加筛选器后，你可以查看并保存垂直。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-114">After adding filters, you can review and save the vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="8e4ca-115">注意事项</span><span class="sxs-lookup"><span data-stu-id="8e4ca-115">Things to consider</span></span>

1. <span data-ttu-id="8e4ca-116">连接内容上存在其他筛选器功能。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-116">Additional filter capabilities exist on connection content.</span></span>

    - <span data-ttu-id="8e4ca-117">还可以在别名上创建连接器源属性的筛选器</span><span class="sxs-lookup"><span data-stu-id="8e4ca-117">You can also create filter on an alias to connector source properties</span></span>
    - <span data-ttu-id="8e4ca-118">如果垂直连接有多个连接，可以在这些连接之间创建一个公用筛选器。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-118">If a vertical has multiple connections, you can create a common filter across these connections.</span></span> <span data-ttu-id="8e4ca-119">为此，可以在常见别名上创建筛选器，该筛选器将跨不同连接对源属性进行别名设置。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-119">This can be done by creating the filter on an common alias which aliases source properties across across the different connections.</span></span> <span data-ttu-id="8e4ca-120">例如，可以通过创建别名跨ServiceNow 和 Jira 连接创建作者筛选器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e4ca-120">For example you can create an **Author** filter across a ServiceNow and a Jira connection by creating aliases as follows:</span></span>

    | <span data-ttu-id="8e4ca-121">Connection</span><span class="sxs-lookup"><span data-stu-id="8e4ca-121">Connection</span></span> | <span data-ttu-id="8e4ca-122">属性</span><span class="sxs-lookup"><span data-stu-id="8e4ca-122">Property</span></span> | <span data-ttu-id="8e4ca-123">别名</span><span class="sxs-lookup"><span data-stu-id="8e4ca-123">Alias</span></span> |
    | --- | --- | --- |
    | <span data-ttu-id="8e4ca-124">服务现在</span><span class="sxs-lookup"><span data-stu-id="8e4ca-124">Service Now</span></span> | <span data-ttu-id="8e4ca-125">所有者</span><span class="sxs-lookup"><span data-stu-id="8e4ca-125">Owner</span></span> | <span data-ttu-id="8e4ca-126">作者</span><span class="sxs-lookup"><span data-stu-id="8e4ca-126">Author</span></span> |
    | <span data-ttu-id="8e4ca-127">Jira</span><span class="sxs-lookup"><span data-stu-id="8e4ca-127">Jira</span></span> | <span data-ttu-id="8e4ca-128">Publisher</span><span class="sxs-lookup"><span data-stu-id="8e4ca-128">Publisher</span></span> | <span data-ttu-id="8e4ca-129">作者</span><span class="sxs-lookup"><span data-stu-id="8e4ca-129">Author</span></span> |

1. <span data-ttu-id="8e4ca-130">筛选器存在于垂直范围内。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-130">Filters exist within the scope of a vertical.</span></span>

    - <span data-ttu-id="8e4ca-131">如果在组织级别以垂直方向创建筛选器，则筛选器将仅在组织级别可见</span><span class="sxs-lookup"><span data-stu-id="8e4ca-131">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
    - <span data-ttu-id="8e4ca-132">如果在网站级别以垂直方式创建筛选器，则筛选器将仅在网站级别可见。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-132">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8e4ca-133">已知限制</span><span class="sxs-lookup"><span data-stu-id="8e4ca-133">Known Limitations</span></span>

1. <span data-ttu-id="8e4ca-134">当前只能对字符串类型托管&创建筛选器。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-134">You can currently create filters only on string & date type managed properties.</span></span>
1. <span data-ttu-id="8e4ca-135">无法创建分层筛选器。</span><span class="sxs-lookup"><span data-stu-id="8e4ca-135">You cannot create hierarchical filters.</span></span>

## <a name="resources"></a><span data-ttu-id="8e4ca-136">资源</span><span class="sxs-lookup"><span data-stu-id="8e4ca-136">Resources</span></span>

[<span data-ttu-id="8e4ca-137">管理垂直领域和结果类型</span><span class="sxs-lookup"><span data-stu-id="8e4ca-137">Manage verticals and result types</span></span>](customize-search-page.md)
