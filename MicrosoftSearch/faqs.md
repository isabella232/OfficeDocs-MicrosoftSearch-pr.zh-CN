---
title: 常见问题
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/19/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: cd3ee09d-58ab-4b8a-8822-fa11a1399672
ROBOTS: NoIndex
description: 获取有关企业搜索和 Microsoft 搜索的常见问题解答
ms.openlocfilehash: 58fb45eec5cc354a6228fb552a3dcda28c2b2367
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591500"
---
# <a name="faqs"></a>常见问题

这些是组织和用户关于管理和使用 Microsoft 搜索的常见问题。

> [!IMPORTANT]
> 本文适用于 Microsoft 必应搜索管理门户。 我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将其删除。 我们建议你使用 Microsoft 365 管理中心快速开始。 [Microsoft 搜索概述](overview-microsoft-search.md)。
  
## <a name="whats-the-value-proposition-for-microsoft-search"></a>Microsoft 搜索的价值主张是什么？

Microsoft 搜索是搜索工作和 Web 内容的一种安全方式。这种跨 Web 和企业的集成只适用于 Microsoft。有关合规性信息，请参阅 [Microsoft 搜索安全性](security.md)。
  
## <a name="what-microsoft-search-features-are-available-now"></a>现在提供了哪些 Microsoft 搜索功能？

有关完整列表，请参阅 [Microsoft 搜索功能](features.md)。
  
## <a name="does-microsoft-search-support-advanced-query-understanding"></a>Microsoft 搜索是否支持高级查询理解？

是的，Microsoft 搜索分析来自较大短语的查询意图。此功能使用 AI 来学习用户在查询中添加的不影响其搜索意图的常见多余短语。例如，当用户搜索“请告诉我更多关于如何更改密码的信息”时，我们会从查询中提取不太重要的字词，并根据“更改密码”等相关字词进行触发。
  
此功能不会覆盖管理门户中设置的关键字。
  
## <a name="does-microsoft-search-search-for-files-on-premises-as-well-as-the-cloud"></a>Microsoft 搜索是否搜索本地和云文件？

Microsoft 搜索支持搜索 SharePoint Online、OneDrive for Business 上的文件，以及混合本地 SharePoint 和 SharePoint Online 上最常见的 Office 文件类型。如果可以在 SharePoint Online 上搜索本地内容，应该能够使用 Microsoft 搜索找到本地内容。 
  
## <a name="does-microsoft-search-replace-other-enterprise-search-experiences"></a>Microsoft 搜索是否取代了其他企业搜索体验？

Microsoft 搜索是一项互补产品/服务，将多个来源的搜索结果汇集在一起。有关支持的文件类型和来源的更多信息，请参见下一个常见问题解答。
  
## <a name="what-file-types-and-sources-does-microsoft-search-support"></a>Microsoft 搜索支持哪些文件类型和源？

我们支持以下内容源：
  
- SharePoint Online
    
- 混合 SharePoint（本地 + SPO）
    
- OneDrive for Business
    
以下文件类型出现在“文件搜索”中，并显示在“人员和组”的“文件”选项卡中：
  
- Word
    
- Excel
    
- PowerPoint
    
- OneNote
    
- PDF
    
## <a name="what-compliance-and-trust-measures-are-in-place-for-microsoft-search"></a>Microsoft 搜索采取了哪些合规性和信任措施？

有关合规性和信任措施的信息，请参阅 [Microsoft 搜索的安全性](security.md)。
  
## <a name="where-can-i-get-info-about-office-365-compliance-tierscategories"></a>我可以从哪里获得有关 Office 365 合规性层/类别的信息？

可在[针对行业标准和法规的合规性框架](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)（PDF 下载）中找到详细信息。 
  
## <a name="how-does-microsoft-search-keep-results-secure"></a>Microsoft 搜索如何保证结果的安全？

有关 Microsoft 搜索如何保证结果安全的信息，请参阅 [Microsoft 搜索安全性](security.md)。
  
## <a name="what-are-the-content-sources-for-the-people-card"></a>人员卡片的内容源有哪些？

人员卡片从 Azure Active Directory、Exchange Online 和 SharePoint Online 获取信息。
  
## <a name="do-microsoft-search-users-earn-microsoft-rewards"></a>Microsoft 搜索用户能否获得 Microsoft Rewards ？

Microsoft 搜索不会获得 Rewards 点数，也不会与用户的 Microsoft 帐户相关联。
  
## <a name="does-microsoft-search-respect-existing-file-permissions"></a>Microsoft 搜索是否重视现有文件权限？

Microsoft 搜索重视来自源的安全修整。用户只能看到他们有权访问的信息。
  
## <a name="how-are-user-queries-protected-from-sharing-on-the-web"></a>如何防止在 Web 上共享用户查询？

有关如何保护用户查询的信息，请参阅 [Microsoft 搜索安全性](security.md)。
  
## <a name="what-types-of-advertising-do-microsoft-search-users-see"></a>Microsoft 搜索用户会看到哪些类型的广告？

有关广告信息，请参阅 [Microsoft 搜索安全性](security.md)。
  
## <a name="what-are-the-minimum-requirements-to-enable-microsoft-search"></a>启用 Microsoft 搜索的最低要求是什么？

有关要求的信息，请参阅 [Microsoft 搜索要求](requirements.md)。
  
## <a name="how-does-microsoft-search-use-azure-active-directory"></a>Microsoft 搜索如何使用 Azure Active Directory？

Microsoft 搜索使用 Azure Active Directory 验证和授权对公司数据的访问。Microsoft 搜索符合所有 Microsoft 产品的标识处理实践标准。这意味着用户可以通过单一登录自动登录。 
  
## <a name="how-do-i-set-bing-as-the-default-search-provider-for-my-users"></a>如何将必应设置为用户的默认搜索提供程序？

有关此信息，请参阅[设置默认搜索引擎](set-default-search-engine.md)、[设置默认主页](set-default-homepage.md)和[设置默认浏览器](set-default-browser.md)。
  
## <a name="does-microsoft-search-provide-search-results-across-tenants"></a>Microsoft 搜索是否在租户之间提供搜索结果？

否，不支持跨租户或共享租户访问。 
  
## <a name="where-can-i-get-help-with-keywords-and-reserved-keywords"></a>在何处可以获得有关关键字和保留关键字的帮助？

有关使用关键字和保留关键字的信息，请参阅[规划内容](plan-your-content.md)。
  
## <a name="which-office-365-skus-are-supported"></a>支持哪些 Office 365 SKU？

有关支持的 SKU 的信息，请参阅 [Microsoft 搜索要求](requirements.md)。
  
## <a name="is-microsoft-search-gdpr-compliant"></a>是否符合 Microsoft 搜索 GDPR？

有关 GDPR 符合性信息，请参阅 [Microsoft 搜索安全性](security.md)。
  
## <a name="why-am-i-signed-into-bing-automatically"></a>为什么我会自动登录必应？

Microsoft 搜索使用 AAD 单一登录功能，当你登录 Office 365 应用或 Windows 10 时，它会自动通过你的工作或学校帐户进行登录。可以随时注销。
  
## <a name="what-is-bing-for-business"></a>什么是 Bing for Business？

Microsoft 搜索以前称为 Bing for Business。
  
## <a name="how-does-microsoft-search-order-result-cards-in-the-all-results-carousel"></a>Microsoft 搜索如何在所有结果传送中对结果卡片进行排序？

Microsoft 搜索使用智能排名算法根据相关性对结果卡进行排序。

  

