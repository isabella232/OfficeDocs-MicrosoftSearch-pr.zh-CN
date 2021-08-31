---
title: Azure DevOps Graph连接器Microsoft 搜索
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
description: 设置Azure DevOps Graph连接器Microsoft 搜索
ms.openlocfilehash: fcf381a92ef397f900b300ca667fa80067a6672a
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701387"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Azure DevOps Graph连接器 (预览) 

通过Azure DevOps Graph连接器，您的组织可以在其服务实例中为工作项Azure DevOps索引。 配置连接器并索引来自 Azure DevOps 的内容后，最终用户可以在 Microsoft 搜索。

> [!NOTE]
> 阅读 [**Graph 连接器的**](configure-connector.md)安装程序一文，了解 Graph 连接器的一般设置说明。

本文适用于配置、运行和监视 Azure DevOps Graph 连接器。 它补充了常规安装过程，并显示了仅适用于 Azure DevOps Graph 连接器的说明。

>[!IMPORTANT]
>the Azure DevOps connector supports only the Azure DevOps cloud service. Azure DevOps Server连接器不支持 TFS 2019、TFS 2018、TFS 2017、TFS 2015 和 TFS 2013。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在Graph连接器中添加Microsoft 365 管理中心

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

若要连接到您的 Azure DevOps实例，您需要您的 Azure DevOps 名称、其应用程序[](/azure/devops/organizations/accounts/create-organization)ID 和客户端密码进行 OAuth 身份验证。

### <a name="register-an-app"></a>注册应用

在应用程序Azure DevOps，以便Microsoft 搜索访问实例。 若要了解更多信息，请参阅Azure DevOps注册应用[的文档](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)。

下表提供了有关如何填写应用程序注册表单的指导：

必需字段 | 说明 | 建议值
--- | --- | ---
| 公司名称         | 公司的名称。 | 使用适当的值   |
| 应用程序名称     | 标识要授权的应用程序的唯一值。    | Microsoft 搜索     |
| 应用程序网站  | 在连接器设置期间请求访问您的 Azure DevOps实例的应用程序的 URL。  (必需) 。  | https://<span>gcs.office。</span>com/
| 授权回调 URL        | 授权服务器重定向到的必需回调 URL。 | https://<span>gcs.office。</span>com/v1.0/admin/oauth/callback|
| 授权范围 | 应用程序的访问范围 | 选择以下范围：Identity (read) 、Work Items (read) 、Variable Groups (read) 、Project and team (read) 、Graph (read) 、Analytics (read) |

>[!IMPORTANT]
>你为应用选择的授权范围应该与上面列出的范围完全匹配。 如果在列表中省略其中一个授权范围，或添加另一个范围，授权将失败。

使用上述详细信息注册应用时，你可获取将用于配置连接器的应用 **ID** 和客户端密码。

>[!NOTE]
>若要撤销对在 Azure DevOps 中注册的任何应用的访问权限，请转到你的 Azure DevOps 实例的右上方的用户设置。 选择"配置文件"，然后在侧窗格的"安全性"部分选择"授权"。 将鼠标悬停在授权 OAuth 应用上方，即可看到应用详细信息右上角的"撤销"按钮。

### <a name="connection-settings"></a>连接设置

向 Microsoft 搜索应用Azure DevOps，可以完成连接设置步骤。 输入组织名称、应用 ID 和客户端密码。

![连接应用程序设置。](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>配置数据：选择项目和字段

您可以选择连接来为整个组织或特定项目编制索引。

如果选择为整个组织编制索引，则组织的所有项目中的项目都将编制索引。 创建新项目和项目后，将在下一次爬网过程中对这些项目编制索引。

如果您选择单个项目，则只会对这些项目中的工作项编制索引。

![配置数据。](media/ADO_Configure_data.png)

接下来，选择您希望连接在这些字段中编制索引和预览数据的字段，然后再继续。

![选择属性。](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>步骤 4：管理搜索权限

the Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**. 如果选择"仅具有此数据源访问权限的用户"，则基于对 Azure DevOps 中组织、Project 或区域路径级别的用户或组的权限，索引数据将显示在搜索结果中。 如果选择" **任何人"，** 则索引数据将显示在所有用户的搜索结果中。

## <a name="step-5-assign-property-labels"></a>步骤 5：分配属性标签

按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-6-manage-schema"></a>步骤 6：管理架构

按照常规 [设置说明操作](./configure-connector.md)。

## <a name="step-7-choose-refresh-settings"></a>步骤 7：选择刷新设置

该Azure DevOps连接器支持完全爬网和增量爬网的刷新计划。
建议的增量爬网计划为 1 小时，完全爬网计划为 1 天。

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](./configure-connector.md)。

>[!TIP]
>**默认结果类型**
>* 连接器Azure DevOps连接器发布[后](./customize-search-page.md#step-2-create-result-types)自动注册结果类型。 结果类型使用基于步骤 3[](./customize-results-layout.md)中选定的字段的动态生成的结果布局。 
>* 可以通过导航到"结果类型"中的"结果类型"来管理 [](https://admin.microsoft.com)[**Microsoft 365 管理中心。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) 默认结果类型将命名为 `ConnectionId` "Default"。 例如，如果你的连接 ID 是 `AzureDevOps` ，结果布局将命名为："AzureDevOpsDefault"
>* 此外，还可以选择创建您自己的结果类型（如果需要）。

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="troubleshooting"></a>疑难解答
以下是配置连接器时观察到的常见错误及其可能的原因。

| 配置步骤 | 错误消息 | 可能 (原因)  |
| ------------ | ------------ | ------------ |
|  | `The account associated with the connector doesn't have permission to access the item.` | 注册的应用没有任何所需的 OAuth 作用域。  (注释 - 2021 年 8 月 31 日引入了新的 OAuth 范围要求"Analytics：read")   |

<!---## Limitations-->
<!---Insert limitations for this data source-->