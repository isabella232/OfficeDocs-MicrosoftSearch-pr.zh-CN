---
title: 创建问答
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: d432b9d9-3792-47a0-9a13-30a1a83caabc
description: 为 Microsoft 搜索工作结果创建常见问题解答的方法
ms.openlocfilehash: 9713608450688a0841aa64d1f3198183b10e05ee
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612495"
---
# <a name="create-qas"></a><span data-ttu-id="4e2cf-103">创建问答</span><span class="sxs-lookup"><span data-stu-id="4e2cf-103">Create Q&As</span></span>

<span data-ttu-id="4e2cf-p101">问答向用户提供包含可选链接的答案或信息。理想情况下，问答包括用户查找的所有详细信息，这样他们就不需要访问源。可以对问答内容进行格式设置，包括图像、列表和表格。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p101">Q&As provide an answer or info to users including an optional link. Ideally, a Q&A includes all the details your users are looking for so they don't need to go to the source. You can format your Q&A content and include images, lists, and tables.</span></span>
  
## <a name="create-a-qa"></a><span data-ttu-id="4e2cf-107">创建问答</span><span class="sxs-lookup"><span data-stu-id="4e2cf-107">Create a Q&A</span></span>

<span data-ttu-id="4e2cf-108">有关创建有效标题、说明、关键字的详细信息信息，请参阅[规划内容](plan-your-content.md)。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-108">For information about creating effective titles, descriptions, keywords, and more, see [Plan your content.](plan-your-content.md)</span></span>
  
1. <span data-ttu-id="4e2cf-109">转到 Microsoft 搜索管理门户</span><span class="sxs-lookup"><span data-stu-id="4e2cf-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="4e2cf-110">在导航窗格中，单击“问答”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4e2cf-110">In the navigation pane, click **ADSI Edit**.</span></span>
    
3. <span data-ttu-id="4e2cf-111">在页面顶部，单击“添加问答”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-111">At the top of the page, click **Share**.</span></span>
    
    <span data-ttu-id="4e2cf-p102">随即出现“编辑问答”页，包含问答在必应上的预览显示。当添加所需信息时，预览将自动更新。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p102">The Edit Q&A page appears, with a preview of how the Q&A will look on Bing. As you add the required information, the preview will automatically update.</span></span>
    
4. <span data-ttu-id="4e2cf-114">输入**标题**</span><span class="sxs-lookup"><span data-stu-id="4e2cf-114">Enter a **Title** for the new tile.</span></span>
    
    <span data-ttu-id="4e2cf-p103">标题是出现在结果中的标题。可长达 120 个字符，建议使用问题格式。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p103">The title is the heading that appears in the result. It can be up to 120 characters long and we recommend using a question format.</span></span>
    
5. <span data-ttu-id="4e2cf-117">如果需要，输入书签将链接到的页面、网站或位置的 **URL**</span><span class="sxs-lookup"><span data-stu-id="4e2cf-117">If needed, enter the **URL** of the page, site, or location the bookmark will link to</span></span> 
    
    <span data-ttu-id="4e2cf-118">这使得需要额外信息的用户可以轻松访问内容源以阅读更多信息。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-118">This lets users that need additional information easily get to the source to read more.</span></span>
    
6. <span data-ttu-id="4e2cf-119">输入**回答说明**</span><span class="sxs-lookup"><span data-stu-id="4e2cf-119">Enter an **Answer description**</span></span>
    
    <span data-ttu-id="4e2cf-p104">这应该能回答标题中提及的问题。可以复制现有的 HTML 内容并粘贴在此处。任何不受支持的标记都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p104">This should answer the question that's asked in the title. You can copy existing HTML content and paste it here. Any unsupported tags will be ignored.</span></span>
    
7. <span data-ttu-id="4e2cf-123">使用 HTML 标记和内置选项设置文本格式，添加图像、列表、表格等</span><span class="sxs-lookup"><span data-stu-id="4e2cf-123">Use HTML tags and the built-in options to format text, add images, lists, tables, and more</span></span>
    
    <span data-ttu-id="4e2cf-p105">使用页面顶部的预览来查看标记和格式将如何显示在必应上。有关信息：</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p105">Use the preview at the top of the page to see how your tags and formatting will appear on Bing. For information about:</span></span>
    
  - <span data-ttu-id="4e2cf-126">HTML 标记，参见下面支持的 HTML 标记列表</span><span class="sxs-lookup"><span data-stu-id="4e2cf-126">HTML tags, see the supported HTML tags list below</span></span>
    
  - <span data-ttu-id="4e2cf-127">内置选项，请单击“Markdown 指南”\*\*\*\*（问号图标）</span><span class="sxs-lookup"><span data-stu-id="4e2cf-127">Built-in options, click **Markdown guide** (question mark icon)</span></span> 
    
8. <span data-ttu-id="4e2cf-128">输入要触发此问答的**关键字**</span><span class="sxs-lookup"><span data-stu-id="4e2cf-128">Enter **Keywords** you want to trigger this Q&A</span></span> 
    
    <span data-ttu-id="4e2cf-p106">和书签一样，当用户搜索你包含的任何关键字时，此问答将包含在他们的工作结果中。尝试添加尽可能多的变体，包括问答标题。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p106">Like a bookmark, when a user searches for any of the keywords you've included, this Q&A will be included in their work results. Try adding as many variants as possible, including the title of the Q&A.</span></span>
    
9. <span data-ttu-id="4e2cf-131">选择“自动匹配类似关键字”\*\*\*\* 展开关键字集</span><span class="sxs-lookup"><span data-stu-id="4e2cf-131">Select **Automatically match similar keywords** to expand your set of keywords</span></span> 
    
    <span data-ttu-id="4e2cf-132">这样可以更广泛地匹配搜索词，并帮助确保将此问答包含在相关工作结果中。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-132">This enables a broader matching of search terms and helps ensure this Q&A is included in relevant work results.</span></span>
    
10. <span data-ttu-id="4e2cf-133">输入**保留的关键字**</span><span class="sxs-lookup"><span data-stu-id="4e2cf-133">Enter **Reserved keywords**</span></span>
    
    <span data-ttu-id="4e2cf-p107">如果一个关键字触发多个问答，Microsoft 搜索将把最热门的一个置顶，并显示其他相关链接。使用一个或多个保留的关键字来确保问答始终显示为置顶结果。保留的关键字不能在问答之间共享。另外，不建议在问答和书签之间共享保留的关键字。如果书签和问答共享关键字或保留的关键字，书签将始终优先，问答不会出现。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p107">If a keyword triggers multiple Q&As, Microsoft Search will place the most popular one at the top and show the others as related links. Use one or more reserved keywords to ensure a Q&A always appears as the top result. Reserved keywords can't be shared across Q&As. Also, sharing reserved keywords across Q&As and bookmarks isn't recommended. If a bookmark and a Q&A share a keyword or a reserved keyword, the bookmark will always take precedence and the Q&A will not appear.</span></span>
    
## <a name="add-qa-settings"></a><span data-ttu-id="4e2cf-139">添加问答设置</span><span class="sxs-lookup"><span data-stu-id="4e2cf-139">Add Q&A settings</span></span>

<span data-ttu-id="4e2cf-140">问答设置让你进一步控制问答何时出现以及谁可以看到它。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-140">Q&A settings give you additional control over when a Q&A appears and who sees it.</span></span>
  
- <span data-ttu-id="4e2cf-141">日期</span><span class="sxs-lookup"><span data-stu-id="4e2cf-141">Dates</span></span>
    
    <span data-ttu-id="4e2cf-142">设置开始日期和可选的结束日期，以控制问答何时发布或过期。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-142">Set a start date as well as an optional end date to control when a Q&A will be published or expire.</span></span>
    
- <span data-ttu-id="4e2cf-143">国家/地区</span><span class="sxs-lookup"><span data-stu-id="4e2cf-143">Country/region</span></span>
    
    <span data-ttu-id="4e2cf-144">如果选择国家或地区，仅这些位置中的用户会看到该问答。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-144">If you select countries or regions, only users in those locations will see that Q&A.</span></span>
    
- <span data-ttu-id="4e2cf-145">组</span><span class="sxs-lookup"><span data-stu-id="4e2cf-145">Groups</span></span>
    
    <span data-ttu-id="4e2cf-p108">使用组设置使问答结果仅对选定组的成员可用。例如，如果创建的问答仅适用于人力资源部门的员工，可以将该设置映射到适当的人力资源安全组。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p108">Use the Groups setting to make a Q&A result available only to members of a selected group. For example, if you're creating Q&As that pertain only to employees in the HR department, you could map this setting to the appropriate HR security group.</span></span>
    
- <span data-ttu-id="4e2cf-148">设备 &amp; OS</span><span class="sxs-lookup"><span data-stu-id="4e2cf-148">Device OS</span></span>
    
    <span data-ttu-id="4e2cf-149">如果选择设备类型或操作系统，只有在这些设备上搜索或使用这些系统的用户才会看到问答。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-149">If you select device types or operating systems, only users searching on those devices or using those systems will see that Q&A.</span></span>
    
- <span data-ttu-id="4e2cf-150">目标变体</span><span class="sxs-lookup"><span data-stu-id="4e2cf-150">Targeted variations</span></span>
    
    <span data-ttu-id="4e2cf-151">使用此设置可以根据用户的设备和位置更改问答内容。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-151">Use this setting to vary the content of the Q&A based on a user's device and location.</span></span>
    
## <a name="use-a-browser-extension-to-create-content"></a><span data-ttu-id="4e2cf-152">使用浏览器扩展来创建内容</span><span class="sxs-lookup"><span data-stu-id="4e2cf-152">Use a browser extension to create content</span></span>

<span data-ttu-id="4e2cf-p109">从管理门户的“工具”部分，下载并安装 Microsoft Edge 或 Chrome 的内容创建程序浏览器扩展。要使用扩展，请登录并进入希望作为问答添加的网站或页面。查看并更改建议的内容（包括关键字）、添加任何其他内容，并保存问答。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p109">From the Tools section of the Admin portal, download and install the Content creator browser extension for Edge or Chrome. To use the extension, sign in and go to a site or page that you want to add as a Q&A. Review and change the suggested content, including keywords, add any additional content, and save the Q&A.</span></span>
  
<span data-ttu-id="4e2cf-156">如果发现多个问答，请检查每个问答，并确定是要发布、保存到草稿还是全部保存到草稿。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-156">If multiple Q&As are found, review each one and determine whether you want to publish, save to draft, or save all to draft.</span></span>
  
## <a name="supported-html-tags"></a><span data-ttu-id="4e2cf-157">受支持的 HTML 标记</span><span class="sxs-lookup"><span data-stu-id="4e2cf-157">Supported HTML tags</span></span>

<span data-ttu-id="4e2cf-p110">可以使用现有的 HTML 内容或向答案说明添加 HTML 标记。不支持的标记将被忽略。</span><span class="sxs-lookup"><span data-stu-id="4e2cf-p110">You can use existing HTML content or add HTML tags to your answer description. Unsupported tags are ignored.</span></span>
  
- <span data-ttu-id="4e2cf-160">blockquote</span><span class="sxs-lookup"><span data-stu-id="4e2cf-160">blockquote</span></span>
    
- <span data-ttu-id="4e2cf-161">div</span><span class="sxs-lookup"><span data-stu-id="4e2cf-161">div</span></span>
    
- <span data-ttu-id="4e2cf-162">em</span><span class="sxs-lookup"><span data-stu-id="4e2cf-162">Em</span></span>
    
- <span data-ttu-id="4e2cf-163">h1、h2、h3 和 h4</span><span class="sxs-lookup"><span data-stu-id="4e2cf-163">h1, h2, h3, and h4</span></span>
    
- <span data-ttu-id="4e2cf-164">ol、ul 和 li</span><span class="sxs-lookup"><span data-stu-id="4e2cf-164">ol, ul, and li</span></span>
    
- <span data-ttu-id="4e2cf-165">p</span><span class="sxs-lookup"><span data-stu-id="4e2cf-165">p</span></span>
    
- <span data-ttu-id="4e2cf-166">pre</span><span class="sxs-lookup"><span data-stu-id="4e2cf-166">pre</span></span>
    
- <span data-ttu-id="4e2cf-167">span</span><span class="sxs-lookup"><span data-stu-id="4e2cf-167">span</span></span>
    
- <span data-ttu-id="4e2cf-168">strong</span><span class="sxs-lookup"><span data-stu-id="4e2cf-168">Strong</span></span>
    
- <span data-ttu-id="4e2cf-169">table、thead、tbody、tr、th 和 td</span><span class="sxs-lookup"><span data-stu-id="4e2cf-169">table, thead, tbody, tr, th, and td</span></span>
    
- <span data-ttu-id="4e2cf-170">u</span><span class="sxs-lookup"><span data-stu-id="4e2cf-170">u</span></span>
    
- <span data-ttu-id="4e2cf-171">a</span><span class="sxs-lookup"><span data-stu-id="4e2cf-171">a</span></span>
    
- <span data-ttu-id="4e2cf-172">code</span><span class="sxs-lookup"><span data-stu-id="4e2cf-172">Code</span></span>
    
- <span data-ttu-id="4e2cf-173">br</span><span class="sxs-lookup"><span data-stu-id="4e2cf-173">br</span></span>
    
- <span data-ttu-id="4e2cf-174">hr</span><span class="sxs-lookup"><span data-stu-id="4e2cf-174">hr</span></span>
    
- <span data-ttu-id="4e2cf-175">img</span><span class="sxs-lookup"><span data-stu-id="4e2cf-175">img</span></span>

  

