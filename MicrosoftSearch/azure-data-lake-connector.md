---
title: 用于 Microsoft 搜索的 Azure Data Lake 连接器
ms.author: v-pamcn
author: monaray
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
ms.openlocfilehash: bedd7307ca2add52408bb9a5e3b3b21fd75df258
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949590"
---
# <a name="azure-data-lake-storage-gen2-connector"></a><span data-ttu-id="cf3bb-103">Azure Data Lake Storage Gen2 connector</span><span class="sxs-lookup"><span data-stu-id="cf3bb-103">Azure Data Lake Storage Gen2 connector</span></span>

<span data-ttu-id="cf3bb-104">使用[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) connector，组织中的用户可以搜索文件及其内容。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-104">With the [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) connector, users in your organization can search for files and their content.</span></span> <span data-ttu-id="cf3bb-105">此连接器访问 azure Data Lake Storage Gen 2 帐户内存储在 Azure Blob 容器和支持层次结构的文件夹中的数据。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-105">This connector accesses data stored in Azure Blob containers and hierarchy-enabled folders within an Azure Data Lake Storage Gen 2 account.</span></span>

<span data-ttu-id="cf3bb-106">本文适用于 Microsoft 365 管理员或任何配置、运行和监控 Azure Data Lake Storage Gen2 连接器的人。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="cf3bb-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="cf3bb-108">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="cf3bb-108">Connect to a data source</span></span>

### <a name="primary-storage-connection-string"></a><span data-ttu-id="cf3bb-109">主存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="cf3bb-109">Primary storage connection string</span></span> 
<span data-ttu-id="cf3bb-110">在 "**身份验证和配置**" 屏幕上，提供主存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-110">On the **Authentication and config** screen, provide the Primary Storage Connection String.</span></span> <span data-ttu-id="cf3bb-111">该字符串是允许访问您的存储帐户所必需的。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-111">That string is required to allow access to your storage account.</span></span> <span data-ttu-id="cf3bb-112">若要查找您的连接字符串，请转到[azure 门户](https://ms.portal.azure.com/#home)，并导航到 Azure Data Lake Storage Gen2 帐户的 "**密钥**" 部分。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-112">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of the Azure Data Lake Storage Gen2 account.</span></span> <span data-ttu-id="cf3bb-113">将连接字符串复制并粘贴到屏幕上的相应字段中。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-113">Copy and paste the connection string in the appropriate field on the screen.</span></span>

<span data-ttu-id="cf3bb-114">如果您不想提供**AccountKey** （主存储连接字符串中的参数），则必须授予对 Graph 连接器服务的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-114">If you do not want to provide the **AccountKey** (a parameter in the primary storage connection string), you have to grant read access to our Graph Connectors Service.</span></span> <span data-ttu-id="cf3bb-115">在 Azure Data Lake Storage Gen2 帐户的 "**访问控制**" 选项卡中，按照该页面上的说明授予对以下应用的访问权限：</span><span class="sxs-lookup"><span data-stu-id="cf3bb-115">In the **Access Control** tab of your Azure Data Lake Storage Gen2 account, follow the instructions on that page to grant access to the following app:</span></span>
* <span data-ttu-id="cf3bb-116">**第一方应用程序 ID：** 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="cf3bb-116">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="cf3bb-117">**第一方应用程序名称：** Graph 连接器服务</span><span class="sxs-lookup"><span data-stu-id="cf3bb-117">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="cf3bb-118">存储帐户和队列通知（可选）</span><span class="sxs-lookup"><span data-stu-id="cf3bb-118">Storage account and queue notifications (Optional)</span></span>
<span data-ttu-id="cf3bb-119">在将来可能会添加在图形连接器服务中实时处理更改的支持。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-119">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="cf3bb-120">在这种情况下，我们将监视存储在队列中的 Azure Data Lake Storage Gen2 更改通知。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-120">In that case, we'll monitor Azure Data Lake Storage Gen2 change notifications stored in a queue.</span></span> <span data-ttu-id="cf3bb-121">您需要在与 Azure Data Lake Storage Gen2 或其他存储帐户相同的帐户中创建队列。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-121">You'll need to create a queue in the same account as your Azure Data Lake Storage Gen2 or in another storage account.</span></span>

<span data-ttu-id="cf3bb-122">创建队列后，转到 "队列" 页中的 "**事件**" 选项卡以配置事件订阅。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-122">After you create a queue, go to the **Events** tab in the queue page to configure Event Subscription.</span></span> <span data-ttu-id="cf3bb-123">选择队列将接收的所有 Blob 事件并将队列连接到 Azure Data Lake Storage Gen2 帐户。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-123">Choose all the Blob events that the queue will receive and connect the queue to the Azure Data Lake Storage Gen2 account.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="cf3bb-124">管理搜索架构</span><span class="sxs-lookup"><span data-stu-id="cf3bb-124">Manage the search schema</span></span>
<span data-ttu-id="cf3bb-125">在 "**管理架构**" 屏幕上，您可以选择更改与托管属性相关联的架构属性（可**查询**、可**搜索**和可**检索**）。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-125">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, and **retrievable**) associated with the managed properties.</span></span> <span data-ttu-id="cf3bb-126">这些托管属性属性是从 Azure Data Lake Storage Gen2 帐户编制索引的数据。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-126">These managed property attributes are data indexed from your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="cf3bb-127">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="cf3bb-127">Manage search permissions</span></span>
<span data-ttu-id="cf3bb-128">在 "**管理搜索权限**" 屏幕上，您可以选择从您的存储帐户中接收访问控制列表（acl）。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-128">On the **Manage search permissions** screen, you can choose to ingest the Access Control Lists (ACLs) from your storage account.</span></span> <span data-ttu-id="cf3bb-129">设置这些搜索权限时，将根据分配给已登录的 Azure AD 用户搜索内容的权限对搜索内容进行修整。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-129">When these search permissions are set, search content is trimmed based on the permissions assigned to the signed-in Azure AD user searching the content.</span></span> <span data-ttu-id="cf3bb-130">或者，您可以选择将从存储帐户编制索引的所有内容对组织中的所有人可见。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-130">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="cf3bb-131">在这种情况下，组织中的每个人都将有权访问存储帐户中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-131">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>
 
## <a name="set-the-refresh-schedule"></a><span data-ttu-id="cf3bb-132">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="cf3bb-132">Set the refresh schedule</span></span>
<span data-ttu-id="cf3bb-133">在 "**刷新设置**" 屏幕上，您可以设置增量爬网间隔和完全爬网间隔。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-133">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="cf3bb-134">对于增量爬网，默认情况下，Azure Data Lake Storage Gen2 连接器的默认间隔为15分钟，对于完全爬网，则为一周。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-134">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>
 
## <a name="limitations"></a><span data-ttu-id="cf3bb-135">限制</span><span class="sxs-lookup"><span data-stu-id="cf3bb-135">Limitations</span></span>
<span data-ttu-id="cf3bb-136">目前，Azure Data Lake Storage Gen2 多协议访问仅适用于美国、西部、加拿大、加拿大、东、东、西亚、北欧、东 US2、东南亚、西欧洲、西 US、澳大利亚东部、日本东部、西 US2 和巴西的美国中部南.</span><span class="sxs-lookup"><span data-stu-id="cf3bb-136">Currently, Azure Data Lake Storage Gen2 Multi-Protocol Access is available only in the Central US, West Central US, Canada Central, East US, East Asia, North Europe, East US2, South East Asia, West Europe, West US, Australia East, Japan East, West US2, and Brazil South.</span></span>

<span data-ttu-id="cf3bb-137">有关更新和详细信息，请参阅[Azure Data Lake Storage 上的多协议访问（预览）](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access)。</span><span class="sxs-lookup"><span data-stu-id="cf3bb-137">For updates and more information, see  [Multi-protocol access on Azure Data Lake Storage (preview)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access).</span></span>


