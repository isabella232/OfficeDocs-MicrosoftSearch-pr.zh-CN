---
title: 安全与隐私Microsoft 搜索中必应
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
description: 保护公司数据和最终用户，同时向授权用户提供信息，Microsoft 搜索必应
ms.openlocfilehash: 181a06ecb9c009d03c71e3e7f8ecfc7d675faa659967bc6a6c1560513a45a5ac
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532674"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>安全与隐私Microsoft 搜索中必应

通过增强的隐私和安全措施，Microsoft 搜索必应帮助保护用户和工作区数据。

## <a name="secure-by-default"></a>默认处于保护状态

Microsoft 搜索请求必应 HTTPS 进行。 连接进行端到端加密，以增强安全性。
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Azure Active Directory 身份验证和授权

Microsoft 搜索中必应身份验证绑定到Azure Active Directory。 当用户Microsoft 搜索转到必应时，必应标头将显示 Microsoft 帐户以及工作或学校帐户的登录选项。 如果必应无法确定用户是否是符合条件的参与者，用户可以转到"浏览[Microsoft 搜索"](https://www.bing.com/business/explore)页面，在那里他们将自动重定向到组织的登录页面。

用户只能通过工作或学校帐户访问 Microsoft 搜索。他们需要使用与用于访问 SharePoint 或 Outlook 等 Office 365 服务相同的凭据登录。Microsoft 个人帐户不能用于登录 Microsoft 搜索。

## <a name="single-sign-on"></a>单一登录

如果用户已在其他服务（如 Outlook 或 SharePoint）中使用工作或学校帐户进行身份验证，当他们在同一浏览器中转到 必应 时，将自动登录到同一工作或学校帐户。 此外，当用户退出工作或学校帐户时，他们将自动从同一浏览器中的其他Microsoft Office登录。
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>通过浏览器与 Microsoft 云通信

当用户使用工作或学校帐户登录时，必应将必要的客户端库下载到浏览器以启用Microsoft 搜索结果。 然后，当他们进行搜索时，浏览器内代码调用Office 365云以获得工作结果。 为此，Microsoft 搜索专用 API，该 API 根据 SSAE 18 SOC2 类型 1 的控制目标运行。 这意味着，与在 必应 Office 365 Core Online Services 中处理工作结果本身相比，工作结果和工作数据不会通过比工作结果本身更严格的数据处理控制目标Office 365流。
  
## <a name="permissions"></a>权限

从 SharePoint 和 OneDrive for Business 等 Office 365 工作负载检索的工作结果在源上进行安全调整。用户不能查看无法通过 Office 365 查看和访问的 Word 文档或 PowerPoint 演示文稿等资源。他们只能在 SharePoint 中看到自己的文件以及作者显式或隐式（例如通过组成员身份）与之共享的文件。

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Microsoft 搜索必应工作区搜索

当用户在搜索查询中输入搜索Microsoft 搜索必应，将同时发生两个搜索请求：

- 对组织内部资源的搜索。
- 从 必应.com 单独搜索公共结果。

由于工作区搜索可能很敏感，Microsoft 搜索实施了一组信任措施，用于描述如何处理从 必应.com 单独搜索公共结果。

### <a name="logging"></a>日志记录

- 与必应流量中Microsoft 搜索的所有 必应.com 搜索日志必应工作区标识相关联。
- 如果满足一组限制或频率阈值，这使我们能够确定查询并非特定于特定组织，则查询将按隐私声明的搜索和人工智能部分所述[处理。](https://privacy.microsoft.com/privacystatement) 例如，此类查询将用于对公共功能（如自动建议或相关搜索）进行建模和训练。
- 不满足限制或频率阈值的查询将与公共的非 Microsoft 搜索流量分开存储。

### <a name="advertising"></a>广告

在 必应.com 上显示的与工作区搜索相关的广告仅与搜索查询的内容相关。 绝对不会基于用户的工作区标识向其定向发布广告。

## <a name="gdpr"></a>GDPR

[2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)年 5 月 21 日，Microsoft 的博客文章反映了我们对 GDPR 合规性的承诺，以及 Microsoft 如何帮助企业和组织履行自己的 GDPR 合规性义务。 可以在 Microsoft 信任中心常见问题解答 [中找到其他详细信息](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)。

Microsoft 搜索客户的内部资源和返回的结果执行的查询被视为客户数据，因此也符合信任中心常见问题解答中第 28 条中列出的处理者[承诺](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)。 对于来自公共Microsoft 搜索的必应，Microsoft 作为数据控制者遵守其 GDPR 义务。
