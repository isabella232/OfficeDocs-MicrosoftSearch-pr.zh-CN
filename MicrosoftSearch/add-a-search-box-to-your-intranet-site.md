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
description: 获取相关搜索建议，并通过将一个 Microsoft 搜索搜索框添加到 intranet 网站或网页查找工作结果更快。
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612415"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="5a9fc-103">将搜索框添加到 Intranet 站点</span><span class="sxs-lookup"><span data-stu-id="5a9fc-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="5a9fc-104">用于快速访问相关搜索建议和工作结果，添加到任何 intranet 网站或页面的 Microsoft 搜索搜索框。</span><span class="sxs-lookup"><span data-stu-id="5a9fc-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="5a9fc-105">将搜索框添加到 intranet 页</span><span class="sxs-lookup"><span data-stu-id="5a9fc-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="5a9fc-106">您需要将两个元素添加到页: 搜索框和电源它的脚本的容器。</span><span class="sxs-lookup"><span data-stu-id="5a9fc-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="5a9fc-107">在 SharePoint 经典网站上，添加脚本编辑器 Web 部件和空投脚本。</span><span class="sxs-lookup"><span data-stu-id="5a9fc-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="5a9fc-108">启用 mobile 的搜索框</span><span class="sxs-lookup"><span data-stu-id="5a9fc-108">Enable the search box for mobile</span></span>

<span data-ttu-id="5a9fc-109">对于 intranet 网站或页，可用于移动用户中，添加 isMobile： 为 true 则设置对象：</span><span class="sxs-lookup"><span data-stu-id="5a9fc-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="5a9fc-110">将焦点放在搜索框中，默认情况下</span><span class="sxs-lookup"><span data-stu-id="5a9fc-110">Put focus on the search box by default</span></span>

<span data-ttu-id="5a9fc-111">可帮助用户更快、 搜索时页面或站点加载将光标放置在搜索框添加焦点： 为 true 则设置对象：</span><span class="sxs-lookup"><span data-stu-id="5a9fc-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="5a9fc-112">使用 iFrame 嵌入的搜索框</span><span class="sxs-lookup"><span data-stu-id="5a9fc-112">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="5a9fc-113">如果嵌入脚本桌网站，使用 iFrame 添加搜索框：</span><span class="sxs-lookup"><span data-stu-id="5a9fc-113">If embedding a script isn't an option for the site, use an iFrame to add the search box:</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
