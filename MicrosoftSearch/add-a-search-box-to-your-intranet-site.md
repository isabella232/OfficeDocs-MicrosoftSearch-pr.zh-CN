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
# <a name="add-a-search-box-to-your-intranet-site"></a>将搜索框添加到 Intranet 站点

用于快速访问相关搜索建议和工作结果，添加到任何 intranet 网站或页面的 Microsoft 搜索搜索框。
  
## <a name="add-a-search-box-to-an-intranet-page"></a>将搜索框添加到 intranet 页

您需要将两个元素添加到页: 搜索框和电源它的脚本的容器。
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

在 SharePoint 经典网站上，添加脚本编辑器 Web 部件和空投脚本。
  
## <a name="enable-the-search-box-for-mobile"></a>启用 mobile 的搜索框

对于 intranet 网站或页，可用于移动用户中，添加 isMobile： 为 true 则设置对象：
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>将焦点放在搜索框中，默认情况下

可帮助用户更快、 搜索时页面或站点加载将光标放置在搜索框添加焦点： 为 true 则设置对象：
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a>使用 iFrame 嵌入的搜索框

如果嵌入脚本桌网站，使用 iFrame 添加搜索框：
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
