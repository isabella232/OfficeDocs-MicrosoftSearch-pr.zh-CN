---
title: 必应 Bing 中的 Microsoft 搜索的安全性和隐私
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 在 Bing 中向具有 Microsoft 搜索的授权用户提供信息，保护贵公司的数据和最终用户
ms.openlocfilehash: d3d8822b68fc730885e973c0c24c52070d50eba8
ms.sourcegitcommit: f4cb37fdf85b895337caee827fb72b5b7fcaa8ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2019
ms.locfileid: "39995384"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a><span data-ttu-id="ae350-103">必应 Bing 中的 Microsoft 搜索的安全性和隐私</span><span class="sxs-lookup"><span data-stu-id="ae350-103">Security and Privacy for Microsoft Search in Bing</span></span>

<span data-ttu-id="ae350-104">使用增强的隐私和安全措施，Bing 中的 Microsoft 搜索可帮助保护您的用户和工作区数据。</span><span class="sxs-lookup"><span data-stu-id="ae350-104">With enhanced privacy and security measures, Microsoft Search in Bing helps protect your users and workplace data.</span></span>

## <a name="secure-by-default"></a><span data-ttu-id="ae350-105">默认处于保护状态</span><span class="sxs-lookup"><span data-stu-id="ae350-105">Secure by default</span></span>

<span data-ttu-id="ae350-106">必应 Bing 请求中的 Microsoft Search 通过 HTTPS 进行。</span><span class="sxs-lookup"><span data-stu-id="ae350-106">Microsoft Search in Bing requests are made over HTTPS.</span></span> <span data-ttu-id="ae350-107">该连接以端到端加密，以实现增强的安全性。</span><span class="sxs-lookup"><span data-stu-id="ae350-107">The connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="ae350-108">Azure Active Directory 身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="ae350-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="ae350-109">Bing 中 Microsoft Search 的身份验证绑定到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="ae350-109">Authentication for Microsoft Search in Bing is tied to Azure Active Directory.</span></span> <span data-ttu-id="ae350-110">当 Microsoft 搜索用户转到 Bing 时，Bing 标头将显示 Microsoft 帐户的登录选项以及工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="ae350-110">When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account.</span></span> <span data-ttu-id="ae350-111">如果 Bing 无法确定用户是否为符合条件的参与者，则用户可以转到 "[浏览 Microsoft 搜索](https://www.bing.com/business/explore)" 页，它们将被自动重定向到组织的登录页。</span><span class="sxs-lookup"><span data-stu-id="ae350-111">If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span>
 
<span data-ttu-id="ae350-p103">用户只能通过工作或学校帐户访问 Microsoft 搜索。他们需要使用与用于访问 SharePoint 或 Outlook 等 Office 365 服务相同的凭据登录。Microsoft 个人帐户不能用于登录 Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="ae350-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
    
## <a name="single-sign-on"></a><span data-ttu-id="ae350-115">单一登录</span><span class="sxs-lookup"><span data-stu-id="ae350-115">Single sign-on</span></span>

<span data-ttu-id="ae350-116">如果用户已通过其他服务（如 Outlook 或 SharePoint）中的工作或学校帐户进行身份验证，则当他们转到同一浏览器中的 Bing 时，他们将自动登录到相同的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="ae350-116">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed into the same work or school account when they go to Bing in the same browser.</span></span> <span data-ttu-id="ae350-117">此外，当用户注销自己的工作或学校帐户时，他们将在同一浏览器中自动从其他 Microsoft Office 服务注销。</span><span class="sxs-lookup"><span data-stu-id="ae350-117">Also, when the user signs out of their work or school account, they'll be automatically signed out from other Microsoft Office services in the same browser.</span></span>
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a><span data-ttu-id="ae350-118">从浏览器与 Microsoft 云通信</span><span class="sxs-lookup"><span data-stu-id="ae350-118">Communicates with the Microsoft cloud from the browser</span></span>

<span data-ttu-id="ae350-119">当用户使用其工作或学校帐户登录时，Bing 将向浏览器下载所需的客户端库，以启用 Microsoft 搜索结果。</span><span class="sxs-lookup"><span data-stu-id="ae350-119">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results.</span></span> <span data-ttu-id="ae350-120">然后，在搜索时，浏览器中的代码会调用 Office 365 云以获取工作结果。</span><span class="sxs-lookup"><span data-stu-id="ae350-120">Then, when they search, the in-browser code calls the Office 365 cloud to get work results.</span></span> <span data-ttu-id="ae350-121">为此，Microsoft Search 使用一个专用的 API，它是符合 Office 365 [符合行业标准和法规的合规性框架] （https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) PDF 下载）的第 C 层（SOC2 类型1）兼容的。</span><span class="sxs-lookup"><span data-stu-id="ae350-121">To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations] (https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span> <span data-ttu-id="ae350-122">这意味着工作结果和工作数据从不通过不合规的 Bing 系统流动。</span><span class="sxs-lookup"><span data-stu-id="ae350-122">This means work results and work data never flow through non-compliant Bing systems.</span></span>
  
## <a name="permissions"></a><span data-ttu-id="ae350-123">权限</span><span class="sxs-lookup"><span data-stu-id="ae350-123">Permissions</span></span>

<span data-ttu-id="ae350-p106">从 SharePoint 和 OneDrive for Business 等 Office 365 工作负载检索的工作结果在源上进行安全调整。用户不能查看无法通过 Office 365 查看和访问的 Word 文档或 PowerPoint 演示文稿等资源。他们只能在 SharePoint 中看到自己的文件以及作者显式或隐式（例如通过组成员身份）与之共享的文件。</span><span class="sxs-lookup"><span data-stu-id="ae350-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a><span data-ttu-id="ae350-127">必应 Bing 中的 Microsoft Search 保护工作区搜索</span><span class="sxs-lookup"><span data-stu-id="ae350-127">Microsoft Search in Bing protects workplace searches</span></span>

<span data-ttu-id="ae350-128">当用户在 Bing 的 Microsoft Search 中输入搜索查询时，将发生两个同时进行的搜索请求：</span><span class="sxs-lookup"><span data-stu-id="ae350-128">When a user enters a search query in Microsoft Search in Bing, two simultaneous search requests occur:</span></span>

- <span data-ttu-id="ae350-129">组织内部资源的搜索。</span><span class="sxs-lookup"><span data-stu-id="ae350-129">A search of your organization’s internal resources.</span></span>
- <span data-ttu-id="ae350-130">从 Bing.com 中单独搜索公共结果。</span><span class="sxs-lookup"><span data-stu-id="ae350-130">A separate search of public results from Bing.com.</span></span>

<span data-ttu-id="ae350-131">由于工作区搜索可能是敏感的，Microsoft Search 实现了一组信任措施，用于描述如何处理来自 Bing.com 的单独搜索的公共结果。</span><span class="sxs-lookup"><span data-stu-id="ae350-131">Because workplace searches might be sensitive, Microsoft Search has implemented a set of trust measures that describe how the separate search of public results from Bing.com is handled.</span></span>

### <a name="logging"></a><span data-ttu-id="ae350-132">日志记录</span><span class="sxs-lookup"><span data-stu-id="ae350-132">Logging</span></span>

<Need an intro paragraph here>

- <span data-ttu-id="ae350-133">与 Bing 流量中的 Microsoft 搜索相关的所有 Bing.com 搜索日志都与工作区标识不关联。</span><span class="sxs-lookup"><span data-stu-id="ae350-133">All Bing.com search logs that pertain to Microsoft Search in Bing traffic are disassociated from your workplace identity.</span></span>
- <span data-ttu-id="ae350-134">如果满足一组限制或频率阈值，则会使我们相信查询并不特定于特定的组织，该查询将按[隐私声明](https://privacy.microsoft.com/privacystatement)的 "搜索和智能化" 部分中所述进行处理。</span><span class="sxs-lookup"><span data-stu-id="ae350-134">If a set of restrictions or frequency thresholds are met which give us confidence that the query is not specific to a particular organization, the query will be treated as described in the Search and artificial intelligence section of the [Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="ae350-135">例如，此类查询将用于对公共功能（如 autosuggest 或相关搜索）进行建模和定型。</span><span class="sxs-lookup"><span data-stu-id="ae350-135">For example, such queries will be used to model and train public features, such as autosuggest or related searches.</span></span>
- <span data-ttu-id="ae350-136">不满足限制或频率阈值的查询将与公共的非 Microsoft 搜索流量分开存储。</span><span class="sxs-lookup"><span data-stu-id="ae350-136">Queries that do not meet the set of restrictions or frequency thresholds will be stored separately from public, non-Microsoft Search traffic.</span></span>

### <a name="advertising"></a><span data-ttu-id="ae350-137">广告</span><span class="sxs-lookup"><span data-stu-id="ae350-137">Advertising</span></span>

<span data-ttu-id="ae350-138">与工作区搜索相关的 Bing.com 上显示的广告与搜索查询的内容完全相关。</span><span class="sxs-lookup"><span data-stu-id="ae350-138">Advertising shown on Bing.com in connection with workplace searches is solely related to the content of the search queries.</span></span> <span data-ttu-id="ae350-139">绝对不会基于用户的工作区标识向其定向发布广告。</span><span class="sxs-lookup"><span data-stu-id="ae350-139">Ads are never targeted to users based on their workplace identity.</span></span>
     
## <a name="gdpr"></a><span data-ttu-id="ae350-140">GDPR</span><span class="sxs-lookup"><span data-stu-id="ae350-140">GDPR</span></span>

<span data-ttu-id="ae350-141">Microsoft [5 月21日的2018，](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)来自 Microsoft 的博客文章反映了我们对 GDPR 合规性的承诺，以及 Microsoft 如何帮助公司和组织遵守自己的 GDPR 合规性义务。</span><span class="sxs-lookup"><span data-stu-id="ae350-141">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations.</span></span> <span data-ttu-id="ae350-142">你可以在 Microsoft[信任中心常见问题解答](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)中找到其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="ae350-142">You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs).</span></span> 

<span data-ttu-id="ae350-143">针对客户的内部资源执行的 Microsoft Search 查询和返回的结果都被视为客户数据，因此，还可以满足在 "[信任中心" 常见问题解答](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)中反映的文章28中所述的处理器承诺。</span><span class="sxs-lookup"><span data-stu-id="ae350-143">Microsoft Search queries executed against a customer’s internal resources and results returned are considered Customer Data and, as such, also  meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs).</span></span> <span data-ttu-id="ae350-144">相对于 Microsoft Search 中转到公共 Bing 的查询，Microsoft 符合其 GDPR 义务作为数据控制器。</span><span class="sxs-lookup"><span data-stu-id="ae350-144">With respect to queries from Microsoft Search that go to public Bing, Microsoft complies with its GDPR obligations as a data controller.</span></span>

