---
title: 用于 Microsoft 搜索的 MediaWiki Graph 连接器
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
ms.openlocfilehash: 5922cf76aa112430f9f6e857066acd054182058c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031689"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="659ce-103">MediaWiki Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="659ce-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="659ce-104">通过 MediaWiki Graph 连接器，组织可以发现使用 MediaWiki 软件创建的 Wiki 数据，并编制数据索引。</span><span class="sxs-lookup"><span data-stu-id="659ce-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="659ce-105">此连接器将指定内容索引到 Microsoft 搜索中，并支持定期爬网，使索引保持最新。</span><span class="sxs-lookup"><span data-stu-id="659ce-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="659ce-106">阅读 [**适用于 Graph 连接器的**](configure-connector.md) 安装程序一文，了解 Graph 连接器的常规设置说明。</span><span class="sxs-lookup"><span data-stu-id="659ce-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="659ce-107">本文适用于配置、运行和监视 MediaWiki Graph 连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="659ce-107">This article is for anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="659ce-108">它补充了常规设置过程，并显示了仅适用于 MediaWiki Graph 连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="659ce-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="659ce-109">本文还包括有关 [限制的信息](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="659ce-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="659ce-110">步骤 1：在 Microsoft 365 管理中心添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="659ce-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="659ce-111">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="659ce-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="659ce-112">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="659ce-112">Step 2: Name the connection</span></span>

<span data-ttu-id="659ce-113">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="659ce-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="659ce-114">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="659ce-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="659ce-115">输入 Wiki **URL，** 然后 **从选项的** 下拉菜单中选择"身份验证"类型。</span><span class="sxs-lookup"><span data-stu-id="659ce-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="659ce-116">选项为 **None、Basic** 和 **OAuth 2.0 AAD。** </span><span class="sxs-lookup"><span data-stu-id="659ce-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="659ce-117">如果选择"**基本**"作为"身份验证"类型，则需要提供 Wiki **的用户名和密码**。</span><span class="sxs-lookup"><span data-stu-id="659ce-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="659ce-118">如果选择 **OAuth 2.0 AAD** 作为身份验证类型，则需要提供 Wiki 安装的资源 **ID。**</span><span class="sxs-lookup"><span data-stu-id="659ce-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="659ce-119">你还需要提供在 AAD 应用程序注册页上生成的客户端 **ID** 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="659ce-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="659ce-120">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="659ce-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="659ce-121">MediaWiki 连接器仅支持对所有人可见的搜索 **权限**。</span><span class="sxs-lookup"><span data-stu-id="659ce-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="659ce-122">索引数据将显示在搜索结果中，并且对组织中所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="659ce-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="659ce-123">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="659ce-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="659ce-124">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="659ce-124">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="659ce-125">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="659ce-125">Step 6: Manage schema</span></span>

<span data-ttu-id="659ce-126">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="659ce-126">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="659ce-127">步骤 7：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="659ce-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="659ce-128">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="659ce-128">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="659ce-129">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="659ce-129">Step 8: Review connection</span></span>

<span data-ttu-id="659ce-130">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="659ce-130">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="659ce-131">限制</span><span class="sxs-lookup"><span data-stu-id="659ce-131">Limitations</span></span>

<span data-ttu-id="659ce-132">MediaWiki 连接器在预览版本中有以下限制：</span><span class="sxs-lookup"><span data-stu-id="659ce-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="659ce-133">仅支持基于云的 Wiki。</span><span class="sxs-lookup"><span data-stu-id="659ce-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="659ce-134">仅支持使用 Azure Active Directory 或 Azure 身份验证的基本或 OAuth 2.0。</span><span class="sxs-lookup"><span data-stu-id="659ce-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="659ce-135">不支持为索引选择命名空间。</span><span class="sxs-lookup"><span data-stu-id="659ce-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="659ce-136">仅索引 Main、Category 和 File 命名空间。</span><span class="sxs-lookup"><span data-stu-id="659ce-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="659ce-137">不支持访问控制列表 (ACL) 。</span><span class="sxs-lookup"><span data-stu-id="659ce-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="659ce-138">因此，索引页对组织所有用户都是可见的。</span><span class="sxs-lookup"><span data-stu-id="659ce-138">Thus, indexed pages are visible to all users in the organization.</span></span>