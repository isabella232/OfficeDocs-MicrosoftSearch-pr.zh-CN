---
title: 用于 Microsoft 搜索的 Azure Data Lake Graph 连接器
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
description: 为 Microsoft 搜索设置 Azure Data Lake Storage Gen2 Graph 连接器
ms.openlocfilehash: 37a035b3de9dc217f885f193992d1e74a675fb35
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031320"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a><span data-ttu-id="c5e5d-103">Azure Data Lake Storage Gen2 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="c5e5d-103">Azure Data Lake Storage Gen2 Graph connector</span></span>

<span data-ttu-id="c5e5d-104">Azure Data Lake Storage Gen2 Graph 连接器允许贵组织的用户搜索存储在 [Azure Blob](/azure/storage/blobs/storage-blobs-introduction) 存储和 [Azure Data Lake Gen 2 存储帐户中](/azure/storage/blobs/data-lake-storage-introduction) 的文件。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-104">The Azure Data Lake Storage Gen2 Graph connector allows users in your organization to search for files stored in [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="c5e5d-105">阅读 [**设置 Graph 连接器一**](configure-connector.md) 文，了解 Graph 连接器的常规设置说明。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-105">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="c5e5d-106">本文适用于配置、运行和监视 Azure Data Lake Storage Gen2 连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-106">This article is for anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="c5e5d-107">它补充了常规设置过程，并显示了仅适用于 Azure Data Lake Storage Gen2 连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-107">It supplements the general setup process, and shows instructions that apply only for the Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="c5e5d-108">本文还包括有关 [限制的信息](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-108">This article also includes information about [Limitations](#limitations).</span></span>

<span data-ttu-id="c5e5d-109">在文章中，我们将 *Azure 存储* 用作 Azure Blob 存储和 [Azure](/azure/storage/blobs/storage-blobs-introduction) [Data Lake Gen 2](/azure/storage/blobs/data-lake-storage-introduction)Storage 的通用术语。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-109">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c5e5d-110">步骤 1：在 Microsoft 365 管理中心添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="c5e5d-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="c5e5d-111">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="c5e5d-112">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="c5e5d-112">Step 2: Name the connection</span></span>

<span data-ttu-id="c5e5d-113">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="c5e5d-114">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="c5e5d-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="c5e5d-115">输入主存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-115">Enter your Primary storage connection String.</span></span> <span data-ttu-id="c5e5d-116">需要此字符串才能访问存储帐户。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-116">This string is required to allow access to your storage account.</span></span> <span data-ttu-id="c5e5d-117">若要查找连接字符串，请转到 [Azure](https://ms.portal.azure.com/#home) 门户并导航到相关 Azure 存储帐户的 **密钥** 部分。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-117">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span>

<span data-ttu-id="c5e5d-118">如果不希望在主存储连接 (字符串中提供 **AccountKey**) ，请授予以下角色对 Graph 连接器服务的访问权限：</span><span class="sxs-lookup"><span data-stu-id="c5e5d-118">If you prefer not to provide the **AccountKey** (a parameter in the primary storage connection string), grant access to our Graph Connectors Service for the following roles:</span></span>

* <span data-ttu-id="c5e5d-119">存储 Blob 数据读取器</span><span class="sxs-lookup"><span data-stu-id="c5e5d-119">Storage Blob Data Reader</span></span>
* <span data-ttu-id="c5e5d-120">存储队列数据参与者</span><span class="sxs-lookup"><span data-stu-id="c5e5d-120">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="c5e5d-121">存储 Blob Delegator</span><span class="sxs-lookup"><span data-stu-id="c5e5d-121">Storage Blob Delegator</span></span>

<span data-ttu-id="c5e5d-122">导航到 Azure **存储帐户** 的"访问控制"选项卡，并按照其中的说明授予对以下应用的访问权限：</span><span class="sxs-lookup"><span data-stu-id="c5e5d-122">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="c5e5d-123">**第一方应用** ID：56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="c5e5d-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="c5e5d-124">**第一方应用名称：** Graph 连接器服务</span><span class="sxs-lookup"><span data-stu-id="c5e5d-124">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="c5e5d-125">存储帐户和队列通知 (可选) </span><span class="sxs-lookup"><span data-stu-id="c5e5d-125">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="c5e5d-126">将来可能会添加对在 Graph 连接器服务中实时处理更改的支持。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-126">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="c5e5d-127">在这种情况下，我们将监视队列中存储的 Azure 存储更改通知。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-127">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="c5e5d-128">你需要使用与 Azure 存储帐户相同的帐户创建队列。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-128">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="c5e5d-129">创建队列后，请转到队列页面上的" **事件** "选项卡以配置 **事件订阅**。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-129">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="c5e5d-130">选择队列将接收的所有 Blob 事件，将队列连接到 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-130">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="c5e5d-131">步骤 4：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="c5e5d-131">Step 4: Assign property labels</span></span>

<span data-ttu-id="c5e5d-132">可以通过从选项菜单中选择来为每个标签分配源属性。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-132">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="c5e5d-133">虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更好的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-133">While this step isn't mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="c5e5d-134">步骤 5：管理架构</span><span class="sxs-lookup"><span data-stu-id="c5e5d-134">Step 5: Manage schema</span></span>

<span data-ttu-id="c5e5d-135">在"**管理架构**"屏幕上，可以更改与属性关联的架构属性，选项为"**查询\*\*\*\*"、"搜索\*\*\*\*"、"检索**"和"**优化"。**</span><span class="sxs-lookup"><span data-stu-id="c5e5d-135">On the **Manage Schema** screen, you can change the schema attributes associated with the properties, the options are **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="c5e5d-136">还可以添加可选别名，然后选择 **Content** 属性。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-136">You also can add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="c5e5d-137">步骤 6：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="c5e5d-137">Step 6: Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="c5e5d-138">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="c5e5d-138">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="c5e5d-139">你可以选择从 Azure Data Lake Gen [2](/azure/storage/blobs/data-lake-storage-introduction) 存储帐户 (访问控制列表) ACL。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-139">You can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="c5e5d-140">设置这些搜索权限后，将基于登录 [Azure Active Directory](/azure/active-directory/)的用户的权限来修整搜索内容。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-140">When these search permissions are set, search content is trimmed based on the permissions of the user signed in [Azure Active Directory](/azure/active-directory/).</span></span> <span data-ttu-id="c5e5d-141">或者，可以选择使存储帐户中编制索引的所有内容对组织中的每个人可见。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-141">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="c5e5d-142">在这种情况下，组织中的每个人都可以访问存储帐户中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-142">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

<span data-ttu-id="c5e5d-143">Azure Data Lake Storage Gen2 Graph 连接器支持对"任何人"或"仅有权访问此数据源的人"**可见的搜索权限**。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-143">The Azure Data Lake Storage Gen2 Graph connector supports search permissions visible to **Everyone**, or **Only people with access to this data source**.</span></span> <span data-ttu-id="c5e5d-144">对于组织中有权访问每个项目的用户，搜索结果中出现的已编制索引的数据可能可见。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-144">Indexed data that appears in the search results could be visible to users in the organization who have access to each item.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="c5e5d-145">Azure Blob 存储</span><span class="sxs-lookup"><span data-stu-id="c5e5d-145">Azure Blob Storage</span></span>

<span data-ttu-id="c5e5d-146">对于与 [Azure Blob 存储](/azure/storage/blobs/storage-blobs-introduction)的连接，从配置源索引的所有内容对组织中的每个人都可见。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-146">For a connection to [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="c5e5d-147">Azure Blob 存储中的 Blob 级别不支持访问控制列表。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-147">Access control lists aren't supported at Blob level in Azure Blob Storage.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="c5e5d-148">步骤 7：设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="c5e5d-148">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="c5e5d-149">在" **刷新设置** "屏幕上，可以设置增量爬网间隔和完全爬网间隔。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-149">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="c5e5d-150">Azure Data Lake Storage Gen2 连接器的默认时间间隔为增量爬网 15 分钟，完全爬网间隔为一周。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-150">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="c5e5d-151">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="c5e5d-151">Step 8: Review connection</span></span>

<span data-ttu-id="c5e5d-152">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-152">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="c5e5d-153">限制</span><span class="sxs-lookup"><span data-stu-id="c5e5d-153">Limitations</span></span>

<span data-ttu-id="c5e5d-154">无法针对 Azure Data Lake Storage Gen2 源和另一种方法重新配置 Azure Blob 存储的已发布连接。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-154">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and the other way around.</span></span> <span data-ttu-id="c5e5d-155">在这种情况下，建议配置新连接。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-155">In such scenarios, it's recommended to configure a new connection.</span></span>

<span data-ttu-id="c5e5d-156">此外，文件的大小需要小于或小于 4 MB，以用于爬网。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-156">Also, the size of the files needs to be 4 MB or less for it to be crawled.</span></span> <span data-ttu-id="c5e5d-157">当前支持的文件类型包括：</span><span class="sxs-lookup"><span data-stu-id="c5e5d-157">File types currently supported are:</span></span>

* <span data-ttu-id="c5e5d-158">Word (docx、.docm、.dotx、.dotm) </span><span class="sxs-lookup"><span data-stu-id="c5e5d-158">Word (docx, .docm, .dotx, .dotm)</span></span>
* <span data-ttu-id="c5e5d-159">PowerPoint (.pptm、.pptx、.potm、.potx、.ppam、.ppsm、.ppsx) </span><span class="sxs-lookup"><span data-stu-id="c5e5d-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span></span>
* <span data-ttu-id="c5e5d-160">Excel (.xlsx，.xlsm) </span><span class="sxs-lookup"><span data-stu-id="c5e5d-160">Excel (.xlsx, .xlsm)</span></span>
* <span data-ttu-id="c5e5d-161">旧版 Office 格式 (.doc、.dot 等) </span><span class="sxs-lookup"><span data-stu-id="c5e5d-161">Legacy Office formats (.doc, .dot, etc.)</span></span>
* <span data-ttu-id="c5e5d-162">Text (.txt) </span><span class="sxs-lookup"><span data-stu-id="c5e5d-162">Text (.txt)</span></span>
* <span data-ttu-id="c5e5d-163">HTML</span><span class="sxs-lookup"><span data-stu-id="c5e5d-163">HTML</span></span>
* <span data-ttu-id="c5e5d-164">PDF</span><span class="sxs-lookup"><span data-stu-id="c5e5d-164">PDF</span></span>

<span data-ttu-id="c5e5d-165">不支持二进制文件 (.jpg、.bmp 等) 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-165">Binary files like images (.jpg, .bmp, etc.) are not supported.</span></span> <span data-ttu-id="c5e5d-166">例如，如果 .docx 文件仅包含图像，可能会跳过该文件，因为它未返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="c5e5d-166">For example, if a .docx file contains only images, it might be skipped because it didn't return any content.</span></span>