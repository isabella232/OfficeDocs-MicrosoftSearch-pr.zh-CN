---
title: 用于 Microsoft 搜索的 ServiceNow 连接器
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置用于 Microsoft 搜索的 ServiceNow 连接器
ms.openlocfilehash: 78b2831e9a52b6bf0204b5a6b2aba147b529b3f5
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626951"
---
# <a name="servicenow-connector"></a>ServiceNow 连接器

使用 ServiceNow 连接器，组织可以对组织中的所有用户可见的知识库文章编制索引。 在从 ServiceNow 配置连接器和索引内容之后，最终用户可以从任何 Microsoft Search client 中搜索这些文章。  

本文适用于 Microsoft 365 管理员或任何配置、运行和监视 ServiceNow 连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。

## <a name="connect-to-a-data-source"></a>连接到数据源
若要连接到你的 ServiceNow 数据，你需要组织的**servicenow 实例 URL**、此帐户的凭据以及用于 OAuth 身份验证的客户端 ID 和客户端密码。  

您的组织的**ServiceNow 实例 URL**的外观通常如下所示**&lt;https://您的组织域> service-now.com**。 除了此 URL，您还需要一个帐户，用于设置与 ServiceNow 的连接，以及允许 Microsoft Search 根据刷新计划定期更新 ServiceNow 中的文章。

若要从 ServiceNow 对内容进行身份验证和同步，请选择以下两个受支持的方法之一： 
1. 基本身份验证 
2. OAuth （推荐）

> [!Note]
> 若要使用 OAuth 进行身份验证，ServiceNow 管理员需要在你的 ServiceNow 实例中预配终结点，以便 Microsoft Search 应用可以访问该实例。 若要了解详细信息，请参阅在 ServiceNow 文档中[创建客户端以访问实例的终结点](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html)。

下表提供了有关如何填写终结点创建表单的指导：

**Field** | **说明** | **推荐值**
--- | --- | ---
名称 | 此唯一值标识您需要 OAuth 访问的应用程序。 | Microsoft 搜索
客户端 ID | 应用程序的只读、自动生成的唯一 ID。 实例在请求访问令牌时使用客户端 ID。 | NA
客户端密码 | 使用此共享机密字符串，ServiceNow 实例和 Microsoft Search 授权相互之间的通信。 | 将此视为密码，以遵循安全性最佳实践。
重定向 URL | 授权服务器重定向到的必需回调 URL。 | 请参阅[OAuth 回调](https://gcs.office.com/v1.0/admin/oauth/callback)。
徽标 URL | 包含应用程序徽标的图像的 URL。 | NA
活动 | 选中此复选框可使应用程序注册表处于活动状态。 | 设置为活动
刷新令牌生命期 | 刷新令牌有效的秒数。 默认情况下，刷新令牌在100天后过期（8640000秒）。 | 31536000（1年）
访问令牌生命周期 | 访问令牌有效的秒数。 | 43200（12个小时）

## <a name="set-a-sync-filter"></a>设置同步筛选器 
使用同步筛选器，可以指定用于同步文章的条件。 它类似于**SQL Select**语句中的**Where**子句。 例如，您可以选择仅对已发布和活动的文章编制索引。 SyncNow 配置页介绍如何捕获和设置同步筛选器。

## <a name="manage-the-search-schema"></a>管理搜索架构
成功连接后，配置搜索架构映射。 您可以选择哪些属性可供**查询**、**搜索**和**检索**。

## <a name="manage-search-permissions"></a>管理搜索权限
ServiceNow 连接器仅支持**所有人都**能看到的搜索权限。 索引数据显示在搜索结果中，并对组织中的所有用户可见。
 
## <a name="set-the-refresh-schedule"></a>设置刷新计划 
ServiceNow 连接器支持完全爬网和增量爬网的刷新计划。 我们建议您同时设置这两个。

完全爬网计划可查找以前同步到 Microsoft 搜索索引的已删除文章以及从同步筛选器中移出的所有文章。 首次连接到 ServiceNow 时，将运行完全爬网以同步所有知识库文章。 若要同步新项目并进行更新，需要安排增量爬网。

对于完全爬网，建议默认值为一天，对于增量爬网，建议默认值为4小时。
