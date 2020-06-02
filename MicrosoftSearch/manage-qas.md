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
description: 单独查找和更新答案，或使用 Microsoft Search tools 以一次性编辑 Q&。
ms.openlocfilehash: af966cfaae6680a063feb25d2736303106c19978
ms.sourcegitcommit: 0050e113517a36e3ca26028a04ac5c236caaf524
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470269"
---
# <a name="manage-qas"></a><span data-ttu-id="33bf1-103">管理问答</span><span class="sxs-lookup"><span data-stu-id="33bf1-103">Manage Q&As</span></span>

<span data-ttu-id="33bf1-104">创建问答类似于创建书签。</span><span class="sxs-lookup"><span data-stu-id="33bf1-104">Creating a Q&A is similar to creating bookmarks.</span></span> <span data-ttu-id="33bf1-105">Q&，使您可以回答用户的问题，而不只是提供指向网页的链接。</span><span class="sxs-lookup"><span data-stu-id="33bf1-105">Q&As allow you to answer the user's questions instead of just providing a link to a webpage.</span></span> <span data-ttu-id="33bf1-106">您还可以设置格式文本中的答案的格式。</span><span class="sxs-lookup"><span data-stu-id="33bf1-106">You can also format the answer in rich text.</span></span> <span data-ttu-id="33bf1-107">如果书签和 Q&共享相同的关键字，则首先显示书签结果。</span><span class="sxs-lookup"><span data-stu-id="33bf1-107">If a bookmark and a Q&A share the same keyword, the bookmark result is shown first.</span></span> <span data-ttu-id="33bf1-108">与书签一样，在添加或更改 Q&A 之后，会立即刷新 Q&索引。</span><span class="sxs-lookup"><span data-stu-id="33bf1-108">Like bookmarks, the Q&A index is refreshed immediately after a Q&A is added or changed.</span></span>

## <a name="add-or-edit-a-single-qa"></a><span data-ttu-id="33bf1-109">添加或编辑单个问答</span><span class="sxs-lookup"><span data-stu-id="33bf1-109">Add or edit a single Q&A</span></span>

1. <span data-ttu-id="33bf1-110">转到 **Microsoft 365 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="33bf1-110">Go to **Microsoft 365 admin center**.</span></span>
1. <span data-ttu-id="33bf1-111">在导航窗格中，转到“**设置**”，然后选择“**Microsoft 搜索**”。</span><span class="sxs-lookup"><span data-stu-id="33bf1-111">In the navigation pane, go to **Settings** and select **Microsoft Search**.</span></span>
1. <span data-ttu-id="33bf1-112">选择 " **Q&一个**选项卡。</span><span class="sxs-lookup"><span data-stu-id="33bf1-112">Select the **Q&A** tab.</span></span>
1. <span data-ttu-id="33bf1-113">若要添加问答，请选择“**新增**”。</span><span class="sxs-lookup"><span data-stu-id="33bf1-113">To add a Q&A, select **Add new**.</span></span>
<span data-ttu-id="33bf1-114">若要编辑问答，请在相关问答列表中选择问答。</span><span class="sxs-lookup"><span data-stu-id="33bf1-114">To edit a Q&A, select the Q&A in the relevant Q&A list.</span></span> <span data-ttu-id="33bf1-115">在你添加或编辑信息时，预览将随之自动更新。</span><span class="sxs-lookup"><span data-stu-id="33bf1-115">As you add or edit the information, the preview automatically updates.</span></span>
1. <span data-ttu-id="33bf1-116">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="33bf1-116">Save your changes.</span></span>

### <a name="supported-html-tags"></a><span data-ttu-id="33bf1-117">受支持的 HTML 标记</span><span class="sxs-lookup"><span data-stu-id="33bf1-117">Supported HTML tags</span></span>

<span data-ttu-id="33bf1-118">可以使用现有的 HTML 内容或为答案（说明）添加 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="33bf1-118">You can use existing HTML content or add HTML tags to your answer (description).</span></span> <span data-ttu-id="33bf1-119">不支持的标记将被忽略。</span><span class="sxs-lookup"><span data-stu-id="33bf1-119">Unsupported tags are ignored.</span></span>

<span data-ttu-id="33bf1-120">支持以下 HTML 标记：</span><span class="sxs-lookup"><span data-stu-id="33bf1-120">The following HTML tags are supported:</span></span>

- <span data-ttu-id="33bf1-121">blockquote</span><span class="sxs-lookup"><span data-stu-id="33bf1-121">blockquote</span></span>
- <span data-ttu-id="33bf1-122">div</span><span class="sxs-lookup"><span data-stu-id="33bf1-122">div</span></span>
- <span data-ttu-id="33bf1-123">em</span><span class="sxs-lookup"><span data-stu-id="33bf1-123">em</span></span>
- <span data-ttu-id="33bf1-124">h1、h2、h3 和 h4</span><span class="sxs-lookup"><span data-stu-id="33bf1-124">h1, h2, h3, and h4</span></span>
- <span data-ttu-id="33bf1-125">ol、ul 和 li</span><span class="sxs-lookup"><span data-stu-id="33bf1-125">ol, ul, and li</span></span>
- <span data-ttu-id="33bf1-126">p</span><span class="sxs-lookup"><span data-stu-id="33bf1-126">p</span></span>
- <span data-ttu-id="33bf1-127">pre</span><span class="sxs-lookup"><span data-stu-id="33bf1-127">pre</span></span>
- <span data-ttu-id="33bf1-128">span</span><span class="sxs-lookup"><span data-stu-id="33bf1-128">span</span></span>
- <span data-ttu-id="33bf1-129">strong</span><span class="sxs-lookup"><span data-stu-id="33bf1-129">strong</span></span>
- <span data-ttu-id="33bf1-130">table、thead、tbody、tr、th 和 td</span><span class="sxs-lookup"><span data-stu-id="33bf1-130">table, thead, tbody, tr, th, and td</span></span>
- <span data-ttu-id="33bf1-131">u</span><span class="sxs-lookup"><span data-stu-id="33bf1-131">u</span></span>
- <span data-ttu-id="33bf1-132">a</span><span class="sxs-lookup"><span data-stu-id="33bf1-132">a</span></span>
- <span data-ttu-id="33bf1-133">code</span><span class="sxs-lookup"><span data-stu-id="33bf1-133">code</span></span>
- <span data-ttu-id="33bf1-134">br</span><span class="sxs-lookup"><span data-stu-id="33bf1-134">br</span></span>
- <span data-ttu-id="33bf1-135">hr</span><span class="sxs-lookup"><span data-stu-id="33bf1-135">hr</span></span>
- <span data-ttu-id="33bf1-136">img</span><span class="sxs-lookup"><span data-stu-id="33bf1-136">img</span></span>

## <a name="add-or-edit-qas-using-browser-extensions"></a><span data-ttu-id="33bf1-137">使用浏览器扩展添加或编辑 Q&</span><span class="sxs-lookup"><span data-stu-id="33bf1-137">Add or edit Q&As using browser extensions</span></span>

<span data-ttu-id="33bf1-138">搜索管理员可以使用浏览器扩展轻松创建搜索内容。</span><span class="sxs-lookup"><span data-stu-id="33bf1-138">Search administrators can create search content easily by using browser extensions.</span></span> <span data-ttu-id="33bf1-139">安装浏览器扩展，然后转到要从中生成 Q&的网站。</span><span class="sxs-lookup"><span data-stu-id="33bf1-139">Install the browser extension, and then go to the site from which you want to generate a Q&A.</span></span> <span data-ttu-id="33bf1-140">然后，您可以创建 Q&A 并包含指向源网站的链接。</span><span class="sxs-lookup"><span data-stu-id="33bf1-140">You can then create the Q&A and include a link to the source site.</span></span>

<span data-ttu-id="33bf1-141">目前，浏览器扩展适用于 Microsoft Edge 和 Chrome。</span><span class="sxs-lookup"><span data-stu-id="33bf1-141">Currently, browser extensions are available for Microsoft Edge and Chrome.</span></span>

- <span data-ttu-id="33bf1-142">若要下载边缘扩展，请转到[Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="33bf1-142">To download Edge extensions, go to [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).</span></span>
- <span data-ttu-id="33bf1-143">若要下载 Chrome 扩展，请转到[chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)。</span><span class="sxs-lookup"><span data-stu-id="33bf1-143">To download Chrome extensions, go to the [Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).</span></span>

## <a name="bulk-add-or-edit-qas"></a><span data-ttu-id="33bf1-144">批量添加或编辑问答</span><span class="sxs-lookup"><span data-stu-id="33bf1-144">Bulk add or edit Q&As</span></span>

<span data-ttu-id="33bf1-145">管理员可以使用导入和导出功能批量创建或编辑 Q&As。</span><span class="sxs-lookup"><span data-stu-id="33bf1-145">Administrators can use the Import and Export features to bulk create or edit Q&As.</span></span>

<span data-ttu-id="33bf1-146">使用导入/导出功能执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="33bf1-146">Use the Import/Export feature to:</span></span>

- <span data-ttu-id="33bf1-147">批量添加 Q&-在 Q&模板文件中添加详细信息，然后将其导入。</span><span class="sxs-lookup"><span data-stu-id="33bf1-147">Bulk add Q&As - Add details in the Q&A template file, and then import it.</span></span>
- <span data-ttu-id="33bf1-148">批量编辑 Q&As-Export Q&为 .csv 文件，请编辑 Q&导出文件中的详细信息，然后导入该文件。</span><span class="sxs-lookup"><span data-stu-id="33bf1-148">Bulk edit Q&As - Export Q&As to a .csv file, edit the Q&A details in the exported file, and then import the file.</span></span>
- <span data-ttu-id="33bf1-149">以 .csv 文件的形式备份 Q&As-Export Q&。</span><span class="sxs-lookup"><span data-stu-id="33bf1-149">Back up Q&As - Export Q&As to a .csv file.</span></span>

<span data-ttu-id="33bf1-150">导入或导出 Q&为：</span><span class="sxs-lookup"><span data-stu-id="33bf1-150">To import or export Q&As:</span></span>

1. <span data-ttu-id="33bf1-151">在“问答”选项卡的右上角，选择“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="33bf1-151">In the upper-right corner of the Q&A tab, select **Import**.</span></span>
<span data-ttu-id="33bf1-152">选择 "**导出**" 以下载所有现有的 Q&，如 .csv 文件中所示。</span><span class="sxs-lookup"><span data-stu-id="33bf1-152">Select **Export** to download all the existing Q&As in a .csv file.</span></span>
1. <span data-ttu-id="33bf1-153">在右侧窗格中，选择要使用 .csv 文件导入的选项。</span><span class="sxs-lookup"><span data-stu-id="33bf1-153">In the right pane, select the option to import by using a .csv file.</span></span> <span data-ttu-id="33bf1-154">下载模板文件以获取必需字段和详细信息的列表。</span><span class="sxs-lookup"><span data-stu-id="33bf1-154">Download the template file to get a list of the required fields and details.</span></span>
1. <span data-ttu-id="33bf1-155">添加或编辑 Q&模板文件中的详细信息，并将其保存到计算机上。</span><span class="sxs-lookup"><span data-stu-id="33bf1-155">Add or edit Q&A details in the template file, and save it on your computer.</span></span>
1. <span data-ttu-id="33bf1-156">在 "**导入 Q&** 窗格中，选择"**浏览**"，然后选择要导入的 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="33bf1-156">In the **Import Q&A** pane, select **Browse**, and then select the .csv file that you want to import.</span></span>
1. <span data-ttu-id="33bf1-157">选择“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="33bf1-157">Select **Import**.</span></span>

<span data-ttu-id="33bf1-158">重要的模板文件提示：</span><span class="sxs-lookup"><span data-stu-id="33bf1-158">Important template file tips:</span></span>

- <span data-ttu-id="33bf1-159">请勿编辑以下字段中的数据：**Id**、**上次修改时间**和**上次修改者**</span><span class="sxs-lookup"><span data-stu-id="33bf1-159">Never edit data in these fields: **Id**, **Last Modified**, and **Last Modified By**</span></span>
- <span data-ttu-id="33bf1-160">如果包含现有书签的 **Id**，则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="33bf1-160">If you include the **Id** of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="33bf1-161">如果现有书签具有相同的标题或 URL，则将使用导入文件中的信息更新该书签。</span><span class="sxs-lookup"><span data-stu-id="33bf1-161">If there's an existing bookmark that has the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="33bf1-162">并不是模板文件中的所有字段都是必需的，并且根据书签状态不同，必需的字段也会有所不同。</span><span class="sxs-lookup"><span data-stu-id="33bf1-162">Not all fields in the template file are required, and the required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="33bf1-163">根据 "**省/市/自治区**" 字段，将书签保存为*草稿*、*建议*或*计划*或自动发布。</span><span class="sxs-lookup"><span data-stu-id="33bf1-163">Based on the **State** field, bookmarks are saved as *draft*, *suggested*, or *scheduled*, or they are published automatically.</span></span>
- <span data-ttu-id="33bf1-164">对于管理多个组织的合作伙伴：您可以从一个组织中导出您的书签并将其导入到另一个组织中。</span><span class="sxs-lookup"><span data-stu-id="33bf1-164">For partners who manage multiple organizations: You can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="33bf1-165">但是，在导入之前，你必须删除 **Id** 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="33bf1-165">But you must remove the data in the **Id** column before you import.</span></span>

> [!NOTE]
> <span data-ttu-id="33bf1-166">您不能导入 Q&，就像模板文件中有任何错误一样。</span><span class="sxs-lookup"><span data-stu-id="33bf1-166">You can't import Q&As if there are any errors in the template file.</span></span> <span data-ttu-id="33bf1-167">若要防止错误，请确保您的导入文件格式正确，并包含所有必需的信息。</span><span class="sxs-lookup"><span data-stu-id="33bf1-167">To prevent errors, make sure your import file is properly formatted, and include all the required information.</span></span>

<span data-ttu-id="33bf1-168">有关避免错误的详细信息，请参阅[防止导入错误](manage-bookmarks.md#prevent-import-errors)。</span><span class="sxs-lookup"><span data-stu-id="33bf1-168">For more information about avoiding errors, see [Prevent import errors](manage-bookmarks.md#prevent-import-errors).</span></span>
