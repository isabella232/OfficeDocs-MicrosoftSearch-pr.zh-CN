---
title: 将搜索框添加到 Intranet 站点
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: 通过将一个搜索框添加到 Intranet 站点或页面，Microsoft 搜索相关搜索建议并更快地查找工作结果。
ms.openlocfilehash: d9f730eee98291d64e1f860c67be3eb7aa52a4a8
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973766"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>将搜索框添加到 Intranet 站点

若要为用户提供轻松访问您组织的结果，Microsoft 搜索搜索框中必应 Intranet 站点或页面。 以下为一些优势：

- Web 门户或 intranet SharePoint上的搜索框提供了一个熟悉、受信任的入口点以开始搜索
- 支持所有主要 Web 浏览器，包括 Google Chrome 和 Microsoft Edge
- 仅显示来自组织的搜索建议，从不包括 Web 建议
- 将用户Microsoft 搜索工作必应，其中不包括广告和 Web 结果
- 控制搜索框的外观和行为，包括使用户登录默认垂直或已创建的自定义垂直方向的能力
  
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
        dropShadow: true,                       // default: false
        iconColor: "#067FA6",                   // default: #067FA6
        title: "Search box",                    // default: "Search box"
        vertical: "Person-people",              // default: not specified, search box directs to the All vertical on the WORK results page
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="direct-users-to-a-default-or-custom-vertical"></a>将用户引导到默认或自定义垂直方向

为了在业务线应用或 Intranet 站点和工作结果之间轻松集成，您还可以通过指定用户单击搜索建议时应登录的默认或自定义垂直搜索框来自定义搜索框。

使用 bfbSearchBoxConfig 中的垂直选项定义您想要的垂直方向。 例如，如果您希望用户始终登录"网站"垂直（默认垂直距离之一）上，请使用值"Site-sites"。

:::image type="content" alt-text="Screenshot of work results page on Microsoft 搜索 in 必应 showing the Sites vertical results and URL." source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

对于自定义垂直方向，使用 URL 末尾的哈希。 您可以通过从 必应 上的工作页进行搜索、单击垂直标签，以及复制数字符号 (#) 。

:::image type="content" alt-text="显示自定义演示文稿垂直结果和 URL Microsoft 搜索必应显示工作结果页面的屏幕截图。" source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a>使用 iFrame 嵌入搜索框

如果嵌入脚本并非网站上的一个选项，请使用 iFrame 添加搜索框。 无法自定义搜索框。
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a>InPrivate 模式和条件访问

如果在 InPrivate 窗口中打开页面或网站，将禁用嵌入搜索框。 此外，由于 Azure AD 条件访问支持Microsoft Edge，必应.com 在使用 InPrivate 模式时不支持 AAD 登录。 有关 Edge 中的条件访问详细信息，请参阅Microsoft Edge[和条件访问](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge)。 
