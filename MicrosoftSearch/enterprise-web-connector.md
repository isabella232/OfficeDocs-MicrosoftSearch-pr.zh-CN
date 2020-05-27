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
ms.openlocfilehash: c4b799a3127a4a302e3f07953a59ea0319a09052
ms.sourcegitcommit: c186be143164f21a3fecdb3037acd90a26c0fcf3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374332"
---
# <a name="enterprise-websites-connector"></a><span data-ttu-id="a73d1-103">企业网站连接器</span><span class="sxs-lookup"><span data-stu-id="a73d1-103">Enterprise websites connector</span></span>

<span data-ttu-id="a73d1-104">通过企业网站连接器，您的组织可以**从其面向内部的网站中**索引文章和内容。</span><span class="sxs-lookup"><span data-stu-id="a73d1-104">With the Enterprise websites connector, your organization can index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="a73d1-105">在配置了该网站的连接器和同步内容之后，最终用户可以从任何 Microsoft 搜索客户端搜索该内容。</span><span class="sxs-lookup"><span data-stu-id="a73d1-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

<span data-ttu-id="a73d1-106">本文适用于[Microsoft 365](https://www.microsoft.com/microsoft-365)管理员或任何配置、运行和监视企业网站连接器的人。</span><span class="sxs-lookup"><span data-stu-id="a73d1-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="a73d1-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="a73d1-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="a73d1-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="a73d1-108">Connect to a data source</span></span> 
<span data-ttu-id="a73d1-109">若要连接到数据源，您需要根 URL 和基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="a73d1-109">To connect to your data source, you need your root URL and Basic Authentication.</span></span>

### <a name="root-url"></a><span data-ttu-id="a73d1-110">根 URL</span><span class="sxs-lookup"><span data-stu-id="a73d1-110">Root URL</span></span>
<span data-ttu-id="a73d1-111">根 URL 是启动爬网并用于身份验证的。</span><span class="sxs-lookup"><span data-stu-id="a73d1-111">The root URL is what initiates the crawl and is used for authentication.</span></span> <span data-ttu-id="a73d1-112">您可以从要对其进行爬网的网站的主页中获取 URL。</span><span class="sxs-lookup"><span data-stu-id="a73d1-112">You can get the URL from the home page of the website you want to crawl.</span></span>

### <a name="authentication"></a><span data-ttu-id="a73d1-113">身份验证</span><span class="sxs-lookup"><span data-stu-id="a73d1-113">Authentication</span></span> 
<span data-ttu-id="a73d1-114">基本身份验证需要用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="a73d1-114">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="a73d1-115">使用 Microsoft 365[管理中心](https://admin.microsoft.com)创建此 bot 帐户。</span><span class="sxs-lookup"><span data-stu-id="a73d1-115">Create this bot account by using the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span>

## <a name="select-the-source-properties"></a><span data-ttu-id="a73d1-116">选择源属性</span><span class="sxs-lookup"><span data-stu-id="a73d1-116">Select the source properties</span></span> 
<span data-ttu-id="a73d1-117">根据企业网站的数据格式定义源属性。</span><span class="sxs-lookup"><span data-stu-id="a73d1-117">Source properties are defined based on the data format of the enterprise website.</span></span> <span data-ttu-id="a73d1-118">但是，如果内容是敏感的或不值得爬网，则可以创建**排除列表**，以排除某些 url 的爬网。</span><span class="sxs-lookup"><span data-stu-id="a73d1-118">However, you can create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="a73d1-119">若要创建排除列表，请浏览根 URL。</span><span class="sxs-lookup"><span data-stu-id="a73d1-119">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="a73d1-120">您可以选择在配置过程中将排除的 Url 添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="a73d1-120">You have the option to add the excluded URLs to the list during the configuration process.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="a73d1-121">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="a73d1-121">Manage search permissions</span></span> 
<span data-ttu-id="a73d1-122">不支持访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="a73d1-122">There's no support for Access Control Lists (ACLs).</span></span> <span data-ttu-id="a73d1-123">因此，我们建议只将对组织中任何用户可见的网站进行连接。</span><span class="sxs-lookup"><span data-stu-id="a73d1-123">Thus, we recommend connecting only the websites that are visible to any user within your organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="a73d1-124">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="a73d1-124">Set the refresh schedule</span></span>
<span data-ttu-id="a73d1-125">企业网站连接器仅支持完全爬网。</span><span class="sxs-lookup"><span data-stu-id="a73d1-125">The Enterprise websites connector only supports a full crawl.</span></span> <span data-ttu-id="a73d1-126">这意味着，在每次爬网期间，连接器都会读取网站的所有内容。</span><span class="sxs-lookup"><span data-stu-id="a73d1-126">This means that the connector reads all the website's content during every crawl.</span></span> <span data-ttu-id="a73d1-127">若要确保连接器获取足够的时间来读取内容，我们建议您设置一个较大的刷新计划间隔。</span><span class="sxs-lookup"><span data-stu-id="a73d1-127">To make sure the connector gets enough time to read the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="a73d1-128">建议在三天和两周之间计划刷新。</span><span class="sxs-lookup"><span data-stu-id="a73d1-128">We recommend a scheduled refresh between three days and two weeks.</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="a73d1-129">故障排除</span><span class="sxs-lookup"><span data-stu-id="a73d1-129">Troubleshooting</span></span>
<span data-ttu-id="a73d1-130">阅读网站的内容时，爬网可能会遇到下面的详细错误代码所表示的一些源错误。</span><span class="sxs-lookup"><span data-stu-id="a73d1-130">When reading the website's content, the crawl may encounter some source errors which are represented by the detailed error codes below.</span></span> <span data-ttu-id="a73d1-131">若要获取有关错误类型的详细信息，请在选择该连接后转到 "**错误详细**信息" 页。</span><span class="sxs-lookup"><span data-stu-id="a73d1-131">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="a73d1-132">单击**错误代码**以查看更多详细错误。</span><span class="sxs-lookup"><span data-stu-id="a73d1-132">Click on the **error code** to see more detailed errors.</span></span> <span data-ttu-id="a73d1-133">此外，请参阅[管理连接器](https://docs.microsoft.com/microsoftsearch/manage-connector)以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a73d1-133">Also refer to [Manage your connector](https://docs.microsoft.com/microsoftsearch/manage-connector) to learn more.</span></span>

 <span data-ttu-id="a73d1-134">**详细错误代码**</span><span class="sxs-lookup"><span data-stu-id="a73d1-134">**Detailed Error code**</span></span> | <span data-ttu-id="a73d1-135">**错误消息**</span><span class="sxs-lookup"><span data-stu-id="a73d1-135">**Error message**</span></span>
 --- | --- 
 <span data-ttu-id="a73d1-136">6001</span><span class="sxs-lookup"><span data-stu-id="a73d1-136">6001</span></span>   | <span data-ttu-id="a73d1-137">尝试建立索引的网站不可访问</span><span class="sxs-lookup"><span data-stu-id="a73d1-137">The site that is being tried to index is not reachable</span></span> 
 <span data-ttu-id="a73d1-138">6005</span><span class="sxs-lookup"><span data-stu-id="a73d1-138">6005</span></span> | <span data-ttu-id="a73d1-139">由于每个机器人 .txt 配置，要尝试索引的源页面已被阻止。</span><span class="sxs-lookup"><span data-stu-id="a73d1-139">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="a73d1-140">6008</span><span class="sxs-lookup"><span data-stu-id="a73d1-140">6008</span></span> | <span data-ttu-id="a73d1-141">无法解析 DNS</span><span class="sxs-lookup"><span data-stu-id="a73d1-141">Unable to resolve the DNS</span></span>
 <span data-ttu-id="a73d1-142">6009</span><span class="sxs-lookup"><span data-stu-id="a73d1-142">6009</span></span> | <span data-ttu-id="a73d1-143">对于所有客户端错误（HTTP 404、408除外），有关详细信息，请参阅 HTTP 4xx 错误代码。</span><span class="sxs-lookup"><span data-stu-id="a73d1-143">For all client side errors (Except HTTP 404, 408), please refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="a73d1-144">6013</span><span class="sxs-lookup"><span data-stu-id="a73d1-144">6013</span></span> | <span data-ttu-id="a73d1-145">找不到要尝试索引的源页面。</span><span class="sxs-lookup"><span data-stu-id="a73d1-145">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="a73d1-146">（HTTP 404 错误）</span><span class="sxs-lookup"><span data-stu-id="a73d1-146">(HTTP 404 error)</span></span>
 <span data-ttu-id="a73d1-147">6018</span><span class="sxs-lookup"><span data-stu-id="a73d1-147">6018</span></span> | <span data-ttu-id="a73d1-148">源页面未响应，且请求已超时。（HTTP 408 错误）</span><span class="sxs-lookup"><span data-stu-id="a73d1-148">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="a73d1-149">6021</span><span class="sxs-lookup"><span data-stu-id="a73d1-149">6021</span></span> | <span data-ttu-id="a73d1-150">要尝试编制索引的源页面在页面上没有文本内容。</span><span class="sxs-lookup"><span data-stu-id="a73d1-150">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="a73d1-151">6023</span><span class="sxs-lookup"><span data-stu-id="a73d1-151">6023</span></span> | <span data-ttu-id="a73d1-152">尝试索引的源页面不受支持（不是 HTML 页面）</span><span class="sxs-lookup"><span data-stu-id="a73d1-152">The source page that is being tried to index is unsupported (not a HTML page)</span></span>
 <span data-ttu-id="a73d1-153">6024</span><span class="sxs-lookup"><span data-stu-id="a73d1-153">6024</span></span> | <span data-ttu-id="a73d1-154">尝试索引的源页面包含不受支持的内容。</span><span class="sxs-lookup"><span data-stu-id="a73d1-154">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="a73d1-155">当数据源由于网络问题或数据源本身被删除、移动或重命名而无法访问时，将发生错误6001-6013。</span><span class="sxs-lookup"><span data-stu-id="a73d1-155">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="a73d1-156">检查提供的数据源详细信息是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="a73d1-156">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="a73d1-157">如果数据源在页面上包含非文本内容或页面不是 HTML，则会出现错误6021-6024 错误。</span><span class="sxs-lookup"><span data-stu-id="a73d1-157">Errors 6021-6024 error occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="a73d1-158">请检查数据源并在排除列表中添加此页面或忽略错误。</span><span class="sxs-lookup"><span data-stu-id="a73d1-158">Please check the data source and add this page in exclusion list or ignore the error.</span></span>

## <a name="limitations"></a><span data-ttu-id="a73d1-159">限制</span><span class="sxs-lookup"><span data-stu-id="a73d1-159">Limitations</span></span>
<span data-ttu-id="a73d1-160">企业网站连接器不支持搜索**动态网页**上的数据。</span><span class="sxs-lookup"><span data-stu-id="a73d1-160">The Enterprise websites connector doesn't support searching data on **dynamic webpages**.</span></span> <span data-ttu-id="a73d1-161">这些网页的示例如[Confluence](https://www.atlassian.com/software/confluence)和[Unily](https://www.unily.com/)之类的内容管理系统中所示，或存储网站内容的数据库。</span><span class="sxs-lookup"><span data-stu-id="a73d1-161">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>
