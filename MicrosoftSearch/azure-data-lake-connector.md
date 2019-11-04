---
title: 用于 Microsoft 搜索的 Azure Data Lake 连接器
ms.author: v-pamcn
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置 Azure Data Lake Storage Gen2 connector for Microsoft Search
ms.openlocfilehash: bedd7307ca2add52408bb9a5e3b3b21fd75df258
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949590"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Azure Data Lake Storage Gen2 connector

使用[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) connector，组织中的用户可以搜索文件及其内容。 此连接器访问 azure Data Lake Storage Gen 2 帐户内存储在 Azure Blob 容器和支持层次结构的文件夹中的数据。

本文适用于 Microsoft 365 管理员或任何配置、运行和监控 Azure Data Lake Storage Gen2 连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。

## <a name="connect-to-a-data-source"></a>连接到数据源

### <a name="primary-storage-connection-string"></a>主存储连接字符串 
在 "**身份验证和配置**" 屏幕上，提供主存储连接字符串。 该字符串是允许访问您的存储帐户所必需的。 若要查找您的连接字符串，请转到[azure 门户](https://ms.portal.azure.com/#home)，并导航到 Azure Data Lake Storage Gen2 帐户的 "**密钥**" 部分。 将连接字符串复制并粘贴到屏幕上的相应字段中。

如果您不想提供**AccountKey** （主存储连接字符串中的参数），则必须授予对 Graph 连接器服务的读取访问权限。 在 Azure Data Lake Storage Gen2 帐户的 "**访问控制**" 选项卡中，按照该页面上的说明授予对以下应用的访问权限：
* **第一方应用程序 ID：** 56c1da01-2129-48f7-9355-af6d59d42766
* **第一方应用程序名称：** Graph 连接器服务

### <a name="storage-account-and-queue-notifications-optional"></a>存储帐户和队列通知（可选）
在将来可能会添加在图形连接器服务中实时处理更改的支持。 在这种情况下，我们将监视存储在队列中的 Azure Data Lake Storage Gen2 更改通知。 您需要在与 Azure Data Lake Storage Gen2 或其他存储帐户相同的帐户中创建队列。

创建队列后，转到 "队列" 页中的 "**事件**" 选项卡以配置事件订阅。 选择队列将接收的所有 Blob 事件并将队列连接到 Azure Data Lake Storage Gen2 帐户。

## <a name="manage-the-search-schema"></a>管理搜索架构
在 "**管理架构**" 屏幕上，您可以选择更改与托管属性相关联的架构属性（可**查询**、可**搜索**和可**检索**）。 这些托管属性属性是从 Azure Data Lake Storage Gen2 帐户编制索引的数据。

## <a name="manage-search-permissions"></a>管理搜索权限
在 "**管理搜索权限**" 屏幕上，您可以选择从您的存储帐户中接收访问控制列表（acl）。 设置这些搜索权限时，将根据分配给已登录的 Azure AD 用户搜索内容的权限对搜索内容进行修整。 或者，您可以选择将从存储帐户编制索引的所有内容对组织中的所有人可见。 在这种情况下，组织中的每个人都将有权访问存储帐户中的所有数据。
 
## <a name="set-the-refresh-schedule"></a>设置刷新计划
在 "**刷新设置**" 屏幕上，您可以设置增量爬网间隔和完全爬网间隔。 对于增量爬网，默认情况下，Azure Data Lake Storage Gen2 连接器的默认间隔为15分钟，对于完全爬网，则为一周。
 
## <a name="limitations"></a>限制
目前，Azure Data Lake Storage Gen2 多协议访问仅适用于美国、西部、加拿大、加拿大、东、东、西亚、北欧、东 US2、东南亚、西欧洲、西 US、澳大利亚东部、日本东部、西 US2 和巴西的美国中部南.

有关更新和详细信息，请参阅[Azure Data Lake Storage 上的多协议访问（预览）](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access)。


