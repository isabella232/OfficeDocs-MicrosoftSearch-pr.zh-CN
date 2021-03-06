---
title: Microsoft 搜索的 MediaWiki Graph 连接器
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
description: 为 Microsoft 搜索设置 MediaWiki Graph 连接器
ms.openlocfilehash: 1c2908de859056ccb26b862820e8b3be7a158569
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508766"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="ddfae-103">MediaWiki Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="ddfae-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="ddfae-104">通过 MediaWiki Graph 连接器，组织可以发现使用 MediaWiki 软件创建的 Wiki 数据，并编制数据索引。</span><span class="sxs-lookup"><span data-stu-id="ddfae-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="ddfae-105">此连接器将指定内容索引到 Microsoft 搜索中，并支持定期爬网，使索引保持最新。</span><span class="sxs-lookup"><span data-stu-id="ddfae-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="ddfae-106">阅读 [**Graph 连接器的安装程序**](configure-connector.md) 文章，了解一般 Graph 连接器设置说明。</span><span class="sxs-lookup"><span data-stu-id="ddfae-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="ddfae-107">本文适用于配置、运行和监视 MediaWiki Graph 连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="ddfae-107">This article is for anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="ddfae-108">它补充了常规安装过程，并显示了仅适用于 MediaWiki Graph 连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="ddfae-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="ddfae-109">本文还包括有关 [限制的信息](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="ddfae-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ddfae-110">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="ddfae-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ddfae-111">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="ddfae-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="ddfae-112">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="ddfae-112">Step 2: Name the connection</span></span>

<span data-ttu-id="ddfae-113">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="ddfae-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="ddfae-114">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="ddfae-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="ddfae-115">输入 **Wiki URL，** 然后 **从** 选项的下拉菜单中选择身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="ddfae-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="ddfae-116">选项包括 **"无\*\*\*\*"、"基本**"**和"OAuth 2.0 AAD"。**</span><span class="sxs-lookup"><span data-stu-id="ddfae-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="ddfae-117">如果选择"**基本**"作为身份验证类型，则需要提供 **Wiki** **的用户名和密码。**</span><span class="sxs-lookup"><span data-stu-id="ddfae-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="ddfae-118">如果选择 **OAuth 2.0 AAD** 作为身份验证类型，则需要提供 Wiki 安装的资源 **ID。**</span><span class="sxs-lookup"><span data-stu-id="ddfae-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="ddfae-119">你还需要提供在 AAD 应用程序注册页上生成的客户端 **ID** 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="ddfae-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="ddfae-120">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="ddfae-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="ddfae-121">MediaWiki 连接器仅支持对所有人可见的搜索 **权限**。</span><span class="sxs-lookup"><span data-stu-id="ddfae-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="ddfae-122">索引数据将显示在搜索结果中，并且对组织中的所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="ddfae-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="ddfae-123">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="ddfae-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="ddfae-124">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="ddfae-124">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="ddfae-125">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="ddfae-125">Step 6: Manage schema</span></span>

<span data-ttu-id="ddfae-126">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="ddfae-126">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="ddfae-127">步骤 7：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="ddfae-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="ddfae-128">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="ddfae-128">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="ddfae-129">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="ddfae-129">Step 8: Review connection</span></span>

<span data-ttu-id="ddfae-130">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="ddfae-130">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="ddfae-131">限制</span><span class="sxs-lookup"><span data-stu-id="ddfae-131">Limitations</span></span>

<span data-ttu-id="ddfae-132">MediaWiki 连接器在预览版中具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="ddfae-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="ddfae-133">仅支持基于云的 Wiki。</span><span class="sxs-lookup"><span data-stu-id="ddfae-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="ddfae-134">仅支持使用 Azure Active Directory 或 Azure 身份验证的基本或 OAuth 2.0。</span><span class="sxs-lookup"><span data-stu-id="ddfae-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="ddfae-135">不支持为索引选择命名空间。</span><span class="sxs-lookup"><span data-stu-id="ddfae-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="ddfae-136">仅索引主命名空间、类别命名空间和文件命名空间。</span><span class="sxs-lookup"><span data-stu-id="ddfae-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="ddfae-137">不支持访问控制列表和 (ACL) 。</span><span class="sxs-lookup"><span data-stu-id="ddfae-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="ddfae-138">因此，索引页对组织中的所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="ddfae-138">Thus, indexed pages are visible to all users in the organization.</span></span>
