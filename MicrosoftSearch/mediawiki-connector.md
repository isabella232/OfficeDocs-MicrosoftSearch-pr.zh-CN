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
description: 设置用于 Microsoft 搜索的 MediaWiki 连接器
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367637"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="329d8-103">MediaWiki 连接器</span><span class="sxs-lookup"><span data-stu-id="329d8-103">MediaWiki connector</span></span>

<span data-ttu-id="329d8-104">通过 MediaWiki 连接器，贵组织可以发现使用 MediaWiki 软件创建的 wiki 中的数据并对其编制索引。</span><span class="sxs-lookup"><span data-stu-id="329d8-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="329d8-105">此连接器将指定的内容索引到 Microsoft Search，并支持定期爬网以保持索引为最新。</span><span class="sxs-lookup"><span data-stu-id="329d8-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="329d8-106">本文适用于 Microsoft 365 管理员或任何配置、运行和监控 MediaWiki 连接器的人。</span><span class="sxs-lookup"><span data-stu-id="329d8-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="329d8-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="329d8-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="329d8-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="329d8-108">Connect to a data source</span></span>

<span data-ttu-id="329d8-109">输入您的 MediaWiki URL 和凭据以对连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="329d8-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="329d8-110">你将需要以下信息： **租户 ID**、 **资源 ID**、 **客户端 ID** 和 **客户端密码**。</span><span class="sxs-lookup"><span data-stu-id="329d8-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="329d8-111">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="329d8-111">Manage search permissions</span></span>

<span data-ttu-id="329d8-112">MediaWiki 连接器仅支持 **所有人都** 能看到的搜索权限。</span><span class="sxs-lookup"><span data-stu-id="329d8-112">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="329d8-113">索引数据显示在搜索结果中，并对组织中的所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="329d8-113">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="329d8-114">分配属性标签</span><span class="sxs-lookup"><span data-stu-id="329d8-114">Assign property labels</span></span>

<span data-ttu-id="329d8-115">通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。</span><span class="sxs-lookup"><span data-stu-id="329d8-115">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="329d8-116">虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。</span><span class="sxs-lookup"><span data-stu-id="329d8-116">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="329d8-117">管理架构</span><span class="sxs-lookup"><span data-stu-id="329d8-117">Manage schema</span></span>

<span data-ttu-id="329d8-118">在 " **管理架构** " 屏幕上，您可以选择更改架构属性， (可 **查询**、可 **搜索**、 **检索** 和 **可精简**) 与属性相关联，添加可选别名，然后选择 **Content** 属性。</span><span class="sxs-lookup"><span data-stu-id="329d8-118">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="329d8-119">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="329d8-119">Set the refresh schedule</span></span>

<span data-ttu-id="329d8-120">此计划将刷新已编制索引的数据，因此 wiki 的更改将反映在 Microsoft Search 中。</span><span class="sxs-lookup"><span data-stu-id="329d8-120">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="329d8-121">在指定的刷新间隔后，所有新页面、删除的页面、页面内容或元数据更改都会显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="329d8-121">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="329d8-122">爬网时间取决于 wiki 的大小。</span><span class="sxs-lookup"><span data-stu-id="329d8-122">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="329d8-123">目前，连接器会在每分钟50页面的周围进行爬网。</span><span class="sxs-lookup"><span data-stu-id="329d8-123">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="329d8-124">限制</span><span class="sxs-lookup"><span data-stu-id="329d8-124">Limitations</span></span>

<span data-ttu-id="329d8-125">在预览版本中，MediaWiki 连接器具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="329d8-125">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="329d8-126">仅支持基于云的 wiki。</span><span class="sxs-lookup"><span data-stu-id="329d8-126">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="329d8-127">仅支持基本或 OAuth 2.0 与 Azure Active Directory 或 Azure 身份验证。</span><span class="sxs-lookup"><span data-stu-id="329d8-127">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="329d8-128">不支持用于索引的命名空间选择。</span><span class="sxs-lookup"><span data-stu-id="329d8-128">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="329d8-129">仅索引 **主**、 **类别** 和 **文件** 命名空间。</span><span class="sxs-lookup"><span data-stu-id="329d8-129">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="329d8-130">不支持 (Acl) 的访问控制列表。</span><span class="sxs-lookup"><span data-stu-id="329d8-130">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="329d8-131">因此，索引页对组织中的所有用户都是可见的。</span><span class="sxs-lookup"><span data-stu-id="329d8-131">Thus, indexed pages are visible to all users in the organization.</span></span>
