---
title: 在"管理"中管理首字母Microsoft 搜索
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 创建和更新首字母缩略词在Microsoft 搜索
ms.openlocfilehash: b7b3272ba98bbce7d43562811389df0a35e9f7a2
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375652"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>在"管理"中管理Microsoft 搜索

用户经常遇到他们组织或团队使用的不熟悉的缩写词和缩写。 对于从一个团队移动到另一个团队、与内部合作伙伴团队合作或对组织而言是新人，特定于组织或团队的术语可能是新术语。

组织并不总是有一个有关其标准术语的参考。 缺少单一引用使查找这些首字母缩写词的定义变得困难。 Microsoft 搜索首字母缩略词解决该问题。

## <a name="what-users-experience"></a>用户体验

Microsoft 搜索用户可以使用 必应、SharePoint、Office 365、Outlook 网页版、Outlook Mobile (Android [](https://products.office.com/sharepoint/collaboration)) 以及[Teams](https://Bing.com)Mobile (iOS 和 Android) 中的首字母缩略词获取定义。 [](https://Office.com) 在 **"搜索** "框中，用户输入类似以下示例的查询：

- *什么是* DNN
- *定义* DNN
- DNN *定义*
- *展开* DNN
- DNN *扩展*
- *的含义* DNN
- DNN *表示*
- DNN *代表*

结果包括存在于用户组织内部的 DNN 的所有含义。

> [!NOTE]
> 用户必须输入包含首字母缩写词的指定关键字的查询，才能触发其对应的答案。 首字母缩略词查询不区分大小写。

## <a name="set-up-acronyms-answers"></a>设置首字母缩写词答案

在 ["Microsoft 365 管理中心"](https://admin.microsoft.com)中，转到 [**"首字母缩**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)略词"，然后选择"**添加首字母缩写词"。**

Microsoft 搜索查询两个数据源，以提供用户搜索的首字母缩写词答案：

1. **管理员所策展**。 由管理中心中的 IT [管理员提供](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)。
2. **System-curated**. 通过Microsoft 搜索用户的电子邮件和文档以及组织中公开可用的数据发现。

### <a name="set-up-admin-curated-acronyms"></a>设置管理员策展的首字母缩写词

搜索管理员可以在管理中心的"首字母缩略词"[选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)上Microsoft 搜索[首字母缩写词](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。 可以将任何内部站点或存储库中的首字母缩写词添加到管理中心。 这些首字母缩写词可以添加到 **已发布或****草稿** 状态：

**已发布状态**。 组织的用户可以通过以下方式使用缩写Microsoft 搜索。

> [!NOTE]
> 添加到 Published 状态中的缩写词最多需要一天的时间，Microsoft 搜索。

**草稿状态**。 如果要在将缩写词用于"草稿"Microsoft 搜索，可以在"草稿"状态中添加缩写词。 "草稿"状态中的缩写词不会显示在搜索结果中。 您需要将缩写词移动到"已发布"状态，使其出现在搜索结果中。

**已排除状态**。 如果要防止首字母缩略词出现在Microsoft 搜索，请使用排除首字母缩略词来添加它。  若要阻止排除首字母缩略词，需要删除已排除的首字母缩写词并添加它或验证它是否位于已发布列表中。

可以单独添加首字母缩写词，或在 CSV 文件中批量导入它们。 Upload包含下表中所示字段的 CSV 文件：

| 首字母缩写 (强制)  | 代表 (强制)  | URL | 描述  | 州 (强制)  | 上次修改时间 | 上次修改者 | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *拼写出缩写* | *Source* |  | *已发布、草稿或已排除* |  |  |  |

### <a name="csv-fields"></a>CSV 字段

**首字母缩略词**。 包含实际的短格式或缩写。 例如 *DNN*。

**代表**。 包含首字母缩写词的定义。 例如， *深度神经网络*。

**说明**。 A brief description of the acronym that gives users more info about the acronym and its definition. 例如， *深度神经网络* 是一个具有一定复杂度的神经网络，一个包含两层以上层的神经网络。

**源**。 您希望用户访问的页面或网站的 URL，以了解有关缩写词详细信息。

**状态**。 此字段可以使用两个值：

- **草稿**。 将缩写词添加到"草稿"状态。
- **已发布**。 将缩写词添加到 Published 状态，使其在"发布Microsoft 搜索。
- **已排除**。 将缩写词添加到"已排除"状态，并阻止它显示在Microsoft 搜索。

### <a name="system-curated-acronyms"></a>系统缩略词

对于管理员来说，将组织中使用的所有缩写词添加到"答案"可能是一个挑战。 此功能可以找到搜索管理员甚至都不知道的缩写词。 为此，Microsoft 搜索发现和选择这些源中的首字母缩写词：

- 用户的电子邮件
- 文档[](https://products.office.com/sharepoint/collaboration)[SharePoint、Microsoft OneDrive]( https://onedrive.live.com/about/)[和](https://www.onenote.com/)Microsoft OneNote
- 组织中用户有权访问的公用文档SharePoint、OneDrive或OneNote

Microsoft 搜索确保只有具有文档访问权限和权限的用户才能看到从文档发现的缩写词。 在用户的邮箱中发现首字母缩写词时，只有该用户才能看到该缩写词。

> [!NOTE]
> 无需为系统策展的首字母缩略词进行设置。

## <a name="frequently-asked-questions"></a>常见问题解答

**问：如何对管理员和系统选择的数据进行排名？**

**答：** 结果的排名可能因人而异，因为结果针对每个用户进行个性化设置。 这两个类别都不始终优先于其他类别。

**问：用户如何触发首字母缩写词答案？**

**答：** 若要获取首字母缩写词答案，用户必须在 [必应、SharePoint、Office 365、Outlook 网页版、Outlook](https://bing.com)Mobile [](https://products.office.com/sharepoint/collaboration) (Android [](https://Office.com)) 或 Teams Mobile (iOS 和 Android) 搜索框中输入特定查询 **模式**。

**问：用户在搜索时能否只输入缩写词？**

**答：** 在必应，用户现在只需搜索首字母缩略词就可以找到首字母缩写词答案，而不再需要关键字。 此相同体验将分阶段为其他Microsoft 搜索入口点启用。

**问：管理员策展的首字母缩略词在发布后Microsoft 搜索需要多久？**

**答：** 添加到 Published 状态中的缩写词最多需要一天的时间，Microsoft 搜索。

**问：接收或发送新电子邮件或文档后，系统选择缩写词需要多久显示？**

**答：** 新电子邮件或文档中找到的首字母缩写词最多需要 7 天时间显示在Microsoft 搜索结果中。

**问：如果首字母缩写词被排除并发布，会发生什么情况？**

**答：** 排除的首字母缩略词将赋予优先级，并阻止已发布的首字母缩略词出现在搜索结果中。 它不会删除或移除已发布的缩写词。

**问：首字母缩略词从结果中排除需要Microsoft 搜索？**

**答：** 排除的首字母缩写词最多需要一天的时间停止显示在搜索结果中。

**问：对于系统策展的首字母缩略词，文档是否需要采用特定格式？**

**答：** 不。 我们支持除图像、文件夹和 zip 文件之外的所有文件类型。

**问：Microsoft 会从所有语言的文档中发现缩写词吗？**

**答：** Microsoft 仅支持来自英语、西班牙语、法语、意大利语、德语和葡萄牙语文档的系统特意缩写词。 将阶段性地添加对其他语言的支持。

**问：如果我的组织不想显示系统特用首字母缩略词，该做什么？能否在搜索结果中停止显示此类型的首字母缩写词？**

**答：** 若要在搜索结果中关闭显示系统创建的首字母缩写词，请按照联系商业产品支持人员中的说明创建客户支持 [票证](/microsoft-365/admin/contact-support-for-business-products)。
创建支持票证后，系统创建的首字母缩略词最多需要 48 小时才能停止显示在搜索结果中。
