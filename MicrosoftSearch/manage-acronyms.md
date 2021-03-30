---
title: 在 Microsoft 搜索中管理首字母缩略词答案
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
description: 在 Microsoft 搜索中创建和更新首字母缩略词答案
ms.openlocfilehash: 013510da28599f41c9dc4bf74da99efa2f6c3e97
ms.sourcegitcommit: 62cb7b8c6a311760cc728f2c70a9a22ca76e977e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408711"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="a6c4d-103">在 Microsoft 搜索中管理首字母缩略词答案</span><span class="sxs-lookup"><span data-stu-id="a6c4d-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="a6c4d-104">用户经常遇到他们组织或团队使用的不熟悉的缩写词和缩写。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="a6c4d-105">对于从一个团队移动到另一个团队、与内部合作伙伴团队合作或对组织而言是新人，特定于组织或团队的术语可能是新术语。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="a6c4d-106">组织并不总是有一个有关其标准术语的参考。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="a6c4d-107">缺少单一引用使查找这些首字母缩写词的定义变得困难。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-107">Lack of a single reference makes it hard to find definitions for these acronyms.</span></span> <span data-ttu-id="a6c4d-108">Microsoft 搜索使用首字母缩略词解决了此问题。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="a6c4d-109">用户体验</span><span class="sxs-lookup"><span data-stu-id="a6c4d-109">What users experience</span></span>

<span data-ttu-id="a6c4d-110">Microsoft 搜索用户可以使用[必应](https://Bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)和[Office 365](https://Office.com)中的首字母缩略词获取定义。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="a6c4d-111">在 **"搜索** "框中，用户输入类似以下示例的查询：</span><span class="sxs-lookup"><span data-stu-id="a6c4d-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="a6c4d-112">*什么是* DNN</span><span class="sxs-lookup"><span data-stu-id="a6c4d-112">*What is* DNN</span></span>
- <span data-ttu-id="a6c4d-113">*定义* DNN</span><span class="sxs-lookup"><span data-stu-id="a6c4d-113">*Define* DNN</span></span>
- <span data-ttu-id="a6c4d-114">DNN *定义*</span><span class="sxs-lookup"><span data-stu-id="a6c4d-114">DNN *definition*</span></span>
- <span data-ttu-id="a6c4d-115">*展开* DNN</span><span class="sxs-lookup"><span data-stu-id="a6c4d-115">*Expand* DNN</span></span>
- <span data-ttu-id="a6c4d-116">DNN *扩展*</span><span class="sxs-lookup"><span data-stu-id="a6c4d-116">DNN *expansion*</span></span>
- <span data-ttu-id="a6c4d-117">*的含义* DNN</span><span class="sxs-lookup"><span data-stu-id="a6c4d-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="a6c4d-118">DNN *表示*</span><span class="sxs-lookup"><span data-stu-id="a6c4d-118">DNN *means*</span></span>
- <span data-ttu-id="a6c4d-119">DNN *代表*</span><span class="sxs-lookup"><span data-stu-id="a6c4d-119">DNN *stands for*</span></span>

<span data-ttu-id="a6c4d-120">结果包括存在于用户组织内部的 DNN 的所有含义。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-120">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="a6c4d-121">用户必须输入包含首字母缩写词的指定关键字的查询，才能触发其对应的答案。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-121">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="a6c4d-122">首字母缩略词查询不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-122">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="a6c4d-123">设置首字母缩写词答案</span><span class="sxs-lookup"><span data-stu-id="a6c4d-123">Set up acronyms answers</span></span>

<span data-ttu-id="a6c4d-124">在 [Microsoft 365 管理](https://admin.microsoft.com)中心中，转到"[**首字母缩写**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)词"，然后选择"**添加首字母缩写词"。**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="a6c4d-125">Microsoft 搜索查询两个数据源，以提供用户搜索的首字母缩略词答案：</span><span class="sxs-lookup"><span data-stu-id="a6c4d-125">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="a6c4d-126">**管理员所策展**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-126">**Admin-curated**.</span></span> <span data-ttu-id="a6c4d-127">由管理中心中的 IT [管理员提供](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-127">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="a6c4d-128">**System-curated**.</span><span class="sxs-lookup"><span data-stu-id="a6c4d-128">**System-curated**.</span></span> <span data-ttu-id="a6c4d-129">由 Microsoft 搜索从用户的电子邮件和文档以及组织中公开可用的数据中发现。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-129">Discovered by Microsoft Search from users' email and documents, as well as publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="a6c4d-130">设置管理员策展的首字母缩写词</span><span class="sxs-lookup"><span data-stu-id="a6c4d-130">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="a6c4d-131">搜索管理员可以在 Microsoft 搜索管理中心的" [首字母缩写词"选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) 上  [添加首字母缩写词](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-131">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="a6c4d-132">可以将任何内部站点或存储库中的首字母缩写词添加到管理中心。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-132">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="a6c4d-133">这些首字母缩写词可以添加到 **已发布或\*\*\*\*草稿** 状态：</span><span class="sxs-lookup"><span data-stu-id="a6c4d-133">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="a6c4d-134">**已发布状态**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-134">**Published state**.</span></span> <span data-ttu-id="a6c4d-135">组织用户可以通过 Microsoft 搜索使用缩写词。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-135">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="a6c4d-136">添加到"已发布"状态首字母缩写词可能需要三天时间，Microsoft 搜索中将可用。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-136">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="a6c4d-137">**草稿状态**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-137">**Draft state**.</span></span> <span data-ttu-id="a6c4d-138">如果要在 Microsoft 搜索中提供首字母缩写词之前查看该缩写词，可以在"草稿"状态中添加缩写词。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-138">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="a6c4d-139">"草稿"状态中的缩写词不会显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-139">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="a6c4d-140">您需要将缩写词移动到"已发布"状态，使其出现在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-140">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="a6c4d-141">**已排除状态**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-141">**Excluded state**.</span></span> <span data-ttu-id="a6c4d-142">如果要阻止在 Microsoft 搜索中显示首字母缩写词，请使用"排除首字母缩写 **词"进行** 添加。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-142">If you want to prevent an acronym from appearing in Microsoft Search, use **Exclude an acronym** to add it.</span></span> <span data-ttu-id="a6c4d-143">若要阻止排除首字母缩略词，需要删除已排除的首字母缩写词并添加它或验证它是否位于已发布列表中。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-143">To stop an acronym from being excluded, you'll need to delete the excluded acronym and add it or verify it's in your published list.</span></span>

<span data-ttu-id="a6c4d-144">可以单独添加首字母缩写词，或在 CSV 文件中批量导入它们。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-144">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="a6c4d-145">上传包含下表中所示字段的 CSV 文件：</span><span class="sxs-lookup"><span data-stu-id="a6c4d-145">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="a6c4d-146">首字母缩写 (强制) </span><span class="sxs-lookup"><span data-stu-id="a6c4d-146">Acronym (Mandatory)</span></span> | <span data-ttu-id="a6c4d-147">代表 (强制) </span><span class="sxs-lookup"><span data-stu-id="a6c4d-147">Stands for (Mandatory)</span></span> | <span data-ttu-id="a6c4d-148">URL</span><span class="sxs-lookup"><span data-stu-id="a6c4d-148">Url</span></span> | <span data-ttu-id="a6c4d-149">说明</span><span class="sxs-lookup"><span data-stu-id="a6c4d-149">Description</span></span>  | <span data-ttu-id="a6c4d-150">州 (强制) </span><span class="sxs-lookup"><span data-stu-id="a6c4d-150">State (Mandatory)</span></span> | <span data-ttu-id="a6c4d-151">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="a6c4d-151">Last Modified</span></span> | <span data-ttu-id="a6c4d-152">上次修改者</span><span class="sxs-lookup"><span data-stu-id="a6c4d-152">Last Modified By</span></span> | <span data-ttu-id="a6c4d-153">Id</span><span class="sxs-lookup"><span data-stu-id="a6c4d-153">Id</span></span> |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| <span data-ttu-id="a6c4d-154">*XXX*</span><span class="sxs-lookup"><span data-stu-id="a6c4d-154">*XXX*</span></span> | <span data-ttu-id="a6c4d-155">*拼写出缩写*</span><span class="sxs-lookup"><span data-stu-id="a6c4d-155">*Spelled out abbreviation*</span></span> | <span data-ttu-id="a6c4d-156">*Source*</span><span class="sxs-lookup"><span data-stu-id="a6c4d-156">*Source*</span></span> |  | <span data-ttu-id="a6c4d-157">*已发布、草稿或已排除*</span><span class="sxs-lookup"><span data-stu-id="a6c4d-157">*Published, Draft, or Excluded*</span></span> |  |  |  |

### <a name="csv-fields"></a><span data-ttu-id="a6c4d-158">CSV 字段</span><span class="sxs-lookup"><span data-stu-id="a6c4d-158">CSV fields</span></span>

<span data-ttu-id="a6c4d-159">**首字母缩略词**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-159">**Acronym**.</span></span> <span data-ttu-id="a6c4d-160">包含实际的短格式或缩写。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-160">Contains the actual short form or acronym.</span></span> <span data-ttu-id="a6c4d-161">例如 *DNN*。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-161">An example is *DNN*.</span></span>

<span data-ttu-id="a6c4d-162">**代表**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-162">**Stands for**.</span></span> <span data-ttu-id="a6c4d-163">包含首字母缩写词的定义。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-163">Contains the definition of the acronym.</span></span> <span data-ttu-id="a6c4d-164">例如， *深度神经网络*。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-164">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="a6c4d-165">**说明**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-165">**Description**.</span></span> <span data-ttu-id="a6c4d-166">A brief description of the acronym that gives users more info about the acronym and its definition.</span><span class="sxs-lookup"><span data-stu-id="a6c4d-166">A brief description of the acronym that gives users more info about the acronym and its definition.</span></span> <span data-ttu-id="a6c4d-167">例如， *深度神经网络* 是一个具有一定复杂度的神经网络，一个包含两层以上层的神经网络。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-167">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="a6c4d-168">**源**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-168">**Source**.</span></span> <span data-ttu-id="a6c4d-169">您希望用户访问的页面或网站的 URL，以了解有关缩写词详细信息。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-169">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="a6c4d-170">**状态**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-170">**State**.</span></span> <span data-ttu-id="a6c4d-171">此字段可以使用两个值：</span><span class="sxs-lookup"><span data-stu-id="a6c4d-171">This field can take two values:</span></span>

- <span data-ttu-id="a6c4d-172">**草稿**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-172">**Draft**.</span></span> <span data-ttu-id="a6c4d-173">将缩写词添加到"草稿"状态。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-173">Adds the acronym to the Draft state.</span></span>
- <span data-ttu-id="a6c4d-174">**已发布**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-174">**Published**.</span></span> <span data-ttu-id="a6c4d-175">将缩写词添加到"已发布"状态，使其在 Microsoft 搜索中可用。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-175">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>
- <span data-ttu-id="a6c4d-176">**已排除**。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-176">**Excluded**.</span></span> <span data-ttu-id="a6c4d-177">将缩写词添加到"已排除"状态，并阻止它出现在 Microsoft 搜索中。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-177">Adds the acronym to the Excluded state and prevents it from appearing in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="a6c4d-178">系统缩略词</span><span class="sxs-lookup"><span data-stu-id="a6c4d-178">System-curated acronyms</span></span>

<span data-ttu-id="a6c4d-179">对于管理员来说，将组织中使用的所有缩写词添加到"答案"可能是一个挑战。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-179">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="a6c4d-180">此功能可以找到搜索管理员甚至都不知道的缩写词。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-180">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="a6c4d-181">为完成该工作，Microsoft 搜索还发现并组织这些源中的缩写词：</span><span class="sxs-lookup"><span data-stu-id="a6c4d-181">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="a6c4d-182">用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a6c4d-182">Users’ emails</span></span>
- <span data-ttu-id="a6c4d-183">[SharePoint、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive]( https://onedrive.live.com/about/)和[Microsoft OneNote 中的文档](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="a6c4d-183">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="a6c4d-184">用户在 SharePoint、OneDrive 或 OneNote 中有权访问的组织中公共文档</span><span class="sxs-lookup"><span data-stu-id="a6c4d-184">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="a6c4d-185">Microsoft 搜索确保只有具有文档访问权限和权限的用户才能看到从文档发现的缩写词。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-185">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="a6c4d-186">在用户的邮箱中发现首字母缩写词时，只有该用户才能看到该缩写词。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-186">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="a6c4d-187">无需为系统策展的首字母缩略词设置。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-187">No setup is needed for system-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a6c4d-188">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="a6c4d-188">Frequently asked questions</span></span>

<span data-ttu-id="a6c4d-189">**问：如何对管理员和系统选择的数据进行排名？**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-189">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="a6c4d-190">**答：** 结果的排名可能因人而异，因为结果针对每个用户进行个性化设置。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-190">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="a6c4d-191">这两个类别都不始终优先于其他类别。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-191">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="a6c4d-192">**问：管理员策展的首字母缩写词在 Microsoft 搜索中发布后需要多久才能显示？**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-192">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="a6c4d-193">**答：**  添加到"已发布"状态首字母缩写词在 Microsoft 搜索中可用需要一天的时间。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-193">**A:**  It takes up to a day for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="a6c4d-194">**问：用户如何触发首字母缩写词答案？**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-194">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="a6c4d-195">**答**：若要获取缩写词答案，用户必须在 [必应](https://bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)或 [Office 365](https://Office.com)搜索框中输入特定 **查询** 模式。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-195">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="a6c4d-196">**问：接收或发送新电子邮件或文档后，系统选择缩写词需要多久显示？**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-196">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="a6c4d-197">**答：** 新电子邮件或文档中的首字母缩写词最多需要 7 天时间显示在 Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-197">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="a6c4d-198">**问：如果首字母缩写词被排除并发布，会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-198">**Q: What happens when an acronym is both excluded and published?**</span></span>

<span data-ttu-id="a6c4d-199">**答：** 排除的首字母缩略词将赋予优先级，并阻止已发布的首字母缩略词出现在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-199">**A:** The excluded acronym is given priority and prevents the published acronym from appearing in search results.</span></span> <span data-ttu-id="a6c4d-200">它不会删除或移除已发布的缩写词。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-200">It doesn't delete or remove the published acronym.</span></span>

<span data-ttu-id="a6c4d-201">**问：首字母缩写词从 Microsoft 搜索结果中排除需要多久？**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-201">**Q: How long does it take for an acronym to be excluded from Microsoft Search results?**</span></span>

<span data-ttu-id="a6c4d-202">**答**：排除的首字母缩写词最多需要一天的时间，以停止显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-202">**A**: It takes up to a day for an excluded acronym to stop appearing in search results.</span></span>

<span data-ttu-id="a6c4d-203">**问：对于系统策展的首字母缩略词，文档是否需要采用特定格式？**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-203">**Q: For system-curated acronyms, do documents need to be in a specific format?**</span></span>

<span data-ttu-id="a6c4d-204">**答：** 不。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-204">**A:** No.</span></span> <span data-ttu-id="a6c4d-205">我们支持除图像、文件夹和 zip 文件之外的所有文件类型。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-205">We support all file types except image, folder, and zip files.</span></span>

<span data-ttu-id="a6c4d-206">**问：Microsoft 会从所有语言的文档中发现缩写词吗？**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-206">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="a6c4d-207">**答**：Microsoft 仅支持来自英语、西班牙语、法语、意大利语、德语和葡萄牙语文档的系统特意缩略词。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-207">**A**: Microsoft only supports system-curated acronyms from documents in English, Spanish, French, Italian, German, and Portuguese.</span></span> <span data-ttu-id="a6c4d-208">将阶段性地添加对其他语言的支持。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-208">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="a6c4d-209">**问：如果我的组织不想显示系统特用首字母缩略词，该做什么？能否在搜索结果中停止显示此类型的首字母缩写词？**</span><span class="sxs-lookup"><span data-stu-id="a6c4d-209">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="a6c4d-210">**答**：若要在搜索结果中关闭显示系统创建的首字母缩写词，请按照联系商业产品支持人员中的说明创建客户支持 [票证](/microsoft-365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-210">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).</span></span>
<span data-ttu-id="a6c4d-211">创建支持票证后，系统创建的首字母缩略词最多需要 48 小时才能停止显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="a6c4d-211">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
