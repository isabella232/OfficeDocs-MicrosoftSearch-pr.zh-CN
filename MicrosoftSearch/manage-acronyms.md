---
title: 在 Microsoft Search 中管理首字母缩写应答
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
description: 在 Microsoft Search 中创建和更新首字母缩略词答案
ms.openlocfilehash: cd9e1a48288e6df8f5746d937684a3f2eedd65df
ms.sourcegitcommit: 46303c60e905c89c133278fa41e87055f81a8637
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "44535353"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>管理 Microsoft Search 中的缩写词答案

用户通常会遇到不熟悉的首字母缩写词和其组织或团队使用的缩写。 特定于组织或团队的术语可能对从一个团队迁移到另一个团队的人员、与内部合作伙伴团队合作的人员或对组织的新用户很新。

组织并不总是拥有针对其标准术语的单一参考。 缺少单个引用使其难以查找这些首字母缩写词的定义或扩展。 Microsoft 搜索解决了与首字母缩略词有关的问题。

## <a name="what-users-experience"></a>用户体验

Microsoft Search 用户可以在[Bing](https://Bing.com)中获取带有缩写词的定义。 在**搜索**框中，用户输入类似以下示例的查询：

- 是*什么*DNN
- *定义*DNN
- DNN*定义*
- *扩展*DNN
- DNN*扩展*
- *的含义*DNN
- DNN*表示*

结果包括用户组织中存在的 DNN 的所有含义。

> [!NOTE]
> 用户必须输入包含首字母缩写词的指定*关键字*的查询，以触发其相应的答案。 首字母缩略词查询不区分大小写。

## <a name="set-up-acronyms-answers"></a>设置首字母缩略词答案

在 microsoft 365[管理中心](https://admin.microsoft.com)，转到 "**设置**  >  **Microsoft Search**  > **首字母缩写词**"，然后选择 "**添加首字母缩写**"。

Microsoft Search 查询两个数据源，以提供对用户搜索的缩写词答案：

1. **编辑首字母缩写词**。 由[管理员中心](https://admin.microsoft.com)的 IT 管理员提供。
2. **挖掘的首字母缩写词**。 由 Microsoft Search 从用户的个人电子邮件和文档以及组织中的公开可用数据进行挖掘。

### <a name="set-up-editorial-acronyms"></a>设置编辑首字母缩写词

搜索管理员可以在[Microsoft 365 管理中心]( https://admin.microsoft.com)的 "[首字母缩写" 选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)上设置编辑首字母缩写词。 您可以向管理中心添加任何内部网站或存储库的首字母缩写词。 编辑缩写词可添加到 "**已发布**" 或 "**草稿**" 状态：

**已发布状态**。 在 Microsoft Search 中，对组织的员工可以使用首字母缩略词。

> [!NOTE]
> 在 Microsoft Search 中，首字母缩略词被添加到已发布状态，可能需要长达三天的时间。

**草稿状态**。 如果管理员希望在 Microsoft Search 中提供首字母缩略词答案，则可以将首字母缩写词添加到草稿状态。 添加到草稿状态的首字母缩写词在 Microsoft Search 中不可用。 管理员需要将首字母缩写词添加到 "已发布" 状态，以使其可用。

管理员可以单独添加首字母缩写词或在 CSV 文件中批量导入。 将 CSV 文件上传到下表所示的字段：

| 首字母缩写词（必需） | 扩展（强制） | 说明  | 源 | State （必需） |
| --------- | --------- | ---------- | --------- |--------- |
| *美元* | *拼写出缩写* |  | *URL* | *已发布或草稿* |

### <a name="csv-fields"></a>CSV 字段

**首字母缩写词**。 包含实际的短格式或首字母缩写词。 一个示例是*DNN*。

**扩展**。 包含首字母缩写词的扩展。 一个示例是*深度神经网络*。

**说明**。 首字母缩写词的简短说明，使用户能够快速了解首字母缩写词和其扩展的含义。 例如， *deep 神经网络是具有某种复杂程度的神经网络，具有多个层的神经网络*。

**源**。 您希望用户转到的页面或网站的 URL，以获取有关首字母缩写词的详细信息。

**状态**。 此字段可采用两个值：

- **草稿**。 将首字母缩写词添加到草稿状态。
- **已发布**。 将首字母缩写项添加到已发布状态，并使其在 Microsoft Search 中可用。

### <a name="mined-acronyms"></a>挖掘首字母缩写词

管理员将组织中使用的所有首字母缩写词添加到答案可能是一项挑战。 此功能可查找搜索管理员甚至不知道的首字母缩写词。 若要执行此操作，Microsoft 搜索还将根据这些来源地雷做首字母缩略词：

- 用户的电子邮件。
- [SharePoint](https://products.office.com/sharepoint/collaboration)、 [Microsoft OneDrive]( https://onedrive.live.com/about/)和[microsoft OneNote](http://www.onenote.com/)中的文档。
- 组织内用户可在 SharePoint、OneDrive 或 OneNote 中访问的公共文档。

Microsoft Search 确保只有对文档具有访问权限的用户才能看到从该文档中挖掘的首字母缩写词。 从用户的邮箱中挖掘首字母缩写词时，只有该用户可以看到该首字母缩略词。

> [!NOTE]
> 挖掘的首字母缩写词不需要任何设置。

## <a name="frequently-asked-questions"></a>常见问题

**问：如何对编辑和挖掘数据进行分级？**

**A：** 目前，该功能对编辑前的首字母缩写词进行排名。

**问：发布后，编辑首字母缩写词需要多长时间才能显示在 Microsoft Search 中？**

**A：** 在 Microsoft Search 中，首字母缩略词已被添加到 "已发布" 状态的时间最长为三天。

**问：用户如何触发首字母缩略词答案？**

**答**：若要获取缩写词答案，用户必须在[必应](https://bing.com)**搜索**框中输入特定查询模式。 目前， [Office 365](https://Office.com)或[SharePoint](https://products.office.com/sharepoint/collaboration)中不提供首字母缩略词答案。

**问：收到或发送新的电子邮件或文档后，要显示挖掘的首字母缩写词需要多长时间？**

**A：** 从新的电子邮件或文档中挖掘的首字母缩写词需要长达七天才能显示在 Microsoft 搜索结果中。

**问：是否需要使用特定格式的文档进行挖掘才能选取它们？**

**A：** 不。 我们支持除图像、文件夹和 zip 文件之外的所有文件类型。

**问： Microsoft 是否会采用所有语言的文档中的首字母缩写词？**

**A**： Microsoft 仅支持从英语文档进行挖掘。 对其他语言的支持将分阶段添加。

**问：如果我的组织不想显示挖掘的首字母缩写词，该怎么办？是否可以在搜索结果中停止显示挖掘的首字母缩写词？**

**A**：若要关闭在搜索结果中显示挖掘的首字母缩写词，请按照[业务产品的联系支持](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)部门的说明创建客户支持票证。
创建支持票证后，提取的首字母缩写词最长需要48小时才能停止显示在搜索结果中。

**问：我何时将在[Office 365](https://Office.com)和[SharePoint Online](https://products.office.com/sharepoint/collaboration)中看到首字母缩略词答案？**

**答**： Office 365 和 SharePoint Online 中的首字母缩写答案是产品路线图的一部分，但我们目前无法提供日期或时间范围。
