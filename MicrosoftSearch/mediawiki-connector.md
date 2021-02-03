---
title: Microsoft 搜索的 MediaWiki Graph 连接器
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
description: 为 Microsoft 搜索设置 MediaWiki Graph 连接器
ms.openlocfilehash: 9d9d7a1ef9aeaba079f8cccef1ec4a4836768e8d
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084980"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>MediaWiki Graph 连接器

通过 MediaWiki Graph 连接器，组织可以发现使用 MediaWiki 软件创建的 Wiki 数据，并编制数据索引。 此连接器将指定内容索引到 Microsoft 搜索中，并支持定期爬网，使索引保持最新。

> [!NOTE]
> 阅读 [**Graph 连接器的安装程序**](configure-connector.md) 文章，了解一般的 Graph 连接器设置过程。

本文适用于配置、运行和监视 ServiceNow Graph 连接器的任何人。 它补充了常规安装过程，并显示了仅适用于 MediaWiki Graph 连接器的说明。 本文还包括有关 [限制的信息](#limitations)。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

输入 **Wiki URL，** 然后从选项的下拉菜单中选择身份验证类型。 选项为 **None、Basic** 和 **OAuth 2.0 AAD。** 

如果选择"**基本**"作为身份验证类型，则需要提供 **Wiki** **的用户名和密码。**

如果选择 **OAuth 2.0 AAD** 作为身份验证类型，则需要提供 Wiki **安装的资源** ID。 你还需要提供在 AAD 应用程序注册 **页上生成的客户端** **ID** 和客户端密码。

## <a name="step-4-manage-search-permissions"></a>步骤 4：管理搜索权限

MediaWiki 连接器仅支持对所有人可见的搜索 **权限**。 索引数据将显示在搜索结果中，并且对组织所有用户可见。

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
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>限制

MediaWiki 连接器在预览版本中有以下限制：

* 仅支持基于云的 Wiki。
* 仅支持使用 Azure Active Directory 或 Azure 身份验证的基本或 OAuth 2.0。
* 不支持为索引选择命名空间。 仅索引主命名空间、类别命名空间和文件命名空间。
* 不支持访问控制列表 (ACL) 。 因此，索引页对组织中所有用户都是可见的。
