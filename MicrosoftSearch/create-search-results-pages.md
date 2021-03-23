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
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a><span data-ttu-id="a84af-103">在 SharePoint Online 中创建自定义搜索结果页面</span><span class="sxs-lookup"><span data-stu-id="a84af-103">Create a custom search results page in SharePoint Online</span></span>

<span data-ttu-id="a84af-104">在 SharePoint 中自定义搜索体验的一个方法就是为网站创建自定义搜索结果页面。</span><span class="sxs-lookup"><span data-stu-id="a84af-104">One way to customize the search experience in SharePoint is to create a custom search results page for a site.</span></span> <span data-ttu-id="a84af-105">这允许您使用您创建的页面，而不是 Microsoft 搜索结果页中的默认值。</span><span class="sxs-lookup"><span data-stu-id="a84af-105">This allows you to use a page that you created, rather than the default in Microsoft Search results page.</span></span> <span data-ttu-id="a84af-106">这样，您就搜索结果体验如何查找用户提供了更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="a84af-106">This gives you more flexibility on how the search results experience looks for your users.</span></span>

>[!NOTE]
> <span data-ttu-id="a84af-107">若要对默认可用的默认 Microsoft 搜索结果页面进行更改，请参阅自定义 [搜索结果页面](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="a84af-107">To make changes to the default Microsoft Search results page that is available by default, please see [Customize the search results page](customize-search-page.md).</span></span>

<span data-ttu-id="a84af-108">使用自定义结果页，您可以创建一个新页面，该页面可用于控制搜索结果的布局和设计，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="a84af-108">With a custom results page you can create a new page that can be used to control the layout and design of search results to support your organization's needs.</span></span> <span data-ttu-id="a84af-109">可以使用任何内置 Web 部件、SharePoint 模式和做法社区中的开放源代码搜索 Web 部件，以及你可能已使用 SharePoint 框架开发的任何自定义 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="a84af-109">You can use any built-in web parts, open-source search web parts from SharePoint Patterns and Practices community, as well as any custom web parts that you may have developed using SharePoint Framework.</span></span>

## <a name="configure-a-results-page"></a><span data-ttu-id="a84af-110">配置结果页</span><span class="sxs-lookup"><span data-stu-id="a84af-110">Configure a results page</span></span>

<span data-ttu-id="a84af-111">若要在 SharePoint Online 中配置自定义结果页面，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a84af-111">To configure a custom results page in SharePoint Online follow the steps below:</span></span>

1. <span data-ttu-id="a84af-112">浏览到要配置自定义结果页的网站，然后转到"网站设置">"网站集设置 **>"搜索设置"。**</span><span class="sxs-lookup"><span data-stu-id="a84af-112">Browse to the site where you would like to configure a custom results page and go to **Site Settings > Site Collection Settings > Search Settings**.</span></span>

2. <span data-ttu-id="a84af-113">在"搜索设置"中，从"使用与我的父级相同的结果页面设置"中清除选择，选择"将查询发送到 **自定义** 结果页面"，并为"结果"页面 URL 提供值 **：。**</span><span class="sxs-lookup"><span data-stu-id="a84af-113">In Search Settings, clear selection from **Use the same results page settings as my parent**, choose **Send queries to a custom results page**, and provide a value for **Results page URL:**.</span></span> <span data-ttu-id="a84af-114">然后，保存更改。</span><span class="sxs-lookup"><span data-stu-id="a84af-114">Then, save your changes.</span></span> <span data-ttu-id="a84af-115">您在此处使用的 URL 应该适用于您创建用作自定义结果页的页面。</span><span class="sxs-lookup"><span data-stu-id="a84af-115">The URL you use here should be for the page that you created to use as your custom results page.</span></span>

>[!NOTE]
> <span data-ttu-id="a84af-116">自定义结果页需要与您的网站位于同一个域中，但它不一定位于同一网站集中。</span><span class="sxs-lookup"><span data-stu-id="a84af-116">The custom results page needs to be on the same domain as your site, but it does not have to be in the same site collection.</span></span>  

<span data-ttu-id="a84af-117">或者，您可以使用 [Set-PnPSearchSettings SharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) 命令设置值，而不是使用"网站设置"页。</span><span class="sxs-lookup"><span data-stu-id="a84af-117">Alternatively, you can use the [Set-PnPSearchSettings SharePoint PnP PowerShell command](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) to set the value instead of using the Site Settings page.</span></span>

<span data-ttu-id="a84af-118">设置后，当您使用 Microsoft 搜索框进行搜索时，将显示自定义搜索结果页面，该框显示在页面顶部的导航栏中，当您从网站页面或网站的主页输入搜索时，会使用该框。</span><span class="sxs-lookup"><span data-stu-id="a84af-118">Once set, the custom search results page is displayed when you search using the Microsoft Search box that appears in the navigation bar on top of the page and is used when you enter search from site pages or the home page of the site.</span></span> <span data-ttu-id="a84af-119">当您在列表、库或网站内容页中搜索时，不会使用。</span><span class="sxs-lookup"><span data-stu-id="a84af-119">It is not used when you are searching within a list, library, or the site contents page.</span></span> <span data-ttu-id="a84af-120">您可以使用链接从列表和库中的搜索结果展开搜索，以访问自定义结果页面。</span><span class="sxs-lookup"><span data-stu-id="a84af-120">You may use the link to expand your search from search results in lists and libraries to get to the custom results page.</span></span>

## <a name="change-the-layout-of-your-custom-results-page"></a><span data-ttu-id="a84af-121">更改自定义结果页面的布局</span><span class="sxs-lookup"><span data-stu-id="a84af-121">Change the layout of your custom results page</span></span>

<span data-ttu-id="a84af-122">可以使用名为 **HeaderlessSearchResults** 的页面布局使搜索结果页面看起来更接近我们开箱即用搜索结果体验。</span><span class="sxs-lookup"><span data-stu-id="a84af-122">A page layout named **HeaderlessSearchResults** can be used to make the search results page appear closer to our out of box search results experience.</span></span> <span data-ttu-id="a84af-123">对于设置为自定义搜索结果页面的页面，此新布局只能处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a84af-123">This new layout can only be active for the pages that are set to be the custom search results page.</span></span>

<span data-ttu-id="a84af-124">若要设置页面布局，可以将 [Set-PnPClientSidePageSharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) 命令与 -LayoutType HeaderlessSearchResults 一同使用。</span><span class="sxs-lookup"><span data-stu-id="a84af-124">To set the page layout, you can use the [Set-PnPClientSidePageSharePoint PnP PowerShell command](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) with -LayoutType HeaderlessSearchResults.</span></span>

## <a name="use-sharepoint-framework-query-extensions"></a><span data-ttu-id="a84af-125">使用 SharePoint 框架查询扩展</span><span class="sxs-lookup"><span data-stu-id="a84af-125">Use SharePoint Framework Query extensions</span></span>

<span data-ttu-id="a84af-126">自定义搜索结果页还可以利用 [SharePoint 框架](/sharepoint/dev/spfx/building-search-extensions) 查询扩展在查询发送到搜索引擎之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="a84af-126">Custom search results pages can also make use of the [SharePoint Framework Query Extension](/sharepoint/dev/spfx/building-search-extensions) to modify the query before it gets sent to the search engine.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a84af-127">其他资源</span><span class="sxs-lookup"><span data-stu-id="a84af-127">Additional resources</span></span>

<span data-ttu-id="a84af-128">若要了解有关自定义结果页面的信息，请查看 [Ignite 2019 搜索自定义和开发会话](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="a84af-128">To learn more about custom results page, check out our [Ignite 2019 Search Customization and Development session](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).</span></span>

<span data-ttu-id="a84af-129">有关开放源代码项目、Microsoft 搜索 API 入门以及更多自定义和扩展性示例，请访问 [GitHub 上的 Microsoft 搜索](https://github.com/microsoft-search)。</span><span class="sxs-lookup"><span data-stu-id="a84af-129">For open source projects, getting started with our Microsoft Search APIs, and more customization and extensibility samples, visit [Microsoft Search on GitHub](https://github.com/microsoft-search).</span></span>