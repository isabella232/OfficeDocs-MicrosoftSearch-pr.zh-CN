---
title: Microsoft 搜索安全性
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: 在使用 Microsoft 搜索向授权用户提供信息的同时保护企业数据和用户
ms.openlocfilehash: 5f59e0e2969ef829d7c14b07ecb47d645cc63013
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508705"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="b12bf-103">Microsoft 搜索安全性</span><span class="sxs-lookup"><span data-stu-id="b12bf-103">Security for Microsoft Search</span></span>

<span data-ttu-id="b12bf-104">使用企业级安全性，Microsoft 搜索可以始终保护用户和数据。</span><span class="sxs-lookup"><span data-stu-id="b12bf-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>
  
## <a name="secure-by-default"></a><span data-ttu-id="b12bf-105">默认处于保护状态</span><span class="sxs-lookup"><span data-stu-id="b12bf-105">Secure by default</span></span>

<span data-ttu-id="b12bf-p101">Microsoft 搜索始终确保通过 HTTPS 发出请求。这一安全措施确保连接是端到端加密的，以增强安全性。</span><span class="sxs-lookup"><span data-stu-id="b12bf-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="b12bf-108">Azure Active Directory 身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="b12bf-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="b12bf-p102">Microsoft 搜索的身份验证绑定到 Azure Active Directory。当 Microsoft 搜索用户访问必应时，必应标题将显示 Microsoft 帐户以及工作或学校帐户的登录选项。如果必应无法确定用户是否是符合条件的参与者，用户可以转到[了解 Microsoft 搜索](https://www.bing.com/business/explore)页，在那里他们将被自动重定向到组织的登录页。</span><span class="sxs-lookup"><span data-stu-id="b12bf-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="b12bf-p103">用户只能通过工作或学校帐户访问 Microsoft 搜索。他们需要使用与用于访问 SharePoint 或 Outlook 等 Office 365 服务相同的凭据登录。Microsoft 个人帐户不能用于登录 Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="b12bf-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="b12bf-115">用户不能同时使用 Microsoft 帐户和工作或学校帐户登录必应。</span><span class="sxs-lookup"><span data-stu-id="b12bf-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="b12bf-116">单一登录</span><span class="sxs-lookup"><span data-stu-id="b12bf-116">Single sign-on</span></span>

<span data-ttu-id="b12bf-p104">如果用户已经通过 Outlook 或 SharePoint 等其他服务中的工作或学校帐户进行了身份验证，当他们在同一浏览器中访问必应时，就会自动登录到 Microsoft 搜索。此外，当用户注销 Microsoft 搜索时，他们将自动从同一浏览器的其他服务中注销。</span><span class="sxs-lookup"><span data-stu-id="b12bf-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="b12bf-119">通过浏览器与受信任的云通信</span><span class="sxs-lookup"><span data-stu-id="b12bf-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="b12bf-p105">当用户登录其工作或学校帐户时，必应会将必要的客户端库下载到浏览器中，以支持 Microsoft 搜索结果。然后，当他们搜索时，浏览器内的代码会调用 Office 365 云来获得工作结果。为此，Microsoft 搜索使用一个专用 API，该 API 根据 Office 365 [行业标准和法规的合规性框架](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)（PDF 下载）符合 Tier C (SOC2 Type 1)。这意味着工作结果和工作数据永远不会流经不符合的必应系统。</span><span class="sxs-lookup"><span data-stu-id="b12bf-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="b12bf-124">权限</span><span class="sxs-lookup"><span data-stu-id="b12bf-124">Permissions</span></span>

<span data-ttu-id="b12bf-p106">从 SharePoint 和 OneDrive for Business 等 Office 365 工作负载检索的工作结果在源上进行安全调整。用户不能查看无法通过 Office 365 查看和访问的 Word 文档或 PowerPoint 演示文稿等资源。他们只能在 SharePoint 中看到自己的文件以及作者显式或隐式（例如通过组成员身份）与之共享的文件。</span><span class="sxs-lookup"><span data-stu-id="b12bf-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="b12bf-128">保护用户查询不受必应公共部分的影响</span><span class="sxs-lookup"><span data-stu-id="b12bf-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="b12bf-129">因为与工作相关的搜索可能是敏感的，Microsoft 搜索为必应的公共 Web 结果部分如何处理这些问题实施了一套信任措施。</span><span class="sxs-lookup"><span data-stu-id="b12bf-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="b12bf-130">无论用户查询在返回的响应中是包含一个还是多个工作结果，都要采取以下措施：</span><span class="sxs-lookup"><span data-stu-id="b12bf-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="b12bf-131">日志记录</span><span class="sxs-lookup"><span data-stu-id="b12bf-131">Logging</span></span>
    
  - <span data-ttu-id="b12bf-p107">与 Microsoft 搜索流量相关的所有搜索日志都被取消标识，并与公共、非 Microsoft 搜索流量分开存储。它们将保留 18 个月，并且访问权限仅限于调试目的。</span><span class="sxs-lookup"><span data-stu-id="b12bf-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="b12bf-134">这些日志中的查询不用于对公共 Web 的自动建议或相关搜索等公共功能进行建模或训练。</span><span class="sxs-lookup"><span data-stu-id="b12bf-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="b12bf-135">受限访问通过各种安全机制进行管理，包括工程系统中的安全组和其他层。</span><span class="sxs-lookup"><span data-stu-id="b12bf-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="b12bf-136">搜索历史记录</span><span class="sxs-lookup"><span data-stu-id="b12bf-136">Search history</span></span>
    
  - <span data-ttu-id="b12bf-137">当用户使用工作或学校帐户登录时，用户的搜索历史记录将无法在其他计算机或设备上使用。</span><span class="sxs-lookup"><span data-stu-id="b12bf-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="b12bf-138">广告</span><span class="sxs-lookup"><span data-stu-id="b12bf-138">Advertising</span></span>
    
  - <span data-ttu-id="b12bf-139">企业搜索查询从不与广告商共享或推荐给广告商。</span><span class="sxs-lookup"><span data-stu-id="b12bf-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="b12bf-140">与 Microsoft 搜索相关的搜索广告日志与公共流量是分开存储的。</span><span class="sxs-lookup"><span data-stu-id="b12bf-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="b12bf-141">广告永远不会以基于工作身份或组织的用户为目标。</span><span class="sxs-lookup"><span data-stu-id="b12bf-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="b12bf-142">GDPR</span><span class="sxs-lookup"><span data-stu-id="b12bf-142">GDPR</span></span>

<span data-ttu-id="b12bf-p108">Microsoft [ 2018 年 5 月 21 日，博客文章](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)反映了我们对遵守 GDPR 的承诺，以及 Microsoft 如何帮助企业和组织履行自己的 GDPR 合规义务。可以在 Microsoft [信任中心常见问题](https://www.microsoft.com/zh-CN/trustcenter/privacy/gdpr/gdpr-faqs)中找到更多详细信息。在 Online Services 中对组织客户的客户数据进行操作的 Microsoft 搜索查询也将满足第 28 条中列出的处理者承诺，如[信任中心常见问题](https://www.microsoft.com/zh-CN/trustcenter/privacy/gdpr/gdpr-faqs)所述。对于从 Microsoft 搜索到公共必应的查询，Microsoft 是一个数据控制器，它已实施一些措施来取消识别 GDPR 下列出的查询。</span><span class="sxs-lookup"><span data-stu-id="b12bf-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/zh-CN/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/zh-CN/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


