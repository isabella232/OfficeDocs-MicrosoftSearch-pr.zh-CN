---
title: 管理书签
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: 创建和更新书签以及批量编辑书签结果的方法Microsoft 搜索
ms.openlocfilehash: a08bef9ccc56d395fe6570bacc856653ff3a1563
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375651"
---
# <a name="manage-bookmarks"></a>管理书签

书签可帮助用户只需搜索一下，就快速找到重要网站和工具。 每个书签包括一个标题、URL、一组用于触发书签的用户友好关键字和一个类别。

## <a name="what-makes-a-great-bookmark"></a>什么是出色的书签

出色的书签包含四个关键元素：

1. 一个强大的信息 **性标题**。 目标为不超过 8 个单词或最多 60 个字符。 您希望用户单击标题并查看内容，但避免明显的点击点击：
    - 好：尝试从餐厅菜单中找到这星期的最喜爱的餐厅。 标题清晰、简洁且有趣，但可能会过度提升。
    - 更好：本周的餐厅菜单。 不要过度承诺或像广告一样发出声音。
    - 避免：你将不会相信这一周将进入餐厅菜单。 使用看起来像广告的 clickbait clichés。
2. 简洁的描述（大约300 个字符）总结了链接资源的用途或功能。
3. 可帮助 **用户搜索** 时查找书签的关键字集合。 建议至少使用五个关键字。 此外，包括组织中人员可能使用的变体，例如，餐厅菜单、午餐菜单和餐厅菜单可能是餐厅菜单的变体。
4. 一组 **有用的类别** ，更易于在管理中心内对书签进行排序和筛选。 您的用户永远不会看到分配的类别。

## <a name="create-bookmark-answers"></a>创建书签答案

In the [Microsoft 365 管理中心，](https://admin.microsoft.com/)go to [Bookmarks](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) and choose how you want to create new bookmarks：

- 添加书签
- 导入SharePoint结果
- 添加默认书签和建议的书签
- 导入书签
- 发布或查看推荐的书签

### <a name="add-bookmarks"></a>添加书签

搜索管理员和编辑人员可以在网站中添加书签Microsoft 365 管理中心并发布书签或将其保存到草稿。 发布书签可立即刷新搜索索引，使其可立即被用户发现。 您还可以通过指定发布书签的日期和时间来计划书签。

- **已发布**：组织用户可以通过以下方式使用书签Microsoft 搜索。
- **草稿**：保存为草稿的书签对用户不可用。 如果你或其他利益干系人想要在发布书签之前查看或更新书签，请使用此状态。
- **计划**：将在指定日期和时间发布的书签。

可以使用内容Microsoft 搜索浏览器扩展轻松添加书签。 只需转到要添加为书签的网站，然后单击扩展中的"添加"。 若要安装适用于 Microsoft Edge Google Chrome 的扩展，请转到[Chrome Web 应用商店](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)，并将其添加到浏览器。

### <a name="import-sharepoint-results"></a>导入SharePoint结果

如果组织在 SharePoint 中设置了升级结果，可以将租户的升级结果中的标题、URL 和说明导入 Microsoft 搜索并为用户提供导入的内容。 在大多数情况下，导入SharePoint结果只需几分钟。 如果要导入大量结果，最多可能需要 48 小时。 这是一种快速填充搜索结果并为用户提供更高效的简单方法。 我们建议使用来自 SharePoint 升级的结果作为参考，以了解如何命名和创建相关搜索结果。

### <a name="add-default-and-suggested-bookmarks"></a>添加默认书签和推荐书签

我们包含了一些用户可能会发现有用的默认建议书签，包括 HR、权益、IT 支持、密码管理等的书签。 查看、更新和发布这些建议的书签，以向用户提供高质量的结果。

你的用户还可以建议书签，以便使用 Microsoft 搜索 中的反馈链接查看添加的书签。 他们的建议将显示为建议的书签。

### <a name="import-bookmarks"></a>导入书签

使用"导入"功能，可以更快捷地添加或编辑大量书签。 使用它：

- 批量添加书签：在书签模板文件中添加详细信息，然后导入它。
- 批量编辑书签：将书签导出到.csv文件，编辑导出的文件中书签的详细信息，然后导入已编辑的文件。

有关模板文件的一些要点：

- 从不编辑以下字段中的数据 *：ID、Last* *Modified* 和 *Last Modified By*
- 如果包含现有 *书签的 ID，* 它将替换为导入文件中的信息。
- 对于具有相同标题或 URL 的现有书签，该书签将用导入文件中的信息进行更新。
- 在模板文件中，并非所有字段都是必填的，并且必填字段因书签状态而异。
- 根据 *"状态* "字段，书签将保存为草稿、建议、计划、排除或自动发布。
- 对于管理多个组织的合作伙伴，你可以从一个组织导出书签，然后将它们导入另一个组织。 但在导入之前，必须删除 *ID* 列中的数据。

### <a name="prevent-import-errors"></a>防止导入错误

如果任何所需数据缺失或无效，你将收到错误，并且系统会生成一个日志文件，其中包含有关要更正的行和列的详细信息。 完成必要的编辑，并再次尝试导入该文件。 在解决所有错误之前，无法导入或保存任何书签。

为防止出错，请确保导入文件具有正确格式，并且：

- 包含导入模板中的标题行和所有列
- 列顺序与导入模板相同
- 除三个可为空的列外，所有列都有值 *：ID、Last* *Modified* 和 *Last Modified By*
- *"* 状态"列不为空，它是必填信息
- 导入已发布、建议、计划或草稿书签时，需要标题 *、URL* 和关键字列
- 导入排除的书签时 *，URL* 列是必需的

防止书签到书签重复错误：

- 不要对不同的书签使用重复的 URL。 如果将一个 URL 分配给另一个书签，并且您尝试从导入文件再次添加它，则您将看到一个错误。 这也适用于其他类型的答案的重复 URL。
- 更新现有书签时，请使用 *书签 ID* 列。 您可以更新现有书签的其他任何属性，如关键字或说明，但应确保书签 *ID* 位于导入文件的适当列中。 如果存在 *书签 ID，* 它不会被视为新增功能，也不会被处理为错误。

### <a name="publish-or-review-recommended-bookmarks"></a>发布或查看推荐的书签

若要减少添加书签所需的手动工作量，Microsoft 搜索可评估您组织的 SharePoint 链接，并推荐书签。 可以在发布之前查看它们，或将其设置为自动发布。 建议书签不需要任何设置，默认情况下会启用这些书签并设置为自动发布。 若要随时更改这些设置，请选择" **管理书签** "以打开"书签设置"面板。

![Screenshot of Recommended bookmark settings in the Microsoft 365 admin portal.](media/bookmarks-recommendedsettings.png)

如果启用建议的书签，建议引擎将SharePoint组织的网站，以确定高流量链接。 初始评估期后，建议书签将被自动发布或添加到建议书签列表中。 接下来，将开始下一个周期（即 30 天评估期，后跟自动发布或添加建议的书签）。

我们建议搜索管理员或编辑定期查看这些自动发布或建议的书签。 此外，建议书签绝不会包含现有已发布、建议、计划或已排除书签中的 URL。

为了确保只有具有访问权限的用户才能在工作结果中看到推荐的书签，会包含所有推荐的书签的访问检查功能。 用户绝不会看到他们无法访问SharePoint网站的建议书签。 此访问检查由每个推荐书签的"组"设置中的"仅有权访问此链接的人"选项控制。

如果建议书签中的 URL 或"组"设置发生更改，则访问检查将停止。

若要阻止建议引擎向特定网站发布或建议书签，可以将 URL 添加到排除的列表。 建议引擎绝不会为排除的网站或已排除网站中的页面发布或建议书签。

## <a name="about-keywords-and-reserved-keywords"></a>关于关键字和保留的关键字

书签可以具有多个关键字并共享同一关键字，但保留的关键字不能共享。 保留的关键字是触发一个特定书签的唯一术语或短语。 保留的关键字只能与一个答案相关联。 请慎用保留的关键字。

## <a name="frequently-asked-questions"></a>常见问题解答

**问：书签发布后，在Microsoft 搜索中可见需要多久？**

**答：** 发布后立即在Microsoft 搜索中提供书签。

**问：建议书签显示需要多久？**

**答：** 只有在同时启用了推荐书签Microsoft 搜索自动发布时，推荐书签才显示在书签中。 在初始评估期间，建议引擎将评估SharePoint流量以确定合适的书签，然后自动发布它们。 发布后，它们将立即在Microsoft 搜索。

**问：删除的书签从结果中删除需要Microsoft 搜索？**

**答**：已删除的书签将立即从工作结果中删除。

**问：Microsoft 搜索从所有语言的网站推荐书签吗？**

**答**：是的，Microsoft 搜索从任何内部网站SharePoint书签，而不考虑语言。

**问：能否停止在搜索结果中显示推荐的书签？**

**答：** 若要停止显示推荐的书签，请关闭管理中心中的自动发布设置。 建议书签将添加到建议书签列表中。

**问：如何在搜索结果或管理中心中标识推荐的书签？**

**答：** 在搜索结果中，建议的书签在 URL 前包含短语"Suggested for you"。 在管理中心，建议的书签将具有"SYSTEM"的所有者值。

**问：如何管理对推荐的书签的访问？**

**答**：由 Microsoft 设计的访问引擎可确定书签 URL 是否可供特定用户访问，并且只向正确的受众显示推荐的书签。 但是，如果编辑 URL 或更改组设置，将禁用已设计的访问引擎。

**问：如果未对添加到建议列表的建议书签执行任何操作，会发生什么情况？**

**答**：为了避免建议列表中出现大量书签，建议书签 (所有者 = SYSTEM) 将在 180 天后清除。

**问：在哪里可以找到 Power App 的应用 ID？**

**答**：转到Power Apps网站并查看应用程序的详细信息窗格。 详细了解如何[获取应用 ID。](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)