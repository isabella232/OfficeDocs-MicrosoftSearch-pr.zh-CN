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
# <a name="add-a-search-box-to-your-intranet-site"></a>将搜索框添加到 Intranet 站点

若要使用户能够轻松访问组织中的结果，请在 Bing 搜索框中向任意 intranet 网站或页面添加 Microsoft 搜索。 以下是一些优点：

- SharePoint 或 intranet 门户中的搜索框提供了一个熟悉的受信任入口点，可开始搜索
- 支持所有主要的 web 浏览器，包括 Google Chrome 和 Microsoft Edge
- 仅显示你的组织的搜索建议，永远不会包含 web 建议
- 将用户带到 Bing 工作结果页面中的 Microsoft 搜索，这将排除广告和 web 结果
- 控制搜索框的外观和行为
  
## <a name="add-a-search-box-to-an-intranet-page"></a>将搜索框添加到 Intranet 页面

需要将两个元素添加到页面：适合于搜索框的容器以及支持该搜索框的脚本。
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

在 SharePoint 经典网站上，添加脚本编辑器 Web 部件并将脚本拖动到其中。
  
## <a name="enable-the-search-box-for-mobile"></a>启用面向移动设备的搜索框

在面向移动用户的 Intranet 网站或页面上，将 isMobile: true 添加到设置对象：
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>默认情况下，已将焦点置于搜索框上

为了帮助用户更快地进行搜索，在加载页面或网站时，通过将 focus: true 添加到设置对象来将光标置于搜索框中：
  
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

## <a name="customize-the-appearance-of-the-search-box"></a>自定义搜索框的外观 

为了帮助搜索框更好地适应 Intranet 的样式，你可以使用各种配置选项。 混合和匹配各种选项以满足你的需求。

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

## <a name="use-an-iframe-to-embed-a-search-box"></a>使用 iFrame 嵌入搜索框

如果嵌入脚本并非网站上的一个选项，请使用 iFrame 添加搜索框。 你将无法自定义搜索框的外观。
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
