---
title: 管理问答
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: 查找和更新单个解答或使用可用的 Microsoft 搜索工具同时编辑所有解答
ms.openlocfilehash: 0877de027b68589e5ba15cd8109ea7edeeae8725
ms.sourcegitcommit: c22e8c3dcc53857da677db98a1a2b7d5ca2c6170
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41721738"
---
# <a name="manage-qas"></a>管理问答

创建问答类似于创建书签。 问答可以让你回答用户的问题，而不仅仅是提供网页链接。 你可以使用可用工具以富文本形式来格式化答案。 如果书签和问答共享同一个关键字，则会先显示书签结果。 与书签一样，在添加或更改问答后将立即刷新问答索引。

## <a name="add-or-edit-a-single-qa"></a>添加或编辑单个问答

1. 转到 **Microsoft 365 管理中心**。
1. 在导航窗格中，转到“**设置**”，然后选择“**Microsoft 搜索**”。
1. 选择“**问答**”选项卡。默认情况下，第一个选项卡（**书签**）处于选中状态。
1. 若要添加问答，请选择“**新增**”。
若要编辑问答，请在相关问答列表中选择问答。
1. 在你添加或编辑信息时，预览将随之自动更新。
1. 保存所做的更改。

### <a name="supported-html-tags"></a>受支持的 HTML 标记

可以使用现有的 HTML 内容或为答案（说明）添加 HTML 标记。 不支持的标记将被忽略。  
支持以下 HTML 标记：

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

## <a name="add-or-edit-qas-using-browser-extensions"></a>使用浏览器扩展添加或编辑 Q&

搜索管理员可以使用浏览器扩展轻松创建搜索内容。 安装浏览器扩展，然后转到要从中生成 Q&的网站。 然后，您可以创建 Q&A 并包含指向源网站的链接。

目前，为 Microsoft Edge 和 Chrome 提供了浏览器扩展。

- 若要下载边缘扩展，请转到[Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)并下载该应用。
- 若要下载 Chrome 扩展，请转到[chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)并下载该应用。

## <a name="bulk-add-or-edit-qas"></a>批量添加或编辑问答

管理员可以使用导入和导出功能批量创建或编辑问答。 当管理员需要添加或编辑大量问答时，这是一项非常有用的功能。

使用导入/导出功能可以：

1. 批量添加问答 - 在问答模板文件中添加详细信息，然后导入它。
1. 批量编辑问答 - 将问答导出到 .csv 文件，编辑导出的 .csv 文件中的问答详细信息，然后导入更新的 .csv 文件。
1. 备份问答 - 将问答导出到 .csv 文件。

若要导入或导出问答：

1. 在“问答”选项卡的右上角，选择“**导入**”。
选择“**导出**”以将所有现有的问答下载到 .csv 文件中。
1. 在右侧窗格中，选择使用 .csv 文件导入的选项。
下载模板文件以获取必填字段和详细信息的列表。
1. 在模板文件中添加或编辑问答详细信息，然后将其保存在你的计算机上。
1. 在“**导入问答**”窗格中，选择“**浏览**”，然后选择要导入的 .csv 文件。
1. 选择“**导入**”。

以下是关于模板文件的一些要点：

- 请勿编辑以下字段中的数据：*Id*、*上次修改时间*和*上次修改者*
- 如果包含现有书签的 *Id*，则会将其替换为导入文件中的信息。
- 如果存在具有相同标题或 URL 的现有书签，则将使用导入文件中的信息更新该书签。
- 在模板文件中，并非所有字段都是必填的，并且必填字段因书签状态而异。
- 基于“状态”字段，书签会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。
- 对于管理多个组织的合作伙伴，您可以从一个组织中导出您的书签并将其导入到另一个组织中。 但是，在导入之前，你必须删除 *Id* 列中的数据。

**注意：** 如果模板文件中有任何错误，则无法导入问答。 为防止出错，请确保导入文件具有正确格式，并且包含所有必需信息。

有关如何防止错误的详细信息，请参阅[防止导入错误](manage-bookmarks.md#prevent-import-errors)。
