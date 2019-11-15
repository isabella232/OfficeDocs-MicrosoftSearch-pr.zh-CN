---
title: 常见问题
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 获取有关企业搜索和 Microsoft 搜索的常见问题解答
ms.openlocfilehash: 3ff2aabae4e09170b6b0380d520bfc620d5de5d8
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626252"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="6d5a2-103">常见问题</span><span class="sxs-lookup"><span data-stu-id="6d5a2-103">Frequently asked questions</span></span>

<span data-ttu-id="6d5a2-104">下面列出了最常见的问题。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="6d5a2-105">此处未列出你的问题的答案？</span><span class="sxs-lookup"><span data-stu-id="6d5a2-105">Don't see your question answered here?</span></span> <span data-ttu-id="6d5a2-106">请在本文的反馈中提出你的问题。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="6d5a2-107">是否支持高级查询理解？</span><span class="sxs-lookup"><span data-stu-id="6d5a2-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="6d5a2-p102">是的，Microsoft 搜索分析来自较大短语的查询意图。此功能使用 AI 来学习用户在查询中添加的不影响其搜索意图的常见多余短语。例如，当用户搜索“请告诉我更多关于如何更改密码的信息”时，我们会从查询中提取不太重要的字词，并根据“更改密码”等相关字词进行触发。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for 'tell me more about how to change my password please' we extract the less important words from the query and trigger based on the relevant ones like 'change password.'</span></span>
  
<span data-ttu-id="6d5a2-111">此功能不会覆盖管理中心中设置的关键字。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-111">This feature will not override keywords set in the admin center.</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="6d5a2-112">是否可以搜索本地文件？</span><span class="sxs-lookup"><span data-stu-id="6d5a2-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="6d5a2-113">是。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-113">Yes.</span></span> <span data-ttu-id="6d5a2-114">如果有 SharePoint 的混合部署，则可以搜索本地 SharePoint 文件。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-114">You can search on-premises SharePoint files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="6d5a2-115">如何将必应设置为我组织中的人员的默认搜索引擎？</span><span class="sxs-lookup"><span data-stu-id="6d5a2-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="6d5a2-116">以下说明介绍了如何设置默认搜索引擎、默认主页和默认浏览器，以便用户在使用必应中的 Microsoft 搜索时获得最佳体验：</span><span class="sxs-lookup"><span data-stu-id="6d5a2-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in Bing:</span></span>

- [<span data-ttu-id="6d5a2-117">将 Edge 设置为默认浏览器</span><span class="sxs-lookup"><span data-stu-id="6d5a2-117">Set Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="6d5a2-118">将必应设置为默认搜索引擎</span><span class="sxs-lookup"><span data-stu-id="6d5a2-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="6d5a2-119">将 Bing.com 设置为企业主页</span><span class="sxs-lookup"><span data-stu-id="6d5a2-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="6d5a2-120">我的搜索结果如何受到保护？</span><span class="sxs-lookup"><span data-stu-id="6d5a2-120">How are my search results protected?</span></span>

<span data-ttu-id="6d5a2-121">我们要求通过 Azure Active Directory (AAD) 身份验证才能访问来自受信任云的结果。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-121">We require Azure Active Directory (AAD) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="6d5a2-122">通过身份验证的用户仅可查看其有权访问的内容。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="6d5a2-123">搜索查询会被取消标识，且日志会与公共必应搜索流量分隔开来。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-123">Search queries are de-identified and logs are separated from public Bing search traffic.</span></span> <span data-ttu-id="6d5a2-124">此级别的保护在行业的其他地方均不可用。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="6d5a2-125">能否跨联合组织进行搜索？</span><span class="sxs-lookup"><span data-stu-id="6d5a2-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="6d5a2-126">否。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="6d5a2-127">从哪里可以获得有关 Office 365 和 Microsoft 365 合规性层和类别的信息？</span><span class="sxs-lookup"><span data-stu-id="6d5a2-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="6d5a2-128">可在[针对行业标准和法规的合规性框架](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)（PDF 下载）中找到详细信息。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="6d5a2-129">用户能否通过其工作或学校帐户获得 Microsoft 奖励积分？</span><span class="sxs-lookup"><span data-stu-id="6d5a2-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="6d5a2-130">Microsoft 搜索需要企业用户使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="6d5a2-131">但是，用户无法通过这些帐户登录到 Microsoft 奖励计划。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="6d5a2-132">不过，也存在企业用户可能看到奖励积分累积的实例。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="6d5a2-133">当 Microsoft 搜索用户拥有通过 <a href="https://www.microsoft.com/en-us/welcome?rtc=1">Microsoft 帐户</a>创建的奖励帐户时，可能会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-133">This can happen when a Microsoft Search user has a Rewards account that was created with a <a href="https://www.microsoft.com/en-us/welcome?rtc=1">Microsoft account</a>.</span></span> <span data-ttu-id="6d5a2-134">（与 Microsoft 帐户关联的电子邮件地址可以来自 Outlook.com、Hotmail.com、Gmail、Yahoo 或其他提供商。）如果用户在相同浏览器规划中使用其工作帐户和 Microsoft 帐户交替登录，则积分可能会累积到期奖励帐户。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="6d5a2-135">通过清除 cookie，用户可以在使用 Microsoft 搜索进行搜索时停止累积积分。</span><span class="sxs-lookup"><span data-stu-id="6d5a2-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span> 

