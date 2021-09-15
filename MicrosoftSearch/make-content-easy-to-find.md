---
title: 使用 Microsoft 搜索轻松查找内容
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 创建书签、位置和问答项目，让用户轻松查找组织的内容。
ms.openlocfilehash: 77b6507c7643e6cf2176f37a9a2cf0def1c640ba
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375653"
---
# <a name="make-content-easy-to-find"></a>使内容易于查找

Microsoft 搜索可帮助用户查找相关内容。 它是一种搜索你的 Intranet 和 Web 内容的安全方式。 这种跨 Web 和组织的集成只能从 Microsoft 获得。 利用 Microsoft 搜索，搜索管理员可以通过对组织的了解，使用户能够轻松查找相关内容。 

## <a name="components-that-find-content"></a>查找内容的组件
在Microsoft 搜索中，管理员创建[书签](manage-bookmarks.md)[、PowerApps、Q](integrate-powerapps.md)&[A](manage-qas.md)和[位置](manage-locations.md)，使内容更易于查找。 每个搜索组件都包括标题、URL 和一组触发关键字。

## <a name="bookmarks"></a>书签
只需几个 [步骤，](manage-bookmarks.md) 就可以创建书签。 每个书签都包括标题、URL 和一组触发关键字。 一个书签可以具有多个关键字，多个书签可以共享同一个关键字。 但保留的关键字无法共享。 创建或修改书签时，搜索索引将刷新，并且用户可以立即使用书签。

如果组织已 **升级在** SharePoint [中设置](http://sharepoint.com/)的结果，可以将这些结果导入Microsoft 搜索。 利用升级的结果，您可以快速填充搜索结果，使内容可供用户使用，Microsoft 搜索设置后就更高效。 我们建议你使用 SharePoint 中的升级结果作为参考，以了解如何命名和创建相关的搜索结果。 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>使用浏览器扩展添加或编辑书签
搜索管理员可以使用浏览器扩展轻松创建搜索内容。 若要将网站添加为书签，请安装浏览器扩展。 然后转到该网站，并添加为书签。 若要了解更多信息，请参阅 [管理书签](manage-bookmarks.md)。

目前，浏览器扩展可用于[Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) [和 Google Chrome：](https://www.google.com) 
- 若要下载边缘扩展，请转到["Microsoft Store"。](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)
- 若要下载 Chrome 扩展，请转到 [Chrome Web 应用商店](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)。

## <a name="powerapps"></a>PowerApps

通过将现有 [PowerApps](integrate-powerapps.md) 添加到 [书签](manage-bookmarks.md)，用户可以完成输入休假时间或报告费用等任务。 

借助 [PowerApps，](integrate-powerapps.md)可以生成在浏览器或手机或平板电脑上运行的业务应用。 无需编码体验。 PowerApps 在任何浏览器和任何设备上都运行。 添加它们的时间少于一分钟。 若要详细了解 PowerApps，请参阅以下文章：
- [引导式学习](/learn/browse/?products=powerapps)
- [PowerApps 文档](/powerapps/maker/canvas-apps/get-sessionid)
- [PowerApps 主页](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>将 PowerApp 添加到书签

1. 查找 [要](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) 添加的 PowerApp 的应用 ID。
1. 在管理Microsoft 365 [中](https://admin.microsoft.com)，转到 **"设置Microsoft 搜索"。**  >   
1. 添加或查找一个要向其添加 PowerApp 的书签。
1. 在 **书签设置中**，选择 **Power App**。 然后选择添加 **Power App**。
1. 输入 **应用 ID**。 高度和宽度自动调整。 [书签](manage-bookmarks.md) 可以支持纵向和横向方向，但当前不能更改大小。 为了便于测试，书签预览显示功能齐全的 PowerApp 。
1. 选择“**发布**”或“**保存到草稿**”。

## <a name="qa"></a>问答

创建[问答&创建](manage-qas.md)[书签](manage-bookmarks.md)。 使用问答&，你可以为用户提供问题的答案，而不只是指向网页的链接。 您可以使用可用工具以格式文本格式回答。 如果书签和问答&同一关键字，则首先显示书签结果。 与书签一样，&A 索引的问答在添加或更改问答后立即&刷新。 

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
> 如果模板文件中&，则不能导入问答项。 若要防止错误，请确保导入文件的格式正确，并且包含所有必需信息。 请参阅如何防止导入 [错误的详细信息](#prevent-import-errors)。

## <a name="locations"></a>位置

[借助位置](manage-locations.md)，用户可以查找地址并找到组织的大楼。 **位置功能** 为办公室、校园和建筑物提供了准确的位置，以及路线和导航。 为了获得最佳结果，管理员需要将组织的所有重要位置添加到Microsoft 搜索。 与 [Bookmarks](manage-bookmarks.md) 和 [Q&A](manage-qas.md)不同，Locations 索引不会立即刷新。 新位置或已更改的位置可能需要几个小时才能显示在搜索结果中。

## <a name="get-started"></a>入门
若要了解用户需要的信息，并轻松发现该信息，请尝试以下一些方法：

- 使用 Intranet 搜索日志，来确定获得最多流量的网站和页面。
- 确定每天或每周使用的应用、网站和工具。
- 查找员工福利的直接链接。
- 查找用户需要了解的策略和流程。
- 确定与支持人员联系的用户及其如何联系。
- 获取季节性或基于业务周期定期需要的信息。 例如，人们正在寻找工具来预订请假或季度财务更新。
- 收集区域用户或移动用户的策略。 示例是因位置而异的好处。
- 确定常见 Web 搜索的内部网站和信息。 示例包括交通、公共交通信息、本地天气、公司合作伙伴提供的折扣以及健康与健身计划。
- 查找有关公司赞助的活动、会议或聚餐的信息。
- 研究常见 IT、人力资源和支持问题以及常见问题 (FAQ) 和答案。

## <a name="involve-smes-and-users"></a>涉及中小型企业和用户
在组织中，用户搜索一系列简单到复杂的主题。 简单示例包括办公室地址和员工福利。 复杂示例包括新的工作流程、技术信息和操作方法内容。 若要创建或查找如此广泛的内容，你需要在不同领域、主题和技术方面的专业知识。 

大多数搜索管理员没有关于每个主题的特定知识。 若要在无需外部资源帮助的情况下扩展可用内容的数量，请向组织其他人寻求专长和知识。

### <a name="get-content-from-smes"></a>从 SMES 获取内容
利用组织中与 (行业) 专家，包括来自人力资源、支持、销售、技术和其他关键领域的专家。 如果将内容添加为编辑人员，SMES 可以直接Microsoft 搜索内容。 

### <a name="involve-your-users"></a>让用户参与进来
让用户推荐要设为书签的资源。 还要要求用户报告损坏或无效链接等错误。

## <a name="set-up-components"></a>设置组件
若要添加或编辑单个或批量 [书签](manage-bookmarks.md)、Q [&A](manage-qas.md)和 [Locations，](manage-locations.md)请执行以下各节中的步骤。 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>添加或编辑单个书签、&A 或位置组件
1. 在管理Microsoft 365 [中](https://admin.microsoft.com)，转到 **"设置Microsoft 搜索"。**  >   选择组件的命名选项卡。默认情况下 **，选择** "书签"选项卡。
1. 若要添加组件，请选择"**添加新"。** 
1. 若要编辑组件，请在相关组件列表中选择书签。 
1. 在你添加或编辑信息时，预览将随之自动更新。

### <a name="bulk-add-or-edit-components"></a>批量添加或编辑组件
借助 **导入** 和 **导出功能**，搜索管理员可以批量创建或编辑书签、问答 [](manage-bookmarks.md)&[A](manage-qas.md)和 [位置](manage-locations.md)。 当管理员希望添加或编辑多个组件时，此功能非常有用。 

导入和导出功能提供以下功能：
- **批量添加**。 在组件的模板文件中添加详细信息，然后导入它。
- **批量编辑**。 将组件导出到 CSV 文件，然后在导出的 CSV 中编辑书签详细信息，然后导入更新后的 CSV。
- **从导入升级的网站SharePoint。 [](http://sharepoint.com/)** 此功能仅适用于 [书签](manage-bookmarks.md)。
- **备份**。 将组件导出到 CSV 文件。

若要导入或导出组件，请执行以下步骤：
1. 在组件的命名选项卡的右上角， **选择导入**。 
1. 若要下载 CSV 文件的所有现有组件，请选择"导出 **"。**
1. 在右侧窗格中，选择使用 CSV 文件或从文件[导入SharePoint。](http://sharepoint.com/)
1. 若要获取所需字段和详细信息的列表，请下载组件的模板文件。 
1. 在模板文件中添加或编辑组件详细信息。 然后，将其保存到您的计算机上。 
1. 在组件的"导入"**窗格中**，选择"浏览 **"。** 然后选择您想要的 CSV 文件，然后选择 **导入**。

### <a name="template-guidelines"></a>模板指南
在使用模板文件时，请注意以下指南和限制：
- 从不编辑以下字段中的数据 *：Id、Last* *Modified* 和 *Last Modified By*。
- 如果包含现有 *书签的 ID，* 它将替换为导入文件中的信息。
- 如果现有文件中存在标题或 URL 相同的书签，则使用导入文件中的信息更新书签。
- 模板文件中并非所有字段都是必需的，并且所需字段因书签状态而异。
- 根据 *状态字段* ，书签保存为 **草稿**、 **建议** 或 **计划**。 否则，将自动发布它们。
- 如果管理多个组织，可以从一个组织导出书签，然后将它们导入另一个组织。 但是，在导入之前，你必须删除 *Id* 列中的数据。

> [!Note]
> 如果模板文件中出现错误，则不能导入组件项。 若要防止错误，请确保导入文件的格式正确，并且包含所有必需信息。

### <a name="prevent-import-errors"></a>防止导入错误

如果任何必需数据缺失或无效，则会显示一条错误消息。 A 日志文件 generates with more information about the rows and columns to be corrected. 进行必要的编辑，然后再次尝试导入该文件。 在解决所有错误之前，无法导入或保存任何书签。

若要防止错误，请确保导入文件的格式正确，并满足以下要求：
- 导入模板中包含标题行和所有列。
- 列顺序与导入模板相同。
- 除了三个可为空的列之外，所有列都有值 *：Id、Last* *Modified* 和 *Last Modified By。* 
- " *状态* "列不为空。

### <a name="titles-and-descriptions"></a>标题和说明
连接的标题和说明可帮助用户确定结果是否回答其搜索查询。 好的标题和说明反映了结果的核心用途。 例如，标题为"托 **儿** 权益"和"了解帮助支付托儿费用 *的好处"。* 借助此连接数据，搜索托儿服务 **的用户** 可以找到资金支持权益，并获取链接了解更多信息。

### <a name="keywords"></a>关键字
使用关键字，您组织的用户可以搜索和查找相关内容。 您需要将关键字术语与它们的相关搜索结果关联。 Microsoft 搜索根据内容的标题和 URL 提供关键字建议。 若要标识更多关键字，请获取这些问题的解答：

1. **哪些搜索词可以找到您标识的信息？** 请参阅组织的任何现有术语，以及相关变体、首字母缩略词、主题和主题。
1. **人们使用哪些变体或词来讨论此信息？** 请支持团队提供这些关键字。

例如，如果您创建一个链接到用于提交休假请求的工具的结果，则关键字 **vacation** 和 submit vacation **请求** 是很好的可包含选项。 您组织的用户可能还搜索休假相关信息以及 **休假****或休假。** 若要让用户更轻松地查找相关内容，请添加这些关键字和其他关键字（如提交 **假日请求** 和 **请求休假**）。

### <a name="reserved-keywords"></a>保留关键字
 保留关键字是用于触发结果的唯一词条或短语。 与其他关键字不同，保留的关键字仅与一个结果相关联。 请慎用保留关键字，以便 Microsoft 搜索能够基于使用情况进行学习。

例如，用于提交工时的网站的书签。 如果 **日志时间** 是保留的关键字，则组织中搜索日志时间的用户会看到该网站是"记录"框中Microsoft 搜索书签。 

### <a name="group-related-content-with-keywords"></a>使用关键字对相关内容进行分组
如果您希望用户在搜索特定术语时查找相关内容集，请为所有相关内容分配相同的关键字。 例如，搜索与生命周期状态更改有关的过程和工具。 若要将有关更新权益、税务信息以及名称和别名更改的解答组合在一起，请包含一个关键字，如 **"我的关键字"。**

### <a name="search-settings"></a>搜索设置
使用搜索设置，您可以定制内容并面向特定的用户组。 以下Microsoft 搜索设置控制搜索结果何时显示以及谁可以看到它：

- **日期**。 若要控制内容何时可用或不可用，请设置开始日期和结束日期。 例如，与时间相关的材料将显示在搜索结果中。
- **国家/地区**。 可以选择一个或多个国家/地区，以便只有这些位置的用户才能看到特定内容。 例如，特定于国家/地区的信息只出现在那些国家/地区中的搜索结果中。
- **组** 设置使结果仅对所选组的成员可用。 例如，如果您创建的网站仅与人力资源部门的员工相关，则将此设置映射到相应的 HR 安全组。
- **设备或操作系统**。 选择设备类型或操作系统，以便只有在这些设备上搜索或使用这些系统的用户才能看到该书签。
- **目标变体**。 此设置根据用户的设备和位置改变书签的内容。

## <a name="test-your-content"></a>测试内容
创建书签 [和](manage-bookmarks.md) 问答&[A 后](manage-qas.md)，验证这些结果：
- 将显示正确的书签或&A。
- 所有与关键字组合在一起的内容将按计划一起显示。
- 搜索答案中不会显示任何意外内容。
- 书签或问答&足够的信息。

参与内容创建的用户和 SMES 可以帮助测试和验证搜索结果。

## <a name="review-and-update-periodically"></a>定期查看并更新
如书签 [和](manage-bookmarks.md) 问答等权威 [&需要](manage-qas.md) 保持新鲜度。 定期执行以下步骤：
- 修复或删除损坏和无效的 URL。
- 删除不再相关的&或问答。
- 检查工具、网站名称或团队名称更改。
- 请考虑书签或问答&是否足够权威或需要更明确的说明。

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>获取有关书签、问答&和位置的见解

Microsoft 搜索显示已发布、计划[或&书签](manage-qas.md)、问答和位置数。 [](manage-bookmarks.md) [](manage-locations.md) 仪表板[Insights按](./usage-reports.md)状态显示书签&问答和位置总计：

- **已发布：** 向用户推出的已发布结果数。
- **已计划：** 发布管道中的已计划结果数。
- **已建议：** 来自用户的建议数。

建议的 [书签](manage-bookmarks.md)、&[A](manage-qas.md)和 [位置](manage-locations.md) 是衡量内容差距的良好指标。 它们可帮助你了解用户查找但找不到内容。 此数据可能指示你需要创建多个书签、问答&A 或位置。 或者，您可能需要使用更好的关键字、保留的关键字和搜索字符串来更新现有内容，使内容更可发现。

### <a name="review-top-search-queries"></a>查看热门搜索查询

若要了解哪些搜索生成了过去 90 天内最多的展示次数，请查看热门搜索查询。 *"* 印象"表示在搜索结果中查看页面多少次。 Insights仪表板上的"热门查询["](./usage-reports.md)卡片显示每个结果类型的前 25 个用户搜索、搜索总数和点击率 (CTR) 。 通过此报告，您可以确定搜索查询量并确定具有较高和较低搜索活动的查询。

较低的搜索计数可能表示用户不满意。 要么用户不查找该内容，要么使用不同的关键字来查找该内容。 CTR 可显示用户选择升级结果的频率以及查询规则和结果对用户的有用程度。 较低的 CTR 表示用户找到内容，但无法满足其需求。 在这种情况下，请查看内容。 若要使内容与搜索查询保持一致，请确保它与用户的搜索相匹配，并更新标题、说明和关键字。 

### <a name="analyze-impressions-by-result-type"></a>按结果类型分析展示次数

仪表板上"展示次数"**分发卡中的** 易读图形Insights显示 [](./usage-reports.md)不同时间帧的展示次数。 时间轴将会显示结果类型的每日展示次数。 使用这些图形，可以确定最常用或不经常使用的结果类型。 不经常使用特定结果类型不一定意味着结果类型不良好。 它只显示用户如何使用搜索结果。

 如果用户首选特定结果类型，则可能会创建更多相同类型的搜索结果。 若要确保关键字适当，请查看使用率较低的结果类型的关键字。 通过此报告，还可以查看用户行为在一段时间的变化。