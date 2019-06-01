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
description: 利用 Microsoft 搜索管理门户中的导入工具一次添加多个位置
ms.openlocfilehash: 186f6973de1ff87b62b5f07a47eb41acdd842010
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591392"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="3e0c8-103">批量创建位置</span><span class="sxs-lookup"><span data-stu-id="3e0c8-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e0c8-104">本文适用于 Microsoft 必应搜索管理门户。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="3e0c8-105">我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将其删除。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="3e0c8-106">我们建议你使用 Microsoft 365 管理中心快速开始。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="3e0c8-107">[Microsoft 搜索概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="3e0c8-108">下载和使用 .csv 模板，批量创建、编辑并保存位置。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="3e0c8-109">在“位置”部分的右上角，单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="3e0c8-109">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="3e0c8-110">单击“**下载位置模板 (.csv)**”</span><span class="sxs-lookup"><span data-stu-id="3e0c8-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="3e0c8-111">保存并打开该 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="3e0c8-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="3e0c8-112">添加位置内容并保存文件</span><span class="sxs-lookup"><span data-stu-id="3e0c8-112">Add the location content and save the file</span></span>

    <span data-ttu-id="3e0c8-113">.csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误</span><span class="sxs-lookup"><span data-stu-id="3e0c8-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="3e0c8-114">在“位置”部分的右上角，单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="3e0c8-114">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="3e0c8-115">在导入位置窗格中，单击“**浏览**”并导航至想要导入的 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="3e0c8-115">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="3e0c8-116">单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="3e0c8-116">Click **Import**.</span></span>

<span data-ttu-id="3e0c8-117">导入问答和导出位置模板中的字段相同。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="3e0c8-118">可以导出、批量编辑和导入编辑内容，也可使用空白模板批量创建新位置。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="3e0c8-119">若要批量编辑现有位置，请从管理门户将其导出，完成必要的编辑，然后再将其导入。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="3e0c8-120">防止导入错误</span><span class="sxs-lookup"><span data-stu-id="3e0c8-120">Prevent import errors</span></span>  
<span data-ttu-id="3e0c8-121">若所需的任何数据缺失或无效，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="3e0c8-122">出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="3e0c8-123">完成必要的编辑，并再次尝试导入该文件。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-123">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3e0c8-124">更正所有错误后才能创建或编辑位置。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="3e0c8-125">为了帮助防止出错，请确保导入文件具有正确格式：</span><span class="sxs-lookup"><span data-stu-id="3e0c8-125">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="3e0c8-126">包含导入模板中的标题行</span><span class="sxs-lookup"><span data-stu-id="3e0c8-126">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="3e0c8-127">包含导入模板中的所有列</span><span class="sxs-lookup"><span data-stu-id="3e0c8-127">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="3e0c8-128">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="3e0c8-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="3e0c8-129">这些列可能为空：ID、上次修改时间、上次修改者和纬度/经度</span><span class="sxs-lookup"><span data-stu-id="3e0c8-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="3e0c8-130">如果该字段为空，则我们将会尝试根据地址确定纬度/经度</span><span class="sxs-lookup"><span data-stu-id="3e0c8-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="3e0c8-131">“状态”列不能为空，因为此信息是必需的</span><span class="sxs-lookup"><span data-stu-id="3e0c8-131">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="3e0c8-132">基于“状态”字段，位置会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-132">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="3e0c8-133">此外，如果包含现有位置的 ID，则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-133">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="3e0c8-134">对于拥有多个租户的组织，你可以从某个租户导出位置并将其导入另一个租户。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-134">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="3e0c8-135">但是，在导入之前，你必须删除 ID 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-135">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="3e0c8-136">若要详细了解必填字段和建议填写的字段，请参阅[添加位置](add-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="3e0c8-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

