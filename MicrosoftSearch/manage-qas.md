---
title: 管理问答
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: 单独查找并更新答案或使用可用的Microsoft 搜索编辑问答&一次编辑问答。
ms.openlocfilehash: 2ee42e3feaf5c14b2af820360f753ecc2e116f9b
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701982"
---
# <a name="manage-qas"></a>管理问答

创建问答类似于创建书签。 Q&As allow you to answer the user's questions instead of just providing a link to a webpage. 您还可以以格式文本格式显示答案。 如果书签和问答&同一关键字，则首先显示书签结果。 与书签一样，&A 问答添加&更改后，将立即刷新索引的问答。

## <a name="add-or-edit-a-single-qa"></a>添加或编辑单个问答

1. In the [Microsoft 365 管理中心，](https://admin.microsoft.com)go to [**Q&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. 若要添加问答&，请选择"添加 **"。**
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

## <a name="add-or-edit-qas-using-browser-extensions"></a>使用浏览器扩展&或编辑问答

搜索管理员可以使用浏览器扩展轻松创建搜索内容。 安装浏览器扩展，然后转到要生成问答&站点。 然后，可以创建问答&并包含指向源网站的链接。

目前，浏览器扩展可用于 Microsoft Edge Chrome。

- 若要下载旧版边缘 (的) ，[请转到Microsoft Store。](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)
- 若要下载 Chrome 或 Edge (Chromium) ，请转到 Chrome [Web 应用商店](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)。

## <a name="bulk-add-or-edit-qas"></a>批量添加或编辑问答

管理员可以使用导入和导出功能批量创建或编辑问答&问题。

使用 导入/导出 功能可：

- 批量添加 Q&As - 在问答模板&添加详细信息，然后导入它。
- 批量编辑&为 - 将问答&导出到 .csv 文件，编辑导出&中的问答详细信息，然后导入该文件。
- 备份问答&- 将问答&导出到.csv文件。

若要导入或导出问答&为：

1. 在“问答”选项卡的右上角，选择“**导入**”。
选择 **导出** 以下载所有现有问答&一个.csv文件。
1. 在右侧窗格中，选择使用文件导入.csv选项。 下载模板文件，获取所需字段和详细信息的列表。
1. 添加或编辑&模板文件中的详细信息，并将其保存在您的计算机上。
1. In the **Import Q&A** pane， select **Browse**， and then select the .csv file that you want to import.
1. 选择“**导入**”。

重要的模板文件提示：

- 请勿编辑以下字段中的数据：**Id**、**上次修改时间** 和 **上次修改者**
- 如果包含现有书签的 **Id**，则会将其替换为导入文件中的信息。
- 如果存在标题或 URL 相同的现有书签，该书签将用导入文件中的信息进行更新。
- 模板文件中并非所有字段都是必需的，并且所需字段因书签状态而异。
- 根据 **"状态"** 字段，书签保存为 *草稿*、建议或计划书签，或者自动发布。
- 对于管理多个组织的合作伙伴：你可以从一个组织导出书签，然后将它们导入另一个组织。 但是，在导入之前，你必须删除 **Id** 列中的数据。

> [!NOTE]
> 无法导入问答&就像模板文件中有任何错误一样。 若要防止错误，请确保导入文件的格式正确，并包含所有必需信息。

有关避免错误的详细信息，请参阅防止 [导入错误](manage-bookmarks.md#prevent-import-errors)。
