---
title: 在 SharePoint Online 中创建自定义搜索结果页面
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: 为 SharePoint Online 网站创建您自己的搜索结果页
ms.openlocfilehash: 9b168dccaa6126148c877b5841b91c63f7bdc2ac
ms.sourcegitcommit: 5fb46a04e86fb49477f8ce7ab3caa1b503215b8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503234"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>在 SharePoint Online 中创建自定义搜索结果页面

在 SharePoint 中自定义搜索体验的一种方法是为网站创建自定义搜索结果页。 这使您可以使用您创建的页面，而不是 Microsoft 搜索结果页面中的默认页面。 这使你可以更灵活地了解搜索结果体验对你的用户的外观。

>[!NOTE]
> 若要更改默认情况下可用的默认 Microsoft 搜索结果页面，请参阅[自定义搜索结果页面](customize-search-page.md)。

使用自定义结果页面，可以创建一个新页面，该页面可用于控制搜索结果的布局和设计，以支持组织的需求。 您可以使用任何内置 web 部件、来自 SharePoint 模式和实践社区的开放源代码搜索 web 部件，以及您可能已使用 SharePoint 框架开发的任何自定义 web 部件。

## <a name="configure-a-results-page"></a>配置结果页

若要在 SharePoint Online 中配置自定义结果页面，请执行以下步骤：

1. 浏览到要在其中配置自定义结果页面的网站，并转到 "**网站设置" > "网站集设置" > "搜索设置**"。

2. 在 "搜索设置" 中，清除 **"使用与我的父项相同的结果页面设置" 中的**"选择将**查询发送到自定义结果" 页**，并为 "结果" **页 URL**提供值：。然后，保存所做的更改。 您在此处使用的 URL 应为您创建的用于自定义结果页面的页面。

>[!NOTE]
> 自定义结果页面必须与网站位于同一域中，但不一定要位于同一网站集中。  

或者，也可以使用[PnPSearchSettings SharePoint PnP PowerShell 命令](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps)设置值，而不是使用 "网站设置" 页。

设置后，在使用页面顶部的导航栏中显示的 Microsoft 搜索框进行搜索时，将显示自定义搜索结果页面，当您在网站页面或网站的主页上输入搜索时，将使用该页面。 当您在列表、库或 "网站内容" 页中进行搜索时，不使用此方法。 您可以使用链接在列表和库中的搜索结果中扩展搜索，以获取自定义结果页面。

## <a name="change-the-layout-of-your-custom-results-page"></a>更改自定义结果页的布局

名为**HeaderlessSearchResults**的页面布局可用于使搜索结果页面看上去更接近我们的 "现成" 搜索结果体验。对于设置为自定义搜索结果页面的页面，此新布局只能是活动的。

若要设置页面布局，可以将[PnPClientSidePageSharePoint PnP PowerShell 命令](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps)与-LayoutType HeaderlessSearchResults 结合使用。

## <a name="use-sharepoint-framework-query-extensions"></a>使用 SharePoint 框架查询扩展

自定义搜索结果页面还可以使用[SharePoint 框架查询扩展](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions)在将查询发送到搜索引擎之前对其进行修改。

## <a name="additional-resources"></a>其他资源

若要了解有关自定义结果页面的详细信息，请查看我们的 [Ignite 2019 搜索自定义和开发会话](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)。

对于开放源代码项目、Microsoft Search Api 入门和更多自定义和扩展性示例，请访问[GitHub 上的 Microsoft search](https://github.com/microsoft-search)。
