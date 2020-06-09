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
ms.openlocfilehash: 4bcd8360957be69bc701e8b356cd222de32bfc5f
ms.sourcegitcommit: 64eea81f8c1db9ee955013462a7b51612fb7d0b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "44604380"
---
# <a name="microsoft-graph-connectors-preview"></a>Microsoft Graph 连接器预览

Microsoft Graph 连接器和 Microsoft 搜索 Api （查询和索引）当前处于预览状态。 若要获取对连接器功能的访问权限，必须在租户中启用目标发布选项。 这是一个早期预览，没有服务级别保证。 我们鼓励客户尝试连接器功能并提供反馈。 在预览期间，我们不建议使用连接器来实现生产目的。

## <a name="set-up-targeted-release"></a>设置目标版本

若要尝试连接器，必须为组织中的所有用户设置**目标 "发布**" 选项。 若要了解有关目标发布选项及其设置方式的详细信息，请参阅[在 Office 365 中设置标准或目标发布选项](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)。

## <a name="choose-a-preview-environment"></a>选择预览环境

若要尝试连接器、索引 Api 和搜索 Api，我们建议采用以下两种方法：

1. **测试租户**。  我们鼓励你使用测试租户尝试 Microsoft Graph 连接器预览。

2. **测试网站集**。 如果你没有测试租户，可以创建测试网站集以试用连接器功能。 若要在不影响组织中其他任何位置的搜索页的情况下显示连接器的结果，请自定义仅该网站集的搜索体验。

## <a name="preview-limitations"></a>预览限制

预览版本具有以下限制：

* 每秒大约4个项目会限制摄取吞吐量。

* 不支持架构更新。 创建连接设置后，无法更新架构。 您只能删除并重新创建连接。

* 索引内容仅在 "自定义垂直" 下的 "搜索结果" 页面中显示。 此限制适用于具有自定义类型的内容。

* 可能需要删除并重新创建在预览期间设置的任何连接。 如果这些连接与改进产品所做的更改不兼容，这些连接将不再起作用。

* 有一个连接限制。 每个租户最长可创建10个连接。

* 源存储库大小。 我们建议您预览具有大约200000项目的来源库的连接器，因为这是我们经过测试的搜索比例限制。 我们正在努力改进搜索性能，我们希望在不久的将来支持更大的存储库大小。

* "编辑对连接的支持" 不可用。 一旦创建了连接，就不能再对其进行编辑或更改。 如果需要更改任何详细信息，则必须删除并重新创建连接。

* 仅可在自定义纵向搜索连接器内容。

* 仅一个连接中的连接器内容可以在每个自定义垂直中显示，并且需要创建结果类型。
