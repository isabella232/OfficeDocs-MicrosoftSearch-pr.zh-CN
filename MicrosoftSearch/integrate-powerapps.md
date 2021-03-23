---
title: 集成 Power Apps
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: 在 Microsoft 搜索的书签结果中包括基于浏览器的应用
ms.openlocfilehash: 52fa78c54ab6db74ef1e3679d3d32151a3f5ac10
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031698"
---
# <a name="integrate-power-apps-in-microsoft-search-bookmarks"></a><span data-ttu-id="2d572-103">在 Microsoft 搜索书签中集成 Power Apps</span><span class="sxs-lookup"><span data-stu-id="2d572-103">Integrate Power Apps in Microsoft Search bookmarks</span></span>
   
<span data-ttu-id="2d572-104">通过将现有 [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) 集成到 Microsoft 搜索书签，帮助用户完成任务，如输入休假时间或报告费用。</span><span class="sxs-lookup"><span data-stu-id="2d572-104">Help your users complete tasks, like entering vacation time or reporting expenses, by integrating existing [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) into your Microsoft Search bookmarks.</span></span> <span data-ttu-id="2d572-105">集成 Power Apps 显示在书签结果中，无需转到其他站点或打开单独的工具，从而节省时间和精力。</span><span class="sxs-lookup"><span data-stu-id="2d572-105">Integrated Power Apps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-power-apps"></a><span data-ttu-id="2d572-106">什么是 Power Apps？</span><span class="sxs-lookup"><span data-stu-id="2d572-106">What are Power Apps?</span></span>

<span data-ttu-id="2d572-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) 是一项服务，允许你构建在浏览器或手机或平板电脑上运行的业务应用，无需编码经验。</span><span class="sxs-lookup"><span data-stu-id="2d572-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="2d572-108">了解更多：</span><span class="sxs-lookup"><span data-stu-id="2d572-108">Learn more:</span></span>
  
- [<span data-ttu-id="2d572-109">引导学习</span><span class="sxs-lookup"><span data-stu-id="2d572-109">Guided Learning</span></span>](/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="2d572-110">文档</span><span class="sxs-lookup"><span data-stu-id="2d572-110">Documentation</span></span>](/powerapps/)
    
## <a name="add-a-power-app-to-a-bookmark"></a><span data-ttu-id="2d572-111">将 Power App 添加到书签</span><span class="sxs-lookup"><span data-stu-id="2d572-111">Add a Power App to a bookmark</span></span>

<span data-ttu-id="2d572-112">[Power Apps (在 https://products.office.com/business/microsoft-powerapps) 任意浏览器和任何设备上工作，添加时间不到一分钟。</span><span class="sxs-lookup"><span data-stu-id="2d572-112">[Power Apps(https://products.office.com/business/microsoft-powerapps) work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="2d572-113">[查找要集成 Power App](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) 的应用 ID。</span><span class="sxs-lookup"><span data-stu-id="2d572-113">[Find the App ID for the Power App](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="2d572-114">在 Microsoft 365 [管理中心中](https://admin.microsoft.com)，转到 **书签**。</span><span class="sxs-lookup"><span data-stu-id="2d572-114">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Bookmarks**.</span></span>
    
3. <span data-ttu-id="2d572-115">添加书签或查找要添加 Power App 的现有书签。</span><span class="sxs-lookup"><span data-stu-id="2d572-115">Add a bookmark or find an existing bookmark that you want to add a Power App to.</span></span>
    
4. <span data-ttu-id="2d572-116">在书签设置中，选择 **"Power App"，** 然后选择"**添加 Power App"。**</span><span class="sxs-lookup"><span data-stu-id="2d572-116">In the bookmark settings, select **Power App**, and then select **Add a Power App**.</span></span>
    
5. <span data-ttu-id="2d572-117">输入或粘贴“应用 ID”。</span><span class="sxs-lookup"><span data-stu-id="2d572-117">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="2d572-118">自动添加高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="2d572-118">The height and width are automatically added.</span></span> <span data-ttu-id="2d572-119">书签支持纵向和横向设置，但是目前无法改变大小。</span><span class="sxs-lookup"><span data-stu-id="2d572-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="2d572-120">书签预览显示 Power App 在书签结果中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="2d572-120">The bookmark preview shows how the Power App will appear in the bookmark result.</span></span>
    
    <span data-ttu-id="2d572-121">预览版中的 Power App 功能完全正常，便于测试和使用。</span><span class="sxs-lookup"><span data-stu-id="2d572-121">The Power App in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="2d572-122">选择“**发布**”。</span><span class="sxs-lookup"><span data-stu-id="2d572-122">Select **Publish**.</span></span>
    
<span data-ttu-id="2d572-123">当授权的 Microsoft 搜索用户在 [必应](https://Bing.com) 上搜索书签的任何关键字或保留的关键字时，Power App 将显示在书签结果中。</span><span class="sxs-lookup"><span data-stu-id="2d572-123">When an authorized Microsoft Search user searches on [Bing](https://Bing.com) for any of the bookmark's keywords or reserved keywords, the Power App will appear in the bookmark result.</span></span>