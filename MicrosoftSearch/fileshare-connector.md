---
title: 文件共享连接器
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: 设置用于 Microsoft 搜索的文件共享连接器
ms.openlocfilehash: a95cfe90ca35a385bb9ce3a4c565c18c5a42ec80
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408930"
---
# <a name="file-share-connector"></a>文件共享连接器

使用文件共享图形连接器，组织中的用户可以搜索内部部署 Windows 文件共享。

本文适用于 Microsoft 365 管理员或任何配置、运行和监视文件共享连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。

## <a name="install-graph-connector-agent"></a>安装图形连接器代理

若要为 Windows 文件共享编制索引，必须安装并注册 [Graph 连接器代理](on-prem-agent.md) 软件。

## <a name="content-requirements"></a>内容要求

### <a name="file-types"></a>文件类型

可以对以下格式的内容编制索引和搜索： DOC、.DOCM、.DOCX、DOT、.DOTX、.EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、.OBD、.OBT、ODP、ODS、ODT、、、、、XLS、.XLSX、.XLT、.pptm、XML、XPS 和 ZIP。 仅对这些格式的文本内容编制索引。 忽略所有多媒体内容。 对于不属于此格式的任何文件，将对单独的元数据编制索引。

### <a name="file-size-limits"></a>文件大小限制

支持的最大文件大小为 100 MB。 不会为超过 100 MB 的文件编制索引。 后处理的最大大小限制为 4 MB。 当文件的大小达到 4 MB 时处理停止。 因此，文件中存在的一些短语可能不适用于搜索。

## <a name="connect-to-a-data-source"></a>连接到数据源

在 " **连接到数据源** " 页上，选择 " **文件共享** " 并提供名称、连接 ID 和说明。 在下一页上，提供文件共享的路径，然后选择您之前安装的图形连接器代理。 输入具有文件共享中所有文件的读取访问权限的 [Microsoft Windows](https://microsoft.com/windows) 用户帐户的凭据。

## <a name="preserve-last-access-time"></a>保留上次访问时间

当连接器尝试对文件进行爬网时，会更新其元数据中的 "上次访问时间" 字段。 如果您依赖于任何存档和备份解决方案的字段，并且不希望在连接器访问它时对其进行更新，则可以在 " **高级设置** " 页中配置此选项。

## <a name="manage-search-permissions"></a>管理搜索权限

您可以限制基于共享访问控制列表或新技术文件系统 (NTFS) 访问控制列表中搜索任何文件的权限。 如果要使用共享访问控制列表，请在 " **高级设置** " 页上选择相应的选项。 如果要使用 NTFS 访问控制列表，请在 " **管理搜索权限** " 页上选择相应的选项。

## <a name="assign-property-labels"></a>分配属性标签

通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。 虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。

## <a name="manage-schema"></a>管理架构

在 " **管理架构** " 屏幕上，您可以选择更改架构属性， (可 **查询**、可 **搜索**、 **检索** 和 **可精简**) 与属性相关联，添加可选别名，然后选择 **Content** 属性。

## <a name="set-the-refresh-schedule"></a>设置刷新计划

建议的默认刷新计划间隔为15分钟，但您可以根据自己的偏好对其进行更改。
