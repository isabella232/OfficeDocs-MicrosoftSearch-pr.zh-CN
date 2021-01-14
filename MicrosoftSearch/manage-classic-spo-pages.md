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
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="1cfd9-103">经典页面和 Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="1cfd9-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="1cfd9-104">在新式网站之前创建的 SharePoint 网站使用经典搜索框和经典搜索结果体验。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="1cfd9-105">我们将推出一项功能，该功能将默认为经典页面，以开始使用使用 Microsoft 搜索的新式搜索体验，从而提供具有更高相关性的个性化结果。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="1cfd9-106">建议所有网站（包括经典网站）使用 Microsoft 搜索，但如果你的经典网站使用自定义母版页和/或你已自定义经典搜索结果体验，我们将自动检测这些自定义项，而不是切换到 Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="1cfd9-107">将自动切换到 Microsoft 搜索的经典网站</span><span class="sxs-lookup"><span data-stu-id="1cfd9-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="1cfd9-108">如果以下所有条件均成立，经典网站将开始使用 Microsoft 搜索：</span><span class="sxs-lookup"><span data-stu-id="1cfd9-108">Classic sites will start using Microsoft Search if all of the following are true:</span></span>

* <span data-ttu-id="1cfd9-109">该网站基于团队网站模板 (STS#0 和 STS#1) 。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="1cfd9-110">网站未打开发布功能。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="1cfd9-111">该网站不使用自定义母版页， (oslo.master 或 seattle.master) 。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="1cfd9-112">除了在默认结果源上为网站、网站集或租户添加提升的结果外，没有活动的查询规则。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="1cfd9-113">默认结果源上没有网站或网站集的自定义结果类型。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="1cfd9-114">使用下面所述的 *SearchBoxInNavBar* 设置，站点或网站集不会选择退出切换。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-114">The site or the site collection is not opted out of the switch using the *SearchBoxInNavBar* setting described below.</span></span>

<span data-ttu-id="1cfd9-115">切换到 Microsoft 搜索后，网站中的经典页面将开始在套件导航栏中显示搜索框，并从页面中删除经典搜索框。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="1cfd9-116">然后，当用户搜索词时，结果将显示为使用 Microsoft 搜索的新式搜索体验。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="1cfd9-117">保持经典搜索体验</span><span class="sxs-lookup"><span data-stu-id="1cfd9-117">Staying with the classic search experience</span></span>

<span data-ttu-id="1cfd9-118">如果您的网站满足上面列出的条件，但您不希望其切换到 Microsoft 搜索体验，可以选择退出以下命令，作为网站或网站集所有者。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="1cfd9-119">在切换发生之前或之后，你随时都可以使用此命令，以便轻松返回到之前过的搜索体验。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="1cfd9-120">若要运行以下命令，需要将 PowerShell 与 SharePoint PnP PowerShell 扩展一同使用。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="1cfd9-121">你可以安装并了解有关如何在此处开始 [了解更多信息](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-121">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="1cfd9-122">您将使用此命令登录到您的网站或网站集：</span><span class="sxs-lookup"><span data-stu-id="1cfd9-122">You will sign in to your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

<span data-ttu-id="1cfd9-123">若要保持网站的经典搜索体验，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1cfd9-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="1cfd9-124">或者，如果要为网站集中的所有网站设置它，可以使用此命令：</span><span class="sxs-lookup"><span data-stu-id="1cfd9-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="1cfd9-125">选择加入 Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="1cfd9-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="1cfd9-126">对于不符合上述条件的网站，或选择保持经典模式的网站集中的特定网站，可以手动启用 Microsoft 搜索体验。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="1cfd9-127">若要更改特定网站的此设置，可以使用此命令：</span><span class="sxs-lookup"><span data-stu-id="1cfd9-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="1cfd9-128">如果要为网站集中的所有网站设置它，可以使用此命令：</span><span class="sxs-lookup"><span data-stu-id="1cfd9-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="1cfd9-129">只能手动为包含"STS"、"CMSPUBLISHING"、"BLANKINTERNET"和"GROUP" (的团队网站或发布网站模板 id 启用 Microsoft 搜索) 。</span><span class="sxs-lookup"><span data-stu-id="1cfd9-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>
