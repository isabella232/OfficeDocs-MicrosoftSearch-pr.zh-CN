---
title: Microsoft 搜索的文件共享 Graph 连接器
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: 为 Microsoft 搜索设置文件共享图形连接器
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097418"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>文件共享 Graph 连接器

文件共享 Graph 连接器允许组织中用户搜索本地 Windows 文件共享。

> [!NOTE]
> 阅读 [**Graph 连接器的安装程序**](configure-connector.md) 文章，了解一般的 Graph 连接器设置过程。

## <a name="before-you-get-started"></a>在开始使用之前

### <a name="install-the-graph-connector-agent"></a>安装 Graph 连接器代理

若要为 Windows 文件共享编制索引，必须安装和注册 Graph 连接器代理。 请参阅 ["安装 Graph 连接器代理"](on-prem-agent.md) 了解更多信息。  

### <a name="content-requirements"></a>内容要求

### <a name="file-types"></a>文件类型

可以索引和搜索以下格式的内容：DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPT、PPTM、PPTX、TXT、XLB、XLC、XLSB、XLS、XLS、XLSX、XLSX、XML、XPS 和 ZIP。 仅对这些格式的文本内容编制索引。 将忽略所有多媒体内容。 对于不属于此格式的任何文件，仅对元数据编制索引。

### <a name="file-size-limits"></a>文件大小限制

支持的最大文件大小为 100 MB。 超过 100 MB 的文件不编制索引。 处理后的最大大小限制为 4 MB。 当文件大小达到 4 MB 时，处理将停止。 因此，文件中呈现的一些短语可能无法用于搜索。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

在 **"连接到数据源"** 页上，选择 **"** 文件共享"并提供名称、连接 ID 和说明。 下一页，提供文件共享的路径，然后选择之前安装的 Graph 连接器代理。 输入对文件共享中所有文件的读取访问权限 [的 Microsoft Windows](https://microsoft.com/windows) 用户帐户的凭据。

### <a name="preserve-last-access-time"></a>保留上一次访问时间

当连接器尝试对文件进行爬网时，将更新其元数据中的"上次访问时间"字段。 如果您依赖于该字段作为任何存档和备份解决方案，并且不希望在连接器访问它时对其进行更新，您可以在"高级设置"页中 **配置此选项。**

## <a name="step-4-manage-search-permissions"></a>步骤 4：管理搜索权限

您可以限制基于"共享 (访问控制列表"或"新技术文件系统"或"NTFS"或"NTFS") 搜索任何文件的权限。 如果要使用"共享访问控制列表"，请在"高级设置"页上 **选择相应的** 选项。 如果要使用 NTFS 访问控制列表，请在"管理搜索权限"页上 **选择相应的** 选项。

## <a name="step-5-assign-property-labels"></a>步骤 5：分配属性标签

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>步骤 6：管理架构

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>步骤 7：选择刷新设置

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
