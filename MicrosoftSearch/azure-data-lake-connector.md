---
title: Azure Data Lake Graph 连接器Microsoft 搜索
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置 Azure Data Lake 存储 Gen2 Graph连接器Microsoft 搜索
ms.openlocfilehash: f60de4252e514f84bc92daf4ea65c535cf40a13d
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701396"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Azure Data Lake 存储 Gen2 Graph连接器

Azure Data Lake 存储 Gen2 Graph 连接器允许贵组织的用户搜索[存储在 Azure Blob 存储](/azure/storage/blobs/storage-blobs-introduction)和 Azure Data Lake Gen [2](/azure/storage/blobs/data-lake-storage-introduction)存储帐户的文件。

> [!NOTE]
> 阅读 [**Setup your Graph connector**](configure-connector.md)一文，了解 Graph连接器的一般设置说明。

本文适用于配置、运行和监视 Azure Data Lake 存储 Gen2 连接器的任何人。 它补充了常规设置过程，并显示了仅适用于 Azure Data Lake 存储 Gen2 连接器的说明。 本文还包括有关 [限制的信息](#limitations)。

在文章中，我们将 Azure 存储用作[Azure Blob](/azure/storage/blobs/storage-blobs-introduction)存储 和[Azure Data Lake Gen 2](/azure/storage/blobs/data-lake-storage-introduction)项目的通用存储。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在Graph连接器中添加Microsoft 365 管理中心

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

输入主存储连接字符串。 需要此字符串才能访问存储帐户。 若要查找连接字符串，请转到[Azure](https://ms.portal.azure.com/#home)门户并导航到相关帐户的密钥Azure 存储部分。

如果您不希望在主存储连接字符串 (中提供 **AccountKey**) ，请授予以下角色对 Graph 连接器服务的访问权限：

* 存储Blob 数据读取器
* 存储队列数据参与者
* 存储Blob Delegator

导航到帐户 **的**"访问控制"Azure 存储，然后按照其中的说明授予对以下应用的访问权限：

* **第一方应用** ID：56c1da01-2129-48f7-9355-af6d59d42766
* **第一方应用名称：Graph** 连接器服务

### <a name="storage-account-and-queue-notifications-optional"></a>存储帐户和队列通知 (可选) 

将来可能会添加对在 Graph 连接器服务中实时处理更改的支持。 在这种情况下，我们将监视Azure 存储中存储的变更通知。 你需要使用与帐户帐户相同的帐户创建Azure 存储队列。

创建队列后，请转到队列页面上的" **事件** "选项卡以配置 **事件订阅**。 选择队列将接收的所有 Blob 事件，将队列连接到Azure 存储帐户。

## <a name="step-4-assign-property-labels"></a>步骤 4：分配属性标签

可以通过从选项菜单中选择来为每个标签分配源属性。 虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更好的搜索结果。

## <a name="step-5-manage-schema"></a>步骤 5：管理架构

在 **"管理架构**"屏幕上，可以更改与属性关联的架构属性，选项为"查询"、"**搜索**"、"**检索**"和"**优化"。** 还可以添加可选别名，然后选择 **Content** 属性。

## <a name="step-6-manage-search-permissions"></a>步骤 6：管理搜索权限

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

你可以选择从[Azure Data Lake Gen 2](/azure/storage/blobs/data-lake-storage-introduction) (帐户) 访问控制列表存储 ACL。 设置这些搜索权限后，将基于登录用户的权限对搜索内容进行[Azure Active Directory。](/azure/active-directory/) 或者，可以选择使存储帐户中编制索引的所有内容对组织中的每个人可见。 在这种情况下，组织中的每个人都可以访问存储帐户中的所有数据。

Azure Data Lake 存储 Gen2 Graph 连接器支持对"任何人"或"仅有权访问此数据源的人"可见的 **搜索权限**。 对于组织中有权访问每个项目的用户，搜索结果中出现的已编制索引的数据可能可见。

### <a name="azure-blob-storage"></a>Azure Blob 存储

对于与[Azure Blob 存储](/azure/storage/blobs/storage-blobs-introduction)的连接，从配置源索引的所有内容对组织中的每个人都可见。 Azure Blob 服务不支持 Blob 级别的访问控制存储。

## <a name="step-7-set-the-refresh-schedule"></a>步骤 7：设置刷新计划

在"**刷新设置"** 屏幕上，可以设置增量爬网间隔和完全爬网间隔。 Azure Data Lake 存储 Gen2 连接器的默认时间间隔为增量爬网 15 分钟，完全爬网间隔为一周。

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>限制

无法为 Azure Data Lake 存储 Gen2 源存储另一种方法重新配置 Azure Blob 数据库的已发布连接。 在这种情况下，建议配置新连接。

此外，文件的大小需要小于或小于 4 MB，以用于爬网。 当前支持的文件类型包括：

* Word (docx、.docm、.dotx、.dotm) 
* PowerPoint (.pptm、.pptx、.potm、.potx、.ppam、.ppsm、.ppsx) 
* Excel (.xlsx、.xlsm) 
* 旧版Office格式 (.doc.dot 等) 
* 文本 (.txt) 
* HTML
* PDF

不支持二进制文件 (.jpg、.bmp等) 二进制文件。 例如，如果.docx文件仅包含图像，可能会跳过该文件，因为它未返回任何内容。