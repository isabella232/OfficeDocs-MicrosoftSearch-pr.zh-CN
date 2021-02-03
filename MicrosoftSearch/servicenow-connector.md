---
title: 用于 Microsoft 搜索的 ServiceNow Graph 连接器
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
description: 为 Microsoft 搜索设置 ServiceNow Graph 连接器
ms.openlocfilehash: d1fdfb5f1aec5091fd526152de2bdc86932cfdb9
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084890"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph 连接器

ServiceNow Graph 连接器允许组织根据组织内的用户条件权限为用户可见的基于知识的文章编制索引。 从 ServiceNow 配置连接器和索引内容后，用户可以从任何 Microsoft 搜索客户端搜索文章。

> [!NOTE]
> 阅读 [**Graph 连接器的安装程序**](configure-connector.md) 文章，了解一般的 Graph 连接器设置过程。

本文适用于配置、运行和监视 ServiceNow Graph 连接器的任何人。 它补充了常规安装过程，并显示了仅适用于 ServiceNow Graph 连接器的说明。 本文还包括有关疑难[解答和](#troubleshooting)[限制的信息](#limitations)。
  
## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>步骤 3：连接设置

若要连接到 ServiceNow 数据，请使用组织的 **ServiceNow** 实例 URL 凭据、此帐户的客户端 ID 和客户端密码进行 OAuth 身份验证。  

组织的 **ServiceNow** 实例 URL 通常https://组织域 **&lt;>.service-now.com。** 除了此 URL 外，还需要一个帐户来设置与 ServiceNow 的连接，并允许 Microsoft 搜索根据刷新计划从 ServiceNow 更新文章。 该帐户至少应具有 <em>知识</em> 角色。 [了解如何为 ServiceNow 帐户分配角色](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。

>[!NOTE]
>如果要对用户和组标识进行爬网以遵循 Microsoft 搜索结果中知识文章的访问权限，则帐户应有权读取 ServiceNow 中的下表记录：
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> 你可以为用于与 Microsoft 搜索连接的帐户创建和分配角色。 可以在该角色上分配对表的读取权限。 若要了解如何设置对表记录的读取访问权限，请参阅["保护表记录"。](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)

若要对 ServiceNow 中的内容进行身份验证和同步，请选择 **以下三种** 受支持的方法之一：

1. 基本身份验证
1. ServiceNow OAuth (推荐) 
1. Azure AD OpenID Connect

### <a name="basic-authentication"></a>基本身份验证

输入具有知识角色的 ServiceNow 帐户 **的用户名和密码** ，以向实例进行身份验证。

### <a name="servicenow-oauth"></a>ServiceNow OAuth

若要使用 ServiceNow OAuth 进行身份验证，请设置 ServiceNow 实例中的终结点。 Microsoft 搜索应用将使用它来访问实例。 若要了解更多信息，请参阅 ["为客户端创建终结点以访问](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) ServiceNow 文档中的实例"。

下表提供了有关如何填写终结点创建表单的指导：

字段 | 说明 | 建议值 
--- | --- | ---
名称 | 标识需要 OAuth 访问的应用程序的唯一值。 | Microsoft 搜索
客户端 ID | 应用程序的只读自动生成的唯一 ID。 实例在请求访问令牌时使用客户端 ID。 | 不适用
客户端密码 | 通过此共享密码字符串，ServiceNow 实例和 Microsoft 搜索可授权相互通信。 | 将密码视为密码，以遵循安全最佳做法。
重定向 URL | 授权服务器重定向到的必需回调 URL。 | https://gcs.office.com/v1.0/admin/oauth/callback
徽标 URL | 包含应用程序徽标图像 URL。 | 不适用
活动文件 | 选中此复选框可以使应用程序注册表处于活动状态。 | 设置为活动
刷新令牌有效期 | 刷新令牌有效的秒数。 默认情况下，刷新令牌在 100 天内过期 (8，640，000 秒) 。 | 31，536，000 (1 年) 
访问令牌有效期 | 访问令牌有效的秒数。 | 43，200 (12 小时) 

输入客户端 ID 和客户端密码以连接到你的实例。 连接后，使用 ServiceNow 帐户凭据对爬网权限进行身份验证。 该帐户至少应具有 **知识** 角色。

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

若要使用 Azure AD OpenID Connect 进行身份验证，请按照以下步骤操作。

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>步骤 3.a：在 Azure Active Directory 中注册新应用程序

若要了解如何在 Azure Active Directory 中注册新应用程序，请参阅["注册应用程序"。](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application) 选择单个租户组织目录。 不需要重定向 URI。 注册后，记下应用程序 (客户端) ID 和目录 (租户) ID。

## <a name="step-3b-create-a-client-secret"></a>步骤 3.b：创建客户端密码

若要了解如何创建客户端密码，请参阅"[创建客户端密码"。](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) 记下客户端密码。

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>步骤 3.c：检索服务主体对象标识符

按照步骤检索服务主体对象标识符

1. 运行 PowerShell。

2. 使用下面的命令安装 Azure PowerShell。

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. 连接到 Azure。

   ```powershell
   Connect-AzAccount
   ```

4. 获取服务主体对象标识符。

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   将"Application-ID"替换为在步骤 3.a (注册的应用程序) ID (不带) 引号。 记下 PowerShell 输出中的 ID 对象的值。 它是服务主体 ID。

现在，你已拥有 Azure 门户中所需的全部信息。 下表中提供了信息的快速摘要。

属性 | 说明 
--- | ---
租户 ID (的目录 ID)  | 步骤 3.a 中 Azure Active Directory 租户的唯一 ID。
客户端 ID (应用程序 ID)  | 步骤 3.a 中注册的应用程序的唯一 ID。
客户端密码 | 从步骤 3.b 开始 (应用程序的密钥) 。 请像密码一样对待它。
服务主体 ID | 作为服务运行的应用程序的标识。  (步骤 3.c 中) 

## <a name="step-3d-register-servicenow-application"></a>步骤 3.d：注册 ServiceNow 应用程序

ServiceNow 实例需要以下配置：

1. 注册新的 OAuth OIDC 实体。 若要了解，请参阅["创建 OAuth OIDC 提供程序"。](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)

2. 下表提供了有关如何填写 OIDC 提供程序注册表单的指导

   字段 | 说明 | 建议值
   --- | --- | ---
   名称 | 标识 OAuth OIDC 实体的唯一名称。 | Azure AD
   客户端 ID | 第三方 OAuth OIDC 服务器中注册的应用程序的客户端 ID。 实例在请求访问令牌时使用客户端 ID。 | 步骤 3.a (客户端) ID
   客户端密码 | 第三方 OAuth OIDC 服务器中注册的应用程序的客户端密码。 | 步骤 3.b 中的客户端密码

   所有其他值都可以为默认值。

3. 在 OIDC 提供程序注册表单中，需要添加新的 OIDC 提供程序配置。 针对 *OAuth OIDC 提供程序配置* 字段选择搜索图标以打开 OIDC 配置的记录。 选择"新建"。

4. 下表提供了有关如何填写 OIDC 提供程序配置表单的指导

   字段 | 建议值
   --- | ---
   OIDC 提供程序 |  Azure AD
   OIDC 元数据 URL | URL 必须采用 https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>将"tenantID"替换为步骤 3.a (的) 租户 ID。
   OIDC 配置缓存生命周期 |  120
   应用程序 | 全球
   用户声明 | sub
   用户字段 | 用户 ID
   启用 JTI 声明验证 | 禁用

5. 选择"提交并更新 OAuth OIDC 实体"表单。

## <a name="step-3e-create-a-servicenow-account"></a>步骤 3.e：创建 ServiceNow 帐户

请参阅创建 ServiceNow 帐户的说明， [在 ServiceNow 中创建用户](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。

下表提供了有关如何填写 ServiceNow 用户帐户注册的指南

字段 | 建议值
--- | ---
用户 ID | 步骤 3.c 中的服务主体 ID
仅 Web 服务访问 | Checked

所有其他值都可以设置为默认值。

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>步骤 3.f：为 ServiceNow 帐户启用"知识"角色

访问使用 ServiceNow 主体 ID 作为用户 ID 创建的 ServiceNow 帐户，并分配知识角色。 有关将角色分配给 ServiceNow 帐户的说明，请参阅：将角色 [分配给用户](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。

使用步骤 3.a 中的应用程序 ID 和步骤 3.b 中的客户端密码，使用 Azure AD OpenID Connect 对 ServiceNow 实例进行身份验证。

## <a name="step-4-select-properties-and-filter-data"></a>步骤 4：选择属性和筛选数据

在此步骤中，可以从 ServiceNow 数据源中添加或删除可用属性。 默认情况下，Microsoft 365 已选择几个属性。

使用 ServiceNow 查询字符串，可以指定同步文章的条件。 它就像 Select 语句中的 **Where** **SQL** 子句。 例如，可以选择仅对已发布和处于活动状态的文章编制索引。 若要了解如何创建自己的查询字符串，请参阅 [使用筛选器生成编码的查询字符串](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。

使用预览结果按钮验证所选属性和查询筛选器的示例值。

## <a name="step-5-manage-search-permissions"></a>步骤 5：管理搜索权限

ServiceNow 连接器支持对具有此数据源访问权限的任何人或 **仅人员可见的搜索权限**。 已编制索引的数据将显示在搜索结果中，并且对组织中分别具有访问权限的用户可见。 ServiceNow 连接器支持默认用户条件权限，而无需高级脚本。 当连接器找到具有高级脚本的用户条件时，使用该用户条件的所有数据将不会显示在搜索结果中。

如果选择"仅具有此数据源访问权限的用户"，则需要进一步选择你的 ServiceNow 实例是否具有 Azure Active Directory (AAD) 设置的用户或非 AAD 用户。

>[!NOTE]
>如果选择仅对此数据源具有访问权限的人，则 ServiceNow 连接器为 **预览版**。

>[!NOTE]
>如果选择 AAD 作为标识源类型，请确保将 UPN 源属性分配给 ServiceNow 中的电子邮件目标属性。 若要验证或更改映射，请参阅在 Azure Active Directory 中为 SaaS 应用程序自定义 [用户预配属性映射](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes)。

如果选择从 ServiceNow 实例中获取 ACL，并且为标识类型选择了"非 AAD"，请参阅"映射非 [Azure AD](map-non-aad.md) 标识"，获取有关映射标识的说明。

## <a name="step-6-assign-property-labels"></a>步骤 6：分配属性标签

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>步骤 7：管理架构

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>步骤 8：选择刷新设置

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>对于标识，将仅应用计划的完全爬网。

## <a name="step-9-review-connection"></a>步骤 9：查看连接

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>故障排除

发布连接后，自定义结果页后，可以在管理中心的"连接器 **"选项卡**[下查看状态](https://admin.microsoft.com)。 若要了解如何进行更新和删除，请参阅["管理连接器"。](manage-connector.md)

## <a name="limitations"></a>限制

ServiceNow Graph 连接器在其最新版本中具有以下限制：

- 为组织中每个人都可用的知识库文章编制索引是一项普遍可用的功能。
- *只有具有"管理搜索权限* "步骤下此数据源功能的访问权限的用户才在预览版中，并且仅处理 [用户条件](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) 权限。 其他任何类型的访问权限不会应用到搜索结果中。
- 当前预览版本中不支持具有高级脚本的用户条件。 具有访问限制的知识文章将编制索引，拒绝所有人访问，并且不会在搜索结果中显示给任何用户，除非我们支持它们。
