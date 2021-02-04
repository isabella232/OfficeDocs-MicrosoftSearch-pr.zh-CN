---
title: 适用于 Microsoft 搜索的企业网站图形连接器
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
ms.openlocfilehash: 526b36a798f50bed457832d576ffebd15820184d
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097427"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a><span data-ttu-id="ca136-103">企业网站图形连接器</span><span class="sxs-lookup"><span data-stu-id="ca136-103">Enterprise websites Graph connector</span></span>

<span data-ttu-id="ca136-104">企业网站 Graph 连接器允许组织从面向内部的网站索引 **文章和内容**。</span><span class="sxs-lookup"><span data-stu-id="ca136-104">The Enterprise websites Graph connector allows your organization to index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="ca136-105">配置连接器并同步网站内容后，最终用户可以从任何 Microsoft 搜索客户端搜索该内容。</span><span class="sxs-lookup"><span data-stu-id="ca136-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="ca136-106">阅读 [**"设置 Graph 连接器"**](configure-connector.md) 文章以了解 Graph 连接器的常规设置过程。</span><span class="sxs-lookup"><span data-stu-id="ca136-106">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="ca136-107">本文适用于配置、运行和监视企业网站连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="ca136-107">This article is for anyone who configures, runs, and monitors a Enterprise websites connector.</span></span> <span data-ttu-id="ca136-108">它补充了常规安装过程，并显示了仅适用于企业网站连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="ca136-108">It supplements the general setup process, and shows instructions that apply only for the Enterprise websites connector.</span></span> <span data-ttu-id="ca136-109">本文还包括有关疑难[解答和](#troubleshooting)[限制的信息](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="ca136-109">This article also includes information about [Troubleshooting](#troubleshooting) and [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ca136-110">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="ca136-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ca136-111">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="ca136-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="ca136-112">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="ca136-112">Step 2: Name the connection</span></span>

<span data-ttu-id="ca136-113">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="ca136-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="ca136-114">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="ca136-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="ca136-115">若要连接到数据源，您需要填写网站的根 URL、选择爬网源和要使用的身份验证类型：无、基本身份验证或 [具有 Azure Active Directory (Azure AD) ](https://docs.microsoft.com/azure/active-directory/)的 OAuth 2.0。</span><span class="sxs-lookup"><span data-stu-id="ca136-115">To connect to your data source, you need to fill in the root URL of the website, select a crawl source, and the type of authentication you'd like to use: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).</span></span> <span data-ttu-id="ca136-116">完成此信息后，选择"测试连接"以验证设置。</span><span class="sxs-lookup"><span data-stu-id="ca136-116">After you complete this information, select Test Connection to verify your settings.</span></span>

### <a name="url"></a><span data-ttu-id="ca136-117">URL</span><span class="sxs-lookup"><span data-stu-id="ca136-117">URL</span></span>

<span data-ttu-id="ca136-118">使用 URL 字段指定要爬网的网站的根。</span><span class="sxs-lookup"><span data-stu-id="ca136-118">Use the URL field to specify the root of the website that you'd like to crawl.</span></span> <span data-ttu-id="ca136-119">企业网站连接器将使用此 URL 作为起始点，并按照此 URL 的所有链接进行爬网。</span><span class="sxs-lookup"><span data-stu-id="ca136-119">The enterprise websites connector will use this URL as the starting point and follow all the links from this URL for its crawl.</span></span>

### <a name="crawl-mode-cloud-or-on-premises-preview"></a><span data-ttu-id="ca136-120">爬网模式：云或本地 (预览) </span><span class="sxs-lookup"><span data-stu-id="ca136-120">Crawl mode: Cloud or On-premises (Preview)</span></span>

<span data-ttu-id="ca136-121">爬网模式确定要编制索引的网站类型（云或本地）。</span><span class="sxs-lookup"><span data-stu-id="ca136-121">The crawl mode determines the type of websites you want to index, either cloud or on-premises.</span></span> <span data-ttu-id="ca136-122">对于云网站，选择 **"云** "作为爬网模式。</span><span class="sxs-lookup"><span data-stu-id="ca136-122">For your cloud websites, select **Cloud** as the crawl mode.</span></span>

<span data-ttu-id="ca136-123">此外，连接器现在支持对本地网站进行爬网。</span><span class="sxs-lookup"><span data-stu-id="ca136-123">Also, the connector now supports crawling of on-premises websites.</span></span> <span data-ttu-id="ca136-124">此模式为预览模式。</span><span class="sxs-lookup"><span data-stu-id="ca136-124">This mode is in preview.</span></span> <span data-ttu-id="ca136-125">若要访问本地数据，必须先安装和配置 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="ca136-125">To access your on-premises data, you must first install and configure the Graph connector agent.</span></span> <span data-ttu-id="ca136-126">若要了解更多信息，请参阅 [Graph 连接器代理](https://docs.microsoft.com/microsoftsearch/on-prem-agent)。</span><span class="sxs-lookup"><span data-stu-id="ca136-126">To learn more, see [Graph connector agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent).</span></span>

<span data-ttu-id="ca136-127">对于本地网站，选择代理作为爬网模式，在"本地代理"字段中，选择之前安装和配置的 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="ca136-127">For your on-premises websites, select **Agent** as the crawl mode and in the **On-Prem Agent** field, choose the Graph connector agent that you installed and configured earlier.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca136-128">![企业 Web 连接器的连接设置窗格屏幕截图](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="ca136-128">![Screenshot of Connection Settings pane for Enterprise Web connector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)</span></span>

### <a name="authentication"></a><span data-ttu-id="ca136-129">身份验证</span><span class="sxs-lookup"><span data-stu-id="ca136-129">Authentication</span></span>

<span data-ttu-id="ca136-130">基本身份验证需要用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="ca136-130">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="ca136-131">使用 [Microsoft 365](https://admin.microsoft.com)管理中心创建此机器人帐户。</span><span class="sxs-lookup"><span data-stu-id="ca136-131">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="ca136-132">具有 Azure AD 的 [OAuth](https://docs.microsoft.com/azure/active-directory/) 2.0 需要资源 ID、客户端 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="ca136-132">OAuth 2.0 with [Azure AD](https://docs.microsoft.com/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span> <span data-ttu-id="ca136-133">OAuth 2.0 仅适用于云模式。</span><span class="sxs-lookup"><span data-stu-id="ca136-133">OAuth 2.0 only works with Cloud mode.</span></span>

<span data-ttu-id="ca136-134">有关详细信息，请参阅授权 [使用 OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)代码授予流访问 Azure Active Directory Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ca136-134">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="ca136-135">注册以下值：</span><span class="sxs-lookup"><span data-stu-id="ca136-135">Register with the following values:</span></span>

<span data-ttu-id="ca136-136">**名称：** Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="ca136-136">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="ca136-137">**Redirect_URI：**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="ca136-137">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="ca136-138">若要获取资源、client_id和client_secret的值，请转到使用授权代码在重定向 URL 网页上请求访问令牌。</span><span class="sxs-lookup"><span data-stu-id="ca136-138">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="ca136-139">有关详细信息，请参阅快速 [入门：使用 Microsoft 标识平台注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="ca136-139">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a><span data-ttu-id="ca136-140">步骤 3a：添加 URL 以排除 (爬网限制) </span><span class="sxs-lookup"><span data-stu-id="ca136-140">Step 3a: Add URLs to exclude (Optional crawl restrictions)</span></span>

<span data-ttu-id="ca136-141">有两种方法可防止对页面进行爬网：禁止在 robots.txt 文件中进行爬网或将其添加到排除列表。</span><span class="sxs-lookup"><span data-stu-id="ca136-141">There are two ways to prevent pages from being crawled: disallow them in your robots.txt file or add them to the Exclusion list.</span></span>

### <a name="support-for-robotstxt"></a><span data-ttu-id="ca136-142">支持robots.txt</span><span class="sxs-lookup"><span data-stu-id="ca136-142">Support for robots.txt</span></span>

<span data-ttu-id="ca136-143">连接器检查根网站是否存在robots.txt文件，如果存在，它将遵循并遵循该文件中的说明。</span><span class="sxs-lookup"><span data-stu-id="ca136-143">The connector checks to see if there is a robots.txt file for your root site and, if one exists, it will follow and respect the directions found within that file.</span></span> <span data-ttu-id="ca136-144">如果您不希望连接器对网站上的某些页面或目录进行爬网，可以在您的 robots.txt 文件中调用这些页面或目录。</span><span class="sxs-lookup"><span data-stu-id="ca136-144">If you do not want the connector to crawl certain pages or directories on your site, you can call out those pages or directories in the "Disallow" declarations in your robots.txt file.</span></span>

### <a name="add-urls-to-exclude"></a><span data-ttu-id="ca136-145">添加要排除的 URL</span><span class="sxs-lookup"><span data-stu-id="ca136-145">Add URLs to exclude</span></span>

<span data-ttu-id="ca136-146">您可以选择创建排除列表，以在内容敏感或不需要爬网时排除某些 URL 进行爬网。</span><span class="sxs-lookup"><span data-stu-id="ca136-146">You can optionally create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="ca136-147">若要创建排除列表，请浏览根 URL。</span><span class="sxs-lookup"><span data-stu-id="ca136-147">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="ca136-148">您可以在配置过程中将排除的 URL 添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="ca136-148">You can add the excluded URLs to the list during the configuration process.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="ca136-149">步骤 4：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="ca136-149">Step 4: Assign property labels</span></span>

<span data-ttu-id="ca136-150">可以通过从选项菜单中选择来为每个标签分配源属性。</span><span class="sxs-lookup"><span data-stu-id="ca136-150">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="ca136-151">虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更准确的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="ca136-151">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="ca136-152">步骤 5：管理架构</span><span class="sxs-lookup"><span data-stu-id="ca136-152">Step 5: Manage schema</span></span>

<span data-ttu-id="ca136-153">在"管理架构"屏幕上，可以更改架构属性 (选项为"查询"、"搜索"、"检索"和"精简 **")** 与属性关联，添加可选别名，然后选择"**内容**"属性。 </span><span class="sxs-lookup"><span data-stu-id="ca136-153">On the **Manage Schema** screen, you can change the schema attributes (the options are **Query**, **Search**, **Retrieve**, and **Refine**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="ca136-154">步骤 6：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="ca136-154">Step 6: Manage search permissions</span></span>

<span data-ttu-id="ca136-155">企业网站连接器仅支持对所有人可见的搜索 **权限**。</span><span class="sxs-lookup"><span data-stu-id="ca136-155">The Enterprise websites connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="ca136-156">索引数据将显示在搜索结果中，并且对组织所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="ca136-156">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="ca136-157">步骤 7：设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="ca136-157">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="ca136-158">企业网站连接器仅支持完全刷新。</span><span class="sxs-lookup"><span data-stu-id="ca136-158">The Enterprise websites connector only supports a full refresh.</span></span> <span data-ttu-id="ca136-159">这意味着连接器将在每次刷新期间对网站的所有内容重新进行重新对。</span><span class="sxs-lookup"><span data-stu-id="ca136-159">This means that the connector will recrawl all the website's content during every refresh.</span></span> <span data-ttu-id="ca136-160">若要确保连接器有足够的时间对内容进行爬网，建议您设置较大的刷新计划间隔。</span><span class="sxs-lookup"><span data-stu-id="ca136-160">To make sure the connector gets enough time to crawl the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="ca136-161">我们建议在一到两周之间安排刷新。</span><span class="sxs-lookup"><span data-stu-id="ca136-161">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="ca136-162">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="ca136-162">Step 8: Review connection</span></span>

<span data-ttu-id="ca136-163">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="ca136-163">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a><span data-ttu-id="ca136-164">故障排除</span><span class="sxs-lookup"><span data-stu-id="ca136-164">Troubleshooting</span></span>

<span data-ttu-id="ca136-165">读取网站内容时，爬网可能会遇到一些源错误，这些错误由下面的详细错误代码表示。</span><span class="sxs-lookup"><span data-stu-id="ca136-165">When reading the website's content, the crawl may encounter some source errors, which are represented by the detailed error codes below.</span></span> <span data-ttu-id="ca136-166">若要获取有关错误类型的详细信息，请转到选择连接 **后** 的错误详细信息页。</span><span class="sxs-lookup"><span data-stu-id="ca136-166">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="ca136-167">选择 **错误代码** 以查看更详细的错误。</span><span class="sxs-lookup"><span data-stu-id="ca136-167">Select the **error code** to see more detailed errors.</span></span> <span data-ttu-id="ca136-168">另请参阅 ["管理连接器"](https://docs.microsoft.com/microsoftsearch/manage-connector) 了解详情。</span><span class="sxs-lookup"><span data-stu-id="ca136-168">Also refer to [Manage your connector](https://docs.microsoft.com/microsoftsearch/manage-connector) to learn more.</span></span>

 <span data-ttu-id="ca136-169">详细错误代码</span><span class="sxs-lookup"><span data-stu-id="ca136-169">Detailed Error code</span></span> | <span data-ttu-id="ca136-170">错误消息</span><span class="sxs-lookup"><span data-stu-id="ca136-170">Error message</span></span>
 --- | ---
 <span data-ttu-id="ca136-171">6001</span><span class="sxs-lookup"><span data-stu-id="ca136-171">6001</span></span> | <span data-ttu-id="ca136-172">无法访问尝试编制索引的网站</span><span class="sxs-lookup"><span data-stu-id="ca136-172">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="ca136-173">6005</span><span class="sxs-lookup"><span data-stu-id="ca136-173">6005</span></span> | <span data-ttu-id="ca136-174">尝试编制索引的源页已按配置robots.txt阻止。</span><span class="sxs-lookup"><span data-stu-id="ca136-174">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="ca136-175">6008</span><span class="sxs-lookup"><span data-stu-id="ca136-175">6008</span></span> | <span data-ttu-id="ca136-176">无法解析 DNS</span><span class="sxs-lookup"><span data-stu-id="ca136-176">Unable to resolve the DNS</span></span>
 <span data-ttu-id="ca136-177">6009</span><span class="sxs-lookup"><span data-stu-id="ca136-177">6009</span></span> | <span data-ttu-id="ca136-178">有关除 HTTP 404 (408) 之外的所有客户端错误，请参阅 HTTP 4xx 错误代码了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="ca136-178">For all client-side errors (Except HTTP 404, 408), refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="ca136-179">6013</span><span class="sxs-lookup"><span data-stu-id="ca136-179">6013</span></span> | <span data-ttu-id="ca136-180">找不到尝试编制索引的源页。</span><span class="sxs-lookup"><span data-stu-id="ca136-180">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="ca136-181"> (HTTP 404 错误) </span><span class="sxs-lookup"><span data-stu-id="ca136-181">(HTTP 404 error)</span></span>
 <span data-ttu-id="ca136-182">6018</span><span class="sxs-lookup"><span data-stu-id="ca136-182">6018</span></span> | <span data-ttu-id="ca136-183">源页面未响应，并且请求已退出。 (HTTP 408 错误) </span><span class="sxs-lookup"><span data-stu-id="ca136-183">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="ca136-184">6021</span><span class="sxs-lookup"><span data-stu-id="ca136-184">6021</span></span> | <span data-ttu-id="ca136-185">试图编制索引的源页在页面上没有文本内容。</span><span class="sxs-lookup"><span data-stu-id="ca136-185">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="ca136-186">6023</span><span class="sxs-lookup"><span data-stu-id="ca136-186">6023</span></span> | <span data-ttu-id="ca136-187">尝试编制索引的源页不受支持， (HTML 页面) </span><span class="sxs-lookup"><span data-stu-id="ca136-187">The source page that is being tried to index is unsupported (not an HTML page)</span></span>
 <span data-ttu-id="ca136-188">6024</span><span class="sxs-lookup"><span data-stu-id="ca136-188">6024</span></span> | <span data-ttu-id="ca136-189">试图编制索引的源页包含的内容不受支持。</span><span class="sxs-lookup"><span data-stu-id="ca136-189">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="ca136-190">如果数据源因网络问题而不可访问，或者数据源本身被删除、移动或重命名，则会发生错误 6001-6013。</span><span class="sxs-lookup"><span data-stu-id="ca136-190">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="ca136-191">检查提供的数据源详细信息是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="ca136-191">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="ca136-192">当数据源包含页面上的非文本内容或页面不是 HTML 时，将发生错误 6021-6024。</span><span class="sxs-lookup"><span data-stu-id="ca136-192">Errors 6021-6024 occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="ca136-193">检查数据源，在排除列表中添加此页面或忽略错误。</span><span class="sxs-lookup"><span data-stu-id="ca136-193">Check the data source and add this page in exclusion list or ignore the error.</span></span>

## <a name="limitations"></a><span data-ttu-id="ca136-194">限制</span><span class="sxs-lookup"><span data-stu-id="ca136-194">Limitations</span></span>

<span data-ttu-id="ca136-195">企业网站连接器不支持在动态网页上 **搜索数据**。</span><span class="sxs-lookup"><span data-stu-id="ca136-195">The Enterprise websites connector doesn't support searching data on **dynamic webpages**.</span></span> <span data-ttu-id="ca136-196">这些网页的示例存储在内容管理系统（如 [Confluence](https://www.atlassian.com/software/confluence) 和 [Unily）](https://www.unily.com/) 或存储网站内容的数据库中。</span><span class="sxs-lookup"><span data-stu-id="ca136-196">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>