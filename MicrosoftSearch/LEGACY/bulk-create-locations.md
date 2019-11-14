---
title: 批量创建位置
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
ROBOTS: NoIndex
description: 使用 Microsoft Search Administration portal 的导入工具一次添加多个位置
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311409"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="adafc-103">批量创建位置</span><span class="sxs-lookup"><span data-stu-id="adafc-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adafc-104">本文适用于必应中的 Microsoft 搜索管理门户。</span><span class="sxs-lookup"><span data-stu-id="adafc-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="adafc-105">我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将必应中的 Microsoft 搜索门户删除。</span><span class="sxs-lookup"><span data-stu-id="adafc-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="adafc-106">我们建议你使用 Microsoft 365 管理中心快速开始。</span><span class="sxs-lookup"><span data-stu-id="adafc-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="adafc-107">[Microsoft 搜索概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="adafc-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="adafc-108">下载并使用 .csv 模板以批量创建、编辑和保存位置。</span><span class="sxs-lookup"><span data-stu-id="adafc-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="adafc-109">在 "位置" 部分的右上角，单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="adafc-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="adafc-110">单击 "**下载位置" 模板（.csv）**</span><span class="sxs-lookup"><span data-stu-id="adafc-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="adafc-111">保存并打开该 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="adafc-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="adafc-112">添加位置内容并保存文件</span><span class="sxs-lookup"><span data-stu-id="adafc-112">Add the location content and save the file</span></span>

    <span data-ttu-id="adafc-113">.csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误</span><span class="sxs-lookup"><span data-stu-id="adafc-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="adafc-114">在 "位置" 部分的右上角，单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="adafc-114">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="adafc-115">在 "导入位置" 窗格中，单击 "**浏览**" 并导航到要导入的 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="adafc-115">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="adafc-116">单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="adafc-116">Click **Import**</span></span>

<span data-ttu-id="adafc-117">"导入" 和 "导出位置" 模板中的字段相同。</span><span class="sxs-lookup"><span data-stu-id="adafc-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="adafc-118">您可以导出、批量编辑和导入编辑，或从空模板开始，以批量创建新位置。</span><span class="sxs-lookup"><span data-stu-id="adafc-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="adafc-119">若要批量编辑现有位置，请从管理门户中导出它们，进行必要的编辑，然后将其导入。</span><span class="sxs-lookup"><span data-stu-id="adafc-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="adafc-120">防止导入错误</span><span class="sxs-lookup"><span data-stu-id="adafc-120">Prevent import errors</span></span>  
<span data-ttu-id="adafc-121">若所需的任何数据缺失或无效，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="adafc-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="adafc-122">出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。</span><span class="sxs-lookup"><span data-stu-id="adafc-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="adafc-123">完成必要的编辑，并再次尝试导入该文件。</span><span class="sxs-lookup"><span data-stu-id="adafc-123">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="adafc-124">在解决所有错误之前，不能创建或编辑任何位置。</span><span class="sxs-lookup"><span data-stu-id="adafc-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="adafc-125">为了帮助防止出错，请确保导入文件具有正确格式：</span><span class="sxs-lookup"><span data-stu-id="adafc-125">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="adafc-126">包含导入模板中的标题行</span><span class="sxs-lookup"><span data-stu-id="adafc-126">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="adafc-127">包含导入模板中的所有列</span><span class="sxs-lookup"><span data-stu-id="adafc-127">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="adafc-128">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="adafc-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="adafc-129">这些列可以为空： Id、上次修改时间、上次修改者和 Lat/长时间</span><span class="sxs-lookup"><span data-stu-id="adafc-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="adafc-130">我们将尝试根据地址（如果该字段为空）来确定 lat/长时间</span><span class="sxs-lookup"><span data-stu-id="adafc-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="adafc-131">“状态”列不能为空，因为此信息是必需的</span><span class="sxs-lookup"><span data-stu-id="adafc-131">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="adafc-132">根据 "省/市/自治区" 字段，位置将保存为草稿、建议、计划或将自动发布。</span><span class="sxs-lookup"><span data-stu-id="adafc-132">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="adafc-133">此外，如果您包含现有位置的 Id，则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="adafc-133">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="adafc-134">对于管理多个组织的合作伙伴，您可以从一个组织中导出位置并将其导入到另一个组织中。</span><span class="sxs-lookup"><span data-stu-id="adafc-134">For partners who manage multiple organizations, you can export your locations from one org and import them into another.</span></span> <span data-ttu-id="adafc-135">但是，在导入之前，你必须删除 ID 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="adafc-135">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="adafc-136">若要了解有关必需字段和推荐字段的详细信息，请参阅[添加位置](add-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="adafc-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

