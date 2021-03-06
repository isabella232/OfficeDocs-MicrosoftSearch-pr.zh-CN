---
title: Microsoft 搜索的文件共享 Graph 连接器
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
ROBOTS: NoIndex
description: 为 Microsoft 搜索设置文件共享 Graph 连接器
ms.openlocfilehash: cd3f28356e41d24182e2da712d476ce2223b39b2
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508784"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="36834-103">文件共享 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="36834-103">File share Graph connector</span></span>

<span data-ttu-id="36834-104">文件共享 Graph 连接器允许组织中用户搜索本地 Windows 文件共享。</span><span class="sxs-lookup"><span data-stu-id="36834-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="36834-105">阅读 [**Graph 连接器的安装程序文章**](configure-connector.md) ，了解一般的 Graph 连接器设置过程。</span><span class="sxs-lookup"><span data-stu-id="36834-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="36834-106">在开始使用之前</span><span class="sxs-lookup"><span data-stu-id="36834-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="36834-107">安装 Graph 连接器代理</span><span class="sxs-lookup"><span data-stu-id="36834-107">Install the Graph connector agent</span></span>

<span data-ttu-id="36834-108">若要为 Windows 文件共享编制索引，必须安装和注册 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="36834-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="36834-109">请参阅 ["安装 Graph 连接器代理"](on-prem-agent.md) 了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="36834-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="36834-110">内容要求</span><span class="sxs-lookup"><span data-stu-id="36834-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="36834-111">文件类型</span><span class="sxs-lookup"><span data-stu-id="36834-111">File types</span></span>

<span data-ttu-id="36834-112">可索引和搜索以下格式的内容：DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPT、PPTM、PPTX、TXT、XLB、XLC、XLSB、XLS、XLSX、XLT、XLXM、XML、XPS 和 ZIP。</span><span class="sxs-lookup"><span data-stu-id="36834-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="36834-113">仅对这些格式的文本内容编制索引。</span><span class="sxs-lookup"><span data-stu-id="36834-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="36834-114">将忽略所有多媒体内容。</span><span class="sxs-lookup"><span data-stu-id="36834-114">All multimedia content is ignored.</span></span> <span data-ttu-id="36834-115">对于不属于此格式的任何文件，仅对元数据编制索引。</span><span class="sxs-lookup"><span data-stu-id="36834-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="36834-116">文件大小限制</span><span class="sxs-lookup"><span data-stu-id="36834-116">File size limits</span></span>

<span data-ttu-id="36834-117">支持的最大文件大小为 100 MB。</span><span class="sxs-lookup"><span data-stu-id="36834-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="36834-118">超过 100 MB 的文件不会编制索引。</span><span class="sxs-lookup"><span data-stu-id="36834-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="36834-119">处理后的最大大小限制为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="36834-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="36834-120">当文件大小达到 4 MB 时，处理将停止。</span><span class="sxs-lookup"><span data-stu-id="36834-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="36834-121">因此，文件中存在某些短语可能无法用于搜索。</span><span class="sxs-lookup"><span data-stu-id="36834-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="36834-122">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="36834-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="36834-123">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="36834-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="36834-124">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="36834-124">Step 2: Name the connection</span></span>

<span data-ttu-id="36834-125">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="36834-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="36834-126">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="36834-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="36834-127">在 **"连接到数据源"** 页上，选择 **"** 文件共享"并提供名称、连接 ID 和说明。</span><span class="sxs-lookup"><span data-stu-id="36834-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="36834-128">下一页，提供文件共享的路径并选择之前安装的 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="36834-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="36834-129">输入对文件共享中所有文件的读取访问权限的 [Microsoft Windows](https://microsoft.com/windows) 用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="36834-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="36834-130">保留上次访问时间</span><span class="sxs-lookup"><span data-stu-id="36834-130">Preserve last access time</span></span>

<span data-ttu-id="36834-131">当连接器尝试对文件进行爬网时，将更新其元数据中的"上次访问时间"字段。</span><span class="sxs-lookup"><span data-stu-id="36834-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="36834-132">如果依赖于该字段进行任何存档和备份解决方案，并且不希望在连接器访问它时对其进行更新，可以在"高级设置"页 **中配置** 此选项。</span><span class="sxs-lookup"><span data-stu-id="36834-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="36834-133">步骤 4：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="36834-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="36834-134">通过在"管理搜索权限"页中选择所需的选项，可以限制基于"共享访问控制列表"或"新技术文件系统 (NTFS) 访问控制列表"搜索任何 **文件的权限。**</span><span class="sxs-lookup"><span data-stu-id="36834-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists, by selecting the desired option in **Manage search permissions** page.</span></span> <span data-ttu-id="36834-135">这些访问控制列表中提供的用户帐户和组必须由 Active Directory (AD) 。</span><span class="sxs-lookup"><span data-stu-id="36834-135">The user accounts and groups provided in these Access Control Lists must be managed by Active Directory (AD).</span></span> <span data-ttu-id="36834-136">如果使用任何其他系统进行用户帐户管理，可以选择"任何人"选项，这样用户就可以搜索所有文件，而没有任何访问限制。</span><span class="sxs-lookup"><span data-stu-id="36834-136">If you are using any other system for user accounts management, you can select 'everyone' option, which lets users search for all the files without any access restrictions.</span></span> <span data-ttu-id="36834-137">但是，当用户尝试打开文件时，将应用在源上设置的访问控制。</span><span class="sxs-lookup"><span data-stu-id="36834-137">However, when users try to open the file, access controls set at the source apply.</span></span>

<span data-ttu-id="36834-138">请注意，默认情况下，当在网络共享文件夹时，Windows 为 Share ACL 中的"任何人"提供"读取"权限。</span><span class="sxs-lookup"><span data-stu-id="36834-138">Note that windows by default provides 'Read' permission to 'Everyone' in Share ACLs when a folder is shared on network.</span></span> <span data-ttu-id="36834-139">通过扩展名，如果您在"管理搜索权限"中选择了"共享 ACL"，则用户将能够搜索所有文件。</span><span class="sxs-lookup"><span data-stu-id="36834-139">By extension, if you are choosing Share ACLs in **Manage search permissions**, users will be able to search for all the files.</span></span> <span data-ttu-id="36834-140">如果要限制访问，请删除文件共享中"任何人"的"读取"访问权限，并仅向所需的用户和组提供访问权限。</span><span class="sxs-lookup"><span data-stu-id="36834-140">If you want to restrict access, remove 'Read' access for 'Everyone' in file shares and provide access only to the desired users and groups.</span></span> <span data-ttu-id="36834-141">然后，连接器读取这些访问限制，并应用它们进行搜索。</span><span class="sxs-lookup"><span data-stu-id="36834-141">The connector then reads these access restrictions and applies them to search.</span></span>

<span data-ttu-id="36834-142">只有在提供的共享路径遵循 UNC 路径格式时，才能选择"共享 ACL"。</span><span class="sxs-lookup"><span data-stu-id="36834-142">You can choose Share ACLs only if the share path you provided follows UNC path format.</span></span> <span data-ttu-id="36834-143">可以通过在"共享"选项下进入"高级共享"来创建 UNC 格式的路径。</span><span class="sxs-lookup"><span data-stu-id="36834-143">You can create a path in UNC format by going to 'Advanced Sharing' under 'Sharing' option.</span></span>

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="36834-145">步骤 5：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="36834-145">Step 5: Assign property labels</span></span>

<span data-ttu-id="36834-146">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="36834-146">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="36834-147">步骤 6：管理架构</span><span class="sxs-lookup"><span data-stu-id="36834-147">Step 6: Manage schema</span></span>

<span data-ttu-id="36834-148">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="36834-148">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="36834-149">步骤 7：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="36834-149">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="36834-150">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="36834-150">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="36834-151">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="36834-151">Step 8: Review connection</span></span>

<span data-ttu-id="36834-152">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="36834-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
