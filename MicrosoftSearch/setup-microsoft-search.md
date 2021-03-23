---
title: 设置 Microsoft 搜索
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
description: 首次设置 Microsoft 搜索。
ms.openlocfilehash: 98499c2df1d8d732cdc1961116cafaaffeb4c5d6
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031662"
---
# <a name="set-up-microsoft-search"></a><span data-ttu-id="fb9b0-103">设置 Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="fb9b0-103">Set up Microsoft Search</span></span>

<span data-ttu-id="fb9b0-104">Microsoft 搜索提供了一个用户友好界面，可帮助用户查找文件和文档、内部网站和业务工具、人员与组、位置和方向、对话和答案等信息。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-104">Microsoft Search provides a user-friendly interface to help users find information like files and documents, internal sites and business tools, people and groups, locations and directions, conversations and answers.</span></span> <span data-ttu-id="fb9b0-105">它通过安全访问所有数据源（包括电子邮件、文件、SharePoint 文件、OneDrive 内容和其他共享资源）来实现此目标。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-105">It does this by securely accessing all data sources, including emails, files, SharePoint files, OneDrive content, and other shared resources as well.</span></span> <span data-ttu-id="fb9b0-106">通过必应中的 Microsoft 搜索，您还可以从 Internet 获取搜索结果。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-106">With Microsoft Search in Bing you can get search results from the internet as well.</span></span>

<span data-ttu-id="fb9b0-107">若要了解有关 Microsoft 搜索功能的详细信息，请参阅 [Microsoft 搜索概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-107">To learn more about Microsoft Search features, see [Microsoft Search Overview](overview-microsoft-search.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="fb9b0-108">入门</span><span class="sxs-lookup"><span data-stu-id="fb9b0-108">Get Started</span></span>

<span data-ttu-id="fb9b0-109">作为 Microsoft 365 的一部分，Microsoft 搜索将在默认情况下为所有支持它的 Microsoft 应用打开。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-109">Microsoft Search is turned on by default for all Microsoft apps that supports it, as a part of Microsoft 365.</span></span> <span data-ttu-id="fb9b0-110">不需要任何设置，但您可以通过一些基本管理任务改进整体 Microsoft 搜索体验。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-110">There is no setup required, but you can improve the overall Microsoft Search experience through some basic administrative tasks.</span></span>

<span data-ttu-id="fb9b0-111">在 Microsoft 365 管理中心管理 Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-111">You manage Microsoft Search from Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="fb9b0-112">在 Microsoft 365 管理中心中，**转到"设置**""搜索  >  [**&智能"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)</span><span class="sxs-lookup"><span data-stu-id="fb9b0-112">In Microsoft 365 admin center, go to **Settings** > [**Search & intelligence**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span>

<span data-ttu-id="fb9b0-113">作为管理员，你应该考虑一些可在组织内实现高效且用户友好的 Microsoft 搜索体验的因素。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-113">As an admin you should consider a few things that can make the Microsoft Search experience efficient and user friendly in your organization.</span></span>

## <a name="step-1-assign-search-admin-and-search-editor"></a><span data-ttu-id="fb9b0-114">步骤 1：分配搜索管理员和搜索编辑器</span><span class="sxs-lookup"><span data-stu-id="fb9b0-114">Step 1: Assign Search admin and Search editor</span></span>

<span data-ttu-id="fb9b0-115">在 Microsoft 搜索中，你可以通过将以下角色分配给用户来管理组织的搜索设置和内容：</span><span class="sxs-lookup"><span data-stu-id="fb9b0-115">In Microsoft Search, you can manage your organization’s search settings and content by assigning these roles to users:</span></span>

1. <span data-ttu-id="fb9b0-116">**搜索管理员：** 此角色可以创建和管理搜索结果内容，并定义查询设置，以改善组织内的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-116">**Search admin:** This role can create and manage search result content and define query settings for improved search results within the organization.</span></span> <span data-ttu-id="fb9b0-117">搜索管理员管理 Microsoft 搜索配置，并且可以执行搜索编辑者可以执行的所有内容管理任务。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-117">Search admin manages the Microsoft Search configuration and can perform all of the content-management tasks a Search editor can.</span></span>
2. <span data-ttu-id="fb9b0-118">**搜索编辑者：** 在 Microsoft 365 管理中心中为 Microsoft 搜索创建、管理和删除内容。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-118">**Search editor:** Creates, manages, and deletes content for Microsoft Search in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fb9b0-119">此角色可以创建和管理编辑内容，例如常见问题和答案、重要的地点和位置、经常搜索和使用的网站和应用。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-119">This role can create and manage editorial content, such as frequently asked questions and answers, important places and locations, frequently searched and used sites and apps.</span></span>

<span data-ttu-id="fb9b0-120">目前，搜索管理员和搜索编辑者角色必须由全局管理员分配。有关详细信息，请参阅[分配管理员角色](/office365/admin/add-users/assign-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-120">Currently, the Search admin and Search editor roles must be assigned by a global admin. For more information, see [Assign admin roles](/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>

<span data-ttu-id="fb9b0-121">搜索管理员直接影响最终用户的搜索体验。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-121">Search administrators directly influence the search experience for end users.</span></span> <span data-ttu-id="fb9b0-122">这包括选择要向用户显示的结果类型。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-122">This includes choosing the types of results you want to surface to your users.</span></span> <span data-ttu-id="fb9b0-123">一个人可能很难针对用户在组织内搜索的许多不同主题选择和创建权威内容。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-123">It may be difficult for one person to choose and create authoritative content on many different topics that users search for in an organization.</span></span> <span data-ttu-id="fb9b0-124">我们建议你通过将行业专家 (SME) 和其他用户添加为搜索编辑者来利用他们的专业技能和知识。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-124">We recommend that you leverage the expertise and knowledge of subject matter experts (SME) and other users by adding them as Search editors.</span></span>

## <a name="step-2-create-answers"></a><span data-ttu-id="fb9b0-125">步骤 2：创建答案</span><span class="sxs-lookup"><span data-stu-id="fb9b0-125">Step 2: Create answers</span></span>

<span data-ttu-id="fb9b0-126">Microsoft 搜索为管理员提供了可用于为其用户构建强大搜索体验的工具。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-126">Microsoft Search provides administrators with tools that they can use to build a robust search experience for their users.</span></span> <span data-ttu-id="fb9b0-127">在 Microsoft 搜索中，管理员可以创建三种不同的搜索内容，以提供更好的搜索体验并提高内容的"可查找性"：</span><span class="sxs-lookup"><span data-stu-id="fb9b0-127">In Microsoft Search, administrators have three different search contents that they can create for a better search experience and to improve the "findability" of content:</span></span>

<span data-ttu-id="fb9b0-128">书签是最常用的答案类型。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-128">Bookmarks are the most commonly used answer type.</span></span> <span data-ttu-id="fb9b0-129">它们将用户查询的最佳结果提升为搜索结果的顶部，并让用户轻松找到他们正在寻找的内容。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-129">They promote the best possible results for your users’ queries to the top of the search results and make it easy for your users to find what they are looking for.</span></span>
<span data-ttu-id="fb9b0-130">可供所有人使用的信息性内容;例如，有关公司的信息、Windows 和 Office 应用的帮助等。组织中人员通常在日常工作中搜索的内容。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-130">Informational content that is available for everyone; for example, information about the company, help for Windows and Office apps, etc. Content that people in the organization generally search for in their day-to-day work.</span></span> <span data-ttu-id="fb9b0-131">与工作相关的常见搜索包括员工福利、时间和费用报告、提交采购订单以及从 IT 服务获取帮助。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-131">Common work-related searches include employee benefits, time and expense reporting, submitting purchase orders, and getting help from IT services.</span></span>

<span data-ttu-id="fb9b0-132">有关创建和管理答案，请参阅 [规划内容](plan-your-content.md)。</span><span class="sxs-lookup"><span data-stu-id="fb9b0-132">For creating and managing answers, see [Plan your content](plan-your-content.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb9b0-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fb9b0-133">Next steps</span></span>

<span data-ttu-id="fb9b0-134">若要详细了解用户如何使用 Microsoft 搜索，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="fb9b0-134">If you'd like to learn more about how your users will use Microsoft Search, see the following articles:</span></span>

- [<span data-ttu-id="fb9b0-135">了解在 Office 中需要 Microsoft 搜索做什么</span><span class="sxs-lookup"><span data-stu-id="fb9b0-135">Find what you need with Microsoft Search in Office</span></span>](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446)
- [<span data-ttu-id="fb9b0-136">Office 365 培训中心</span><span class="sxs-lookup"><span data-stu-id="fb9b0-136">Office 365 Training Center</span></span>](https://support.office.com/office-training-center)
- [<span data-ttu-id="fb9b0-137">Microsoft 搜索中心</span><span class="sxs-lookup"><span data-stu-id="fb9b0-137">Microsoft Search Center</span></span>](https://support.office.com/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc)