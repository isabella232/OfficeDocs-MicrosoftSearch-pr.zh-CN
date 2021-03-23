---
title: 在 SharePoint 网站中管理搜索框
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
description: 如何自定义 SharePoint 网站的搜索框体验
ms.openlocfilehash: c58e7cf0a47d22fa9c6fd3abd93cc97087625690
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031356"
---
# <a name="search-box-settings-on-sharepoint-sites"></a><span data-ttu-id="8b17f-103">SharePoint 网站的搜索框设置</span><span class="sxs-lookup"><span data-stu-id="8b17f-103">Search box settings on SharePoint sites</span></span>

<span data-ttu-id="8b17f-104">在 SharePoint 网站上自定义 Microsoft 搜索的几种方法之一是定制套件导航栏中的搜索框在 SharePoint 网站中的工作方式，以最好地满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="8b17f-104">One of the several ways Microsoft Search can be customized on SharePoint sites is to tailor how the search box in the suite navigation bar works in SharePoint sites to best fit your needs.</span></span>

<span data-ttu-id="8b17f-105">有关其他自定义选项，请参阅 Changing [the Microsoft Search results page to add custom verticals， result types and layouts](customize-search-page.md)和 Creating a custom search results [page](create-search-results-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="8b17f-105">For other customization options, see [Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8b17f-106">套件导航栏搜索框目前并非可供所有客户使用，但这些选项仍可立即设置，并且将在可用时生效。</span><span class="sxs-lookup"><span data-stu-id="8b17f-106">The suite navigation bar search box is not available for all customers at this time, but these options can still be set now and they will take effect when it becomes available.</span></span>

<span data-ttu-id="8b17f-107">对于下面列出的任务，你将 PowerShell 与 SharePoint PnP PowerShell 扩展一同使用。</span><span class="sxs-lookup"><span data-stu-id="8b17f-107">For the tasks listed below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="8b17f-108">可以在此处安装并了解有关如何开始使用 [的更多信息](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="8b17f-108">You can install and learn more about how to get started [here](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="8b17f-109">您将使用此命令登录到您的网站或网站集：</span><span class="sxs-lookup"><span data-stu-id="8b17f-109">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a><span data-ttu-id="8b17f-110">更改搜索范围</span><span class="sxs-lookup"><span data-stu-id="8b17f-110">Changing the scope of search</span></span>

<span data-ttu-id="8b17f-111">今天在 SharePoint Online 中创建新网站并键入搜索框中时，你将进入 Microsoft 搜索结果页面。</span><span class="sxs-lookup"><span data-stu-id="8b17f-111">When you create a new site in SharePoint Online today, and type into the search box, you are taken to the Microsoft Search results page.</span></span> <span data-ttu-id="8b17f-112">此页面默认显示来自当前网站的结果，并允许您将搜索范围扩展到当前网站与 (（如果有一个) ）关联的中心，或扩展到整个组织。</span><span class="sxs-lookup"><span data-stu-id="8b17f-112">This page shows results from your current site by default and allows you to expand the scope of your search to the hub that the current site is associated with (if there is one), or to the whole organization.</span></span>

<span data-ttu-id="8b17f-113">默认情况下，搜索框使用的范围取决于网站类型。</span><span class="sxs-lookup"><span data-stu-id="8b17f-113">The scope the search box uses, by default, depends on type of site.</span></span>

* <span data-ttu-id="8b17f-114">常规网站搜索当前网站。</span><span class="sxs-lookup"><span data-stu-id="8b17f-114">Regular sites search over the current site.</span></span>
* <span data-ttu-id="8b17f-115">中心网站搜索中心内的所有网站。</span><span class="sxs-lookup"><span data-stu-id="8b17f-115">Hub sites search over all sites in the hub.</span></span>
* <span data-ttu-id="8b17f-116">主网站搜索所有内容。</span><span class="sxs-lookup"><span data-stu-id="8b17f-116">Home sites search over all content.</span></span>

<span data-ttu-id="8b17f-117">在某些情况下，您可能需要更改这些默认值以始终在整个组织或网站关联的中心进行搜索，而无需额外单击。</span><span class="sxs-lookup"><span data-stu-id="8b17f-117">In some cases, you may want to change these defaults to always search over the whole organization, or across the hub a site is associated with, without needing an additional click.</span></span>

<span data-ttu-id="8b17f-118">作为网站所有者，您可以使用以下命令更改这些默认值：</span><span class="sxs-lookup"><span data-stu-id="8b17f-118">As a site owner, you can change these defaults using the following command:</span></span>

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

<span data-ttu-id="8b17f-119">运行此命令后，之前默认显示当前网站的结果的网站将开始显示来自整个组织的结果。</span><span class="sxs-lookup"><span data-stu-id="8b17f-119">After running this command, the site that was previously showing results from the current site by default will start to show results from the whole organization.</span></span>

<span data-ttu-id="8b17f-120">若要返回到默认设置，请再次运行命令，值为"DefaultScope"。</span><span class="sxs-lookup"><span data-stu-id="8b17f-120">To go back to the default setting, run the command again with the value “DefaultScope".</span></span> <span data-ttu-id="8b17f-121">若要在 Hub 中搜索，请使用"Hub"作为 SearchScope 值。</span><span class="sxs-lookup"><span data-stu-id="8b17f-121">To search across the Hub, use “Hub” as the SearchScope value.</span></span>

<span data-ttu-id="8b17f-122">此设置适用于单个网站级别。</span><span class="sxs-lookup"><span data-stu-id="8b17f-122">This setting applies at the individual site level.</span></span> <span data-ttu-id="8b17f-123">网站集没有等效设置。</span><span class="sxs-lookup"><span data-stu-id="8b17f-123">There is no equivalent setting for site collections.</span></span>

## <a name="show-or-hide-the-search-box"></a><span data-ttu-id="8b17f-124">显示或隐藏搜索框</span><span class="sxs-lookup"><span data-stu-id="8b17f-124">Show or hide the search box</span></span>

<span data-ttu-id="8b17f-125">如果你想要阻止用户搜索或使用自定义搜索框实现，你可以选择隐藏套件导航栏搜索框。</span><span class="sxs-lookup"><span data-stu-id="8b17f-125">You can choose to hide the suite navigation bar search box if you want to prevent your users from searching or to use a custom search box implementation.</span></span>

<span data-ttu-id="8b17f-126">若要更改给定网站的此设置，请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="8b17f-126">To change this setting for a given site use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="8b17f-127">或者，如果要为网站集中的所有网站设置它，可以使用此命令：</span><span class="sxs-lookup"><span data-stu-id="8b17f-127">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="8b17f-128">运行这些命令后，搜索框将不再显示在页面顶部的导航栏中。</span><span class="sxs-lookup"><span data-stu-id="8b17f-128">After running these commands, the search box will no longer show up in the navigation bar on top of your page.</span></span> <span data-ttu-id="8b17f-129">若要返回显示搜索框，请再次运行命令，将提供给"SearchBoxInNavBar"参数的值返回到"Inherit"。</span><span class="sxs-lookup"><span data-stu-id="8b17f-129">To go back to showing the search box, run the commands again with the value provided to "SearchBoxInNavBar" parameter to “Inherit”.</span></span>

<span data-ttu-id="8b17f-130">有几个点需要考虑：</span><span class="sxs-lookup"><span data-stu-id="8b17f-130">There are several points to consider:</span></span>

* <span data-ttu-id="8b17f-131">此设置仅适用于套件导航栏中的搜索框。</span><span class="sxs-lookup"><span data-stu-id="8b17f-131">This setting only applies to the search box in the suite navigation bar.</span></span> <span data-ttu-id="8b17f-132">它不适用于页面中的搜索框或经典页面上的搜索框。</span><span class="sxs-lookup"><span data-stu-id="8b17f-132">It does not apply to search boxes that are in the page, or to search boxes on classic pages.</span></span>

* <span data-ttu-id="8b17f-133">在导航栏中禁用搜索框后，如果您希望网站具有搜索功能，您必须使用自定义 Web 部件或 SharePoint 框架扩展自己提供搜索框。</span><span class="sxs-lookup"><span data-stu-id="8b17f-133">Once you’ve disabled the search box in the navigation bar, if you want search functionality in your site, you will have to provide it yourself using a custom web part or a SharePoint Framework extension.</span></span>

* <span data-ttu-id="8b17f-134">此解决方案还将从网站的列表和库中删除搜索框。</span><span class="sxs-lookup"><span data-stu-id="8b17f-134">This solution will remove the search box from lists and libraries for your site as well.</span></span> <span data-ttu-id="8b17f-135">除了网站范围的搜索之外，自定义搜索解决方案还需要考虑 SharePoint 列表和库的上下文搜索。</span><span class="sxs-lookup"><span data-stu-id="8b17f-135">Your custom search solution will need to consider contextual searches for SharePoint lists and libraries, in addition to site-wide search.</span></span>

* <span data-ttu-id="8b17f-136">如果将设置应用到域的根网站，SharePoint 起始页也将停止显示搜索框。</span><span class="sxs-lookup"><span data-stu-id="8b17f-136">If you apply the setting to the root site of your domain, the SharePoint start page will also stop showing the search box.</span></span>

## <a name="changing-the-hint-displayed-in-the-search-box"></a><span data-ttu-id="8b17f-137">更改搜索框中显示的提示</span><span class="sxs-lookup"><span data-stu-id="8b17f-137">Changing the hint displayed in the search box</span></span>

<span data-ttu-id="8b17f-138">您可以更改针对给定站点或网站集的搜索框显示的提示。</span><span class="sxs-lookup"><span data-stu-id="8b17f-138">You can change the hint the search box shows for a given site or site collection.</span></span> <span data-ttu-id="8b17f-139">这是在搜索框中开始键入之前显示的文本。</span><span class="sxs-lookup"><span data-stu-id="8b17f-139">This is the text that appears in the search box before they start typing into it.</span></span> <span data-ttu-id="8b17f-140">如果你以其他方式配置了自定义结果页面或更改了搜索行为，这可以帮助指导用户了解搜索预期内容。</span><span class="sxs-lookup"><span data-stu-id="8b17f-140">This may help guide your users about what to expect from search if you’ve configured a custom results page or changed behavior of search in other ways.</span></span>

> [!NOTE]
> <span data-ttu-id="8b17f-141">为了能够进行此更改，需要允许以租户管理员角色在有关网站上运行自定义脚本，这默认情况下是不允许的。</span><span class="sxs-lookup"><span data-stu-id="8b17f-141">To be able to make this change, you need to allow running custom scripts on the site in question as a tenant administrator, which is disallowed by default.</span></span> <span data-ttu-id="8b17f-142">有关详细信息 https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script ，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="8b17f-142">Please see https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script for details.</span></span> <span data-ttu-id="8b17f-143">您可以允许运行自定义脚本，进行更改，然后在必要时还原为禁止网站的脚本。</span><span class="sxs-lookup"><span data-stu-id="8b17f-143">You can allow running custom scripts, make the change, and then revert to disallowing scripts for the site if necessary.</span></span>

<span data-ttu-id="8b17f-144">若要更改给定网站的此设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8b17f-144">To change this setting for a given site run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="8b17f-145">或者，如果要为网站集中的所有网站设置它，可以使用此命令：</span><span class="sxs-lookup"><span data-stu-id="8b17f-145">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="8b17f-146">若要返回到默认占位符文本，将该值设置为空白 ("") 。</span><span class="sxs-lookup"><span data-stu-id="8b17f-146">To go back to the default placeholder text, set the value to be blank ("").</span></span>