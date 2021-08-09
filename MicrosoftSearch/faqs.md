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
ms.openlocfilehash: 94161d3ac53ca72a9f8298674a53fdaa0a80caaf5ca3802d47ea693043a30530
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533929"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>常见问题

下面列出了最常见的问题。

> [!TIP]
> 此处未列出你的问题的答案？ 请在本文的反馈中提出你的问题。

## <a name="is-advanced-query-understanding-supported"></a>是否支持高级查询理解？

是的，Microsoft 搜索分析来自较大短语的查询意图。 此功能使用 AI 了解用户添加到查询中而不会影响其搜索意图的常见多余短语。 例如，当用户搜索时，告诉我有关如何更改密码的更多信息时，我们会从查询中提取不太重要的字词，并基于更改密码等相关字词 *触发。*
  
此功能不会替代在关键字集合中设置的[Microsoft 365 管理中心。](https://admin.microsoft.com)
  
## <a name="can-you-search-for-files-on-premises"></a>是否可以搜索本地文件？

是。 如果具有混合部署[SharePoint，](http://sharepoint.com/)可以搜索本地部署SharePoint。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>如何将必应设置为我组织中的人员的默认搜索引擎？

下面提供了设置默认搜索引擎、默认主页和默认浏览器的说明，以便为用户提供在 必应 中Microsoft 搜索[体验](https://Bing.com)：

- [将Microsoft Edge设置为默认浏览器](/deployedge/edge-default-browser)
- [将必应设置为默认搜索引擎](set-default-search-engine.md)
- [将 Bing.com 设置为企业主页](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>我的搜索结果如何受到保护？

我们需要[Azure Active Directory](/azure/active-directory/)身份验证来访问受信任云中的结果。 通过身份验证的用户仅可查看其有权访问的内容。 搜索查询已取消标识，当您在搜索流中[必应搜索流量](https://Bing.com)时，日志Microsoft 搜索公共必应。

## <a name="can-i-search-across-federated-organizations"></a>能否跨联合组织进行搜索？

否。

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>在哪里可以获取有关安全Office 365和隐私的信息？

有关详细信息，请参阅"信任[中心"页面上Office 365。](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>来宾用户能否利用Microsoft 搜索中的功能？

Microsoft 365通过来宾访问与组织外部人员进行[丰富的协作。](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) 这些用户将能够对文档、网站、组、列表和库执行搜索操作。 但是，来宾用户将不会获得完整、个性化的Microsoft 搜索体验，并且可能需要利用页面搜索框，而不是标头中的统一 Microsoft 搜索 框。