---
title: Microsoft 搜索的 MediaWiki 连接器
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置用于 Microsoft 搜索的 MediaWiki 连接器
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367637"
---
# <a name="mediawiki-connector"></a>MediaWiki 连接器

通过 MediaWiki 连接器，贵组织可以发现使用 MediaWiki 软件创建的 wiki 中的数据并对其编制索引。 此连接器将指定的内容索引到 Microsoft Search，并支持定期爬网以保持索引为最新。

本文适用于 Microsoft 365 管理员或任何配置、运行和监控 MediaWiki 连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。

## <a name="connect-to-a-data-source"></a>连接到数据源

输入您的 MediaWiki URL 和凭据以对连接进行身份验证。 你将需要以下信息： **租户 ID**、 **资源 ID**、 **客户端 ID** 和 **客户端密码**。

## <a name="manage-search-permissions"></a>管理搜索权限

MediaWiki 连接器仅支持 **所有人都** 能看到的搜索权限。 索引数据显示在搜索结果中，并对组织中的所有用户可见。

## <a name="assign-property-labels"></a>分配属性标签

通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。 虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。

## <a name="manage-schema"></a>管理架构

在 " **管理架构** " 屏幕上，您可以选择更改架构属性， (可 **查询**、可 **搜索**、 **检索** 和 **可精简**) 与属性相关联，添加可选别名，然后选择 **Content** 属性。

## <a name="set-the-refresh-schedule"></a>设置刷新计划

此计划将刷新已编制索引的数据，因此 wiki 的更改将反映在 Microsoft Search 中。 在指定的刷新间隔后，所有新页面、删除的页面、页面内容或元数据更改都会显示在搜索结果中。 爬网时间取决于 wiki 的大小。 目前，连接器会在每分钟50页面的周围进行爬网。

## <a name="limitations"></a>限制

在预览版本中，MediaWiki 连接器具有以下限制：

* 仅支持基于云的 wiki。
* 仅支持基本或 OAuth 2.0 与 Azure Active Directory 或 Azure 身份验证。
* 不支持用于索引的命名空间选择。 仅索引 **主**、 **类别** 和 **文件** 命名空间。
* 不支持 (Acl) 的访问控制列表。 因此，索引页对组织中的所有用户都是可见的。
