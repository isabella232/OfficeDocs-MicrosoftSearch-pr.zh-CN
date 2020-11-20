---
title: 文件共享连接器
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置用于 Microsoft 搜索的文件共享连接器
ms.openlocfilehash: c11c407016315e638205adddddd17d90bbe6b33d
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367714"
---
# <a name="file-share-connector"></a><span data-ttu-id="d6143-103">文件共享连接器</span><span class="sxs-lookup"><span data-stu-id="d6143-103">File share connector</span></span>

<span data-ttu-id="d6143-104">使用文件共享图形连接器，组织中的用户可以搜索内部部署 Windows 文件共享。</span><span class="sxs-lookup"><span data-stu-id="d6143-104">With the File share Graph connector, users in your organization can search on-premise Windows file shares.</span></span>

<span data-ttu-id="d6143-105">本文适用于 Microsoft 365 管理员或任何配置、运行和监视文件共享连接器的人。</span><span class="sxs-lookup"><span data-stu-id="d6143-105">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="d6143-106">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="d6143-106">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-graph-connector-agent"></a><span data-ttu-id="d6143-107">安装图形连接器代理</span><span class="sxs-lookup"><span data-stu-id="d6143-107">Install Graph connector agent</span></span>

<span data-ttu-id="d6143-108">若要为 Windows 文件共享编制索引，必须安装并注册 [Graph 连接器代理](on-prem-agent.md) 软件。</span><span class="sxs-lookup"><span data-stu-id="d6143-108">In order to index your Windows file shares, you must install and register [Graph connector agent](on-prem-agent.md) software.</span></span>

## <a name="content-requirements"></a><span data-ttu-id="d6143-109">内容要求</span><span class="sxs-lookup"><span data-stu-id="d6143-109">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="d6143-110">文件类型</span><span class="sxs-lookup"><span data-stu-id="d6143-110">File types</span></span>

<span data-ttu-id="d6143-111">可以对以下格式的内容编制索引和搜索： DOC、.DOCM、.DOCX、DOT、.DOTX、.EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、.OBD、.OBT、ODP、ODS、ODT、、、、、XLS、.XLSX、.XLT、.pptm、XML、XPS 和 ZIP。</span><span class="sxs-lookup"><span data-stu-id="d6143-111">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="d6143-112">仅对这些格式的文本内容编制索引。</span><span class="sxs-lookup"><span data-stu-id="d6143-112">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="d6143-113">忽略所有多媒体内容。</span><span class="sxs-lookup"><span data-stu-id="d6143-113">All multimedia content is ignored.</span></span> <span data-ttu-id="d6143-114">对于不属于此格式的任何文件，将对单独的元数据编制索引。</span><span class="sxs-lookup"><span data-stu-id="d6143-114">For any file that does not belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="d6143-115">文件大小限制</span><span class="sxs-lookup"><span data-stu-id="d6143-115">File size limits</span></span>

<span data-ttu-id="d6143-116">支持的最大文件大小为 100 MB。</span><span class="sxs-lookup"><span data-stu-id="d6143-116">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="d6143-117">不会为超过 100 MB 的文件编制索引。</span><span class="sxs-lookup"><span data-stu-id="d6143-117">Files that exceed 100 MB are not indexed.</span></span> <span data-ttu-id="d6143-118">后处理的最大大小限制为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="d6143-118">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="d6143-119">当文件的大小达到 4 MB 时处理停止。</span><span class="sxs-lookup"><span data-stu-id="d6143-119">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="d6143-120">因此，文件中存在的一些短语可能不适用于搜索。</span><span class="sxs-lookup"><span data-stu-id="d6143-120">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="d6143-121">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="d6143-121">Connect to a data source</span></span>

<span data-ttu-id="d6143-122">在 " **连接到数据源** " 页上，选择 " **文件共享** " 并提供名称、连接 ID 和说明。</span><span class="sxs-lookup"><span data-stu-id="d6143-122">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="d6143-123">在下一页上，提供文件共享的路径，然后选择您之前安装的图形连接器代理。</span><span class="sxs-lookup"><span data-stu-id="d6143-123">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="d6143-124">输入具有文件共享中所有文件的读取访问权限的 [Microsoft Windows](https://microsoft.com/windows) 用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="d6143-124">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

## <a name="preserve-last-access-time"></a><span data-ttu-id="d6143-125">保留上次访问时间</span><span class="sxs-lookup"><span data-stu-id="d6143-125">Preserve last access time</span></span>

<span data-ttu-id="d6143-126">当连接器尝试对文件进行爬网时，会更新其元数据中的 "上次访问时间" 字段。</span><span class="sxs-lookup"><span data-stu-id="d6143-126">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="d6143-127">如果您依赖于任何存档和备份解决方案的字段，并且不希望在连接器访问它时对其进行更新，则可以在 " **高级设置** " 页中配置此选项。</span><span class="sxs-lookup"><span data-stu-id="d6143-127">If you depend on that field for any archiving and backup solutions and do not want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="d6143-128">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="d6143-128">Manage search permissions</span></span>

<span data-ttu-id="d6143-129">您可以限制基于共享访问控制列表或新技术文件系统 (NTFS) 访问控制列表中搜索任何文件的权限。</span><span class="sxs-lookup"><span data-stu-id="d6143-129">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="d6143-130">如果要使用共享访问控制列表，请在 " **高级设置** " 页上选择相应的选项。</span><span class="sxs-lookup"><span data-stu-id="d6143-130">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="d6143-131">如果要使用 NTFS 访问控制列表，请在 " **管理搜索权限** " 页上选择相应的选项。</span><span class="sxs-lookup"><span data-stu-id="d6143-131">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="d6143-132">分配属性标签</span><span class="sxs-lookup"><span data-stu-id="d6143-132">Assign property labels</span></span>

<span data-ttu-id="d6143-133">通过从选项菜单中进行选择，可以为每个标签分配一个 source 属性。</span><span class="sxs-lookup"><span data-stu-id="d6143-133">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="d6143-134">虽然这一步并不是强制性的，但具有一些属性标签将改进搜索相关性，并确保最终用户更准确地搜索结果。</span><span class="sxs-lookup"><span data-stu-id="d6143-134">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="d6143-135">管理架构</span><span class="sxs-lookup"><span data-stu-id="d6143-135">Manage schema</span></span>

<span data-ttu-id="d6143-136">在 " **管理架构** " 屏幕上，您可以选择更改架构属性， (可 **查询**、可 **搜索**、 **检索** 和 **可精简**) 与属性相关联，添加可选别名，然后选择 **Content** 属性。</span><span class="sxs-lookup"><span data-stu-id="d6143-136">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="d6143-137">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="d6143-137">Set the refresh schedule</span></span>

<span data-ttu-id="d6143-138">建议的默认刷新计划间隔为15分钟，但您可以根据自己的偏好对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="d6143-138">The recommended default refresh schedule interval is 15 minutes, but you can change it based on your preferences.</span></span>
