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
ms.openlocfilehash: 45d3cc7b33f27d2f4e77d8099fbfa91e01aabcbb
ms.sourcegitcommit: ef94ffd6111acb929c8343f0f4f82ea109b68fb6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122153"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="31586-103">在 Microsoft 搜索中管理首字母缩写词答案</span><span class="sxs-lookup"><span data-stu-id="31586-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="31586-104">用户经常遇到其组织或团队使用的不熟悉的缩写词和缩写。</span><span class="sxs-lookup"><span data-stu-id="31586-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="31586-105">对于从一个团队移动到另一个团队、与内部合作伙伴团队合作或对组织而言是新术语的人，特定于组织或团队的术语可能是新的。</span><span class="sxs-lookup"><span data-stu-id="31586-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="31586-106">组织并不总是有一个标准术语参考。</span><span class="sxs-lookup"><span data-stu-id="31586-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="31586-107">缺少单一引用使查找这些首字母缩写词的定义或扩展变得困难。</span><span class="sxs-lookup"><span data-stu-id="31586-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="31586-108">Microsoft 搜索使用首字母缩略词解决了此问题。</span><span class="sxs-lookup"><span data-stu-id="31586-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="31586-109">用户体验</span><span class="sxs-lookup"><span data-stu-id="31586-109">What users experience</span></span>

<span data-ttu-id="31586-110">Microsoft 搜索用户可以使用[必应](https://Bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)和[Office 365](https://Office.com)中的首字母缩略词获取定义。</span><span class="sxs-lookup"><span data-stu-id="31586-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="31586-111">在 **"搜索** "框中，用户输入类似以下示例的查询：</span><span class="sxs-lookup"><span data-stu-id="31586-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="31586-112">*什么是* DNN</span><span class="sxs-lookup"><span data-stu-id="31586-112">*What is* DNN</span></span>
- <span data-ttu-id="31586-113">*定义* DNN</span><span class="sxs-lookup"><span data-stu-id="31586-113">*Define* DNN</span></span>
- <span data-ttu-id="31586-114">DNN *定义*</span><span class="sxs-lookup"><span data-stu-id="31586-114">DNN *definition*</span></span>
- <span data-ttu-id="31586-115">*展开* DNN</span><span class="sxs-lookup"><span data-stu-id="31586-115">*Expand* DNN</span></span>
- <span data-ttu-id="31586-116">DNN *扩展*</span><span class="sxs-lookup"><span data-stu-id="31586-116">DNN *expansion*</span></span>
- <span data-ttu-id="31586-117">*含义* DNN</span><span class="sxs-lookup"><span data-stu-id="31586-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="31586-118">DNN *表示*</span><span class="sxs-lookup"><span data-stu-id="31586-118">DNN *means*</span></span>

<span data-ttu-id="31586-119">结果包括存在于用户组织内部的 DNN 的所有含义。</span><span class="sxs-lookup"><span data-stu-id="31586-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="31586-120">用户必须输入包含首字母缩写词指定关键字的查询，才能触发其对应的答案。</span><span class="sxs-lookup"><span data-stu-id="31586-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="31586-121">首字母缩略词查询不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="31586-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="31586-122">设置首字母缩写词答案</span><span class="sxs-lookup"><span data-stu-id="31586-122">Set up acronyms answers</span></span>

<span data-ttu-id="31586-123">在 [Microsoft 365 管理中心](https://admin.microsoft.com)中，转到 [**首字母**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)缩略词，然后选择"添加 **首字母缩写词"。**</span><span class="sxs-lookup"><span data-stu-id="31586-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="31586-124">Microsoft 搜索查询两个数据源，以提供用户搜索的首字母缩略词解答：</span><span class="sxs-lookup"><span data-stu-id="31586-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="31586-125">**Admin-curated**.</span><span class="sxs-lookup"><span data-stu-id="31586-125">**Admin-curated**.</span></span> <span data-ttu-id="31586-126">由管理中心中的 IT [管理员提供](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)。</span><span class="sxs-lookup"><span data-stu-id="31586-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="31586-127">**系统所设计**。</span><span class="sxs-lookup"><span data-stu-id="31586-127">**System-curated**.</span></span> <span data-ttu-id="31586-128">Microsoft 搜索从用户的电子邮件和文档以及组织中公开的数据中发现。</span><span class="sxs-lookup"><span data-stu-id="31586-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="31586-129">设置 Admin-curated 首字母缩略词</span><span class="sxs-lookup"><span data-stu-id="31586-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="31586-130">搜索管理员可以在 Microsoft 搜索管理中心的首字母缩写[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)词[选项卡上添加首字母缩写词](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。</span><span class="sxs-lookup"><span data-stu-id="31586-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="31586-131">可以将任何内部站点或存储库中的首字母缩写词添加到管理中心。</span><span class="sxs-lookup"><span data-stu-id="31586-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="31586-132">可以将这些缩写词添加到"已发布" **或** " **草稿"** 状态：</span><span class="sxs-lookup"><span data-stu-id="31586-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="31586-133">**已发布状态**。</span><span class="sxs-lookup"><span data-stu-id="31586-133">**Published state**.</span></span> <span data-ttu-id="31586-134">通过 Microsoft 搜索，组织用户可以使用首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="31586-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="31586-135">添加到已发布状态首字母缩略词在 Microsoft 搜索中可能最多需要三天。</span><span class="sxs-lookup"><span data-stu-id="31586-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="31586-136">**草稿状态**。</span><span class="sxs-lookup"><span data-stu-id="31586-136">**Draft state**.</span></span> <span data-ttu-id="31586-137">如果要在 Microsoft 搜索中提供首字母缩略词之前查看该缩写词，可以添加草稿状态中的首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="31586-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="31586-138">"草稿"状态中的首字母缩略词不会显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="31586-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="31586-139">您需要将缩写词移动到"已发布"状态，使其显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="31586-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="31586-140">可以单独添加首字母缩写词，也可以将其批量导入 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="31586-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="31586-141">上载包含下表中所示字段的 CSV 文件：</span><span class="sxs-lookup"><span data-stu-id="31586-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="31586-142">首字母缩写词 (强制) </span><span class="sxs-lookup"><span data-stu-id="31586-142">Acronym (Mandatory)</span></span> | <span data-ttu-id="31586-143">扩展 (强制) </span><span class="sxs-lookup"><span data-stu-id="31586-143">Expansion (Mandatory)</span></span> | <span data-ttu-id="31586-144">URL</span><span class="sxs-lookup"><span data-stu-id="31586-144">Url</span></span> | <span data-ttu-id="31586-145">说明</span><span class="sxs-lookup"><span data-stu-id="31586-145">Description</span></span>  | <span data-ttu-id="31586-146">State (Mandatory) </span><span class="sxs-lookup"><span data-stu-id="31586-146">State (Mandatory)</span></span> | <span data-ttu-id="31586-147">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="31586-147">Last Modified</span></span> | <span data-ttu-id="31586-148">上次修改者</span><span class="sxs-lookup"><span data-stu-id="31586-148">Last Modified By</span></span> | <span data-ttu-id="31586-149">Id</span><span class="sxs-lookup"><span data-stu-id="31586-149">Id</span></span> |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| <span data-ttu-id="31586-150">*XXX*</span><span class="sxs-lookup"><span data-stu-id="31586-150">*XXX*</span></span> | <span data-ttu-id="31586-151">*拼写的缩写*</span><span class="sxs-lookup"><span data-stu-id="31586-151">*Spelled out abbreviation*</span></span> | <span data-ttu-id="31586-152">*Source*</span><span class="sxs-lookup"><span data-stu-id="31586-152">*Source*</span></span> |  | <span data-ttu-id="31586-153">*已发布或草稿*</span><span class="sxs-lookup"><span data-stu-id="31586-153">*Published or Draft*</span></span> |  |  |  |

### <a name="csv-fields"></a><span data-ttu-id="31586-154">CSV 字段</span><span class="sxs-lookup"><span data-stu-id="31586-154">CSV fields</span></span>

<span data-ttu-id="31586-155">**首字母缩略词**。</span><span class="sxs-lookup"><span data-stu-id="31586-155">**Acronym**.</span></span> <span data-ttu-id="31586-156">包含实际的短格式或首字母缩写。</span><span class="sxs-lookup"><span data-stu-id="31586-156">Contains the actual short form or acronym.</span></span> <span data-ttu-id="31586-157">例如 *，DNN*。</span><span class="sxs-lookup"><span data-stu-id="31586-157">An example is *DNN*.</span></span>

<span data-ttu-id="31586-158">**展开**。</span><span class="sxs-lookup"><span data-stu-id="31586-158">**Expansion**.</span></span> <span data-ttu-id="31586-159">包含首字母缩略词的扩展。</span><span class="sxs-lookup"><span data-stu-id="31586-159">Contains the expansion of the acronym.</span></span> <span data-ttu-id="31586-160">例如， *深度神经网络*。</span><span class="sxs-lookup"><span data-stu-id="31586-160">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="31586-161">**说明**。</span><span class="sxs-lookup"><span data-stu-id="31586-161">**Description**.</span></span> <span data-ttu-id="31586-162">A brief description of the acronym that gives users more info about the acronym and its expansion.</span><span class="sxs-lookup"><span data-stu-id="31586-162">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="31586-163">例如， *深度神经网络* 是一个具有一定复杂度的神经网络，一个包含两层以上层的神经网络。</span><span class="sxs-lookup"><span data-stu-id="31586-163">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="31586-164">**源**。</span><span class="sxs-lookup"><span data-stu-id="31586-164">**Source**.</span></span> <span data-ttu-id="31586-165">您希望用户转到的页面或网站的 URL，以了解有关首字母缩写词详细信息。</span><span class="sxs-lookup"><span data-stu-id="31586-165">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="31586-166">**状态**。</span><span class="sxs-lookup"><span data-stu-id="31586-166">**State**.</span></span> <span data-ttu-id="31586-167">此字段可以使用两个值：</span><span class="sxs-lookup"><span data-stu-id="31586-167">This field can take two values:</span></span>

- <span data-ttu-id="31586-168">**草稿**。</span><span class="sxs-lookup"><span data-stu-id="31586-168">**Draft**.</span></span> <span data-ttu-id="31586-169">将缩写词添加到"草稿"状态。</span><span class="sxs-lookup"><span data-stu-id="31586-169">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="31586-170">**已发布**。</span><span class="sxs-lookup"><span data-stu-id="31586-170">**Published**.</span></span> <span data-ttu-id="31586-171">将缩写词添加到"已发布"状态，使其在 Microsoft 搜索中可用。</span><span class="sxs-lookup"><span data-stu-id="31586-171">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="31586-172">系统库缩略词</span><span class="sxs-lookup"><span data-stu-id="31586-172">System-curated acronyms</span></span>

<span data-ttu-id="31586-173">对于管理员来说，将组织中使用的所有首字母缩写词添加到"答案"可能是一个挑战。</span><span class="sxs-lookup"><span data-stu-id="31586-173">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="31586-174">此功能可以找到搜索管理员甚至不知道的首字母缩略词。</span><span class="sxs-lookup"><span data-stu-id="31586-174">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="31586-175">为完成这一工作，Microsoft 搜索还发现并特地从这些源中提供首字母缩略词：</span><span class="sxs-lookup"><span data-stu-id="31586-175">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="31586-176">用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="31586-176">Users’ emails</span></span>
- <span data-ttu-id="31586-177">[SharePoint、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive]( https://onedrive.live.com/about/)和[Microsoft OneNote 中的文档](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="31586-177">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="31586-178">用户在 SharePoint、OneDrive 或 OneNote 中有权访问的组织中公共文档</span><span class="sxs-lookup"><span data-stu-id="31586-178">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="31586-179">Microsoft 搜索确保只有具有文档访问权限和权限的用户才能看到从文档发现的缩写词。</span><span class="sxs-lookup"><span data-stu-id="31586-179">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="31586-180">在用户的邮箱中发现首字母缩写词时，只有该用户才能看到该缩写词。</span><span class="sxs-lookup"><span data-stu-id="31586-180">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="31586-181">无需为管理员设置的首字母缩略词进行设置。</span><span class="sxs-lookup"><span data-stu-id="31586-181">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="31586-182">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="31586-182">Frequently asked questions</span></span>

<span data-ttu-id="31586-183">**问：如何对管理员和系统选择的数据进行排名？**</span><span class="sxs-lookup"><span data-stu-id="31586-183">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="31586-184">**答：** 结果的排名可能因人而异，因为结果针对每个用户进行个性化设置。</span><span class="sxs-lookup"><span data-stu-id="31586-184">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="31586-185">这两个类别都不始终优先于其他类别。</span><span class="sxs-lookup"><span data-stu-id="31586-185">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="31586-186">**问：管理员编辑的首字母缩略词在 Microsoft 搜索中发布后需要多久才能显示？**</span><span class="sxs-lookup"><span data-stu-id="31586-186">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="31586-187">**答：**  添加到已发布状态首字母缩略词在 Microsoft 搜索中可用最多需要三天。</span><span class="sxs-lookup"><span data-stu-id="31586-187">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="31586-188">**问：用户如何触发首字母缩写词答案？**</span><span class="sxs-lookup"><span data-stu-id="31586-188">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="31586-189">**答**：若要获取首字母缩写词答案，用户必须在 [必应](https://bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)或 [Office 365](https://Office.com)搜索框中输入特定的 **查询** 模式。</span><span class="sxs-lookup"><span data-stu-id="31586-189">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="31586-190">**问：接收或发送新电子邮件或文档后，系统选择缩写词需要多久显示？**</span><span class="sxs-lookup"><span data-stu-id="31586-190">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="31586-191">**答：** 新电子邮件或文档中的首字母缩略词最多需要 7 天时间显示在 Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="31586-191">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="31586-192">**问：文档是否需要采用特定格式进行挖掘以选取它们？**</span><span class="sxs-lookup"><span data-stu-id="31586-192">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="31586-193">**答：** 不。</span><span class="sxs-lookup"><span data-stu-id="31586-193">**A:** No.</span></span> <span data-ttu-id="31586-194">支持除图像、文件夹和 zip 文件之外的所有文件类型。</span><span class="sxs-lookup"><span data-stu-id="31586-194">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="31586-195">**问：Microsoft 会从所有语言的文档中发现首字母缩略词吗？**</span><span class="sxs-lookup"><span data-stu-id="31586-195">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="31586-196">**答**：Microsoft 仅支持从英语文档进行挖掘。</span><span class="sxs-lookup"><span data-stu-id="31586-196">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="31586-197">将分阶段添加对其他语言的支持。</span><span class="sxs-lookup"><span data-stu-id="31586-197">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="31586-198">**问：如果我的组织不想显示系统特有首字母缩略词，该做什么？能否在搜索结果中停止显示此类型的首字母缩写词？**</span><span class="sxs-lookup"><span data-stu-id="31586-198">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="31586-199">**答**：若要在搜索结果中关闭显示系统创建的首字母缩略词，请按照联系商业产品支持人员中的说明创建 [客户支持票证](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="31586-199">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products).</span></span>
<span data-ttu-id="31586-200">创建支持票证后，系统创建的首字母缩略词最多需要 48 小时才能停止显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="31586-200">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
