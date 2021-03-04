---
title: 适用于 Microsoft 搜索的企业网站 Graph 连接器
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
description: 为 Microsoft 搜索设置企业网站图形连接器
ms.openlocfilehash: 7d71e6e3d775c97d8916e20ab032c312c269c5f1
ms.sourcegitcommit: 6a7522d9aeaedeedaac096c485d3f343ce98d3d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421096"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a>企业网站 Graph 连接器

企业网站 Graph 连接器允许组织从面向内部的网站索引 **文章和内容**。 配置连接器并同步网站内容后，最终用户可以从任何 Microsoft 搜索客户端搜索该内容。

> [!NOTE]
> 阅读 [**"设置 Graph 连接器"**](configure-connector.md) 文章，了解一般的 Graph 连接器设置过程。

本文适用于配置、运行和监视企业网站连接器的任何人。 它补充了常规安装过程，并显示了仅适用于企业网站连接器的说明。 本文还包括有关疑[难解答和](#troubleshooting)[限制的信息](#limitations)。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

若要连接到数据源，您需要填写网站的根 URL、选择爬网源以及要使用身份验证的类型：无、基本身份验证或使用 [Azure Active Directory (Azure AD) ](https://docs.microsoft.com/azure/active-directory/)的 OAuth 2.0。 完成此信息后，选择"测试连接"以验证设置。

> [!NOTE]
> 如果要爬网的网站定义了站点地图，则连接器将仅对网站地图中列出的 URL 进行爬网。 如果未定义站点图，连接器将深入爬网在网站的根 URL 上找到的所有链接。

### <a name="url"></a>URL

使用 URL 字段指定要爬网的网站的根。 企业网站连接器将使用此 URL 作为起点，并按照此 URL 的所有链接进行爬网。

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>爬网模式：云或本地 (预览) 

爬网模式确定要索引的网站类型（云或本地）。 对于云网站，选择 **"云** "作为爬网模式。

此外，连接器现在支持对本地网站进行爬网。 此模式为预览模式。 若要访问本地数据，必须先安装和配置 Graph 连接器代理。 若要了解更多信息，请参阅 [Graph 连接器代理](https://docs.microsoft.com/microsoftsearch/on-prem-agent)。

对于本地网站，选择 **代理作为爬网** 模式，在"本地代理"字段中，选择之前安装和配置的 Graph 连接器代理。  

> [!div class="mx-imgBorder"]
> ![企业 Web 连接器的连接设置窗格屏幕截图](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>身份验证

基本身份验证需要用户名和密码。 使用 [Microsoft 365](https://admin.microsoft.com)管理中心创建此机器人帐户。

使用 Azure AD 的 [OAuth](https://docs.microsoft.com/azure/active-directory/) 2.0 需要资源 ID、客户端 ID 和客户端密码。 OAuth 2.0 仅适用于云模式。

有关详细信息，请参阅授权 [使用 OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)代码授予流访问 Azure Active Directory Web 应用程序。 注册以下值：

**名称：** Microsoft 搜索 <br/>
**Redirect_URI：**`https://gcs.office.com/v1.0/admin/oauth/callback`

若要获取资源、client_id和client_secret的值，请转到使用授权代码请求重定向 URL **网页上的访问** 令牌。

有关详细信息，请参阅快速 [入门：使用 Microsoft 标识平台注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a>步骤 3a：添加 URL 以排除 (可选的爬网限制) 

有两种方法可阻止对页面进行爬网：禁止在robots.txt或将其添加到排除列表中。

### <a name="support-for-robotstxt"></a>支持robots.txt

连接器检查根网站是否有robots.txt文件，如果存在，它将遵循并遵循该文件中提供的方向。 如果您不希望连接器对网站上的某些页面或目录进行爬网，可以在您的 robots.txt 文件中调用这些页面或目录。

### <a name="add-urls-to-exclude"></a>添加要排除的 URL

可以选择创建排除列表，以在内容敏感或值得爬网时排除某些 URL 进行爬网。 若要创建排除列表，请浏览根 URL。 您可以在配置过程中将排除的 URL 添加到列表中。

## <a name="step-4-assign-property-labels"></a>步骤 4：分配属性标签

可以通过从选项菜单中选择来为每个标签分配源属性。 虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更准确的搜索结果。

## <a name="step-5-manage-schema"></a>步骤 5：管理架构

在"管理架构"屏幕上，可以更改架构属性 (选项为"查询"、"搜索"、"检索"和"精简 **")** 与属性关联，添加可选别名，然后选择 **"内容**"属性。 

## <a name="step-6-manage-search-permissions"></a>步骤 6：管理搜索权限

企业网站连接器仅支持对所有人可见的搜索 **权限**。 索引数据将显示在搜索结果中，并且对组织中的所有用户可见。

## <a name="step-7-set-the-refresh-schedule"></a>步骤 7：设置刷新计划

企业网站连接器仅支持完全刷新。 这意味着连接器将在每次刷新期间重新对网站的所有内容进行重新对接。 若要确保连接器有足够的时间对内容进行爬网，建议您设置较大的刷新计划间隔。 我们建议在一到两周之间计划刷新。

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>疑难解答

在读取网站内容时，爬网可能会遇到一些源错误，这些错误由下面的详细错误代码表示。 若要获取有关错误类型的详细信息，请转到选择连接后的错误详细信息页。 选择 **错误代码** 以查看更详细的错误。 另请参阅 ["管理连接器"](https://docs.microsoft.com/microsoftsearch/manage-connector) 了解详情。

 详细错误代码 | 错误消息
 --- | ---
 6001 | 尝试编制索引的网站不可访问
 6005 | 尝试编制索引的源页已按配置robots.txt阻止。
 6008 | 无法解析 DNS
 6009 | 对于除 HTTP 404 (408) 之外的所有客户端错误，请参阅 HTTP 4xx 错误代码了解详细信息。
 6013 | 找不到尝试编制索引的源页。  (HTTP 404 错误) 
 6018 | 源页面未响应，并且请求已退出。 (HTTP 408 错误) 
 6021 | 尝试编制索引的源页面在页面上没有文本内容。
 6023 | 尝试编制索引的源页不受支持， (HTML 页面) 
 6024 | 尝试编制索引的源页包含的内容不受支持。

* 错误 6001-6013 在数据源因网络问题而不可访问或数据源本身被删除、移动或重命名时发生。 检查提供的数据源详细信息是否仍然有效。
* 当数据源包含页面上的非文本内容或页面不是 HTML 时，将发生错误 6021-6024。 检查数据源，将此页面添加到排除列表中或忽略错误。

## <a name="limitations"></a>限制

企业网站连接器不支持在动态网页上 **搜索数据**。 这些网页的示例存储在内容管理系统（如 [Confluence](https://www.atlassian.com/software/confluence) 和 [Unily）](https://www.unily.com/) 或存储网站内容的数据库中。