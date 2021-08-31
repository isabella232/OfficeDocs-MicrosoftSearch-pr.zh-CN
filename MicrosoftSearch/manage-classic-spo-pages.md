---
title: SharePoint Online 和 Microsoft 搜索
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
description: 在经典Microsoft 搜索页面上使用SharePoint
ms.openlocfilehash: 5b9c40da63ccf3b28cf2d61282763d3d4f62f867
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702036"
---
# <a name="classic-pages-and-microsoft-search"></a>经典页面和Microsoft 搜索

SharePoint网站之前创建的网站使用经典搜索框和经典搜索结果体验。 我们将推出一项功能，该功能将默认使用经典页面，以开始使用使用 Microsoft 搜索 的新式搜索体验，从而提供具有更高相关性的个性化结果。

建议Microsoft 搜索所有网站（包括经典网站）使用自定义母版页和/或自定义经典搜索结果体验，我们将自动检测这些自定义项，而不是切换到 Microsoft 搜索。

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>将自动切换到网站的经典Microsoft 搜索

如果以下所有条件Microsoft 搜索，经典网站将开始使用经典网站：

* 该网站基于团队网站模板， (STS#0 和 STS#1) 。
* 网站未打开发布功能。
* 该网站不使用与 oslo.master 或 seattle.master (母版页不同的自定义母版) 。
* 除了在默认结果源上为网站、网站集或租户添加升级结果的活动查询规则外，没有活动的查询规则。
* 默认结果源上没有网站或网站集的自定义结果类型。
* 使用下面所述的 *SearchBoxInNavBar* 设置不会选择退出站点或网站集。

切换到 Microsoft 搜索 后，网站中的经典页面将开始在套件导航栏中显示搜索框，并从页面中删除经典搜索框。 然后，当用户搜索词时，结果将显示为使用新式搜索体验的 Microsoft 搜索。

## <a name="staying-with-the-classic-search-experience"></a>保持经典搜索体验

如果您的网站满足上面列出的条件，但您不希望其切换到 Microsoft 搜索 体验，则作为站点或网站集所有者，您可以选择退出以下命令。

在切换发生之前或之后，你随时都可以使用此命令，因此可以很轻松地返回到之前过的搜索体验。

若要运行以下命令，请使用 PowerShell 和 SharePoint PnP PowerShell 扩展。 可以在此处安装并了解有关如何开始使用 [的更多信息](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。 您将使用此命令登录到您的网站或网站集：

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

若要保持网站的经典搜索体验，请运行以下命令：

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

或者，如果要为网站集中的所有网站设置它，可以使用此命令：

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>选择加入Microsoft 搜索

对于不符合上面列出的条件的网站，或者对于选择保持经典体验的网站集中的特定网站，可以手动启用Microsoft 搜索体验。

若要更改特定网站的此设置，可以使用此命令：

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

如果要为网站集中的所有网站设置它，可以使用此命令：

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> 只能 Microsoft 搜索为包含"STS"、"CMSPUBLISHING"、"BLANKINTERNET"和"GROUP" (的团队网站或发布网站模板 id 手动启用) 。