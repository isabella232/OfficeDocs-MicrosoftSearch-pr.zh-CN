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
description: 为Enterprise连接器Graph网站Microsoft 搜索
ms.openlocfilehash: 32e38c9bef036556dae2734e23b1d26ba4fe2c27
ms.sourcegitcommit: 38a0f09596c2bca0e12bf4cada7b4c64fd4c48e4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53449041"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a><span data-ttu-id="009e6-103">Enterprise连接器Graph网站</span><span class="sxs-lookup"><span data-stu-id="009e6-103">Enterprise websites Graph connector</span></span>

<span data-ttu-id="009e6-104">通过Enterprise连接器Graph组织可以索引其面向内部的网站 **的文章和内容**。</span><span class="sxs-lookup"><span data-stu-id="009e6-104">The Enterprise websites Graph connector allows your organization to index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="009e6-105">配置连接器并同步网站内容后，最终用户可以从任何客户端搜索Microsoft 搜索内容。</span><span class="sxs-lookup"><span data-stu-id="009e6-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="009e6-106">阅读 [**Setup your Graph connector**](configure-connector.md)一文，了解 Graph 连接器的一般设置说明。</span><span class="sxs-lookup"><span data-stu-id="009e6-106">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="009e6-107">本文适用于配置、运行和监视 Enterprise连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="009e6-107">This article is for anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="009e6-108">它补充了常规安装过程，并显示了仅适用于 Enterprise 连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="009e6-108">It supplements the general setup process, and shows instructions that apply only for the Enterprise websites connector.</span></span> <span data-ttu-id="009e6-109">本文还包括有关疑难 [解答的信息](#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="009e6-109">This article also includes information about [Troubleshooting](#troubleshooting).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="009e6-110">步骤 1：在Graph中添加一个Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="009e6-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="009e6-111">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="009e6-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="009e6-112">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="009e6-112">Step 2: Name the connection</span></span>

<span data-ttu-id="009e6-113">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="009e6-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="009e6-114">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="009e6-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="009e6-115">若要连接到数据源，请填写网站的根 URL，选择爬网源和你要使用的身份验证类型：无、基本身份验证或[包含 Azure Active Directory (Azure AD) ](/azure/active-directory/)的 OAuth 2.0。</span><span class="sxs-lookup"><span data-stu-id="009e6-115">To connect to your data source, fill in the root URL of the website, select a crawl source, and the type of authentication you'd like to use: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](/azure/active-directory/).</span></span> <span data-ttu-id="009e6-116">完成此信息后，选择"测试连接"以验证设置。</span><span class="sxs-lookup"><span data-stu-id="009e6-116">After you complete this information, select Test Connection to verify your settings.</span></span>

### <a name="url"></a><span data-ttu-id="009e6-117">URL</span><span class="sxs-lookup"><span data-stu-id="009e6-117">URL</span></span>

<span data-ttu-id="009e6-118">使用 URL 字段指定要爬网的网站的根。</span><span class="sxs-lookup"><span data-stu-id="009e6-118">Use the URL field to specify the root of the website that you'd like to crawl.</span></span> <span data-ttu-id="009e6-119">企业网站连接器将使用此 URL 作为起点，并按照此 URL 的所有链接进行爬网。</span><span class="sxs-lookup"><span data-stu-id="009e6-119">The enterprise websites connector will use this URL as the starting point and follow all the links from this URL for its crawl.</span></span>

### <a name="crawl-websites-listed-in-the-sitemap"></a><span data-ttu-id="009e6-120">对网站地图中列出的网站进行爬网</span><span class="sxs-lookup"><span data-stu-id="009e6-120">Crawl websites listed in the sitemap</span></span>

<span data-ttu-id="009e6-121">选择后，连接器将仅对网站地图中列出的 URL 进行爬网。</span><span class="sxs-lookup"><span data-stu-id="009e6-121">When selected the connector will only crawl the URLs listed in the sitemap.</span></span> <span data-ttu-id="009e6-122">如果未选择或未找到站点地图，连接器将深入爬网在网站的根 URL 上找到的所有链接。</span><span class="sxs-lookup"><span data-stu-id="009e6-122">If not selected or no site map is found, the connector will do a deep crawl of all the links found on the root URL of the site.</span></span>

### <a name="dynamic-site-configuration"></a><span data-ttu-id="009e6-123">动态网站配置</span><span class="sxs-lookup"><span data-stu-id="009e6-123">Dynamic site configuration</span></span>

<span data-ttu-id="009e6-124">如果您的网站包含动态内容（例如，内容管理系统（如 Confluence 或 Unily）中的网页，您可以启用动态爬网程序。</span><span class="sxs-lookup"><span data-stu-id="009e6-124">If your website contains dynamic content, for example, webpages that live in content management systems like Confluence or Unily, you can enable a dynamic crawler.</span></span> <span data-ttu-id="009e6-125">若要将其打开，请选择"**为动态网站启用爬网"。**</span><span class="sxs-lookup"><span data-stu-id="009e6-125">To turn it on, select **Enable crawl for dynamic sites**.</span></span> <span data-ttu-id="009e6-126">爬网程序将等待动态内容呈现，然后再开始爬网。</span><span class="sxs-lookup"><span data-stu-id="009e6-126">The crawler will wait for dynamic content to render before it begins crawling.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="009e6-127">![Web 连接器的连接设置窗格Enterprise屏幕截图](media/enterprise-web-connector/connectors-enterpriseweb-connectionsettings-dynamicconfig-small.png)</span><span class="sxs-lookup"><span data-stu-id="009e6-127">![Screenshot of Connection Settings pane for Enterprise Web connector](media/enterprise-web-connector/connectors-enterpriseweb-connectionsettings-dynamicconfig-small.png)</span></span>

<span data-ttu-id="009e6-128">除了该复选框之外，还有三个可选字段可用：</span><span class="sxs-lookup"><span data-stu-id="009e6-128">In addition to the check box, there are three optional fields available:</span></span>

1. <span data-ttu-id="009e6-129">**DOM Ready：** 输入爬网程序应用作内容已完全呈现且应开始爬网的信号的 DOM 元素。</span><span class="sxs-lookup"><span data-stu-id="009e6-129">**DOM Ready**: Enter the DOM element the crawler should use as the signal that the content is fully rendered and the crawl should begin.</span></span>
1. <span data-ttu-id="009e6-130">**要添加的标头**：指定在发送特定 Web URL 时爬网程序应包含的 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="009e6-130">**Headers to Add**: Specify which HTTP headers the crawler should include when sending that specific web URL.</span></span> <span data-ttu-id="009e6-131">您可以为不同的网站设置多个标头。</span><span class="sxs-lookup"><span data-stu-id="009e6-131">You can set multiple headers for different websites.</span></span> <span data-ttu-id="009e6-132">我们建议包括身份验证令牌值。</span><span class="sxs-lookup"><span data-stu-id="009e6-132">We suggest including auth token values.</span></span>
1. <span data-ttu-id="009e6-133">**要跳过的标题**：指定应从动态爬网请求中排除的任何不必要的标头。</span><span class="sxs-lookup"><span data-stu-id="009e6-133">**Headers to Skip**: Specify any unnecessary headers that should be excluded from dynamic crawling requests.</span></span>

> [!NOTE]
> <span data-ttu-id="009e6-134">动态爬网仅受代理爬网模式支持。</span><span class="sxs-lookup"><span data-stu-id="009e6-134">Dynamic crawling is only supported for Agent crawl mode.</span></span>

### <a name="crawl-mode-cloud-or-on-premises"></a><span data-ttu-id="009e6-135">爬网模式：云或本地</span><span class="sxs-lookup"><span data-stu-id="009e6-135">Crawl mode: Cloud or On-premises</span></span>

<span data-ttu-id="009e6-136">爬网模式确定要索引的网站类型（云或本地）。</span><span class="sxs-lookup"><span data-stu-id="009e6-136">The crawl mode determines the type of websites you want to index, either cloud or on-premises.</span></span> <span data-ttu-id="009e6-137">对于云网站，选择 **"云** "作为爬网模式。</span><span class="sxs-lookup"><span data-stu-id="009e6-137">For your cloud websites, select **Cloud** as the crawl mode.</span></span>

<span data-ttu-id="009e6-138">此外，连接器现在支持对本地网站进行爬网。</span><span class="sxs-lookup"><span data-stu-id="009e6-138">Also, the connector now supports crawling of on-premises websites.</span></span> <span data-ttu-id="009e6-139">若要访问本地数据，必须先安装和配置 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="009e6-139">To access your on-premises data, you must first install and configure the Graph connector agent.</span></span> <span data-ttu-id="009e6-140">若要了解更多信息，请参阅[Graph代理](./on-prem-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="009e6-140">To learn more, see [Graph connector agent](./on-prem-agent.md).</span></span>

<span data-ttu-id="009e6-141">对于本地网站，选择"代理"作为爬网模式，在"本地代理"字段中，选择之前安装和配置的 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="009e6-141">For your on-premises websites, select **Agent** as the crawl mode and in the **On-prem Agent** field, choose the Graph connector agent that you installed and configured earlier.</span></span>  

### <a name="authentication"></a><span data-ttu-id="009e6-142">身份验证</span><span class="sxs-lookup"><span data-stu-id="009e6-142">Authentication</span></span>

<span data-ttu-id="009e6-143">基本身份验证需要用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="009e6-143">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="009e6-144">使用帐户创建此自动程序[Microsoft 365 管理中心。](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="009e6-144">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="009e6-145">具有 [Azure AD](/azure/active-directory/) 的 OAuth 2.0 需要资源 ID、客户端 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="009e6-145">OAuth 2.0 with [Azure AD](/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span> <span data-ttu-id="009e6-146">OAuth 2.0 仅适用于云模式。</span><span class="sxs-lookup"><span data-stu-id="009e6-146">OAuth 2.0 only works with Cloud mode.</span></span>

<span data-ttu-id="009e6-147">有关详细信息，请参阅使用[OAuth 2.0 代码Azure Active Directory授权访问 Web](/azure/active-directory/develop/v1-protocols-oauth-code)应用程序。</span><span class="sxs-lookup"><span data-stu-id="009e6-147">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="009e6-148">注册以下值：</span><span class="sxs-lookup"><span data-stu-id="009e6-148">Register with the following values:</span></span>

<span data-ttu-id="009e6-149">**名称：Microsoft 搜索**</span><span class="sxs-lookup"><span data-stu-id="009e6-149">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="009e6-150">**Redirect_URI：**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="009e6-150">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="009e6-151">若要获取资源、client_id 和 client_secret 的值，请转到使用授权代码请求重定向 URL **网页上的访问** 令牌。</span><span class="sxs-lookup"><span data-stu-id="009e6-151">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="009e6-152">有关详细信息，请参阅快速入门[：向应用程序注册Microsoft 标识平台。](/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="009e6-152">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a><span data-ttu-id="009e6-153">步骤 3a：添加 URL 以排除 (可选的爬网限制) </span><span class="sxs-lookup"><span data-stu-id="009e6-153">Step 3a: Add URLs to exclude (Optional crawl restrictions)</span></span>

<span data-ttu-id="009e6-154">有两种方法可以阻止对页面进行爬网：禁止在robots.txt文件中对页面进行爬网或将其添加到排除列表。</span><span class="sxs-lookup"><span data-stu-id="009e6-154">There are two ways to prevent pages from being crawled: disallow them in your robots.txt file or add them to the Exclusion list.</span></span>

### <a name="support-for-robotstxt"></a><span data-ttu-id="009e6-155">支持robots.txt</span><span class="sxs-lookup"><span data-stu-id="009e6-155">Support for robots.txt</span></span>

<span data-ttu-id="009e6-156">连接器检查根网站是否存在robots.txt文件，如果存在，它将遵循并遵循该文件中的说明。</span><span class="sxs-lookup"><span data-stu-id="009e6-156">The connector checks to see if there is a robots.txt file for your root site and, if one exists, it will follow and respect the directions found within that file.</span></span> <span data-ttu-id="009e6-157">如果您不希望连接器对网站上的某些页面或目录进行爬网，可以在您的 robots.txt 文件中调用这些页面或目录。</span><span class="sxs-lookup"><span data-stu-id="009e6-157">If you do not want the connector to crawl certain pages or directories on your site, you can call out those pages or directories in the "Disallow" declarations in your robots.txt file.</span></span>

### <a name="add-urls-to-exclude"></a><span data-ttu-id="009e6-158">添加要排除的 URL</span><span class="sxs-lookup"><span data-stu-id="009e6-158">Add URLs to exclude</span></span>

<span data-ttu-id="009e6-159">您可以选择创建排除列表，以在内容敏感或值得爬网时排除某些 URL 进行爬网。</span><span class="sxs-lookup"><span data-stu-id="009e6-159">You can optionally create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="009e6-160">若要创建排除列表，请浏览根 URL。</span><span class="sxs-lookup"><span data-stu-id="009e6-160">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="009e6-161">您可以在配置过程中将排除的 URL 添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="009e6-161">You can add the excluded URLs to the list during the configuration process.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="009e6-162">步骤 4：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="009e6-162">Step 4: Assign property labels</span></span>

<span data-ttu-id="009e6-163">可以通过从选项菜单中选择来为每个标签分配源属性。</span><span class="sxs-lookup"><span data-stu-id="009e6-163">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="009e6-164">虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更准确的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="009e6-164">While this step isn't mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="009e6-165">步骤 5：管理架构</span><span class="sxs-lookup"><span data-stu-id="009e6-165">Step 5: Manage schema</span></span>

<span data-ttu-id="009e6-166">在"管理架构"屏幕上，可以更改架构属性 (选项包括"查询"、搜索、检索和精简) 与属性关联，添加可选别名，然后选择"**内容**"属性。</span><span class="sxs-lookup"><span data-stu-id="009e6-166">On the **Manage Schema** screen, you can change the schema attributes (the options are **Query**, **Search**, **Retrieve**, and **Refine**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="009e6-167">步骤 6：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="009e6-167">Step 6: Manage search permissions</span></span>

<span data-ttu-id="009e6-168">the Enterprise websites connector only supports search permissions visible to **Everyone**.</span><span class="sxs-lookup"><span data-stu-id="009e6-168">The Enterprise websites connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="009e6-169">索引数据将显示在搜索结果中，并且对组织中所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="009e6-169">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="009e6-170">步骤 7：设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="009e6-170">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="009e6-171">Enterprise网站连接器仅支持完全刷新。</span><span class="sxs-lookup"><span data-stu-id="009e6-171">The Enterprise websites connector only supports a full refresh.</span></span> <span data-ttu-id="009e6-172">这意味着连接器将在每次刷新过程中对网站的所有内容重新进行crawl。</span><span class="sxs-lookup"><span data-stu-id="009e6-172">This means that the connector will recrawl all the website's content during every refresh.</span></span> <span data-ttu-id="009e6-173">若要确保连接器有足够的时间对内容进行爬网，建议您设置一个大型刷新计划间隔。</span><span class="sxs-lookup"><span data-stu-id="009e6-173">To make sure the connector gets enough time to crawl the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="009e6-174">我们建议在一到两周之间计划刷新。</span><span class="sxs-lookup"><span data-stu-id="009e6-174">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="009e6-175">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="009e6-175">Step 8: Review connection</span></span>

<span data-ttu-id="009e6-176">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="009e6-176">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a><span data-ttu-id="009e6-177">疑难解答</span><span class="sxs-lookup"><span data-stu-id="009e6-177">Troubleshooting</span></span>

<span data-ttu-id="009e6-178">在读取网站内容时，爬网可能会遇到一些源错误，这些错误由下面的详细错误代码表示。</span><span class="sxs-lookup"><span data-stu-id="009e6-178">When reading the website's content, the crawl may encounter some source errors, which are represented by the detailed error codes below.</span></span> <span data-ttu-id="009e6-179">若要获取有关错误类型的详细信息，请转到选择连接后 **的错误** 详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="009e6-179">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="009e6-180">选择 **错误代码** 以查看更详细的错误。</span><span class="sxs-lookup"><span data-stu-id="009e6-180">Select the **error code** to see more detailed errors.</span></span> <span data-ttu-id="009e6-181">另请参阅 [管理连接器以了解](./manage-connector.md) 详情。</span><span class="sxs-lookup"><span data-stu-id="009e6-181">Also refer to [Manage your connector](./manage-connector.md) to learn more.</span></span>

 <span data-ttu-id="009e6-182">详细错误代码</span><span class="sxs-lookup"><span data-stu-id="009e6-182">Detailed Error code</span></span> | <span data-ttu-id="009e6-183">错误消息</span><span class="sxs-lookup"><span data-stu-id="009e6-183">Error message</span></span>
 --- | ---
 <span data-ttu-id="009e6-184">6001</span><span class="sxs-lookup"><span data-stu-id="009e6-184">6001</span></span> | <span data-ttu-id="009e6-185">尝试编制索引的网站不可访问</span><span class="sxs-lookup"><span data-stu-id="009e6-185">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="009e6-186">6005</span><span class="sxs-lookup"><span data-stu-id="009e6-186">6005</span></span> | <span data-ttu-id="009e6-187">尝试编制索引的源页已因配置robots.txt阻止。</span><span class="sxs-lookup"><span data-stu-id="009e6-187">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="009e6-188">6008</span><span class="sxs-lookup"><span data-stu-id="009e6-188">6008</span></span> | <span data-ttu-id="009e6-189">无法解析 DNS</span><span class="sxs-lookup"><span data-stu-id="009e6-189">Unable to resolve the DNS</span></span>
 <span data-ttu-id="009e6-190">6009</span><span class="sxs-lookup"><span data-stu-id="009e6-190">6009</span></span> | <span data-ttu-id="009e6-191">对于除 HTTP 404 (408) 之外的所有客户端错误，请参阅 HTTP 4xx 错误代码了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="009e6-191">For all client-side errors (Except HTTP 404, 408), refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="009e6-192">6013</span><span class="sxs-lookup"><span data-stu-id="009e6-192">6013</span></span> | <span data-ttu-id="009e6-193">找不到尝试编制索引的源页。</span><span class="sxs-lookup"><span data-stu-id="009e6-193">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="009e6-194"> (HTTP 404 错误) </span><span class="sxs-lookup"><span data-stu-id="009e6-194">(HTTP 404 error)</span></span>
 <span data-ttu-id="009e6-195">6018</span><span class="sxs-lookup"><span data-stu-id="009e6-195">6018</span></span> | <span data-ttu-id="009e6-196">源页面未响应，并且请求已退出。 (HTTP 408 错误) </span><span class="sxs-lookup"><span data-stu-id="009e6-196">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="009e6-197">6021</span><span class="sxs-lookup"><span data-stu-id="009e6-197">6021</span></span> | <span data-ttu-id="009e6-198">试图编制索引的源页面在页面上没有文本内容。</span><span class="sxs-lookup"><span data-stu-id="009e6-198">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="009e6-199">6023</span><span class="sxs-lookup"><span data-stu-id="009e6-199">6023</span></span> | <span data-ttu-id="009e6-200">尝试编制索引的源页不受支持， (HTML 页面) </span><span class="sxs-lookup"><span data-stu-id="009e6-200">The source page that is being tried to index is unsupported (not an HTML page)</span></span>
 <span data-ttu-id="009e6-201">6024</span><span class="sxs-lookup"><span data-stu-id="009e6-201">6024</span></span> | <span data-ttu-id="009e6-202">试图编制索引的源页包含的内容不受支持。</span><span class="sxs-lookup"><span data-stu-id="009e6-202">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="009e6-203">错误 6001-6013 在数据源因网络问题而不可访问时发生，或者数据源本身被删除、移动或重命名时发生。</span><span class="sxs-lookup"><span data-stu-id="009e6-203">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="009e6-204">检查提供的数据源详细信息是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="009e6-204">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="009e6-205">当数据源包含页面上的非文本内容或页面不是 HTML 时，将发生错误 6021-6024。</span><span class="sxs-lookup"><span data-stu-id="009e6-205">Errors 6021-6024 occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="009e6-206">检查数据源，在排除列表中添加此页面或忽略错误。</span><span class="sxs-lookup"><span data-stu-id="009e6-206">Check the data source and add this page in exclusion list or ignore the error.</span></span>
