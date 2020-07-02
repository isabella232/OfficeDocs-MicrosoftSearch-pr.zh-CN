---
title: 在 Microsoft Search 中管理首字母缩写应答
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
description: 在 Microsoft Search 中创建和更新首字母缩略词答案
ms.openlocfilehash: 9d58306751f735cef77eba4404597c73c0528c11
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996073"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="d3b16-103">管理 Microsoft Search 中的缩写词答案</span><span class="sxs-lookup"><span data-stu-id="d3b16-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="d3b16-104">用户通常会遇到不熟悉的首字母缩写词和其组织或团队使用的缩写。</span><span class="sxs-lookup"><span data-stu-id="d3b16-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="d3b16-105">特定于组织或团队的术语可能对从一个团队迁移到另一个团队的人员、与内部合作伙伴团队合作的人员或对组织的新用户很新。</span><span class="sxs-lookup"><span data-stu-id="d3b16-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, those who work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="d3b16-106">组织并不总是拥有针对其标准术语的单一参考。</span><span class="sxs-lookup"><span data-stu-id="d3b16-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="d3b16-107">缺少单个引用使其难以查找这些首字母缩写词的定义或扩展。</span><span class="sxs-lookup"><span data-stu-id="d3b16-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="d3b16-108">Microsoft 搜索解决了与首字母缩略词有关的问题。</span><span class="sxs-lookup"><span data-stu-id="d3b16-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="d3b16-109">用户体验</span><span class="sxs-lookup"><span data-stu-id="d3b16-109">What users experience</span></span>

<span data-ttu-id="d3b16-110">Microsoft Search 用户可以在[Bing](https://Bing.com)中获取带有缩写词的定义。</span><span class="sxs-lookup"><span data-stu-id="d3b16-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com).</span></span> <span data-ttu-id="d3b16-111">在**搜索**框中，用户输入类似以下示例的查询：</span><span class="sxs-lookup"><span data-stu-id="d3b16-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="d3b16-112">是*什么*DNN</span><span class="sxs-lookup"><span data-stu-id="d3b16-112">*What is* DNN</span></span>
- <span data-ttu-id="d3b16-113">*定义*DNN</span><span class="sxs-lookup"><span data-stu-id="d3b16-113">*Define* DNN</span></span>
- <span data-ttu-id="d3b16-114">DNN*定义*</span><span class="sxs-lookup"><span data-stu-id="d3b16-114">DNN *definition*</span></span>
- <span data-ttu-id="d3b16-115">*扩展*DNN</span><span class="sxs-lookup"><span data-stu-id="d3b16-115">*Expand* DNN</span></span>
- <span data-ttu-id="d3b16-116">DNN*扩展*</span><span class="sxs-lookup"><span data-stu-id="d3b16-116">DNN *expansion*</span></span>
- <span data-ttu-id="d3b16-117">*的含义*DNN</span><span class="sxs-lookup"><span data-stu-id="d3b16-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="d3b16-118">DNN*表示*</span><span class="sxs-lookup"><span data-stu-id="d3b16-118">DNN *means*</span></span>

<span data-ttu-id="d3b16-119">结果包括用户组织中存在的 DNN 的所有含义。</span><span class="sxs-lookup"><span data-stu-id="d3b16-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="d3b16-120">用户必须输入包含首字母缩写词的指定*关键字*的查询，以触发其相应的答案。</span><span class="sxs-lookup"><span data-stu-id="d3b16-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="d3b16-121">首字母缩略词查询不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d3b16-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="d3b16-122">设置首字母缩略词答案</span><span class="sxs-lookup"><span data-stu-id="d3b16-122">Set up Acronyms answers</span></span>

<span data-ttu-id="d3b16-123">在 Microsoft 365[管理中心](https://admin.microsoft.com)，转到 " **Settings**  >  **microsoft Search**  >  **解答**  >  [**首字母缩写词**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)" "设置"，然后选择 "**添加首字母缩写**"。</span><span class="sxs-lookup"><span data-stu-id="d3b16-123">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Answers** > [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronyms**.</span></span>

<span data-ttu-id="d3b16-124">Microsoft Search 查询两个数据源，以提供对用户搜索的缩写词答案：</span><span class="sxs-lookup"><span data-stu-id="d3b16-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="d3b16-125">**编辑首字母缩写词**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-125">**Editorial acronyms**.</span></span> <span data-ttu-id="d3b16-126">由[管理员中心](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)的 IT 管理员提供。</span><span class="sxs-lookup"><span data-stu-id="d3b16-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="d3b16-127">**挖掘的首字母缩写词**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-127">**Mined acronyms**.</span></span> <span data-ttu-id="d3b16-128">由 Microsoft Search 从用户的个人电子邮件和文档以及组织中的公开可用数据进行挖掘。</span><span class="sxs-lookup"><span data-stu-id="d3b16-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="d3b16-129">设置编辑首字母缩写词</span><span class="sxs-lookup"><span data-stu-id="d3b16-129">Set up editorial acronyms</span></span>

<span data-ttu-id="d3b16-130">搜索管理员可以在[Microsoft Search 管理中心](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)的 "[首字母缩写" 选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)上设置编辑首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="d3b16-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="d3b16-131">您可以向管理中心添加任何内部网站或存储库的首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="d3b16-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="d3b16-132">编辑缩写词可添加到 "**已发布**" 或 "**草稿**" 状态：</span><span class="sxs-lookup"><span data-stu-id="d3b16-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="d3b16-133">**已发布状态**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-133">**Published state**.</span></span> <span data-ttu-id="d3b16-134">在 Microsoft Search 中，对组织的员工可以使用首字母缩略词。</span><span class="sxs-lookup"><span data-stu-id="d3b16-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="d3b16-135">在 Microsoft Search 中，首字母缩略词被添加到已发布状态，可能需要长达三天的时间。</span><span class="sxs-lookup"><span data-stu-id="d3b16-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="d3b16-136">**草稿状态**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-136">**Draft state**.</span></span> <span data-ttu-id="d3b16-137">如果管理员希望在 Microsoft Search 中提供首字母缩略词答案，则可以将首字母缩写词添加到草稿状态。</span><span class="sxs-lookup"><span data-stu-id="d3b16-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="d3b16-138">添加到草稿状态的首字母缩写词在 Microsoft Search 中不可用。</span><span class="sxs-lookup"><span data-stu-id="d3b16-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="d3b16-139">管理员需要将首字母缩写词添加到 "已发布" 状态，以使其可用。</span><span class="sxs-lookup"><span data-stu-id="d3b16-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="d3b16-140">管理员可以单独添加首字母缩写词或在 CSV 文件中批量导入。</span><span class="sxs-lookup"><span data-stu-id="d3b16-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="d3b16-141">将 CSV 文件上传到下表所示的字段：</span><span class="sxs-lookup"><span data-stu-id="d3b16-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="d3b16-142">首字母缩写词（必需）</span><span class="sxs-lookup"><span data-stu-id="d3b16-142">Acronym (mandatory)</span></span> | <span data-ttu-id="d3b16-143">扩展（强制）</span><span class="sxs-lookup"><span data-stu-id="d3b16-143">Expansion (mandatory)</span></span> | <span data-ttu-id="d3b16-144">说明</span><span class="sxs-lookup"><span data-stu-id="d3b16-144">Description</span></span>  | <span data-ttu-id="d3b16-145">Source</span><span class="sxs-lookup"><span data-stu-id="d3b16-145">Source</span></span> | <span data-ttu-id="d3b16-146">State （必需）</span><span class="sxs-lookup"><span data-stu-id="d3b16-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="d3b16-147">*美元*</span><span class="sxs-lookup"><span data-stu-id="d3b16-147">*XXX*</span></span> | <span data-ttu-id="d3b16-148">*拼写出缩写*</span><span class="sxs-lookup"><span data-stu-id="d3b16-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="d3b16-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="d3b16-149">*URL*</span></span> | <span data-ttu-id="d3b16-150">*已发布或草稿*</span><span class="sxs-lookup"><span data-stu-id="d3b16-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="d3b16-151">CSV 字段</span><span class="sxs-lookup"><span data-stu-id="d3b16-151">CSV fields</span></span>

<span data-ttu-id="d3b16-152">**首字母缩写词**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-152">**Acronym**.</span></span> <span data-ttu-id="d3b16-153">包含实际的短格式或首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="d3b16-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="d3b16-154">一个示例是*DNN*。</span><span class="sxs-lookup"><span data-stu-id="d3b16-154">An example is *DNN*.</span></span>

<span data-ttu-id="d3b16-155">**扩展**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-155">**Expansion**.</span></span> <span data-ttu-id="d3b16-156">包含首字母缩写词的扩展。</span><span class="sxs-lookup"><span data-stu-id="d3b16-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="d3b16-157">一个示例是*深度神经网络*。</span><span class="sxs-lookup"><span data-stu-id="d3b16-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="d3b16-158">**说明**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-158">**Description**.</span></span> <span data-ttu-id="d3b16-159">首字母缩写词的简短说明，使用户能够快速了解首字母缩写词和其扩展的含义。</span><span class="sxs-lookup"><span data-stu-id="d3b16-159">A brief description of the acronym that gives users quick insight into what the acronym and its expansion mean.</span></span> <span data-ttu-id="d3b16-160">例如， *deep 神经网络是具有某种复杂程度的神经网络，具有多个层的神经网络*。</span><span class="sxs-lookup"><span data-stu-id="d3b16-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="d3b16-161">**源**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-161">**Source**.</span></span> <span data-ttu-id="d3b16-162">您希望用户转到的页面或网站的 URL，以获取有关首字母缩写词的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d3b16-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="d3b16-163">**状态**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-163">**State**.</span></span> <span data-ttu-id="d3b16-164">此字段可采用两个值：</span><span class="sxs-lookup"><span data-stu-id="d3b16-164">This field can take two values:</span></span>

- <span data-ttu-id="d3b16-165">**草稿**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-165">**Draft**.</span></span> <span data-ttu-id="d3b16-166">将首字母缩写词添加到草稿状态。</span><span class="sxs-lookup"><span data-stu-id="d3b16-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="d3b16-167">**已发布**。</span><span class="sxs-lookup"><span data-stu-id="d3b16-167">**Published**.</span></span> <span data-ttu-id="d3b16-168">将首字母缩写项添加到已发布状态，并使其在 Microsoft Search 中可用。</span><span class="sxs-lookup"><span data-stu-id="d3b16-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="d3b16-169">挖掘首字母缩写词</span><span class="sxs-lookup"><span data-stu-id="d3b16-169">Mined acronyms</span></span>

<span data-ttu-id="d3b16-170">管理员将组织中使用的所有首字母缩写词添加到答案可能是一项挑战。</span><span class="sxs-lookup"><span data-stu-id="d3b16-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="d3b16-171">此功能可查找搜索管理员甚至不知道的首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="d3b16-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="d3b16-172">若要执行此操作，Microsoft 搜索还将根据这些来源地雷做首字母缩略词：</span><span class="sxs-lookup"><span data-stu-id="d3b16-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="d3b16-173">用户的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d3b16-173">Users’ emails.</span></span>
- <span data-ttu-id="d3b16-174">[SharePoint](https://products.office.com/sharepoint/collaboration)、 [Microsoft OneDrive]( https://onedrive.live.com/about/)和[microsoft OneNote](http://www.onenote.com/)中的文档。</span><span class="sxs-lookup"><span data-stu-id="d3b16-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) and [Microsoft OneNote](http://www.onenote.com/).</span></span>
- <span data-ttu-id="d3b16-175">组织内用户可在 SharePoint、OneDrive 或 OneNote 中访问的公共文档。</span><span class="sxs-lookup"><span data-stu-id="d3b16-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="d3b16-176">Microsoft Search 确保只有对文档具有访问权限的用户才能看到从该文档中挖掘的首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="d3b16-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="d3b16-177">从用户的邮箱中挖掘首字母缩写词时，只有该用户可以看到该首字母缩略词。</span><span class="sxs-lookup"><span data-stu-id="d3b16-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="d3b16-178">挖掘的首字母缩写词不需要任何设置。</span><span class="sxs-lookup"><span data-stu-id="d3b16-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d3b16-179">常见问题</span><span class="sxs-lookup"><span data-stu-id="d3b16-179">Frequently asked questions</span></span>

<span data-ttu-id="d3b16-180">**问：如何对编辑和挖掘数据进行分级？**</span><span class="sxs-lookup"><span data-stu-id="d3b16-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="d3b16-181">**A：** 目前，该功能对编辑前的首字母缩写词进行排名。</span><span class="sxs-lookup"><span data-stu-id="d3b16-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="d3b16-182">**问：发布后，编辑首字母缩写词需要多长时间才能显示在 Microsoft Search 中？**</span><span class="sxs-lookup"><span data-stu-id="d3b16-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="d3b16-183">**A：** 在 Microsoft Search 中，首字母缩略词已被添加到 "已发布" 状态的时间最长为三天。</span><span class="sxs-lookup"><span data-stu-id="d3b16-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="d3b16-184">**问：用户如何触发首字母缩略词答案？**</span><span class="sxs-lookup"><span data-stu-id="d3b16-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="d3b16-185">**答**：若要获取缩写词答案，用户必须在[必应](https://bing.com)**搜索**框中输入特定查询模式。</span><span class="sxs-lookup"><span data-stu-id="d3b16-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com) **Search** box.</span></span> <span data-ttu-id="d3b16-186">目前， [Office 365](https://Office.com)或[SharePoint](https://products.office.com/sharepoint/collaboration)中不提供首字母缩略词答案。</span><span class="sxs-lookup"><span data-stu-id="d3b16-186">Currently, Acronym answers aren't available in [Office 365](https://Office.com) or [SharePoint](https://products.office.com/sharepoint/collaboration).</span></span>

<span data-ttu-id="d3b16-187">**问：收到或发送新的电子邮件或文档后，要显示挖掘的首字母缩写词需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="d3b16-187">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="d3b16-188">**A：** 从新的电子邮件或文档中挖掘的首字母缩写词需要长达七天才能显示在 Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="d3b16-188">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="d3b16-189">**问：是否需要使用特定格式的文档进行挖掘才能选取它们？**</span><span class="sxs-lookup"><span data-stu-id="d3b16-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="d3b16-190">**A：** 不。</span><span class="sxs-lookup"><span data-stu-id="d3b16-190">**A:** No.</span></span> <span data-ttu-id="d3b16-191">我们支持除图像、文件夹和 zip 文件之外的所有文件类型。</span><span class="sxs-lookup"><span data-stu-id="d3b16-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="d3b16-192">**问： Microsoft 是否会采用所有语言的文档中的首字母缩写词？**</span><span class="sxs-lookup"><span data-stu-id="d3b16-192">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="d3b16-193">**A**： Microsoft 仅支持从英语文档进行挖掘。</span><span class="sxs-lookup"><span data-stu-id="d3b16-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="d3b16-194">对其他语言的支持将分阶段添加。</span><span class="sxs-lookup"><span data-stu-id="d3b16-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="d3b16-195">**问：如果我的组织不想显示挖掘的首字母缩写词，该怎么办？是否可以在搜索结果中停止显示挖掘的首字母缩写词？**</span><span class="sxs-lookup"><span data-stu-id="d3b16-195">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="d3b16-196">**A**：若要关闭在搜索结果中显示挖掘的首字母缩写词，请按照[业务产品的联系支持](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)部门的说明创建客户支持票证。</span><span class="sxs-lookup"><span data-stu-id="d3b16-196">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="d3b16-197">创建支持票证后，提取的首字母缩写词最长需要48小时才能停止显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="d3b16-197">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>

<span data-ttu-id="d3b16-198">**问：我何时将在[Office 365](https://Office.com)和[SharePoint Online](https://products.office.com/sharepoint/collaboration)中看到首字母缩略词答案？**</span><span class="sxs-lookup"><span data-stu-id="d3b16-198">**Q: When will I see Acronyms answers in [Office 365](https://Office.com) and [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**</span></span>

<span data-ttu-id="d3b16-199">**答**： Office 365 和 SharePoint Online 中的首字母缩写答案是产品路线图的一部分，但我们目前无法提供日期或时间范围。</span><span class="sxs-lookup"><span data-stu-id="d3b16-199">**A**: Acronyms answers in Office 365 and SharePoint Online are part of our product roadmap, but we're currently unable to provide a date or timeframe.</span></span>
