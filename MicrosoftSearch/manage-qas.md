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
description: 单独查找和更新答案，或使用 Microsoft Search tools 以一次性编辑 Q&。
ms.openlocfilehash: 78a6ee0ff14f3347b0b2e2a65cc1ee0f68500981
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996082"
---
# <a name="manage-qas"></a>管理问答

创建问答类似于创建书签。 Q&，使您可以回答用户的问题，而不只是提供指向网页的链接。 您还可以设置格式文本中的答案的格式。 如果书签和 Q&共享相同的关键字，则首先显示书签结果。 与书签一样，在添加或更改 Q&A 之后，会立即刷新 Q&索引。

## <a name="add-or-edit-a-single-qa"></a>添加或编辑单个问答

1. 转到 **Microsoft 365 管理中心**。
1. 在导航窗格中，转到 "**设置**  >  **Microsoft Search**  >  **问答**  >  [**问答"&**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. 若要添加问答，请选择“**新增**”。
若要编辑问答，请在相关问答列表中选择问答。 在你添加或编辑信息时，预览将随之自动更新。
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

目前，浏览器扩展适用于 Microsoft Edge 和 Chrome。

- 若要下载边缘（旧版）的扩展，请转到[Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)。
- 若要下载分机版式或边缘（Chromium），请转到[Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)。

## <a name="bulk-add-or-edit-qas"></a>批量添加或编辑问答

管理员可以使用导入和导出功能批量创建或编辑 Q&As。

使用导入/导出功能执行以下操作：

- 批量添加 Q&-在 Q&模板文件中添加详细信息，然后将其导入。
- 批量编辑 Q&As-Export Q&为 .csv 文件，请编辑 Q&导出文件中的详细信息，然后导入该文件。
- 以 .csv 文件的形式备份 Q&As-Export Q&。

导入或导出 Q&为：

1. 在“问答”选项卡的右上角，选择“**导入**”。
选择 "**导出**" 以下载所有现有的 Q&，如 .csv 文件中所示。
1. 在右侧窗格中，选择要使用 .csv 文件导入的选项。 下载模板文件以获取必需字段和详细信息的列表。
1. 添加或编辑 Q&模板文件中的详细信息，并将其保存到计算机上。
1. 在 "**导入 Q&** 窗格中，选择"**浏览**"，然后选择要导入的 .csv 文件。
1. 选择“**导入**”。

重要的模板文件提示：

- 请勿编辑以下字段中的数据：**Id**、**上次修改时间**和**上次修改者**
- 如果包含现有书签的 **Id**，则会将其替换为导入文件中的信息。
- 如果现有书签具有相同的标题或 URL，则将使用导入文件中的信息更新该书签。
- 并不是模板文件中的所有字段都是必需的，并且根据书签状态不同，必需的字段也会有所不同。
- 根据 "**省/市/自治区**" 字段，将书签保存为*草稿*、*建议*或*计划*或自动发布。
- 对于管理多个组织的合作伙伴：您可以从一个组织中导出您的书签并将其导入到另一个组织中。 但是，在导入之前，你必须删除 **Id** 列中的数据。

> [!NOTE]
> 您不能导入 Q&，就像模板文件中有任何错误一样。 若要防止错误，请确保您的导入文件格式正确，并包含所有必需的信息。

有关避免错误的详细信息，请参阅[防止导入错误](manage-bookmarks.md#prevent-import-errors)。
