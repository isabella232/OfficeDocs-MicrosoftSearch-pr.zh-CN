---
title: 在 Microsoft 搜索中管理首字母缩写词答案
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 在 Microsoft 搜索中创建和更新首字母缩写词答案
ms.openlocfilehash: 45d3cc7b33f27d2f4e77d8099fbfa91e01aabcbb
ms.sourcegitcommit: ef94ffd6111acb929c8343f0f4f82ea109b68fb6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122153"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>在 Microsoft 搜索中管理首字母缩写词答案

用户经常遇到其组织或团队使用的不熟悉的缩写词和缩写。 对于从一个团队移动到另一个团队、与内部合作伙伴团队合作或对组织而言是新术语的人，特定于组织或团队的术语可能是新的。

组织并不总是有一个标准术语参考。 缺少单一引用使查找这些首字母缩写词的定义或扩展变得困难。 Microsoft 搜索使用首字母缩略词解决了此问题。

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

1. **Admin-curated**. 由管理中心中的 IT [管理员提供](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)。
2. **系统所设计**。 Microsoft 搜索从用户的电子邮件和文档以及组织中公开的数据中发现。

### <a name="set-up-admin-curated-acronyms"></a>设置 Admin-curated 首字母缩略词

搜索管理员可以在 Microsoft 搜索管理中心的首字母缩写[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)词[选项卡上添加首字母缩写词](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。 可以将任何内部站点或存储库中的首字母缩写词添加到管理中心。 可以将这些缩写词添加到"已发布" **或** " **草稿"** 状态：

**已发布状态**。 通过 Microsoft 搜索，组织用户可以使用首字母缩写词。

> [!NOTE]
> 添加到已发布状态首字母缩略词在 Microsoft 搜索中可能最多需要三天。

**草稿状态**。 如果要在 Microsoft 搜索中提供首字母缩略词之前查看该缩写词，可以添加草稿状态中的首字母缩写词。 "草稿"状态中的首字母缩略词不会显示在搜索结果中。 您需要将缩写词移动到"已发布"状态，使其显示在搜索结果中。

可以单独添加首字母缩写词，也可以将其批量导入 CSV 文件中。 上载包含下表中所示字段的 CSV 文件：

| 首字母缩写词 (强制)  | 扩展 (强制)  | URL | 说明  | State (Mandatory)  | 上次修改时间 | 上次修改者 | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *拼写的缩写* | *Source* |  | *已发布或草稿* |  |  |  |

### <a name="csv-fields"></a>CSV 字段

**首字母缩略词**。 包含实际的短格式或首字母缩写。 例如 *，DNN*。

**展开**。 包含首字母缩略词的扩展。 例如， *深度神经网络*。

**说明**。 A brief description of the acronym that gives users more info about the acronym and its expansion. 例如， *深度神经网络* 是一个具有一定复杂度的神经网络，一个包含两层以上层的神经网络。

**源**。 您希望用户转到的页面或网站的 URL，以了解有关首字母缩写词详细信息。

**状态**。 此字段可以使用两个值：

- **草稿**。 将缩写词添加到"草稿"状态。
- **已发布**。 将缩写词添加到"已发布"状态，使其在 Microsoft 搜索中可用。

### <a name="system-curated-acronyms"></a>系统库缩略词

对于管理员来说，将组织中使用的所有首字母缩写词添加到"答案"可能是一个挑战。 此功能可以找到搜索管理员甚至不知道的首字母缩略词。 为完成这一工作，Microsoft 搜索还发现并特地从这些源中提供首字母缩略词：

- 用户的电子邮件
- [SharePoint、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive]( https://onedrive.live.com/about/)和[Microsoft OneNote 中的文档](https://www.onenote.com/)
- 用户在 SharePoint、OneDrive 或 OneNote 中有权访问的组织中公共文档

Microsoft 搜索确保只有具有文档访问权限和权限的用户才能看到从文档发现的缩写词。 在用户的邮箱中发现首字母缩写词时，只有该用户才能看到该缩写词。

> [!NOTE]
> 无需为管理员设置的首字母缩略词进行设置。

## <a name="frequently-asked-questions"></a>常见问题解答

**问：如何对管理员和系统选择的数据进行排名？**

**答：** 结果的排名可能因人而异，因为结果针对每个用户进行个性化设置。 这两个类别都不始终优先于其他类别。

**问：管理员编辑的首字母缩略词在 Microsoft 搜索中发布后需要多久才能显示？**

**答：**  添加到已发布状态首字母缩略词在 Microsoft 搜索中可用最多需要三天。

**问：用户如何触发首字母缩写词答案？**

**答**：若要获取首字母缩写词答案，用户必须在 [必应](https://bing.com)[、SharePoint](https://products.office.com/sharepoint/collaboration)或 [Office 365](https://Office.com)搜索框中输入特定的 **查询** 模式。

**问：接收或发送新电子邮件或文档后，系统选择缩写词需要多久显示？**

**答：** 新电子邮件或文档中的首字母缩略词最多需要 7 天时间显示在 Microsoft 搜索结果中。

**问：文档是否需要采用特定格式进行挖掘以选取它们？**

**答：** 不。 支持除图像、文件夹和 zip 文件之外的所有文件类型。

**问：Microsoft 会从所有语言的文档中发现首字母缩略词吗？**

**答**：Microsoft 仅支持从英语文档进行挖掘。 将分阶段添加对其他语言的支持。

**问：如果我的组织不想显示系统特有首字母缩略词，该做什么？能否在搜索结果中停止显示此类型的首字母缩写词？**

**答**：若要在搜索结果中关闭显示系统创建的首字母缩略词，请按照联系商业产品支持人员中的说明创建 [客户支持票证](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)。
创建支持票证后，系统创建的首字母缩略词最多需要 48 小时才能停止显示在搜索结果中。
