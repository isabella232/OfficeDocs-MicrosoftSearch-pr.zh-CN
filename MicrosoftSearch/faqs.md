---
title: 常见问题
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 获取有关企业搜索和 Microsoft 搜索的常见问题解答
ms.openlocfilehash: 8b4de717ab63af8842dc86135748e551ff386a2a
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375681"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>常见问题

下面列出了最常见的问题。

> [!TIP]
> 此处未列出你的问题的答案？ 请在本文的反馈中提出你的问题。

## <a name="is-advanced-query-understanding-supported"></a>是否支持高级查询理解？

是的，Microsoft 搜索分析来自较大短语的查询意图。 此功能使用 AI 了解用户添加到查询中而不影响其搜索意图的常见多余短语。 例如，当用户搜索时，告诉我有关如何更改密码的更多信息时，我们会从查询中提取不太重要的字词，并基于更改密码等相关字词 *触发。*
  
此功能不会替代在"关键字"中设置的[Microsoft 365 管理中心。](https://admin.microsoft.com)
  
## <a name="can-you-search-for-files-on-premises"></a>是否可以搜索本地文件？

是。 如果具有混合部署[SharePoint，](http://sharepoint.com/)可以搜索本地部署SharePoint。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>如何将必应设置为我组织中的人员的默认搜索引擎？

下面是设置默认搜索引擎、默认主页和默认浏览器的说明，以便为用户提供在 必应 中获得最佳Microsoft 搜索[体验](https://Bing.com)：

- [将Microsoft Edge设置为默认浏览器](/deployedge/edge-default-browser)
- [将必应设置为默认搜索引擎](set-default-search-engine.md)
- [将 Bing.com 设置为企业主页](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>我的搜索结果如何受到保护？

我们需要[Azure Active Directory](/azure/active-directory/)身份验证来访问受信任云中的结果。 通过身份验证的用户仅可查看其有权访问的内容。 在Microsoft 搜索中必应时，将取消标识搜索查询，并且日志与公共搜索[必应分开。](https://Bing.com)

## <a name="can-i-search-across-federated-organizations"></a>能否跨联合组织进行搜索？

否。

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>在哪里可以获取有关安全Office 365和隐私的信息？

有关详细信息，请参阅"信任[中心"页面上Office 365。](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)

## <a name="can-guest-users-access-microsoft-search-in-my-organization"></a>来宾用户能否Microsoft 搜索我的组织中访问？

Microsoft 365通过来宾访问与组织外部人员进行[丰富的协作。](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) 这些用户可以搜索文档、网站、组、列表和库。 但是，来宾用户将不会获得完整的个性化 Microsoft 搜索 体验，并且可能需要使用页面搜索框，而不是标头中的统一 Microsoft 搜索 框。

## <a name="how-do-i-turn-microsoft-search-in-bing-on-or-off"></a>如何打开或Microsoft 搜索必应打开或关闭设备？

对于大多数组织（包括企业和教育组织Microsoft 搜索，必应默认为启用状态。 若要在Microsoft 搜索中必应配置"，请转到"配置"页Microsoft 365 管理中心。 [](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/configurations) Under Microsoft 搜索 in 必应 settings， choose **Change settings** and turn on Allow **your organization to use Microsoft 搜索 in 必应**. 此更改最多需要 24 小时才能生效。

如果此设置关闭，用户在搜索"搜索"或"搜索"必应Windows不会获得内部Microsoft Edge。 关闭Microsoft 搜索搜索必应不会停止或阻止将内部内容添加到搜索索引。 它仅禁用必应入口点Microsoft 搜索。 若要查找答案和内部结果，用户将需要使用其他入口点，例如 SharePoint Online 或 Office 365 应用。
