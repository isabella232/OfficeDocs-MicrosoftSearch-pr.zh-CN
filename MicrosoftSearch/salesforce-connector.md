---
title: 用于 Microsoft 搜索的 Salesforce 连接器
ms.author: rusamai
author: rsamai
manager: jameslao
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: 设置用于 Microsoft 搜索的 Salesforce 连接器
ms.openlocfilehash: 8de7784cae7d430bc385889bd836360c69492591
ms.sourcegitcommit: 77ec27736f3c8434b2ac47e10897ac2606ee8a03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "48992844"
---
# <a name="salesforce-connector"></a>Salesforce 连接器

使用 Salesforce 图形连接器，组织可以在你的 Salesforce 实例中索引联系人、商机、潜在客户和帐户对象。 在从 Salesforce 配置连接器和索引内容之后，最终用户可以从任何 Microsoft Search client 中搜索这些项目。

本文适用于 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理员或任何配置、运行和监控 Salesforce 连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。

>[!IMPORTANT]
>Salesforce Graph 连接器目前支持夏季 "20"、"春季 20"、"冬季 20" 和 "夏季" 19 版。

## <a name="connection-settings"></a>连接设置

若要连接到您的 Salesforce 实例，需要您的 Salesforce 实例 URL、客户端 ID 和 OAuth 身份验证的客户端密码。 以下步骤介绍了您或您的 Salesforce 管理员如何从 Salesforce 帐户获取此信息：

- 登录到您的 Salesforce 实例，然后转到 "设置"

- 导航到 "应用程序-> 应用程序管理器"。

- 选择 " **新建已连接的应用程序** "。

- 完成 "API" 部分，如下所示：

    - 选中 " **启用 Oauth 设置** " 复选框。

    - 将回调 URL 指定为： [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - 选择 "这些必需的 OAuth 作用域"。 

        - 访问和管理您的数据 (api)  

        - 随时以您的身份执行请求 (refresh_token，offline_access)  

    - 选中 " **需要 web 服务器流的密码** " 复选框。

    - 保存应用程序。
    
      ![Salesforce 实例中的 API 部分，管理员输入了上面列出的所有必需配置。](media/salesforce-connector/sf1.png)

- 复制使用者密钥和使用者密码。 当您在 Microsoft 365 管理门户中配置 Graph 连接器的连接设置时，这些设置将用作客户端 ID 和客户端密码。

  ![管理员提交所有必需的配置后，Salesforce 实例中的 API 部分返回的结果。 使用者密钥位于左列顶部，且使用者密码位于右列顶部。](media/salesforce-connector/clientsecret.png)
- 在关闭您的 Salesforce 实例之前，请执行以下步骤以确保刷新令牌不会过期： 
    - 转到应用程序-> 应用程序管理器
    - 查找刚创建的应用程序，然后选择右侧的下拉箭头。 选择 " **管理**
    - 选择 **编辑策略**
    - 对于 "刷新令牌" 策略，请选择 " **刷新令牌" 在废除前有效**

  ![选择名为 "刷新令牌在吊销前有效的刷新令牌策略"](media/salesforce-connector/oauthpolicies.png)

现在，您可以使用 [M365 管理中心](https://admin.microsoft.com/) 完成 Graph 连接器的其余设置过程。  

为您的 Graph 连接器配置连接设置，如下所示：

- 对于实例 URL，请使用 https：//[域]. 我的 .com，其中的域将成为您的组织的 Salesforce 域。 
- 输入你从 Salesforce 实例获取的客户端 ID 和客户端密码，并选择 "登录"。
- 如果这是你第一次尝试使用这些设置登录，你将看到一个弹出窗口，要求你使用管理员用户名和密码登录到 Salesforce。 下面的屏幕截图显示弹出窗口。 输入你的凭据，然后选择 "登录"。

  ![登录弹出窗口要求输入用户名和密码。](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >如果没有出现弹出窗口，则可能在浏览器中被阻止，因此您必须允许弹出窗口和重定向。

  >[!NOTE]
  >如果您的组织使用 (SSO) 的单一登录，则可以在登录接口的右下角选择 " **使用自** 定义域"。 输入域，然后选择 " **继续** "。 它将转到您的组织特定登录页，您可以在其中使用 SSO 登录选项。

- 通过在下面的屏幕截图中搜索显示 "连接成功" 的绿色标题，检查连接是否成功。

  ![成功登录的屏幕截图。 显示 "连接成功" 的绿色横幅位于您的 Salesforce 实例 URL 的字段下](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a>管理搜索权限
你将需要选择哪些用户将看到来自此数据源的搜索结果。 如果仅允许特定 Azure Active Directory (AAD) 或非 AAD 用户查看搜索结果，则需要映射这些标识。

### <a name="select-permissions"></a>选择权限
您可以选择从您的 Salesforce 实例中)  (Acl 中引入访问控制列表，也可以允许组织中的所有人查看此数据源中的搜索结果。 Acl 可以包含 Azure Active Directory (AAD) 标识、非 AAD 标识，也可以同时包含这两者。

![选择管理员已完成的 "权限" 屏幕。管理员已选择 "只有可访问此数据源的人员" 选项，并且还从 "标识类型" 的下拉菜单中选择了 "AAD"。](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a>映射非 AAD 标识 
如果你选择从 Salesforce 实例中引入 ACL 并为标识类型选择了 "非 AAD"，请参阅 [映射你的非 AZURE AD 标识 ](map-non-aad.md) ，了解有关标识标识的说明。

### <a name="map-aad-identities"></a>映射 AAD 标识
如果你选择从 Salesforce 实例中引入 ACL 并为标识类型选择了 "AAD"，请参阅 [映射 AZURE AD 标识](map-aad.md) 以获取有关映射标识的说明。

## <a name="assign-property-labels"></a>分配属性标签 
通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。 虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。 默认情况下，某些标签（如 "Title"、"url" 和 "LastModifiedBy"）已分配了源属性。

![分配显示默认源属性的属性标签屏幕。](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a>管理架构
您可以选择应为其编制索引的源属性，以便它们可以显示在搜索结果中。 默认情况下，连接向导根据一组源属性选择一个搜索架构。 您可以通过选中 "搜索架构" 页中每个属性和属性的复选框对其进行修改。 搜索架构属性包括搜索、查询、检索和优化。 优化允许您定义可在以后用作搜索体验中的自定义精简条件或筛选器的属性。  

![为每个 source 属性选择架构。 选项包括查询、搜索、检索和优化](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a>设置刷新计划

Salesforce 连接器仅支持当前完全爬网的刷新计划。

>[!IMPORTANT]
>完全爬网可查找以前同步到 Microsoft 搜索索引的已删除对象和用户。

建议的日程安排为一周完全爬网。

## <a name="limitations"></a>限制

- Graph 连接器目前不支持基于区域的共享和使用 Salesforce 中的个人组共享基于区域的共享和共享 Apex。
- 在 Salesforce API 中存在一个已知的错误，图连接器使用的是潜在客户的专用组织范围默认值在当前未生效的情况。  
- 如果字段具有字段级安全性 (FLS) 设置配置文件，Graph 连接器将不会为该 Salesforce 组织中的任何配置文件摄取该字段。因此，用户将无法搜索这些域的值，也不会显示在结果中。  
- 在完全同步连接器的过程中，将会接受任何设置的 FLS。
- 在 "管理架构" 屏幕中，这些常用的标准属性名称列出一次，所做的选择使其可查询、搜索和检索适用于所有或无。
    - 名称
    - URL 
    - 说明
    - Fax
    - 电话版
    - MobilePhone
    - 电子邮件
    - 类型
    - 标题
    - AccountId
    - AccountName
    - AccountUrl
    - AccountOwner
    - AccountOwnerUrl
    - 所有者
    - OwnerUrl
    - CreatedBy 
    - CreatedByUrl 
    - LastModifiedBy 
    - LastModifiedByUrl 
    - LastModifiedDate
    - ObjectName 
