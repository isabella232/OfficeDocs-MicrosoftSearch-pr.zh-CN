---
title: Microsoft 搜索的企业网站连接器
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置企业网站连接器以进行 Microsoft Search
ms.openlocfilehash: 14eef035f4cc054ab87582b573cb6b7e3c12d0c7
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699518"
---
# <a name="enterprise-websites-connector"></a>企业网站连接器

通过企业网站连接器，您的组织可以**从其面向内部的网站中**索引文章和内容。 在配置了该网站的连接器和同步内容之后，最终用户可以从任何 Microsoft 搜索客户端搜索该内容。

本文适用于[Microsoft 365](https://www.microsoft.com/microsoft-365)管理员或任何配置、运行和监视企业网站连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。  

## <a name="connect-to-a-data-source"></a>连接到数据源 
若要连接到数据源，您需要根 URL 和一种身份验证形式：基本身份验证或使用[Azure Active Directory （AZURE AD）](https://docs.microsoft.com/azure/active-directory/)的 OAuth 2.0。

### <a name="root-url"></a>根 URL
根 URL 是启动爬网并用于身份验证的。 您可以从要对其进行爬网的网站的主页中获取 URL。

### <a name="authentication"></a>身份验证 
基本身份验证需要用户名和密码。 使用 Microsoft 365[管理中心](https://admin.microsoft.com)创建此 bot 帐户。

使用[AZURE AD](https://docs.microsoft.com/azure/active-directory/)的 OAuth 2.0 需要租户 ID、资源 ID、客户端 ID 和客户端密码。
有关详细信息，请参阅[使用 OAuth 2.0 代码授予流授予对 Azure Active Directory web 应用程序的访问权限](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)。 使用以下值注册：
* **名称：** Microsoft Search
* **Redirect_URI：**`https://gcs.office.com/v1.0/admin/oauth/callback`

若要获取命名的租户、资源、client_id 和 client_secret 的值，请转到**使用授权代码请求**重定向 URL 网页上的访问令牌。

有关更多详细信息，请参阅[快速入门：使用 Microsoft identity Platform 注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。

### <a name="reverse-proxy-url"></a>反向代理 URL 
企业网站连接器是基于云的，因此它不会访问本地内容。 若要提供此访问权限，请安装反向代理。 反向代理提供对本地网站的安全、可靠的访问。 我们建议[Azure 应用程序代理](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。

根 URL 和身份验证的反向代理要求与基于云的内容相同，不同之处在于根 URL 和身份验证由反向代理服务器提供。

有关[使用 AZURE AD 应用程序代理远程访问应用程序的安全注意事项，](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security)请参阅。

## <a name="select-the-source-properties"></a>选择源属性 
根据企业网站的数据格式定义源属性。 但是，如果内容是敏感的或不值得爬网，则可以创建**排除列表**，以排除某些 url 的爬网。 若要创建排除列表，请浏览根 URL。 您可以选择在配置过程中将排除的 Url 添加到列表中。

## <a name="manage-search-permissions"></a>管理搜索权限 
不支持访问控制列表（Acl）。 因此，我们建议只将对组织中任何用户可见的网站进行连接。

## <a name="set-the-refresh-schedule"></a>设置刷新计划
企业网站连接器仅支持完全爬网。 这意味着，在每次爬网期间，连接器都会读取网站的所有内容。 若要确保连接器获取足够的时间来读取内容，我们建议您设置一个较大的刷新计划间隔。 建议在三天和两周之间计划刷新。

## <a name="limitations"></a>限制 
企业网站连接器不支持搜索动态网页上的数据。 这些网页的示例如[Confluence](https://www.atlassian.com/software/confluence)和[Unily](https://www.unily.com/)之类的内容管理系统中所示，或存储网站内容的数据库。