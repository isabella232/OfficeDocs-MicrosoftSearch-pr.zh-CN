---
title: 用于 Microsoft 搜索的 Azure Data Lake 连接器
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 为 Microsoft 搜索设置 Azure Data Lake Storage Gen2 连接器
ms.openlocfilehash: 8891c9a1fdf5397c397a941b5131f014db9e7a54
ms.sourcegitcommit: 597c338bf9c1c425747ac74a9a1ae57c5e8957ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49920719"
---
# <a name="azure-data-lake-storage-gen2-connector"></a><span data-ttu-id="1e254-103">Azure Data Lake Storage Gen2 连接器</span><span class="sxs-lookup"><span data-stu-id="1e254-103">Azure Data Lake Storage Gen2 connector</span></span>

<span data-ttu-id="1e254-104">借助 Azure Data Lake Storage Gen2 连接器，贵组织用户可以搜索存储在 [Azure Blob](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) 存储和 [Azure Data Lake Gen 2 存储](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) 帐户中的文件。</span><span class="sxs-lookup"><span data-stu-id="1e254-104">With the Azure Data Lake Storage Gen2 connector, users in your organization can search for files stored in [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

<span data-ttu-id="1e254-105">本文适用于 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理员或配置、运行和监视 Azure Data Lake Storage Gen2 连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="1e254-105">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="1e254-106">它概述了连接器配置、功能、限制和疑难解答技术。</span><span class="sxs-lookup"><span data-stu-id="1e254-106">It gives an overview of the connector configuration, capabilities, limitations, and troubleshooting techniques.</span></span> <span data-ttu-id="1e254-107">在本文中，我们将 *Azure 存储* 用作 Azure [Blob](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) 存储和 [Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)存储的通用术语。</span><span class="sxs-lookup"><span data-stu-id="1e254-107">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="1e254-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="1e254-108">Connect to a data source</span></span>

### <a name="primary-storage-connection-string"></a><span data-ttu-id="1e254-109">主存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="1e254-109">Primary storage connection string</span></span>

<span data-ttu-id="1e254-110">在 **"身份验证和配置"** 屏幕上，提供主存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="1e254-110">On the **Authentication and config** screen, provide the Primary Storage Connection String.</span></span> <span data-ttu-id="1e254-111">该字符串是允许访问存储帐户的必需字符串。</span><span class="sxs-lookup"><span data-stu-id="1e254-111">That string is required to allow access to your storage account.</span></span> <span data-ttu-id="1e254-112">若要查找连接字符串，请转到 [Azure](https://ms.portal.azure.com/#home) 门户并导航到相关 Azure **存储帐户的** "密钥"部分。</span><span class="sxs-lookup"><span data-stu-id="1e254-112">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span> <span data-ttu-id="1e254-113">将连接字符串复制并粘贴到屏幕上的相应字段中。</span><span class="sxs-lookup"><span data-stu-id="1e254-113">Copy and paste the connection string in the appropriate field on the screen.</span></span>

<span data-ttu-id="1e254-114">如果不希望在主存储连接字符串 (中提供 **AccountKey**) 参数，则需要为以下角色授予对 Graph 连接器服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1e254-114">If you do not prefer to provide the **AccountKey** (a parameter in the primary storage connection string), you will need to grant access to our Graph Connectors Service for the following roles.</span></span> <span data-ttu-id="1e254-115"> (此功能仅受分层存储支持。</span><span class="sxs-lookup"><span data-stu-id="1e254-115">(This feature is only supported for hierarchical storage.</span></span> <span data-ttu-id="1e254-116">传统 Blob 存储必须提供 AccountKey.) </span><span class="sxs-lookup"><span data-stu-id="1e254-116">Traditional Blob storage will have to provide AccountKey.)</span></span>
* <span data-ttu-id="1e254-117">存储 Blob 数据读取器</span><span class="sxs-lookup"><span data-stu-id="1e254-117">Storage Blob Data Reader</span></span>
* <span data-ttu-id="1e254-118">存储队列数据参与者</span><span class="sxs-lookup"><span data-stu-id="1e254-118">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="1e254-119">存储 Blob Delegator</span><span class="sxs-lookup"><span data-stu-id="1e254-119">Storage Blob Delegator</span></span>

<span data-ttu-id="1e254-120">导航到 Azure **存储帐户** 的"访问控制"选项卡，并按照其中的说明授予对以下应用的访问权限：</span><span class="sxs-lookup"><span data-stu-id="1e254-120">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="1e254-121">**第一方应用** ID：56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="1e254-121">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="1e254-122">**第一方应用名称：** Graph 连接器服务</span><span class="sxs-lookup"><span data-stu-id="1e254-122">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="1e254-123">存储帐户和队列通知 (可选) </span><span class="sxs-lookup"><span data-stu-id="1e254-123">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="1e254-124">将来可能会添加对在 Graph 连接器服务中实时处理更改的支持。</span><span class="sxs-lookup"><span data-stu-id="1e254-124">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="1e254-125">在这种情况下，我们将监视存储在队列中的 Azure 存储更改通知。</span><span class="sxs-lookup"><span data-stu-id="1e254-125">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="1e254-126">你需要在 Azure 存储帐户相同的帐户中创建队列。</span><span class="sxs-lookup"><span data-stu-id="1e254-126">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="1e254-127">创建队列后，请转到队列页面上的" **事件** "选项卡以配置 **事件订阅**。</span><span class="sxs-lookup"><span data-stu-id="1e254-127">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="1e254-128">选择队列将接收的所有 Blob 事件，将队列连接到 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="1e254-128">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="1e254-129">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="1e254-129">Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="1e254-130">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="1e254-130">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="1e254-131">在 **"管理搜索** 权限"屏幕上，你可以选择从 [Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) 存储帐户 (访问控制列表) ACL。</span><span class="sxs-lookup"><span data-stu-id="1e254-131">On the **Manage search permissions** screen, you can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="1e254-132">设置这些搜索权限后，将基于分配给搜索内容的已登录 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) 用户的权限来修整搜索内容。</span><span class="sxs-lookup"><span data-stu-id="1e254-132">When these search permissions are set, search content is trimmed based on the permissions assigned to the signed-in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) user searching the content.</span></span> <span data-ttu-id="1e254-133">或者，可以选择使从存储帐户编制索引的所有内容对组织中的每个人可见。</span><span class="sxs-lookup"><span data-stu-id="1e254-133">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="1e254-134">在这种情况下，组织中的每个人都将有权访问存储帐户中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="1e254-134">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="1e254-135">Azure Blob 存储</span><span class="sxs-lookup"><span data-stu-id="1e254-135">Azure Blob Storage</span></span>

<span data-ttu-id="1e254-136">对于与 [Azure Blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)的连接，从配置源编制索引的所有内容对组织中的每个人都可见。</span><span class="sxs-lookup"><span data-stu-id="1e254-136">For a connection to [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="1e254-137">Azure Blob 存储中不支持 Blob 级别的访问控制列表。</span><span class="sxs-lookup"><span data-stu-id="1e254-137">Access control lists are not supported at Blob level in Azure Blob Storage.</span></span>

## <a name="search-permissions"></a><span data-ttu-id="1e254-138">搜索权限</span><span class="sxs-lookup"><span data-stu-id="1e254-138">Search permissions</span></span>

<span data-ttu-id="1e254-139">Azure Data Lake Storage Gen2 连接器支持对具有此数据源访问权限的任何人或仅人员可见的 **搜索权限**。</span><span class="sxs-lookup"><span data-stu-id="1e254-139">The Azure Data Lake Storage Gen2 connector supports search permissions visible to **Everyone** or **Only people with access to this data source**.</span></span> <span data-ttu-id="1e254-140">搜索结果中出现的索引数据可能对组织所有用户可见，或仅对有权访问每个项目的用户可见。</span><span class="sxs-lookup"><span data-stu-id="1e254-140">Indexed data that appears in the search results could be visible to all users in the organization or only to users who have access to each item.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="1e254-141">分配属性标签</span><span class="sxs-lookup"><span data-stu-id="1e254-141">Assign property labels</span></span>

<span data-ttu-id="1e254-142">可以通过从选项菜单中选择来为每个标签分配源属性。</span><span class="sxs-lookup"><span data-stu-id="1e254-142">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="1e254-143">虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更准确的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="1e254-143">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="1e254-144">管理架构</span><span class="sxs-lookup"><span data-stu-id="1e254-144">Manage schema</span></span>

<span data-ttu-id="1e254-145">在"管理架构"屏幕上，你可以选择更改架构属性 (可查询、可搜索、可检索和可精简 **)** 这些属性、添加可选别名以及选择 **Content** 属性。</span><span class="sxs-lookup"><span data-stu-id="1e254-145">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="1e254-146">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="1e254-146">Set the refresh schedule</span></span>

<span data-ttu-id="1e254-147">在 **"刷新设置** "屏幕上，可以设置增量爬网间隔和完全爬网间隔。</span><span class="sxs-lookup"><span data-stu-id="1e254-147">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="1e254-148">Azure Data Lake Storage Gen2 连接器的默认间隔为增量爬网 15 分钟，完全爬网间隔为一周。</span><span class="sxs-lookup"><span data-stu-id="1e254-148">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="1e254-149">限制</span><span class="sxs-lookup"><span data-stu-id="1e254-149">Limitations</span></span>

<span data-ttu-id="1e254-150">无法为 Azure Data Lake Storage Gen2 源重新配置 Azure Blob 存储的已发布连接，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="1e254-150">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and vice-versa.</span></span> <span data-ttu-id="1e254-151">在这种情况下，建议配置新连接。</span><span class="sxs-lookup"><span data-stu-id="1e254-151">In such scenarios, it is recommended to configure a new connection.</span></span>
