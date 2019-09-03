---
title: 设置 Microsoft 搜索
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 08/06/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: 首次设置 Microsoft 搜索。
ms.openlocfilehash: 7c80701e83fea7b9b93e4e01f98fd1eeedbfa749
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639494"
---
# <a name="set-up-microsoft-search"></a>设置 Microsoft 搜索

Microsoft 搜索提供了一个用户友好界面，可帮助用户通过安全访问所有数据源（包括电子邮件、文件、SharePoint 文件、OneDrive 内容和其他共享资源以及用户组织中的 Internet）来查找文件和文档、内部网站和业务工具、人员和组、位置和方向、对话和答案等信息。

若要了解有关 Microsoft 搜索功能的详细信息，请参阅 [Microsoft 搜索概述](overview-microsoft-search.md)。

## <a name="get-started"></a>入门

作为 Microsoft 365 的一部分，Microsoft 搜索将在默认情况下为所有支持它的 Microsoft 应用打开。 用户需要做的就是使用工作或学校帐户登录，并使用将必应设置为默认搜索提供程序的浏览器。

在 Microsoft 365 管理中心管理 Microsoft 搜索。

1. 在 Microsoft 365 管理中心中，转到“**设置**” > “**Microsoft**”。

**注意：** 如果没有在“**设置**”下看到 Microsoft 搜索，请打开任意管理中心页面右上角的“**试用预览版**”开关。

作为管理员，你应该考虑一些可在组织内实现高效且用户友好的 Microsoft 搜索体验的因素。

## <a name="step-1-check-access-level-of-your-users"></a>步骤 1：检查用户的访问级别

Microsoft 搜索尊重内容源的安全设置。 用户在搜索结果中看到的内容取决于他们的权限和访问级别。 查看组织内的用户访问级别，以确保用户仅查找允许他们访问的内容。

| 服务         | 说明                                                                                                                                                                                                                                         |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 组          | [添加或删除组成员](https://docs.microsoft.com/office365/admin/create-groups/add-or-remove-members-from-groups)                                                                                                                     |
| 人员          | 通过使用 [Set-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-user) cmdlet 将 `HiddenFromAddressListEnabled` 参数设置为 `true`，可以隐藏地址列表中的某些用户，使其不被搜索到。 |
| Microsoft Teams | [管理 Microsoft Teams 的用户访问](https://docs.microsoft.com/microsoftteams/user-access)                                                                                                                                                      |
| OneDrive        | [管理共享](https://docs.microsoft.com/OneDrive/manage-sharing)                                                                                                                                                                                |
| SharePoint      | [规划权限](https://docs.microsoft.com/zh-CN/sharepoint/plan-your-permissions-strategy)<br> [创建权限级别](https://docs.microsoft.com/zh-CN/sharepoint/how-to-create-and-edit-permission-levels)                          |
| OneNote         | 无法搜索嵌入在 OneNote 中的文件。 [更改 OneDrive 上的笔记本的权限](https://support.office.com/article/B9600CCF-045A-40E6-9913-4A7EB02869A5)                                                                    |
| Yammer          | [Yammer 安全设置](https://docs.microsoft.com/Yammer/manage-security-and-compliance/yammer-security-settings)                                                                                                                               |

## <a name="step-2-assign-search-admin-and-search-editor"></a>步骤 2：分配搜索管理员和搜索编辑者

在 Microsoft 搜索中，你可以通过将以下角色分配给用户来管理组织的搜索设置和内容：

1. **搜索管理员：** 此角色可以创建和管理搜索结果内容，并定义查询设置，以改善组织内的搜索结果。 搜索管理员管理 Microsoft 搜索配置，并且可以执行搜索编辑者可以执行的所有内容管理任务。
2. **搜索编辑者：** 在 Microsoft 365 管理中心中为 Microsoft 搜索创建、管理和删除内容。 此角色可以创建和管理编辑内容，例如常见问题和答案、重要的地点和位置、经常搜索和使用的网站和应用。

目前，搜索管理员和搜索编辑者角色必须由全局管理员分配。有关详细信息，请参阅[分配管理员角色](https://docs.microsoft.com/zh-CN/office365/admin/add-users/assign-admin-roles?view=o365-worldwide)。

搜索管理员直接影响最终用户的搜索体验。 这包括选择要向用户显示的结果类型。 一个人可能很难针对用户在组织内搜索的许多不同主题选择和创建权威内容。 我们建议你通过将行业专家 (SME) 和其他用户添加为搜索编辑者来利用他们的专业技能和知识。

## <a name="step-3-make-content-easy-to-find"></a>步骤 3：使内容易于查找

Microsoft 搜索为管理员提供了可用于为其用户构建强大搜索体验的工具。 在 Microsoft 搜索中，管理员可以创建三种不同的搜索内容，以获得更好的搜索体验并提高内容的可查找性：

- **书签：** 书签类似于 SharePoint 中的升级的结果，有助于将用户查询的最佳结果提升到搜索结果的顶部，并使用户能够轻松找到重要的内部网站。
- **问答：** 问答与常见问题类似，通常采用问答形式。 对于用户提出的工作相关问题，它能提供尽可能最佳的答案。
- **位置：** 位置是帮助用户找到你所在组织的大楼、办公室和校园的地址。

你拥有的书签、问答和位置越多，你为用户增加的价值和权益就越大。 但是，数量太多可能会大幅增加管理开销，因为必须定期检查和更新这些开销才能使结果保持相关且最新。

以下是你应该考虑为用户添加书签的一些内容示例：

- 组织、产品或服务信息。
- 每个人都可以获得的信息内容；例如，有关公司的信息、Windows 和 Office 应用的帮助等。
- 组织内的人员在日常工作中通常搜索的内容。 与工作相关的常见搜索包括员工福利、时间和费用报告、提交采购订单以及从 IT 服务获取帮助。

有关创建和管理搜索内容的信息，请参阅[使内容易于查找](make-content-easy-to-find.md)。

## <a name="step-4-training-and-communication"></a>步骤 4：培训和沟通

建立员工可以轻松访问的自助服务资源。 这将有助于减轻你和团队的总体负担，以便不断推动沟通、协助展开自我培训和教育员工。 为用户提供沟通、常见问题、视频以及录制的培训或网络研讨会。 以下是一些有用的链接：

- [了解在 Office 中需要 Microsoft 搜索做什么](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Office 365 培训中心](https://support.office.com/office-training-center)
- [Microsoft 搜索中心](https://support.office.com/zh-CN/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)