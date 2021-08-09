---
title: ServiceNow Graph连接器Microsoft 搜索
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
description: 为 Graph 设置 ServiceNow Microsoft 搜索
ms.openlocfilehash: 11abe956e624fa23cd19e2dfc2ae9a4af31a0f81407f6e2c5672723c5fdfc8b5
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2021
ms.locfileid: "54534128"
---
<!---Previous ms.author: kam1 --->


# <a name="servicenow-graph-connector"></a>ServiceNow Graph 连接器

借助 Microsoft Graph Connector for ServiceNow，组织可以索引对所有用户可见的知识库文章，或对组织中具有用户条件权限受限的知识库文章编制索引。 从 ServiceNow 配置连接器并索引内容后，最终用户可以从任何客户端搜索Microsoft 搜索文章。  

本文适用于配置Microsoft 365运行和监视 ServiceNow 连接器的管理员Graph用户。 它补充了设置连接器文章中提供的Graph[说明](configure-connector.md)。 如果尚未这样做，请阅读整个设置 Graph 连接器一文，了解常规设置过程。

下面列出了安装过程的每一步以及一条说明，指示你应遵循常规设置说明或仅适用于 ServiceNow Graph 连接器的其他说明，包括有关疑难解答和限制[的信息。](#limitations) [](#troubleshooting)  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在Graph中添加一个Microsoft 365 管理中心。
按照常规设置说明操作。

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接。
按照常规设置说明操作。


## <a name="step-3-connection-settings"></a>步骤 3：连接设置
若要连接到 ServiceNow 数据，你需要组织的 **ServiceNow 实例 URL**。 组织的 ServiceNow 实例 URL 通常 https:// **&lt; 组织域>.service-now.com**。 

除了此 URL 外，还需要一个服务帐户来设置与 ServiceNow 的连接，并允许 Microsoft 搜索 根据刷新计划定期更新知识文章。 该服务帐户将需要对以下 **ServiceNow** 表记录的读取权限，以成功对各种实体进行爬网。

**功能** | **需要读取访问权限的表** | **说明**
--- | --- | ---
索引可供所有人使用的知识 <em>文章</em> | kb_knowledge | 用于对知识库文章进行爬网
索引和支持用户条件权限 | kb_uc_can_read_mtom | Who阅读此知识库
| | kb_uc_can_contribute_mtom | Who可参与此知识库
| | kb_uc_cannot_read_mtom | Who无法读取此知识库
| | kb_uc_cannot_contribute_mtom | Who无法参与此知识库
| | sys_user | 读取用户表
| | sys_user_has_role | 读取用户的角色信息
| | sys_user_grmember | 读取用户的组成员身份
| | user_criteria | 读取用户条件权限
| | kb_knowledge_base | 读取知识库信息

你可以 **为用于连接** 服务帐户的服务帐户创建和分配Microsoft 搜索。 [了解如何为 ServiceNow 帐户分配角色](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。 可以在已创建的角色上分配表的读取权限。 若要了解如何设置对表记录的读取访问权限，请参阅 [保护表记录](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)。 


>[!NOTE]
> ServiceNow Graph 连接器可以在没有高级脚本的情况下对知识库文章和用户条件权限编制索引。 如果用户条件包含高级脚本，将在搜索结果中隐藏所有相关的知识库文章。

若要对 ServiceNow 中的内容进行身份验证和同步，请选择 **以下三种受支持的方法** 之一： 
 
- 基本身份验证 
- ServiceNow OAuth (推荐) 
- Azure AD OpenID 连接

## <a name="step-31-basic-authentication"></a>步骤 3.1：基本身份验证

输入具有知识角色的 ServiceNow 帐户 **的用户名和密码** ，以向实例进行身份验证。

## <a name="step-32-servicenow-oauth"></a>步骤 3.2：ServiceNow OAuth

若要使用 ServiceNow OAuth 进行身份验证，ServiceNow 管理员需要在 ServiceNow 实例中预配终结点，以便Microsoft 搜索访问它。 若要了解更多信息，请参阅[](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html)ServiceNow 文档中的为客户端创建用于访问实例的终结点。

下表提供了有关如何填写终结点创建表单的指导：

字段 | 说明 | 建议值 
--- | --- | ---
名称 | 标识需要 OAuth 访问的应用程序的唯一值。 | Microsoft 搜索
客户端 ID | 应用程序的只读自动生成的唯一 ID。 实例在请求访问令牌时使用客户端 ID。 | 不适用
客户端密码 | 通过此共享密码字符串，ServiceNow 实例Microsoft 搜索相互授权通信。 | 通过将密码视为密码来遵循安全性最佳做法。
重定向 URL | 授权服务器重定向到的必需回调 URL。 | https://gcs.office.com/v1.0/admin/oauth/callback
徽标 URL | 包含应用程序徽标的图像的 URL。 | 不适用
活动 | 选中此复选框可以使应用程序注册表处于活动状态。 | 设置为活动
刷新令牌有效期 | 刷新令牌有效的秒数。 默认情况下，刷新令牌在 100 天后过期 (8，640，000 秒) 。 | 31，536，000 (年 1) 
访问令牌有效期 | 访问令牌有效的秒数。 | 43，200 (12 小时) 

输入客户端 ID 和客户端密码以连接到实例。 连接后，使用 ServiceNow 帐户凭据对爬网权限进行身份验证。 帐户应至少具有 **知识** 角色。 参考步骤 [3：连接](#step-3-connection-settings) 设置开头的表，该表格提供对更多 ServiceNow 表记录和索引用户条件权限的读取访问权限。

## <a name="step-33-azure-ad-openid-connect"></a>步骤 3.3：Azure AD OpenID 连接

若要使用 Azure AD OpenID 连接进行身份验证，请按照以下步骤操作。

### <a name="step-331-register-a-new-application-in-azure-active-directory"></a>步骤 3.3.1：在 Azure Active Directory

若要了解如何在应用程序中注册新Azure Active Directory，请参阅[注册应用程序](/azure/active-directory/develop/quickstart-register-app#register-an-application)。 选择单个租户组织目录。 不需要重定向 URI。 注册后，记下应用程序 (客户端) ID 和目录 (租户) ID。

### <a name="step-332-create-a-client-secret"></a>步骤 3.3.2：创建客户端密码

若要了解如何创建客户端密码，请参阅创建 [客户端密码](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。 记下客户端密码。

### <a name="step-333-retrieve-service-principal-object-identifier"></a>步骤 3.3.3：检索服务主体对象标识符

按照步骤检索服务主体对象标识符

1. 运行 PowerShell。

2. 使用Azure PowerShell安装客户端。

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. 连接 Azure。

   ```powershell
   Connect-AzAccount
   ```

4. 获取服务主体对象标识符。

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   将"Application-ID"替换为 Application (client) ID (，而不) 步骤 3.a 中注册的应用程序的引号。 请注意 PowerShell 输出中的 ID 对象的值。 它是服务主体 ID。

现在，你已拥有 Azure 门户中需要的所有信息。 下表提供了信息的快速摘要。

属性 | 说明 
--- | ---
租户 ID (的目录 ID)  | 步骤 3.a Azure Active Directory租户的唯一 ID。
客户端 ID (应用程序 ID)  | 步骤 3.a 中注册的应用程序的唯一 ID。
客户端密码 | 应用程序的密钥从步骤 3.b (开始) 。 请像处理密码一样处理它。
服务主体 ID | 作为服务运行的应用程序的标识。  (步骤 3.c) 

### <a name="step-334-register-servicenow-application"></a>步骤 3.3.4：注册 ServiceNow 应用程序

ServiceNow 实例需要以下配置：

1. 注册新的 OAuth OIDC 实体。 若要了解，请参阅 [创建 OAuth OIDC 提供程序](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

2. 下表提供了有关如何填写 OIDC 提供程序注册表单的指导

   字段 | 说明 | 建议值
   --- | --- | ---
   名称 | 标识 OAuth OIDC 实体的唯一名称。 | Azure AD
   客户端 ID | 第三方 OAuth OIDC 服务器中注册的应用程序的客户端 ID。 实例在请求访问令牌时使用客户端 ID。 | 步骤 3 (客户端) ID
   客户端密码 | 第三方 OAuth OIDC 服务器中注册的应用程序的客户端密码。 | 步骤 3.b 中的客户端密码

   所有其他值都可以为默认值。

3. 在 OIDC 提供程序注册表单中，需要添加新的 OIDC 提供程序配置。 选择针对 *OAuth OIDC 提供程序配置字段的* 搜索图标以打开 OIDC 配置的记录。 选择"新建"。

4. 下表提供了有关如何填写 OIDC 提供程序配置表单的指南

   字段 | 建议值
   --- | ---
   OIDC 提供程序 |  Azure AD
   OIDC 元数据 URL | URL 格式必须为 https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>将"tenantID"替换为步骤 3.a 中的 (租户) ID。
   OIDC 配置缓存生命周期 |  120
   应用程序 | 全球
   用户声明 | sub
   用户字段 | 用户 ID
   启用 JTI 声明验证 | 禁用

5. 选择"提交并更新 OAuth OIDC 实体"表单。

### <a name="step-335-create-a-servicenow-account"></a>步骤 3.3.5：创建 ServiceNow 帐户

请参阅创建 ServiceNow 帐户、在 [ServiceNow 中创建用户的说明](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。

下表提供了有关如何填写 ServiceNow 用户帐户注册的指南

字段 | 建议值
--- | ---
用户 ID | 步骤 3.c 中的服务主体 ID
仅 Web 服务访问 | Checked

所有其他值都可以留为默认值。

### <a name="step-336-enable-knowledge-role-for-the-servicenow-account"></a>步骤 3.3.6：为 ServiceNow 帐户启用知识角色

访问使用 ServiceNow 主体 ID 作为用户 ID 创建的 ServiceNow 帐户，并分配知识角色。 可以在此处找到将角色分配给 ServiceNow 帐户的说明，将角色 [分配给用户](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。 参考步骤 [3：连接](#step-3-connection-settings) 设置开头的表，该表格提供对更多 ServiceNow 表记录和索引用户条件权限的读取访问权限。

在管理中心配置向导中，将应用程序 ID 用作步骤 3.a) 中的客户端 ID (和步骤 3.b) 中的客户端密码 (，以使用 Azure AD OpenID 连接 向 ServiceNow 实例进行身份验证。

## <a name="step-4-select-properties-and-filter-data"></a>步骤 4：选择属性和筛选数据

在此步骤中，可以从 ServiceNow 数据源中添加或删除可用属性。 Microsoft 365已默认选择了几个属性。

使用 ServiceNow 查询字符串，可以指定用于同步文章的条件。 它就像 Select 语句中的 **Where** **SQL** 子句。 例如，可以选择仅对已发布和处于活动状态的文章编制索引。 若要了解如何创建自己的查询字符串，请参阅使用筛选器生成编码 [的查询字符串](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。

使用"预览结果"按钮验证所选属性和查询筛选器的示例值。

## <a name="step-5-manage-search-permissions"></a>步骤 5：管理搜索权限

ServiceNow 连接器支持对"任何人"或"仅有权访问此数据源的人"**可见的搜索权限**。 索引数据显示在搜索结果中，并且对组织中所有用户或分别可通过用户条件权限访问它们的用户可见。 如果未使用用户条件启用知识库文章，则它将出现在组织中所有人的搜索结果中。

ServiceNow Graph 连接器支持不带高级脚本的默认用户条件权限。 当连接器遇到具有高级脚本的用户条件时，使用该用户条件的所有数据将不会显示在搜索结果中。

>[!NOTE]
>若要选择 **"仅有权访问此数据源的人"，** 请对租户启用定向发布更新。 若要了解如何设置定向发布，请参阅设置 [定向发布选项。](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)

如果选择"仅有权访问此数据源的用户 **"，** 则需要进一步选择 ServiceNow 实例是否Azure Active Directory (AAD) 用户或非 AAD 用户。

>[!NOTE]
>如果选择 AAD 作为标识源类型，请确保将 UserPrincipalName (UPN) 属性分配给 ServiceNow 中的电子邮件目标属性。 若要验证或更改映射，请参阅自定义 SaaS 应用程序中的用户预配属性[Azure Active Directory。](/azure/active-directory/app-provisioning/customize-application-attributes)

如果你为标识类型选择"非 AAD"，请参阅映射非 [Azure AD](map-non-aad.md) 标识，获取有关映射标识的说明。 

还可以参考以下视频，了解有关管理搜索权限的更多内容。

[![Managing Search Permissions in Microsoft Graph Connector for ServiceNow](https://img.youtube.com/vi/TVSkJpk1RiE/hqdefault.jpg)](https://www.youtube.com/watch?v=TVSkJpk1RiE)

## <a name="step-6-assign-property-labels"></a>步骤 6：分配属性标签

按照常规设置说明操作。

## <a name="step-7-manage-schema"></a>步骤 7：管理架构

按照常规设置说明操作。

## <a name="step-8-choose-refresh-settings"></a>步骤 8：选择刷新设置

按照常规设置说明操作。

>[!NOTE]
>对于标识，将仅应用计划的完全爬网。

## <a name="step-9-review-connection"></a>步骤 9：查看连接

按照常规 [设置说明操作](./configure-connector.md)。

ServiceNow Graph连接器在其最新版本中具有以下限制：

发布连接后，需要自定义搜索结果页面。 若要了解如何自定义搜索结果，请参阅自定义 [搜索结果页面](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)。

## <a name="limitations"></a>限制
ServiceNow Graph连接器在其最新版本中具有以下限制：
- 对组织中每个人都可用的知识库文章编制索引是一项普遍可用的功能。
- *只有具有"管理* 搜索权限"步骤下此数据源功能的访问权限的用户才位于目标发布频道中，并且仅处理 [用户条件](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) 权限。 任何任何类型的访问权限将不会在搜索结果中应用。
- 当前版本不支持具有高级脚本的用户条件。 任何具有此类访问限制的知识文章都会编制索引，拒绝所有人访问，即，在我们支持它们之前，这些文章不会显示在任何用户的搜索结果中。

## <a name="troubleshooting"></a>疑难解答
发布连接后，自定义结果页后，可以在管理中心的"数据源 **"选项卡下** 查看 [状态](https://admin.microsoft.com)。 若要了解如何进行更新和删除，请参阅 [管理连接器](manage-connector.md)。
在下面可以找到常见问题的疑难解答步骤。
### <a name="1-unable-to-login-due-to-single-sign-on-enabled-servicenow-instance"></a>1. 无法登录，因为启用了单Sign-On ServiceNow 实例

如果组织已启用单一Sign-On (SSO) ServiceNow，则使用服务帐户登录时可能遇到问题。 可以通过添加到 ServiceNow 实例 URL<em> `login.do` </em>来显示基于用户名和密码的登录名。 示例。 `https://<your-organization-domain>.service-now.com./login.do` 

### <a name="2-unauthorized-or-forbidden-response-to-api-request"></a>2. 未经授权或禁止响应 API 请求

#### <a name="21-check-table-access-permissions"></a>2.1. 检查表访问权限
如果在连接状态中看到禁止响应或未授权响应，请检查服务帐户是否具有对步骤 [3：](#step-3-connection-settings)连接设置 中提到的表所需的访问权限。 请检查表中的所有列是否具有读取权限。

#### <a name="22-check-if-servicenow-instance-behind-firewall"></a>2.2. 检查防火墙后的 ServiceNow 实例
Graph如果连接器位于网络防火墙后面，则可能无法访问 ServiceNow 实例。 您需要明确允许访问 Graph 连接器服务。 您可以在下表中查找 Graph 连接器服务的公用 IP 地址范围。 根据你的租户区域，将其添加到你的 ServiceNow 实例网络白名单。

**环境** | **Region** | **区域**
--- | --- | ---
PROD | 北美 | 52.250.92.252/30, 52.224.250.216/30
PROD | 欧洲 | 20.54.41.208/30, 51.105.159.88/30 
PROD | 亚太地区 | 52.139.188.212/30, 20.43.146.44/30 


如果你有任何其他问题或想要提供反馈，请告诉我们 aka.ms/TalkToGraphConnectors [](https://aka.ms/TalkToGraphConnectors)
