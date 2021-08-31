---
title: Enterprise网站Graph连接器Microsoft 搜索
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
description: 设置 Enterprise 网站Graph连接器Microsoft 搜索
ms.openlocfilehash: 2be52bc83718c2450ad91444a6176f5f63c03890
ms.sourcegitcommit: e5d56d6ce1cd285c5af3e0472ce169cb34883017
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2021
ms.locfileid: "58469975"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a>Enterprise连接器Graph网站

the Enterprise websites Graph connector allows your organization to index articles and **content from its internal-facing websites**. 配置连接器并同步网站内容后，最终用户可以从任何客户端搜索Microsoft 搜索内容。

> [!NOTE]
> 阅读 [**Setup your Graph connector**](configure-connector.md)一文，了解 Graph连接器的一般设置说明。

本文适用于配置、运行和监视 Enterprise连接器的任何人。 它补充了常规设置过程，并显示了仅适用于 Enterprise 连接器的说明。 本文还包括有关疑难 [解答的信息](#troubleshooting)。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在Graph中添加Microsoft 365 管理中心

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

若要连接到数据源，请填写网站的根 URL，选择爬网源和你要使用的身份验证类型：无、基本身份验证或[包含 Azure Active Directory (Azure AD) ](/azure/active-directory/)的 OAuth 2.0。 完成此信息后，选择"测试连接"以验证设置。

### <a name="url"></a>URL

使用 URL 字段指定要爬网的网站的根。 企业网站连接器将使用此 URL 作为起点，并按照此 URL 的所有链接进行爬网。

### <a name="crawl-websites-listed-in-the-sitemap"></a>对网站地图中列出的网站进行爬网

选择后，连接器将仅对网站地图中列出的 URL 进行爬网。 如果未选择或未找到站点地图，连接器将深入爬网在网站的根 URL 上找到的所有链接。

### <a name="dynamic-site-configuration"></a>动态网站配置

如果您的网站包含动态内容（例如，内容管理系统（如 Confluence 或 Unily）中的网页，您可以启用动态爬网程序。 若要将其打开，请选择"**为动态网站启用爬网"。** 爬网程序将等待动态内容呈现，然后再开始爬网。

> [!div class="mx-imgBorder"]
> ![Web 连接器设置连接Enterprise屏幕截图。](media/enterprise-web-connector/connectors-enterpriseweb-connectionsettings-dynamicconfig-small.png)

除了该复选框之外，还有三个可选字段可用：

1. **DOM Ready：** 输入爬网程序应用作内容已完全呈现且应开始爬网的信号的 DOM 元素。
1. **要添加的标头**：指定在发送特定 Web URL 时爬网程序应包含的 HTTP 标头。 您可以为不同的网站设置多个标头。 我们建议包括身份验证令牌值。
1. **要跳过的标题**：指定应从动态爬网请求中排除的任何不必要的标头。

> [!NOTE]
> 动态爬网仅受代理爬网模式支持。

### <a name="crawl-mode-cloud-or-on-premises"></a>爬网模式：云或本地

爬网模式确定要索引的网站类型（云或本地）。 对于云网站，选择 **"云** "作为爬网模式。

此外，连接器现在支持对本地网站进行爬网。 若要访问本地数据，必须先安装和配置 Graph 连接器代理。 若要了解更多信息，请参阅[Graph代理](./graph-connector-agent.md)。

对于本地网站，选择"代理"作为爬网模式，在"本地代理"字段中，选择之前安装和配置的 Graph 连接器代理。  

### <a name="authentication"></a>身份验证

基本身份验证需要用户名和密码。 使用帐户创建此自动程序[Microsoft 365 管理中心。](https://admin.microsoft.com)

具有 [Azure AD](/azure/active-directory/) 的 OAuth 2.0 需要资源 ID、客户端 ID 和客户端密码。 OAuth 2.0 仅适用于云模式。

有关详细信息，请参阅使用[OAuth 2.0 代码Azure Active Directory授权访问 Web](/azure/active-directory/develop/v1-protocols-oauth-code)应用程序。 注册以下值：

**名称：Microsoft 搜索** <br/>
**Redirect_URI：**`https://gcs.office.com/v1.0/admin/oauth/callback`

若要获取资源、client_id 和 client_secret 的值，请转到使用授权代码请求重定向 URL **网页上的访问** 令牌。

有关详细信息，请参阅快速入门[：向应用程序注册Microsoft 标识平台。](/azure/active-directory/develop/quickstart-register-app)

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a>步骤 3a：添加 URL 以排除 (可选的爬网限制) 

有两种方法可阻止对页面进行爬网：禁止在 robots.txt 文件中对页面进行爬网或将其添加到排除列表。

### <a name="support-for-robotstxt"></a>支持robots.txt

连接器检查根网站是否存在robots.txt文件，如果存在，它将遵循并遵循该文件中的说明。 如果您不希望连接器对网站中的某些页面或目录进行爬网，可以在您的 robots.txt 文件中在"禁止"声明中调用这些页面或目录。

### <a name="add-urls-to-exclude"></a>添加要排除的 URL

您可以选择创建排除列表，以在内容敏感或值得爬网时排除某些 URL 进行爬网。 若要创建排除列表，请浏览根 URL。 您可以在配置过程中将排除的 URL 添加到列表中。

## <a name="step-4-assign-property-labels"></a>步骤 4：分配属性标签

可以通过从选项菜单中选择来为每个标签分配源属性。 虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更准确的搜索结果。

## <a name="step-5-manage-schema"></a>步骤 5：管理架构

在"管理架构"屏幕上，可以更改架构属性 (选项为"查询、搜索、检索"和"精简) 这些属性关联，添加可选别名，然后选择 **"内容**"属性。

## <a name="step-6-manage-search-permissions"></a>步骤 6：管理搜索权限

the Enterprise websites connector only supports search permissions visible to **Everyone**. 索引数据将显示在搜索结果中，并且对组织中所有用户可见。

## <a name="step-7-set-the-refresh-schedule"></a>步骤 7：设置刷新计划

Enterprise网站连接器仅支持完全刷新。 这意味着连接器将在每次刷新过程中对网站的所有内容重新进行crawl。 若要确保连接器有足够的时间对内容进行爬网，建议您设置一个大型刷新计划间隔。 我们建议在一到两周之间计划刷新。

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>疑难解答

在读取网站内容时，爬网可能会遇到一些源错误，这些错误由下面的详细错误代码表示。 若要获取有关错误类型的详细信息，请转到选择连接后 **的错误** 详细信息页面。 选择 **错误代码** 以查看更详细的错误。 另请参阅 [管理连接器以了解](./manage-connector.md) 详情。

 详细错误代码 | 错误消息
 --- | ---
 6001 | 尝试编制索引的网站不可访问
 6005 | 尝试编制索引的源页已根据配置robots.txt阻止。
 6008 | 无法解析 DNS
 6009 | 对于除 HTTP 404 (408) 之外的所有客户端错误，请参阅 HTTP 4xx 错误代码了解详细信息。
 6013 | 找不到尝试编制索引的源页。  (HTTP 404 错误) 
 6018 | 源页面未响应，并且请求已退出。 (HTTP 408 错误) 
 6021 | 试图编制索引的源页面在页面上没有文本内容。
 6023 | 尝试编制索引的源页不受支持， (HTML 页面) 
 6024 | 试图编制索引的源页包含的内容不受支持。

* 错误 6001-6013 在数据源因网络问题而不可访问时发生，或者数据源本身被删除、移动或重命名时发生。 检查提供的数据源详细信息是否仍然有效。
* 当数据源包含页面上的非文本内容或页面不是 HTML 时，将发生错误 6021-6024。 检查数据源，在排除列表中添加此页面或忽略错误。
