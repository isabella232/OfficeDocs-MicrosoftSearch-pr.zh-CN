---
title: 管理书签
ms.author: jeffkizn
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
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: 创建和更新书签以及批量编辑 Microsoft 搜索的书签结果的方法
ms.openlocfilehash: 6a678464ec23c2d4c90190b6a02c0a73839b50ee
ms.sourcegitcommit: 41d28060238091455c7b8b011c67ae60c8a41f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619571"
---
# <a name="manage-bookmarks"></a><span data-ttu-id="e7583-103">管理书签</span><span class="sxs-lookup"><span data-stu-id="e7583-103">Manage bookmarks</span></span>

<span data-ttu-id="e7583-104">书签可帮助用户通过搜索快速查找重要网站和工具。</span><span class="sxs-lookup"><span data-stu-id="e7583-104">Bookmarks help people quickly find important sites and tools with just a search.</span></span> <span data-ttu-id="e7583-105">每个书签包括一个标题、URL、一组用于触发书签的用户友好关键字和一个类别。</span><span class="sxs-lookup"><span data-stu-id="e7583-105">Each bookmark includes a title, URL, a set of user-friendly keywords to trigger the bookmark, and a category.</span></span>

## <a name="what-makes-a-great-bookmark"></a><span data-ttu-id="e7583-106">什么是出色的书签</span><span class="sxs-lookup"><span data-stu-id="e7583-106">What makes a great bookmark</span></span>

<span data-ttu-id="e7583-107">一个出色的书签包含四个关键元素：</span><span class="sxs-lookup"><span data-stu-id="e7583-107">A great bookmark has four key elements:</span></span>

1. <span data-ttu-id="e7583-108">一个强的信息 **性标题**。</span><span class="sxs-lookup"><span data-stu-id="e7583-108">A strong, informative **title**.</span></span> <span data-ttu-id="e7583-109">目标不超过 8 个单词或最多 60 个字符。</span><span class="sxs-lookup"><span data-stu-id="e7583-109">Aim for no more than 8 words or about 60 characters maximum.</span></span> <span data-ttu-id="e7583-110">您希望用户单击标题并查看内容，但避免明显的单击：</span><span class="sxs-lookup"><span data-stu-id="e7583-110">You want your users to click on the title and view the content, but avoid obvious clickbait:</span></span>
    - <span data-ttu-id="e7583-111">好：尝试一下这一周从餐厅菜单中的一些不新鲜收藏夹。</span><span class="sxs-lookup"><span data-stu-id="e7583-111">Good: Try this week’s tasty favorites from the cafeteria menu.</span></span> <span data-ttu-id="e7583-112">标题清晰、简洁且有趣，但可能会过度提升。</span><span class="sxs-lookup"><span data-stu-id="e7583-112">Title is clear, concise, and interesting, but could be overpromising.</span></span>
    - <span data-ttu-id="e7583-113">更好：这星期的餐厅菜单。</span><span class="sxs-lookup"><span data-stu-id="e7583-113">Better: This week’s cafeteria menu.</span></span> <span data-ttu-id="e7583-114">不过度承诺或像广告一样。</span><span class="sxs-lookup"><span data-stu-id="e7583-114">Doesn't overpromise or sound like an ad.</span></span>
    - <span data-ttu-id="e7583-115">避免：你将不会相信这一周菜单上将发生什么问题。</span><span class="sxs-lookup"><span data-stu-id="e7583-115">Avoid: You won’t believe what’s coming to the cafeteria menu this week.</span></span> <span data-ttu-id="e7583-116">使用看起来像广告的 clickbait clichés。</span><span class="sxs-lookup"><span data-stu-id="e7583-116">Uses clickbait clichés that sound like an ad.</span></span>
2. <span data-ttu-id="e7583-117">概括 **链接资源的用途** 或功能的简洁描述（大约 300 个字符）。</span><span class="sxs-lookup"><span data-stu-id="e7583-117">A succinct **description**, about 300 characters, that summarizes the purpose or functionality of the linked resource.</span></span>
3. <span data-ttu-id="e7583-118">可帮助 **用户搜索** 书签的关键字集合。</span><span class="sxs-lookup"><span data-stu-id="e7583-118">A collection of **keywords** that will help people find the bookmark when they search.</span></span> <span data-ttu-id="e7583-119">建议至少使用五个关键字。</span><span class="sxs-lookup"><span data-stu-id="e7583-119">We suggest a minimum of at least five keywords.</span></span> <span data-ttu-id="e7583-120">此外，包括组织中人员可能使用的变体，例如，菜单、午餐菜单和餐厅菜单可能是菜单的变体。</span><span class="sxs-lookup"><span data-stu-id="e7583-120">Also, include variations that people in your organization might use, for example, dining menu, lunch menus, and café menu could all be variations for cafeteria menu.</span></span>
4. <span data-ttu-id="e7583-121">一组 **有用的类别** ，便于在管理中心内对书签进行排序和筛选。</span><span class="sxs-lookup"><span data-stu-id="e7583-121">A helpful set of **categories** that make it easier to sort and filter bookmarks in the admin center.</span></span> <span data-ttu-id="e7583-122">你的用户永远不会看到分配的类别。</span><span class="sxs-lookup"><span data-stu-id="e7583-122">Your users never see the assigned categories.</span></span>

## <a name="create-bookmark-answers"></a><span data-ttu-id="e7583-123">创建书签答案</span><span class="sxs-lookup"><span data-stu-id="e7583-123">Create bookmark answers</span></span>

<span data-ttu-id="e7583-124">在[Microsoft 365 管理中心](https://admin.microsoft.com/)，[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks)转到"书签"并选择想要如何创建新书签：</span><span class="sxs-lookup"><span data-stu-id="e7583-124">In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to [Bookmarks](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) and choose how you want to create new bookmarks:</span></span>

- <span data-ttu-id="e7583-125">添加书签</span><span class="sxs-lookup"><span data-stu-id="e7583-125">Add bookmarks</span></span>
- <span data-ttu-id="e7583-126">导入 SharePoint 结果</span><span class="sxs-lookup"><span data-stu-id="e7583-126">Import SharePoint results</span></span>
- <span data-ttu-id="e7583-127">添加默认书签和建议的书签</span><span class="sxs-lookup"><span data-stu-id="e7583-127">Add default bookmarks and suggested bookmarks</span></span>
- <span data-ttu-id="e7583-128">导入书签</span><span class="sxs-lookup"><span data-stu-id="e7583-128">Import bookmarks</span></span>
- <span data-ttu-id="e7583-129">发布或查看推荐的书签</span><span class="sxs-lookup"><span data-stu-id="e7583-129">Publish or review recommended bookmarks</span></span>

### <a name="add-bookmarks"></a><span data-ttu-id="e7583-130">添加书签</span><span class="sxs-lookup"><span data-stu-id="e7583-130">Add bookmarks</span></span>

<span data-ttu-id="e7583-131">搜索管理员和编辑人员可以在 Microsoft 365 管理中心中添加书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-131">Search admins and editors can add bookmarks in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e7583-132">书签可以发布或保存到草稿中。</span><span class="sxs-lookup"><span data-stu-id="e7583-132">Bookmarks can be published or saved to draft.</span></span> <span data-ttu-id="e7583-133">发布书签会立即刷新搜索索引，以便用户可以立即开始发现和使用它。</span><span class="sxs-lookup"><span data-stu-id="e7583-133">Publishing a bookmark immediately refreshes the search index so users can begin discovering and using it right away.</span></span> <span data-ttu-id="e7583-134">您还可以通过指定发布书签的日期和时间来计划书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-134">You can also schedule a bookmark by specifying the date and time it will be published.</span></span>

- <span data-ttu-id="e7583-135">**已发布**：通过 Microsoft 搜索，组织用户可以使用书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-135">**Published**: Bookmarks are available to the organization’s users through Microsoft Search.</span></span>
- <span data-ttu-id="e7583-136">**草稿**：保存为草稿的书签对用户不可用。</span><span class="sxs-lookup"><span data-stu-id="e7583-136">**Draft**: Bookmarks saved as drafts are not available to your users.</span></span> <span data-ttu-id="e7583-137">如果您或其他利益干系人想要在发布书签之前查看或更新书签，请使用此状态。</span><span class="sxs-lookup"><span data-stu-id="e7583-137">Use this status if you or other stakeholders want to review or update bookmarks before publishing them.</span></span>
- <span data-ttu-id="e7583-138">**计划**：将在指定日期和时间发布的书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-138">**Scheduled**: Bookmarks that will be published on the specified date and time.</span></span>

<span data-ttu-id="e7583-139">可以使用 Microsoft 搜索内容创建者浏览器扩展轻松添加书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-139">You can use the Microsoft Search content creator browser extension to easily add bookmarks.</span></span> <span data-ttu-id="e7583-140">若要安装浏览器扩展，请转到要添加为书签的网站，然后单击"在扩展中添加"。</span><span class="sxs-lookup"><span data-stu-id="e7583-140">To install the browser extension, go to the site you want to add as a bookmark, and click Add in the extension.</span></span>
<span data-ttu-id="e7583-141">安装 Edge 和 Chrome 的扩展：</span><span class="sxs-lookup"><span data-stu-id="e7583-141">Install the extension for Edge and Chrome:</span></span>

- <span data-ttu-id="e7583-142">对于 Chromium Edge 或 Chrome：转到 [Chrome Web 应用商店](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) 并添加扩展。</span><span class="sxs-lookup"><span data-stu-id="e7583-142">For Chromium Edge or Chrome: go to the [Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) and add the extension.</span></span>
- <span data-ttu-id="e7583-143">对于旧版 Edge：转到 [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) 并添加扩展。</span><span class="sxs-lookup"><span data-stu-id="e7583-143">For legacy Edge: go to the [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) and add the extension.</span></span>

### <a name="import-sharepoint-results"></a><span data-ttu-id="e7583-144">导入 SharePoint 结果</span><span class="sxs-lookup"><span data-stu-id="e7583-144">Import SharePoint results</span></span>

<span data-ttu-id="e7583-145">如果组织在 SharePoint 中设置了升级结果，您可以将租户的升级结果中的标题、URL 和说明导入 Microsoft 搜索，并为用户提供导入的内容。</span><span class="sxs-lookup"><span data-stu-id="e7583-145">If your organization set up Promoted Results in SharePoint, you can import the titles, URLs, and descriptions from the Promoted Results for your tenant into Microsoft Search and make the imported content available to your users.</span></span> <span data-ttu-id="e7583-146">在大多数情况下，导入 SharePoint 结果只需几分钟。</span><span class="sxs-lookup"><span data-stu-id="e7583-146">In most cases, importing SharePoint results takes just a few minutes.</span></span> <span data-ttu-id="e7583-147">如果要导入大量结果，可能需要 48 小时。</span><span class="sxs-lookup"><span data-stu-id="e7583-147">If you're importing a large number of results, it may take up to 48 hours.</span></span> <span data-ttu-id="e7583-148">这是一种快速填充搜索结果并为用户提供更有效的方式。</span><span class="sxs-lookup"><span data-stu-id="e7583-148">This is an easy way to quickly populate search results and make it more effective for your users.</span></span> <span data-ttu-id="e7583-149">我们建议使用 SharePoint 中的升级结果作为参考，以了解如何命名和创建相关搜索结果。</span><span class="sxs-lookup"><span data-stu-id="e7583-149">We recommend using promoted results from SharePoint as a reference to understand how to name and create relevant search results.</span></span>

### <a name="add-default-and-suggested-bookmarks"></a><span data-ttu-id="e7583-150">添加默认书签和推荐书签</span><span class="sxs-lookup"><span data-stu-id="e7583-150">Add default and suggested bookmarks</span></span>

<span data-ttu-id="e7583-151">我们包含了一些默认的建议书签，你的用户可能会发现这些书签很有用，包括 HR 书签、权益、IT 支持、密码管理等。</span><span class="sxs-lookup"><span data-stu-id="e7583-151">We've included some default suggested bookmarks that your users may find helpful, including bookmarks for HR, benefits, IT support, password management and more.</span></span> <span data-ttu-id="e7583-152">查看、更新和发布这些建议的书签，以向用户提供高质量的结果。</span><span class="sxs-lookup"><span data-stu-id="e7583-152">Review, update, and publish these suggested bookmarks to provide high-quality results to your users right away.</span></span>

<span data-ttu-id="e7583-153">你的用户还可以建议使用 Microsoft 搜索中的反馈链接查看添加的书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-153">Your users can also suggest bookmarks that would like to see added using feedback links in Microsoft Search.</span></span> <span data-ttu-id="e7583-154">他们的建议将显示为建议的书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-154">Their recommendations will appear as suggested bookmarks.</span></span>

### <a name="import-bookmarks"></a><span data-ttu-id="e7583-155">导入书签</span><span class="sxs-lookup"><span data-stu-id="e7583-155">Import bookmarks</span></span>

<span data-ttu-id="e7583-156">使用"导入"功能，可以更快、更轻松地添加或编辑大量书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-156">Use the Import feature to make adding or editing a large number of bookmarks faster and easier.</span></span> <span data-ttu-id="e7583-157">使用它：</span><span class="sxs-lookup"><span data-stu-id="e7583-157">Use it to:</span></span>

- <span data-ttu-id="e7583-158">批量添加书签：在书签模板文件中添加详细信息，然后导入它。</span><span class="sxs-lookup"><span data-stu-id="e7583-158">Bulk add bookmarks: Add details in the bookmark template file, and then import it.</span></span>
- <span data-ttu-id="e7583-159">批量编辑书签：将书签导出到 .csv 文件，在导出文件中编辑书签详细信息，然后导入编辑的文件。</span><span class="sxs-lookup"><span data-stu-id="e7583-159">Bulk edit bookmarks: Export bookmarks to a .csv file, edit the bookmark details in the exported file, and then import the edited file.</span></span>

<span data-ttu-id="e7583-160">有关模板文件的一些要点：</span><span class="sxs-lookup"><span data-stu-id="e7583-160">A few important points about the template file:</span></span>

- <span data-ttu-id="e7583-161">从不编辑以下字段中的数据 *：ID、Last* *Modified* 和 *Last Modified By*</span><span class="sxs-lookup"><span data-stu-id="e7583-161">Never edit data in these fields: *ID*, *Last Modified*, and *Last Modified By*</span></span>
- <span data-ttu-id="e7583-162">如果包含现有 *书签的 ID，* 它将替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="e7583-162">If you include the *ID* of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="e7583-163">对于具有相同标题或 URL 的现有书签，该书签将更新为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="e7583-163">For existing bookmarks with the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="e7583-164">在模板文件中，并非所有字段都是必填的，并且必填字段因书签状态而异。</span><span class="sxs-lookup"><span data-stu-id="e7583-164">Not all fields in the template file are required and required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="e7583-165">根据" *状态* "字段，书签将另存为草稿、建议、计划、排除或自动发布。</span><span class="sxs-lookup"><span data-stu-id="e7583-165">Based on the *State* field, bookmarks will be saved as draft, suggested, scheduled, excluded, or they'll be published automatically.</span></span>
- <span data-ttu-id="e7583-166">对于管理多个组织的合作伙伴，你可以从一个组织导出书签，然后将它们导入另一个组织。</span><span class="sxs-lookup"><span data-stu-id="e7583-166">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="e7583-167">但在导入之前，必须删除 *ID* 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="e7583-167">But you must remove the data in the *ID* column before you import.</span></span>

### <a name="prevent-import-errors"></a><span data-ttu-id="e7583-168">防止导入错误</span><span class="sxs-lookup"><span data-stu-id="e7583-168">Prevent import errors</span></span>

<span data-ttu-id="e7583-169">如果任何所需数据缺失或无效，你将收到错误，并且系统会生成一个日志文件，其中包含有关要更正的行和列的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e7583-169">You'll get an error if any required data is missing or invalid, and a log file is generated with more information about the rows and columns to be corrected.</span></span> <span data-ttu-id="e7583-170">完成必要的编辑，并再次尝试导入该文件。</span><span class="sxs-lookup"><span data-stu-id="e7583-170">Make necessary edits and try importing the file again.</span></span> <span data-ttu-id="e7583-171">在解决所有错误之前，你无法导入或保存任何书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-171">You cannot import or save any bookmarks until all errors are resolved.</span></span>

<span data-ttu-id="e7583-172">为防止出错，请确保导入文件具有正确格式，并且：</span><span class="sxs-lookup"><span data-stu-id="e7583-172">To prevent errors, make sure your import file is properly formatted and:</span></span>

- <span data-ttu-id="e7583-173">包含导入模板中的标题行和所有列</span><span class="sxs-lookup"><span data-stu-id="e7583-173">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="e7583-174">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="e7583-174">The column order is the same as the import template</span></span>
- <span data-ttu-id="e7583-175">除三个可为空的列外，所有列都有值 *：ID、Last* *Modified* 和 *Last Modified By*</span><span class="sxs-lookup"><span data-stu-id="e7583-175">All columns have values, except the three that can be empty: *ID*, *Last Modified*, and *Last Modified By*</span></span>
- <span data-ttu-id="e7583-176">" *状态* "列不为空，它是必需信息</span><span class="sxs-lookup"><span data-stu-id="e7583-176">The *State* column is not empty, it's required information</span></span>
- <span data-ttu-id="e7583-177">导入已发布、建议、计划或草稿书签时，需要标题 *、URL\*\*和关键字* 列</span><span class="sxs-lookup"><span data-stu-id="e7583-177">When importing Published, Suggested, Scheduled, or Draft bookmarks, the *Title*, *URL*, and *Keywords* columns are required</span></span>
- <span data-ttu-id="e7583-178">导入排除的书签时，需要 *URL* 列</span><span class="sxs-lookup"><span data-stu-id="e7583-178">When importing Excluded bookmarks, the *URL* column is required</span></span>

<span data-ttu-id="e7583-179">若要防止书签到书签重复错误：</span><span class="sxs-lookup"><span data-stu-id="e7583-179">To prevent bookmark-to-bookmark duplication errors:</span></span>

- <span data-ttu-id="e7583-180">不要对不同的书签使用重复 URL。</span><span class="sxs-lookup"><span data-stu-id="e7583-180">Don't use duplicate URLS for different bookmarks.</span></span> <span data-ttu-id="e7583-181">如果将 URL 分配给另一个书签，并且您尝试从导入文件再次添加它，则您将看到一个错误。</span><span class="sxs-lookup"><span data-stu-id="e7583-181">If a URL is assigned to another bookmark and you try to add it again from an import file, you'll get an error.</span></span> <span data-ttu-id="e7583-182">这也适用于其他类型的答案的重复 URL。</span><span class="sxs-lookup"><span data-stu-id="e7583-182">This also applies to duplicate URLs for other types of answers.</span></span>
- <span data-ttu-id="e7583-183">更新现有书签时，请使用 *书签 ID* 列。</span><span class="sxs-lookup"><span data-stu-id="e7583-183">When updating existing bookmarks, use the *bookmark ID* column.</span></span> <span data-ttu-id="e7583-184">您可以更新现有书签的其他任何属性，如关键字或说明，但应确保书签 *ID* 位于导入文件的适当列中。</span><span class="sxs-lookup"><span data-stu-id="e7583-184">You can update any other property of an existing bookmark, such as keyword or description, but you should make sure the *bookmark ID* is in the appropriate column of the import file.</span></span> <span data-ttu-id="e7583-185">如果存在 *书签 ID，* 则它不会被视为新增功能，也不会被处理为错误。</span><span class="sxs-lookup"><span data-stu-id="e7583-185">If the *bookmark ID* is present, it won't be treated as new addition and won't be processed as an error.</span></span>

### <a name="publish-or-review-recommended-bookmarks"></a><span data-ttu-id="e7583-186">发布或查看推荐的书签</span><span class="sxs-lookup"><span data-stu-id="e7583-186">Publish or review recommended bookmarks</span></span>

<span data-ttu-id="e7583-187">为了减少添加书签所需的手动工作量，Microsoft 搜索可以评估您组织的 SharePoint 链接并推荐书签，您可以在发布之前查看它们或将其设置为自动发布。</span><span class="sxs-lookup"><span data-stu-id="e7583-187">To reduce the manual effort required to add bookmarks, Microsoft Search can evaluate SharePoint links in your organization and recommend bookmarks, and you can review them before publishing or set them to automatically publish.</span></span> <span data-ttu-id="e7583-188">建议书签不需要任何设置，默认情况下，它们已启用并设置为自动发布。</span><span class="sxs-lookup"><span data-stu-id="e7583-188">No setup is needed for recommended bookmarks, they're enabled and set to auto-publish by default.</span></span> <span data-ttu-id="e7583-189">若要随时更改这些设置，请选择"管理 **书签"** 以打开书签设置面板。</span><span class="sxs-lookup"><span data-stu-id="e7583-189">To change these settings at any time, select **Manage bookmarks** to open the Bookmark settings panel.</span></span>

![Microsoft 365 管理门户中推荐书签设置的屏幕截图](media/bookmarks-recommendedsettings.png)

<span data-ttu-id="e7583-191">如果启用建议的书签，则建议引擎将评估您组织的 SharePoint 网站，以确定高流量链接。</span><span class="sxs-lookup"><span data-stu-id="e7583-191">If recommended bookmarks are enabled, the recommendation engine will evaluate SharePoint sites in your organization to identify high-traffic links.</span></span> <span data-ttu-id="e7583-192">初始评估期后，建议书签将自动发布或添加到建议书签列表中。</span><span class="sxs-lookup"><span data-stu-id="e7583-192">After an initial evaluation period, the recommended bookmarks will either be auto-published or added to the list of suggested bookmarks.</span></span> <span data-ttu-id="e7583-193">下一个周期（30 天评估周期后，自动发布或添加建议的书签）将开始。</span><span class="sxs-lookup"><span data-stu-id="e7583-193">The next cycle—a 30-day evaluation period followed by auto-publishing or adding suggested bookmarks—will then begin.</span></span>

<span data-ttu-id="e7583-194">我们建议搜索管理员或编辑定期查看这些自动发布的书签或建议书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-194">We suggest Search admins or editors review these auto-published or suggested bookmarks on a regular basis.</span></span> <span data-ttu-id="e7583-195">此外，建议的书签绝不会包含现有已发布、建议、计划或排除的书签中的 URL。</span><span class="sxs-lookup"><span data-stu-id="e7583-195">Also, recommended bookmarks will never include URLs found in existing Published, Suggested, Scheduled, or Excluded bookmarks.</span></span>

<span data-ttu-id="e7583-196">为了确保只有具有访问权限的用户才能在工作结果中看到推荐的书签，所有推荐的书签都包含访问检查功能。</span><span class="sxs-lookup"><span data-stu-id="e7583-196">To ensure only users with access will see a recommended bookmark in their work results, an access check feature is included for all recommended bookmarks.</span></span> <span data-ttu-id="e7583-197">无权访问 SharePoint 网站的用户绝不会看到该网站的建议书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-197">Users that don't have permissions to access a SharePoint site will never see the recommended bookmark for that site.</span></span> <span data-ttu-id="e7583-198">此访问检查由每个推荐书签的"组"设置中"仅有权访问此链接的人"选项控制。</span><span class="sxs-lookup"><span data-stu-id="e7583-198">This access check is controlled by the option **Only people with access to this link** in the Groups setting for each recommended bookmark.</span></span>

<span data-ttu-id="e7583-199">如果建议书签中的 URL 或"组"设置发生更改，则访问检查将停止。</span><span class="sxs-lookup"><span data-stu-id="e7583-199">The access check will stop if the URL in the recommended bookmark or the Groups setting is changed.</span></span>

<span data-ttu-id="e7583-200">若要阻止建议引擎向特定网站发布或建议书签，可以将 URL 添加到排除的列表。</span><span class="sxs-lookup"><span data-stu-id="e7583-200">To prevent the recommendation engine from publishing or suggesting a bookmark to a particular site, you can add the URL to an excluded list.</span></span> <span data-ttu-id="e7583-201">建议引擎绝不会为排除的网站或已排除网站中的页面发布或建议书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-201">The recommendation engine will never publish or suggest a bookmark for an excluded site or a page within an excluded site.</span></span>

## <a name="about-keywords-and-reserved-keywords"></a><span data-ttu-id="e7583-202">关于关键字和保留的关键字</span><span class="sxs-lookup"><span data-stu-id="e7583-202">About keywords and reserved keywords</span></span>

<span data-ttu-id="e7583-203">书签可以具有多个关键字，书签可以共享相同的关键字，但保留的关键字不能共享。</span><span class="sxs-lookup"><span data-stu-id="e7583-203">A bookmark can have several keywords and bookmarks can share the same keyword, but reserved keyword can't be shared.</span></span> <span data-ttu-id="e7583-204">保留的关键字是触发一个特定书签的唯一术语或短语。</span><span class="sxs-lookup"><span data-stu-id="e7583-204">A reserved keyword is a unique term or phrase that triggers one specific bookmark.</span></span> <span data-ttu-id="e7583-205">保留的关键字只能与一个答案相关联。</span><span class="sxs-lookup"><span data-stu-id="e7583-205">A reserved keyword can be associated with one answer only.</span></span> <span data-ttu-id="e7583-206">请谨慎使用保留的关键字。</span><span class="sxs-lookup"><span data-stu-id="e7583-206">Use reserved keywords sparingly.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e7583-207">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="e7583-207">Frequently asked questions</span></span>

<span data-ttu-id="e7583-208">**问：书签发布后在 Microsoft 搜索中可见需要多久？**</span><span class="sxs-lookup"><span data-stu-id="e7583-208">**Q: How long does it take for a bookmark to be visible in Microsoft Search after it's published?**</span></span>

<span data-ttu-id="e7583-209">**答：**  发布后立即在 Microsoft 搜索中提供书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-209">**A:**  A bookmark is available in Microsoft Search immediately after publishing.</span></span>

<span data-ttu-id="e7583-210">**问：显示建议的书签需要多久？**</span><span class="sxs-lookup"><span data-stu-id="e7583-210">**Q: How long does it take for a recommended bookmark to appear?**</span></span>

<span data-ttu-id="e7583-211">**答：**  只有在同时启用推荐书签和自动发布时，建议的书签才显示在 Microsoft 搜索中。</span><span class="sxs-lookup"><span data-stu-id="e7583-211">**A:**  Recommended bookmarks will only appear in Microsoft Search if both Recommended bookmarks and auto-publishing are enabled.</span></span> <span data-ttu-id="e7583-212">在初始评估期间，建议引擎将评估 SharePoint 流量，以确定合适的书签，然后自动发布它们。</span><span class="sxs-lookup"><span data-stu-id="e7583-212">During the initial evaluation period, the recommendation engine will evaluate SharePoint traffic to identify suitable bookmarks and then auto-publish them.</span></span> <span data-ttu-id="e7583-213">一旦发布，它们将立即在 Microsoft 搜索中可用。</span><span class="sxs-lookup"><span data-stu-id="e7583-213">Once published they become available immediately in Microsoft Search.</span></span>

<span data-ttu-id="e7583-214">**问：Microsoft 搜索会从所有语言的网站推荐书签吗？**</span><span class="sxs-lookup"><span data-stu-id="e7583-214">**Q: Will Microsoft Search recommend bookmarks from sites in all languages?**</span></span>

<span data-ttu-id="e7583-215">**答**：是的，Microsoft 搜索可以从任何内部 SharePoint 网站推荐书签，无论语言如何。</span><span class="sxs-lookup"><span data-stu-id="e7583-215">**A**: Yes, Microsoft Search can recommend bookmarks from any internal SharePoint site, regardless of the language.</span></span>

<span data-ttu-id="e7583-216">**问：能否停止在搜索结果中显示推荐的书签？**</span><span class="sxs-lookup"><span data-stu-id="e7583-216">**Q: Can I stop showing recommended bookmarks in search results?**</span></span>

<span data-ttu-id="e7583-217">**答：** 若要停止显示推荐的书签，请关闭管理中心中的自动发布设置。</span><span class="sxs-lookup"><span data-stu-id="e7583-217">**A:** To stop showing recommended bookmarks, turn the auto-publish setting off in your admin center.</span></span> <span data-ttu-id="e7583-218">建议书签将添加到建议书签列表中。</span><span class="sxs-lookup"><span data-stu-id="e7583-218">Recommended bookmarks will be added to the list of suggested bookmarks.</span></span>

<span data-ttu-id="e7583-219">**问：如何在搜索结果或管理中心中标识推荐的书签？**</span><span class="sxs-lookup"><span data-stu-id="e7583-219">**Q: How can I identify a recommended bookmark in search results or the admin center?**</span></span>

<span data-ttu-id="e7583-220">**答：** 在搜索结果中，建议的书签在 URL 前包含短语"Suggested for you"。</span><span class="sxs-lookup"><span data-stu-id="e7583-220">**A:** In search results, recommended bookmarks include the phrase "Suggested for you" before the URL.</span></span> <span data-ttu-id="e7583-221">在管理中心中，缩小的书签的所有者值为"SYSTEM"。</span><span class="sxs-lookup"><span data-stu-id="e7583-221">In the admin center, mined bookmarks will have an Owner value of "SYSTEM".</span></span>

<span data-ttu-id="e7583-222">**问：如何管理对推荐的书签的访问？**</span><span class="sxs-lookup"><span data-stu-id="e7583-222">**Q: How is access to a recommended bookmark managed?**</span></span>

<span data-ttu-id="e7583-223">**答**：由 Microsoft 设计的访问引擎确定书签 URL 是否可供特定用户访问，并且只会向正确的受众显示推荐的书签。</span><span class="sxs-lookup"><span data-stu-id="e7583-223">**A**: A Microsoft-engineered access engine determines if the bookmark URL is accessible to a particular user and will only show the recommended bookmark to the correct audience.</span></span> <span data-ttu-id="e7583-224">但是，如果编辑了 URL 或更改了组设置，则工程访问引擎将被禁用。</span><span class="sxs-lookup"><span data-stu-id="e7583-224">However, if the URL is edited or the Groups setting is changed, the engineered access engine will be disabled.</span></span>

<span data-ttu-id="e7583-225">**问：如果对添加到"建议"列表的建议书签未执行任何操作，会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="e7583-225">**Q: What happens if no action is taken on recommended bookmarks added to the Suggested list?**</span></span>

<span data-ttu-id="e7583-226">**答**：为了避免建议列表中出现大量书签，建议 (所有者 = SYSTEM) 将在 180 天后清除。</span><span class="sxs-lookup"><span data-stu-id="e7583-226">**A**: To avoid a high volume of bookmarks in the suggested list, a recommended bookmark (owner = SYSTEM) will be purged after 180 days.</span></span>

<span data-ttu-id="e7583-227">**问：在哪里可以找到 Power App 的应用 ID？**</span><span class="sxs-lookup"><span data-stu-id="e7583-227">**Q: Where do I find the App ID for a Power App?**</span></span>

<span data-ttu-id="e7583-228">**答**：转到 Power Apps 网站并查看应用的详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="e7583-228">**A**: Go to the Power Apps site and view the Details pane for the app.</span></span> <span data-ttu-id="e7583-229">详细了解如何[获取应用 ID。](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)</span><span class="sxs-lookup"><span data-stu-id="e7583-229">Learn more about [getting an app ID](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id).</span></span>
