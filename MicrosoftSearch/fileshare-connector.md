---
title: Microsoft 搜索的文件共享 Graph 连接器
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: 为 Microsoft 搜索设置文件共享图形连接器
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097418"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="65a1f-103">文件共享 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="65a1f-103">File share Graph connector</span></span>

<span data-ttu-id="65a1f-104">文件共享 Graph 连接器允许组织中用户搜索本地 Windows 文件共享。</span><span class="sxs-lookup"><span data-stu-id="65a1f-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="65a1f-105">阅读 [**Graph 连接器的安装程序**](configure-connector.md) 文章，了解一般的 Graph 连接器设置过程。</span><span class="sxs-lookup"><span data-stu-id="65a1f-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="65a1f-106">在开始使用之前</span><span class="sxs-lookup"><span data-stu-id="65a1f-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="65a1f-107">安装 Graph 连接器代理</span><span class="sxs-lookup"><span data-stu-id="65a1f-107">Install the Graph connector agent</span></span>

<span data-ttu-id="65a1f-108">若要为 Windows 文件共享编制索引，必须安装和注册 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="65a1f-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="65a1f-109">请参阅 ["安装 Graph 连接器代理"](on-prem-agent.md) 了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="65a1f-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="65a1f-110">内容要求</span><span class="sxs-lookup"><span data-stu-id="65a1f-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="65a1f-111">文件类型</span><span class="sxs-lookup"><span data-stu-id="65a1f-111">File types</span></span>

<span data-ttu-id="65a1f-112">可以索引和搜索以下格式的内容：DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPT、PPTM、PPTX、TXT、XLB、XLC、XLSB、XLS、XLS、XLSX、XLSX、XML、XPS 和 ZIP。</span><span class="sxs-lookup"><span data-stu-id="65a1f-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="65a1f-113">仅对这些格式的文本内容编制索引。</span><span class="sxs-lookup"><span data-stu-id="65a1f-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="65a1f-114">将忽略所有多媒体内容。</span><span class="sxs-lookup"><span data-stu-id="65a1f-114">All multimedia content is ignored.</span></span> <span data-ttu-id="65a1f-115">对于不属于此格式的任何文件，仅对元数据编制索引。</span><span class="sxs-lookup"><span data-stu-id="65a1f-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="65a1f-116">文件大小限制</span><span class="sxs-lookup"><span data-stu-id="65a1f-116">File size limits</span></span>

<span data-ttu-id="65a1f-117">支持的最大文件大小为 100 MB。</span><span class="sxs-lookup"><span data-stu-id="65a1f-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="65a1f-118">超过 100 MB 的文件不编制索引。</span><span class="sxs-lookup"><span data-stu-id="65a1f-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="65a1f-119">处理后的最大大小限制为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="65a1f-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="65a1f-120">当文件大小达到 4 MB 时，处理将停止。</span><span class="sxs-lookup"><span data-stu-id="65a1f-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="65a1f-121">因此，文件中呈现的一些短语可能无法用于搜索。</span><span class="sxs-lookup"><span data-stu-id="65a1f-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="65a1f-122">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="65a1f-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="65a1f-123">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="65a1f-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="65a1f-124">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="65a1f-124">Step 2: Name the connection</span></span>

<span data-ttu-id="65a1f-125">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="65a1f-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="65a1f-126">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="65a1f-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="65a1f-127">在 **"连接到数据源"** 页上，选择 **"** 文件共享"并提供名称、连接 ID 和说明。</span><span class="sxs-lookup"><span data-stu-id="65a1f-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="65a1f-128">下一页，提供文件共享的路径，然后选择之前安装的 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="65a1f-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="65a1f-129">输入对文件共享中所有文件的读取访问权限 [的 Microsoft Windows](https://microsoft.com/windows) 用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="65a1f-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="65a1f-130">保留上一次访问时间</span><span class="sxs-lookup"><span data-stu-id="65a1f-130">Preserve last access time</span></span>

<span data-ttu-id="65a1f-131">当连接器尝试对文件进行爬网时，将更新其元数据中的"上次访问时间"字段。</span><span class="sxs-lookup"><span data-stu-id="65a1f-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="65a1f-132">如果您依赖于该字段作为任何存档和备份解决方案，并且不希望在连接器访问它时对其进行更新，您可以在"高级设置"页中 **配置此选项。**</span><span class="sxs-lookup"><span data-stu-id="65a1f-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="65a1f-133">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="65a1f-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="65a1f-134">您可以限制基于"共享 (访问控制列表"或"新技术文件系统"或"NTFS"或"NTFS") 搜索任何文件的权限。</span><span class="sxs-lookup"><span data-stu-id="65a1f-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="65a1f-135">如果要使用"共享访问控制列表"，请在"高级设置"页上 **选择相应的** 选项。</span><span class="sxs-lookup"><span data-stu-id="65a1f-135">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="65a1f-136">如果要使用 NTFS 访问控制列表，请在"管理搜索权限"页上 **选择相应的** 选项。</span><span class="sxs-lookup"><span data-stu-id="65a1f-136">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="65a1f-137">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="65a1f-137">Step 5: Assign property labels</span></span>

<span data-ttu-id="65a1f-138">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="65a1f-138">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="65a1f-139">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="65a1f-139">Step 6: Manage schema</span></span>

<span data-ttu-id="65a1f-140">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="65a1f-140">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="65a1f-141">步骤 7：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="65a1f-141">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="65a1f-142">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="65a1f-142">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="65a1f-143">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="65a1f-143">Step 8: Review connection</span></span>

<span data-ttu-id="65a1f-144">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="65a1f-144">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
