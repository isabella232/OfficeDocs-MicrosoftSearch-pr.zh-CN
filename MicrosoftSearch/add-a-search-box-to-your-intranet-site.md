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
description: 通过将 Microsoft 搜索框添加到 Intranet 站点或页面来更快地获取相关搜索建议和查找工作结果。
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612415"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="76b3a-103">将搜索框添加到 Intranet 站点</span><span class="sxs-lookup"><span data-stu-id="76b3a-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="76b3a-104">将 Microsoft 搜索框添加到 Intranet 站点或页面，以快速访问相关搜索建议和工作结果。</span><span class="sxs-lookup"><span data-stu-id="76b3a-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="76b3a-105">将搜索框添加到 Intranet 页面</span><span class="sxs-lookup"><span data-stu-id="76b3a-105">Add a search box to your intranet site</span></span>

<span data-ttu-id="76b3a-106">需要将两个元素添加到页面：适合于搜索框的容器以及支持该搜索框的脚本。</span><span class="sxs-lookup"><span data-stu-id="76b3a-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="76b3a-107">在 SharePoint 经典网站上，添加脚本编辑器 Web 部件并将脚本拖动到其中。</span><span class="sxs-lookup"><span data-stu-id="76b3a-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="76b3a-108">启用面向移动设备的搜索框</span><span class="sxs-lookup"><span data-stu-id="76b3a-108">Enable the search box for mobile</span></span>

<span data-ttu-id="76b3a-109">在面向移动用户的 Intranet 网站或页面上，将 isMobile: true 添加到设置对象：</span><span class="sxs-lookup"><span data-stu-id="76b3a-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="76b3a-110">默认情况下，已将焦点置于搜索框上</span><span class="sxs-lookup"><span data-stu-id="76b3a-110">Put focus on the search box by default</span></span>

<span data-ttu-id="76b3a-111">为了帮助用户更快地进行搜索，在加载页面或网站时，通过将 focus: true 添加到设置对象来将光标置于搜索框中：</span><span class="sxs-lookup"><span data-stu-id="76b3a-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="76b3a-112">使用 iFrame 嵌入搜索框</span><span class="sxs-lookup"><span data-stu-id="76b3a-112">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="76b3a-113">如果嵌入脚本并非网站上的一个选项，请使用 iFrame 添加搜索框：</span><span class="sxs-lookup"><span data-stu-id="76b3a-113">If embedding a script isn't an option for the site, use an iFrame to add the search box:</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
