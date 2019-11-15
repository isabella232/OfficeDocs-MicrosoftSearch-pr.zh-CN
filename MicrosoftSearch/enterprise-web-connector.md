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
ms.openlocfilehash: c2495487b24b11512a182434f72a90044a439d5d
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626270"
---
# <a name="enterprise-websites-connector"></a><span data-ttu-id="6b061-103">企业网站连接器</span><span class="sxs-lookup"><span data-stu-id="6b061-103">Enterprise websites connector</span></span>

<span data-ttu-id="6b061-104">通过企业网站连接器，您的组织可以**从其面向内部的网站中**索引文章和内容。</span><span class="sxs-lookup"><span data-stu-id="6b061-104">With the Enterprise websites connector, your organization can index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="6b061-105">在配置了该网站的连接器和同步内容之后，最终用户可以从任何 Microsoft 搜索客户端搜索该内容。</span><span class="sxs-lookup"><span data-stu-id="6b061-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

<span data-ttu-id="6b061-106">本文适用于 Microsoft 365 管理员或任何配置、运行和监视企业网站连接器的人。</span><span class="sxs-lookup"><span data-stu-id="6b061-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="6b061-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="6b061-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="6b061-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="6b061-108">Connect to a data source</span></span> 
<span data-ttu-id="6b061-109">若要连接到数据源，您需要根 URL 和身份验证形式（基本身份验证或使用 Azure AD 的 OAuth 2.0）。</span><span class="sxs-lookup"><span data-stu-id="6b061-109">To connect to your data source, you need your root URL and a form of authentication (Basic Authentication or OAuth 2.0 with Azure AD).</span></span>

### <a name="root-url"></a><span data-ttu-id="6b061-110">根 URL</span><span class="sxs-lookup"><span data-stu-id="6b061-110">Root URL</span></span>
<span data-ttu-id="6b061-111">根 URL 是启动爬网并用于身份验证的。</span><span class="sxs-lookup"><span data-stu-id="6b061-111">The root URL is what initiates the crawl and is used for authentication.</span></span> <span data-ttu-id="6b061-112">您可以从要对其进行爬网的网站的主页中获取 URL。</span><span class="sxs-lookup"><span data-stu-id="6b061-112">You can get the URL from the home page of the website you want to crawl.</span></span>

### <a name="authentication"></a><span data-ttu-id="6b061-113">身份验证</span><span class="sxs-lookup"><span data-stu-id="6b061-113">Authentication</span></span> 
<span data-ttu-id="6b061-114">基本身份验证需要用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="6b061-114">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="6b061-115">使用[Microsoft 365 管理中心](https://admin.microsoft.com)创建此 bot 帐户。</span><span class="sxs-lookup"><span data-stu-id="6b061-115">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="6b061-116">使用 Azure AD 的 OAuth 2.0 需要租户 ID、资源 ID、客户端 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="6b061-116">OAuth 2.0 with Azure AD requires a tenant ID, resource ID, Client ID, and Client Secret.</span></span>
<span data-ttu-id="6b061-117">有关详细信息，请参阅[使用 OAuth 2.0 代码授予流授予对 Azure Active Directory web 应用程序的访问权限](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="6b061-117">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="6b061-118">使用以下值注册：</span><span class="sxs-lookup"><span data-stu-id="6b061-118">Register with the following values:</span></span>
* <span data-ttu-id="6b061-119">**名称：** Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="6b061-119">**Name:** Microsoft Search</span></span>
* <span data-ttu-id="6b061-120">**Redirect_URI：**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="6b061-120">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="6b061-121">若要获取命名的租户、资源、client_id 和 client_secret 的值，请转到**使用授权代码请求**重定向 URL 网页上的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="6b061-121">To get the values for named tenant, resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="6b061-122">有关更多详细信息，请参阅[快速入门：使用 Microsoft identity Platform 注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="6b061-122">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

### <a name="reverse-proxy-url"></a><span data-ttu-id="6b061-123">反向代理 URL</span><span class="sxs-lookup"><span data-stu-id="6b061-123">Reverse proxy URL</span></span> 
<span data-ttu-id="6b061-124">企业网站连接器是基于云的，因此它不会访问本地内容。</span><span class="sxs-lookup"><span data-stu-id="6b061-124">The Enterprise websites connector is cloud-based, so it doesn't access on-premises content.</span></span> <span data-ttu-id="6b061-125">若要提供此访问权限，请安装反向代理。</span><span class="sxs-lookup"><span data-stu-id="6b061-125">To provide that access, install a reverse proxy.</span></span> <span data-ttu-id="6b061-126">反向代理提供对本地网站的安全、可靠的访问。</span><span class="sxs-lookup"><span data-stu-id="6b061-126">A reverse proxy provides secure, reliable access to on-premises websites.</span></span> <span data-ttu-id="6b061-127">建议采用 Azure 应用程序代理（AAP）。</span><span class="sxs-lookup"><span data-stu-id="6b061-127">We recommend Azure Application Proxy (AAP).</span></span>

<span data-ttu-id="6b061-128">根 URL 和身份验证的反向代理要求与基于云的内容相同，不同之处在于根 URL 和身份验证由反向代理服务器提供。</span><span class="sxs-lookup"><span data-stu-id="6b061-128">The reverse proxy requirement for root URL and authentication is the same as for cloud-based content except that the root URL and authentication are provided by the reverse proxy server.</span></span>

<span data-ttu-id="6b061-129">有关[使用 AZURE AD 应用程序代理远程访问应用程序的安全注意事项，](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security)请参阅。</span><span class="sxs-lookup"><span data-stu-id="6b061-129">See [Security considerations for accessing apps remotely with Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).</span></span>

## <a name="select-the-source-properties"></a><span data-ttu-id="6b061-130">选择源属性</span><span class="sxs-lookup"><span data-stu-id="6b061-130">Select the source properties</span></span> 
<span data-ttu-id="6b061-131">根据企业网站的数据格式定义源属性。</span><span class="sxs-lookup"><span data-stu-id="6b061-131">Source properties are defined based on the data format of the enterprise website.</span></span> <span data-ttu-id="6b061-132">但是，您可以创建**排除列表**，以排除某些 url 的爬网，因为该内容可能是敏感的，也可能不值得爬网。</span><span class="sxs-lookup"><span data-stu-id="6b061-132">However you can create an **Exclusion list** to exclude some URLs from getting crawled since that content might be sensitive or not worth crawling.</span></span> <span data-ttu-id="6b061-133">若要创建排除列表，请浏览根 URL。</span><span class="sxs-lookup"><span data-stu-id="6b061-133">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="6b061-134">您可以选择在配置过程中将排除的 Url 添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="6b061-134">You have the option to add the excluded URLs to the list during the configuration process.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="6b061-135">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="6b061-135">Manage search permissions</span></span> 
<span data-ttu-id="6b061-136">不支持访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="6b061-136">There is no support for Access Control Lists (ACLs).</span></span> <span data-ttu-id="6b061-137">因此，建议仅将对组织中任何用户可见的网站进行连接。</span><span class="sxs-lookup"><span data-stu-id="6b061-137">Thus, it is advised to connect only the websites that are visible to any user within your organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="6b061-138">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="6b061-138">Set the refresh schedule</span></span>
<span data-ttu-id="6b061-139">企业网站连接器仅支持完全爬网。</span><span class="sxs-lookup"><span data-stu-id="6b061-139">The Enterprise websites connector only supports a full crawl.</span></span> <span data-ttu-id="6b061-140">这意味着，在每次爬网期间，连接器都会读取网站的所有内容。</span><span class="sxs-lookup"><span data-stu-id="6b061-140">This means that the connector reads all the website's content during every crawl.</span></span> <span data-ttu-id="6b061-141">若要确保连接器获取足够的时间来读取内容，建议设置较大的刷新计划间隔。</span><span class="sxs-lookup"><span data-stu-id="6b061-141">To make sure the connector gets enough time to read the content, it is recommended to set a large refresh schedule interval.</span></span> <span data-ttu-id="6b061-142">建议在三天和两周之间计划刷新。</span><span class="sxs-lookup"><span data-stu-id="6b061-142">We recommend a scheduled refresh between three days and two weeks.</span></span>

## <a name="limitations"></a><span data-ttu-id="6b061-143">限制</span><span class="sxs-lookup"><span data-stu-id="6b061-143">Limitations</span></span> 
<span data-ttu-id="6b061-144">企业网站连接器不支持搜索动态网页上的数据。</span><span class="sxs-lookup"><span data-stu-id="6b061-144">The Enterprise websites connector doesn't support searching data on dynamic webpages.</span></span> <span data-ttu-id="6b061-145">这些网页的示例如 Confluence 和 Unily 之类的内容管理系统中所示，或存储网站内容的数据库。</span><span class="sxs-lookup"><span data-stu-id="6b061-145">Examples of those webpages live in content management systems like Confluence and Unily or databases that store website content.</span></span>