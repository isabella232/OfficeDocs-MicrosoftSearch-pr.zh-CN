---
title: Microsoft 搜索的企业网站连接器
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置企业网站连接器以进行 Microsoft Search
ms.openlocfilehash: 4fb80ce4e3dbc77638e3b7db9c2ebd3c39d5a6d8
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422952"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a>企业网站连接器

通过企业网站连接器，您的组织可以 **从其面向内部的网站中**索引文章和内容。 在配置了该网站的连接器和同步内容之后，最终用户可以从任何 Microsoft 搜索客户端搜索该内容。

本文适用于 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理员或任何配置、运行和监视企业网站连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。  

## <a name="connect-to-a-data-source"></a>连接到数据源

若要连接到数据源，您需要根 URL 和一种形式的身份验证：无、基本身份验证或使用 [Azure Active Directory (AZURE AD) ](https://docs.microsoft.com/azure/active-directory/)的 OAuth 2.0。

### <a name="authentication"></a>身份验证

基本身份验证需要用户名和密码。 使用 [Microsoft 365 管理中心](https://admin.microsoft.com)创建此 bot 帐户。

使用 [AZURE AD](https://docs.microsoft.com/azure/active-directory/) 的 OAuth 2.0 需要资源 ID、客户端 ID 和客户端密码。

有关详细信息，请参阅 [使用 OAuth 2.0 代码授予流授予对 Azure Active Directory web 应用程序的访问权限](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)。 使用以下值注册：

**名称：** Microsoft Search <br/>
**Redirect_URI：**`https://gcs.office.com/v1.0/admin/oauth/callback`

若要获取资源、client_id 和 client_secret 的值，请转到 **使用授权代码请求** 重定向 URL 网页上的访问令牌。

有关更多详细信息，请参阅 [快速入门：使用 Microsoft identity Platform 注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。

### <a name="root-url"></a>根 URL

根 URL 是启动爬网并用于身份验证的。 您可以从要对其进行爬网的网站的主页中获取 URL。

## <a name="select-the-source-properties"></a>选择源属性

根据企业网站的数据格式定义源属性。 但是，如果内容是敏感的或不值得爬网，则可以创建 **排除列表** ，以排除某些 url 的爬网。 若要创建排除列表，请浏览根 URL。 您可以选择在配置过程中将排除的 Url 添加到列表中。

## <a name="manage-search-permissions"></a>管理搜索权限

 (Acl) 不支持访问控制列表。 因此，我们建议只将对组织中任何用户可见的网站进行连接。

## <a name="set-the-refresh-schedule"></a>设置刷新计划

企业网站连接器仅支持完全爬网。 这意味着，在每次爬网期间，连接器都会读取网站的所有内容。 若要确保连接器获取足够的时间来读取内容，我们建议您设置一个较大的刷新计划间隔。 建议在一到两周之间进行计划刷新。

## <a name="troubleshooting"></a>故障排除

阅读网站的内容时，爬网可能会遇到下面的详细错误代码所表示的一些源错误。 若要获取有关错误类型的详细信息，请在选择该连接后转到 " **错误详细** 信息" 页。 单击 **错误代码** 以查看更多详细错误。 此外，请参阅 [管理连接器](https://docs.microsoft.com/microsoftsearch/manage-connector) 以了解详细信息。

 详细错误代码 | 错误消息
 --- | ---
 6001 | 尝试建立索引的网站不可访问
 6005 | 根据 robots.txt 配置，要尝试索引的源页面已被阻止。
 6008 | 无法解析 DNS
 6009 | 对于除 HTTP 404、408) 之外的所有客户端错误 (，请参阅 HTTP 4xx 错误代码了解详细信息。
 6013 | 找不到要尝试索引的源页面。  (HTTP 404 错误) 
 6018 | 源页面未响应，且请求已超时。 (HTTP 408 错误) 
 6021 | 要尝试编制索引的源页面在页面上没有文本内容。
 6023 | 不支持要尝试编制索引的源页面， (不是 HTML 页面) 
 6024 | 尝试索引的源页面包含不受支持的内容。

* 当数据源由于网络问题或数据源本身被删除、移动或重命名而无法访问时，将发生错误6001-6013。 检查提供的数据源详细信息是否仍然有效。
* 如果数据源在页面上包含非文本内容或页面不是 HTML，则会出现错误6021-6024 错误。 请检查数据源并在排除列表中添加此页面或忽略错误。

## <a name="limitations"></a>限制

企业网站连接器不支持搜索 **动态网页**上的数据。 这些网页的示例如 [Confluence](https://www.atlassian.com/software/confluence) 和 [Unily](https://www.unily.com/) 之类的内容管理系统中所示，或存储网站内容的数据库。
