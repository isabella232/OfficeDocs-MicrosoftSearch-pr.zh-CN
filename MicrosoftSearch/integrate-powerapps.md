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
description: 在 Microsoft Search 的书签结果中添加基于浏览器的应用程序
ms.openlocfilehash: d8d9d099848e719c86e0f3cadee330263566d243
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508823"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="6559c-103">集成 PowerApps</span><span class="sxs-lookup"><span data-stu-id="6559c-103">Integrate PowerApps</span></span>

<span data-ttu-id="6559c-104">通过将现有 PowerApps 集成到您的书签中, 帮助您的用户完成任务, 例如输入休假时间或报告费用。</span><span class="sxs-lookup"><span data-stu-id="6559c-104">Help your users complete tasks, such as entering vacation time or reporting expenses by integrating existing PowerApps into your bookmarks.</span></span> <span data-ttu-id="6559c-105">集成 PowerApps 显示在书签结果中, 无需转到其他网站或打开单独的工具来节省时间和精力。</span><span class="sxs-lookup"><span data-stu-id="6559c-105">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="6559c-106">什么是 PowerApps？</span><span class="sxs-lookup"><span data-stu-id="6559c-106">What are PowerApps?</span></span>

<span data-ttu-id="6559c-107">PowerApps 是一项服务, 它允许您构建在浏览器中或在手机或平板电脑上运行的业务应用程序, 无需任何编码体验。</span><span class="sxs-lookup"><span data-stu-id="6559c-107">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="6559c-108">了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="6559c-108">Learn more:</span></span>
  
- [<span data-ttu-id="6559c-109">引导式学习</span><span class="sxs-lookup"><span data-stu-id="6559c-109">Guided Learning</span></span>](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="6559c-110">文档</span><span class="sxs-lookup"><span data-stu-id="6559c-110">Documentation</span></span>](https://docs.microsoft.com/en-us/powerapps/)
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="6559c-111">向书签添加 PowerApp</span><span class="sxs-lookup"><span data-stu-id="6559c-111">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="6559c-112">PowerApps 在任何浏览器和任何设备上工作, 要添加的时间不到一分钟。</span><span class="sxs-lookup"><span data-stu-id="6559c-112">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="6559c-113">[查找要集成的 PowerApp 的应用程序 ID](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)</span><span class="sxs-lookup"><span data-stu-id="6559c-113">[Find the App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate</span></span> 
    
2. <span data-ttu-id="6559c-114">在 Microsoft SearchAdmin 门户中, 转到 "**书签**"</span><span class="sxs-lookup"><span data-stu-id="6559c-114">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="6559c-115">添加书签或查找要向其添加 PowerApp 的现有书签</span><span class="sxs-lookup"><span data-stu-id="6559c-115">Add a bookmark or find an existing bookmark that you want to add a PowerApp to</span></span>
    
4. <span data-ttu-id="6559c-116">在 "书签设置" 中, 单击 " **Power app**", 然后单击 "**添加电源应用程序**"</span><span class="sxs-lookup"><span data-stu-id="6559c-116">In the bookmark settings, click **Power App**, and then click **Add a Power App**</span></span>
    
5. <span data-ttu-id="6559c-117">输入或粘贴应用 ID</span><span class="sxs-lookup"><span data-stu-id="6559c-117">Enter or paste the App ID</span></span>
    
    <span data-ttu-id="6559c-118">自动添加高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="6559c-118">The height and width are automatically added.</span></span> <span data-ttu-id="6559c-119">书签可以同时支持纵向和横向方向, 但当前大小不能更改。</span><span class="sxs-lookup"><span data-stu-id="6559c-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="6559c-120">书签预览显示 PowerApp 将在书签结果中的显示方式</span><span class="sxs-lookup"><span data-stu-id="6559c-120">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="6559c-121">预览中的 PowerApp 可充分发挥作用, 使其易于测试和使用。</span><span class="sxs-lookup"><span data-stu-id="6559c-121">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="6559c-122">单击 "**发布**"</span><span class="sxs-lookup"><span data-stu-id="6559c-122">Click **Publish**</span></span>
    
<span data-ttu-id="6559c-123">当授权的 Microsoft 搜索用户在 Bing 上搜索任何书签的关键字或保留关键字时, PowerApp 将显示在书签结果中。</span><span class="sxs-lookup"><span data-stu-id="6559c-123">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

