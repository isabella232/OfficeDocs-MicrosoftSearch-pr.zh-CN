---
title: 在 SharePoint Online 中创建自定义搜索结果页面
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: 为 SharePoint Online 网站创建您自己的搜索结果页面
ms.openlocfilehash: b5abb25f15795389dd8b6d5683ac336af7422e0a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031635"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>在 SharePoint Online 中创建自定义搜索结果页面

在 SharePoint 中自定义搜索体验的一个方法就是为网站创建自定义搜索结果页面。 这允许您使用您创建的页面，而不是 Microsoft 搜索结果页中的默认值。 这样，您就搜索结果体验如何查找用户提供了更大的灵活性。

>[!NOTE]
> 若要对默认可用的默认 Microsoft 搜索结果页面进行更改，请参阅自定义 [搜索结果页面](customize-search-page.md)。

使用自定义结果页，您可以创建一个新页面，该页面可用于控制搜索结果的布局和设计，以满足组织的需求。 可以使用任何内置 Web 部件、SharePoint 模式和做法社区中的开放源代码搜索 Web 部件，以及你可能已使用 SharePoint 框架开发的任何自定义 Web 部件。

## <a name="configure-a-results-page"></a>配置结果页

若要在 SharePoint Online 中配置自定义结果页面，请按照以下步骤操作：

1. 浏览到要配置自定义结果页的网站，然后转到"网站设置">"网站集设置 **>"搜索设置"。**

2. 在"搜索设置"中，从"使用与我的父级相同的结果页面设置"中清除选择，选择"将查询发送到 **自定义** 结果页面"，并为"结果"页面 URL 提供值 **：。** 然后，保存更改。 您在此处使用的 URL 应该适用于您创建用作自定义结果页的页面。

>[!NOTE]
> 自定义结果页需要与您的网站位于同一个域中，但它不一定位于同一网站集中。  

或者，您可以使用 [Set-PnPSearchSettings SharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) 命令设置值，而不是使用"网站设置"页。

设置后，当您使用 Microsoft 搜索框进行搜索时，将显示自定义搜索结果页面，该框显示在页面顶部的导航栏中，当您从网站页面或网站的主页输入搜索时，会使用该框。 当您在列表、库或网站内容页中搜索时，不会使用。 您可以使用链接从列表和库中的搜索结果展开搜索，以访问自定义结果页面。

## <a name="change-the-layout-of-your-custom-results-page"></a>更改自定义结果页面的布局

可以使用名为 **HeaderlessSearchResults** 的页面布局使搜索结果页面看起来更接近我们开箱即用搜索结果体验。 对于设置为自定义搜索结果页面的页面，此新布局只能处于活动状态。

若要设置页面布局，可以将 [Set-PnPClientSidePageSharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) 命令与 -LayoutType HeaderlessSearchResults 一同使用。

## <a name="use-sharepoint-framework-query-extensions"></a>使用 SharePoint 框架查询扩展

自定义搜索结果页还可以利用 [SharePoint 框架](/sharepoint/dev/spfx/building-search-extensions) 查询扩展在查询发送到搜索引擎之前对其进行修改。

## <a name="additional-resources"></a>其他资源

若要了解有关自定义结果页面的信息，请查看 [Ignite 2019 搜索自定义和开发会话](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)。

有关开放源代码项目、Microsoft 搜索 API 入门以及更多自定义和扩展性示例，请访问 [GitHub 上的 Microsoft 搜索](https://github.com/microsoft-search)。