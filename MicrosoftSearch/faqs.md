---
title: 常见问题
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 获取有关企业搜索和 Microsoft 搜索的常见问题解答
ms.openlocfilehash: 5a134116c98b4feea0c04909349ce4b972c59ffe
ms.sourcegitcommit: 0b8c3c57384cecaa93c5cbaf3b3b30f8e20d1a69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408435"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="738e4-103">常见问题</span><span class="sxs-lookup"><span data-stu-id="738e4-103">Frequently asked questions</span></span>

<span data-ttu-id="738e4-104">下面列出了最常见的问题。</span><span class="sxs-lookup"><span data-stu-id="738e4-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="738e4-105">此处未列出你的问题的答案？</span><span class="sxs-lookup"><span data-stu-id="738e4-105">Don't see your question answered here?</span></span> <span data-ttu-id="738e4-106">请在本文的反馈中提出你的问题。</span><span class="sxs-lookup"><span data-stu-id="738e4-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="738e4-107">是否支持高级查询理解？</span><span class="sxs-lookup"><span data-stu-id="738e4-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="738e4-p102">是的，Microsoft Search 根据较大短语解析查询意图。此功能使用 AI 来了解用户在不影响其搜索意图的查询中添加的常见的多余短语。例如，当用户搜索 " *告诉我有关如何更改密码" 的详细信息*时，我们会从查询中提取不重要的词，并根据相关的更改密码（如 " *更改密码*"）进行触发。</span><span class="sxs-lookup"><span data-stu-id="738e4-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password please*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="738e4-111">此功能不会覆盖 [Microsoft 365 管理中心](https://admin.microsoft.com)中设置的关键字。</span><span class="sxs-lookup"><span data-stu-id="738e4-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="738e4-112">是否可以搜索本地文件？</span><span class="sxs-lookup"><span data-stu-id="738e4-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="738e4-113">是。</span><span class="sxs-lookup"><span data-stu-id="738e4-113">Yes.</span></span> <span data-ttu-id="738e4-114">如果您具有 SharePoint 的混合部署，则可以搜索本地 [SharePoint](http://sharepoint.com/) 文件。</span><span class="sxs-lookup"><span data-stu-id="738e4-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="738e4-115">如何将必应设置为我组织中的人员的默认搜索引擎？</span><span class="sxs-lookup"><span data-stu-id="738e4-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="738e4-116">以下是有关设置默认搜索引擎、默认主页和默认浏览器的说明，以便为用户提供 Microsoft Search in [Bing](https://Bing.com)的最佳体验：</span><span class="sxs-lookup"><span data-stu-id="738e4-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="738e4-117">将 Microsoft Edge 设置为默认浏览器</span><span class="sxs-lookup"><span data-stu-id="738e4-117">Set Microsoft Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="738e4-118">将必应设置为默认搜索引擎</span><span class="sxs-lookup"><span data-stu-id="738e4-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="738e4-119">将 Bing.com 设置为企业主页</span><span class="sxs-lookup"><span data-stu-id="738e4-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="738e4-120">我的搜索结果如何受到保护？</span><span class="sxs-lookup"><span data-stu-id="738e4-120">How are my search results protected?</span></span>

<span data-ttu-id="738e4-121">我们需要 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) 身份验证才能访问受信任云中的结果。</span><span class="sxs-lookup"><span data-stu-id="738e4-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="738e4-122">通过身份验证的用户仅可查看其有权访问的内容。</span><span class="sxs-lookup"><span data-stu-id="738e4-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="738e4-123">对搜索查询进行取消标识，并将日志与公共 [Bing](https://Bing.com) 搜索流量分开。</span><span class="sxs-lookup"><span data-stu-id="738e4-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic.</span></span> <span data-ttu-id="738e4-124">此级别的保护在行业的其他地方均不可用。</span><span class="sxs-lookup"><span data-stu-id="738e4-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="738e4-125">能否跨联合组织进行搜索？</span><span class="sxs-lookup"><span data-stu-id="738e4-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="738e4-126">否。</span><span class="sxs-lookup"><span data-stu-id="738e4-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="738e4-127">在哪里可以获取有关 Office 365 安全性、合规性和隐私的信息？</span><span class="sxs-lookup"><span data-stu-id="738e4-127">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="738e4-128">详细信息可在 [Office 365 的 "信任中心" 页](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)上找到。</span><span class="sxs-lookup"><span data-stu-id="738e4-128">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="738e4-129">用户能否通过其工作或学校帐户获得 Microsoft 奖励积分？</span><span class="sxs-lookup"><span data-stu-id="738e4-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="738e4-130">Microsoft 搜索需要企业用户使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="738e4-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="738e4-131">但是，用户无法通过这些帐户登录到 Microsoft 奖励计划。</span><span class="sxs-lookup"><span data-stu-id="738e4-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="738e4-132">不过，也存在企业用户可能看到奖励积分累积的实例。</span><span class="sxs-lookup"><span data-stu-id="738e4-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="738e4-133">当 Microsoft 搜索用户拥有通过 [Microsoft 帐户](https://www.microsoft.com/welcome?rtc=1)创建的奖励帐户时，可能会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="738e4-133">This can happen when a Microsoft Search user has a Rewards account that was created with a [Microsoft account](https://www.microsoft.com/welcome?rtc=1).</span></span> <span data-ttu-id="738e4-134">（与 Microsoft 帐户关联的电子邮件地址可以来自 Outlook.com、Hotmail.com、Gmail、Yahoo 或其他提供商。）如果用户在相同浏览器规划中使用其工作帐户和 Microsoft 帐户交替登录，则积分可能会累积到期奖励帐户。</span><span class="sxs-lookup"><span data-stu-id="738e4-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="738e4-135">通过清除 cookie，用户可以在使用 Microsoft 搜索进行搜索时停止累积积分。</span><span class="sxs-lookup"><span data-stu-id="738e4-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="738e4-136">来宾用户能否在我的组织中利用 Microsoft 搜索？</span><span class="sxs-lookup"><span data-stu-id="738e4-136">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="738e4-137">Microsoft 365 通过[来宾访问](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)实现与组织外部人员的丰富协作。</span><span class="sxs-lookup"><span data-stu-id="738e4-137">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="738e4-138">这些用户将能够对文档、网站、组、列表和库执行搜索操作。</span><span class="sxs-lookup"><span data-stu-id="738e4-138">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="738e4-139">但是，来宾用户将不会获得完整、个性化的 Microsoft 搜索体验，并且可能需要使用页面中的搜索框，而不是页眉中的统一 Microsoft 搜索框。</span><span class="sxs-lookup"><span data-stu-id="738e4-139">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>
