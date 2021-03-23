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
ms.openlocfilehash: 98128297047d50e2d418a8ed062066ab9e86749e
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031617"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="c3359-103">常见问题</span><span class="sxs-lookup"><span data-stu-id="c3359-103">Frequently asked questions</span></span>

<span data-ttu-id="c3359-104">下面列出了最常见的问题。</span><span class="sxs-lookup"><span data-stu-id="c3359-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="c3359-105">此处未列出你的问题的答案？</span><span class="sxs-lookup"><span data-stu-id="c3359-105">Don't see your question answered here?</span></span> <span data-ttu-id="c3359-106">请在本文的反馈中提出你的问题。</span><span class="sxs-lookup"><span data-stu-id="c3359-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="c3359-107">是否支持高级查询理解？</span><span class="sxs-lookup"><span data-stu-id="c3359-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="c3359-108">是的，Microsoft 搜索分析来自较大短语的查询意图。</span><span class="sxs-lookup"><span data-stu-id="c3359-108">Yes, Microsoft Search parses query intent from larger phrases.</span></span> <span data-ttu-id="c3359-109">此功能使用 AI 了解用户添加到查询中而不会影响其搜索意图的常见多余短语。</span><span class="sxs-lookup"><span data-stu-id="c3359-109">This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent.</span></span> <span data-ttu-id="c3359-110">例如，当用户搜索时，告诉我有关如何更改密码的更多信息时，我们会从查询中提取不太重要的字词，并基于更改密码等相关字词 *触发。*</span><span class="sxs-lookup"><span data-stu-id="c3359-110">For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="c3359-111">此功能不会覆盖在 [Microsoft 365](https://admin.microsoft.com)管理中心 中设置的关键字。</span><span class="sxs-lookup"><span data-stu-id="c3359-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="c3359-112">是否可以搜索本地文件？</span><span class="sxs-lookup"><span data-stu-id="c3359-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="c3359-113">是。</span><span class="sxs-lookup"><span data-stu-id="c3359-113">Yes.</span></span> <span data-ttu-id="c3359-114">如果具有 [SharePoint](http://sharepoint.com/) 的混合部署，可以搜索本地 SharePoint 文件。</span><span class="sxs-lookup"><span data-stu-id="c3359-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="c3359-115">如何将必应设置为我组织中的人员的默认搜索引擎？</span><span class="sxs-lookup"><span data-stu-id="c3359-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="c3359-116">下面是设置默认搜索引擎、默认主页和默认浏览器以为用户提供在必应中使用 Microsoft 搜索的最佳体验 [的说明](https://Bing.com)：</span><span class="sxs-lookup"><span data-stu-id="c3359-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="c3359-117">将 Microsoft Edge 设置为默认浏览器</span><span class="sxs-lookup"><span data-stu-id="c3359-117">Set Microsoft Edge as your default browser</span></span>](/deployedge/edge-default-browser)
- [<span data-ttu-id="c3359-118">将必应设置为默认搜索引擎</span><span class="sxs-lookup"><span data-stu-id="c3359-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="c3359-119">将 Bing.com 设置为企业主页</span><span class="sxs-lookup"><span data-stu-id="c3359-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="c3359-120">我的搜索结果如何受到保护？</span><span class="sxs-lookup"><span data-stu-id="c3359-120">How are my search results protected?</span></span>

<span data-ttu-id="c3359-121">我们需要 [Azure Active Directory](/azure/active-directory/) 身份验证来访问受信任云中的结果。</span><span class="sxs-lookup"><span data-stu-id="c3359-121">We require [Azure Active Directory](/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="c3359-122">通过身份验证的用户仅可查看其有权访问的内容。</span><span class="sxs-lookup"><span data-stu-id="c3359-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="c3359-123">搜索查询已取消标识，当您在必应中使用 Microsoft[](https://Bing.com)搜索时，日志会与公共必应搜索流量分隔开。</span><span class="sxs-lookup"><span data-stu-id="c3359-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic when you use Microsoft Search in Bing.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="c3359-124">能否跨联合组织进行搜索？</span><span class="sxs-lookup"><span data-stu-id="c3359-124">Can I search across federated organizations?</span></span>

<span data-ttu-id="c3359-125">否。</span><span class="sxs-lookup"><span data-stu-id="c3359-125">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="c3359-126">在哪里可以获取有关 Office 365 安全、合规性和隐私的信息？</span><span class="sxs-lookup"><span data-stu-id="c3359-126">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="c3359-127">有关详细信息，请参阅 Office [365 的信任中心页面](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c3359-127">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="c3359-128">用户能否通过其工作或学校帐户获得 Microsoft 奖励积分？</span><span class="sxs-lookup"><span data-stu-id="c3359-128">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="c3359-129">Microsoft 搜索需要企业用户使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c3359-129">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="c3359-130">但是，用户无法通过这些帐户登录到 Microsoft 奖励计划。</span><span class="sxs-lookup"><span data-stu-id="c3359-130">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="c3359-131">不过，也存在企业用户可能看到奖励积分累积的实例。</span><span class="sxs-lookup"><span data-stu-id="c3359-131">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="c3359-132">当 Microsoft 搜索用户拥有通过 [Microsoft 帐户](https://www.microsoft.com/welcome?rtc=1)创建的奖励帐户时，可能会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="c3359-132">This can happen when a Microsoft Search user has a Rewards account that was created with a [Microsoft account](https://www.microsoft.com/welcome?rtc=1).</span></span> <span data-ttu-id="c3359-133">（与 Microsoft 帐户关联的电子邮件地址可以来自 Outlook.com、Hotmail.com、Gmail、Yahoo 或其他提供商。）如果用户在相同浏览器规划中使用其工作帐户和 Microsoft 帐户交替登录，则积分可能会累积到期奖励帐户。</span><span class="sxs-lookup"><span data-stu-id="c3359-133">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="c3359-134">通过清除 cookie，用户可以在使用 Microsoft 搜索进行搜索时停止累积积分。</span><span class="sxs-lookup"><span data-stu-id="c3359-134">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="c3359-135">来宾用户能否在我的组织中利用 Microsoft 搜索？</span><span class="sxs-lookup"><span data-stu-id="c3359-135">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="c3359-136">Microsoft 365 允许通过来宾访问与组织外部人员 [进行丰富的协作。](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="c3359-136">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="c3359-137">这些用户将能够对文档、网站、组、列表和库执行搜索操作。</span><span class="sxs-lookup"><span data-stu-id="c3359-137">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="c3359-138">但是，来宾用户将不会获得完整的个性化 Microsoft 搜索体验，并且可能需要利用页面上的搜索框，而不是标头中的统一 Microsoft 搜索框。</span><span class="sxs-lookup"><span data-stu-id="c3359-138">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>