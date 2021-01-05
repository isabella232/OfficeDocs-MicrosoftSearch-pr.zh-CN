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
ROBOTS: NoIndex
description: 为 Microsoft 搜索设置文件共享连接器
ms.openlocfilehash: bf9fb730abd4ca6e42b681893525bbe3dd8a1419
ms.sourcegitcommit: 249f41723dd6fda1e93ee1a8f3f7571ef066454b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750894"
---
# <a name="file-share-connector"></a><span data-ttu-id="96254-103">文件共享连接器</span><span class="sxs-lookup"><span data-stu-id="96254-103">File share connector</span></span>

<span data-ttu-id="96254-104">借助文件共享 Graph 连接器，贵组织的用户可以搜索本地 Windows 文件共享。</span><span class="sxs-lookup"><span data-stu-id="96254-104">With the File share Graph connector, users in your organization can search on-premise Windows file shares.</span></span>

<span data-ttu-id="96254-105">本文适用于 Microsoft 365 管理员或配置、运行和监视文件共享连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="96254-105">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="96254-106">它介绍了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="96254-106">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-graph-connector-agent"></a><span data-ttu-id="96254-107">安装 Graph 连接器代理</span><span class="sxs-lookup"><span data-stu-id="96254-107">Install Graph connector agent</span></span>

<span data-ttu-id="96254-108">若要为 Windows 文件共享编制索引，必须安装和注册 [Graph 连接器代理](on-prem-agent.md) 软件。</span><span class="sxs-lookup"><span data-stu-id="96254-108">In order to index your Windows file shares, you must install and register [Graph connector agent](on-prem-agent.md) software.</span></span>

## <a name="content-requirements"></a><span data-ttu-id="96254-109">内容要求</span><span class="sxs-lookup"><span data-stu-id="96254-109">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="96254-110">文件类型</span><span class="sxs-lookup"><span data-stu-id="96254-110">File types</span></span>

<span data-ttu-id="96254-111">可以索引和搜索以下格式的内容：DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPT、PPTM、PPTX、TXT、XLB、XLC、XLSB、XLS、XLS、XLSX、XLSX、XML、XPS 和 ZIP。</span><span class="sxs-lookup"><span data-stu-id="96254-111">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="96254-112">仅对这些格式的文本内容编制索引。</span><span class="sxs-lookup"><span data-stu-id="96254-112">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="96254-113">将忽略所有多媒体内容。</span><span class="sxs-lookup"><span data-stu-id="96254-113">All multimedia content is ignored.</span></span> <span data-ttu-id="96254-114">对于不属于此格式的任何文件，仅对元数据编制索引。</span><span class="sxs-lookup"><span data-stu-id="96254-114">For any file that does not belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="96254-115">文件大小限制</span><span class="sxs-lookup"><span data-stu-id="96254-115">File size limits</span></span>

<span data-ttu-id="96254-116">支持的最大文件大小为 100 MB。</span><span class="sxs-lookup"><span data-stu-id="96254-116">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="96254-117">超过 100 MB 的文件不会编制索引。</span><span class="sxs-lookup"><span data-stu-id="96254-117">Files that exceed 100 MB are not indexed.</span></span> <span data-ttu-id="96254-118">处理后的最大大小限制为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="96254-118">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="96254-119">当文件大小达到 4 MB 时，处理将停止。</span><span class="sxs-lookup"><span data-stu-id="96254-119">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="96254-120">因此，文件中呈现的一些短语可能无法用于搜索。</span><span class="sxs-lookup"><span data-stu-id="96254-120">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="96254-121">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="96254-121">Connect to a data source</span></span>

<span data-ttu-id="96254-122">在 **"连接到数据源"** 页上，选择 **"** 文件共享"并提供名称、连接 ID 和说明。</span><span class="sxs-lookup"><span data-stu-id="96254-122">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="96254-123">下一页，提供文件共享的路径并选择之前安装的 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="96254-123">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="96254-124">输入对文件共享中所有文件的读取访问权限 [的 Microsoft Windows](https://microsoft.com/windows) 用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="96254-124">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

## <a name="preserve-last-access-time"></a><span data-ttu-id="96254-125">保留上一次访问时间</span><span class="sxs-lookup"><span data-stu-id="96254-125">Preserve last access time</span></span>

<span data-ttu-id="96254-126">当连接器尝试对文件进行爬网时，将更新其元数据中的"上次访问时间"字段。</span><span class="sxs-lookup"><span data-stu-id="96254-126">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="96254-127">如果您依赖于该字段作为任何存档和备份解决方案，并且不希望在连接器访问它时对其进行更新，您可以在"高级设置"页中 **配置此选项。**</span><span class="sxs-lookup"><span data-stu-id="96254-127">If you depend on that field for any archiving and backup solutions and do not want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="96254-128">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="96254-128">Manage search permissions</span></span>

<span data-ttu-id="96254-129">您可以限制基于"共享 (访问控制列表"或"新技术文件系统"或"NTFS"或"NTFS") 搜索任何文件的权限。</span><span class="sxs-lookup"><span data-stu-id="96254-129">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="96254-130">如果要使用"共享访问控制列表"，请在"高级设置"页上 **选择相应的** 选项。</span><span class="sxs-lookup"><span data-stu-id="96254-130">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="96254-131">如果要使用 NTFS 访问控制列表，请在"管理搜索权限"页上 **选择相应的** 选项。</span><span class="sxs-lookup"><span data-stu-id="96254-131">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="96254-132">分配属性标签</span><span class="sxs-lookup"><span data-stu-id="96254-132">Assign property labels</span></span>

<span data-ttu-id="96254-133">可以通过从选项菜单中选择来为每个标签分配源属性。</span><span class="sxs-lookup"><span data-stu-id="96254-133">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="96254-134">虽然此步骤不是必需的，但具有一些属性标签将提高搜索相关性，并确保最终用户获得更准确的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="96254-134">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="96254-135">管理架构</span><span class="sxs-lookup"><span data-stu-id="96254-135">Manage schema</span></span>

<span data-ttu-id="96254-136">在"管理架构"屏幕上，你可以选择更改架构属性 (可查询、可搜索、可检索和可精简 **)** 这些属性、添加可选别名以及选择 **Content** 属性。</span><span class="sxs-lookup"><span data-stu-id="96254-136">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="96254-137">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="96254-137">Set the refresh schedule</span></span>

<span data-ttu-id="96254-138">建议的默认刷新计划间隔为 15 分钟，但您可以根据您的首选项更改它。</span><span class="sxs-lookup"><span data-stu-id="96254-138">The recommended default refresh schedule interval is 15 minutes, but you can change it based on your preferences.</span></span>

## <a name="result-layout"></a><span data-ttu-id="96254-139">结果布局</span><span class="sxs-lookup"><span data-stu-id="96254-139">Result layout</span></span>

<span data-ttu-id="96254-140">建议使用默认结果布局来显示文件共享连接器结果，因为它具有相应的图标和控件，可帮助你导航到文件路径。</span><span class="sxs-lookup"><span data-stu-id="96254-140">We recommend that you use the default result layout to display your Fileshare connector results because it has appropriate icons and controls that help you navigate to the file path.</span></span> <span data-ttu-id="96254-141">如果创建新的结果布局，它将覆盖默认值。</span><span class="sxs-lookup"><span data-stu-id="96254-141">If you create a new result layout, it will override the default.</span></span>
