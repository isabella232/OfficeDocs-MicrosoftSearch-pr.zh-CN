---
title: 用于 Microsoft 搜索的 Azure DevOps 连接器
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置 Azure DevOps connector for Microsoft Search
ms.openlocfilehash: a0028c3b336c2b5e3d01bb14006ee0debb4524f2
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927186"
---
# <a name="azure-devops-connector"></a><span data-ttu-id="e55e4-103">Azure DevOps 连接器</span><span class="sxs-lookup"><span data-stu-id="e55e4-103">Azure DevOps connector</span></span>

<span data-ttu-id="e55e4-104">使用 Azure DevOps 连接器，组织可以在其 Azure DevOps 服务实例中对工作项编制索引。</span><span class="sxs-lookup"><span data-stu-id="e55e4-104">With the Azure DevOps connector, your organization can index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="e55e4-105">在从 Azure DevOps 配置连接器和索引内容之后，最终用户可以在 Microsoft Search 中搜索这些项目。</span><span class="sxs-lookup"><span data-stu-id="e55e4-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

<span data-ttu-id="e55e4-106">本文适用于 Microsoft 365 管理员或任何配置、运行和监控 Azure DevOps 连接器的人。</span><span class="sxs-lookup"><span data-stu-id="e55e4-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure DevOps connector.</span></span> <span data-ttu-id="e55e4-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="e55e4-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e55e4-108">Azure DevOps 连接器仅支持 Azure DevOps 云服务。</span><span class="sxs-lookup"><span data-stu-id="e55e4-108">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="e55e4-109">此连接器不支持 Azure DevOps Server 2019、TFS 2018、TFS 2017、TFS 2015 和 TFS 2013。</span><span class="sxs-lookup"><span data-stu-id="e55e4-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="e55e4-110">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="e55e4-110">Connect to a data source</span></span>

<span data-ttu-id="e55e4-111">若要连接到 Azure DevOps 实例，需要你的 Azure DevOps [组织](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) 名称、其应用 ID 和 OAuth 身份验证的客户端密码。</span><span class="sxs-lookup"><span data-stu-id="e55e4-111">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="e55e4-112">注册应用</span><span class="sxs-lookup"><span data-stu-id="e55e4-112">Register an app</span></span>

<span data-ttu-id="e55e4-113">您必须在 Azure DevOps 中注册应用程序，以便 Microsoft 搜索应用程序可以访问该实例。</span><span class="sxs-lookup"><span data-stu-id="e55e4-113">You must register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="e55e4-114">若要了解详细信息，请参阅 Azure DevOps 文档了解如何 [注册应用](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app)。</span><span class="sxs-lookup"><span data-stu-id="e55e4-114">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="e55e4-115">下表提供了有关如何填写 "应用注册" 表单的指导：</span><span class="sxs-lookup"><span data-stu-id="e55e4-115">The following table provides guidance on how to fill out the app registration form:</span></span>

 <span data-ttu-id="e55e4-116">**必填字段**</span><span class="sxs-lookup"><span data-stu-id="e55e4-116">**Mandatory Fields**</span></span> | <span data-ttu-id="e55e4-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="e55e4-117">**Description**</span></span>      | <span data-ttu-id="e55e4-118">**推荐值**</span><span class="sxs-lookup"><span data-stu-id="e55e4-118">**Recommended Value**</span></span>
--- | --- | ---
| <span data-ttu-id="e55e4-119">公司名称</span><span class="sxs-lookup"><span data-stu-id="e55e4-119">Company Name</span></span>         | <span data-ttu-id="e55e4-120">这是您的公司的名称。</span><span class="sxs-lookup"><span data-stu-id="e55e4-120">This is the name of your company.</span></span> | <span data-ttu-id="e55e4-121">使用适当的值</span><span class="sxs-lookup"><span data-stu-id="e55e4-121">Use an appropriate value</span></span>   |
| <span data-ttu-id="e55e4-122">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="e55e4-122">Application name</span></span>     | <span data-ttu-id="e55e4-123">此唯一值标识您正在授权的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e55e4-123">This unique value identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="e55e4-124">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="e55e4-124">Microsoft Search</span></span>     |
| <span data-ttu-id="e55e4-125">应用程序网站</span><span class="sxs-lookup"><span data-stu-id="e55e4-125">Application website</span></span>  | <span data-ttu-id="e55e4-126">此必填字段是在连接器设置过程中请求访问你的 Azure DevOps 实例的应用程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="e55e4-126">This required field is the URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span>  | <https://gcs.office.com/>                |
| <span data-ttu-id="e55e4-127">授权回调 URL</span><span class="sxs-lookup"><span data-stu-id="e55e4-127">Authorization callback URL</span></span>        | <span data-ttu-id="e55e4-128">授权服务器重定向到的必需回调 URL。</span><span class="sxs-lookup"><span data-stu-id="e55e4-128">A required callback URL that the authorization server redirects to.</span></span> | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| <span data-ttu-id="e55e4-129">授权作用域</span><span class="sxs-lookup"><span data-stu-id="e55e4-129">Authorized scopes</span></span> | <span data-ttu-id="e55e4-130">这是应用程序的访问范围</span><span class="sxs-lookup"><span data-stu-id="e55e4-130">This is the scope of access for the application</span></span> | <span data-ttu-id="e55e4-131">选择以下作用域：标识 (读取) 、工作项 (读取) 、变量组 (读取) 、项目和团队 (读取) 、Graph (读取) </span><span class="sxs-lookup"><span data-stu-id="e55e4-131">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="e55e4-132">在向上面的详细信息注册应用程序时，将获取将用于配置连接器的 **应用程序 ID** 和 **客户端密码** 。</span><span class="sxs-lookup"><span data-stu-id="e55e4-132">On registering the app with the details above, you will get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="e55e4-133">若要撤销对 Azure DevOps 中注册的任何应用程序的访问权限，请转到 Azure DevOps 实例右侧的 "用户设置"。</span><span class="sxs-lookup"><span data-stu-id="e55e4-133">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="e55e4-134">单击 "配置文件"，然后单击侧窗格的 "安全" 部分中的 "授权"。</span><span class="sxs-lookup"><span data-stu-id="e55e4-134">Click on Profile and then click on Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="e55e4-135">将鼠标悬停在授权的 OAuth 应用上，以查看应用程序详细信息一角的 "撤消" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e55e4-135">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="e55e4-136">连接设置</span><span class="sxs-lookup"><span data-stu-id="e55e4-136">Connection settings</span></span>

<span data-ttu-id="e55e4-137">在使用 Azure DevOps 注册 Microsoft Search 应用程序后，您可以完成 "连接设置" 步骤。</span><span class="sxs-lookup"><span data-stu-id="e55e4-137">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="e55e4-138">输入你的组织名称、应用 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="e55e4-138">Enter your organization name, App ID, and Client secret.</span></span>

![连接应用程序设置](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a><span data-ttu-id="e55e4-140">选择项目和字段</span><span class="sxs-lookup"><span data-stu-id="e55e4-140">Select projects and fields</span></span>

<span data-ttu-id="e55e4-141">您可以选择用于为整个组织或特定项目编制索引的连接。</span><span class="sxs-lookup"><span data-stu-id="e55e4-141">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="e55e4-142">如果选择对整个组织编制索引，则组织中所有项目中的项目都将获得索引。</span><span class="sxs-lookup"><span data-stu-id="e55e4-142">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="e55e4-143">在下一次爬网过程中创建新项目和项目时将对其编制索引。</span><span class="sxs-lookup"><span data-stu-id="e55e4-143">New projects and items will be indexed during the next crawl after they are created.</span></span> <span data-ttu-id="e55e4-144">如果选择单个项目，则只会对这些项目中的工作项编制索引。</span><span class="sxs-lookup"><span data-stu-id="e55e4-144">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![配置数据](media/ADO_Configure_data.png)

<span data-ttu-id="e55e4-146">接下来，选择您希望连接在继续之前对这些字段中的数据编制索引和预览的字段。</span><span class="sxs-lookup"><span data-stu-id="e55e4-146">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![选择属性](media/ADO_choose_properties.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="e55e4-148">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="e55e4-148">Manage search permissions</span></span>

<span data-ttu-id="e55e4-149">Azure DevOps 连接器当前仅支持 **所有人都能看到** 的搜索权限。</span><span class="sxs-lookup"><span data-stu-id="e55e4-149">The Azure DevOps connector currently only supports search permissions **Visible to Everyone**.</span></span> <span data-ttu-id="e55e4-150">已编制索引的数据将显示在所有用户的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="e55e4-150">Indexed data will appear in the search results for all users.</span></span>

## <a name="manage-search-schema"></a><span data-ttu-id="e55e4-151">管理搜索架构</span><span class="sxs-lookup"><span data-stu-id="e55e4-151">Manage search schema</span></span>

<span data-ttu-id="e55e4-152">配置搜索架构映射。</span><span class="sxs-lookup"><span data-stu-id="e55e4-152">Configure the search schema mapping.</span></span> <span data-ttu-id="e55e4-153">您可以选择哪些属性可供 **查询** 、可 **搜索** 和 **检索** 。</span><span class="sxs-lookup"><span data-stu-id="e55e4-153">You can choose which properties to make **queryable** , **searchable** and **retrievable**.</span></span>


## <a name="set-refresh-schedule"></a><span data-ttu-id="e55e4-154">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="e55e4-154">Set refresh schedule</span></span>

<span data-ttu-id="e55e4-155">Azure DevOps 连接器支持完全爬网和增量爬网的刷新计划。</span><span class="sxs-lookup"><span data-stu-id="e55e4-155">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="e55e4-156">完全爬网可查找以前同步到 Microsoft 搜索索引的已删除工作项。</span><span class="sxs-lookup"><span data-stu-id="e55e4-156">A full crawl finds deleted work items that were previously synced to the Microsoft Search index.</span></span> <span data-ttu-id="e55e4-157">将运行完全爬网以同步所有工作项。</span><span class="sxs-lookup"><span data-stu-id="e55e4-157">A full crawl runs to sync all the work items.</span></span> <span data-ttu-id="e55e4-158">若要同步新的工作项和对现有工作项的更新，您需要计划增量爬网。</span><span class="sxs-lookup"><span data-stu-id="e55e4-158">To sync new work items and updates to existing work items, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="e55e4-159">对于增量爬网，建议的日程安排为1小时，对于完全爬网，则为一天。</span><span class="sxs-lookup"><span data-stu-id="e55e4-159">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>
