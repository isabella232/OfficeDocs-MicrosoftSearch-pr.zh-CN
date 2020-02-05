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
ms.openlocfilehash: 1acf4b5c4b3e771072ea67f4d807454723352c3f
ms.sourcegitcommit: c22e8c3dcc53857da677db98a1a2b7d5ca2c6170
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41721756"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>常见问题

下面列出了最常见的问题。

> [!TIP]
> 此处未列出你的问题的答案？ 请在本文的反馈中提出你的问题。

## <a name="is-advanced-query-understanding-supported"></a>是否支持高级查询理解？

是的，Microsoft Search 根据较大短语解析查询意图。此功能使用 AI 来了解用户在不影响其搜索意图的查询中添加的常见的多余短语。例如，当用户搜索 "*告诉我有关如何更改密码" 的详细信息*时，我们会从查询中提取不重要的词，并根据相关的更改密码（如 "*更改密码*"）进行触发。
  
此功能不会覆盖 Microsoft 365[管理中心](https://admin.microsoft.com)中设置的关键字。
  
## <a name="can-you-search-for-files-on-premises"></a>是否可以搜索本地文件？

是。 如果您具有 SharePoint 的混合部署，则可以搜索本地[SharePoint](http://sharepoint.com/)文件。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>如何将必应设置为我组织中的人员的默认搜索引擎？

以下是有关设置默认搜索引擎、默认主页和默认浏览器的说明，以便为用户提供 Microsoft Search in [Bing](https://Bing.com)的最佳体验：

- [将 Microsoft Edge 设置为默认浏览器](set-default-browser.md)
- [将必应设置为默认搜索引擎](set-default-search-engine.md)
- [将 Bing.com 设置为企业主页](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>我的搜索结果如何受到保护？

我们需要[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)身份验证才能访问受信任云中的结果。 通过身份验证的用户仅可查看其有权访问的内容。 对搜索查询进行取消标识，并将日志与公共[Bing](https://Bing.com)搜索流量分开。 此级别的保护在行业的其他地方均不可用。

## <a name="can-i-search-across-federated-organizations"></a>能否跨联合组织进行搜索？

否。

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>在哪里可以获取有关 Office 365 安全性、合规性和隐私的信息？

详细信息可在[Office 365 的 "信任中心" 页](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)上找到。

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>用户能否通过其工作或学校帐户获得 Microsoft 奖励积分？

Microsoft 搜索需要企业用户使用工作或学校帐户登录。 但是，用户无法通过这些帐户登录到 Microsoft 奖励计划。 不过，也存在企业用户可能看到奖励积分累积的实例。 当 Microsoft 搜索用户拥有通过 [Microsoft 帐户](https://www.microsoft.com/welcome?rtc=1)创建的奖励帐户时，可能会出现此情况。 （与 Microsoft 帐户关联的电子邮件地址可以来自 Outlook.com、Hotmail.com、Gmail、Yahoo 或其他提供商。）如果用户在相同浏览器规划中使用其工作帐户和 Microsoft 帐户交替登录，则积分可能会累积到期奖励帐户。 通过清除 cookie，用户可以在使用 Microsoft 搜索进行搜索时停止累积积分。
