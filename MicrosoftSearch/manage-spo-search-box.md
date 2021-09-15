---
title: 管理网站中的SharePoint框
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 如何自定义网站搜索框SharePoint体验
ms.openlocfilehash: b5d58dd5a241ccf2ada556c44ec0ea5479ea2e2b
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334462"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>搜索网站上搜索SharePoint设置

在 SharePoint 网站上自定义 Microsoft 搜索 的几种方法之一是定制套件导航栏中的搜索框在 SharePoint 网站中的工作方式，以最好地满足您的需求。

有关其他自定义选项，请参阅[Changing the Microsoft 搜索 results page to add custom verticals， result types and layouts](customize-search-page.md)和 Creating a custom search results [page](create-search-results-pages.md)。

> [!NOTE]
> 套件导航栏搜索框目前并非可供所有客户使用，但这些选项仍可立即设置，并且将在可用时生效。

对于下面列出的任务，你将使用 PowerShell 和 SharePoint PnP PowerShell 扩展。 可以在此处安装并了解有关如何开始使用 [的更多信息](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。 您将使用此命令登录到您的网站或网站集：

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>更改搜索范围

当今天在 SharePoint Online 中创建新网站并键入搜索框时，你将进入Microsoft 搜索页面。 此页面默认显示来自当前网站的结果，并允许您将搜索范围扩展到当前网站与 (（如果有一个) ）关联的中心，或扩展到整个组织。

默认情况下，搜索框使用的范围取决于网站类型。

* 常规网站搜索当前网站。
* 中心网站搜索中心内的所有网站。
* 主网站搜索所有内容。

在某些情况下，您可能需要更改这些默认值以始终在整个组织或网站关联的中心进行搜索，而无需额外单击。

作为网站所有者，您可以使用以下命令更改这些默认值：

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

运行此命令后，之前默认显示当前网站的结果的网站将开始显示来自整个组织的结果。

若要返回到默认设置，请再次运行命令，值为"DefaultScope"。 若要在 Hub 中搜索，请使用"Hub"作为 SearchScope 值。

此设置适用于单个网站级别。 网站集没有等效设置。

## <a name="show-or-hide-the-search-box"></a>显示或隐藏搜索框

如果你想要阻止用户搜索或使用自定义搜索框实现，你可以选择隐藏套件导航栏搜索框。

若要更改给定网站的此设置，请使用此命令：

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

或者，如果要为网站集中的所有网站设置它，可以使用此命令：

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

运行这些命令后，搜索框将不再显示在页面顶部的导航栏中。 若要返回到显示搜索框，请再次运行命令，将提供给"SearchBoxInNavBar"参数的值返回到"Inherit"。

有几个点需要考虑：

* 此设置仅适用于套件导航栏中的搜索框。 它不适用于页面中的搜索框，或经典页面上的搜索框。

* 在导航栏中禁用搜索框后，如果要在网站中实现搜索功能，您必须使用自定义 Web 部件或扩展名自己SharePoint 框架它。

* 此解决方案还将从网站的列表和库中删除搜索框。 除了网站范围的搜索之外，自定义搜索解决方案还需要考虑SharePoint列表和库的上下文搜索。

* 如果将设置应用到域的根网站，SharePoint起始页也将停止显示搜索框。

## <a name="changing-the-hint-displayed-in-the-search-box"></a>更改搜索框中显示的提示

您可以更改针对给定站点或网站集的搜索框显示的提示。 这是在搜索框中开始键入之前显示的文本。 如果你以其他方式配置了自定义结果页面或更改了搜索行为，这可以帮助指导用户了解搜索预期内容。

> [!NOTE]
> 为了能够进行此更改，需要允许以租户管理员角色在有关网站上运行自定义脚本，这默认情况下是不允许的。 有关详细信息 https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script ，请参阅 。 您可以允许运行自定义脚本，进行更改，然后在必要时还原为禁止网站的脚本。

若要更改给定网站的此设置，请运行以下命令：

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

或者，如果要为网站集中的所有网站设置它，可以使用此命令：

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

若要返回到默认占位符文本，将该值设置为空白 ("") 。