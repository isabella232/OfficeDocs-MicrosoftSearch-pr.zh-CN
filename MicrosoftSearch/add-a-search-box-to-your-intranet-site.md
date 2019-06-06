---
title: 将搜索框添加到 Intranet 站点
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: 通过将 Microsoft 搜索框添加到 Intranet 站点或页面来更快地获取相关搜索建议和查找工作结果。
ms.openlocfilehash: ea3efc224b69ffe894104068b055efe8b5882cc1
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727921"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="d2269-103">将搜索框添加到 Intranet 站点</span><span class="sxs-lookup"><span data-stu-id="d2269-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="d2269-104">将 Microsoft 搜索框添加到 Intranet 站点或页面，以快速访问相关搜索建议和工作结果。</span><span class="sxs-lookup"><span data-stu-id="d2269-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="d2269-105">将搜索框添加到 Intranet 页面</span><span class="sxs-lookup"><span data-stu-id="d2269-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="d2269-106">需要将两个元素添加到页面：适合于搜索框的容器以及支持该搜索框的脚本。</span><span class="sxs-lookup"><span data-stu-id="d2269-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="d2269-107">在 SharePoint 经典网站上，添加脚本编辑器 Web 部件并将脚本拖动到其中。</span><span class="sxs-lookup"><span data-stu-id="d2269-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="d2269-108">启用面向移动设备的搜索框</span><span class="sxs-lookup"><span data-stu-id="d2269-108">Enable the search box for mobile</span></span>

<span data-ttu-id="d2269-109">在面向移动用户的 Intranet 网站或页面上，将 isMobile: true 添加到设置对象：</span><span class="sxs-lookup"><span data-stu-id="d2269-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox", 
        isMobile: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="d2269-110">默认情况下，已将焦点置于搜索框上</span><span class="sxs-lookup"><span data-stu-id="d2269-110">Put focus on the search box by default</span></span>

<span data-ttu-id="d2269-111">为了帮助用户更快地进行搜索，在加载页面或网站时，通过将 focus: true 添加到设置对象来将光标置于搜索框中：</span><span class="sxs-lookup"><span data-stu-id="d2269-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        focus: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="d2269-112">自定义搜索框的外观</span><span class="sxs-lookup"><span data-stu-id="d2269-112">Customize the appearance of the search box</span></span> 

<span data-ttu-id="d2269-113">为了帮助搜索框更好地适应 Intranet 的样式，你可以使用各种配置选项。</span><span class="sxs-lookup"><span data-stu-id="d2269-113">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="d2269-114">混合和匹配各种选项以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="d2269-114">Mix and match options to suit your needs.</span></span>

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: true
        iconColor: "#067FA6",                   // default: #067FA6
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work and the web"
                                                // when specified, text will be "Search the web and [Contoso]"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="d2269-115">使用 iFrame 嵌入搜索框</span><span class="sxs-lookup"><span data-stu-id="d2269-115">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="d2269-116">如果嵌入脚本并非网站上的一个选项，请使用 iFrame 添加搜索框。</span><span class="sxs-lookup"><span data-stu-id="d2269-116">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="d2269-117">你将无法自定义搜索框的外观。</span><span class="sxs-lookup"><span data-stu-id="d2269-117">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```