---
title: 管理书签
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: 创建和更新书签以及批量编辑 Microsoft 搜索的书签结果的方式
ms.openlocfilehash: 0cd37ebcd7cd3ea7bbe55064fd41a3c42b2e4725
ms.sourcegitcommit: f9760d027637cc0d2e5c3a9e47928422cb6e452a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2019
ms.locfileid: "36170317"
---
# <a name="manage-bookmarks"></a>管理书签

你只需几步即可创建书签。 每个书签都包括标题、URL 和一组触发关键字。 书签可以具有多个关键字，多个书签可以共享同一个关键字，但保留关键字不能共享。 创建或修改书签时，搜索索引将立即刷新，并立即向用户提供书签。

如果你的组织在 SharePoint 中设置了“升级结果”，则可以将升级结果导入 **Microsoft 搜索**，并将导入的内容提供给用户。 只要你设置了 **Microsoft 搜索**，就可以轻松快速地填充搜索结果，并提高用户效率。 我们建议你使用 SharePoint 中的升级结果作为参考，以了解如何命名和创建相关的搜索结果。 

## <a name="add-or-edit-a-single-bookmark"></a>添加或编辑单个书签
1. 转到 **Microsoft 365 管理中心**。
1. 在导航窗格中，转到**设置**，然后选择**Microsoft 搜索**。
默认情况下，“**书签**”选项卡处于选中状态。
1. 若要添加书签，请选择“**新增**”。 若要编辑书签，请从相关书签列表中选择书签。 
1. 在你添加或编辑信息时，预览将随之自动更新。
1. 保存所做的更改。

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>使用浏览器扩展添加或编辑书签
搜索管理员可以使用浏览器扩展轻松创建搜索内容。 安装浏览器扩展，然后转到要添加为书签的网站，并将该网站添加为书签。

目前，为 Microsoft Edge 和 Chrome 提供了浏览器扩展。 
- 若要下载 Microsoft Edge 扩展，请转到 [Microsoft 官方商城](https://www.microsoft.com/en-us/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)并下载应用。
- 若要下载 Chrom 扩展，请转到 [Chrome 网上应用商店](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)并下载应用。

## <a name="bulk-add-or-edit-bookmarks"></a>批量添加或编辑书签
搜索管理员可以使用导入或导出功能批量创建或编辑书签。 当管理员想要添加或编辑大量书签时，这是一项非常有用的功能。 

使用导入/导出功能可以：
- 批量添加书签 - 在书签模板文件中添加详细信息，然后导入它。
- 批量编辑书签 - 将书签导出到 .csv 文件，编辑导出的 .csv 文件中的书签详细信息，然后导入更新的 .csv 文件。
- 从 SharePoint 导入已升级的网站。
- 备份书签 - 将书签导出到 .csv 文件。

若要导入或导出书签：
1. 在“**书签**”选项卡的右上角，选择“**导入**”。 选择“**导出**”以将所有现有的书签下载到 .csv 文件中。
1. 在右侧窗格中，选择使用 .csv 文件或从 SharePoint 导入的选项。
下载模板文件以获取必填字段和详细信息的列表。 
1. 在模板文件中添加或编辑书签详细信息，然后将其保存在你的计算机上。 
1. 在“**导入书签**”窗格中，选择“**浏览**”，然后选择要导入的 .csv 文件。
1. 选择“**导入**”。

以下是有关模板文件的一些重要注意事项：
- 请勿编辑以下字段中的数据：*Id*、*上次修改时间*和*上次修改者*
- 如果包含现有书签的 *Id*，则会将其替换为导入文件中的信息。
- 如果存在具有相同标题或 URL 的现有书签，则将使用导入文件中的信息更新该书签。
- 在模板文件中，并非所有字段都是必填的，并且必填字段因书签状态而异。
- 基于“*状态*”字段，书签会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。
- 对于拥有多个租户的组织，你可以从某个租户导出书签并将其导入另一个租户。 但是，在导入之前，你必须删除 *Id* 列中的数据。

### <a name="prevent-import-errors"></a>防止导入错误
如果任何所需数据缺失或无效，你将收到错误，并且系统会生成一个日志文件，其中包含有关要更正的行和列的详细信息。 完成必要的编辑，并再次尝试导入该文件。 在解决所有错误之前，你无法导入或保存任何书签。

为防止出错，请确保导入文件具有正确格式，并且：
- 包含导入模板中的标题行和所有列
- 列顺序与导入模板相同
- 所有列都包含值，但三个可以为空的列除外：*Id*、*上次修改时间*和*上次修改者* 
- “*状态*”列不能为空，因为此信息是必需的

## <a name="powerapps"></a>PowerApps
帮助用户完成任务，例如通过将现有的 PowerApps 添加到书签来输入休假时间或上报费用。 

### <a name="what-are-powerapps"></a>什么是 PowerApps？
PowerApps 是一种服务，通过该服务可生成在浏览器、手机或平板电脑上运行的商业应用，且无需编码经验。 PowerApps 可在任何浏览器和任何设备上运行，且添加该服务所需时间不到一分钟。 有关 PowerApps 的详细信息，请参阅：
- [引导学习](https://docs.microsoft.com/zh-CN/learn/browse/?products=powerapps)
- [文档](https://docs.microsoft.com/zh-CN/powerapps/maker/canvas-apps/get-sessionid)
- [PowerApps 主页](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>将 PowerApp 添加到书签
1. 查找要添加的 [PowerApp 的应用 ID](https://docs.microsoft.com/zh-CN/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)。
1. 登录并转到 **Microsoft 365 管理中心**。
1. 在导航窗格中，转到“**设置**”，然后选择“**Microsoft 搜索**”。
1. 添加或查找一个要向其添加 **PowerApp** 的书签。
1. 在“**书签设置**”中，选择“**Power 应用**”，然后选择“**添加 Power 应用**”。
1. 输入或粘贴“**应用 ID**”。
    将自动调整高度和宽度。 书签支持纵向和横向设置，但是目前无法改变大小。 书签预览将显示功能齐全的 PowerApp，使其易于测试。
1. 选择“**发布**”或“**保存到草稿**”。
