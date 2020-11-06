---
title: 用于 Microsoft 搜索的 ServiceNow 连接器
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置用于 Microsoft 搜索的 ServiceNow 连接器
ms.openlocfilehash: b60583e61687b13c7fd631cd1c4a9f6d663724e8
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927195"
---
# <a name="servicenow-connector"></a>ServiceNow 连接器

使用 ServiceNow 连接器，组织可以对组织中的所有用户可见的知识库文章编制索引。 在从 ServiceNow 配置连接器和索引内容之后，最终用户可以从任何 Microsoft Search client 中搜索这些文章。  

本文适用于 Microsoft 365 管理员或任何配置、运行和监视 ServiceNow 连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。

了解如何在 microsoft Search 中设置 microsoft [构建的连接器以](https://docs.microsoft.com/microsoftsearch/configure-connector)访问 microsoft 构建的连接器。 有关特定于 ServiceNow 连接器的特定配置，请见下面一文。

## <a name="connection-settings"></a>连接设置
若要连接到你的 ServiceNow 数据，你需要组织的 **servicenow 实例 URL** 、此帐户的凭据以及用于 OAuth 身份验证的客户端 ID 和客户端密码。  

您的组织的 **ServiceNow 实例 URL** 的外观通常如下所示 **https:// &lt; 您的组织域> service-now.com** 。 除了此 URL，您还需要一个帐户，用于设置与 ServiceNow 的连接，以及允许 Microsoft Search 根据刷新计划定期更新 ServiceNow 中的文章。 帐户应具有 <em>知识</em> 角色。 [了解如何为 ServiceNow 帐户分配角色](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。

若要从 ServiceNow 验证和同步内容，请选择 **以下三** 种受支持的方法之一：
1. 基本身份验证 
2.  (建议的 ServiceNow OAuth) 
3. Azure AD OpenID Connect

#### <a name="basic-authentication"></a>基本身份验证
输入具有 <em>知识</em> 角色的 ServiceNow 帐户的用户名和密码，以向你的实例进行身份验证。
#### <a name="servicenow-oauth"></a>ServiceNow OAuth

若要使用 ServiceNow OAuth 进行身份验证，ServiceNow 管理员需要在你的 ServiceNow 实例中预配终结点，以便 Microsoft Search 应用可以访问该实例。 若要了解详细信息，请参阅在 ServiceNow 文档中 [创建客户端以访问实例的终结点](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) 。

下表提供了有关如何填写终结点创建表单的指导：

**Field** | **说明** | **推荐值**
--- | --- | ---
名称 | 此唯一值标识您需要 OAuth 访问的应用程序。 | Microsoft 搜索
客户端 ID | 应用程序的只读、自动生成的唯一 ID。 实例在请求访问令牌时使用客户端 ID。 | 不适用
客户端密码 | 使用此共享机密字符串，ServiceNow 实例和 Microsoft Search 授权相互之间的通信。 | 将此视为密码，以遵循安全性最佳实践。
重定向 URL | 授权服务器重定向到的必需回调 URL。 | https://gcs.office.com/v1.0/admin/oauth/callback
徽标 URL | 包含应用程序徽标的图像的 URL。 | 不适用
活动 | 选中此复选框可使应用程序注册表处于活动状态。 | 设置为活动
刷新令牌生命期 | 刷新令牌有效的秒数。 默认情况下，刷新令牌在100天内过期 (8640000 秒) 。 | 31536000 (1 年) 
访问令牌生命周期 | 访问令牌有效的秒数。 | 43200 (12 小时) 

输入客户端 id 和客户端密码以连接到你的实例。 连接后，使用 ServiceNow 帐户凭据对要进行爬网的权限进行身份验证。 帐户应具有 <em>知识</em> 角色。 

#### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

若要使用 Azure AD OpenID Connect 进行身份验证，请执行以下步骤。

###### <a name="step-1-register-a-new-application-in-azure-active-directory"></a>步骤1：在 Azure Active Directory 中注册新应用程序

若要了解如何在 Azure Active Directory 中注册新应用程序，请参阅 [注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application)。 选择 "单个租户组织目录"。 不需要重定向 URI。 注册后，记下应用程序 (客户端) ID 和目录 (租户) ID。

###### <a name="step-2-create-a-client-secret"></a>步骤2：创建客户端密码

若要了解如何创建客户端密码，请参阅 [创建客户端密码](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。 记录客户端密码。

###### <a name="step-3-retrieve-service-principal-object-identifier"></a>步骤3：检索服务主体对象标识符

按照步骤检索服务主体对象标识符

1. 运行 PowerShell
2. 使用以下命令安装 Azure PowerShell
```<language>
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
```
3. 连接到 Azure
```<language>
    Connect-AzAccount
```
4. 获取服务主体对象标识符
```<language>
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
```
将 "应用程序 ID" 替换为应用程序 (客户端) ID (没有引号) 在步骤1中注册的应用程序。 请注意 PowerShell 输出中 ID 对象的值。 它是服务主体 ID。

现在，你已拥有 Azure 门户所需的所有信息。 下面的表中给出了信息的快速摘要。

**属性** | **说明**
--- | ---
 (租户 ID) 的目录 ID | 这是从步骤 1) 中引用 Azure Active Directory 租户 (的唯一 ID。
 (客户端 ID) 的应用程序 ID | 这是引用在步骤1中注册的应用程序的唯一 ID。
客户端密码 | 这是第2步) 中的应用程序 (的机密密钥。 像密码一样对待它。
服务主体 ID | 作为服务运行的应用程序的标识。 步骤3中的 () 

###### <a name="step-4-register-servicenow-application"></a>步骤4：注册 ServiceNow 应用程序

需要在 ServiceNow 实例中执行以下配置。

1. 注册新的 OAuth OIDC 实体。 若要了解详情，请参阅 [Create a OAUTH OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)。
2. 下表提供了有关如何填写 OIDC 提供程序注册表单的指南

**Field** | **说明** | **推荐值**
--- | --- | ---
名称 | 标识 OAuth OIDC 实体的唯一名称。 | Azure AD
客户端 ID | 在第三方 OAuth OIDC 服务器中注册的应用程序的客户端 ID。 请求访问令牌时，实例使用客户端 ID。 | 第1步中的应用程序 (客户端) ID
客户端密码 | 在第三方 OAuth OIDC 服务器中注册的应用程序的客户端密码。 | 步骤2中的客户端密码

所有其他值都可以是默认值。

3. 在 OIDC 提供程序注册表单中，需要添加新的 OIDC 提供程序配置。 单击 "针对 *OAUTH OIDC Provider 配置* " 字段的 "搜索" 图标，打开 OIDC 配置的记录。 单击"新建"。
4. 下表提供了有关如何填写 OIDC 提供程序配置表单的指南

**Field** | **推荐值**
--- | ---
OIDC 提供程序 |  Azure AD
OIDC 元数据 URL | 此格式必须采用 https \: //login.microsoftonline.com/"tenandId"/.well-known/openid-configuration <br/>将 "tenantID" 从步骤 1 (中的目录 (租户) ID 替换为) 不带引号的 ID。
OIDC 配置缓存寿命范围 |  120
应用程序 | 全球
用户声明 | sub
用户字段 | 用户 ID
启用 JTI 声明验证 | 禁用

5. 单击 "提交" 并更新 "OAuth OIDC 实体" 表单。

###### <a name="step-5-create-a-servicenow-account"></a>步骤5：创建 ServiceNow 帐户

请参阅说明创建 ServiceNow 帐户， [在 ServiceNow 中创建一个用户](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。

下表提供了有关如何填写 ServiceNow 用户帐户注册的指南。

**Field** | **推荐值**
--- | ---
用户 ID | 步骤3中的服务主体 ID
仅 Web 服务访问 | Checked

所有其他值都可以保留为默认值。

###### <a name="step-6-enable-knowledge-role-for-the-servicenow-account"></a>步骤6：为 ServiceNow 帐户启用知识角色

访问使用 ServiceNow 主体 ID 创建的 ServiceNow 帐户作为用户 ID，并分配知识角色。 可在此处找到向 ServiceNow 帐户分配角色的说明，可在此处 [为用户分配角色](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。

使用 "应用程序 ID" 作为 "客户端 (ID) " 中的 "应用程序 ID" 和 "客户端密钥" (从步骤 2) 在管理中心配置向导中使用 Azure AD OpenID Connect 向你的 ServiceNow 实例进行身份验证。

## <a name="filter-data"></a>筛选数据 
使用 ServiceNow 查询字符串，可以指定用于同步文章的条件。 它类似于 **SQL Select** 语句中的 **Where** 子句。 例如，您可以选择仅对已发布和活动的文章编制索引。 若要了解如何创建自己的查询字符串，请参阅 [使用筛选器生成已编码的查询字符串](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。

## <a name="manage-search-permissions"></a>管理搜索权限
ServiceNow 连接器仅支持 **所有人都** 能看到的搜索权限。 索引数据显示在搜索结果中，并对组织中的所有用户可见。

## <a name="manage-the-search-schema"></a>管理搜索架构
成功连接后，配置搜索架构映射。 您可以选择哪些属性可供 **查询** 、 **搜索** 和 **检索** 。 若要了解有关管理搜索架构的详细信息，请参阅 [管理搜索架构](https://docs.microsoft.com/microsoftsearch/configure-connector#manage-the-search-schema)。

## <a name="set-the-refresh-schedule"></a>设置刷新计划
ServiceNow 连接器支持完全爬网和增量爬网的刷新计划。 我们建议您同时设置这两个。

完全爬网计划可查找以前同步到 Microsoft 搜索索引的已删除文章以及从同步筛选器中移出的所有文章。 首次连接到 ServiceNow 时，将运行完全爬网以同步所有知识库文章。 若要同步新项目并进行更新，需要安排增量爬网。

对于完全爬网，建议默认值为一天，对于增量爬网，建议默认值为4小时。

## <a name="review-and-publish"></a>查看和发布
配置连接器后，可以查看并发布连接。

## <a name="next-steps"></a>后续步骤
发布连接后，需要自定义搜索结果页面。 若要了解有关自定义搜索结果的信息，请参阅 [自定义搜索结果页](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)。