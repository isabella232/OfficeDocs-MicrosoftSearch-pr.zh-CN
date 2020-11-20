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
description: 设置 Azure Data Lake Storage Gen2 connector for Microsoft Search
ms.openlocfilehash: 860c923c62495c7df20152fb530797e390949305
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367583"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Azure Data Lake Storage Gen2 connector

使用 Azure Data Lake Storage Gen2 连接器，组织中的用户可以搜索存储在 [Azure Blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) 和 [Azure Data Lake Gen 2 存储](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) 帐户中的文件。

本文适用于 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理员或任何配置、运行和监控 Azure Data Lake Storage Gen2 连接器的人。 它概述了连接器配置、功能、限制和故障排除技术。 在本文中，我们使用 *Azure 存储* 作为 [Azure Blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) 和 [Azure Data Lake Gen 2 存储](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)的通用术语。

## <a name="connect-to-a-data-source"></a>连接到数据源

### <a name="primary-storage-connection-string"></a>主存储连接字符串

在 " **身份验证和配置** " 屏幕上，提供主存储连接字符串。 该字符串是允许访问您的存储帐户所必需的。 若要查找您的连接字符串，请转到 [Azure 门户](https://ms.portal.azure.com/#home) ，并导航到相关 Azure 存储帐户的 " **密钥** " 部分。 将连接字符串复制并粘贴到屏幕上的相应字段中。

如果您不想提供 **AccountKey** (主存储连接字符串中的参数) ，您需要为以下角色授予对我们的 Graph 连接器服务的访问权限。

* 存储 Blob 数据读取器
* 存储队列数据参与者
* 存储 Blob 代理者仅对分层存储)  (

导航到 Azure 存储帐户的 " **访问控制** " 选项卡，然后按照中的说明授予对以下应用程序的访问权限：

* **第一方应用程序 ID：** 56c1da01-2129-48f7-9355-af6d59d42766
* **第一方应用程序名称：** Graph 连接器服务

### <a name="storage-account-and-queue-notifications-optional"></a>存储帐户和队列通知 (可选) 

在将来可能会添加在图形连接器服务中实时处理更改的支持。 在这种情况下，我们将监视存储在队列中的 Azure 存储更改通知。 你将需要使用与你的 Azure 存储帐户相同的帐户创建队列。

创建队列后，转到 "队列" 页上的 " **事件** " 选项卡以配置 **事件订阅**。 选择队列将接收的所有 Blob 事件，并将队列连接到 Azure 存储帐户。

## <a name="manage-search-permissions"></a>管理搜索权限

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

在 " **管理搜索权限** " 屏幕上，您可以选择从您的 [Azure Data Lake Gen 2 存储](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) 帐户中接收 (Acl) 的访问控制列表。 设置这些搜索权限时，将根据分配给已登录的 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) 用户搜索内容的权限对搜索内容进行修整。 或者，您可以选择将从存储帐户编制索引的所有内容对组织中的所有人可见。 在这种情况下，组织中的每个人都将有权访问存储帐户中的所有数据。

### <a name="azure-blob-storage"></a>Azure Blob 存储

对于与 [Azure Blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)的连接，组织中的所有人都可以看到从已配置的源编制索引的所有内容。 Azure Blob 存储中的 Blob 级别不支持访问控制列表。

## <a name="manage-search-permissions"></a>管理搜索权限

Azure Data Lake Storage Gen2 连接器支持对 **所有人** 可见的搜索权限，或仅支持对 **此数据源具有访问权限的用户**。 搜索结果中显示的索引数据可能对组织中的所有用户可见，或者仅对对每个项目具有访问权限的用户可见。

## <a name="assign-property-labels"></a>分配属性标签

通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。 虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。

## <a name="manage-schema"></a>管理架构

在 " **管理架构** " 屏幕上，您可以选择更改架构属性， (可 **查询**、可 **搜索**、 **检索** 和 **可精简**) 与属性相关联，添加可选别名，然后选择 **Content** 属性。

## <a name="set-the-refresh-schedule"></a>设置刷新计划

在 " **刷新设置** " 屏幕上，您可以设置增量爬网间隔和完全爬网间隔。 对于增量爬网，默认情况下，Azure Data Lake Storage Gen2 连接器的默认间隔为15分钟，对于完全爬网，则为一周。

## <a name="limitations"></a>限制

无法为 Azure Data Lake Storage Gen2 源重新配置已发布的 Azure Blob 存储连接，反之亦然。 在这种情况下，建议配置新连接。
