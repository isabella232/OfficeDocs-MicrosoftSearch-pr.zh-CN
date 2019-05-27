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
description: 利用 Microsoft 搜索管理门户中的导入工具一次添加多个位置
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968289"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="d6308-103">批量创建位置</span><span class="sxs-lookup"><span data-stu-id="d6308-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6308-104">Microsoft 365 管理中心现提供有 Microsoft 必应搜索设置。</span><span class="sxs-lookup"><span data-stu-id="d6308-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d6308-105">从在管理中心[分配搜索管理员](https://docs.microsoft.com/zh-CN/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)开始入手。</span><span class="sxs-lookup"><span data-stu-id="d6308-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="d6308-106">下载和使用 .csv 模板，批量创建、编辑并保存位置。</span><span class="sxs-lookup"><span data-stu-id="d6308-106">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="d6308-107">在“位置”部分的右上角，单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="d6308-107">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="d6308-108">单击“**下载位置模板 (.csv)**”</span><span class="sxs-lookup"><span data-stu-id="d6308-108">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="d6308-109">保存并打开该 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="d6308-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="d6308-110">添加位置内容并保存文件</span><span class="sxs-lookup"><span data-stu-id="d6308-110">Add the location content and save the file</span></span>

    <span data-ttu-id="d6308-111">.csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误</span><span class="sxs-lookup"><span data-stu-id="d6308-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="d6308-112">在“位置”部分的右上角，单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="d6308-112">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="d6308-113">在导入位置窗格中，单击“**浏览**”并导航至想要导入的 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="d6308-113">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="d6308-114">单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="d6308-114">Click **Import**.</span></span>

<span data-ttu-id="d6308-115">导入问答和导出位置模板中的字段相同。</span><span class="sxs-lookup"><span data-stu-id="d6308-115">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="d6308-116">可以导出、批量编辑和导入编辑内容，也可使用空白模板批量创建新位置。</span><span class="sxs-lookup"><span data-stu-id="d6308-116">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="d6308-117">若要批量编辑现有位置，请从管理门户将其导出，完成必要的编辑，然后再将其导入。</span><span class="sxs-lookup"><span data-stu-id="d6308-117">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="d6308-118">防止导入错误</span><span class="sxs-lookup"><span data-stu-id="d6308-118">Prevent import errors</span></span>  
<span data-ttu-id="d6308-119">若所需的任何数据缺失或无效，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="d6308-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="d6308-120">出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。</span><span class="sxs-lookup"><span data-stu-id="d6308-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="d6308-121">完成必要的编辑，并再次尝试导入该文件。</span><span class="sxs-lookup"><span data-stu-id="d6308-121">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6308-122">更正所有错误后才能创建或编辑位置。</span><span class="sxs-lookup"><span data-stu-id="d6308-122">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="d6308-123">为了帮助防止出错，请确保导入文件具有正确格式：</span><span class="sxs-lookup"><span data-stu-id="d6308-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="d6308-124">包含导入模板中的标题行</span><span class="sxs-lookup"><span data-stu-id="d6308-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="d6308-125">包含导入模板中的所有列</span><span class="sxs-lookup"><span data-stu-id="d6308-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="d6308-126">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="d6308-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="d6308-127">这些列可能为空：ID、上次修改时间、上次修改者和纬度/经度</span><span class="sxs-lookup"><span data-stu-id="d6308-127">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="d6308-128">如果该字段为空，则我们将会尝试根据地址确定纬度/经度</span><span class="sxs-lookup"><span data-stu-id="d6308-128">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="d6308-129">“状态”列不能为空，因为此信息是必需的</span><span class="sxs-lookup"><span data-stu-id="d6308-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="d6308-130">基于“状态”字段，位置会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。</span><span class="sxs-lookup"><span data-stu-id="d6308-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="d6308-131">此外，如果包含现有位置的 ID，则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="d6308-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="d6308-132">对于拥有多个租户的组织，你可以从某个租户导出位置并将其导入另一个租户。</span><span class="sxs-lookup"><span data-stu-id="d6308-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="d6308-133">但是，在导入之前，你必须删除 ID 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="d6308-133">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="d6308-134">若要详细了解必填字段和建议填写的字段，请参阅[添加位置](add-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="d6308-134">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

