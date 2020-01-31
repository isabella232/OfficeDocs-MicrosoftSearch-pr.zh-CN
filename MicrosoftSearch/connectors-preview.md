---
title: 连接器预览
ms.author: mounika.narayanan
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 了解 microsoft Search 的 Microsoft Graph 连接器预览。
ms.openlocfilehash: 52bf174875bf3e262c0cb71d53ec209e481ee0b7
ms.sourcegitcommit: 1e8dc8e10722ed26ba85cbb5e8c9df62f3625de6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41578684"
---
# <a name="microsoft-graph-connectors-preview"></a>Microsoft Graph 连接器预览

Microsoft Graph 连接器和 Microsoft 搜索 Api （查询和索引）当前处于预览状态。 若要获取对连接器功能的访问权限，您必须通过提交<a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">Microsoft Graph 连接器预览注册表单</a>来请求加入预览计划。 这是一个早期预览，没有服务级别保证。 我们鼓励客户尝试连接器功能并提供反馈。 在预览期间，我们不建议使用连接器来实现生产目的。

## <a name="set-up-targeted-release"></a>设置目标版本
若要尝试连接器，必须为组织中的所有用户设置**目标 "发布**" 选项。 无论您选择以下哪种预览环境，目标发布要求均适用。
若要了解有关目标发布选项及其设置方式的详细信息，请参阅<a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">在 Office 365 中设置标准或目标发布选项</a>。

## <a name="choose-a-preview-environment"></a>选择预览环境 
若要尝试连接器、索引 Api 和搜索 Api，我们建议采用以下两种方法：
1. **测试租户**。  我们鼓励你使用测试租户尝试 Microsoft Graph 连接器预览。
2. **测试网站集**。 如果你没有测试租户，可以创建测试网站集以试用连接器功能。 若要在不影响组织中其他任何位置的搜索页的情况下显示连接器的结果，请自定义仅该网站集的搜索体验。

## <a name="preview-limitations"></a>预览限制
预览版本具有以下限制： 
* 每秒大约4个项目会限制摄取吞吐量。
* 不支持架构更新。 创建连接设置后，无法更新架构。 您只能删除并重新创建连接。
* 索引内容仅在 "自定义垂直" 下的 "搜索结果" 页面中显示。 此限制适用于具有自定义类型的内容。
* 在正式发行之前，您在预览期间设置的任何连接可能需要删除并重新创建。 如果这些连接与改进产品所做的更改不兼容，这些连接将不再起作用。
* 有一个连接限制。 每个租户最长可创建10个连接。
