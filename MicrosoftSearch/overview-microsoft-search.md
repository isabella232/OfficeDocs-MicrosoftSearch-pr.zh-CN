---
title: Microsoft 搜索概述
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
description: 概述 Microsoft Search 的内容、它的优势以及哪些应用支持 Microsoft 搜索。
ms.openlocfilehash: 28bd561e53bb1878c601a08e919e37f524a6470c
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626969"
---
# <a name="overview-of-microsoft-search"></a>Microsoft 搜索概述

Microsoft Search 可帮助你查找完成正在处理的内容所需的操作。 无论搜索的是用户、文件、组织结构图、网站还是常见问题的答案，您都可以在整个工作日使用 Microsoft 搜索来获取答案。

Microsoft 搜索可帮助用户找到正确的答案、人员和内容，以便在他们所使用的应用中完成其任务。

- 用户可获得与其搜索的应用的**上下文**相关的结果。 例如，当他们在[Microsoft Outlook](https://www.microsoft.com/outlook)中进行搜索时，他们会发现电子邮件，而不是[SharePoint](http://sharepoint.com/)网站。 在 SharePoint 中搜索时，他们可找到网站、页面和文件。
- 无论用户使用哪种应用，Microsoft 搜索都提供**个人**结果。 Microsoft Search 使用[Microsoft Graph](https://developer.microsoft.com/graph/)中的见解显示与每个用户相关的结果。 每个用户可能会看到不同的结果，即使他们搜索相同的字词。 他们只能看到其有权访问的结果，Microsoft 搜索不会更改权限。
- 用户无需记住信息所在的位置。 例如，用户在[Microsoft Word](https://products.office.com/word)中工作，并希望重用来自其[OneDrive](https://onedrive.live.com/about/)的同事共享的演示文稿中的信息。 无需切换到 OneDrive 并搜索该演示文稿，他们只需从 Word 搜索即可。
- 在[必应](https://bing.com)中，除了公共网页结果之外，用户还可以从组织内部获得结果。

## <a name="what-users-see"></a>用户看到的内容

在[Bing](https://bing.com)中，用户与 web 搜索使用相同的搜索框。 在 Office 应用程序中，用户会在标题栏中找到 Microsoft 搜索框。 其外观如下所示：

![标题栏中带有 Microsoft 搜索框的应用窗口的屏幕截图](media/Headings_520.png)

当用户在**搜索**框中单击时，搜索将根据其在 Office 365 中的前一个活动和基于您的组织中的趋势的内容来推荐结果。 他们最近处理的文件、最近使用的命令以及展开合作的人员都是搜索所考虑的活动示例。 当用户开始在**搜索**框中键入内容时，建议的结果更新。 用户可以从**搜索**框中直接打开搜索结果。 下面的示例展示了如何在[SharePoint](http://sharepoint.com/)中搜索。

![包含查询和建议结果的 Microsoft 搜索框的屏幕截图](media/SERP_text_520.png)

如果搜索框中的建议不是用户要查找的内容，请按**Enter**打开完整的结果列表。 他们可以使用元数据（例如最后修改项目的人员和时间、项目所在的位置以及预览）来确定这是否为其所查找的内容。

![Microsoft 搜索结果页面的屏幕截图](media/search_box.png)

## <a name="benefits-of-microsoft-search"></a>Microsoft 搜索的优点

**从任何 Microsoft 搜索框对整个 Microsoft 365 进行搜索** – 用户可以从任何 Microsoft 搜索框进行搜索，并快速回到正在执行的任务。 Microsoft Search 通过 Office 365 中的数据源（包括[SharePoint](http://sharepoint.com/)、 [Microsoft OneDrive For Business](https://onedrive.live.com/about/en-us/business/)和[microsoft Exchange Server](https://products.office.com/en-us/exchange/microsoft-exchange-server)）将结果汇集在一起。

**易于搜索**– Microsoft search 根据用户在 Office 365 中的前一个活动，在**搜索**框中直接提供建议结果。

**查找共享文件** – Microsoft 搜索使用高级查询理解功能让查找共享文件变得更简单。 用户可以轻松找到他们正在协作的文件。

**显示相关内容** – 提供用户完成任务所需的信息和答案，例如策略、权益、资源、工具等。 您还可以将特定的组作为目标，如新员工、远程工作人员或不同地理位置。

**跨所有应用进行管理** – 默认情况下，Microsoft 搜索处于**启用状态**，你所做的任何管理都将应用于所有应用中的 Microsoft 搜索。

## <a name="tailoring-microsoft-search-to-your-organization"></a>为你的组织定制 Microsoft 搜索

作为管理员，你可以为你的用户创建和奇妙的 Microsoft 搜索体验。 

**显示有用的内容**–答案提供快速、权威的结果，以根据关键字搜索查询。 [使内容易于查找](make-content-easy-to-find.md)。

**添加外部内容**-Microsoft Graph 连接器允许您将外部内容引入索引。 使用连接器丰富来自 Microsoft 365 外部的数据和文件的搜索体验。 [Microsoft Graph 连接器概述](connectors-overview.md)

**自定义用户体验**-您可以通过使用纵向和其他配置来自定义用户体验。 [自定义 Microsoft Search 页面](customize-search-page.md)

## <a name="what-content-is-searched"></a>搜索哪些内容？

Microsoft Search 显示您的组织已存储在 Microsoft 365 或通过连接器编制索引的内容。 Microsoft Search 不会跨租户搜索，也不会显示由其他组织共享的内容的结果。 如果你的组织已设置了使用云混合搜索的混合 SharePoint 环境，则 Microsoft 搜索将同时返回来自在线和本地 SharePoint 内容（包括已连接到 SharePoint Server 环境的任何外部内容）的搜索结果。 [详细了解混合搜索环境](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint)。

用户将获得从其他位置获取的相同企业级搜索结果，也会从 internet 获取结果。

## <a name="how-does-microsoft-search-work"></a>Microsoft 搜索如何工作？

当用户进行搜索时，Microsoft 搜索会处理查询并从较长的短语解析搜索意图，使用人工智能 (AI) 来了解用户添加到查询的常见多余短语，这些短语不影响他们的搜索意图。 例如，当用户搜索“如何更改密码”时，我们会从查询中提取不太重要的字词，并根据“更改密码”等相关字词进行触发。  
用户**有权**查看的搜索结果将显示在搜索结果页面上。 Microsoft 搜索使用智能排名算法根据相关性对结果进行排序。

## <a name="microsoft-search-in-bing-protects-enterprise-searches"></a>必应中的 Microsoft 搜索可以保护企业搜搜

当用户在 Bing 的 Microsoft Search 中输入搜索查询时，将发生两个同时进行的搜索请求：

- 组织内部资源的搜索。
- 从 Bing.com 中单独搜索公共结果。 

由于企业级搜索可能是敏感的，Microsoft Search 实现了一组信任措施，用于描述如何处理单独搜索的公共`Bing.com`结果。

### <a name="logging"></a>日志记录
 - 所有`Bing.com`与 Bing 流量中的 Microsoft 搜索相关的搜索日志都与工作区标识不关联。
- 如果满足一组限制或频率阈值，让我们相信查询并不特定于特定组织，则将按照[隐私声明](https://privacy.microsoft.com/privacystatement)的必应服务部分中所述对查询进行处理。 例如，此类查询将用于对公共功能（如 autosuggest 或相关搜索）进行建模和定型。
- 不满足限制或频率阈值的查询将与公共的非 Microsoft 搜索流量分开存储。
### <a name="advertising"></a>广告 
与企业级`Bing.com`搜索一起显示在中的广告与搜索查询的内容完全相关。 绝对不会基于用户的工作区标识向其定向发布广告。

## <a name="see-also"></a>另请参阅

[设置 Microsoft 搜索](setup-microsoft-search.md)

[使内容易于查找](make-content-easy-to-find.md)
