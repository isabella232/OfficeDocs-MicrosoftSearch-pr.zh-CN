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
description: 设置 Azure Data Lake Storage Gen2 connector for Microsoft Search
ms.openlocfilehash: 860c923c62495c7df20152fb530797e390949305
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367583"
---
# <a name="azure-data-lake-storage-gen2-connector"></a><span data-ttu-id="33718-103">Azure Data Lake Storage Gen2 connector</span><span class="sxs-lookup"><span data-stu-id="33718-103">Azure Data Lake Storage Gen2 connector</span></span>

<span data-ttu-id="33718-104">使用 Azure Data Lake Storage Gen2 连接器，组织中的用户可以搜索存储在 [Azure Blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) 和 [Azure Data Lake Gen 2 存储](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) 帐户中的文件。</span><span class="sxs-lookup"><span data-stu-id="33718-104">With the Azure Data Lake Storage Gen2 connector, users in your organization can search for files stored in [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

<span data-ttu-id="33718-105">本文适用于 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理员或任何配置、运行和监控 Azure Data Lake Storage Gen2 连接器的人。</span><span class="sxs-lookup"><span data-stu-id="33718-105">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="33718-106">它概述了连接器配置、功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="33718-106">It gives an overview of the connector configuration, capabilities, limitations, and troubleshooting techniques.</span></span> <span data-ttu-id="33718-107">在本文中，我们使用 *Azure 存储* 作为 [Azure Blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) 和 [Azure Data Lake Gen 2 存储](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)的通用术语。</span><span class="sxs-lookup"><span data-stu-id="33718-107">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="33718-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="33718-108">Connect to a data source</span></span>

### <a name="primary-storage-connection-string"></a><span data-ttu-id="33718-109">主存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="33718-109">Primary storage connection string</span></span>

<span data-ttu-id="33718-110">在 " **身份验证和配置** " 屏幕上，提供主存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="33718-110">On the **Authentication and config** screen, provide the Primary Storage Connection String.</span></span> <span data-ttu-id="33718-111">该字符串是允许访问您的存储帐户所必需的。</span><span class="sxs-lookup"><span data-stu-id="33718-111">That string is required to allow access to your storage account.</span></span> <span data-ttu-id="33718-112">若要查找您的连接字符串，请转到 [Azure 门户](https://ms.portal.azure.com/#home) ，并导航到相关 Azure 存储帐户的 " **密钥** " 部分。</span><span class="sxs-lookup"><span data-stu-id="33718-112">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span> <span data-ttu-id="33718-113">将连接字符串复制并粘贴到屏幕上的相应字段中。</span><span class="sxs-lookup"><span data-stu-id="33718-113">Copy and paste the connection string in the appropriate field on the screen.</span></span>

<span data-ttu-id="33718-114">如果您不想提供 **AccountKey** (主存储连接字符串中的参数) ，您需要为以下角色授予对我们的 Graph 连接器服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="33718-114">If you do not prefer to provide the **AccountKey** (a parameter in the primary storage connection string), you will need to grant access to our Graph Connectors Service for the following roles.</span></span>

* <span data-ttu-id="33718-115">存储 Blob 数据读取器</span><span class="sxs-lookup"><span data-stu-id="33718-115">Storage Blob Data Reader</span></span>
* <span data-ttu-id="33718-116">存储队列数据参与者</span><span class="sxs-lookup"><span data-stu-id="33718-116">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="33718-117">存储 Blob 代理者仅对分层存储)  (</span><span class="sxs-lookup"><span data-stu-id="33718-117">Storage Blob Delegator (only for hierarchical storage)</span></span>

<span data-ttu-id="33718-118">导航到 Azure 存储帐户的 " **访问控制** " 选项卡，然后按照中的说明授予对以下应用程序的访问权限：</span><span class="sxs-lookup"><span data-stu-id="33718-118">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="33718-119">**第一方应用程序 ID：** 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="33718-119">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="33718-120">**第一方应用程序名称：** Graph 连接器服务</span><span class="sxs-lookup"><span data-stu-id="33718-120">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="33718-121">存储帐户和队列通知 (可选) </span><span class="sxs-lookup"><span data-stu-id="33718-121">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="33718-122">在将来可能会添加在图形连接器服务中实时处理更改的支持。</span><span class="sxs-lookup"><span data-stu-id="33718-122">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="33718-123">在这种情况下，我们将监视存储在队列中的 Azure 存储更改通知。</span><span class="sxs-lookup"><span data-stu-id="33718-123">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="33718-124">你将需要使用与你的 Azure 存储帐户相同的帐户创建队列。</span><span class="sxs-lookup"><span data-stu-id="33718-124">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="33718-125">创建队列后，转到 "队列" 页上的 " **事件** " 选项卡以配置 **事件订阅**。</span><span class="sxs-lookup"><span data-stu-id="33718-125">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="33718-126">选择队列将接收的所有 Blob 事件，并将队列连接到 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="33718-126">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="33718-127">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="33718-127">Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="33718-128">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="33718-128">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="33718-129">在 " **管理搜索权限** " 屏幕上，您可以选择从您的 [Azure Data Lake Gen 2 存储](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) 帐户中接收 (Acl) 的访问控制列表。</span><span class="sxs-lookup"><span data-stu-id="33718-129">On the **Manage search permissions** screen, you can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="33718-130">设置这些搜索权限时，将根据分配给已登录的 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) 用户搜索内容的权限对搜索内容进行修整。</span><span class="sxs-lookup"><span data-stu-id="33718-130">When these search permissions are set, search content is trimmed based on the permissions assigned to the signed-in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) user searching the content.</span></span> <span data-ttu-id="33718-131">或者，您可以选择将从存储帐户编制索引的所有内容对组织中的所有人可见。</span><span class="sxs-lookup"><span data-stu-id="33718-131">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="33718-132">在这种情况下，组织中的每个人都将有权访问存储帐户中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="33718-132">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="33718-133">Azure Blob 存储</span><span class="sxs-lookup"><span data-stu-id="33718-133">Azure Blob Storage</span></span>

<span data-ttu-id="33718-134">对于与 [Azure Blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)的连接，组织中的所有人都可以看到从已配置的源编制索引的所有内容。</span><span class="sxs-lookup"><span data-stu-id="33718-134">For a connection to [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="33718-135">Azure Blob 存储中的 Blob 级别不支持访问控制列表。</span><span class="sxs-lookup"><span data-stu-id="33718-135">Access control lists are not supported at Blob level in Azure Blob Storage.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="33718-136">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="33718-136">Manage search permissions</span></span>

<span data-ttu-id="33718-137">Azure Data Lake Storage Gen2 连接器支持对 **所有人** 可见的搜索权限，或仅支持对 **此数据源具有访问权限的用户**。</span><span class="sxs-lookup"><span data-stu-id="33718-137">The Azure Data Lake Storage Gen2 connector supports search permissions visible to **Everyone** or **Only people with access to this data source**.</span></span> <span data-ttu-id="33718-138">搜索结果中显示的索引数据可能对组织中的所有用户可见，或者仅对对每个项目具有访问权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="33718-138">Indexed data that appears in the search results could be visible to all users in the organization or only to users who have access to each item.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="33718-139">分配属性标签</span><span class="sxs-lookup"><span data-stu-id="33718-139">Assign property labels</span></span>

<span data-ttu-id="33718-140">通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。</span><span class="sxs-lookup"><span data-stu-id="33718-140">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="33718-141">虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。</span><span class="sxs-lookup"><span data-stu-id="33718-141">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="33718-142">管理架构</span><span class="sxs-lookup"><span data-stu-id="33718-142">Manage schema</span></span>

<span data-ttu-id="33718-143">在 " **管理架构** " 屏幕上，您可以选择更改架构属性， (可 **查询**、可 **搜索**、 **检索** 和 **可精简**) 与属性相关联，添加可选别名，然后选择 **Content** 属性。</span><span class="sxs-lookup"><span data-stu-id="33718-143">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="33718-144">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="33718-144">Set the refresh schedule</span></span>

<span data-ttu-id="33718-145">在 " **刷新设置** " 屏幕上，您可以设置增量爬网间隔和完全爬网间隔。</span><span class="sxs-lookup"><span data-stu-id="33718-145">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="33718-146">对于增量爬网，默认情况下，Azure Data Lake Storage Gen2 连接器的默认间隔为15分钟，对于完全爬网，则为一周。</span><span class="sxs-lookup"><span data-stu-id="33718-146">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="33718-147">限制</span><span class="sxs-lookup"><span data-stu-id="33718-147">Limitations</span></span>

<span data-ttu-id="33718-148">无法为 Azure Data Lake Storage Gen2 源重新配置已发布的 Azure Blob 存储连接，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="33718-148">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and vice-versa.</span></span> <span data-ttu-id="33718-149">在这种情况下，建议配置新连接。</span><span class="sxs-lookup"><span data-stu-id="33718-149">In such scenarios, it is recommended to configure a new connection.</span></span>
