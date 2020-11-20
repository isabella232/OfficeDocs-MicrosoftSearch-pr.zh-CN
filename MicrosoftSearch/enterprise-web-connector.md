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
ms.openlocfilehash: 4b9d8a8472c81c2bc647b3cef3cdb437073d36cf
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367466"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a><span data-ttu-id="f6d62-103">企业网站连接器</span><span class="sxs-lookup"><span data-stu-id="f6d62-103">Enterprise websites connector</span></span>

<span data-ttu-id="f6d62-104">通过企业网站连接器，您的组织可以 **从其面向内部的网站中** 索引文章和内容。</span><span class="sxs-lookup"><span data-stu-id="f6d62-104">With the Enterprise websites connector, your organization can index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="f6d62-105">在配置了该网站的连接器和同步内容之后，最终用户可以从任何 Microsoft 搜索客户端搜索该内容。</span><span class="sxs-lookup"><span data-stu-id="f6d62-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

<span data-ttu-id="f6d62-106">本文适用于 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理员或任何配置、运行和监视企业网站连接器的人。</span><span class="sxs-lookup"><span data-stu-id="f6d62-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="f6d62-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="f6d62-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="f6d62-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="f6d62-108">Connect to a data source</span></span>

<span data-ttu-id="f6d62-109">若要连接到数据源，您需要填写网站的根 URL 和要使用的身份验证类型：无、基本身份验证或使用 [Azure Active Directory (AZURE AD) ](https://docs.microsoft.com/azure/active-directory/)的 OAuth 2.0。</span><span class="sxs-lookup"><span data-stu-id="f6d62-109">To connect to your data source, you need to fill in the root URL of the website and the type of authentication you'd like to use: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).</span></span>

### <a name="url"></a><span data-ttu-id="f6d62-110">URL</span><span class="sxs-lookup"><span data-stu-id="f6d62-110">URL</span></span>

<span data-ttu-id="f6d62-111">使用 "URL" 字段指定要对其进行爬网的网站的根目录。</span><span class="sxs-lookup"><span data-stu-id="f6d62-111">Use the URL field to specify the root of the website that you'd like to crawl.</span></span> <span data-ttu-id="f6d62-112">企业网站连接器将使用此 URL 作为起始点，并根据此 URL 中的所有链接进行爬网。</span><span class="sxs-lookup"><span data-stu-id="f6d62-112">The enterprise websites connector will use this URL as the starting point and follow all the links from this URL for its crawl.</span></span>

### <a name="authentication"></a><span data-ttu-id="f6d62-113">身份验证</span><span class="sxs-lookup"><span data-stu-id="f6d62-113">Authentication</span></span>

<span data-ttu-id="f6d62-114">基本身份验证需要用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="f6d62-114">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="f6d62-115">使用 [Microsoft 365 管理中心](https://admin.microsoft.com)创建此 bot 帐户。</span><span class="sxs-lookup"><span data-stu-id="f6d62-115">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="f6d62-116">使用 [AZURE AD](https://docs.microsoft.com/azure/active-directory/) 的 OAuth 2.0 需要资源 ID、客户端 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="f6d62-116">OAuth 2.0 with [Azure AD](https://docs.microsoft.com/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span>

<span data-ttu-id="f6d62-117">有关详细信息，请参阅 [使用 OAuth 2.0 代码授予流授予对 Azure Active Directory web 应用程序的访问权限](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="f6d62-117">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="f6d62-118">使用以下值注册：</span><span class="sxs-lookup"><span data-stu-id="f6d62-118">Register with the following values:</span></span>

<span data-ttu-id="f6d62-119">**名称：** Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="f6d62-119">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="f6d62-120">**Redirect_URI：**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="f6d62-120">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="f6d62-121">若要获取资源、client_id 和 client_secret 的值，请转到 **使用授权代码请求** 重定向 URL 网页上的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="f6d62-121">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="f6d62-122">有关更多详细信息，请参阅 [快速入门：使用 Microsoft identity Platform 注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="f6d62-122">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="add-urls-to-exclude"></a><span data-ttu-id="f6d62-123">添加要排除的 Url</span><span class="sxs-lookup"><span data-stu-id="f6d62-123">Add URLs to exclude</span></span>

<span data-ttu-id="f6d62-124">您可以根据需要创建 **排除列表** ，以排除某些 url 的爬网，如果该内容是敏感的或不值得爬网。</span><span class="sxs-lookup"><span data-stu-id="f6d62-124">You can optionally create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="f6d62-125">若要创建排除列表，请浏览根 URL。</span><span class="sxs-lookup"><span data-stu-id="f6d62-125">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="f6d62-126">您可以选择在配置过程中将排除的 Url 添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="f6d62-126">You have the option to add the excluded URLs to the list during the configuration process.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="f6d62-127">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="f6d62-127">Manage search permissions</span></span>

<span data-ttu-id="f6d62-128">企业网站连接器仅支持 **所有人都** 能看到的搜索权限。</span><span class="sxs-lookup"><span data-stu-id="f6d62-128">The Enterprise websites connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="f6d62-129">索引数据显示在搜索结果中，并对组织中的所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="f6d62-129">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="f6d62-130">分配属性标签</span><span class="sxs-lookup"><span data-stu-id="f6d62-130">Assign property labels</span></span>

<span data-ttu-id="f6d62-131">通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。</span><span class="sxs-lookup"><span data-stu-id="f6d62-131">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="f6d62-132">虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。</span><span class="sxs-lookup"><span data-stu-id="f6d62-132">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="f6d62-133">管理架构</span><span class="sxs-lookup"><span data-stu-id="f6d62-133">Manage schema</span></span>

<span data-ttu-id="f6d62-134">在 " **管理架构** " 屏幕上，您可以选择更改架构属性， (可 **查询**、可 **搜索**、 **检索** 和 **可精简**) 与属性相关联，添加可选别名，然后选择 **Content** 属性。</span><span class="sxs-lookup"><span data-stu-id="f6d62-134">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="f6d62-135">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="f6d62-135">Set the refresh schedule</span></span>

<span data-ttu-id="f6d62-136">企业网站连接器仅支持完全刷新。</span><span class="sxs-lookup"><span data-stu-id="f6d62-136">The Enterprise websites connector only supports a full refresh.</span></span> <span data-ttu-id="f6d62-137">这意味着连接器将在每次刷新期间对网站的所有内容进行重新爬网。</span><span class="sxs-lookup"><span data-stu-id="f6d62-137">This means that the connector will recrawl all the website's content during every refresh.</span></span> <span data-ttu-id="f6d62-138">若要确保连接器获取足够的时间来对内容进行爬网，建议您设置一个较大的刷新计划间隔。</span><span class="sxs-lookup"><span data-stu-id="f6d62-138">To make sure the connector gets enough time to crawl the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="f6d62-139">建议在一到两周之间进行计划刷新。</span><span class="sxs-lookup"><span data-stu-id="f6d62-139">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f6d62-140">疑难解答</span><span class="sxs-lookup"><span data-stu-id="f6d62-140">Troubleshooting</span></span>

<span data-ttu-id="f6d62-141">阅读网站的内容时，爬网可能会遇到下面的详细错误代码所表示的一些源错误。</span><span class="sxs-lookup"><span data-stu-id="f6d62-141">When reading the website's content, the crawl may encounter some source errors which are represented by the detailed error codes below.</span></span> <span data-ttu-id="f6d62-142">若要获取有关错误类型的详细信息，请在选择该连接后转到 " **错误详细** 信息" 页。</span><span class="sxs-lookup"><span data-stu-id="f6d62-142">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="f6d62-143">单击 **错误代码** 以查看更多详细错误。</span><span class="sxs-lookup"><span data-stu-id="f6d62-143">Click on the **error code** to see more detailed errors.</span></span> <span data-ttu-id="f6d62-144">此外，请参阅 [管理连接器](https://docs.microsoft.com/microsoftsearch/manage-connector) 以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6d62-144">Also refer to [Manage your connector](https://docs.microsoft.com/microsoftsearch/manage-connector) to learn more.</span></span>

 <span data-ttu-id="f6d62-145">详细错误代码</span><span class="sxs-lookup"><span data-stu-id="f6d62-145">Detailed Error code</span></span> | <span data-ttu-id="f6d62-146">错误消息</span><span class="sxs-lookup"><span data-stu-id="f6d62-146">Error message</span></span>
 --- | ---
 <span data-ttu-id="f6d62-147">6001</span><span class="sxs-lookup"><span data-stu-id="f6d62-147">6001</span></span> | <span data-ttu-id="f6d62-148">尝试建立索引的网站不可访问</span><span class="sxs-lookup"><span data-stu-id="f6d62-148">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="f6d62-149">6005</span><span class="sxs-lookup"><span data-stu-id="f6d62-149">6005</span></span> | <span data-ttu-id="f6d62-150">根据 robots.txt 配置，要尝试索引的源页面已被阻止。</span><span class="sxs-lookup"><span data-stu-id="f6d62-150">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="f6d62-151">6008</span><span class="sxs-lookup"><span data-stu-id="f6d62-151">6008</span></span> | <span data-ttu-id="f6d62-152">无法解析 DNS</span><span class="sxs-lookup"><span data-stu-id="f6d62-152">Unable to resolve the DNS</span></span>
 <span data-ttu-id="f6d62-153">6009</span><span class="sxs-lookup"><span data-stu-id="f6d62-153">6009</span></span> | <span data-ttu-id="f6d62-154">对于除 HTTP 404、408) 之外的所有客户端错误 (，请参阅 HTTP 4xx 错误代码了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6d62-154">For all client side errors (Except HTTP 404, 408), please refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="f6d62-155">6013</span><span class="sxs-lookup"><span data-stu-id="f6d62-155">6013</span></span> | <span data-ttu-id="f6d62-156">找不到要尝试索引的源页面。</span><span class="sxs-lookup"><span data-stu-id="f6d62-156">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="f6d62-157"> (HTTP 404 错误) </span><span class="sxs-lookup"><span data-stu-id="f6d62-157">(HTTP 404 error)</span></span>
 <span data-ttu-id="f6d62-158">6018</span><span class="sxs-lookup"><span data-stu-id="f6d62-158">6018</span></span> | <span data-ttu-id="f6d62-159">源页面未响应，且请求已超时。 (HTTP 408 错误) </span><span class="sxs-lookup"><span data-stu-id="f6d62-159">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="f6d62-160">6021</span><span class="sxs-lookup"><span data-stu-id="f6d62-160">6021</span></span> | <span data-ttu-id="f6d62-161">要尝试编制索引的源页面在页面上没有文本内容。</span><span class="sxs-lookup"><span data-stu-id="f6d62-161">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="f6d62-162">6023</span><span class="sxs-lookup"><span data-stu-id="f6d62-162">6023</span></span> | <span data-ttu-id="f6d62-163">不支持要尝试编制索引的源页面， (不是 HTML 页面) </span><span class="sxs-lookup"><span data-stu-id="f6d62-163">The source page that is being tried to index is unsupported (not a HTML page)</span></span>
 <span data-ttu-id="f6d62-164">6024</span><span class="sxs-lookup"><span data-stu-id="f6d62-164">6024</span></span> | <span data-ttu-id="f6d62-165">尝试索引的源页面包含不受支持的内容。</span><span class="sxs-lookup"><span data-stu-id="f6d62-165">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="f6d62-166">当数据源由于网络问题或数据源本身被删除、移动或重命名而无法访问时，将发生错误6001-6013。</span><span class="sxs-lookup"><span data-stu-id="f6d62-166">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="f6d62-167">检查提供的数据源详细信息是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="f6d62-167">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="f6d62-168">如果数据源在页面上包含非文本内容或页面不是 HTML，则会出现错误6021-6024 错误。</span><span class="sxs-lookup"><span data-stu-id="f6d62-168">Errors 6021-6024 error occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="f6d62-169">请检查数据源并在排除列表中添加此页面或忽略错误。</span><span class="sxs-lookup"><span data-stu-id="f6d62-169">Please check the data source and add this page in exclusion list or ignore the error.</span></span>

## <a name="limitations"></a><span data-ttu-id="f6d62-170">限制</span><span class="sxs-lookup"><span data-stu-id="f6d62-170">Limitations</span></span>

<span data-ttu-id="f6d62-171">企业网站连接器不支持搜索 **动态网页** 上的数据。</span><span class="sxs-lookup"><span data-stu-id="f6d62-171">The Enterprise websites connector doesn't support searching data on **dynamic webpages**.</span></span> <span data-ttu-id="f6d62-172">这些网页的示例如 [Confluence](https://www.atlassian.com/software/confluence) 和 [Unily](https://www.unily.com/) 之类的内容管理系统中所示，或存储网站内容的数据库。</span><span class="sxs-lookup"><span data-stu-id="f6d62-172">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>
