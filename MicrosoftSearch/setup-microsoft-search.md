---
title: 设置 **Microsoft 搜索**
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: 首次设置 Microsoft 搜索。
ms.openlocfilehash: c95cc0d11d60e3d4d9a509dc691c01858ede7262
ms.sourcegitcommit: 9df9b1a5f83c9fbe62900df183bee239a8ea6d91
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2019
ms.locfileid: "34947740"
---
# <a name="set-up-microsoft-search"></a>设置 Microsoft 搜索

**Microsoft 搜索**提供了一个用户友好界面，可帮助用户通过安全访问所有数据源（包括电子邮件、文件、SharePoint 文件、OneDrive 内容和其他共享资源以及用户组织中的 Internet）来查找文件和文档、内部网站和业务工具、人员和组、位置和方向、对话和答案等信息。

若要了解有关 **Microsoft 搜索**功能的详细信息，请参阅 [Microsoft 搜索概述](overview-microsoft-search.md)。

## <a name="get-started"></a>入门

作为 Microsoft 365 的一部分，**Microsoft 搜索**将在默认情况下为所有支持它的 Microsoft 应用打开。 用户需要做的就是使用工作或学校帐户登录，并使用将必应设置为默认搜索提供程序的浏览器。

在 **Microsoft 365 管理中心**管理 **Microsoft Search**。 使用管理员凭据登录，然后从 Office 365 应用列表中选择“**管理员**”磁贴（单击引用列表左上角的“**应用启动器**”图标）。 在 **Microsoft 365 管理中心**，左侧导航面板的 **Settings** 下选择 **Microsoft Search**。

 

**注意：** 如果没有在 **Microsoft 365 管理中心**的“**设置**”下看到 **Microsoft 搜索**，请打开管理中心右上角的“**试用预览版**”开关。 

作为管理员，你应该考虑一些可使 **Microsoft Search** 体验在组织内实现高效且用户友好的因素。

## <a name="step-1-check-access-level-of-your-users"></a>步骤 1：检查用户的访问级别

**Microsoft 搜索**尊重内容源的安全设置。 用户在搜索结果中看到的内容取决于他们的权限和访问级别。 查看组织内的用户访问级别，以确保用户仅查找允许他们访问的内容。

详细了解[计划权限](https://docs.microsoft.com/zh-CN/sharepoint/plan-your-permissions-strategy)和[创建权限级别](https://docs.microsoft.com/zh-CN/sharepoint/how-to-create-and-edit-permission-levels)。

## <a name="step-2-assign-search-admin-and-search-editor"></a>步骤 2：分配搜索管理员和搜索编辑人员

**Microsoft 管理中心**有两个新角色 - 搜索管理员和搜索编辑人员。  拥有完整特权的全局管理员为用户分配管理员角色，包括搜索管理员角色。 搜索管理员可以将搜索管理员或搜索编辑人员角色委派给其他用户。 有关不同管理角色的详细信息，请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)。

**备注：** 这两个新角色 – 搜索管理员和搜索编辑人员 – 仅在 **Microsoft 365 管理中心**中提供，不在旧版管理门户中提供。 

搜索管理员直接影响最终用户的搜索体验。 这包括选择要向用户显示的结果类型。 一个人可能很难针对用户在组织内搜索的许多不同主题选择和创建权威内容。 我们建议你通过将它们添加为编辑人员来利用 SME 和其他用户的专业技能和知识。 

在 **Microsoft 搜索**中，你可以使用两个新角色来管理组织的搜索设置和内容：
1. **搜索管理员：** 此角色可以创建和管理搜索结果内容，并定义查询设置，以改善组织内的搜索结果。 搜索管理员负责管理 **Microsoft 搜索**配置并指定创建内容的搜索编辑人员。
2. **搜索编辑人员：** 在 Microsoft 365 管理中心中为 **Microsoft 搜索**创建、管理和删除内容。 此角色可以创建和管理编辑内容，例如常见问题和答案、重要的地点和位置、经常搜索和使用的网站和应用等。但是，他们无权管理搜索设置。

有关分配管理员角色的信息，请参阅[在 Office 365 商业版中分配管理角色](https://docs.microsoft.com/zh-CN/office365/admin/add-users/assign-admin-roles?view=o365-worldwide)。

## <a name="step-3-make-content-easy-to-find"></a>步骤 3：使内容易于查找 

**Microsoft 搜索**为管理员提供了可用于为其用户构建强大搜索体验的工具。 在 **Microsoft 搜索**中，管理员可以创建三种不同的搜索内容，以获得更好的搜索体验并提高内容的可查找性：
- **书签：** 书签类似于 SharePoint 中的升级结果，有助于将用户查询的尽可能最佳结果提升到搜索结果的顶部，并使用户能够轻松查找重要的内部网站。 
- **问答：** 问答与常见问题类似，通常采用问答形式。 对于用户提出的工作相关问题，它能提供尽可能最佳的答案。
- **位置：** 位置是帮助用户找到你所在组织的大楼、办公室和校园的地址。 

你拥有的书签、问答和位置越多，你为用户增加的价值和权益就越大。 但是，数量太多可能会大幅增加管理开销，因为必须定期检查和更新这些开销才能使结果保持相关且最新。

以下是你应该考虑为用户添加书签的一些内容示例：
- 组织、产品或服务信息。
- 每个人都可以获得的信息内容；例如，有关公司的信息、Windows 和 Office 应用的帮助等。 
- 组织内的人员在日常工作中通常搜索的内容。 与工作相关的常见搜索包括员工福利、时间和费用报告、提交采购订单以及从 IT 服务获取帮助。 

有关创建和管理搜索内容的信息，请参阅[轻使内容易于查找](make-content-easy-to-find.md)。

## <a name="step-4-test-single-sign-on"></a>步骤 4：测试单一登录
**Microsoft 搜索**使用 Azure Active Directory (AAD) 对组织的数据进行身份验证和授权访问。  这意味着当你登录 Office 365 应用或 Windows 10 时，用户将自动使用你的工作或学校帐户登录。

我们建议 **Microsoft 搜索**用户使用单一登录，因为它会减少提示用户登录的次数。 管理员应该用一小组用户来测试单一登录，以帮助排查任何导致配置受阻的问题。 

对于 Windows 10 上的 Chrome 用户，仅当安装 Windows 10 和 AAD 登录扩展后，单一登录才能正常工作。 安装后，在登录支持的站点（包括 Office 365 和必应）时使用 Chrome 扩展轻松完成 AAD 身份验证。 此功能仅适用于授权用户。 

若要下载并安装适用于 Chrome 的 Windows 10 和 AAD 登录扩展，请转到 [Chrome 网上应用商店](https://go.microsoft.com/fwlink/?linkid=2090961)。

## <a name="step-5-training-and-communication"></a>步骤 5：培训和沟通
建立员工可以轻松访问的自助服务资源。 这将有助于减轻你和团队的总体负担，以便不断推动沟通、协助展开自我培训和教育员工。 为用户提供沟通、常见问题、视频以及录制的培训或网络研讨会。 以下是一些有用的链接：
- [了解在 Office 中需要 Microsoft 搜索做什么](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Office 365 培训中心](https://support.office.com/office-training-center)
- 
  [Microsoft 搜索中心](https://support.office.com/zh-CN/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)

## <a name="trying-out-microsoft-search-in-bing"></a>在必应中尝试 **Microsoft 搜索** 
**Microsoft 搜索**管理员可以在必应中关闭 **Microsoft 搜索**。 如果关闭，用户将无法在必应搜索中看到组织内容。 默认情况下，已在必应中打开 **Microsoft 搜索**。 我们建议你在必应中打开 **Microsoft 搜索**以获得更好的用户体验。 

如果你想在测试租户上试用 **Microsoft 搜索**，或者你希望在将搜索体验提供给所有用户之前测试搜索体验，则可以关闭 **Microsoft 搜索**。
若要在必应中打开/关闭 **Microsoft 搜索**，请转到 **Microsoft 365 管理中心**中的**服务和加载项**，然后打开/关闭 **Microsoft 必应搜索**。
