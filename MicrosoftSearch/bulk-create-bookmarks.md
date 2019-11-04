---
title: 批量创建书签
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: 使用 Microsoft Search Administration portal 的导入工具一次创建大量书签
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948921"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="a4a83-103">批量创建书签</span><span class="sxs-lookup"><span data-stu-id="a4a83-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4a83-104">本文适用于必应中的 Microsoft 搜索管理门户。</span><span class="sxs-lookup"><span data-stu-id="a4a83-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="a4a83-105">我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将必应中的 Microsoft 搜索门户删除。</span><span class="sxs-lookup"><span data-stu-id="a4a83-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="a4a83-106">我们建议你使用 Microsoft 365 管理中心快速开始。</span><span class="sxs-lookup"><span data-stu-id="a4a83-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="a4a83-107">[Microsoft 搜索概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="a4a83-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="a4a83-108">下载并使用 .csv 模板以批量创建、编辑和保存书签。</span><span class="sxs-lookup"><span data-stu-id="a4a83-108">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="a4a83-109">若要批量编辑现有书签，请从管理门户中导出它们，进行必要的编辑，然后将其导入。</span><span class="sxs-lookup"><span data-stu-id="a4a83-109">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="a4a83-110">在 "书签" 部分的右上角，单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="a4a83-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="a4a83-111">单击 "**下载书签模板（.csv）** "</span><span class="sxs-lookup"><span data-stu-id="a4a83-111">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="a4a83-112">保存并打开该 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="a4a83-112">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="a4a83-113">添加书签内容和设置并保存文件</span><span class="sxs-lookup"><span data-stu-id="a4a83-113">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="a4a83-114">.csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误</span><span class="sxs-lookup"><span data-stu-id="a4a83-114">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="a4a83-115">在 "书签" 部分的右上角，单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="a4a83-115">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="a4a83-116">在 "导入书签" 窗格中，单击 "**浏览**" 并导航到要导入的 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="a4a83-116">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="a4a83-117">单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="a4a83-117">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="a4a83-118">防止导入错误</span><span class="sxs-lookup"><span data-stu-id="a4a83-118">Prevent import errors</span></span>      
<span data-ttu-id="a4a83-119">若所需的任何数据缺失或无效，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="a4a83-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="a4a83-120">出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。</span><span class="sxs-lookup"><span data-stu-id="a4a83-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="a4a83-121">完成必要的编辑，并再次尝试导入该文件。</span><span class="sxs-lookup"><span data-stu-id="a4a83-121">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="a4a83-122">在解决所有错误之前，不能创建或编辑任何书签。</span><span class="sxs-lookup"><span data-stu-id="a4a83-122">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="a4a83-123">为了帮助防止出错，请确保导入文件具有正确格式：</span><span class="sxs-lookup"><span data-stu-id="a4a83-123">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="a4a83-124">包含导入模板中的标题行</span><span class="sxs-lookup"><span data-stu-id="a4a83-124">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="a4a83-125">包含导入模板中的所有列</span><span class="sxs-lookup"><span data-stu-id="a4a83-125">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="a4a83-126">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="a4a83-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="a4a83-127">这些列可能为空：ID、上次修改时间和上次修改者</span><span class="sxs-lookup"><span data-stu-id="a4a83-127">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="a4a83-128">“状态”列不能为空，因为此信息是必需的</span><span class="sxs-lookup"><span data-stu-id="a4a83-128">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="a4a83-129">基于“状态”字段，书签会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。</span><span class="sxs-lookup"><span data-stu-id="a4a83-129">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="a4a83-130">此外，如果包括现有书签的 Id，则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="a4a83-130">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="a4a83-131">对于管理多个组织的合作伙伴，您可以从一个组织中导出您的书签并将其导入到另一个组织中。</span><span class="sxs-lookup"><span data-stu-id="a4a83-131">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="a4a83-132">但是，在导入之前，你必须删除 ID 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="a4a83-132">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="a4a83-133">若要了解有关必需字段和推荐字段的详细信息，请参阅[创建书签](create-bookmarks.md)。</span><span class="sxs-lookup"><span data-stu-id="a4a83-133">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
