---
title: SharePoint Online 和 Microsoft 搜索中的经典页面
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 在经典 SharePoint 页面上使用 Microsoft 搜索
ms.openlocfilehash: 9a5aeb2e683297faccfb55d3407653c1791b3961
ms.sourcegitcommit: 7133d46ca9c3a5216ee9159db781febd17e5a831
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "49863171"
---
# <a name="classic-pages-and-microsoft-search"></a>经典页面和 Microsoft 搜索

在新式网站之前创建的 SharePoint 网站使用经典搜索框和经典搜索结果体验。 我们将推出一项功能，该功能将默认为经典页面，以开始使用使用 Microsoft 搜索的新式搜索体验，从而提供具有更高相关性的个性化结果。

建议所有网站（包括经典网站）使用 Microsoft 搜索，但如果你的经典网站使用自定义母版页和/或你已自定义经典搜索结果体验，我们将自动检测这些自定义项，而不是切换到 Microsoft 搜索。

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>将自动切换到 Microsoft 搜索的经典网站

如果以下所有条件均成立，经典网站将开始使用 Microsoft 搜索：

* 该网站基于团队网站模板 (STS#0 和 STS#1) 。
* 网站未打开发布功能。
* 该网站不使用自定义母版页， (oslo.master 或 seattle.master) 。
* 除了在默认结果源上为网站、网站集或租户添加提升的结果外，没有活动的查询规则。
* 默认结果源上没有网站或网站集的自定义结果类型。
* 使用下面所述的 *SearchBoxInNavBar* 设置，站点或网站集不会选择退出切换。

切换到 Microsoft 搜索后，网站中的经典页面将开始在套件导航栏中显示搜索框，并从页面中删除经典搜索框。 然后，当用户搜索词时，结果将显示为使用 Microsoft 搜索的新式搜索体验。

## <a name="staying-with-the-classic-search-experience"></a>保持经典搜索体验

如果您的网站满足上面列出的条件，但您不希望其切换到 Microsoft 搜索体验，可以选择退出以下命令，作为网站或网站集所有者。

在切换发生之前或之后，你随时都可以使用此命令，以便轻松返回到之前过的搜索体验。

若要运行以下命令，需要将 PowerShell 与 SharePoint PnP PowerShell 扩展一同使用。 你可以安装并了解有关如何在此处开始 [了解更多信息](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。 您将使用此命令登录到您的网站或网站集：

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

## <a name="opting-into-microsoft-search"></a>选择加入 Microsoft 搜索

对于不符合上述条件的网站，或选择保持经典模式的网站集中的特定网站，可以手动启用 Microsoft 搜索体验。

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
> 只能手动为包含"STS"、"CMSPUBLISHING"、"BLANKINTERNET"和"GROUP" (的团队网站或发布网站模板 id 启用 Microsoft 搜索) 。
