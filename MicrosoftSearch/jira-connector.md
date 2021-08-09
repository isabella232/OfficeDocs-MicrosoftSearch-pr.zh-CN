---
title: Atlassian Jira Graph连接器Microsoft 搜索
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
description: 设置适用于 Microsoft 搜索 的 Atlassian Jira Graph 连接器
ms.openlocfilehash: 6023e8ec4539bd37358a3e801ef81947fe9f87ff38736344347d5634d0527753
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533686"
---
# <a name="atlassian-jira-graph-connector-preview"></a>Atlassian Jira Graph 连接器 (预览) 

通过 Atlassian Jira Graph连接器，组织可以索引 Jira 问题。 配置连接器并索引 Jira 站点中的内容后，最终用户可以在该站点中搜索Microsoft 搜索。

> [!NOTE]
> 阅读 [**Graph 连接器**](configure-connector.md)的安装程序一文，了解 Graph 连接器的一般设置说明。

本文适用于配置、运行和监视 Atlassian Jira Graph连接器。 它补充了常规安装过程，并显示了仅适用于 Atlassian Jira 连接器Graph说明。

>[!IMPORTANT]
>Atlassian Jira Graph连接器仅支持 Jira 云托管实例。 此连接器不支持 Jira Server 和 Jira 数据中心版本。

## <a name="before-you-get-started"></a>在开始使用之前
你必须是组织的 M365 租户的管理员以及组织的 Jira 网站的管理员。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在Graph中添加一个Microsoft 365 管理中心
按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接
按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置
若要连接到你的 Jira 站点，请使用你的 Jira 站点 URL。 Jira 云站点 URL 通常类似于 *https：//<organization_name>.atlassian.net/*。 你可以选择基本身份验证或 OAuth 2.0 (推荐) Jira 站点进行身份验证。

### <a name="basic-auth"></a>基本身份验证
输入帐户的用户名 (电子邮件 ID) API 令牌使用基本身份验证进行身份验证。若要了解有关生成 API 令牌的信息，请参阅 Atlassian 的文档，了解如何管理 [您的 Atlassian 帐户](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)的 API 令牌。

### <a name="oauth-20"></a>OAuth 2.0
在 Atlassian Jira 中注册应用，Microsoft 搜索应用可以访问该实例。 若要了解更多信息，请参阅如何启用 [OAuth 2.0](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)的 Atlassian 支持文档。

以下步骤提供了有关如何注册应用的指南：

1. 使用你的 [Atlassian](https://developer.atlassian.com/console/myapps/) Jira 管理员帐户登录到 Atlassian 开发人员控制台。
2. 单击并选择 `Create``OAuth 2.0 integration`
3. 为应用程序提供适当的名称并创建新应用。
4. 从左侧 `Permissions` 导航窗格中导航到 。 单击 `Add` 以选择 `Jira platform REST API` 。 添加后，单击 `Configure` 并添加以下范围 - `View Jira issue data` 和 `Manage Jira global settings` `View user profiles` 。
5. 从左侧 `Authorization` 导航窗格中导航到 。 添加回调 URL `https://gcs.office.com/v1.0/admin/oauth/callback` 并保存更改。
6. 从左侧 `Settings` 导航窗格中导航到 。 你将从 `Client ID` 此页面获取 `Secret` 和 。

使用上述详细信息注册应用时，你可获取 **客户端 ID** 和 **密码**。 使用这些方法完成连接设置步骤。

### <a name="step-3a-configure-data-select-projects"></a>步骤 3a：配置数据：选择项目

你可以选择连接以只为整个 Jira 站点或特定项目编制索引。

* 如果选择为整个 Jira 网站编制索引，网站中所有项目中的 Jira 问题都将编制索引。 创建新项目和问题后，将在下一次爬网过程中对这些项目和问题编制索引。
* 如果选择单个项目，则只会对这些项目中的 Jira 问题编制索引。

你可以进一步选择筛选 Jira 问题，这些问题将按 2 种方式编制索引。
* 指定 **问题的修改时间段**。 这将仅对在基于当前爬网滚动选择的时间段中创建或修改的 Jira 问题编制索引。 
* 指定 **JQL**。 这将仅根据所提供的 JQL 查询语言和 JQL 查询语言对筛选后返回的 Jira (编制) 。 若要了解有关使用 JQL 的信息，请参阅有关使用 Jira 查询语言的高级搜索的 Atlassian [支持文档](https://support.atlassian.com/jira-service-management-cloud/docs/use-advanced-search-with-jira-query-language-jql/)

> [!TIP]
> 您可以使用 JQL 筛选器仅对特定 Jira 问题类型编制索引，使用 *"bug，改进 (中的"issueType") "*

### <a name="step-3b-configure-data-select-properties"></a>步骤 3b：配置数据：选择属性

在继续之前，选择您希望连接在这些字段中索引和预览数据的字段。 默认情况下，某些字段已选中，不能删除。

Atlassian Jira Graph 连接器可以索引默认问题字段和自定义创建的问题字段。

> [!NOTE]
> 如果所选的自定义创建字段在一些 Jira 问题类型中不存在 () ，则该字段将被作为 *NULL* (空) 。

## <a name="step-4-manage-search-permissions"></a>步骤 4：管理搜索权限

Atlassian Jira Graph 连接器支持对"任何人"或" **** 仅有权访问此数据源的人"**可见的搜索权限**。 如果选择" **任何人"，** 则索引数据将显示在所有用户的搜索结果中。 如果选择"仅有权访问此数据源的用户 **"，** 则索引数据将显示在具有访问权限的用户的搜索结果中。 在 Atlassian Jira 中，使用包含网站级别组和项目角色的项目权限方案定义安全权限。 也可使用问题级别权限方案定义问题级别安全性。

如果选择"**仅有权访问** 此数据源的用户"，则需要进一步选择你的 Jira 站点是否Azure Active Directory (AAD) 用户或非 AAD 用户。

若要确定适合贵组织的选项：

1. 如果 **Jira** 用户的电子邮件 ID 与 AAD中用户的 UserPrincipalName (UPN) ，请选择 AAD 选项。
2. 如果 Jira 用户的电子邮件 ID 与 **AAD** 中用户的 UserPrincipalName (UPN) ，请选择"非 AAD"选项。 

>[!NOTE]
> * 如果选择 AAD 作为标识源类型，连接器将直接从 Jira 获取的用户的电子邮件标识映射到 AAD 中的 UPN 属性。
> * 如果你为标识类型选择"非 AAD"，请参阅映射非 [Azure AD](map-non-aad.md) 标识，获取有关映射标识的说明。 可以使用此选项提供从电子邮件 ID 到 UPN 的映射正则表达式。

## <a name="step-5-assign-property-labels"></a>步骤 5：分配属性标签

按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-6-manage-schema"></a>步骤 6：管理架构

按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-7-choose-refresh-settings"></a>步骤 7：选择刷新设置

Atlassian Jira Graph 连接器支持完全爬网和增量爬网的刷新计划。
建议的增量爬网计划为 1 小时，完全爬网计划为 1 天。

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](./configure-connector.md)。

## <a name="troubleshooting"></a>疑难解答
下面列出了配置连接器时观察到的常见错误及其可能的原因。

| 配置步骤 | 错误消息 | 可能 (原因)  |
| ------------ | ------------ | ------------ |
| 连接设置 | 该请求格式有误或不正确。 | Jira 站点 URL 不正确 |
| 连接设置 | 无法访问 Jira 站点的 Jira 云服务。 | Jira 站点 URL 不正确 |
| 连接设置 | 客户端没有执行此操作的权限。 | 为基本身份验证提供的 API 令牌无效 |


## <a name="limitations"></a>限制
以下是 Atlassian Jira 连接器的已知Graph：
* 不支持 Jira Server 和数据中心版本。