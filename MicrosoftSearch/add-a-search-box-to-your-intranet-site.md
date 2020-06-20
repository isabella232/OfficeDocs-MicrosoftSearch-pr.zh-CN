---
title: 将搜索框添加到 Intranet 站点
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: 通过将 Microsoft 搜索框添加到 Intranet 站点或页面来更快地获取相关搜索建议和查找工作结果。
ms.openlocfilehash: af12ce4d17c2695e196f8e4d79ccd515f002f238
ms.sourcegitcommit: 92206ea179ec00b22496f6fd2866b5406449cf40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44798222"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="889b1-103">将搜索框添加到 Intranet 站点</span><span class="sxs-lookup"><span data-stu-id="889b1-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="889b1-104">若要使用户能够轻松访问组织中的结果，请在 Bing 搜索框中向任意 intranet 网站或页面添加 Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="889b1-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="889b1-105">以下是一些优点：</span><span class="sxs-lookup"><span data-stu-id="889b1-105">These are some of the benefits:</span></span>

- <span data-ttu-id="889b1-106">SharePoint 或 intranet 门户中的搜索框提供了一个熟悉的受信任入口点，可开始搜索</span><span class="sxs-lookup"><span data-stu-id="889b1-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="889b1-107">支持所有主要的 web 浏览器，包括 Google Chrome 和 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="889b1-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="889b1-108">仅显示你的组织的搜索建议，永远不会包含 web 建议</span><span class="sxs-lookup"><span data-stu-id="889b1-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="889b1-109">将用户带到 Bing 工作结果页面中的 Microsoft 搜索，这将排除广告和 web 结果</span><span class="sxs-lookup"><span data-stu-id="889b1-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="889b1-110">控制搜索框的外观和行为</span><span class="sxs-lookup"><span data-stu-id="889b1-110">You control the appearance and behavior of the search box</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="889b1-111">将搜索框添加到 Intranet 页面</span><span class="sxs-lookup"><span data-stu-id="889b1-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="889b1-112">需要将两个元素添加到页面：适合于搜索框的容器以及支持该搜索框的脚本。</span><span class="sxs-lookup"><span data-stu-id="889b1-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="889b1-113">在 SharePoint 经典网站上，添加脚本编辑器 Web 部件并将脚本拖动到其中。</span><span class="sxs-lookup"><span data-stu-id="889b1-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="889b1-114">启用面向移动设备的搜索框</span><span class="sxs-lookup"><span data-stu-id="889b1-114">Enable the search box for mobile</span></span>

<span data-ttu-id="889b1-115">在面向移动用户的 Intranet 网站或页面上，将 isMobile: true 添加到设置对象：</span><span class="sxs-lookup"><span data-stu-id="889b1-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="889b1-116">默认情况下，已将焦点置于搜索框上</span><span class="sxs-lookup"><span data-stu-id="889b1-116">Put focus on the search box by default</span></span>

<span data-ttu-id="889b1-117">为了帮助用户更快地进行搜索，在加载页面或网站时，通过将 focus: true 添加到设置对象来将光标置于搜索框中：</span><span class="sxs-lookup"><span data-stu-id="889b1-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="889b1-118">自定义搜索框的外观</span><span class="sxs-lookup"><span data-stu-id="889b1-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="889b1-119">为了帮助搜索框更好地适应 Intranet 的样式，你可以使用各种配置选项。</span><span class="sxs-lookup"><span data-stu-id="889b1-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="889b1-120">混合和匹配各种选项以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="889b1-120">Mix and match options to suit your needs.</span></span>

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
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="889b1-121">使用 iFrame 嵌入搜索框</span><span class="sxs-lookup"><span data-stu-id="889b1-121">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="889b1-122">如果嵌入脚本并非网站上的一个选项，请使用 iFrame 添加搜索框。</span><span class="sxs-lookup"><span data-stu-id="889b1-122">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="889b1-123">你将无法自定义搜索框的外观。</span><span class="sxs-lookup"><span data-stu-id="889b1-123">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
