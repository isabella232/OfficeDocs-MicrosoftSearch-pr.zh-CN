---
title: 在 Microsoft 搜索中管理首字母缩写词答案
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
description: 在 Microsoft 搜索中创建和更新首字母缩略词解答
ms.openlocfilehash: 9de9de8287e3ddf206f93f53573922f3cf526580
ms.sourcegitcommit: ad225af81060a2e3d7e4c953eeb6977d54698b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709679"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="feb9d-103">在 Microsoft 搜索中管理首字母缩写词答案</span><span class="sxs-lookup"><span data-stu-id="feb9d-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="feb9d-104">用户经常遇到其组织或团队使用的不熟悉的缩写词和缩写。</span><span class="sxs-lookup"><span data-stu-id="feb9d-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="feb9d-105">对于从一个团队移动到另一个团队、与内部合作伙伴团队合作或对组织而言是新术语的人，特定于组织或团队的术语可能是新的。</span><span class="sxs-lookup"><span data-stu-id="feb9d-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="feb9d-106">组织并不总是有一个标准术语参考。</span><span class="sxs-lookup"><span data-stu-id="feb9d-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="feb9d-107">缺少单个引用使查找这些首字母缩写词的定义或扩展变得困难。</span><span class="sxs-lookup"><span data-stu-id="feb9d-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="feb9d-108">Microsoft 搜索使用首字母缩略词解决了此问题。</span><span class="sxs-lookup"><span data-stu-id="feb9d-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="feb9d-109">用户体验</span><span class="sxs-lookup"><span data-stu-id="feb9d-109">What users experience</span></span>

<span data-ttu-id="feb9d-110">Microsoft 搜索用户可以使用[必应](https://Bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)和[Office 365](https://Office.com)中的首字母缩略词获取定义。</span><span class="sxs-lookup"><span data-stu-id="feb9d-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="feb9d-111">在 **"搜索** "框中，用户输入类似以下示例的查询：</span><span class="sxs-lookup"><span data-stu-id="feb9d-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="feb9d-112">*什么是* DNN</span><span class="sxs-lookup"><span data-stu-id="feb9d-112">*What is* DNN</span></span>
- <span data-ttu-id="feb9d-113">*定义* DNN</span><span class="sxs-lookup"><span data-stu-id="feb9d-113">*Define* DNN</span></span>
- <span data-ttu-id="feb9d-114">DNN *定义*</span><span class="sxs-lookup"><span data-stu-id="feb9d-114">DNN *definition*</span></span>
- <span data-ttu-id="feb9d-115">*展开* DNN</span><span class="sxs-lookup"><span data-stu-id="feb9d-115">*Expand* DNN</span></span>
- <span data-ttu-id="feb9d-116">DNN *扩展*</span><span class="sxs-lookup"><span data-stu-id="feb9d-116">DNN *expansion*</span></span>
- <span data-ttu-id="feb9d-117">*含义* DNN</span><span class="sxs-lookup"><span data-stu-id="feb9d-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="feb9d-118">DNN *表示*</span><span class="sxs-lookup"><span data-stu-id="feb9d-118">DNN *means*</span></span>

<span data-ttu-id="feb9d-119">结果包括存在于用户组织内部的 DNN 的所有含义。</span><span class="sxs-lookup"><span data-stu-id="feb9d-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="feb9d-120">用户必须输入包含首字母缩写词指定关键字的查询，才能触发其对应的答案。</span><span class="sxs-lookup"><span data-stu-id="feb9d-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="feb9d-121">首字母缩略词查询不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="feb9d-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="feb9d-122">设置首字母缩写词答案</span><span class="sxs-lookup"><span data-stu-id="feb9d-122">Set up Acronyms answers</span></span>

<span data-ttu-id="feb9d-123">在 [Microsoft 365 管理中心](https://admin.microsoft.com)中，转到 [**首字母**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)缩略词，然后选择"添加 **首字母缩写词"。**</span><span class="sxs-lookup"><span data-stu-id="feb9d-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="feb9d-124">Microsoft 搜索查询两个数据源，以提供用户搜索的首字母缩略词解答：</span><span class="sxs-lookup"><span data-stu-id="feb9d-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="feb9d-125">**编辑首字母缩略词**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-125">**Editorial acronyms**.</span></span> <span data-ttu-id="feb9d-126">由管理中心中的 IT [管理员提供](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)。</span><span class="sxs-lookup"><span data-stu-id="feb9d-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="feb9d-127">**缩写首字母缩略词**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-127">**Mined acronyms**.</span></span> <span data-ttu-id="feb9d-128">由 Microsoft 搜索从用户的个人电子邮件和文档以及组织中公开的数据中缩小。</span><span class="sxs-lookup"><span data-stu-id="feb9d-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="feb9d-129">设置编辑首字母缩略词</span><span class="sxs-lookup"><span data-stu-id="feb9d-129">Set up editorial acronyms</span></span>

<span data-ttu-id="feb9d-130">搜索管理员可以在 Microsoft 搜索管理中心的首字母缩写词 [选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) 上设置  [编辑首字母缩略词](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。</span><span class="sxs-lookup"><span data-stu-id="feb9d-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="feb9d-131">可以将任何内部站点或存储库中的首字母缩写词添加到管理中心。</span><span class="sxs-lookup"><span data-stu-id="feb9d-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="feb9d-132">可以将编辑首字母缩略词添加到"已发布" **或** " **草稿"** 状态：</span><span class="sxs-lookup"><span data-stu-id="feb9d-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="feb9d-133">**已发布状态**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-133">**Published state**.</span></span> <span data-ttu-id="feb9d-134">通过 Microsoft 搜索，组织的员工可以使用缩写词。</span><span class="sxs-lookup"><span data-stu-id="feb9d-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="feb9d-135">添加到已发布状态首字母缩略词在 Microsoft 搜索中可能最多需要三天。</span><span class="sxs-lookup"><span data-stu-id="feb9d-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="feb9d-136">**草稿状态**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-136">**Draft state**.</span></span> <span data-ttu-id="feb9d-137">如果管理员想要在 Microsoft 搜索中提供首字母缩略词答案之前查看它们，他们可以将首字母缩写词添加到"草稿"状态。</span><span class="sxs-lookup"><span data-stu-id="feb9d-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="feb9d-138">添加到草稿状态中的首字母缩写词在 Microsoft 搜索中不可用。</span><span class="sxs-lookup"><span data-stu-id="feb9d-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="feb9d-139">管理员需要将缩写词添加到已发布状态，使其可用。</span><span class="sxs-lookup"><span data-stu-id="feb9d-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="feb9d-140">管理员可以单独添加首字母缩写词或在 CSV 文件中批量导入它们。</span><span class="sxs-lookup"><span data-stu-id="feb9d-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="feb9d-141">上载包含下表中所示字段的 CSV 文件：</span><span class="sxs-lookup"><span data-stu-id="feb9d-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="feb9d-142">首字母缩略 (强制) </span><span class="sxs-lookup"><span data-stu-id="feb9d-142">Acronym (mandatory)</span></span> | <span data-ttu-id="feb9d-143">扩展 (强制) </span><span class="sxs-lookup"><span data-stu-id="feb9d-143">Expansion (mandatory)</span></span> | <span data-ttu-id="feb9d-144">说明</span><span class="sxs-lookup"><span data-stu-id="feb9d-144">Description</span></span>  | <span data-ttu-id="feb9d-145">Source</span><span class="sxs-lookup"><span data-stu-id="feb9d-145">Source</span></span> | <span data-ttu-id="feb9d-146">州 (强制) </span><span class="sxs-lookup"><span data-stu-id="feb9d-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="feb9d-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="feb9d-147">*XXX*</span></span> | <span data-ttu-id="feb9d-148">*拼写的缩写*</span><span class="sxs-lookup"><span data-stu-id="feb9d-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="feb9d-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="feb9d-149">*URL*</span></span> | <span data-ttu-id="feb9d-150">*已发布或草稿*</span><span class="sxs-lookup"><span data-stu-id="feb9d-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="feb9d-151">CSV 字段</span><span class="sxs-lookup"><span data-stu-id="feb9d-151">CSV fields</span></span>

<span data-ttu-id="feb9d-152">**首字母缩略词**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-152">**Acronym**.</span></span> <span data-ttu-id="feb9d-153">包含实际的短格式或缩写。</span><span class="sxs-lookup"><span data-stu-id="feb9d-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="feb9d-154">例如 *，DNN*。</span><span class="sxs-lookup"><span data-stu-id="feb9d-154">An example is *DNN*.</span></span>

<span data-ttu-id="feb9d-155">**展开**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-155">**Expansion**.</span></span> <span data-ttu-id="feb9d-156">包含首字母缩略词的扩展。</span><span class="sxs-lookup"><span data-stu-id="feb9d-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="feb9d-157">例如， *深度神经网络*。</span><span class="sxs-lookup"><span data-stu-id="feb9d-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="feb9d-158">**说明**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-158">**Description**.</span></span> <span data-ttu-id="feb9d-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span><span class="sxs-lookup"><span data-stu-id="feb9d-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="feb9d-160">例如， *深度神经网络* 是一个具有一定复杂度的神经网络，一个包含两层以上层的神经网络。</span><span class="sxs-lookup"><span data-stu-id="feb9d-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="feb9d-161">**源**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-161">**Source**.</span></span> <span data-ttu-id="feb9d-162">您希望用户转到的页面或网站的 URL，以了解有关首字母缩写词详细信息。</span><span class="sxs-lookup"><span data-stu-id="feb9d-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="feb9d-163">**状态**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-163">**State**.</span></span> <span data-ttu-id="feb9d-164">此字段可以使用两个值：</span><span class="sxs-lookup"><span data-stu-id="feb9d-164">This field can take two values:</span></span>

- <span data-ttu-id="feb9d-165">**草稿**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-165">**Draft**.</span></span> <span data-ttu-id="feb9d-166">将缩写词添加到"草稿"状态。</span><span class="sxs-lookup"><span data-stu-id="feb9d-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="feb9d-167">**已发布**。</span><span class="sxs-lookup"><span data-stu-id="feb9d-167">**Published**.</span></span> <span data-ttu-id="feb9d-168">将缩写词添加到"已发布"状态，使其在 Microsoft 搜索中可用。</span><span class="sxs-lookup"><span data-stu-id="feb9d-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="feb9d-169">Mined 首字母缩略词</span><span class="sxs-lookup"><span data-stu-id="feb9d-169">Mined acronyms</span></span>

<span data-ttu-id="feb9d-170">对于管理员来说，将组织中使用的所有首字母缩写词添加到"答案"可能是一个挑战。</span><span class="sxs-lookup"><span data-stu-id="feb9d-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="feb9d-171">此功能可以找到搜索管理员甚至不知道的首字母缩略词。</span><span class="sxs-lookup"><span data-stu-id="feb9d-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="feb9d-172">为完成该工作，Microsoft 搜索还从这些源中输入缩写词：</span><span class="sxs-lookup"><span data-stu-id="feb9d-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="feb9d-173">用户的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="feb9d-173">Users’ emails.</span></span>
- <span data-ttu-id="feb9d-174">[SharePoint、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive]( https://onedrive.live.com/about/)和[Microsoft OneNote 中的文档](https://www.onenote.com/)。</span><span class="sxs-lookup"><span data-stu-id="feb9d-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/).</span></span>
- <span data-ttu-id="feb9d-175">用户在 SharePoint、OneDrive 或 OneNote 中有权访问的组织中公共文档。</span><span class="sxs-lookup"><span data-stu-id="feb9d-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="feb9d-176">Microsoft 搜索确保只有具有文档访问权限和权限的用户才能看到从文档获取的缩写词。</span><span class="sxs-lookup"><span data-stu-id="feb9d-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="feb9d-177">从用户的邮箱中缩小首字母缩写词时，只有该用户才能看到该缩写词。</span><span class="sxs-lookup"><span data-stu-id="feb9d-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="feb9d-178">无需为缩写首字母缩略词进行设置。</span><span class="sxs-lookup"><span data-stu-id="feb9d-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="feb9d-179">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="feb9d-179">Frequently asked questions</span></span>

<span data-ttu-id="feb9d-180">**问：如何对编辑和缩小数据进行排名？**</span><span class="sxs-lookup"><span data-stu-id="feb9d-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="feb9d-181">**答：** 结果的排名可能因人而异，因为结果针对每个用户进行个性化设置。</span><span class="sxs-lookup"><span data-stu-id="feb9d-181">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span>

<span data-ttu-id="feb9d-182">**问：编辑首字母缩写词在 Microsoft 搜索中发布后需要多久才能显示？**</span><span class="sxs-lookup"><span data-stu-id="feb9d-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="feb9d-183">**答：**  添加到"已发布"状态首字母缩写词在 Microsoft 搜索中最多需要三天的时间。</span><span class="sxs-lookup"><span data-stu-id="feb9d-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="feb9d-184">**问：用户如何触发首字母缩略词答案？**</span><span class="sxs-lookup"><span data-stu-id="feb9d-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="feb9d-185">**答**：若要获取首字母缩写词答案，用户必须在 [必应](https://bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)或 [Office 365 搜索](https://Office.com)框中输入特定 **查询** 模式。</span><span class="sxs-lookup"><span data-stu-id="feb9d-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="feb9d-186">**问：接收或发送新电子邮件或文档后，显示缩略词需要多久？**</span><span class="sxs-lookup"><span data-stu-id="feb9d-186">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="feb9d-187">**答：** 来自新电子邮件或文档的缩写缩写词最多需要 7 天时间显示在 Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="feb9d-187">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="feb9d-188">**问：文档是否需要采用特定格式进行挖掘以选取它们？**</span><span class="sxs-lookup"><span data-stu-id="feb9d-188">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="feb9d-189">**答：** 不。</span><span class="sxs-lookup"><span data-stu-id="feb9d-189">**A:** No.</span></span> <span data-ttu-id="feb9d-190">支持除图像、文件夹和 zip 文件之外的所有文件类型。</span><span class="sxs-lookup"><span data-stu-id="feb9d-190">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="feb9d-191">**问：Microsoft 会从所有语言的文档中挖掘首字母缩写词吗？**</span><span class="sxs-lookup"><span data-stu-id="feb9d-191">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="feb9d-192">**答**：Microsoft 仅支持从英语文档进行挖掘。</span><span class="sxs-lookup"><span data-stu-id="feb9d-192">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="feb9d-193">将分阶段添加对其他语言的支持。</span><span class="sxs-lookup"><span data-stu-id="feb9d-193">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="feb9d-194">**问：如果我的组织不想显示缩略词，该做什么？我能否停止在搜索结果中显示缩略词？**</span><span class="sxs-lookup"><span data-stu-id="feb9d-194">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="feb9d-195">**答**：若要在搜索结果中关闭显示缩略缩略词，请按照有关业务产品的联系人支持人员的说明创建 [客户支持票证](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)。</span><span class="sxs-lookup"><span data-stu-id="feb9d-195">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="feb9d-196">创建支持票证后，最多需要 48 小时才能在搜索结果中停止显示缩略词。</span><span class="sxs-lookup"><span data-stu-id="feb9d-196">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>
