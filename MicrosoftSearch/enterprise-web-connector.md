---
title: Microsoft 搜索的企业网站连接器
ms.author: monaray
author: monaray97
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
ms.openlocfilehash: b4d9f837892bcfd795421530e0571fa0509a2761
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206938"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a><span data-ttu-id="c7bd1-103">企业网站连接器</span><span class="sxs-lookup"><span data-stu-id="c7bd1-103">Enterprise websites connector</span></span>

<span data-ttu-id="c7bd1-104">通过企业网站连接器，您的组织可以 **从其面向内部的网站中**索引文章和内容。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-104">With the Enterprise websites connector, your organization can index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="c7bd1-105">在配置了该网站的连接器和同步内容之后，最终用户可以从任何 Microsoft 搜索客户端搜索该内容。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

<span data-ttu-id="c7bd1-106">本文适用于 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理员或任何配置、运行和监视企业网站连接器的人。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="c7bd1-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="c7bd1-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="c7bd1-108">Connect to a data source</span></span>

<span data-ttu-id="c7bd1-109">若要连接到数据源，您需要根 URL 和一种形式的身份验证：无、基本身份验证或使用 [Azure Active Directory (AZURE AD) ](https://docs.microsoft.com/azure/active-directory/)的 OAuth 2.0。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-109">To connect to your data source, you need your root URL and a form of authentication: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).</span></span>

### <a name="authentication"></a><span data-ttu-id="c7bd1-110">身份验证</span><span class="sxs-lookup"><span data-stu-id="c7bd1-110">Authentication</span></span>

<span data-ttu-id="c7bd1-111">基本身份验证需要用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-111">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="c7bd1-112">使用 [Microsoft 365 管理中心](https://admin.microsoft.com)创建此 bot 帐户。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-112">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="c7bd1-113">使用 [AZURE AD](https://docs.microsoft.com/azure/active-directory/) 的 OAuth 2.0 需要资源 ID、客户端 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-113">OAuth 2.0 with [Azure AD](https://docs.microsoft.com/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span>

<span data-ttu-id="c7bd1-114">有关详细信息，请参阅 [使用 OAuth 2.0 代码授予流授予对 Azure Active Directory web 应用程序的访问权限](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-114">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="c7bd1-115">使用以下值注册：</span><span class="sxs-lookup"><span data-stu-id="c7bd1-115">Register with the following values:</span></span>

<span data-ttu-id="c7bd1-116">**名称：** Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="c7bd1-116">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="c7bd1-117">**Redirect_URI：**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="c7bd1-117">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="c7bd1-118">若要获取资源、client_id 和 client_secret 的值，请转到 **使用授权代码请求** 重定向 URL 网页上的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-118">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="c7bd1-119">有关更多详细信息，请参阅 [快速入门：使用 Microsoft identity Platform 注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-119">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

### <a name="root-url"></a><span data-ttu-id="c7bd1-120">根 URL</span><span class="sxs-lookup"><span data-stu-id="c7bd1-120">Root URL</span></span>

<span data-ttu-id="c7bd1-121">根 URL 是启动爬网并用于身份验证的。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-121">The root URL is what initiates the crawl and is used for authentication.</span></span> <span data-ttu-id="c7bd1-122">您可以从要对其进行爬网的网站的主页中获取 URL。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-122">You can get the URL from the home page of the website you want to crawl.</span></span>

## <a name="select-the-source-properties"></a><span data-ttu-id="c7bd1-123">选择源属性</span><span class="sxs-lookup"><span data-stu-id="c7bd1-123">Select the source properties</span></span>

<span data-ttu-id="c7bd1-124">根据企业网站的数据格式定义源属性。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-124">Source properties are defined based on the data format of the enterprise website.</span></span> <span data-ttu-id="c7bd1-125">但是，如果内容是敏感的或不值得爬网，则可以创建 **排除列表** ，以排除某些 url 的爬网。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-125">However, you can create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="c7bd1-126">若要创建排除列表，请浏览根 URL。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-126">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="c7bd1-127">您可以选择在配置过程中将排除的 Url 添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-127">You have the option to add the excluded URLs to the list during the configuration process.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="c7bd1-128">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="c7bd1-128">Manage search permissions</span></span>

<span data-ttu-id="c7bd1-129"> (Acl) 不支持访问控制列表。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-129">There's no support for Access Control Lists (ACLs).</span></span> <span data-ttu-id="c7bd1-130">因此，我们建议只将对组织中任何用户可见的网站进行连接。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-130">Thus, we recommend connecting only the websites that are visible to any user within your organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="c7bd1-131">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="c7bd1-131">Set the refresh schedule</span></span>

<span data-ttu-id="c7bd1-132">企业网站连接器仅支持完全爬网。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-132">The Enterprise websites connector only supports a full crawl.</span></span> <span data-ttu-id="c7bd1-133">这意味着，在每次爬网期间，连接器都会读取网站的所有内容。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-133">This means that the connector reads all the website's content during every crawl.</span></span> <span data-ttu-id="c7bd1-134">若要确保连接器获取足够的时间来读取内容，我们建议您设置一个较大的刷新计划间隔。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-134">To make sure the connector gets enough time to read the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="c7bd1-135">建议在一到两周之间进行计划刷新。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-135">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c7bd1-136">故障排除</span><span class="sxs-lookup"><span data-stu-id="c7bd1-136">Troubleshooting</span></span>

<span data-ttu-id="c7bd1-137">阅读网站的内容时，爬网可能会遇到下面的详细错误代码所表示的一些源错误。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-137">When reading the website's content, the crawl may encounter some source errors which are represented by the detailed error codes below.</span></span> <span data-ttu-id="c7bd1-138">若要获取有关错误类型的详细信息，请在选择该连接后转到 " **错误详细** 信息" 页。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-138">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="c7bd1-139">单击 **错误代码** 以查看更多详细错误。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-139">Click on the **error code** to see more detailed errors.</span></span> <span data-ttu-id="c7bd1-140">此外，请参阅 [管理连接器](https://docs.microsoft.com/microsoftsearch/manage-connector) 以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-140">Also refer to [Manage your connector](https://docs.microsoft.com/microsoftsearch/manage-connector) to learn more.</span></span>

 <span data-ttu-id="c7bd1-141">详细错误代码</span><span class="sxs-lookup"><span data-stu-id="c7bd1-141">Detailed Error code</span></span> | <span data-ttu-id="c7bd1-142">错误消息</span><span class="sxs-lookup"><span data-stu-id="c7bd1-142">Error message</span></span>
 --- | ---
 <span data-ttu-id="c7bd1-143">6001</span><span class="sxs-lookup"><span data-stu-id="c7bd1-143">6001</span></span> | <span data-ttu-id="c7bd1-144">尝试建立索引的网站不可访问</span><span class="sxs-lookup"><span data-stu-id="c7bd1-144">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="c7bd1-145">6005</span><span class="sxs-lookup"><span data-stu-id="c7bd1-145">6005</span></span> | <span data-ttu-id="c7bd1-146">根据 robots.txt 配置，要尝试索引的源页面已被阻止。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-146">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="c7bd1-147">6008</span><span class="sxs-lookup"><span data-stu-id="c7bd1-147">6008</span></span> | <span data-ttu-id="c7bd1-148">无法解析 DNS</span><span class="sxs-lookup"><span data-stu-id="c7bd1-148">Unable to resolve the DNS</span></span>
 <span data-ttu-id="c7bd1-149">6009</span><span class="sxs-lookup"><span data-stu-id="c7bd1-149">6009</span></span> | <span data-ttu-id="c7bd1-150">对于除 HTTP 404、408) 之外的所有客户端错误 (，请参阅 HTTP 4xx 错误代码了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-150">For all client side errors (Except HTTP 404, 408), please refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="c7bd1-151">6013</span><span class="sxs-lookup"><span data-stu-id="c7bd1-151">6013</span></span> | <span data-ttu-id="c7bd1-152">找不到要尝试索引的源页面。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-152">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="c7bd1-153"> (HTTP 404 错误) </span><span class="sxs-lookup"><span data-stu-id="c7bd1-153">(HTTP 404 error)</span></span>
 <span data-ttu-id="c7bd1-154">6018</span><span class="sxs-lookup"><span data-stu-id="c7bd1-154">6018</span></span> | <span data-ttu-id="c7bd1-155">源页面未响应，且请求已超时。 (HTTP 408 错误) </span><span class="sxs-lookup"><span data-stu-id="c7bd1-155">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="c7bd1-156">6021</span><span class="sxs-lookup"><span data-stu-id="c7bd1-156">6021</span></span> | <span data-ttu-id="c7bd1-157">要尝试编制索引的源页面在页面上没有文本内容。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-157">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="c7bd1-158">6023</span><span class="sxs-lookup"><span data-stu-id="c7bd1-158">6023</span></span> | <span data-ttu-id="c7bd1-159">不支持要尝试编制索引的源页面， (不是 HTML 页面) </span><span class="sxs-lookup"><span data-stu-id="c7bd1-159">The source page that is being tried to index is unsupported (not a HTML page)</span></span>
 <span data-ttu-id="c7bd1-160">6024</span><span class="sxs-lookup"><span data-stu-id="c7bd1-160">6024</span></span> | <span data-ttu-id="c7bd1-161">尝试索引的源页面包含不受支持的内容。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-161">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="c7bd1-162">当数据源由于网络问题或数据源本身被删除、移动或重命名而无法访问时，将发生错误6001-6013。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-162">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="c7bd1-163">检查提供的数据源详细信息是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-163">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="c7bd1-164">如果数据源在页面上包含非文本内容或页面不是 HTML，则会出现错误6021-6024 错误。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-164">Errors 6021-6024 error occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="c7bd1-165">请检查数据源并在排除列表中添加此页面或忽略错误。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-165">Please check the data source and add this page in exclusion list or ignore the error.</span></span>

## <a name="limitations"></a><span data-ttu-id="c7bd1-166">限制</span><span class="sxs-lookup"><span data-stu-id="c7bd1-166">Limitations</span></span>

<span data-ttu-id="c7bd1-167">企业网站连接器不支持搜索 **动态网页**上的数据。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-167">The Enterprise websites connector doesn't support searching data on **dynamic webpages**.</span></span> <span data-ttu-id="c7bd1-168">这些网页的示例如 [Confluence](https://www.atlassian.com/software/confluence) 和 [Unily](https://www.unily.com/) 之类的内容管理系统中所示，或存储网站内容的数据库。</span><span class="sxs-lookup"><span data-stu-id="c7bd1-168">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>
