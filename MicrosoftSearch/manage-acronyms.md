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
ms.openlocfilehash: e328ecb7604a144b51f3a1483eef1b1c3a7e0bcb
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422943"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="c1c4f-103">管理 Microsoft Search 中的缩写词答案</span><span class="sxs-lookup"><span data-stu-id="c1c4f-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="c1c4f-104">用户通常会遇到不熟悉的首字母缩写词和其组织或团队使用的缩写。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="c1c4f-105">特定于组织或团队的术语可能对于从一个团队迁移到另一个团队的人员来说很新，可与内部合作伙伴团队或组织的新人员合作。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="c1c4f-106">组织并不总是拥有针对其标准术语的单一参考。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="c1c4f-107">缺少单个引用使其难以查找这些首字母缩写词的定义或扩展。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="c1c4f-108">Microsoft 搜索解决了与首字母缩略词有关的问题。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="c1c4f-109">用户体验</span><span class="sxs-lookup"><span data-stu-id="c1c4f-109">What users experience</span></span>

<span data-ttu-id="c1c4f-110">Microsoft Search 用户可以在 [Bing](https://Bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)和 [Office 365](https://Office.com)中获取具有首字母缩写词的定义。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="c1c4f-111">在 **搜索** 框中，用户输入类似以下示例的查询：</span><span class="sxs-lookup"><span data-stu-id="c1c4f-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="c1c4f-112">是*什么*DNN</span><span class="sxs-lookup"><span data-stu-id="c1c4f-112">*What is* DNN</span></span>
- <span data-ttu-id="c1c4f-113">*定义* DNN</span><span class="sxs-lookup"><span data-stu-id="c1c4f-113">*Define* DNN</span></span>
- <span data-ttu-id="c1c4f-114">DNN *定义*</span><span class="sxs-lookup"><span data-stu-id="c1c4f-114">DNN *definition*</span></span>
- <span data-ttu-id="c1c4f-115">*扩展* DNN</span><span class="sxs-lookup"><span data-stu-id="c1c4f-115">*Expand* DNN</span></span>
- <span data-ttu-id="c1c4f-116">DNN *扩展*</span><span class="sxs-lookup"><span data-stu-id="c1c4f-116">DNN *expansion*</span></span>
- <span data-ttu-id="c1c4f-117">*的含义* DNN</span><span class="sxs-lookup"><span data-stu-id="c1c4f-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="c1c4f-118">DNN *表示*</span><span class="sxs-lookup"><span data-stu-id="c1c4f-118">DNN *means*</span></span>

<span data-ttu-id="c1c4f-119">结果包括用户组织中存在的 DNN 的所有含义。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="c1c4f-120">用户必须输入包含首字母缩写词的指定 *关键字* 的查询，以触发其相应的答案。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="c1c4f-121">首字母缩略词查询不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="c1c4f-122">设置首字母缩略词答案</span><span class="sxs-lookup"><span data-stu-id="c1c4f-122">Set up Acronyms answers</span></span>

<span data-ttu-id="c1c4f-123">在 [Microsoft 365 管理中心](https://admin.microsoft.com)，转到 " [**首字母缩写词**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)"，然后选择 " **添加首字母缩略词**"。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="c1c4f-124">Microsoft Search 查询两个数据源，以提供对用户搜索的缩写词答案：</span><span class="sxs-lookup"><span data-stu-id="c1c4f-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="c1c4f-125">**编辑首字母缩写词**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-125">**Editorial acronyms**.</span></span> <span data-ttu-id="c1c4f-126">由 [管理员中心](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)的 IT 管理员提供。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="c1c4f-127">**挖掘的首字母缩写词**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-127">**Mined acronyms**.</span></span> <span data-ttu-id="c1c4f-128">由 Microsoft Search 从用户的个人电子邮件和文档以及组织中的公开可用数据进行挖掘。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="c1c4f-129">设置编辑首字母缩写词</span><span class="sxs-lookup"><span data-stu-id="c1c4f-129">Set up editorial acronyms</span></span>

<span data-ttu-id="c1c4f-130">搜索管理员可以在[Microsoft Search 管理中心](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)的 "[首字母缩写" 选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)上设置编辑首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="c1c4f-131">您可以向管理中心添加任何内部网站或存储库的首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="c1c4f-132">编辑缩写词可添加到 " **已发布** " 或 " **草稿** " 状态：</span><span class="sxs-lookup"><span data-stu-id="c1c4f-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="c1c4f-133">**已发布状态**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-133">**Published state**.</span></span> <span data-ttu-id="c1c4f-134">在 Microsoft Search 中，对组织的员工可以使用首字母缩略词。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="c1c4f-135">在 Microsoft Search 中，首字母缩略词被添加到已发布状态，可能需要长达三天的时间。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="c1c4f-136">**草稿状态**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-136">**Draft state**.</span></span> <span data-ttu-id="c1c4f-137">如果管理员希望在 Microsoft Search 中提供首字母缩略词答案，则可以将首字母缩写词添加到草稿状态。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="c1c4f-138">添加到草稿状态的首字母缩写词在 Microsoft Search 中不可用。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="c1c4f-139">管理员需要将首字母缩写词添加到 "已发布" 状态，以使其可用。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="c1c4f-140">管理员可以单独添加首字母缩写词或在 CSV 文件中批量导入。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="c1c4f-141">将 CSV 文件上传到下表所示的字段：</span><span class="sxs-lookup"><span data-stu-id="c1c4f-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="c1c4f-142">首字母缩略词 (强制) </span><span class="sxs-lookup"><span data-stu-id="c1c4f-142">Acronym (mandatory)</span></span> | <span data-ttu-id="c1c4f-143">扩展 (强制) </span><span class="sxs-lookup"><span data-stu-id="c1c4f-143">Expansion (mandatory)</span></span> | <span data-ttu-id="c1c4f-144">说明</span><span class="sxs-lookup"><span data-stu-id="c1c4f-144">Description</span></span>  | <span data-ttu-id="c1c4f-145">Source</span><span class="sxs-lookup"><span data-stu-id="c1c4f-145">Source</span></span> | <span data-ttu-id="c1c4f-146">状态 (强制) </span><span class="sxs-lookup"><span data-stu-id="c1c4f-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="c1c4f-147">*美元*</span><span class="sxs-lookup"><span data-stu-id="c1c4f-147">*XXX*</span></span> | <span data-ttu-id="c1c4f-148">*拼写出缩写*</span><span class="sxs-lookup"><span data-stu-id="c1c4f-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="c1c4f-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="c1c4f-149">*URL*</span></span> | <span data-ttu-id="c1c4f-150">*已发布或草稿*</span><span class="sxs-lookup"><span data-stu-id="c1c4f-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="c1c4f-151">CSV 字段</span><span class="sxs-lookup"><span data-stu-id="c1c4f-151">CSV fields</span></span>

<span data-ttu-id="c1c4f-152">**首字母缩写词**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-152">**Acronym**.</span></span> <span data-ttu-id="c1c4f-153">包含实际的短格式或首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="c1c4f-154">一个示例是 *DNN*。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-154">An example is *DNN*.</span></span>

<span data-ttu-id="c1c4f-155">**扩展**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-155">**Expansion**.</span></span> <span data-ttu-id="c1c4f-156">包含首字母缩写词的扩展。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="c1c4f-157">一个示例是 *深度神经网络*。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="c1c4f-158">**说明**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-158">**Description**.</span></span> <span data-ttu-id="c1c4f-159">首字母缩写词的简短说明，为用户提供有关首字母缩写词和扩展的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="c1c4f-160">例如， *deep 神经网络是具有某种复杂程度的神经网络，具有多个层的神经网络*。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="c1c4f-161">**源**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-161">**Source**.</span></span> <span data-ttu-id="c1c4f-162">您希望用户转到的页面或网站的 URL，以获取有关首字母缩写词的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="c1c4f-163">**状态**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-163">**State**.</span></span> <span data-ttu-id="c1c4f-164">此字段可采用两个值：</span><span class="sxs-lookup"><span data-stu-id="c1c4f-164">This field can take two values:</span></span>

- <span data-ttu-id="c1c4f-165">**草稿**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-165">**Draft**.</span></span> <span data-ttu-id="c1c4f-166">将首字母缩写词添加到草稿状态。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="c1c4f-167">**已发布**。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-167">**Published**.</span></span> <span data-ttu-id="c1c4f-168">将首字母缩写项添加到已发布状态，并使其在 Microsoft Search 中可用。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="c1c4f-169">挖掘首字母缩写词</span><span class="sxs-lookup"><span data-stu-id="c1c4f-169">Mined acronyms</span></span>

<span data-ttu-id="c1c4f-170">管理员将组织中使用的所有首字母缩写词添加到答案可能是一项挑战。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="c1c4f-171">此功能可查找搜索管理员甚至不知道的首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="c1c4f-172">若要执行此操作，Microsoft 搜索还将根据这些来源地雷做首字母缩略词：</span><span class="sxs-lookup"><span data-stu-id="c1c4f-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="c1c4f-173">用户的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-173">Users’ emails.</span></span>
- <span data-ttu-id="c1c4f-174">[SharePoint](https://products.office.com/sharepoint/collaboration)、 [Microsoft OneDrive]( https://onedrive.live.com/about/)和[microsoft OneNote](https://www.onenote.com/)中的文档。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/).</span></span>
- <span data-ttu-id="c1c4f-175">组织内用户可在 SharePoint、OneDrive 或 OneNote 中访问的公共文档。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="c1c4f-176">Microsoft Search 确保只有对文档具有访问权限的用户才能看到从该文档中挖掘的首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="c1c4f-177">从用户的邮箱中挖掘首字母缩写词时，只有该用户可以看到该首字母缩略词。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="c1c4f-178">挖掘的首字母缩写词不需要任何设置。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c1c4f-179">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="c1c4f-179">Frequently asked questions</span></span>

<span data-ttu-id="c1c4f-180">**问：如何对编辑和挖掘数据进行分级？**</span><span class="sxs-lookup"><span data-stu-id="c1c4f-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="c1c4f-181">**A：** 目前，该功能对编辑前的首字母缩写词进行排名。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="c1c4f-182">**问：发布后，编辑首字母缩写词需要多长时间才能显示在 Microsoft Search 中？**</span><span class="sxs-lookup"><span data-stu-id="c1c4f-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="c1c4f-183">**A：**  在 Microsoft Search 中，首字母缩略词已被添加到 "已发布" 状态的时间最长为三天。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="c1c4f-184">**问：用户如何触发首字母缩略词答案？**</span><span class="sxs-lookup"><span data-stu-id="c1c4f-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="c1c4f-185">**答**：若要获取首字母缩写的答案，用户必须在 [Bing](https://bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)或 [Office 365](https://Office.com) **搜索** 框中输入特定的查询模式。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="c1c4f-186">**问：收到或发送新的电子邮件或文档后，要显示挖掘的首字母缩写词需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="c1c4f-186">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="c1c4f-187">**A：** 从新的电子邮件或文档中挖掘的首字母缩写词需要长达七天才能显示在 Microsoft 搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-187">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="c1c4f-188">**问：是否需要使用特定格式的文档进行挖掘才能选取它们？**</span><span class="sxs-lookup"><span data-stu-id="c1c4f-188">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="c1c4f-189">**A：** 不。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-189">**A:** No.</span></span> <span data-ttu-id="c1c4f-190">我们支持除图像、文件夹和 zip 文件之外的所有文件类型。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-190">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="c1c4f-191">**问： Microsoft 是否会采用所有语言的文档中的首字母缩写词？**</span><span class="sxs-lookup"><span data-stu-id="c1c4f-191">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="c1c4f-192">**A**： Microsoft 仅支持从英语文档进行挖掘。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-192">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="c1c4f-193">对其他语言的支持将分阶段添加。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-193">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="c1c4f-194">**问：如果我的组织不想显示挖掘的首字母缩写词，该怎么办？是否可以在搜索结果中停止显示挖掘的首字母缩写词？**</span><span class="sxs-lookup"><span data-stu-id="c1c4f-194">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="c1c4f-195">**A**：若要关闭在搜索结果中显示挖掘的首字母缩写词，请按照 [业务产品的联系支持](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)部门的说明创建客户支持票证。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-195">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="c1c4f-196">创建支持票证后，提取的首字母缩写词最长需要48小时才能停止显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="c1c4f-196">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>
