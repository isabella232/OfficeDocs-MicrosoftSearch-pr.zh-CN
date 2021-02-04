---
title: 用于 Microsoft 搜索的 Azure DevOps Graph 连接器
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
description: 为 Microsoft 搜索设置 Azure DevOps Graph 连接器
ms.openlocfilehash: 8fe783c847c672223e051f4433af3e41678fe367
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097400"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Azure DevOps Graph 连接器 (预览) 

Azure DevOps Graph 连接器允许组织在其 Azure DevOps 服务实例中为工作项编制索引。 配置 Azure DevOps 中的连接器和索引内容后，最终用户可以在 Microsoft 搜索中搜索这些项目。

> [!NOTE]
> 阅读 [**Graph 连接器的安装程序**](configure-connector.md) 文章，了解一般的 Graph 连接器设置过程。

本文适用于配置、运行和监视 Azure DevOps Graph 连接器的任何人。 它补充了常规安装过程，并显示了仅适用于 Azure DevOps Graph 连接器的说明。

>[!IMPORTANT]
>Azure DevOps 连接器仅支持 Azure DevOps 云服务。 此连接器不支持 Azure DevOps Server 2019、TFS 2018、TFS 2017、TFS 2015 和 TFS 2013。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

若要连接到 Azure DevOps 实例，需要 Azure [DevOps](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) 组织名称、应用 ID 和客户端密码进行 OAuth 身份验证。

### <a name="register-an-app"></a>注册应用

在 Azure DevOps 中注册应用，以便 Microsoft 搜索应用可以访问该实例。 若要了解更多信息，请参阅 Azure DevOps 文档，了解如何 [注册应用](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)。

下表提供了有关如何填写应用程序注册表单的指导：

必填字段 | 说明 | 建议值
--- | --- | ---
| 公司名称         | 公司的名称。 | 使用适当的值   |
| 应用程序名称     | 标识要授权的应用程序的唯一值。    | Microsoft 搜索     |
| 应用程序网站  | 在连接器设置过程中请求访问 Azure DevOps 实例的应用程序的 URL。  (必需) 。  | https://<span>gcs.office。</span>com/
| 授权回调 URL        | 授权服务器重定向到的必需回调 URL。 | https://<span>gcs.office。</span>com/v1.0/admin/oauth/callback|
| 授权范围 | 应用程序的访问范围 | 选择以下范围：标识 (读取) 、工作项 (读取) 、变量组 (读取) 、项目和团队 (读取) 、Graph (读取) |

使用上述详细信息注册应用时，将获取将用于配置连接器的应用 **ID** 和客户端密码。

>[!NOTE]
>若要撤销对在 Azure DevOps 中注册的任何应用的访问权限，请转到 Azure DevOps 实例右上方的用户设置。 选择"配置文件"，然后在侧窗格的"安全性"部分选择"授权"。 将鼠标悬停在已授权的 OAuth 应用上，以查看应用详细信息的一角的"撤销"按钮。

### <a name="connection-settings"></a>连接设置

向 Azure DevOps 注册 Microsoft 搜索应用后，可以完成连接设置步骤。 输入组织名称、应用 ID 和客户端密码。

![连接应用程序设置](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>配置数据：选择项目和字段

您可以选择连接来为整个组织或特定项目编制索引。

如果选择为整个组织编制索引，则组织的所有项目中的项目都将编制索引。 创建新项目和项目后，将在下一次爬网过程中对这些项目编制索引。

如果您选择单个项目，则只会对这些项目中的工作项编制索引。

![配置数据](media/ADO_Configure_data.png)

接下来，在继续操作之前，选择您希望连接索引和预览这些字段中数据的字段。

![选择属性](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>步骤 4：管理搜索权限

Azure DevOps 连接器支持仅对此数据源或  **** 所有人具有访问权限的用户可见的 **搜索权限**。 如果选择"仅有权访问此数据源的用户"，则基于对 Azure DevOps 中组织、项目或区域路径级别用户或组的权限，已编制索引的数据将显示在具有访问权限的用户的搜索结果中。 如果选择" **每个人**"，则索引数据将显示在所有用户的搜索结果中。

## <a name="step-5-assign-property-labels"></a>步骤 5：分配属性标签

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。

## <a name="step-6-manage-schema"></a>步骤 6：管理架构

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。

## <a name="step-7-choose-refresh-settings"></a>步骤 7：选择刷新设置

Azure DevOps 连接器支持完全爬网和增量爬网的刷新计划。
对于增量爬网，建议计划为一小时，完全爬网为一天。

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
