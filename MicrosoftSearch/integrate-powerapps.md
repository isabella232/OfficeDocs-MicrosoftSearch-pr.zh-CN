---
title: 集成 PowerApps
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
ROBOTS: NOINDEX
description: 将基于浏览器的应用包括在 Microsoft 搜索的书签结果中
ms.openlocfilehash: 655b8c8c6f4a9729461447112b21ca7c6c7864f9
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591608"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="1fe7c-103">集成 PowerApps</span><span class="sxs-lookup"><span data-stu-id="1fe7c-103">Integrate PowerApps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fe7c-104">本文适用于 Microsoft 必应搜索管理门户。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="1fe7c-105">我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将其删除。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="1fe7c-106">我们建议你使用 Microsoft 365 管理中心快速开始。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="1fe7c-107">[Microsoft 搜索概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="1fe7c-108">帮助用户完成任务，例如通过将现有的 PowerApps 集成进书签来输入休假时间或上报费用。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-108">Help your users complete tasks, such as entering vacation time or reporting expenses, by adding existing PowerApps to your bookmarks.</span></span> <span data-ttu-id="1fe7c-109">集成的 PowerApps 显示在书签结果中，不需要转至另一个站点或打开单独的工具，省时又省力。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-109">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="1fe7c-110">什么是 PowerApps？</span><span class="sxs-lookup"><span data-stu-id="1fe7c-110">What are PowerApps?</span></span>

<span data-ttu-id="1fe7c-111">PowerApps 是一种服务，通过该服务可生成在浏览器、手机或平板电脑上运行的商业应用，且无需编码经验。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-111">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="1fe7c-112">了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="1fe7c-112">Learn more:</span></span>
  
- <span data-ttu-id="1fe7c-113">
  [引导学习](https://docs.microsoft.com/zh-CN/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="1fe7c-113">[Guided Learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)</span></span>
    
- <span data-ttu-id="1fe7c-114">
  [文档](https://docs.microsoft.com/zh-CN/powerapps/)</span><span class="sxs-lookup"><span data-stu-id="1fe7c-114">[Documentation](https://docs.microsoft.com/en-us/powerapps/)</span></span>
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="1fe7c-115">将 PowerApp 添加到书签</span><span class="sxs-lookup"><span data-stu-id="1fe7c-115">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="1fe7c-116">PowerApps 可在任何浏览器和任何设备上运行，且添加该服务所需时间不到一分钟。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-116">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="1fe7c-117">
  [查找要集成的 PowerApp 的应用 ID](https://docs.microsoft.com/zh-CN/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)</span><span class="sxs-lookup"><span data-stu-id="1fe7c-117">Find the [App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) that you want to add.</span></span> 
    
2. <span data-ttu-id="1fe7c-118">在 Microsoft 搜索管理门户中，转至“**书签**”</span><span class="sxs-lookup"><span data-stu-id="1fe7c-118">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="1fe7c-119">添加或查找一个要向其添加 PowerApp 的书签</span><span class="sxs-lookup"><span data-stu-id="1fe7c-119">Add a bookmark or find an existing bookmark that you want to add a PowerApp to.</span></span>
    
4. <span data-ttu-id="1fe7c-120">在书签设置中单击“**Power 应用**”，然后单击“**添加 Power 应用**”</span><span class="sxs-lookup"><span data-stu-id="1fe7c-120">In Bookmark settings, select Power App, and then Add a Power App.</span></span>
    
5. <span data-ttu-id="1fe7c-121">输入或粘贴应用 ID。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-121">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="1fe7c-122">将自动添加高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-122">The height and width are automatically adjusted.</span></span> <span data-ttu-id="1fe7c-123">书签支持纵向和横向设置，但是目前无法改变大小。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-123">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="1fe7c-124">书签预览会展示 PowerApp 在书签结果中的显示方式</span><span class="sxs-lookup"><span data-stu-id="1fe7c-124">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="1fe7c-125">预览中的 PowerApp 功能完备，可轻松地测试和使用。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-125">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="1fe7c-126">单击“**发布**”</span><span class="sxs-lookup"><span data-stu-id="1fe7c-126">Click **Publish**.</span></span>
    
<span data-ttu-id="1fe7c-127">当有权限的 Microsoft 搜索用户在必应上搜索该书签的任何关键字或保留关键字时，该 PowerApp 都会出现在书签结果中。</span><span class="sxs-lookup"><span data-stu-id="1fe7c-127">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

