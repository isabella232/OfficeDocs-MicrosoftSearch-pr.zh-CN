---
title: MediaWiki Graph连接器Microsoft 搜索
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
description: 为媒体连接器Graph MediaWiki Microsoft 搜索
ms.openlocfilehash: 7e1c308eb1785dd7fec23fac7e9002957a0d50ca
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973426"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>MediaWiki Graph连接器

通过 MediaWiki Graph连接器，组织可以发现使用 MediaWiki 软件创建的 Wiki 数据，并编制数据索引。 此连接器将指定内容索引Microsoft 搜索并支持定期爬网，使索引保持最新。

> [!NOTE]
> 阅读 [**Graph 连接器的**](configure-connector.md)安装程序一文，了解 Graph 连接器的一般设置说明。

本文适用于配置、运行和监视 MediaWiki Graph连接器。 它补充了常规设置过程，并显示了仅适用于 MediaWiki 连接器Graph说明。 本文还包括有关 [限制的信息](#limitations)。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在Graph连接器中添加Microsoft 365 管理中心

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

输入 Wiki **URL，** 然后 **从选项的** 下拉菜单中选择"身份验证"类型。 选项为 **None、Basic** 和 **OAuth 2.0 AAD。** 

如果选择"**基本**"作为"身份验证"类型，则需要提供 Wiki **的用户名和密码**。

如果选择 **OAuth 2.0 AAD** 作为身份验证类型，则需要提供 Wiki 安装的资源 **ID。** 你还需要提供在 AAD 应用程序注册页上生成的客户端 **ID** 和客户端密码。

## <a name="step-4-manage-search-permissions"></a>步骤 4：管理搜索权限

MediaWiki 连接器仅支持对所有人可见的搜索 **权限**。 索引数据将显示在搜索结果中，并且对组织中所有用户可见。

## <a name="step-5-assign-property-labels"></a>步骤 5：分配属性标签

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>步骤 6：管理架构

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>步骤 7：选择刷新设置

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>限制

MediaWiki 连接器在预览版本中有以下限制：

* 仅支持基于云的 Wiki。
* 仅支持基本或 OAuth 2.0 Azure Active Directory Azure 身份验证。
* 不支持为索引选择命名空间。 仅索引 Main、Category 和 File 命名空间。
* 不支持访问控制列表 (ACL) 。 因此，索引页对组织所有用户都是可见的。