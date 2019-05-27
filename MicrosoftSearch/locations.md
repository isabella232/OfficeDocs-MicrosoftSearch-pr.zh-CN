---
title: 位置
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 2379e72c-a7da-4e3f-932a-12d431a0a284
description: 可以在 Microsoft 搜索工作结果中保护你组织位置的所有方法概述
ms.openlocfilehash: bcda64315f85b9770f47d1b6c08fd90296063487
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968457"
---
# <a name="locations"></a><span data-ttu-id="816cd-103">位置</span><span class="sxs-lookup"><span data-stu-id="816cd-103">Locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="816cd-104">Microsoft 365 管理中心现提供有 Microsoft 必应搜索设置。</span><span class="sxs-lookup"><span data-stu-id="816cd-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="816cd-105">从在管理中心[分配搜索管理员](https://docs.microsoft.com/zh-CN/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)开始入手。</span><span class="sxs-lookup"><span data-stu-id="816cd-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
## <a name="add-locations"></a><span data-ttu-id="816cd-106">添加位置</span><span class="sxs-lookup"><span data-stu-id="816cd-106">Add federated locations</span></span>

<span data-ttu-id="816cd-107">位置可以帮助用户在地图上查找地址并定位组织的大楼、办公室和其他工作区。</span><span class="sxs-lookup"><span data-stu-id="816cd-107">Find addresses and locate your organization's buildings, offices, and other workspaces on a map</span></span> <span data-ttu-id="816cd-108">他们可以使用必应地图来辨别方向以及查看附近的情况等等。</span><span class="sxs-lookup"><span data-stu-id="816cd-108">They can also use Bing Maps to get directions, see what's nearby, and more.</span></span>
  
- [<span data-ttu-id="816cd-109">添加位置</span><span class="sxs-lookup"><span data-stu-id="816cd-109">Add a location</span></span>](add-a-location.md)
    
    <span data-ttu-id="816cd-110">添加大楼、办公室、校园或其他工作区</span><span class="sxs-lookup"><span data-stu-id="816cd-110">Add a building, office, campus, or other workspace</span></span>
    
- [<span data-ttu-id="816cd-111">批量创建位置</span><span class="sxs-lookup"><span data-stu-id="816cd-111">Bulk create locations</span></span>](bulk-create-locations.md)
    
    <span data-ttu-id="816cd-112">将位置添加到 .csv 文件并将它们批量导入</span><span class="sxs-lookup"><span data-stu-id="816cd-112">Add locations to a .csv file and bulk import them</span></span>
    
## <a name="manage-locations"></a><span data-ttu-id="816cd-113">管理位置</span><span class="sxs-lookup"><span data-stu-id="816cd-113">Manage locations</span></span>

<span data-ttu-id="816cd-114">使用位置状态、筛选工具和批量导出/导入工具来[查找并更新位置](manage-locations.md)，包括地址和位置名称</span><span class="sxs-lookup"><span data-stu-id="816cd-114">Use the location status, filtering tools, and bulk export/import tools to [find and update locations](manage-locations.md), including address and location name</span></span>
  
## <a name="location-status"></a><span data-ttu-id="816cd-115">位置状态</span><span class="sxs-lookup"><span data-stu-id="816cd-115">Location status</span></span>

<span data-ttu-id="816cd-116">在管理门户中，可按当前状态查看位置：</span><span class="sxs-lookup"><span data-stu-id="816cd-116">In the Admin portal, you can view locations by their current status:</span></span>
  
- <span data-ttu-id="816cd-117">已发布</span><span class="sxs-lookup"><span data-stu-id="816cd-117">Published</span></span>
    
    <span data-ttu-id="816cd-118">在得到授权的用户搜索某个关键字时，已发布的位置会出现在必应搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="816cd-118">Published locations appear in Bing search results when an authorized user searches for a keyword.</span></span>
    
- <span data-ttu-id="816cd-119">草稿</span><span class="sxs-lookup"><span data-stu-id="816cd-119">Draft</span></span>
    
    <span data-ttu-id="816cd-120">若还没有准备好发布某个位置，请将其保存为草稿。</span><span class="sxs-lookup"><span data-stu-id="816cd-120">If a location isn't ready to publish, save it as a draft.</span></span> <span data-ttu-id="816cd-121">草稿位置不会显示在必应上。</span><span class="sxs-lookup"><span data-stu-id="816cd-121">Draft locations will not appear on Bing.</span></span>
    
- <span data-ttu-id="816cd-122">已计划</span><span class="sxs-lookup"><span data-stu-id="816cd-122">Scheduled</span></span>
    
    <span data-ttu-id="816cd-123">已计划了发布时间的位置会在未来某个日期自动发布。</span><span class="sxs-lookup"><span data-stu-id="816cd-123">Scheduled locations are automatically published on a future date.</span></span>
    
- <span data-ttu-id="816cd-124">已过期</span><span class="sxs-lookup"><span data-stu-id="816cd-124">Expired</span></span>
    
    <span data-ttu-id="816cd-125">已过期的位置会根据自己的到期日期自动从已发布的内容中删除。</span><span class="sxs-lookup"><span data-stu-id="816cd-125">Expired locations were automatically removed from published content based on their expiration dates.</span></span>
    
- <span data-ttu-id="816cd-126">推荐</span><span class="sxs-lookup"><span data-stu-id="816cd-126">Suggested Meetings</span></span>
    
    <span data-ttu-id="816cd-127">推荐的位置基于用户反馈。</span><span class="sxs-lookup"><span data-stu-id="816cd-127">Suggested locations are based on feedback from users.</span></span> <span data-ttu-id="816cd-128">可能还会看到来自 Microsoft 的默认推荐内容。</span><span class="sxs-lookup"><span data-stu-id="816cd-128">You may also see default suggestions from Microsoft.</span></span>

  

