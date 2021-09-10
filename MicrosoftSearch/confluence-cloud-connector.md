---
title: Confluence 云Graph连接器Microsoft 搜索
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置 Confluence 云Graph连接器Microsoft 搜索
ms.openlocfilehash: baf6139257c8bf8e40bc997e2a408efb4fc2549f
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973377"
---
<!---Previous ms.author: kam1 --->

# <a name="confluence-cloud-graph-connector-preview"></a>Confluence Cloud Graph Connector (Preview) 

Confluence 云Graph连接器允许组织对 Confluence 内容编制索引。 配置来自 Confluence 网站的连接器和索引数据后，最终用户可以在网站中搜索Microsoft 搜索。

>[!NOTE]
>Confluence 云Graph连接器预览版。 如果希望提前访问试用，请使用此表单 [<b> 进行注册 </b>](https://forms.office.com/r/duLxv8Nf8U)。  

本文适用于配置Microsoft 365运行和监视 Confluence 云连接器的管理员Graph用户。 它补充了设置连接器文章中提供的Graph[说明](configure-connector.md)。 如果尚未这样做，请阅读整个设置 Graph 连接器一文，了解常规设置过程。

下面列出了设置过程的每一步以及一条说明，指示你应遵循常规设置说明或仅适用于 Confluence 云 Graph 连接器的其他说明，包括有关疑难解答和限制[的信息](#limitations)。 [](#troubleshooting)


## <a name="before-you-get-started"></a>在开始使用之前
你必须是组织的 M365 租户的管理员以及组织的 Confluence 网站的管理员。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在Graph连接器中添加Microsoft 365 管理中心
按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接
按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置
若要连接到 Confluence 网站，请使用您的网站 URL。 Confluence 云站点 URL 通常类似于 *https：//<organization_name>.atlassian.net/*。 可以选择"基本身份验证"或"OAuth 2.0" (推荐) 向 Confluence 网站进行身份验证。

### <a name="basic-auth"></a>基本身份验证
输入帐户的用户名 (电子邮件 ID) API 令牌，以使用基本身份验证进行身份验证。若要了解有关生成 API 令牌的信息，请参阅 Atlassian 的文档，了解如何管理 [您的 Atlassian](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)帐户的 API 令牌。

### <a name="oauth-20"></a>OAuth 2.0
在 Confluence 云中注册应用，Microsoft 搜索访问实例。 若要了解更多信息，请参阅如何启用 [OAuth 2.0](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)的 Atlassian 支持文档。

以下步骤提供了有关如何注册应用的指南：

1. 使用你的 [Atlassian](https://developer.atlassian.com/console/myapps/) Confluence 管理员帐户登录到 Atlassian 开发人员控制台。
2. 单击并选择 `Create``OAuth 2.0 integration`
3. 为应用程序提供适当的名称并创建新应用。
4. 从左侧 `Permissions` 导航窗格中导航到 。 单击 `Add` 以选择 `Confluence API` 。 添加后，单击 `Configure` 并添加以下范围 ： 、 `Read Confluence space summary` `Read Confluence content properties` 、 、 和 `Read Confluence detailed content` `Read Confluence content summary` `Read content permission in Confluence` `Read user` `Read user groups` `Search Confluence content and space summaries` 。
5. 从左侧 `Authorization` 导航窗格中导航到 。 添加回调 URL `https://gcs.office.com/v1.0/admin/oauth/callback` 并保存更改。
6. 从左侧 `Settings` 导航窗格中导航到 。 你将从 `Client ID` 此页面获取 `Secret` 和 。

使用上述详细信息注册应用时，你可获取 **客户端 ID** 和 **密码**。 使用这些方法完成连接设置步骤。

## <a name="step-4-select-properties-and-filter-data"></a>步骤 4：选择属性和筛选数据

在此步骤中，可以在 Confluence 数据源中添加或删除可用属性。 Microsoft 365已默认选择了几个属性。

使用 CQL 查询语言 (CQL) ，您可以指定同步页面的条件。 它就像 Select 语句中的 **Where** **SQL** 语句。 例如，可以选择仅对过去两年修改的页面编制索引。 若要了解如何创建自己的查询字符串，请参阅使用 [CQL 的高级搜索](https://developer.atlassian.com/server/confluence/advanced-searching-using-cql/)。 默认情况下，连接器将索引所有博客和页面。

使用"预览结果"按钮验证所选属性和 CQL 字符串的示例值。

## <a name="step-5-manage-search-permissions"></a>步骤 5：管理搜索权限

Confluence 云Graph连接器支持对"任何人"或"仅  **** 有权访问此 **数据源的人"可见的搜索权限**。 如果选择" **任何人"，** 则索引数据将显示在所有用户的搜索结果中。 如果您选择"仅有权访问此数据源的用户 **"，** 则索引数据将显示在具有访问权限的用户的搜索结果中。

在 Confluence 云中，使用空间权限和页面限制定义用户和组的安全权限。 Confluence 云Graph连接器将应用空间权限（如果没有页面限制）。 如果存在页面级别限制，则优先于空间权限。

如果您选择"**仅有权访问** 此数据源的用户"，则需要进一步选择您的 Confluence 网站是否Azure Active Directory (AAD) 已设置用户或非 AAD 用户。

若要确定适合贵组织的选项：

1. 如果 Confluence 用户的电子邮件 ID 与 **AAD** 中用户的 UserPrincipalName (UPN) ，请选择"AAD"选项。 
2. 如果 Confluence 用户的电子邮件 ID 与 **AAD** 中用户的 UserPrincipalName (UPN) ，请选择"非 AAD"选项。 

>[!NOTE]
> * 如果选择 AAD 作为标识源类型，连接器将直接从 Confluence 获取的用户的电子邮件标识映射到 AAD 中的 UPN 属性。
> * 如果你为标识类型选择"非 AAD"，请参阅映射非 [Azure AD](map-non-aad.md) 标识，获取映射标识的说明。 可以使用此选项提供从电子邮件 ID 到 UPN 的映射正则表达式。

## <a name="step-6-assign-property-labels"></a>步骤 6：分配属性标签

按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-7-manage-schema"></a>步骤 7：管理架构

按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-8-choose-refresh-settings"></a>步骤 8：选择刷新设置

按照常规 [设置说明操作](./configure-connector.md)。

>[!NOTE]
>对于访问权限更新，将仅应用计划的完全爬网。

## <a name="step-9-review-connection"></a>步骤 9：查看连接

按照常规 [设置说明操作](./configure-connector.md)。

发布连接后，需要自定义搜索结果页面。 若要了解如何自定义搜索结果，请参阅自定义 [搜索结果页面](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)。

## <a name="troubleshooting"></a>疑难解答
下面列出了配置连接器时观察到的常见错误及其可能的原因。

| 配置步骤 | 错误消息 | 可能 (原因)  |
| ------------ | ------------ | ------------ |
| 连接设置 | 该请求格式有误或不正确。 | 错误的 Confluence 网站 URL |
| 连接设置 | 无法访问 Confluence 站点的 Confluence 云服务。 | 错误的 Confluence 网站 URL |
| 连接设置 | 客户端没有执行此操作的权限。 | 为基本身份验证提供的 API 令牌无效 |
| 选择属性 | 无错误消息和预览结果 | 检查 CQL 查询是否有效 |

## <a name="limitations"></a>限制
Confluence 云Graph连接器在其最新版本中具有以下已知限制：

- Confluence 云连接器不索引附件文件和注释。
- 索引服务器和数据中心部署将作为单独的连接器发布。