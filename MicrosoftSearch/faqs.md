---
title: 常见问题
ms.author: anfowler
author: adefowler
manager: shohara
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
ms.openlocfilehash: 3b30980c76915405767381fb3b6397468bdd1b68
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639495"
---
# <a name="frequently-asked-questions"></a>常见问题

下面列出了最常见的问题。

> [!TIP]
> 此处未列出你的问题的答案？ 请在本文的反馈中提出你的问题。

## <a name="is-advanced-query-understanding-supported"></a>是否支持高级查询理解？

是的，Microsoft 搜索分析来自较大短语的查询意图。此功能使用 AI 来学习用户在查询中添加的不影响其搜索意图的常见多余短语。例如，当用户搜索“请告诉我更多关于如何更改密码的信息”时，我们会从查询中提取不太重要的字词，并根据“更改密码”等相关字词进行触发。
  
此功能不会覆盖管理中心中设置的关键字。
  
## <a name="can-you-search-for-files-on-premises"></a>是否可以搜索本地文件？

是。 如果有 SharePoint 的混合部署，则可以搜索本地 SharePoint 文件。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>如何将必应设置为我组织中的人员的默认搜索引擎？

以下说明介绍了如何设置默认搜索引擎、默认主页和默认浏览器，以便用户在使用必应中的 Microsoft 搜索时获得最佳体验：

- [将 Edge 设置为默认浏览器](set-default-browser.md)
- [将必应设置为默认搜索引擎](set-default-search-engine.md)
- [将 Bing.com 设置为企业主页](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a>我的搜索结果如何受到保护？

我们要求通过 Azure Active Directory (AAD) 身份验证才能访问来自受信任云的结果。 通过身份验证的用户仅可查看其有权访问的内容。 搜索查询会被取消标识，且日志会与公共必应搜索流量分隔开来。 此级别的保护在行业的其他地方均不可用。

## <a name="can-i-search-across-federated-organizations"></a>能否跨联合组织进行搜索？

否。

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a>从哪里可以获得有关 Office 365 和 Microsoft 365 合规性层和类别的信息？

可在[针对行业标准和法规的合规性框架](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)（PDF 下载）中找到详细信息。