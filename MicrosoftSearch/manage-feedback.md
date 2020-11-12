---
title: 管理用户反馈
ms.author: lebhansa
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
ROBOTS: NoIndex
description: 查看 Microsoft Search 中的用户反馈并对其执行操作
ms.openlocfilehash: 332410cd29a7256cccd651c3a668fdf3eb473ba4
ms.sourcegitcommit: 102371815e739da33d1711197cdc743ae8124baa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "48996789"
---
# <a name="managing-user-feedback"></a>管理用户反馈

为您的用户创建出色的搜索体验是 Microsoft 与搜索管理员之间的合作关系。 通过你的用户反馈，我们可以持续评估产品并进行调整，以获得最佳体验。 不过，你最好先解决一些反馈。

现在我们提供的工具将允许你查看和管理你的用户在搜索体验上提供的反馈。

## <a name="how-users-submit-feedback"></a>用户如何提交反馈

当组织中的人员使用 Microsoft 搜索时，他们可能会获得有关体验的反馈。 当他们单击 "结果" 页面上的 "反馈" 链接时，他们可以对他们的反馈进行分类并包含其他注释。

![全局反馈表单](media/feedback/feedback-global-dialog.png)

用户还可以选择将其查询和其他诊断信息连同类别和注释一起发送给 Microsoft。 [了解](https://privacy.microsoft.com/en-US/privacystatement) 有关隐私的详细信息以及我们如何保护此数据。 诊断数据包含 Microsoft 为产品改进使用反馈项目所需的最关键信息。

大多数反馈提交都显示在 Microsoft 搜索管理中心的 " [反馈](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) " 部分。 与 **我要建议的内部链接** 类别一起发送的反馈在 " [书签](https://admin-ignite.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) " 部分中显示为建议的书签，可通过 " **建议** 的状态" 筛选来查看。

## <a name="review-feedback"></a>查看反馈

在 " [反馈](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) " 页面上，您可以查看和导出组织中的人员在过去30天内发送的反馈。 一旦用户提交反馈，它就会在此列表中显示20分钟。 您可以使用 "刷新" 按钮来确保您查看的是最新数据

通过使用筛选器，可以查看特定回答类型的反馈。 您还可以按源和日期范围进行筛选。

您可以使用 "反馈" 列表上方的搜索框搜索有关特定查询的反馈。

在反馈列表中，逐字列指示用户的反馈也包含注释或建议。 若要读取它，请单击查询以打开 " **详细信息** " 面板。

## <a name="update-feedback-state"></a>更新反馈状态

当反馈进入时，它将处于 *新* 状态，并将一直保留，直到你将其更改为 " *已解决* " 或 " *重复* "。

若要更改此状态：

1. 在查询旁边，选择 " **更多选项** " (三个垂直点) 。
1. 在菜单上，选择 " **标记为 ' 已解决** " 或 " **标记为重复"。**
1. 该列表将刷新并显示更新的状态。

您还可以更新多个项目的状态，只需将其选中，然后选择 "更多选项" 下一个项目。

## <a name="export-feedback"></a>导出反馈

如果要与其他人共享搜索反馈或保留超过30天的搜索反馈，请单击 " **导出"。** 将自动下载一个名为反馈的 .csv 文件，该文件的日期为 "Feedbacks_10_31_2020.csv"，如 ""。

## <a name="send-user-feedback-to-microsoft"></a>向 Microsoft 发送用户反馈

默认情况下，所有用户反馈都将发送给 Microsoft 并向您添加。 若要停止向 Microsoft 发送反馈，请单击 " **管理设置** "，然后清除 " **自动向 microsoft 发送用户反馈** " 复选框。 此更改可能需要长达24小时才会生效。

如果你已决定不自动将反馈发送给 Microsoft，你仍可以向 Microsoft 发送各个反馈片段。

1. 选择要共享的反馈。
1. 在操作栏中，选择 "更多 (三个点) "，然后单击 " **向 Microsoft 发送反馈** "。

1. "发送到 Microsoft" 列中的状态将更改为 "挂起"。 在发送反馈时，它将更改为 "是"。

如果您自动或手动共享反馈，则永远不会为选择不包含此信息的用户提供查询和其他诊断信息。

## <a name="suggestions-on-how-to-use-feedback"></a>有关如何使用反馈的建议

作为搜索管理员，您应了解组织中的主要角色以及这些人员通常与之交互和搜索的内容类型。 了解这一点后，您可以使用反馈对用户的搜索体验做出目标改进。

1. "我找不到要查找的内容"，并且类似的反馈可用于标识用户需要的内容，但当前不包含在搜索索引中。 确定这一过程通常会根据了解你的用户来进行调查和推断。 找到后，确定包含该内容的哪些方法最适合：
    1. 书签适用于具有高质量登录页和有限种类的搜索词的内容源，以便用户社区从书签中获取高质量结果，然后可以有效地查找他们要查找的内容。
    1. 问：&A 对只是相当频繁，但不会发生变化的单个答案非常有用。
    1. 连接器对于具有各种内容源和各种搜索词的内容源非常有用。
1. "结果过长，无法加载" & "我发现问题" 可能是一个更大问题的指示器。 在每天查找此反馈可能会有帮助，如果显示多个事例，则可以验证自己的搜索体验，并根据需要在 Microsoft 中打开支持案例。 这种类型的反馈对 Microsoft 来说也很重要，这也是将所有反馈传递给我们的极好理由。
1. "我希望推荐一个内部链接" 可评估为添加为书签或已连接的内容。 你的第一个想法应是书签;如果书签的使用率较高，则可以考虑通过连接器引入内容，以实现更丰富的搜索体验。
