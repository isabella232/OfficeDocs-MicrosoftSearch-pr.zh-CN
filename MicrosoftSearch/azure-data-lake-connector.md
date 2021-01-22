---
title: 用于 Microsoft 搜索的 Azure Data Lake 连接器
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 为 Microsoft 搜索设置 Azure Data Lake Storage Gen2 连接器
ms.openlocfilehash: 8891c9a1fdf5397c397a941b5131f014db9e7a54
ms.sourcegitcommit: 597c338bf9c1c425747ac74a9a1ae57c5e8957ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49920719"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Azure Data Lake Storage Gen2 连接器

借助 Azure Data Lake Storage Gen2 连接器，贵组织用户可以搜索存储在 [Azure Blob](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) 存储和 [Azure Data Lake Gen 2 存储](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) 帐户中的文件。

本文适用于 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理员或配置、运行和监视 Azure Data Lake Storage Gen2 连接器的任何人。 它概述了连接器配置、功能、限制和疑难解答技术。 在本文中，我们将 *Azure 存储* 用作 Azure [Blob](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) 存储和 [Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)存储的通用术语。

## <a name="connect-to-a-data-source"></a>连接到数据源

### <a name="primary-storage-connection-string"></a>主存储连接字符串

在 **"身份验证和配置"** 屏幕上，提供主存储连接字符串。 该字符串是允许访问存储帐户的必需字符串。 若要查找连接字符串，请转到 [Azure](https://ms.portal.azure.com/#home) 门户并导航到相关 Azure **存储帐户的** "密钥"部分。 将连接字符串复制并粘贴到屏幕上的相应字段中。

如果不希望在主存储连接字符串 (中提供 **AccountKey**) 参数，则需要为以下角色授予对 Graph 连接器服务的访问权限。  (此功能仅受分层存储支持。 传统 Blob 存储必须提供 AccountKey.) 
* 存储 Blob 数据读取器
* 存储队列数据参与者
* 存储 Blob Delegator

导航到 Azure **存储帐户** 的"访问控制"选项卡，并按照其中的说明授予对以下应用的访问权限：

* **第一方应用** ID：56c1da01-2129-48f7-9355-af6d59d42766
* **第一方应用名称：** Graph 连接器服务

### <a name="storage-account-and-queue-notifications-optional"></a>存储帐户和队列通知 (可选) 

将来可能会添加对在 Graph 连接器服务中实时处理更改的支持。 在这种情况下，我们将监视存储在队列中的 Azure 存储更改通知。 你需要在 Azure 存储帐户相同的帐户中创建队列。

创建队列后，请转到队列页面上的" **事件** "选项卡以配置 **事件订阅**。 选择队列将接收的所有 Blob 事件，将队列连接到 Azure 存储帐户。

## <a name="manage-search-permissions"></a>管理搜索权限

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

在 **"管理搜索** 权限"屏幕上，你可以选择从 [Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) 存储帐户 (访问控制列表) ACL。 设置这些搜索权限后，将基于分配给搜索内容的已登录 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) 用户的权限来修整搜索内容。 或者，可以选择使从存储帐户编制索引的所有内容对组织中的每个人可见。 在这种情况下，组织中的每个人都将有权访问存储帐户中的所有数据。

### <a name="azure-blob-storage"></a>Azure Blob 存储

对于与 [Azure Blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)的连接，从配置源编制索引的所有内容对组织中的每个人都可见。 Azure Blob 存储中不支持 Blob 级别的访问控制列表。

## <a name="search-permissions"></a>搜索权限

Azure Data Lake Storage Gen2 连接器支持对具有此数据源访问权限的任何人或仅人员可见的 **搜索权限**。 搜索结果中出现的索引数据可能对组织所有用户可见，或仅对有权访问每个项目的用户可见。

## <a name="assign-property-labels"></a>分配属性标签

可以通过从选项菜单中选择来为每个标签分配源属性。 虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更准确的搜索结果。

## <a name="manage-schema"></a>管理架构

在"管理架构"屏幕上，你可以选择更改架构属性 (可查询、可搜索、可检索和可精简 **)** 这些属性、添加可选别名以及选择 **Content** 属性。

## <a name="set-the-refresh-schedule"></a>设置刷新计划

在 **"刷新设置** "屏幕上，可以设置增量爬网间隔和完全爬网间隔。 Azure Data Lake Storage Gen2 连接器的默认间隔为增量爬网 15 分钟，完全爬网间隔为一周。

## <a name="limitations"></a>限制

无法为 Azure Data Lake Storage Gen2 源重新配置 Azure Blob 存储的已发布连接，反之亦然。 在这种情况下，建议配置新连接。
