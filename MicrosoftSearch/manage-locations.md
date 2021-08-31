---
title: 管理位置
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: 随着时间推移，可能需要更新位置状态和内容以保持其相关性。
ms.openlocfilehash: 0c93e29c8c899a4b70a30cf97354cf00fc19667f
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701991"
---
# <a name="manage-locations"></a>管理位置

## <a name="location"></a>位置

通过提供办公室、校园和大楼的准确位置和路线及导航，位置可帮助用户查找地址并找到你组织的大楼。 管理员应添加组织的所有重要位置。 与书签和问答不同，索引不会立即刷新，新位置或更改的位置可能需要几个小时才能显示在搜索结果中。

### <a name="add-or-edit-a-single-location"></a>添加或编辑单个位置

1. 在 ["Microsoft 365 管理中心"](https://admin.microsoft.com)中，转到 [**"位置"**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)
1. 若要添加新位置，请选择"添加 **"。**
1. 若要编辑位置，请在相关位置列表中选择该位置。
1. 在你添加或编辑信息时，预览将随之自动更新。
1. 保存所做的更改。

### <a name="bulk-add-or-edit-locations"></a>批量添加或编辑位置

管理员可以使用导入或导出功能批量创建或编辑位置。

使用导入/导出功能可以：

1. 批量添加位置 - 在位置模板文件中添加详细信息，然后导入它。
1. 批量编辑位置 - 将书签导出到 .csv 文件，编辑导出的 .csv 文件中的位置详细信息，然后导入更新的 .csv 文件。
1. 备份位置 – 将现有位置导出到.csv文件。

若要导出或导入位置：

1. 在“**位置**”选项卡的右上角，选择“**导入**”。
选择“**导出**”以将现有位置下载到 .csv 文件中。
1. 在右侧窗格中，选择使用 .csv 文件导入的选项。
下载模板文件以获取必填字段和详细信息的列表。
1. 在模板文件中添加或编辑位置详细信息，然后将其保存在你的计算机上。
1. 在“**导入位置**”窗格中，选择“**浏览**”，然后选择要导入的 .csv 文件。
1. 选择“**导入**”。

以下是关于模板文件的一些要点：

- 请勿编辑以下字段中的数据：*Id*、*上次修改时间* 和 *上次修改者*
- 如果包含现有位置的 *ID，* 它将替换为导入文件中的信息。
- 如果存在同名的现有位置，该位置将用导入文件中的信息进行更新。
- 模板文件中并非所有字段都是必需的，并且必填字段因位置状态而异。
- 根据" *状态* "字段，位置将另存为草稿、建议、计划或自动发布。
- 对于管理多个组织的合作伙伴，你可以从一个组织导出位置，然后将它们导入另一个组织。 但是，在导入之前，你必须删除 *Id* 列中的数据。

> [!NOTE]
> 如果模板文件中出现任何错误，则不能导入位置。 为防止出错，请确保导入文件具有正确格式，并且包含所有必需信息。

有关如何防止错误的详细信息，请参阅[防止导入错误](manage-bookmarks.md#prevent-import-errors)。
