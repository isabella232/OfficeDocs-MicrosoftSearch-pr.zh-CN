---
title: 用于 Microsoft 搜索的 Azure DevOps Graph 连接器
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
description: 为 Microsoft 搜索设置 Azure DevOps Graph 连接器
ms.openlocfilehash: 3d922a5384de8bf0ef3c6dfd80bd67ad9170eb66
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084935"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="77973-103">Azure DevOps Graph 连接器 (预览) </span><span class="sxs-lookup"><span data-stu-id="77973-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="77973-104">Azure DevOps Graph 连接器允许组织在其 Azure DevOps 服务实例中为工作项编制索引。</span><span class="sxs-lookup"><span data-stu-id="77973-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="77973-105">配置 Azure DevOps 中的连接器和索引内容后，最终用户可以在 Microsoft 搜索中搜索这些项目。</span><span class="sxs-lookup"><span data-stu-id="77973-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="77973-106">阅读 [**Graph 连接器的安装程序**](configure-connector.md) 文章，了解一般的 Graph 连接器设置过程。</span><span class="sxs-lookup"><span data-stu-id="77973-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="77973-107">本文适用于配置、运行和监视 ServiceNow Graph 连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="77973-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="77973-108">它补充了常规安装过程，并显示了仅适用于 ServiceNow Graph 连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="77973-108">It supplements the general setup process, and shows instructions that apply only for the ServiceNow Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="77973-109">Azure DevOps 连接器仅支持 Azure DevOps 云服务。</span><span class="sxs-lookup"><span data-stu-id="77973-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="77973-110">此连接器不支持 Azure DevOps Server 2019、TFS 2018、TFS 2017、TFS 2015 和 TFS 2013。</span><span class="sxs-lookup"><span data-stu-id="77973-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="77973-111">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="77973-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="77973-112">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="77973-112">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="77973-113">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="77973-113">Step 2: Name the connection</span></span>

<span data-ttu-id="77973-114">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="77973-114">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="77973-115">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="77973-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="77973-116">若要连接到 Azure DevOps 实例，需要 Azure [DevOps](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) 组织名称、应用 ID 和客户端密码进行 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="77973-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="77973-117">注册应用</span><span class="sxs-lookup"><span data-stu-id="77973-117">Register an app</span></span>

<span data-ttu-id="77973-118">在 Azure DevOps 中注册应用，以便 Microsoft 搜索应用可以访问该实例。</span><span class="sxs-lookup"><span data-stu-id="77973-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="77973-119">若要了解更多信息，请参阅 Azure DevOps 文档，了解如何 [注册应用](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="77973-119">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true).</span></span>

<span data-ttu-id="77973-120">下表提供了有关如何填写应用程序注册表单的指导：</span><span class="sxs-lookup"><span data-stu-id="77973-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="77973-121">必填字段</span><span class="sxs-lookup"><span data-stu-id="77973-121">Mandatory Fields</span></span> | <span data-ttu-id="77973-122">Description</span><span class="sxs-lookup"><span data-stu-id="77973-122">Description</span></span> | <span data-ttu-id="77973-123">建议值</span><span class="sxs-lookup"><span data-stu-id="77973-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="77973-124">公司名称</span><span class="sxs-lookup"><span data-stu-id="77973-124">Company Name</span></span>         | <span data-ttu-id="77973-125">公司的名称。</span><span class="sxs-lookup"><span data-stu-id="77973-125">The name of your company.</span></span> | <span data-ttu-id="77973-126">使用适当的值</span><span class="sxs-lookup"><span data-stu-id="77973-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="77973-127">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="77973-127">Application name</span></span>     | <span data-ttu-id="77973-128">标识要授权的应用程序的唯一值。</span><span class="sxs-lookup"><span data-stu-id="77973-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="77973-129">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="77973-129">Microsoft Search</span></span>     |
| <span data-ttu-id="77973-130">应用程序网站</span><span class="sxs-lookup"><span data-stu-id="77973-130">Application website</span></span>  | <span data-ttu-id="77973-131">在连接器设置过程中请求访问 Azure DevOps 实例的应用程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="77973-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="77973-132"> (必需) 。</span><span class="sxs-lookup"><span data-stu-id="77973-132">(Required).</span></span>  | <span data-ttu-id="77973-133"> https://<span>gcs.office。</span>com/</span><span class="sxs-lookup"><span data-stu-id="77973-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="77973-134">授权回调 URL</span><span class="sxs-lookup"><span data-stu-id="77973-134">Authorization callback URL</span></span>        | <span data-ttu-id="77973-135">授权服务器重定向到的必需回调 URL。</span><span class="sxs-lookup"><span data-stu-id="77973-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="77973-136"> https://<span>gcs.office。</span>com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="77973-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="77973-137">授权范围</span><span class="sxs-lookup"><span data-stu-id="77973-137">Authorized scopes</span></span> | <span data-ttu-id="77973-138">应用程序的访问范围</span><span class="sxs-lookup"><span data-stu-id="77973-138">The scope of access for the application</span></span> | <span data-ttu-id="77973-139">选择以下范围：标识 (读取) 、工作项 (读取) 、变量组 (读取) 、项目和团队 (读取) 、Graph (读取) </span><span class="sxs-lookup"><span data-stu-id="77973-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="77973-140">使用上述详细信息注册应用时，将获取将用于配置连接器的应用 **ID** 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="77973-140">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="77973-141">若要撤销对在 Azure DevOps 中注册的任何应用的访问权限，请转到 Azure DevOps 实例右上方的用户设置。</span><span class="sxs-lookup"><span data-stu-id="77973-141">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="77973-142">选择"配置文件"，然后在侧窗格的"安全性"部分选择"授权"。</span><span class="sxs-lookup"><span data-stu-id="77973-142">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="77973-143">将鼠标悬停在已授权的 OAuth 应用上，以查看应用详细信息的一角的"撤销"按钮。</span><span class="sxs-lookup"><span data-stu-id="77973-143">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="77973-144">连接设置</span><span class="sxs-lookup"><span data-stu-id="77973-144">Connection settings</span></span>

<span data-ttu-id="77973-145">向 Azure DevOps 注册 Microsoft 搜索应用后，可以完成连接设置步骤。</span><span class="sxs-lookup"><span data-stu-id="77973-145">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="77973-146">输入组织名称、应用 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="77973-146">Enter your organization name, App ID, and Client secret.</span></span>

![连接应用程序设置](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="77973-148">配置数据：选择项目和字段</span><span class="sxs-lookup"><span data-stu-id="77973-148">Configure data: select projects and fields</span></span>

<span data-ttu-id="77973-149">您可以选择连接来为整个组织或特定项目编制索引。</span><span class="sxs-lookup"><span data-stu-id="77973-149">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="77973-150">如果选择为整个组织编制索引，则组织的所有项目中的项目都将编制索引。</span><span class="sxs-lookup"><span data-stu-id="77973-150">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="77973-151">创建新项目和项目后，将在下一次爬网过程中对这些项目编制索引。</span><span class="sxs-lookup"><span data-stu-id="77973-151">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="77973-152">如果您选择单个项目，则只会对这些项目中的工作项编制索引。</span><span class="sxs-lookup"><span data-stu-id="77973-152">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![配置数据](media/ADO_Configure_data.png)

<span data-ttu-id="77973-154">接下来，在继续操作之前，选择您希望连接索引和预览这些字段中数据的字段。</span><span class="sxs-lookup"><span data-stu-id="77973-154">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![选择属性](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="77973-156">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="77973-156">Step 4: Manage search permissions</span></span>

<span data-ttu-id="77973-157">Azure DevOps 连接器支持仅对此数据源或  \*\*\*\* 所有人具有访问权限的用户可见的 **搜索权限**。</span><span class="sxs-lookup"><span data-stu-id="77973-157">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="77973-158">如果选择"仅有权访问此数据源的用户"，则基于对 Azure DevOps 中组织、项目或区域路径级别用户或组的权限，已编制索引的数据将显示在具有访问权限的用户的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="77973-158">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="77973-159">如果选择" **每个人**"，则索引数据将显示在所有用户的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="77973-159">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="77973-160">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="77973-160">Step 5: Assign property labels</span></span>

<span data-ttu-id="77973-161">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="77973-161">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="77973-162">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="77973-162">Step 6: Manage schema</span></span>

<span data-ttu-id="77973-163">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="77973-163">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="77973-164">步骤 7：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="77973-164">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="77973-165">Azure DevOps 连接器支持完全爬网和增量爬网的刷新计划。</span><span class="sxs-lookup"><span data-stu-id="77973-165">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="77973-166">对于增量爬网，建议计划为一小时，完全爬网为一天。</span><span class="sxs-lookup"><span data-stu-id="77973-166">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="77973-167">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="77973-167">Step 8: Review connection</span></span>

<span data-ttu-id="77973-168">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="77973-168">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
