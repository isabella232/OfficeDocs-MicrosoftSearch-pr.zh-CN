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
description: 为 Microsoft 搜索设置文件共享连接器
ms.openlocfilehash: bf9fb730abd4ca6e42b681893525bbe3dd8a1419
ms.sourcegitcommit: 249f41723dd6fda1e93ee1a8f3f7571ef066454b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750894"
---
# <a name="file-share-connector"></a>文件共享连接器

借助文件共享 Graph 连接器，贵组织的用户可以搜索本地 Windows 文件共享。

本文适用于 Microsoft 365 管理员或配置、运行和监视文件共享连接器的任何人。 它介绍了如何配置连接器和连接器功能、限制和故障排除技术。

## <a name="install-graph-connector-agent"></a>安装 Graph 连接器代理

若要为 Windows 文件共享编制索引，必须安装和注册 [Graph 连接器代理](on-prem-agent.md) 软件。

## <a name="content-requirements"></a>内容要求

### <a name="file-types"></a>文件类型

可以索引和搜索以下格式的内容：DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPT、PPTM、PPTX、TXT、XLB、XLC、XLSB、XLS、XLS、XLSX、XLSX、XML、XPS 和 ZIP。 仅对这些格式的文本内容编制索引。 将忽略所有多媒体内容。 对于不属于此格式的任何文件，仅对元数据编制索引。

### <a name="file-size-limits"></a>文件大小限制

支持的最大文件大小为 100 MB。 超过 100 MB 的文件不会编制索引。 处理后的最大大小限制为 4 MB。 当文件大小达到 4 MB 时，处理将停止。 因此，文件中呈现的一些短语可能无法用于搜索。

## <a name="connect-to-a-data-source"></a>连接到数据源

在 **"连接到数据源"** 页上，选择 **"** 文件共享"并提供名称、连接 ID 和说明。 下一页，提供文件共享的路径并选择之前安装的 Graph 连接器代理。 输入对文件共享中所有文件的读取访问权限 [的 Microsoft Windows](https://microsoft.com/windows) 用户帐户的凭据。

## <a name="preserve-last-access-time"></a>保留上一次访问时间

当连接器尝试对文件进行爬网时，将更新其元数据中的"上次访问时间"字段。 如果您依赖于该字段作为任何存档和备份解决方案，并且不希望在连接器访问它时对其进行更新，您可以在"高级设置"页中 **配置此选项。**

## <a name="manage-search-permissions"></a>管理搜索权限

您可以限制基于"共享 (访问控制列表"或"新技术文件系统"或"NTFS"或"NTFS") 搜索任何文件的权限。 如果要使用"共享访问控制列表"，请在"高级设置"页上 **选择相应的** 选项。 如果要使用 NTFS 访问控制列表，请在"管理搜索权限"页上 **选择相应的** 选项。

## <a name="assign-property-labels"></a>分配属性标签

可以通过从选项菜单中选择来为每个标签分配源属性。 虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更准确的搜索结果。

## <a name="manage-schema"></a>管理架构

在"管理架构"屏幕上，你可以选择更改架构属性 (可查询、可搜索、可检索和可精简 **)** 这些属性、添加可选别名以及选择 **Content** 属性。

## <a name="set-the-refresh-schedule"></a>设置刷新计划

建议的默认刷新计划间隔为 15 分钟，但您可以根据您的首选项更改它。

## <a name="result-layout"></a>结果布局

建议使用默认结果布局来显示文件共享连接器结果，因为它具有相应的图标和控件，可帮助你导航到文件路径。 如果创建新的结果布局，它将覆盖默认值。
