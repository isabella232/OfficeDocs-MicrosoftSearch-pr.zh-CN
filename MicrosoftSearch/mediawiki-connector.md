---
title: Microsoft 搜索的 MediaWiki 连接器
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置用于 Microsoft 搜索的 MediaWiki 连接器
ms.openlocfilehash: 281d270a47051e20cb1cfd44540bd51371557c13
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949641"
---
# <a name="mediawiki-connector"></a>MediaWiki 连接器

通过 MediaWiki 连接器，贵组织可以发现使用 MediaWiki 软件创建的 wiki 中的数据并对其编制索引。 此连接器将指定的内容索引到 Microsoft Search，并支持定期爬网以保持索引为最新。

本文适用于 Microsoft 365 管理员或任何配置、运行和监控 MediaWiki 连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。

## <a name="connect-to-a-data-source"></a>连接到数据源
输入您的 MediaWiki URL 和凭据以对连接进行身份验证。 你将需要以下信息：**租户 ID**、**资源 ID**、**客户端 ID**和**客户端密码**。

## <a name="manage-the-search-schema"></a>管理搜索架构
成功连接后，配置搜索架构映射。 您可以选择哪些属性可供**查询**、**搜索**和**检索**。

## <a name="manage-search-permissions"></a>管理搜索权限
MediaWiki 连接器仅支持**所有人都**能看到的搜索权限。 索引数据显示在搜索结果中，并对组织中的所有用户可见。

## <a name="set-the-refresh-schedule"></a>设置刷新计划 
此计划将刷新已编制索引的数据，因此 wiki 的更改将反映在 Microsoft Search 中。 在指定的刷新间隔后，所有新页面、删除的页面、页面内容或元数据更改都会显示在搜索结果中。 爬网时间取决于 wiki 的大小。 目前，连接器会在每分钟50页面的周围进行爬网。

## <a name="limitations"></a>限制 
在预览版本中，MediaWiki 连接器具有以下限制：
* 仅支持基于云的 wiki。
* 仅支持基本或 OAuth 2.0 与 Azure Active Directory 或 Azure 身份验证。
* 不支持用于索引的命名空间选择。 仅索引**主**、**类别**和**文件**命名空间。
* 不支持访问控制列表（Acl）。 因此，索引页对组织中的所有用户都是可见的。
