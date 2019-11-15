---
title: Microsoft 搜索的 MediaWiki 连接器
ms.author: v-pamcn
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
description: 设置用于 Microsoft 搜索的 MediaWiki 连接器
ms.openlocfilehash: 2aa0ef494aa42b1a7364ec68f6532dec737b9c25
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626960"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="d15e7-103">MediaWiki 连接器</span><span class="sxs-lookup"><span data-stu-id="d15e7-103">MediaWiki connector</span></span>

<span data-ttu-id="d15e7-104">通过 MediaWiki 连接器，贵组织可以发现使用 MediaWiki 软件创建的 wiki 中的数据并对其编制索引。</span><span class="sxs-lookup"><span data-stu-id="d15e7-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="d15e7-105">此连接器将指定的内容索引到 Microsoft Search，并支持定期爬网以保持索引为最新。</span><span class="sxs-lookup"><span data-stu-id="d15e7-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="d15e7-106">本文适用于 Microsoft 365 管理员或任何配置、运行和监控 MediaWiki 连接器的人。</span><span class="sxs-lookup"><span data-stu-id="d15e7-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="d15e7-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="d15e7-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="d15e7-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="d15e7-108">Connect to a data source</span></span>
<span data-ttu-id="d15e7-109">输入您的 MediaWiki URL 和凭据以对连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d15e7-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="d15e7-110">你将需要以下信息：**租户 ID**、**资源 ID**、**客户端 ID**和**客户端密码**。</span><span class="sxs-lookup"><span data-stu-id="d15e7-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="d15e7-111">管理搜索架构</span><span class="sxs-lookup"><span data-stu-id="d15e7-111">Manage the search schema</span></span>
<span data-ttu-id="d15e7-112">成功连接后，配置搜索架构映射。</span><span class="sxs-lookup"><span data-stu-id="d15e7-112">After successful connection, configure the search schema mapping.</span></span> <span data-ttu-id="d15e7-113">您可以选择哪些属性可供**查询**、**搜索**和**检索**。</span><span class="sxs-lookup"><span data-stu-id="d15e7-113">You can choose which properties to make **queryable**, **searchable**, and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="d15e7-114">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="d15e7-114">Manage search permissions</span></span>
<span data-ttu-id="d15e7-115">MediaWiki 连接器仅支持**所有人都**能看到的搜索权限。</span><span class="sxs-lookup"><span data-stu-id="d15e7-115">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="d15e7-116">索引数据显示在搜索结果中，并对组织中的所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="d15e7-116">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="d15e7-117">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="d15e7-117">Set the refresh schedule</span></span> 
<span data-ttu-id="d15e7-118">此计划将刷新已编制索引的数据，因此 wiki 的更改将反映在 Microsoft Search 中。</span><span class="sxs-lookup"><span data-stu-id="d15e7-118">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="d15e7-119">在指定的刷新间隔后，所有新页面、删除的页面、页面内容或元数据更改都会显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="d15e7-119">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="d15e7-120">爬网时间取决于 wiki 的大小。</span><span class="sxs-lookup"><span data-stu-id="d15e7-120">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="d15e7-121">目前，连接器会在每分钟50页面的周围进行爬网。</span><span class="sxs-lookup"><span data-stu-id="d15e7-121">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="d15e7-122">限制</span><span class="sxs-lookup"><span data-stu-id="d15e7-122">Limitations</span></span> 
<span data-ttu-id="d15e7-123">在预览版本中，MediaWiki 连接器具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="d15e7-123">The MediaWiki connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="d15e7-124">仅支持基于云的 wiki。</span><span class="sxs-lookup"><span data-stu-id="d15e7-124">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="d15e7-125">仅支持基本或 OAuth 2.0 与 Azure Active Directory 或 Azure 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d15e7-125">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="d15e7-126">不支持用于索引的命名空间选择。</span><span class="sxs-lookup"><span data-stu-id="d15e7-126">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="d15e7-127">仅索引**主**、**类别**和**文件**命名空间。</span><span class="sxs-lookup"><span data-stu-id="d15e7-127">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="d15e7-128">不支持访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="d15e7-128">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="d15e7-129">因此，索引页对组织中的所有用户都是可见的。</span><span class="sxs-lookup"><span data-stu-id="d15e7-129">Thus, indexed pages are visible to all users in the organization.</span></span>
