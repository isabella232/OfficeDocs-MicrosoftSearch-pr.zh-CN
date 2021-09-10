---
title: 在 SharePoint Online 中创建自定义搜索结果页面
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
description: 为 SharePoint Online 网站创建自己的搜索结果页面
ms.openlocfilehash: df99287dbdd9a82c1a8bc66b39e67a37fcb22da8
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973758"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>在 SharePoint Online 中创建自定义搜索结果页面

自定义搜索体验的一SharePoint一个方法就是为网站创建自定义搜索结果页面。 这允许您使用您创建的页面，而不是结果页中的Microsoft 搜索。 这样，您就搜索结果体验如何查找用户提供了更大的灵活性。

>[!NOTE]
> 若要对默认可用的Microsoft 搜索页面进行更改，请参阅自定义[搜索结果页面](customize-search-page.md)。

通过自定义结果页，您可以创建一个新页面，该页面可用于控制搜索结果的布局和设计，以满足组织的需求。 您可以使用任何内置 Web 部件、SharePoint 模式和做法社区中的开放源代码搜索 Web 部件，以及您可能已使用 SharePoint 框架 开发的任何自定义 Web 部件。

## <a name="configure-a-results-page"></a>配置结果页

若要在 SharePoint Online 中配置自定义结果页面，请按照以下步骤操作：

1. 浏览到要配置自定义结果页的网站，然后转到S site 设置 > **Site Collection 设置 > Search 设置**。

2. 在"设置"中，清除"使用与我的父级相同的结果页面设置"中的选择，选择"将查询发送到自定义结果页面"，并为"结果"页面 URL 提供值 **：。** 然后，保存更改。 您在此处使用的 URL 应该用于您创建用作自定义结果页的页面。

>[!NOTE]
> 自定义结果页需要与您的网站位于同一个域中，但它不一定位于同一网站集中。  

或者，您可以使用[Set-PnPSearchSettings SharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps)命令来设置值，而不是使用"网站设置页面。

设置后，当您使用 Microsoft 搜索 框进行搜索时，将显示自定义搜索结果页面，该框显示在页面顶部的导航栏中，当您从网站页面或网站的主页输入搜索时，将使用该框。 当您在列表、库或网站内容页中搜索时，不会使用。 您可以使用链接从列表和库中的搜索结果展开搜索，以访问自定义结果页面。

## <a name="change-the-layout-of-your-custom-results-page"></a>更改自定义结果页面的布局

可以使用名为 **HeaderlessSearchResults** 的页面布局使搜索结果页面看起来离我们开箱即用搜索结果体验更近。 对于设置为自定义搜索结果页面的页面，此新布局只能处于活动状态。

若要设置页面布局，可以将 [Set-PnPClientSidePageSharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) 命令与 -LayoutType HeaderlessSearchResults 一同使用。

## <a name="use-sharepoint-framework-query-extensions"></a>使用SharePoint 框架查询扩展

自定义搜索结果页还可以利用查询扩展SharePoint 框架查询，[](/sharepoint/dev/spfx/building-search-extensions)在查询发送到搜索引擎之前对其进行修改。

## <a name="additional-resources"></a>其他资源

若要了解有关自定义结果页面的信息，请查看 [Ignite 2019 搜索自定义和开发会话](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)。

有关开放源代码项目、Microsoft 搜索 API 入门以及更多自定义和扩展性示例，请访问 Microsoft 搜索[上的](https://github.com/microsoft-search)GitHub。