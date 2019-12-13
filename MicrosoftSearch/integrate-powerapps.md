---
title: 集成高级应用程序
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
description: 在 Microsoft Search 的书签结果中添加基于浏览器的应用程序
ms.openlocfilehash: 7d3dd21758c63da14bbd3896ece1ce67a19c80a2
ms.sourcegitcommit: f4cb37fdf85b895337caee827fb72b5b7fcaa8ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2019
ms.locfileid: "39995020"
---
# <a name="integrate-power-apps-in-microsoft-search-bookmarks"></a><span data-ttu-id="7c83b-103">在 Microsoft Search 书签中集成 Power Apps</span><span class="sxs-lookup"><span data-stu-id="7c83b-103">Integrate Power Apps in Microsoft Search bookmarks</span></span>
   
<span data-ttu-id="7c83b-104">通过将现有[Microsoft 电源应用](https://products.office.com/business/microsoft-powerapps)集成到 Microsoft 搜索书签，帮助用户完成任务，如输入休假时间或报告费用。</span><span class="sxs-lookup"><span data-stu-id="7c83b-104">Help your users complete tasks, like entering vacation time or reporting expenses, by integrating existing [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) into your Microsoft Search bookmarks.</span></span> <span data-ttu-id="7c83b-105">集成的 Power Apps 显示在书签结果中，无需转到其他网站或打开单独的工具来节省时间和精力。</span><span class="sxs-lookup"><span data-stu-id="7c83b-105">Integrated Power Apps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-power-apps"></a><span data-ttu-id="7c83b-106">什么是电源应用？</span><span class="sxs-lookup"><span data-stu-id="7c83b-106">What are Power Apps?</span></span>

<span data-ttu-id="7c83b-107">[Power Apps](https://products.office.com/business/microsoft-powerapps)是一项服务，允许您构建在浏览器中或在手机或平板电脑上运行的业务应用程序，无需任何编码体验。</span><span class="sxs-lookup"><span data-stu-id="7c83b-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="7c83b-108">了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="7c83b-108">Learn more:</span></span>
  
- [<span data-ttu-id="7c83b-109">引导学习</span><span class="sxs-lookup"><span data-stu-id="7c83b-109">Guided Learning</span></span>](https://docs.microsoft.com/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="7c83b-110">文档</span><span class="sxs-lookup"><span data-stu-id="7c83b-110">Documentation</span></span>](https://docs.microsoft.com/powerapps/)
    
## <a name="add-a-power-app-to-a-bookmark"></a><span data-ttu-id="7c83b-111">向书签添加电源应用程序</span><span class="sxs-lookup"><span data-stu-id="7c83b-111">Add a Power App to a bookmark</span></span>

<span data-ttu-id="7c83b-112">[Power Apps （https://products.office.com/business/microsoft-powerapps)在任何浏览器和任何设备上工作，要添加的时间不到一分钟。</span><span class="sxs-lookup"><span data-stu-id="7c83b-112">[Power Apps(https://products.office.com/business/microsoft-powerapps) work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="7c83b-113">查找要集成的[电源应用程序的应用程序 ID](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) 。</span><span class="sxs-lookup"><span data-stu-id="7c83b-113">[Find the App ID for the Power App](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="7c83b-114">在 Microsoft 365[管理中心](https://admin.microsoft.com)，转到 "**书签**"。</span><span class="sxs-lookup"><span data-stu-id="7c83b-114">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Bookmarks**.</span></span>
    
3. <span data-ttu-id="7c83b-115">添加书签或查找要向其添加电源应用程序的现有书签。</span><span class="sxs-lookup"><span data-stu-id="7c83b-115">Add a bookmark or find an existing bookmark that you want to add a Power App to.</span></span>
    
4. <span data-ttu-id="7c83b-116">在 "书签设置" 中，选择 " **Power app**"，然后选择 "**添加电源应用**"。</span><span class="sxs-lookup"><span data-stu-id="7c83b-116">In the bookmark settings, select **Power App**, and then select **Add a Power App**.</span></span>
    
5. <span data-ttu-id="7c83b-117">输入或粘贴“应用 ID”。</span><span class="sxs-lookup"><span data-stu-id="7c83b-117">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="7c83b-118">自动添加高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="7c83b-118">The height and width are automatically added.</span></span> <span data-ttu-id="7c83b-119">书签支持纵向和横向设置，但是目前无法改变大小。</span><span class="sxs-lookup"><span data-stu-id="7c83b-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="7c83b-120">书签预览显示了 Power 应用程序将在书签结果中显示的方式。</span><span class="sxs-lookup"><span data-stu-id="7c83b-120">The bookmark preview shows how the Power App will appear in the bookmark result.</span></span>
    
    <span data-ttu-id="7c83b-121">预览中的高级应用程序功能齐全，可以轻松进行测试和使用。</span><span class="sxs-lookup"><span data-stu-id="7c83b-121">The Power App in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="7c83b-122">选择“**发布**”。</span><span class="sxs-lookup"><span data-stu-id="7c83b-122">Select **Publish**.</span></span>
    
<span data-ttu-id="7c83b-123">当授权的 Microsoft 搜索用户在[Bing](https://Bing.com)上搜索任何书签的关键字或保留关键字时，该 Power App 将显示在书签结果中。</span><span class="sxs-lookup"><span data-stu-id="7c83b-123">When an authorized Microsoft Search user searches on [Bing](https://Bing.com) for any of the bookmark's keywords or reserved keywords, the Power App will appear in the bookmark result.</span></span>
