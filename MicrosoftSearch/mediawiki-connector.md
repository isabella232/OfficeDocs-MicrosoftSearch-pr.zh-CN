---
title: Microsoft 搜索的 MediaWiki 连接器
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
description: 为 Microsoft 搜索设置 MediaWiki 连接器
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905946"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="df7ac-103">MediaWiki 连接器</span><span class="sxs-lookup"><span data-stu-id="df7ac-103">MediaWiki connector</span></span>

<span data-ttu-id="df7ac-104">通过 MediaWiki 连接器，组织可以发现使用 MediaWiki 软件创建的 Wiki 数据并编制数据索引。</span><span class="sxs-lookup"><span data-stu-id="df7ac-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="df7ac-105">此连接器将指定内容索引到 Microsoft 搜索中，并支持定期爬网，使索引保持最新。</span><span class="sxs-lookup"><span data-stu-id="df7ac-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="df7ac-106">本文适用于 Microsoft 365 管理员或配置、运行和监视 MediaWiki Graph 连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="df7ac-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="df7ac-107">它补充了"设置 Graph 连接器 ["文章中提供的一般](configure-connector.md) 说明。</span><span class="sxs-lookup"><span data-stu-id="df7ac-107">It supplements the general instructions provided in the [Set up your Graph connector](configure-connector.md) article.</span></span> <span data-ttu-id="df7ac-108">如果尚未这样做，请阅读整个"设置 Graph 连接器"文章以了解常规安装过程。</span><span class="sxs-lookup"><span data-stu-id="df7ac-108">If you have not already done so, read the entire Set up your Graph connector article to understand the general setup process.</span></span>

<span data-ttu-id="df7ac-109">下面列出了安装过程的每一步以及一条说明，指示你应遵循常规设置说明或仅适用于 MediaWiki Graph 连接器的其他说明。</span><span class="sxs-lookup"><span data-stu-id="df7ac-109">Each step in the setup process is listed below along with either a note that indicates you should follow the general setup instructions OR other instructions that apply to only MediaWiki Graph connectors.</span></span> <span data-ttu-id="df7ac-110">本文还包括有关 MediaWiki Graph [连接器的限制](#limitations) 的信息。</span><span class="sxs-lookup"><span data-stu-id="df7ac-110">This article also includes information about [Limitations](#limitations) for MediaWiki Graph connectors.</span></span> 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="df7ac-111">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器。</span><span class="sxs-lookup"><span data-stu-id="df7ac-111">Step 1: Add a Graph connector in the Microsoft 365 admin center.</span></span>
<span data-ttu-id="df7ac-112">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="df7ac-112">Follow the general setup instructions.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="df7ac-113">步骤 2：命名连接。</span><span class="sxs-lookup"><span data-stu-id="df7ac-113">Step 2: Name the connection.</span></span>
<span data-ttu-id="df7ac-114">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="df7ac-114">Follow the general setup instructions.</span></span>
 
## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="df7ac-115">步骤 3：配置连接设置。</span><span class="sxs-lookup"><span data-stu-id="df7ac-115">Step 3: Configure the connection settings.</span></span>
<span data-ttu-id="df7ac-116">输入 **Wiki URL，** 然后从选项的下拉菜单中选择身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="df7ac-116">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="df7ac-117">选项为 **None、Basic** 和 **OAuth 2.0 AAD。** </span><span class="sxs-lookup"><span data-stu-id="df7ac-117">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="df7ac-118">如果选择"**基本**"作为身份验证类型，则需要提供 **Wiki** **的用户名和密码。**</span><span class="sxs-lookup"><span data-stu-id="df7ac-118">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="df7ac-119">如果选择 **OAuth 2.0 AAD** 作为身份验证类型，则需要提供 Wiki **安装的资源** ID。</span><span class="sxs-lookup"><span data-stu-id="df7ac-119">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="df7ac-120">你还需要提供在 AAD 应用程序注册 **页上生成的客户端** **ID** 和客户端密码。</span><span class="sxs-lookup"><span data-stu-id="df7ac-120">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span> 

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="df7ac-121">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="df7ac-121">Step 4: Manage search permissions</span></span>
<span data-ttu-id="df7ac-122">MediaWiki 连接器仅支持对所有人可见的搜索 **权限**。</span><span class="sxs-lookup"><span data-stu-id="df7ac-122">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="df7ac-123">索引数据将显示在搜索结果中，并且对组织所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="df7ac-123">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="df7ac-124">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="df7ac-124">Step 5: Assign property labels</span></span>
<span data-ttu-id="df7ac-125">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="df7ac-125">Follow the general setup instructions.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="df7ac-126">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="df7ac-126">Step 6: Manage schema</span></span>
<span data-ttu-id="df7ac-127">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="df7ac-127">Follow the general setup instructions.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="df7ac-128">步骤 7：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="df7ac-128">Step 7: Choose refresh settings</span></span>
<span data-ttu-id="df7ac-129">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="df7ac-129">Follow the general setup instructions.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="df7ac-130">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="df7ac-130">Step 8: Review connection</span></span>
<span data-ttu-id="df7ac-131">按照常规设置说明操作。</span><span class="sxs-lookup"><span data-stu-id="df7ac-131">Follow the general setup instructions.</span></span>

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="df7ac-132">限制</span><span class="sxs-lookup"><span data-stu-id="df7ac-132">Limitations</span></span>
<span data-ttu-id="df7ac-133">MediaWiki 连接器在预览版本中有以下限制：</span><span class="sxs-lookup"><span data-stu-id="df7ac-133">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="df7ac-134">仅支持基于云的 Wiki。</span><span class="sxs-lookup"><span data-stu-id="df7ac-134">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="df7ac-135">仅支持使用 Azure Active Directory 或 Azure 身份验证的基本或 OAuth 2.0。</span><span class="sxs-lookup"><span data-stu-id="df7ac-135">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="df7ac-136">不支持为索引选择命名空间。</span><span class="sxs-lookup"><span data-stu-id="df7ac-136">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="df7ac-137">仅索引主命名空间、类别命名空间和文件命名空间。</span><span class="sxs-lookup"><span data-stu-id="df7ac-137">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="df7ac-138">不支持访问控制列表 (ACL) 。</span><span class="sxs-lookup"><span data-stu-id="df7ac-138">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="df7ac-139">因此，索引页对组织中所有用户都是可见的。</span><span class="sxs-lookup"><span data-stu-id="df7ac-139">Thus, indexed pages are visible to all users in the organization.</span></span>
