---
title: 使用 Microsoft 搜索轻松查找内容
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 创建书签、位置和问答项目，让用户轻松查找组织的内容。
ms.openlocfilehash: 605610264e2068deb6215c3157efc24cf0b0a2fd
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626825"
---
# <a name="make-content-easy-to-find"></a>使内容易于查找

Microsoft 搜索可帮助用户查找相关内容。 这是一种搜索 intranet 和 web 内容的安全方法。 这种在 web 和组织的集成类型仅适用于 Microsoft。 通过 Microsoft Search，管理员可以使用他们的组织知识，让用户能够轻松地查找相关内容。 

## <a name="components-that-find-content"></a>查找内容的组件
在 Microsoft Search 中，管理员创建[书签](manage-bookmarks.md)、 [PowerApps](integrate-powerapps.md)、 [Q&A](manage-qas.md)以及使内容更易于查找的[位置](manage-locations.md)。 每个搜索组件都包括标题、URL 和一组触发关键字。

## <a name="bookmarks"></a>书签
只需几个步骤即可创建[书签](manage-bookmarks.md)。 每个书签都包括标题、URL 和一组触发关键字。 书签可以包含多个关键字，而多个书签可以共享同一个关键字。 但不能共享保留的关键字。 当您创建或修改书签时，搜索索引将会刷新，并且书签将立即对用户可用。

如果你的组织已在[SharePoint](http://sharepoint.com/)中设置了**提升的结果**，则可以将这些结果导入到 Microsoft Search 中。 利用提升的结果，您可以快速填充搜索结果，使内容可供用户使用，并使 Microsoft 搜索在您进行设置后立即生效。 我们建议你使用 SharePoint 中的升级结果作为参考，以了解如何命名和创建相关的搜索结果。 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>使用浏览器扩展添加或编辑书签
搜索管理员可以使用浏览器扩展轻松创建搜索内容。 若要将网站添加为书签，请安装浏览器扩展。 然后转到网站并将其添加为书签。 若要了解详细信息，请参阅[管理书签](manage-bookmarks.md)。

目前，浏览器扩展适用于[Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge)和[Google Chrome](https://www.google.com)： 
- 若要下载边缘扩展，请转到[Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)。
- 若要下载 Chrome 扩展，请转到[chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)。

## <a name="powerapps"></a>PowerApps

通过将现有[PowerApps](integrate-powerapps.md)添加到[书签](manage-bookmarks.md)中，用户可以完成任务，如输入休假时间或报告费用。 

使用[PowerApps](integrate-powerapps.md)，可以生成在浏览器中或在手机或平板电脑上运行的业务应用程序。 无需任何编码体验。 PowerApps 在任何浏览器和任何设备上工作。 添加的时间不会超过一分钟。 若要了解有关 PowerApps 的详细信息，请参阅以下文章：
- [引导式学习](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [PowerApps 文档](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [PowerApps 主页](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>将 PowerApp 添加到书签

1. 查找要添加的 PowerApp 的[应用程序 ID](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) 。
1. 在 microsoft 365[管理中心](https://admin.microsoft.com)，转到 "**microsoft 搜索**" "**设置** > "。 
1. 添加或查找一个要向其添加 PowerApp 的书签。
1. 在 "**书签设置**" 中，选择 "**电源应用**"。 然后选择 "**添加电源应用**"。
1. 输入**应用 ID**。 自动调整高度和宽度。 [书签](manage-bookmarks.md)可以同时支持纵向和横向方向，但当前大小不能更改。 为了便于测试，书签预览显示了一个功能齐全的 PowerApp。
1. 选择“**发布**”或“**保存到草稿**”。

## <a name="qa"></a>问答

创建[Q&](manage-qas.md)类似于创建[书签](manage-bookmarks.md)。 使用 Q&A，可以提供用户问题的答案，而不仅仅是网页的链接。 您可以使用可用工具来设置格式文本中的答案的格式。 如果书签和 Q&共享同一个关键字，则书签结果将首先显示。 与书签一样，Q&索引在您添加或更改 Q&A 后立即刷新。 

### <a name="supported-html-tags"></a>受支持的 HTML 标记

您可以使用 HTML 内容或向答案或说明添加 HTML 标记。 我们支持以下 HTML 标记：
 
- blockquote
- div
- em
- h1、h2、h3 和 h4
- ol、ul 和 li
- p
- pre
- span
- strong
- table、thead、tbody、tr、th 和 td
- u
- a
- code
- br
- hr
- img

不支持的标记将被忽略或显示为文本。 请确保预览卡片。

> [!Note]
> 如果模板文件中存在错误，则不能导入 Q&项目。 若要防止错误，请确保您的导入文件格式正确，并且包含所有必需的信息。 有关如何[防止导入错误](#prevent-import-errors)的详细信息，请参阅。

## <a name="locations"></a>位置

通过[位置](manage-locations.md)，您的用户可以找到地址并找到您的组织的建筑物。 **位置**功能为办公室、校园、大楼以及方位和导航提供准确的位置。 为了获得最佳效果，管理员需要将其组织的所有重要位置添加到 Microsoft Search 中。 与[书签](manage-bookmarks.md) [&A](manage-qas.md)不同，位置索引不会立即刷新。 在搜索结果中显示新的或更改的位置可能需要几个小时。

## <a name="get-started"></a>入门
若要了解用户所需的信息并使其易于发现，请尝试以下方法：

- 使用 Intranet 搜索日志，来确定获得最多流量的网站和页面。
- 确定每天或每周使用的应用、网站和工具。
- 查找员工福利的直接链接。
- 查找用户需要了解的策略和流程。
- 决定用户联系以获取支持的人以及它们的操作方式。
- 根据业务周期，获取定期（seasonally 或基于业务周期）所需的信息。 例如，人们正在寻找用于预订休息时间或季度财务更新的工具。
- 收集针对区域或移动用户的策略。 示例是因位置而异的好处。
- 确定用于常见 web 搜索的内部网站和信息。 例如流量、公共转口信息、本地天气、公司合作伙伴提供的折扣以及健康和健身计划。
- 查找有关公司赞助的活动、会议或聚餐的信息。
- 研究常见 IT、人力资源和支持问题以及常见问题 (FAQ) 和答案。

## <a name="involve-smes-and-users"></a>涉及 Sme 和用户
在组织中，用户可以搜索一系列简单而复杂的主题。 Office 地址和员工福利就是简单的示例。 复杂示例包括新的工作流程、技术信息和操作方法内容。 若要创建或查找各种各样的内容，您需要具有不同的字段、主题和技术方面的专业技能。 

大多数搜索管理员对每个主题没有特定的知识。 若要在外部资源无帮助的情况下扩展可用内容的数量，请寻求组织中其他人的专业技能和知识。

### <a name="get-content-from-smes"></a>从 Sme 获取内容
利用组织中的行业专家（Sme），包括 HR、支持、销售、技术和其他关键领域的专家。 如果将其添加为 Microsoft Search 编辑器，则 Sme 可以直接加入内容。 

### <a name="involve-your-users"></a>让用户参与进来
让用户推荐要设为书签的资源。 还要求用户报告损坏或无效的链接等错误。

## <a name="set-up-components"></a>设置组件
若要添加或编辑单个书签或批量[书签](manage-bookmarks.md)， [Q&A](manage-qas.md)和[位置](manage-locations.md)，请执行以下各节中的步骤。 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>添加或编辑单个书签 "Q&A" 或 "位置" 组件
1. 在 microsoft 365[管理中心](https://admin.microsoft.com)，转到 "**microsoft 搜索**" "**设置** > "。 选择组件的 "已命名" 选项卡。默认情况下，"**书签**" 选项卡处于选中状态。
1. 若要添加组件，请选择 "**添加新**"。 
1. 若要编辑组件，请选择相关组件列表中的书签。 
1. 在你添加或编辑信息时，预览将随之自动更新。

### <a name="bulk-add-or-edit-components"></a>批量添加或编辑组件
使用 "**导入**和**导出**" 功能，搜索管理员可以批量创建或编辑[书签](manage-bookmarks.md)、 [Q&A](manage-qas.md)和[位置](manage-locations.md)。 当管理员要添加或编辑多个组件时，此功能非常有用。 

导入和导出功能提供以下功能：
- **批量添加**。 在组件的模板文件中添加详细信息，然后将其导入。
- **批量编辑**。 将组件导出到 CSV 文件，然后在导出的 CSV 中编辑书签详细信息，然后导入更新后的 CSV。
- **从[SharePoint](http://sharepoint.com/)导入已升级的网站**。 此功能仅适用于[书签](manage-bookmarks.md)。
- **备份**。 将组件导出到 CSV 文件。

若要导入或导出组件，请执行以下步骤：
1. 在组件的 "已命名" 选项卡的右上角，选择 "**导入**"。 
1. 若要下载 CSV 文件中的所有现有组件，请选择 "**导出**"。
1. 在右侧窗格中，选择要使用 CSV 文件或从[SharePoint](http://sharepoint.com/)导入的选项。
1. 若要获取必需字段和详细信息的列表，请下载组件的模板文件。 
1. 在模板文件中添加或编辑组件详细信息。 然后将其保存到您的计算机上。 
1. 在组件的 "**导入**" 窗格中，选择 "**浏览**"。 然后选择所需的 CSV 文件，并选择 "**导入**"。

### <a name="template-guidelines"></a>模板指南
使用模板文件时，请注意这些准则和限制：
- 从不编辑这些字段中的数据： *Id*、*上次修改**者和上次修改者*。
- 如果包含现有书签的*Id* ，则会将其替换为导入文件中的信息。
- 如果现有文件中有一个具有相同标题或 URL 的书签，则会使用导入文件中的信息更新该书签。
- 并不是模板文件中的所有字段都是必需的，并且必填字段因书签状态而异。
- 根据 "*省/市/自治区*" 字段，书签将保存为**草稿**、**建议**或**计划**。 否则，它们会自动发布。
- 如果您管理多个组织，则可以从一个组织中导出您的书签并将其导入到另一个组织中。 但是，在导入之前，你必须删除 *Id* 列中的数据。

> [!Note]
> 如果模板文件中存在错误，则不能导入组件项。 若要防止错误，请确保您的导入文件格式正确，并且包含所有必需的信息。

### <a name="prevent-import-errors"></a>防止导入错误

如果任何必需的数据丢失或无效，则会收到错误消息。 日志文件生成了有关要更正的行和列的详细信息。 进行必要的编辑并再次尝试导入文件。 在解决所有错误之前，不能导入或保存任何书签。

若要防止错误，请确保您的导入文件格式正确并满足以下要求：
- 包含标题行和导入模板中的所有列。
- 列顺序与导入模板相同。
- 除可以为空的三个列之外，所有列都具有值： *Id*、*上次修改*时间和*上次修改者*。 
- "*状态*" 列不为空。

### <a name="titles-and-descriptions"></a>标题和说明
连接的标题和说明可帮助用户确定结果是否应答其搜索查询。 正确的标题和说明反映了结果的核心目的。 例如，标题 Childcare 的**好处**介绍了*有助于支付 Childcare 成本的好处*。 使用此连接的数据，搜索**childcare**的用户可以找到货币支持的好处，并获取有关详细信息的链接。

### <a name="keywords"></a>关键字
使用关键字，组织中的用户可以搜索和查找相关内容。 您需要将关键字术语与它们相关的搜索结果相关联。 Microsoft 搜索根据内容的标题和 URL 提出关键字建议。 若要识别更多关键字，请获取以下问题的答案：

1. **哪些搜索词可以找到您标识的信息？** 请参阅您的组织中的任何现有术语，以及相关的变体、首字母缩略词、主题和主题。
1. **人们使用什么变体或词来讨论此信息？** 请求你的支持团队提供这些关键字。

例如，如果您创建了一个链接到用于提交假期请求的工具的结果，则关键字 "**度假**" 和 "**提交假期" 请求**是包含的有效选项。 组织中的用户可能还会使用**假日**或**休息时间**搜索与假期相关的信息。 若要使用户能够更轻松地查找相关内容，请添加这些关键字，如 "**提交假日请求**" 和 "**请求超时**"。

### <a name="reserved-keywords"></a>保留关键字
 保留关键字是用于触发结果的唯一词条或短语。 与其他关键字不同，保留的关键字仅与一个结果相关联。 请慎用保留关键字，以便 Microsoft 搜索能够基于使用情况进行学习。

例如，用于提交小时数的网站的书签。 [！注意] 如果**log time**是保留的关键字，则组织中搜索**日志时间**的用户会在 Microsoft 搜索框中将该网站作为唯一的书签。 

### <a name="group-related-content-with-keywords"></a>使用关键字对相关内容进行分组
如果您希望用户在搜索特定术语时查找一组相关的内容，请为所有相关的内容分配相同的关键字。 例如，搜索有关生命状态更改的流程和工具。 若要将答案组合在一起以更新福利、税务信息和名称和别名更改，请包含关键字（如**marriage**）。

### <a name="search-settings"></a>搜索设置
使用搜索设置，您可以对内容进行量身定制，并面向特定的用户组。 这些 Microsoft 搜索设置控制何时显示搜索结果以及谁可以查看它：

- **日期**。 若要控制内容何时可用或不可用，请设置开始日期和结束日期。 例如，当与时间相关的搜索结果相关时，该材料将显示在搜索结果中。
- **国家或地区**。 您可以选择国家或地区，因此只有这些位置的用户才能看到特定内容。 例如，特定国家/地区的信息仅显示在这些国家/地区的搜索结果中。
- **组**设置使结果仅可用于所选组的成员。 例如，如果创建了仅与 HR 部门的员工相关的网站，请将此设置映射到相应的 HR 安全组。
- **设备或操作系统**。 选择 "设备类型" 或 "操作系统"，因此只有对这些设备进行搜索或使用这些系统的用户才能看到该书签。
- **目标变体**。 此设置根据用户的设备和位置改变书签的内容。

## <a name="test-your-content"></a>测试内容
在创建了[书签](manage-bookmarks.md)和[Q&](manage-qas.md)后，请验证以下结果：
- 显示正确的书签或 Q&。
- 所有与关键字组合在一起的内容都将按计划显示在一起。
- 搜索答案中不会出现任何意外。
- 书签或 Q&A 具有足够的信息。

参与创建内容的用户和 Sme 可帮助测试和验证搜索结果。

## <a name="review-and-update-periodically"></a>定期查看并更新
权威信息，如[书签](manage-bookmarks.md)和[Q&](manage-qas.md)需要保持最新。 定期执行以下步骤：
- 修复或删除已损坏和无效的 Url。
- 删除不再相关的书签或 Q&。
- 检查工具、网站名称或团队名称更改。
- 请考虑书签或 Q&的权威是否足够或需要更清楚的说明。

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>获取有关书签、问答&和位置的见解

Microsoft Search 显示发布、计划或建议的[书签](manage-bookmarks.md)、 [Q&A](manage-qas.md)和[位置](manage-locations.md)的数目。 [Insights 仪表板](get-insights.md)按状态显示书签、Q&A 和 location 总计：

- **已发布：** 向用户推出的已发布结果数。
- **已计划：** 发布管道中的已计划结果数。
- **已建议：** 来自用户的建议数。

建议的[书签](manage-bookmarks.md)、 [Q&A](manage-qas.md)和[位置](manage-locations.md)是内容中的差距的很棒的指示器。 它们可帮助您了解用户的查找内容，但不能找到。 此数据可能表示需要创建更多的书签、Q&或位置。 或者，您可能需要使用更好的关键字、保留关键字和搜索字符串来更新现有内容，以使您的内容更容易发现。

### <a name="review-top-search-queries"></a>查看热门搜索查询

若要找出最近90天内最有印象的搜索，请查看您的搜索查询。 "*印象*" 表示在搜索结果中查看页面的次数。 [Insights 仪表板](get-insights.md)上的**顶部查询**卡片显示每个结果类型、搜索总数和点击率（CTR）的前25个用户搜索。 使用此报告，您可以确定搜索查询量并确定 "高搜索" 和 "低搜索" 活动的查询。

低搜索计数可能指示用户不满意。 任何用户都不查找该内容，或者他们使用不同的关键字来查找它。 CTR 可显示用户选择升级结果的频率以及查询规则和结果对用户的有用程度。 较低的 CTR 表示用户找到了内容，但它不能满足其需求。 在这种情况下，请查看内容。 若要将内容与搜索查询对齐，请确保它与用户的搜索和更新标题、说明和关键字相匹配。 

### <a name="analyze-impressions-by-result-type"></a>按结果类型分析展示次数

"[真知灼见" 仪表板](get-insights.md)上的 "**印象分布**卡" 中的易于阅读的图形显示了不同时间段的印记。 时间轴将会显示结果类型的每日展示次数。 通过这些关系图，可以确定最常使用或不经常使用的结果类型。 偶尔使用特定结果类型并不一定意味着结果类型不正常。 它只显示用户如何使用搜索结果。

 如果特定的结果类型是用户首选的，则可以创建相同类型的更多搜索结果。 若要确保关键字适用，请查看使用率较低的结果类型的关键字。 使用此报告，您还可以查看一段时间内用户行为的变化。
