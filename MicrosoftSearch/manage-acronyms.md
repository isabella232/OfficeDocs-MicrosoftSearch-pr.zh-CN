---
title: 在 Microsoft 搜索中管理首字母缩写词答案
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
description: 在 Microsoft 搜索中创建和更新首字母缩略词解答
ms.openlocfilehash: 9de9de8287e3ddf206f93f53573922f3cf526580
ms.sourcegitcommit: ad225af81060a2e3d7e4c953eeb6977d54698b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709679"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>在 Microsoft 搜索中管理首字母缩写词答案

用户经常遇到其组织或团队使用的不熟悉的缩写词和缩写。 对于从一个团队移动到另一个团队、与内部合作伙伴团队合作或对组织而言是新术语的人，特定于组织或团队的术语可能是新的。

组织并不总是有一个标准术语参考。 缺少单个引用使查找这些首字母缩写词的定义或扩展变得困难。 Microsoft 搜索使用首字母缩略词解决了此问题。

## <a name="what-users-experience"></a>用户体验

Microsoft 搜索用户可以使用[必应](https://Bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)和[Office 365](https://Office.com)中的首字母缩略词获取定义。 在 **"搜索** "框中，用户输入类似以下示例的查询：

- *什么是* DNN
- *定义* DNN
- DNN *定义*
- *展开* DNN
- DNN *扩展*
- *含义* DNN
- DNN *表示*

结果包括存在于用户组织内部的 DNN 的所有含义。

> [!NOTE]
> 用户必须输入包含首字母缩写词指定关键字的查询，才能触发其对应的答案。 首字母缩略词查询不区分大小写。

## <a name="set-up-acronyms-answers"></a>设置首字母缩写词答案

在 [Microsoft 365 管理中心](https://admin.microsoft.com)中，转到 [**首字母**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)缩略词，然后选择"添加 **首字母缩写词"。**

Microsoft 搜索查询两个数据源，以提供用户搜索的首字母缩略词解答：

1. **编辑首字母缩略词**。 由管理中心中的 IT [管理员提供](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)。
2. **缩写首字母缩略词**。 由 Microsoft 搜索从用户的个人电子邮件和文档以及组织中公开的数据中缩小。

### <a name="set-up-editorial-acronyms"></a>设置编辑首字母缩略词

搜索管理员可以在 Microsoft 搜索管理中心的首字母缩写词 [选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) 上设置  [编辑首字母缩略词](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。 可以将任何内部站点或存储库中的首字母缩写词添加到管理中心。 可以将编辑首字母缩略词添加到"已发布" **或** " **草稿"** 状态：

**已发布状态**。 通过 Microsoft 搜索，组织的员工可以使用缩写词。

> [!NOTE]
> 添加到已发布状态首字母缩略词在 Microsoft 搜索中可能最多需要三天。

**草稿状态**。 如果管理员想要在 Microsoft 搜索中提供首字母缩略词答案之前查看它们，他们可以将首字母缩写词添加到"草稿"状态。 添加到草稿状态中的首字母缩写词在 Microsoft 搜索中不可用。 管理员需要将缩写词添加到已发布状态，使其可用。

管理员可以单独添加首字母缩写词或在 CSV 文件中批量导入它们。 上载包含下表中所示字段的 CSV 文件：

| 首字母缩略 (强制)  | 扩展 (强制)  | 说明  | Source | 州 (强制)  |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *拼写的缩写* |  | *URL* | *已发布或草稿* |

### <a name="csv-fields"></a>CSV 字段

**首字母缩略词**。 包含实际的短格式或缩写。 例如 *，DNN*。

**展开**。 包含首字母缩略词的扩展。 例如， *深度神经网络*。

**说明**。 A brief description of the acronym that gives users more info about the acronym and its expansion. 例如， *深度神经网络* 是一个具有一定复杂度的神经网络，一个包含两层以上层的神经网络。

**源**。 您希望用户转到的页面或网站的 URL，以了解有关首字母缩写词详细信息。

**状态**。 此字段可以使用两个值：

- **草稿**。 将缩写词添加到"草稿"状态。
- **已发布**。 将缩写词添加到"已发布"状态，使其在 Microsoft 搜索中可用。

### <a name="mined-acronyms"></a>Mined 首字母缩略词

对于管理员来说，将组织中使用的所有首字母缩写词添加到"答案"可能是一个挑战。 此功能可以找到搜索管理员甚至不知道的首字母缩略词。 为完成该工作，Microsoft 搜索还从这些源中输入缩写词：

- 用户的电子邮件。
- [SharePoint、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive]( https://onedrive.live.com/about/)和[Microsoft OneNote 中的文档](https://www.onenote.com/)。
- 用户在 SharePoint、OneDrive 或 OneNote 中有权访问的组织中公共文档。

Microsoft 搜索确保只有具有文档访问权限和权限的用户才能看到从文档获取的缩写词。 从用户的邮箱中缩小首字母缩写词时，只有该用户才能看到该缩写词。

> [!NOTE]
> 无需为缩写首字母缩略词进行设置。

## <a name="frequently-asked-questions"></a>常见问题解答

**问：如何对编辑和缩小数据进行排名？**

**答：** 结果的排名可能因人而异，因为结果针对每个用户进行个性化设置。

**问：编辑首字母缩写词在 Microsoft 搜索中发布后需要多久才能显示？**

**答：**  添加到"已发布"状态首字母缩写词在 Microsoft 搜索中最多需要三天的时间。

**问：用户如何触发首字母缩略词答案？**

**答**：若要获取首字母缩写词答案，用户必须在 [必应](https://bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)或 [Office 365 搜索](https://Office.com)框中输入特定 **查询** 模式。

**问：接收或发送新电子邮件或文档后，显示缩略词需要多久？**

**答：** 来自新电子邮件或文档的缩写缩写词最多需要 7 天时间显示在 Microsoft 搜索结果中。

**问：文档是否需要采用特定格式进行挖掘以选取它们？**

**答：** 不。 支持除图像、文件夹和 zip 文件之外的所有文件类型。

**问：Microsoft 会从所有语言的文档中挖掘首字母缩写词吗？**

**答**：Microsoft 仅支持从英语文档进行挖掘。 将分阶段添加对其他语言的支持。

**问：如果我的组织不想显示缩略词，该做什么？我能否停止在搜索结果中显示缩略词？**

**答**：若要在搜索结果中关闭显示缩略缩略词，请按照有关业务产品的联系人支持人员的说明创建 [客户支持票证](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)。
创建支持票证后，最多需要 48 小时才能在搜索结果中停止显示缩略词。
