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
# <a name="frequently-asked-questions"></a>常见问题

下面列出了最常见的问题。

> [!TIP]
> 此处未列出你的问题的答案？ 请在本文的反馈中提出你的问题。

## <a name="is-advanced-query-understanding-supported"></a>是否支持高级查询理解？

是的，Microsoft 搜索分析来自较大短语的查询意图。 此功能使用 AI 了解用户添加到查询中而不会影响其搜索意图的常见多余短语。 例如，当用户搜索时，告诉我有关如何更改密码的更多信息时，我们会从查询中提取不太重要的字词，并基于更改密码等相关字词 *触发。*
  
此功能不会覆盖在 [Microsoft 365](https://admin.microsoft.com)管理中心 中设置的关键字。
  
## <a name="can-you-search-for-files-on-premises"></a>是否可以搜索本地文件？

是。 如果具有 [SharePoint](http://sharepoint.com/) 的混合部署，可以搜索本地 SharePoint 文件。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>如何将必应设置为我组织中的人员的默认搜索引擎？

下面是设置默认搜索引擎、默认主页和默认浏览器以为用户提供在必应中使用 Microsoft 搜索的最佳体验 [的说明](https://Bing.com)：

- [将 Microsoft Edge 设置为默认浏览器](/deployedge/edge-default-browser)
- [将必应设置为默认搜索引擎](set-default-search-engine.md)
- [将 Bing.com 设置为企业主页](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>我的搜索结果如何受到保护？

我们需要 [Azure Active Directory](/azure/active-directory/) 身份验证来访问受信任云中的结果。 通过身份验证的用户仅可查看其有权访问的内容。 搜索查询已取消标识，当您在必应中使用 Microsoft[](https://Bing.com)搜索时，日志会与公共必应搜索流量分隔开。

## <a name="can-i-search-across-federated-organizations"></a>能否跨联合组织进行搜索？

否。

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>在哪里可以获取有关 Office 365 安全、合规性和隐私的信息？

有关详细信息，请参阅 Office [365 的信任中心页面](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)。

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>用户能否通过其工作或学校帐户获得 Microsoft 奖励积分？

Microsoft 搜索需要企业用户使用工作或学校帐户登录。 但是，用户无法通过这些帐户登录到 Microsoft 奖励计划。 不过，也存在企业用户可能看到奖励积分累积的实例。 当 Microsoft 搜索用户拥有通过 [Microsoft 帐户](https://www.microsoft.com/welcome?rtc=1)创建的奖励帐户时，可能会出现此情况。 （与 Microsoft 帐户关联的电子邮件地址可以来自 Outlook.com、Hotmail.com、Gmail、Yahoo 或其他提供商。）如果用户在相同浏览器规划中使用其工作帐户和 Microsoft 帐户交替登录，则积分可能会累积到期奖励帐户。 通过清除 cookie，用户可以在使用 Microsoft 搜索进行搜索时停止累积积分。

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>来宾用户能否在我的组织中利用 Microsoft 搜索？

Microsoft 365 允许通过来宾访问与组织外部人员 [进行丰富的协作。](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) 这些用户将能够对文档、网站、组、列表和库执行搜索操作。 但是，来宾用户将不会获得完整的个性化 Microsoft 搜索体验，并且可能需要利用页面上的搜索框，而不是标头中的统一 Microsoft 搜索框。