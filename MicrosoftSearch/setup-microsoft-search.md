---
title: 设置 Microsoft 搜索
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 首次设置 Microsoft 搜索。
ms.openlocfilehash: 94ee7ece8a56d599778b151d5b836240d8832762
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626906"
---
# <a name="set-up-microsoft-search"></a><span data-ttu-id="68495-103">设置 Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="68495-103">Set up Microsoft Search</span></span>

<span data-ttu-id="68495-104">Microsoft 搜索提供了一个用户友好界面，可帮助用户通过安全访问所有数据源（包括电子邮件、文件、SharePoint 文件、OneDrive 内容和其他共享资源以及用户组织中的 Internet）来查找文件和文档、内部网站和业务工具、人员和组、位置和方向、对话和答案等信息。</span><span class="sxs-lookup"><span data-stu-id="68495-104">Microsoft Search provides a user-friendly interface to help users find information, like files and documents, internal sites and business tools, people and groups, locations and directions, conversations and answers by securely accessing all data sources, including emails, files, SharePoint files, OneDrive content, and other shared resources as well as the internet in the user’s organization.</span></span>

<span data-ttu-id="68495-105">若要了解有关 Microsoft 搜索功能的详细信息，请参阅 [Microsoft 搜索概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="68495-105">To learn more about Microsoft Search features, see [Microsoft Search Overview](overview-microsoft-search.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="68495-106">入门</span><span class="sxs-lookup"><span data-stu-id="68495-106">Get Started</span></span>

<span data-ttu-id="68495-107">作为 Microsoft 365 的一部分，Microsoft 搜索将在默认情况下为所有支持它的 Microsoft 应用打开。</span><span class="sxs-lookup"><span data-stu-id="68495-107">Microsoft Search is turned on by default for all Microsoft apps that supports it, as a part of Microsoft 365.</span></span> <span data-ttu-id="68495-108">无需进行任何设置，但可以通过一些基本管理任务来改进 Microsoft 搜索的整体体验。</span><span class="sxs-lookup"><span data-stu-id="68495-108">There is no setup required,but you can improve the overall Microsoft Search experience through some basic administrative tasks.</span></span>

<span data-ttu-id="68495-109">在 Microsoft 365 管理中心管理 Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="68495-109">You manage Microsoft Search from Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="68495-110">在 Microsoft 365 管理中心中，转到“**设置**” > “**Microsoft 搜索**”。</span><span class="sxs-lookup"><span data-stu-id="68495-110">In Microsoft 365 admin center, go to **Settings** > **Microsoft Search**.</span></span>

<span data-ttu-id="68495-111">**注意：** 如果没有在“**设置**”下看到 Microsoft 搜索，请打开任意管理中心页面右上角的“**试用预览版**”开关。</span><span class="sxs-lookup"><span data-stu-id="68495-111">**Note:** If you are NOT seeing Microsoft Search under **Settings**, turn on the **Try the preview** switch in the right top corner of any admin center page.</span></span>

<span data-ttu-id="68495-112">作为管理员，你应该考虑一些可在组织内实现高效且用户友好的 Microsoft 搜索体验的因素。</span><span class="sxs-lookup"><span data-stu-id="68495-112">As an admin you should consider a few things that can make the Microsoft Search experience efficient and user friendly in your organization.</span></span>

## <a name="step-1-assign-search-admin-and-search-editor"></a><span data-ttu-id="68495-113">步骤1：分配搜索管理和搜索编辑器</span><span class="sxs-lookup"><span data-stu-id="68495-113">Step 1: Assign Search admin and Search editor</span></span>

<span data-ttu-id="68495-114">在 Microsoft 搜索中，你可以通过将以下角色分配给用户来管理组织的搜索设置和内容：</span><span class="sxs-lookup"><span data-stu-id="68495-114">In Microsoft Search, you can manage your organization’s search settings and content by assigning these roles to users:</span></span>

1. <span data-ttu-id="68495-115">**搜索管理员：** 此角色可以创建和管理搜索结果内容，并定义查询设置，以改善组织内的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="68495-115">**Search admin:** This role can create and manage search result content and define query settings for improved search results within the organization.</span></span> <span data-ttu-id="68495-116">搜索管理员管理 Microsoft 搜索配置，并且可以执行搜索编辑者可以执行的所有内容管理任务。</span><span class="sxs-lookup"><span data-stu-id="68495-116">Search admin manages the Microsoft Search configuration and can perform all of the content-management tasks a Search editor can.</span></span>
2. <span data-ttu-id="68495-117">**搜索编辑者：** 在 Microsoft 365 管理中心中为 Microsoft 搜索创建、管理和删除内容。</span><span class="sxs-lookup"><span data-stu-id="68495-117">**Search editor:** Creates, manages, and deletes content for Microsoft Search in the Microsoft 365 admin center.</span></span> <span data-ttu-id="68495-118">此角色可以创建和管理编辑内容，例如常见问题和答案、重要的地点和位置、经常搜索和使用的网站和应用。</span><span class="sxs-lookup"><span data-stu-id="68495-118">This role can create and manage editorial content, such as frequently asked questions and answers, important places and locations, frequently searched and used sites and apps.</span></span>

<span data-ttu-id="68495-119">目前，搜索管理员和搜索编辑者角色必须由全局管理员分配。有关详细信息，请参阅[分配管理员角色](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="68495-119">Currently, the Search admin and Search editor roles must be assigned by a global admin. For more information, see [Assign admin roles](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>

<span data-ttu-id="68495-120">搜索管理员直接影响最终用户的搜索体验。</span><span class="sxs-lookup"><span data-stu-id="68495-120">Search administrators directly influence the search experience for end users.</span></span> <span data-ttu-id="68495-121">这包括选择要向用户显示的结果类型。</span><span class="sxs-lookup"><span data-stu-id="68495-121">This includes choosing the types of results you want to surface to your users.</span></span> <span data-ttu-id="68495-122">一个人可能很难针对用户在组织内搜索的许多不同主题选择和创建权威内容。</span><span class="sxs-lookup"><span data-stu-id="68495-122">It may be difficult for one person to choose and create authoritative content on many different topics that users search for in an organization.</span></span> <span data-ttu-id="68495-123">我们建议你通过将行业专家 (SME) 和其他用户添加为搜索编辑者来利用他们的专业技能和知识。</span><span class="sxs-lookup"><span data-stu-id="68495-123">We recommend that you leverage the expertise and knowledge of subject matter experts (SME) and other users by adding them as Search editors.</span></span>

## <a name="step-2-create-answers"></a><span data-ttu-id="68495-124">步骤2：创建答案</span><span class="sxs-lookup"><span data-stu-id="68495-124">Step 2: Create answers</span></span>

<span data-ttu-id="68495-125">Microsoft 搜索为管理员提供了可用于为其用户构建强大搜索体验的工具。</span><span class="sxs-lookup"><span data-stu-id="68495-125">Microsoft Search provides administrators with tools that they can use to build a robust search experience for their users.</span></span> <span data-ttu-id="68495-126">在 Microsoft Search 中，管理员具有三个不同的搜索内容，他们可以创建这些内容以获得更好的搜索体验，并可改进内容的 "findability"：</span><span class="sxs-lookup"><span data-stu-id="68495-126">In Microsoft Search, administrators have three different search contents that they can create for a better search experience and to improve the "findability" of content:</span></span>

<span data-ttu-id="68495-127">书签是最常使用的答案类型。</span><span class="sxs-lookup"><span data-stu-id="68495-127">Bookmarks are the most commonly used answer type.</span></span> <span data-ttu-id="68495-128">它们会将用户查询的最佳结果提升到搜索结果的顶部，并使用户能够轻松找到他们要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="68495-128">They promote the best possible results for your users’ queries to the top of the search results and make it easy for your users to find what they are looking for.</span></span>
<span data-ttu-id="68495-129">每个人都可以使用的信息内容;例如，有关公司的信息、Windows 和 Office 相关应用程序等。组织中的人员通常在日常工作中搜索的内容。</span><span class="sxs-lookup"><span data-stu-id="68495-129">Informational content that is available for everyone; for example, information about the company, help for Windows and Office apps, etc. Content that people in the organization generally search for in their day-to-day work.</span></span> <span data-ttu-id="68495-130">与工作相关的常见搜索包括员工福利、时间和费用报告、提交采购订单以及从 IT 服务获取帮助。</span><span class="sxs-lookup"><span data-stu-id="68495-130">Common work-related searches include employee benefits, time and expense reporting, submitting purchase orders, and getting help from IT services.</span></span>

<span data-ttu-id="68495-131">有关创建和管理答案的详细内容，请参阅[规划内容](plan-your-content.md)。</span><span class="sxs-lookup"><span data-stu-id="68495-131">For creating and managing answers, see [Plan your content](plan-your-content.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="68495-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="68495-132">Next steps</span></span>

<span data-ttu-id="68495-133">如果你想要详细了解你的用户如何使用 Microsoft 搜索，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="68495-133">If you'd like to learn more about how your users will use Microsoft Search, see the following articles:</span></span>

- [<span data-ttu-id="68495-134">了解在 Office 中需要 Microsoft 搜索做什么</span><span class="sxs-lookup"><span data-stu-id="68495-134">Find what you need with Microsoft Search in Office</span></span>](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446)
- [<span data-ttu-id="68495-135">Office 365 培训中心</span><span class="sxs-lookup"><span data-stu-id="68495-135">Office 365 Training Center</span></span>](https://support.office.com/office-training-center)
- [<span data-ttu-id="68495-136">Microsoft 搜索中心</span><span class="sxs-lookup"><span data-stu-id="68495-136">Microsoft Search Center</span></span>](https://support.office.com/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc)
