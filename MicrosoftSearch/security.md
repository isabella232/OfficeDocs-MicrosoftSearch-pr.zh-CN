---
title: Microsoft 搜索功能的安全性
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
description: 保护您的企业数据和用户，同时提供 Microsoft 搜索信息授权用户
ms.openlocfilehash: 5f59e0e2969ef829d7c14b07ecb47d645cc63013
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612519"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="c14d9-103">Microsoft 搜索功能的安全性</span><span class="sxs-lookup"><span data-stu-id="c14d9-103">Security for Microsoft Search</span></span>

<span data-ttu-id="c14d9-104">企业级安全 Microsoft 搜索始终保留您的用户和受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="c14d9-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>
  
## <a name="secure-by-default"></a><span data-ttu-id="c14d9-105">默认情况下保护</span><span class="sxs-lookup"><span data-stu-id="c14d9-105">Secure by default</span></span>

<span data-ttu-id="c14d9-p101">Microsoft Search 始终确保通过 HTTPS 发出请求。此保护确保连接加密的端到端为了增强安全性。</span><span class="sxs-lookup"><span data-stu-id="c14d9-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="c14d9-108">身份验证和授权与 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c14d9-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="c14d9-p102">Microsoft Search 身份验证与 Azure Active Directory。当 Microsoft 搜索用户转到 Bing 时，Bing 标头将显示为 Microsoft 帐户登录选项以及工作或学校帐户。如果 Bing 无法确定用户是否符合条件的参与者，用户可以转到[浏览 Microsoft 搜索](https://www.bing.com/business/explore)页上，其中他们将被自动重定向到组织的登录页。</span><span class="sxs-lookup"><span data-stu-id="c14d9-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="c14d9-p103">用户可以访问 Microsoft 搜索仅通过工作或学校帐户。他们需要使用用于访问 Office 365 服务，例如 SharePoint 或 Outlook 相同的凭据登录。不能使用个人 Microsoft 帐户登录到 Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="c14d9-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="c14d9-115">用户无法登录到 Bing 使用 Microsoft 帐户和工作或学校帐户同时。</span><span class="sxs-lookup"><span data-stu-id="c14d9-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="c14d9-116">单一登录</span><span class="sxs-lookup"><span data-stu-id="c14d9-116">Single sign-on</span></span>

<span data-ttu-id="c14d9-p104">如果用户已通过身份验证与中其他服务，如 Outlook 或 SharePoint，其工作或学校帐户他们将自动登录到 Microsoft 搜索在转至时 Bing 的相同浏览器中。此外，当用户注销利用 Microsoft 搜索，它们将自动注销从的相同浏览器中的其他服务。</span><span class="sxs-lookup"><span data-stu-id="c14d9-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="c14d9-119">与从浏览器中的受信任的云进行通信</span><span class="sxs-lookup"><span data-stu-id="c14d9-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="c14d9-p105">当用户登录与其工作或学校帐户，Bing 将将必要的客户端库下载到浏览器以启用 Microsoft 搜索结果。然后，当他们搜索时，在浏览器代码调用 Office 365 云获取工作结果。若要执行此操作，Microsoft 搜索，请使用层 c (SOC2 类型 1) 符合 Office 365[的行业标准和法规合规性框架](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)（PDF 下载） 的保密协议专用的 API。这意味着工作结果和工作数据从不流通过不符合标准的 Bing 系统。</span><span class="sxs-lookup"><span data-stu-id="c14d9-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="c14d9-124">权限</span><span class="sxs-lookup"><span data-stu-id="c14d9-124">Permissions</span></span>

<span data-ttu-id="c14d9-p106">在源修整工作检索从 Office 365 工作负载，如 SharePoint 和 OneDrive for Business 是安全的结果。用户无法看到如 Word 文档或 PowerPoint 演示文稿他们不能看到并通过 Office 365 访问的资源。他们只能看到他们自己的文件和已与共享其作者显式或隐式的文件 （通过组成员身份，例如） SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="c14d9-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="c14d9-128">Bing 的公共部分可防止用户查询</span><span class="sxs-lookup"><span data-stu-id="c14d9-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="c14d9-129">与工作相关搜索可能写，因为 Microsoft 搜索已实现一组信任的公共 web 结果一部分 Bing 如何处理这些的度量值。</span><span class="sxs-lookup"><span data-stu-id="c14d9-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="c14d9-130">是否用户查询包含一个或多个工作结果中返回的响应，无论是采取以下措施：</span><span class="sxs-lookup"><span data-stu-id="c14d9-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="c14d9-131">Logging</span><span class="sxs-lookup"><span data-stu-id="c14d9-131">Logging</span></span>
    
  - <span data-ttu-id="c14d9-p107">与 Microsoft 搜索通信相关的所有搜索日志的注销标识和存储分开公用，Microsoft 搜索通信。它们保留 18 个月，并限制仅用于调试目的的访问。</span><span class="sxs-lookup"><span data-stu-id="c14d9-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="c14d9-134">这些日志中的查询不使用到模型或公共功能，如 autosuggest 或相关搜索公共 web 的培训。</span><span class="sxs-lookup"><span data-stu-id="c14d9-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="c14d9-135">通过各种安全机制，包括安全组和工程系统中的其他层管理受限制的访问。</span><span class="sxs-lookup"><span data-stu-id="c14d9-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="c14d9-136">搜索历史记录</span><span class="sxs-lookup"><span data-stu-id="c14d9-136">Search history</span></span>
    
  - <span data-ttu-id="c14d9-137">当使用的单位电话或学校帐户登录，用户的搜索历史记录不会在其他计算机或设备上可用。</span><span class="sxs-lookup"><span data-stu-id="c14d9-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="c14d9-138">广告</span><span class="sxs-lookup"><span data-stu-id="c14d9-138">Advertising</span></span>
    
  - <span data-ttu-id="c14d9-139">企业级搜索查询从不与共享或给广告商建议。</span><span class="sxs-lookup"><span data-stu-id="c14d9-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="c14d9-140">与 Microsoft 搜索相关的搜索广告日志公用通信分开存储。</span><span class="sxs-lookup"><span data-stu-id="c14d9-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="c14d9-141">广告从不针对基于其工作标识或组织的用户。</span><span class="sxs-lookup"><span data-stu-id="c14d9-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="c14d9-142">GDPR</span><span class="sxs-lookup"><span data-stu-id="c14d9-142">GDPR</span></span>

<span data-ttu-id="c14d9-p108">[5 月 21 2018年博客文章](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)从 Microsoft 反映了我们承诺 GDPR 合规性和 Microsoft 如何帮助企业和组织自己 GDPR 合规性义务。Microsoft[信任中心常见问题](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)中，您可以找到更多详细信息。针对组织客户的客户数据联机服务内运行的 Microsoft 搜索查询还能满足按照文章 28，具体体现在[信任中心 FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)中的处理器承诺。转到公共 Bing 来自 Microsoft 的搜索查询，对于 Microsoft 数据控制器，并已实现措施以消除标识查询 GDPR 下所述。</span><span class="sxs-lookup"><span data-stu-id="c14d9-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


