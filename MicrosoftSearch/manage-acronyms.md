---
title: 在 Microsoft 搜索中管理首字母缩写词答案
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 在 Microsoft 搜索中创建和更新首字母缩写词答案
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728003"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="d285a-103">在 Microsoft 搜索中管理首字母缩写词答案</span><span class="sxs-lookup"><span data-stu-id="d285a-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="d285a-104">用户经常遇到其组织或团队使用的不熟悉的缩写词和缩写。</span><span class="sxs-lookup"><span data-stu-id="d285a-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="d285a-105">对于从一个团队移动到另一个团队、与内部合作伙伴团队合作或对组织而言是新术语的人，特定于组织或团队的术语可能是新的。</span><span class="sxs-lookup"><span data-stu-id="d285a-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="d285a-106">组织并不总是有一个标准术语参考。</span><span class="sxs-lookup"><span data-stu-id="d285a-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="d285a-107">缺少单一引用使查找这些首字母缩写词的定义或扩展变得困难。</span><span class="sxs-lookup"><span data-stu-id="d285a-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="d285a-108">Microsoft 搜索使用首字母缩略词解决了此问题。</span><span class="sxs-lookup"><span data-stu-id="d285a-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="d285a-109">用户体验</span><span class="sxs-lookup"><span data-stu-id="d285a-109">What users experience</span></span>

<span data-ttu-id="d285a-110">Microsoft 搜索用户可以使用[必应](https://Bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)和[Office 365](https://Office.com)中的首字母缩略词获取定义。</span><span class="sxs-lookup"><span data-stu-id="d285a-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="d285a-111">在 **"搜索** "框中，用户输入类似以下示例的查询：</span><span class="sxs-lookup"><span data-stu-id="d285a-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="d285a-112">*什么是* DNN</span><span class="sxs-lookup"><span data-stu-id="d285a-112">*What is* DNN</span></span>
- <span data-ttu-id="d285a-113">*定义* DNN</span><span class="sxs-lookup"><span data-stu-id="d285a-113">*Define* DNN</span></span>
- <span data-ttu-id="d285a-114">DNN *定义*</span><span class="sxs-lookup"><span data-stu-id="d285a-114">DNN *definition*</span></span>
- <span data-ttu-id="d285a-115">*展开* DNN</span><span class="sxs-lookup"><span data-stu-id="d285a-115">*Expand* DNN</span></span>
- <span data-ttu-id="d285a-116">DNN *扩展*</span><span class="sxs-lookup"><span data-stu-id="d285a-116">DNN *expansion*</span></span>
- <span data-ttu-id="d285a-117">*含义* DNN</span><span class="sxs-lookup"><span data-stu-id="d285a-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="d285a-118">DNN *表示*</span><span class="sxs-lookup"><span data-stu-id="d285a-118">DNN *means*</span></span>

<span data-ttu-id="d285a-119">结果包括存在于用户组织内部的 DNN 的所有含义。</span><span class="sxs-lookup"><span data-stu-id="d285a-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="d285a-120">用户必须输入包含首字母缩写词指定关键字的查询，才能触发其对应的答案。</span><span class="sxs-lookup"><span data-stu-id="d285a-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="d285a-121">首字母缩略词查询不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d285a-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="d285a-122">设置首字母缩写词答案</span><span class="sxs-lookup"><span data-stu-id="d285a-122">Set up acronyms answers</span></span>

<span data-ttu-id="d285a-123">在 [Microsoft 365 管理中心](https://admin.microsoft.com)中，转到 [**首字母**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)缩略词，然后选择"添加 **首字母缩写词"。**</span><span class="sxs-lookup"><span data-stu-id="d285a-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="d285a-124">Microsoft 搜索查询两个数据源，以提供用户搜索的首字母缩略词解答：</span><span class="sxs-lookup"><span data-stu-id="d285a-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="d285a-125">**Admin-curated**.</span><span class="sxs-lookup"><span data-stu-id="d285a-125">**Admin-curated**.</span></span> <span data-ttu-id="d285a-126">由管理中心中的 IT [管理员提供](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)。</span><span class="sxs-lookup"><span data-stu-id="d285a-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="d285a-127">**系统所设计**。</span><span class="sxs-lookup"><span data-stu-id="d285a-127">**System-curated**.</span></span> <span data-ttu-id="d285a-128">Microsoft 搜索从用户的电子邮件和文档以及组织中公开的数据中发现。</span><span class="sxs-lookup"><span data-stu-id="d285a-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="d285a-129">设置 Admin-curated 首字母缩略词</span><span class="sxs-lookup"><span data-stu-id="d285a-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="d285a-130">搜索管理员可以在 Microsoft 搜索管理中心的首字母缩写[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)词[选项卡上添加首字母缩写词](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。</span><span class="sxs-lookup"><span data-stu-id="d285a-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="d285a-131">可以将任何内部站点或存储库中的首字母缩写词添加到管理中心。</span><span class="sxs-lookup"><span data-stu-id="d285a-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="d285a-132">可以将这些缩写词添加到"已发布" **或** " **草稿"** 状态：</span><span class="sxs-lookup"><span data-stu-id="d285a-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="d285a-133">**已发布状态**。</span><span class="sxs-lookup"><span data-stu-id="d285a-133">**Published state**.</span></span> <span data-ttu-id="d285a-134">通过 Microsoft 搜索，组织用户可以使用首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="d285a-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="d285a-135">添加到已发布状态首字母缩略词在 Microsoft 搜索中可能最多需要三天。</span><span class="sxs-lookup"><span data-stu-id="d285a-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="d285a-136">**草稿状态**。</span><span class="sxs-lookup"><span data-stu-id="d285a-136">**Draft state**.</span></span> <span data-ttu-id="d285a-137">如果要在 Microsoft 搜索中提供首字母缩略词之前查看该缩写词，可以添加草稿状态中的首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="d285a-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="d285a-138">"草稿"状态中的首字母缩略词不会显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="d285a-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="d285a-139">您需要将缩写词移动到"已发布"状态，使其显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="d285a-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="d285a-140">可以单独添加首字母缩写词，也可以将其批量导入 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="d285a-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="d285a-141">上传包含下表中所示字段的 CSV 文件：</span><span class="sxs-lookup"><span data-stu-id="d285a-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="d285a-142">首字母缩略 (强制) </span><span class="sxs-lookup"><span data-stu-id="d285a-142">Acronym (mandatory)</span></span> | <span data-ttu-id="d285a-143">扩展 (强制) </span><span class="sxs-lookup"><span data-stu-id="d285a-143">Expansion (mandatory)</span></span> | <span data-ttu-id="d285a-144">说明</span><span class="sxs-lookup"><span data-stu-id="d285a-144">Description</span></span>  | <span data-ttu-id="d285a-145">Source</span><span class="sxs-lookup"><span data-stu-id="d285a-145">Source</span></span> | <span data-ttu-id="d285a-146">州 (强制) </span><span class="sxs-lookup"><span data-stu-id="d285a-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="d285a-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="d285a-147">*XXX*</span></span> | <span data-ttu-id="d285a-148">*拼写的缩写*</span><span class="sxs-lookup"><span data-stu-id="d285a-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="d285a-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="d285a-149">*URL*</span></span> | <span data-ttu-id="d285a-150">*已发布或草稿*</span><span class="sxs-lookup"><span data-stu-id="d285a-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="d285a-151">CSV 字段</span><span class="sxs-lookup"><span data-stu-id="d285a-151">CSV fields</span></span>

<span data-ttu-id="d285a-152">**首字母缩略词**。</span><span class="sxs-lookup"><span data-stu-id="d285a-152">**Acronym**.</span></span> <span data-ttu-id="d285a-153">包含实际的短格式或缩写。</span><span class="sxs-lookup"><span data-stu-id="d285a-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="d285a-154">例如 *，DNN*。</span><span class="sxs-lookup"><span data-stu-id="d285a-154">An example is *DNN*.</span></span>

<span data-ttu-id="d285a-155">**展开**。</span><span class="sxs-lookup"><span data-stu-id="d285a-155">**Expansion**.</span></span> <span data-ttu-id="d285a-156">包含首字母缩略词的扩展。</span><span class="sxs-lookup"><span data-stu-id="d285a-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="d285a-157">例如， *深度神经网络*。</span><span class="sxs-lookup"><span data-stu-id="d285a-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="d285a-158">**说明**。</span><span class="sxs-lookup"><span data-stu-id="d285a-158">**Description**.</span></span> <span data-ttu-id="d285a-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span><span class="sxs-lookup"><span data-stu-id="d285a-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="d285a-160">例如， *深度神经网络* 是一个具有一定复杂度的神经网络，一个包含两层以上层的神经网络。</span><span class="sxs-lookup"><span data-stu-id="d285a-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="d285a-161">**源**。</span><span class="sxs-lookup"><span data-stu-id="d285a-161">**Source**.</span></span> <span data-ttu-id="d285a-162">您希望用户转到的页面或网站的 URL，以了解有关首字母缩写词详细信息。</span><span class="sxs-lookup"><span data-stu-id="d285a-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="d285a-163">**状态**。</span><span class="sxs-lookup"><span data-stu-id="d285a-163">**State**.</span></span> <span data-ttu-id="d285a-164">此字段可以使用两个值：</span><span class="sxs-lookup"><span data-stu-id="d285a-164">This field can take two values:</span></span>

- <span data-ttu-id="d285a-165">**草稿**。</span><span class="sxs-lookup"><span data-stu-id="d285a-165">**Draft**.</span></span> <span data-ttu-id="d285a-166">将缩写词添加到"草稿"状态。</span><span class="sxs-lookup"><span data-stu-id="d285a-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="d285a-167">**已发布**。</span><span class="sxs-lookup"><span data-stu-id="d285a-167">**Published**.</span></span> <span data-ttu-id="d285a-168">将缩写词添加到"已发布"状态，使其在 Microsoft 搜索中可用。</span><span class="sxs-lookup"><span data-stu-id="d285a-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="d285a-169">系统库缩略词</span><span class="sxs-lookup"><span data-stu-id="d285a-169">System-curated acronyms</span></span>

<span data-ttu-id="d285a-170">对于管理员来说，将组织中使用的所有首字母缩写词添加到"答案"可能是一个挑战。</span><span class="sxs-lookup"><span data-stu-id="d285a-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="d285a-171">此功能可以找到搜索管理员甚至不知道的首字母缩略词。</span><span class="sxs-lookup"><span data-stu-id="d285a-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="d285a-172">为完成这一工作，Microsoft 搜索还发现并组织这些源中的首字母缩写词：</span><span class="sxs-lookup"><span data-stu-id="d285a-172">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="d285a-173">用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="d285a-173">Users’ emails</span></span>
- <span data-ttu-id="d285a-174">[SharePoint、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive]( https://onedrive.live.com/about/)和[Microsoft OneNote 中的文档](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="d285a-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="d285a-175">用户在 SharePoint、OneDrive 或 OneNote 中有权访问的组织中公共文档</span><span class="sxs-lookup"><span data-stu-id="d285a-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="d285a-176">Microsoft 搜索确保只有具有文档访问权限和权限的用户才能看到从文档发现的缩写词。</span><span class="sxs-lookup"><span data-stu-id="d285a-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="d285a-177">在用户的邮箱中发现首字母缩写词时，只有该用户才能看到该缩写词。</span><span class="sxs-lookup"><span data-stu-id="d285a-177">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="d285a-178">无需为管理员设置的首字母缩略词进行设置。</span><span class="sxs-lookup"><span data-stu-id="d285a-178">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d285a-179">常见问题</span><span class="sxs-lookup"><span data-stu-id="d285a-179">Frequently asked questions</span></span>

<span data-ttu-id="d285a-180">**问：如何对管理员选择和系统选择的数据进行排名？**</span><span class="sxs-lookup"><span data-stu-id="d285a-180">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="d285a-181">**答：** 结果的排名可能因人而异，因为结果针对每个用户进行个性化设置。</span><span class="sxs-lookup"><span data-stu-id="d285a-181">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="d285a-182">这两个类别都不始终优先于其他类别。</span><span class="sxs-lookup"><span data-stu-id="d285a-182">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="d285a-183">**问：管理员编辑的首字母缩略词在 Microsoft 搜索中发布后需要多久才能显示？**</span><span class="sxs-lookup"><span data-stu-id="d285a-183">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="d285a-184">**答：**  添加到已发布状态首字母缩略词在 Microsoft 搜索中可用最多需要三天。</span><span class="sxs-lookup"><span data-stu-id="d285a-184">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="d285a-185">**问：用户如何触发首字母缩写词答案？**</span><span class="sxs-lookup"><span data-stu-id="d285a-185">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="d285a-186">**答**：若要获取首字母缩写词答案，用户必须在 [必应](https://bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)或 [Office 365](https://Office.com)搜索框中输入特定的 **查询** 模式。</span><span class="sxs-lookup"><span data-stu-id="d285a-186">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="d285a-187">**问：接收或发送新电子邮件或文档后，系统选择缩写词需要多久显示？**</span><span class="sxs-lookup"><span data-stu-id="d285a-187">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="d285a-188">**答：** 新电子邮件或文档中的首字母缩略词最多需要 7 天时间显示在 Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="d285a-188">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="d285a-189">**问：文档是否需要采用特定格式进行挖掘以选取它们？**</span><span class="sxs-lookup"><span data-stu-id="d285a-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="d285a-190">**答：** 不。</span><span class="sxs-lookup"><span data-stu-id="d285a-190">**A:** No.</span></span> <span data-ttu-id="d285a-191">支持除图像、文件夹和 zip 文件之外的所有文件类型。</span><span class="sxs-lookup"><span data-stu-id="d285a-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="d285a-192">**问：Microsoft 会从所有语言的文档中发现首字母缩略词吗？**</span><span class="sxs-lookup"><span data-stu-id="d285a-192">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="d285a-193">**答**：Microsoft 仅支持从英语文档进行挖掘。</span><span class="sxs-lookup"><span data-stu-id="d285a-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="d285a-194">将分阶段添加对其他语言的支持。</span><span class="sxs-lookup"><span data-stu-id="d285a-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="d285a-195">**问：如果我的组织不想显示系统特有首字母缩略词，该做什么？能否在搜索结果中停止显示此类型的首字母缩写词？**</span><span class="sxs-lookup"><span data-stu-id="d285a-195">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="d285a-196">**答**：若要在搜索结果中关闭显示系统创建的首字母缩略词，请按照联系商业产品支持人员中的说明创建 [客户支持票证](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)。</span><span class="sxs-lookup"><span data-stu-id="d285a-196">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="d285a-197">创建支持票证后，系统创建的首字母缩略词最多需要 48 小时才能停止显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="d285a-197">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
