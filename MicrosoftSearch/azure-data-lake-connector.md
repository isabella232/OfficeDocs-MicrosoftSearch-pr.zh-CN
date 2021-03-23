---
title: 用于 Microsoft 搜索的 Azure Data Lake Graph 连接器
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 为 Microsoft 搜索设置 Azure Data Lake Storage Gen2 Graph 连接器
ms.openlocfilehash: 37a035b3de9dc217f885f193992d1e74a675fb35
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031320"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Azure Data Lake Storage Gen2 Graph 连接器

Azure Data Lake Storage Gen2 Graph 连接器允许贵组织的用户搜索存储在 [Azure Blob](/azure/storage/blobs/storage-blobs-introduction) 存储和 [Azure Data Lake Gen 2 存储帐户中](/azure/storage/blobs/data-lake-storage-introduction) 的文件。

> [!NOTE]
> 阅读 [**设置 Graph 连接器一**](configure-connector.md) 文，了解 Graph 连接器的常规设置说明。

本文适用于配置、运行和监视 Azure Data Lake Storage Gen2 连接器的任何人。 它补充了常规设置过程，并显示了仅适用于 Azure Data Lake Storage Gen2 连接器的说明。 本文还包括有关 [限制的信息](#limitations)。

在文章中，我们将 *Azure 存储* 用作 Azure Blob 存储和 [Azure](/azure/storage/blobs/storage-blobs-introduction) [Data Lake Gen 2](/azure/storage/blobs/data-lake-storage-introduction)Storage 的通用术语。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在 Microsoft 365 管理中心添加 Graph 连接器

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

输入主存储连接字符串。 需要此字符串才能访问存储帐户。 若要查找连接字符串，请转到 [Azure](https://ms.portal.azure.com/#home) 门户并导航到相关 Azure 存储帐户的 **密钥** 部分。

如果不希望在主存储连接 (字符串中提供 **AccountKey**) ，请授予以下角色对 Graph 连接器服务的访问权限：

* 存储 Blob 数据读取器
* 存储队列数据参与者
* 存储 Blob Delegator

导航到 Azure **存储帐户** 的"访问控制"选项卡，并按照其中的说明授予对以下应用的访问权限：

* **第一方应用** ID：56c1da01-2129-48f7-9355-af6d59d42766
* **第一方应用名称：** Graph 连接器服务

### <a name="storage-account-and-queue-notifications-optional"></a>存储帐户和队列通知 (可选) 

将来可能会添加对在 Graph 连接器服务中实时处理更改的支持。 在这种情况下，我们将监视队列中存储的 Azure 存储更改通知。 你需要使用与 Azure 存储帐户相同的帐户创建队列。

创建队列后，请转到队列页面上的" **事件** "选项卡以配置 **事件订阅**。 选择队列将接收的所有 Blob 事件，将队列连接到 Azure 存储帐户。

## <a name="step-4-assign-property-labels"></a>步骤 4：分配属性标签

可以通过从选项菜单中选择来为每个标签分配源属性。 虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更好的搜索结果。

## <a name="step-5-manage-schema"></a>步骤 5：管理架构

在"**管理架构**"屏幕上，可以更改与属性关联的架构属性，选项为"**查询****"、"搜索****"、"检索**"和"**优化"。** 还可以添加可选别名，然后选择 **Content** 属性。

## <a name="step-6-manage-search-permissions"></a>步骤 6：管理搜索权限

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

你可以选择从 Azure Data Lake Gen [2](/azure/storage/blobs/data-lake-storage-introduction) 存储帐户 (访问控制列表) ACL。 设置这些搜索权限后，将基于登录 [Azure Active Directory](/azure/active-directory/)的用户的权限来修整搜索内容。 或者，可以选择使存储帐户中编制索引的所有内容对组织中的每个人可见。 在这种情况下，组织中的每个人都可以访问存储帐户中的所有数据。

Azure Data Lake Storage Gen2 Graph 连接器支持对"任何人"或"仅有权访问此数据源的人"**可见的搜索权限**。 对于组织中有权访问每个项目的用户，搜索结果中出现的已编制索引的数据可能可见。

### <a name="azure-blob-storage"></a>Azure Blob 存储

对于与 [Azure Blob 存储](/azure/storage/blobs/storage-blobs-introduction)的连接，从配置源索引的所有内容对组织中的每个人都可见。 Azure Blob 存储中的 Blob 级别不支持访问控制列表。

## <a name="step-7-set-the-refresh-schedule"></a>步骤 7：设置刷新计划

在" **刷新设置** "屏幕上，可以设置增量爬网间隔和完全爬网间隔。 Azure Data Lake Storage Gen2 连接器的默认时间间隔为增量爬网 15 分钟，完全爬网间隔为一周。

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>限制

无法针对 Azure Data Lake Storage Gen2 源和另一种方法重新配置 Azure Blob 存储的已发布连接。 在这种情况下，建议配置新连接。

此外，文件的大小需要小于或小于 4 MB，以用于爬网。 当前支持的文件类型包括：

* Word (docx、.docm、.dotx、.dotm) 
* PowerPoint (.pptm、.pptx、.potm、.potx、.ppam、.ppsm、.ppsx) 
* Excel (.xlsx，.xlsm) 
* 旧版 Office 格式 (.doc、.dot 等) 
* Text (.txt) 
* HTML
* PDF

不支持二进制文件 (.jpg、.bmp 等) 二进制文件。 例如，如果 .docx 文件仅包含图像，可能会跳过该文件，因为它未返回任何内容。