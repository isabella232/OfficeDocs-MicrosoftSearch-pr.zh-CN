---
title: 必应 Bing 中的 Microsoft 搜索的安全性和隐私
ms.author: jeffkizn
author: jeffkizn
manager: pmanek
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 在 Bing 中向具有 Microsoft 搜索的授权用户提供信息，保护贵公司的数据和最终用户
ms.openlocfilehash: 7f19327f3d62f68ed876875596610181b5f1bc0e
ms.sourcegitcommit: ac1209d11b8cc265d2224917fbe2a2bb0f65ef84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2020
ms.locfileid: "41005618"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>必应 Bing 中的 Microsoft 搜索的安全性和隐私

使用增强的隐私和安全措施，Bing 中的 Microsoft 搜索可帮助保护您的用户和工作区数据。

## <a name="secure-by-default"></a>默认处于保护状态

必应 Bing 请求中的 Microsoft Search 通过 HTTPS 进行。 该连接以端到端加密，以实现增强的安全性。
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Azure Active Directory 身份验证和授权

Bing 中 Microsoft Search 的身份验证绑定到 Azure Active Directory。 当 Microsoft 搜索用户转到 Bing 时，Bing 标头将显示 Microsoft 帐户的登录选项以及工作或学校帐户。 如果 Bing 无法确定用户是否为符合条件的参与者，则用户可以转到 "[浏览 Microsoft 搜索](https://www.bing.com/business/explore)" 页，它们将被自动重定向到组织的登录页。

用户只能通过工作或学校帐户访问 Microsoft 搜索。他们需要使用与用于访问 SharePoint 或 Outlook 等 Office 365 服务相同的凭据登录。Microsoft 个人帐户不能用于登录 Microsoft 搜索。

## <a name="single-sign-on"></a>单一登录

如果用户已通过其他服务（如 Outlook 或 SharePoint）中的工作或学校帐户进行身份验证，则当他们转到同一浏览器中的 Bing 时，他们将自动登录到相同的工作或学校帐户。 此外，当用户注销自己的工作或学校帐户时，他们将在同一浏览器中自动从其他 Microsoft Office 服务注销。
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>从浏览器与 Microsoft 云通信

当用户登录其工作或学校帐户时，必应会将必要的客户端库下载到浏览器中，以支持 Microsoft 搜索结果。然后，当他们搜索时，浏览器内的代码会调用 Office 365 云来获得工作结果。为此，Microsoft 搜索使用一个专用 API，该 API 根据 Office 365 [行业标准和法规的合规性框架](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf)（PDF 下载）符合 Tier C (SOC2 Type 1)。这意味着工作结果和工作数据永远不会流经不符合的必应系统。
  
## <a name="permissions"></a>权限

从 SharePoint 和 OneDrive for Business 等 Office 365 工作负载检索的工作结果在源上进行安全调整。用户不能查看无法通过 Office 365 查看和访问的 Word 文档或 PowerPoint 演示文稿等资源。他们只能在 SharePoint 中看到自己的文件以及作者显式或隐式（例如通过组成员身份）与之共享的文件。

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>必应 Bing 中的 Microsoft Search 保护工作区搜索

当用户在 Bing 的 Microsoft Search 中输入搜索查询时，将发生两个同时进行的搜索请求：

- 组织内部资源的搜索。
- 从 Bing.com 中单独搜索公共结果。

由于工作区搜索可能是敏感的，Microsoft Search 实现了一组信任措施，用于描述如何处理来自 Bing.com 的单独搜索的公共结果。

### <a name="logging"></a>日志记录

- 与 Bing 流量中的 Microsoft 搜索相关的所有 Bing.com 搜索日志都与工作区标识不关联。
- 如果满足一组限制或频率阈值，则会使我们相信查询并不特定于特定的组织，该查询将按[隐私声明](https://privacy.microsoft.com/privacystatement)的 "搜索和智能化" 部分中所述进行处理。 例如，此类查询将用于对公共功能（如 autosuggest 或相关搜索）进行建模和定型。
- 不满足限制或频率阈值的查询将与公共的非 Microsoft 搜索流量分开存储。

### <a name="advertising"></a>广告

与工作区搜索相关的 Bing.com 上显示的广告与搜索查询的内容完全相关。 绝对不会基于用户的工作区标识向其定向发布广告。

## <a name="gdpr"></a>GDPR

Microsoft [5 月21日的2018，](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)来自 Microsoft 的博客文章反映了我们对 GDPR 合规性的承诺，以及 Microsoft 如何帮助公司和组织遵守自己的 GDPR 合规性义务。 你可以在 Microsoft[信任中心常见问题解答](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)中找到其他详细信息。

针对客户的内部资源执行的 Microsoft Search 查询和返回的结果都被视为客户数据，因此，还可以满足在 "[信任中心" 常见问题解答](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)中反映的文章28中所述的处理器承诺。 相对于 Microsoft Search 中转到公共 Bing 的查询，Microsoft 符合其 GDPR 义务作为数据控制器。
