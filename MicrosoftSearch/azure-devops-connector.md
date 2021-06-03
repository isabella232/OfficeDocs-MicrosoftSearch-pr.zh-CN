---
title: Azure DevOps Graph Microsoft 搜索的连接器
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
description: 为 Microsoft 搜索Azure DevOps Graph连接器
ms.openlocfilehash: bfe04a022360a968424b673ad03ba05f27c8c333
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720949"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="6fb2f-103">Azure DevOps Graph连接器 (预览) </span><span class="sxs-lookup"><span data-stu-id="6fb2f-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="6fb2f-104">此Azure DevOps Graph连接器允许您的组织在其服务实例中为工作项Azure DevOps索引。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="6fb2f-105">配置连接器并索引来自Azure DevOps后，最终用户可以在 Microsoft 搜索中搜索这些项目。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="6fb2f-106">阅读 [**Graph 连接器**](configure-connector.md)的安装程序一文，了解 Graph 连接器的一般设置说明。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="6fb2f-107">本文适用于配置、运行和监视 Azure DevOps Graph 连接器。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="6fb2f-108">它补充了常规安装过程，并显示了仅适用于 Azure DevOps Graph 连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="6fb2f-109">the Azure DevOps connector supports only the Azure DevOps cloud service.</span><span class="sxs-lookup"><span data-stu-id="6fb2f-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="6fb2f-110">Azure DevOps Server 2019、TFS 2018、TFS 2017、TFS 2015 和 TFS 2013 不受此连接器支持。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6fb2f-111">步骤 1：在Graph管理中心中添加Microsoft 365连接器</span><span class="sxs-lookup"><span data-stu-id="6fb2f-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6fb2f-112">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-112">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="6fb2f-113">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="6fb2f-113">Step 2: Name the connection</span></span>

<span data-ttu-id="6fb2f-114">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-114">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="6fb2f-115">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="6fb2f-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="6fb2f-116">若要连接到您的 Azure DevOps实例，您需要您的 Azure DevOps名称、其应用程序[](/azure/devops/organizations/accounts/create-organization)ID 和客户端密码进行 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="6fb2f-117">注册应用</span><span class="sxs-lookup"><span data-stu-id="6fb2f-117">Register an app</span></span>

<span data-ttu-id="6fb2f-118">在应用程序中注册Azure DevOps，以便 Microsoft 搜索应用可以访问该实例。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="6fb2f-119">若要了解更多信息，请参阅Azure DevOps注册应用[的文档](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-119">To learn more, see Azure DevOps documentation on how to [register an app](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="6fb2f-120">下表提供了有关如何填写应用程序注册表单的指导：</span><span class="sxs-lookup"><span data-stu-id="6fb2f-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="6fb2f-121">必需字段</span><span class="sxs-lookup"><span data-stu-id="6fb2f-121">Mandatory Fields</span></span> | <span data-ttu-id="6fb2f-122">说明</span><span class="sxs-lookup"><span data-stu-id="6fb2f-122">Description</span></span> | <span data-ttu-id="6fb2f-123">建议值</span><span class="sxs-lookup"><span data-stu-id="6fb2f-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="6fb2f-124">公司名称</span><span class="sxs-lookup"><span data-stu-id="6fb2f-124">Company Name</span></span>         | <span data-ttu-id="6fb2f-125">公司的名称。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-125">The name of your company.</span></span> | <span data-ttu-id="6fb2f-126">使用适当的值</span><span class="sxs-lookup"><span data-stu-id="6fb2f-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="6fb2f-127">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="6fb2f-127">Application name</span></span>     | <span data-ttu-id="6fb2f-128">标识要授权的应用程序的唯一值。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="6fb2f-129">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="6fb2f-129">Microsoft Search</span></span>     |
| <span data-ttu-id="6fb2f-130">应用程序网站</span><span class="sxs-lookup"><span data-stu-id="6fb2f-130">Application website</span></span>  | <span data-ttu-id="6fb2f-131">在连接器设置期间请求访问您的 Azure DevOps 实例的应用程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="6fb2f-132"> (必需) 。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-132">(Required).</span></span>  | <span data-ttu-id="6fb2f-133"> https://<span>gcs.office。</span>com/</span><span class="sxs-lookup"><span data-stu-id="6fb2f-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="6fb2f-134">授权回调 URL</span><span class="sxs-lookup"><span data-stu-id="6fb2f-134">Authorization callback URL</span></span>        | <span data-ttu-id="6fb2f-135">授权服务器重定向到的必需回调 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="6fb2f-136"> https://<span>gcs.office。</span>com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="6fb2f-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="6fb2f-137">授权范围</span><span class="sxs-lookup"><span data-stu-id="6fb2f-137">Authorized scopes</span></span> | <span data-ttu-id="6fb2f-138">应用程序的访问范围</span><span class="sxs-lookup"><span data-stu-id="6fb2f-138">The scope of access for the application</span></span> | <span data-ttu-id="6fb2f-139">选择以下范围：Identity (read) 、Work Items (read) 、Variable Groups (read) 、Project and team (read) ， Graph (read) </span><span class="sxs-lookup"><span data-stu-id="6fb2f-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

>[!IMPORTANT]
><span data-ttu-id="6fb2f-140">你为应用选择的授权范围应该与上面列出的范围完全匹配。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-140">The authorized scopes that you select for the app should match the scopes exactly as listed above.</span></span> <span data-ttu-id="6fb2f-141">如果在列表中省略其中一个授权范围，或添加另一个范围，授权将失败。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-141">If you omit one of the authorized scopes in the list, or add another scope, the authorization will fail.</span></span>

<span data-ttu-id="6fb2f-142">使用上述详细信息注册应用时，你可获取将用于配置连接器的应用 **ID** 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-142">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="6fb2f-143">若要撤销对在 Azure DevOps 中注册的任何应用的访问权限，请转到你的 Azure DevOps 实例的右上方的用户设置。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-143">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="6fb2f-144">选择"配置文件"，然后在侧窗格的"安全性"部分选择"授权"。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-144">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="6fb2f-145">将鼠标悬停在授权 OAuth 应用上方，即可看到应用详细信息右上角的"撤销"按钮。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-145">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="6fb2f-146">连接设置</span><span class="sxs-lookup"><span data-stu-id="6fb2f-146">Connection settings</span></span>

<span data-ttu-id="6fb2f-147">向 Microsoft Search 应用注册Azure DevOps，可以完成连接设置步骤。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-147">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="6fb2f-148">输入组织名称、应用 ID 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-148">Enter your organization name, App ID, and Client secret.</span></span>

![连接应用程序设置](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="6fb2f-150">配置数据：选择项目和字段</span><span class="sxs-lookup"><span data-stu-id="6fb2f-150">Configure data: select projects and fields</span></span>

<span data-ttu-id="6fb2f-151">您可以选择连接来为整个组织或特定项目编制索引。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-151">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="6fb2f-152">如果选择为整个组织编制索引，则组织的所有项目中的项目都将编制索引。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-152">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="6fb2f-153">创建新项目和项目后，将在下一次爬网过程中对这些项目编制索引。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-153">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="6fb2f-154">如果您选择单个项目，则只会对这些项目中的工作项编制索引。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-154">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![配置数据](media/ADO_Configure_data.png)

<span data-ttu-id="6fb2f-156">接下来，选择您希望连接在这些字段中编制索引和预览数据的字段，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-156">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![选择属性](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="6fb2f-158">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="6fb2f-158">Step 4: Manage search permissions</span></span>

<span data-ttu-id="6fb2f-159">the Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span><span class="sxs-lookup"><span data-stu-id="6fb2f-159">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="6fb2f-160">如果选择"仅具有此数据源访问权限的用户"，索引数据将显示在搜索结果中，这些用户基于对 Azure DevOps 中组织、Project 或区域路径级别的用户或组的权限来访问它们。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-160">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="6fb2f-161">如果选择" **任何人"，** 则索引数据将显示在所有用户的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-161">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="6fb2f-162">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="6fb2f-162">Step 5: Assign property labels</span></span>

<span data-ttu-id="6fb2f-163">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-163">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="6fb2f-164">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="6fb2f-164">Step 6: Manage schema</span></span>

<span data-ttu-id="6fb2f-165">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-165">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="6fb2f-166">步骤 7：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="6fb2f-166">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="6fb2f-167">该Azure DevOps连接器支持完全爬网和增量爬网的刷新计划。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-167">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="6fb2f-168">建议的增量爬网计划为 1 小时，完全爬网计划为 1 天。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-168">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="6fb2f-169">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="6fb2f-169">Step 8: Review connection</span></span>

<span data-ttu-id="6fb2f-170">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-170">Follow the general [setup instructions](./configure-connector.md).</span></span>

>[!TIP]
><span data-ttu-id="6fb2f-171">**默认结果类型**</span><span class="sxs-lookup"><span data-stu-id="6fb2f-171">**Default Result type**</span></span>
>* <span data-ttu-id="6fb2f-172">连接器Azure DevOps连接器发布[后](./customize-search-page.md#step-2-create-the-result-types)自动注册结果类型。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-172">The Azure DevOps connector automatically registers a [result type](./customize-search-page.md#step-2-create-the-result-types) once the connector is published.</span></span> <span data-ttu-id="6fb2f-173">结果类型使用基于步骤 3[](./customize-results-layout.md)中选定的字段的动态生成的结果布局。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-173">The result type uses a dynamically generated [result layout](./customize-results-layout.md) based on the fields selected in step 3.</span></span> 
>* <span data-ttu-id="6fb2f-174">可以通过导航到管理中心中的结果类型来管理 [**结果**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)[Microsoft 365类型](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-174">You can manage the result type by navigating to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="6fb2f-175">默认结果类型将命名为 `ConnectionId` "Default"。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-175">The default result type will be named as "`ConnectionId`Default".</span></span> <span data-ttu-id="6fb2f-176">例如，如果你的连接 ID 是 `AzureDevOps` ，结果布局将命名为："AzureDevOpsDefault"</span><span class="sxs-lookup"><span data-stu-id="6fb2f-176">For example, if your connection id is `AzureDevOps`, your result layout will be named: "AzureDevOpsDefault"</span></span>
>* <span data-ttu-id="6fb2f-177">此外，还可以选择创建您自己的结果类型（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="6fb2f-177">Also, you can choose to create your own result type if needed.</span></span>

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->