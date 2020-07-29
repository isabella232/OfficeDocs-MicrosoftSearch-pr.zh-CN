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
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a><span data-ttu-id="99138-103">在 SharePoint Online 中创建自定义搜索结果页面</span><span class="sxs-lookup"><span data-stu-id="99138-103">Create a custom search results page in SharePoint Online</span></span>

<span data-ttu-id="99138-104">在 SharePoint 中自定义搜索体验的一种方法是为网站创建自定义搜索结果页。</span><span class="sxs-lookup"><span data-stu-id="99138-104">One way to customize the search experience in SharePoint is to create a custom search results page for a site.</span></span> <span data-ttu-id="99138-105">这使您可以使用您创建的页面，而不是 Microsoft 搜索结果页面中的默认页面。</span><span class="sxs-lookup"><span data-stu-id="99138-105">This allows you to use a page that you created, rather than the default in Microsoft Search results page.</span></span> <span data-ttu-id="99138-106">这使你可以更灵活地了解搜索结果体验对你的用户的外观。</span><span class="sxs-lookup"><span data-stu-id="99138-106">This gives you more flexibility on how the search results experience looks for your users.</span></span>

>[!NOTE]
> <span data-ttu-id="99138-107">若要更改默认情况下可用的默认 Microsoft 搜索结果页面，请参阅[自定义搜索结果页面](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="99138-107">To make changes to the default Microsoft Search results page that is available by default, please see [Customize the search results page](customize-search-page.md).</span></span>

<span data-ttu-id="99138-108">使用自定义结果页面，可以创建一个新页面，该页面可用于控制搜索结果的布局和设计，以支持组织的需求。</span><span class="sxs-lookup"><span data-stu-id="99138-108">With a custom results page you can create a new page that can be used to control the layout and design of search results to support your organization's needs.</span></span> <span data-ttu-id="99138-109">您可以使用任何内置 web 部件、来自 SharePoint 模式和实践社区的开放源代码搜索 web 部件，以及您可能已使用 SharePoint 框架开发的任何自定义 web 部件。</span><span class="sxs-lookup"><span data-stu-id="99138-109">You can use any built-in web parts, open-source search web parts from SharePoint Patterns and Practices community, as well as any custom web parts that you may have developed using SharePoint Framework.</span></span>

## <a name="configure-a-results-page"></a><span data-ttu-id="99138-110">配置结果页</span><span class="sxs-lookup"><span data-stu-id="99138-110">Configure a results page</span></span>

<span data-ttu-id="99138-111">若要在 SharePoint Online 中配置自定义结果页面，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="99138-111">To configure a custom results page in SharePoint Online follow the steps below:</span></span>

1. <span data-ttu-id="99138-112">浏览到要在其中配置自定义结果页面的网站，并转到 "**网站设置" > "网站集设置" > "搜索设置**"。</span><span class="sxs-lookup"><span data-stu-id="99138-112">Browse to the site where you would like to configure a custom results page and go to **Site Settings > Site Collection Settings > Search Settings**.</span></span>

2. <span data-ttu-id="99138-113">在 "搜索设置" 中，清除 **"使用与我的父项相同的结果页面设置" 中的**"选择将**查询发送到自定义结果" 页**，并为 "结果" **页 URL**提供值：。</span><span class="sxs-lookup"><span data-stu-id="99138-113">In Search Settings, clear selection from **Use the same results page settings as my parent**, choose **Send queries to a custom results page**, and provide a value for **Results page URL:**.</span></span><span data-ttu-id="99138-114">然后，保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="99138-114"> Then, save your changes.</span></span> <span data-ttu-id="99138-115">您在此处使用的 URL 应为您创建的用于自定义结果页面的页面。</span><span class="sxs-lookup"><span data-stu-id="99138-115">The URL you use here should be for the page that you created to use as your custom results page.</span></span>

>[!NOTE]
> <span data-ttu-id="99138-116">自定义结果页面必须与网站位于同一域中，但不一定要位于同一网站集中。</span><span class="sxs-lookup"><span data-stu-id="99138-116">The custom results page needs to be on the same domain as your site, but it does not have to be in the same site collection.</span></span>  

<span data-ttu-id="99138-117">或者，也可以使用[PnPSearchSettings SharePoint PnP PowerShell 命令](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps)设置值，而不是使用 "网站设置" 页。</span><span class="sxs-lookup"><span data-stu-id="99138-117">Alternatively, you can use the [Set-PnPSearchSettings SharePoint PnP PowerShell command](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) to set the value instead of using the Site Settings page.</span></span>

<span data-ttu-id="99138-118">设置后，在使用页面顶部的导航栏中显示的 Microsoft 搜索框进行搜索时，将显示自定义搜索结果页面，当您在网站页面或网站的主页上输入搜索时，将使用该页面。</span><span class="sxs-lookup"><span data-stu-id="99138-118">Once set, the custom search results page is displayed when you search using the Microsoft Search box that appears in the navigation bar on top of the page and is used when you enter search from site pages or the home page of the site.</span></span> <span data-ttu-id="99138-119">当您在列表、库或 "网站内容" 页中进行搜索时，不使用此方法。</span><span class="sxs-lookup"><span data-stu-id="99138-119">It is not used when you are searching within a list, library, or the site contents page.</span></span> <span data-ttu-id="99138-120">您可以使用链接在列表和库中的搜索结果中扩展搜索，以获取自定义结果页面。</span><span class="sxs-lookup"><span data-stu-id="99138-120">You may use the link to expand your search from search results in lists and libraries to get to the custom results page.</span></span>

## <a name="change-the-layout-of-your-custom-results-page"></a><span data-ttu-id="99138-121">更改自定义结果页的布局</span><span class="sxs-lookup"><span data-stu-id="99138-121">Change the layout of your custom results page</span></span>

<span data-ttu-id="99138-122">名为**HeaderlessSearchResults**的页面布局可用于使搜索结果页面看上去更接近我们的 "现成" 搜索结果体验。</span><span class="sxs-lookup"><span data-stu-id="99138-122">A page layout named **HeaderlessSearchResults** can be used to make the search results page appear closer to our out of box search results experience.</span></span><span data-ttu-id="99138-123">对于设置为自定义搜索结果页面的页面，此新布局只能是活动的。</span><span class="sxs-lookup"><span data-stu-id="99138-123"> This new layout can only be active for the pages that are set to be the custom search results page.</span></span>

<span data-ttu-id="99138-124">若要设置页面布局，可以将[PnPClientSidePageSharePoint PnP PowerShell 命令](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps)与-LayoutType HeaderlessSearchResults 结合使用。</span><span class="sxs-lookup"><span data-stu-id="99138-124">To set the page layout, you can use the [Set-PnPClientSidePageSharePoint PnP PowerShell command](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) with -LayoutType HeaderlessSearchResults.</span></span>

## <a name="use-sharepoint-framework-query-extensions"></a><span data-ttu-id="99138-125">使用 SharePoint 框架查询扩展</span><span class="sxs-lookup"><span data-stu-id="99138-125">Use SharePoint Framework Query extensions</span></span>

<span data-ttu-id="99138-126">自定义搜索结果页面还可以使用[SharePoint 框架查询扩展](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions)在将查询发送到搜索引擎之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="99138-126">Custom search results pages can also make use of the [SharePoint Framework Query Extension](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions) to modify the query before it gets sent to the search engine.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99138-127">其他资源</span><span class="sxs-lookup"><span data-stu-id="99138-127">Additional resources</span></span>

<span data-ttu-id="99138-128">若要了解有关自定义结果页面的详细信息，请查看我们的 [Ignite 2019 搜索自定义和开发会话](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="99138-128">To learn more about custom results page, check out our [Ignite 2019 Search Customization and Development session](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).</span></span>

<span data-ttu-id="99138-129">对于开放源代码项目、Microsoft Search Api 入门和更多自定义和扩展性示例，请访问[GitHub 上的 Microsoft search](https://github.com/microsoft-search)。</span><span class="sxs-lookup"><span data-stu-id="99138-129">For open source projects, getting started with our Microsoft Search APIs, and more customization and extensibility samples, visit [Microsoft Search on GitHub](https://github.com/microsoft-search).</span></span>
