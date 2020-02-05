---
title: 管理问答
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: 查找和更新单个解答或使用可用的 Microsoft 搜索工具同时编辑所有解答
ms.openlocfilehash: 0877de027b68589e5ba15cd8109ea7edeeae8725
ms.sourcegitcommit: c22e8c3dcc53857da677db98a1a2b7d5ca2c6170
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41721738"
---
# <a name="manage-qas"></a><span data-ttu-id="6d03c-103">管理问答</span><span class="sxs-lookup"><span data-stu-id="6d03c-103">Manage Q&As</span></span>

<span data-ttu-id="6d03c-104">创建问答类似于创建书签。</span><span class="sxs-lookup"><span data-stu-id="6d03c-104">Creating a Q&A is similar to creating bookmarks.</span></span> <span data-ttu-id="6d03c-105">问答可以让你回答用户的问题，而不仅仅是提供网页链接。</span><span class="sxs-lookup"><span data-stu-id="6d03c-105">Q&A allows you to answer the user's question instead of just providing a link to webpage.</span></span> <span data-ttu-id="6d03c-106">你可以使用可用工具以富文本形式来格式化答案。</span><span class="sxs-lookup"><span data-stu-id="6d03c-106">You can format the answer in rich text using the available tools.</span></span> <span data-ttu-id="6d03c-107">如果书签和问答共享同一个关键字，则会先显示书签结果。</span><span class="sxs-lookup"><span data-stu-id="6d03c-107">If a Bookmark and a Q&A share the same keyword, the Bookmark result is shown first.</span></span> <span data-ttu-id="6d03c-108">与书签一样，在添加或更改问答后将立即刷新问答索引。</span><span class="sxs-lookup"><span data-stu-id="6d03c-108">Like Bookmarks, the Q&A index is refreshed immediately after a Q&A is added or changed.</span></span>

## <a name="add-or-edit-a-single-qa"></a><span data-ttu-id="6d03c-109">添加或编辑单个问答</span><span class="sxs-lookup"><span data-stu-id="6d03c-109">Add or edit a single Q&A</span></span>

1. <span data-ttu-id="6d03c-110">转到 **Microsoft 365 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="6d03c-110">Go to **Microsoft 365 admin center**.</span></span>
1. <span data-ttu-id="6d03c-111">在导航窗格中，转到“**设置**”，然后选择“**Microsoft 搜索**”。</span><span class="sxs-lookup"><span data-stu-id="6d03c-111">In the navigation pane, go to **Settings** and select **Microsoft Search**.</span></span>
1. <span data-ttu-id="6d03c-112">选择“**问答**”选项卡。默认情况下，第一个选项卡（**书签**）处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="6d03c-112">Select **Q&A** tab. By default, the first tab (**Bookmarks**) is selected.</span></span>
1. <span data-ttu-id="6d03c-113">若要添加问答，请选择“**新增**”。</span><span class="sxs-lookup"><span data-stu-id="6d03c-113">To add a Q&A, select **Add new**.</span></span>
<span data-ttu-id="6d03c-114">若要编辑问答，请在相关问答列表中选择问答。</span><span class="sxs-lookup"><span data-stu-id="6d03c-114">To edit a Q&A, select the Q&A in the relevant Q&A list.</span></span>
1. <span data-ttu-id="6d03c-115">在你添加或编辑信息时，预览将随之自动更新。</span><span class="sxs-lookup"><span data-stu-id="6d03c-115">As you add or edit the information, the preview automatically updates.</span></span>
1. <span data-ttu-id="6d03c-116">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6d03c-116">Save your changes.</span></span>

### <a name="supported-html-tags"></a><span data-ttu-id="6d03c-117">受支持的 HTML 标记</span><span class="sxs-lookup"><span data-stu-id="6d03c-117">Supported HTML tags</span></span>

<span data-ttu-id="6d03c-118">可以使用现有的 HTML 内容或为答案（说明）添加 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="6d03c-118">You can use existing HTML content or add HTML tags to your answer (description).</span></span> <span data-ttu-id="6d03c-119">不支持的标记将被忽略。</span><span class="sxs-lookup"><span data-stu-id="6d03c-119">Unsupported tags are ignored.</span></span>  
<span data-ttu-id="6d03c-120">支持以下 HTML 标记：</span><span class="sxs-lookup"><span data-stu-id="6d03c-120">The following HTML tags are supported:</span></span>

- <span data-ttu-id="6d03c-121">blockquote</span><span class="sxs-lookup"><span data-stu-id="6d03c-121">blockquote</span></span>
- <span data-ttu-id="6d03c-122">div</span><span class="sxs-lookup"><span data-stu-id="6d03c-122">div</span></span>
- <span data-ttu-id="6d03c-123">em</span><span class="sxs-lookup"><span data-stu-id="6d03c-123">em</span></span>
- <span data-ttu-id="6d03c-124">h1、h2、h3 和 h4</span><span class="sxs-lookup"><span data-stu-id="6d03c-124">h1, h2, h3, and h4</span></span>
- <span data-ttu-id="6d03c-125">ol、ul 和 li</span><span class="sxs-lookup"><span data-stu-id="6d03c-125">ol, ul, and li</span></span>
- <span data-ttu-id="6d03c-126">p</span><span class="sxs-lookup"><span data-stu-id="6d03c-126">p</span></span>
- <span data-ttu-id="6d03c-127">pre</span><span class="sxs-lookup"><span data-stu-id="6d03c-127">pre</span></span>
- <span data-ttu-id="6d03c-128">span</span><span class="sxs-lookup"><span data-stu-id="6d03c-128">span</span></span>
- <span data-ttu-id="6d03c-129">strong</span><span class="sxs-lookup"><span data-stu-id="6d03c-129">strong</span></span>
- <span data-ttu-id="6d03c-130">table、thead、tbody、tr、th 和 td</span><span class="sxs-lookup"><span data-stu-id="6d03c-130">table, thead, tbody, tr, th, and td</span></span>
- <span data-ttu-id="6d03c-131">u</span><span class="sxs-lookup"><span data-stu-id="6d03c-131">u</span></span>
- <span data-ttu-id="6d03c-132">a</span><span class="sxs-lookup"><span data-stu-id="6d03c-132">a</span></span>
- <span data-ttu-id="6d03c-133">code</span><span class="sxs-lookup"><span data-stu-id="6d03c-133">code</span></span>
- <span data-ttu-id="6d03c-134">br</span><span class="sxs-lookup"><span data-stu-id="6d03c-134">br</span></span>
- <span data-ttu-id="6d03c-135">hr</span><span class="sxs-lookup"><span data-stu-id="6d03c-135">hr</span></span>
- <span data-ttu-id="6d03c-136">img</span><span class="sxs-lookup"><span data-stu-id="6d03c-136">img</span></span>

## <a name="add-or-edit-qas-using-browser-extensions"></a><span data-ttu-id="6d03c-137">使用浏览器扩展添加或编辑 Q&</span><span class="sxs-lookup"><span data-stu-id="6d03c-137">Add or edit Q&As using browser extensions</span></span>

<span data-ttu-id="6d03c-138">搜索管理员可以使用浏览器扩展轻松创建搜索内容。</span><span class="sxs-lookup"><span data-stu-id="6d03c-138">Search administrators can create search content easily by using browser extensions.</span></span> <span data-ttu-id="6d03c-139">安装浏览器扩展，然后转到要从中生成 Q&的网站。</span><span class="sxs-lookup"><span data-stu-id="6d03c-139">Install the browser extension and then go to the site from which you want to generate a Q&A.</span></span> <span data-ttu-id="6d03c-140">然后，您可以创建 Q&A 并包含指向源网站的链接。</span><span class="sxs-lookup"><span data-stu-id="6d03c-140">You can then create the Q&A and include a link to the source site.</span></span>

<span data-ttu-id="6d03c-141">目前，为 Microsoft Edge 和 Chrome 提供了浏览器扩展。</span><span class="sxs-lookup"><span data-stu-id="6d03c-141">Currently, browser extensions are available for Edge and Chrome.</span></span>

- <span data-ttu-id="6d03c-142">若要下载边缘扩展，请转到[Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)并下载该应用。</span><span class="sxs-lookup"><span data-stu-id="6d03c-142">To download Edge extensions, go to [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) and download the app.</span></span>
- <span data-ttu-id="6d03c-143">若要下载 Chrome 扩展，请转到[chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)并下载该应用。</span><span class="sxs-lookup"><span data-stu-id="6d03c-143">To download Chrome extensions, go to [Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) and download the app.</span></span>

## <a name="bulk-add-or-edit-qas"></a><span data-ttu-id="6d03c-144">批量添加或编辑问答</span><span class="sxs-lookup"><span data-stu-id="6d03c-144">Bulk add or edit Q&As</span></span>

<span data-ttu-id="6d03c-145">管理员可以使用导入和导出功能批量创建或编辑问答。</span><span class="sxs-lookup"><span data-stu-id="6d03c-145">Administrators can use the Import and Export features to bulk create or edit Q&A.</span></span> <span data-ttu-id="6d03c-146">当管理员需要添加或编辑大量问答时，这是一项非常有用的功能。</span><span class="sxs-lookup"><span data-stu-id="6d03c-146">This is a useful feature when administrators need to add or edit a large number of Q&A.</span></span>

<span data-ttu-id="6d03c-147">使用导入/导出功能可以：</span><span class="sxs-lookup"><span data-stu-id="6d03c-147">Use the import/export feature to:</span></span>

1. <span data-ttu-id="6d03c-148">批量添加问答 - 在问答模板文件中添加详细信息，然后导入它。</span><span class="sxs-lookup"><span data-stu-id="6d03c-148">Bulk add Q&A - Add details in the Q&A template file, and then import it.</span></span>
1. <span data-ttu-id="6d03c-149">批量编辑问答 - 将问答导出到 .csv 文件，编辑导出的 .csv 文件中的问答详细信息，然后导入更新的 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="6d03c-149">Bulk edit Q&A - Export Q&A to a .csv file, then edit the Q&A details in the exported .csv file, and then import the .csv file.</span></span>
1. <span data-ttu-id="6d03c-150">备份问答 - 将问答导出到 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="6d03c-150">Backup Q&A - Export Q&A to a .csv file.</span></span>

<span data-ttu-id="6d03c-151">若要导入或导出问答：</span><span class="sxs-lookup"><span data-stu-id="6d03c-151">To import or export Q&A:</span></span>

1. <span data-ttu-id="6d03c-152">在“问答”选项卡的右上角，选择“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="6d03c-152">In the upper-right corner of the Q&A tab, select **Import**.</span></span>
<span data-ttu-id="6d03c-153">选择“**导出**”以将所有现有的问答下载到 .csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="6d03c-153">Select **Export** to download all the existing Q&A in a .csv file.</span></span>
1. <span data-ttu-id="6d03c-154">在右侧窗格中，选择使用 .csv 文件导入的选项。</span><span class="sxs-lookup"><span data-stu-id="6d03c-154">In the right pane, choose the option to import using a .csv file.</span></span>
<span data-ttu-id="6d03c-155">下载模板文件以获取必填字段和详细信息的列表。</span><span class="sxs-lookup"><span data-stu-id="6d03c-155">Download the template file for a list of the required fields and details.</span></span>
1. <span data-ttu-id="6d03c-156">在模板文件中添加或编辑问答详细信息，然后将其保存在你的计算机上。</span><span class="sxs-lookup"><span data-stu-id="6d03c-156">Add or edit Q&A details in the template file and save it on your computer.</span></span>
1. <span data-ttu-id="6d03c-157">在“**导入问答**”窗格中，选择“**浏览**”，然后选择要导入的 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="6d03c-157">In the **Import Q&A** pane, select **Browse**, and then the .csv file that you want to import.</span></span>
1. <span data-ttu-id="6d03c-158">选择“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="6d03c-158">Select **Import**.</span></span>

<span data-ttu-id="6d03c-159">以下是关于模板文件的一些要点：</span><span class="sxs-lookup"><span data-stu-id="6d03c-159">Here are some important points regarding the template file:</span></span>

- <span data-ttu-id="6d03c-160">请勿编辑以下字段中的数据：*Id*、*上次修改时间*和*上次修改者*</span><span class="sxs-lookup"><span data-stu-id="6d03c-160">Never edit data in these fields: *Id*, *Last Modified*, and *Last Modified By*</span></span>
- <span data-ttu-id="6d03c-161">如果包含现有书签的 *Id*，则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="6d03c-161">If you include the *Id* of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="6d03c-162">如果存在具有相同标题或 URL 的现有书签，则将使用导入文件中的信息更新该书签。</span><span class="sxs-lookup"><span data-stu-id="6d03c-162">If there is an existing bookmark with the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="6d03c-163">在模板文件中，并非所有字段都是必填的，并且必填字段因书签状态而异。</span><span class="sxs-lookup"><span data-stu-id="6d03c-163">Not all fields in the template file are required and required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="6d03c-164">基于“状态”字段，书签会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。</span><span class="sxs-lookup"><span data-stu-id="6d03c-164">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>
- <span data-ttu-id="6d03c-165">对于管理多个组织的合作伙伴，您可以从一个组织中导出您的书签并将其导入到另一个组织中。</span><span class="sxs-lookup"><span data-stu-id="6d03c-165">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="6d03c-166">但是，在导入之前，你必须删除 *Id* 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="6d03c-166">But you must remove the data in the *Id* column before you import.</span></span>

<span data-ttu-id="6d03c-167">**注意：** 如果模板文件中有任何错误，则无法导入问答。</span><span class="sxs-lookup"><span data-stu-id="6d03c-167">**Note:** You cannot import Q&A if there are any errors in the template file.</span></span> <span data-ttu-id="6d03c-168">为防止出错，请确保导入文件具有正确格式，并且包含所有必需信息。</span><span class="sxs-lookup"><span data-stu-id="6d03c-168">To prevent errors, make sure your import file is properly formatted and include all the required information.</span></span>

<span data-ttu-id="6d03c-169">有关如何防止错误的详细信息，请参阅[防止导入错误](manage-bookmarks.md#prevent-import-errors)。</span><span class="sxs-lookup"><span data-stu-id="6d03c-169">For more information on how to prevent error, see [Prevent import errors](manage-bookmarks.md#prevent-import-errors).</span></span>
