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
description: 使用 Microsoft Search administration portal 的导入工具一次添加多个位置
ms.openlocfilehash: 3c7e43b03b97b46769d5e73f20ddae47b3459b59
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508559"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="1dc18-103">批量创建位置</span><span class="sxs-lookup"><span data-stu-id="1dc18-103">Bulk create locations</span></span>

<span data-ttu-id="1dc18-104">下载并使用 .csv 模板以批量创建、编辑和保存位置。</span><span class="sxs-lookup"><span data-stu-id="1dc18-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="1dc18-105">在 "位置" 部分的右上角, 单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="1dc18-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="1dc18-106">单击 "**下载位置" 模板 (.csv)**</span><span class="sxs-lookup"><span data-stu-id="1dc18-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="1dc18-107">保存并打开 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="1dc18-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="1dc18-108">添加位置内容并保存文件</span><span class="sxs-lookup"><span data-stu-id="1dc18-108">Add the location content and save the file</span></span>

    <span data-ttu-id="1dc18-109">.csv 文件应保存为 csv utf-8 文件, 其他文件类型和或编码可能导致导入错误</span><span class="sxs-lookup"><span data-stu-id="1dc18-109">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="1dc18-110">在 "位置" 部分的右上角, 单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="1dc18-110">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="1dc18-111">在 "导入位置" 窗格中, 单击 "**浏览**" 并导航到要导入的 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="1dc18-111">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="1dc18-112">单击 "**导入**</span><span class="sxs-lookup"><span data-stu-id="1dc18-112">Click **Import**</span></span>

<span data-ttu-id="1dc18-113">"导入" 和 "导出位置" 模板中的字段相同。</span><span class="sxs-lookup"><span data-stu-id="1dc18-113">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="1dc18-114">您可以导出、批量编辑和导入编辑, 或从空模板开始, 以批量创建新位置。</span><span class="sxs-lookup"><span data-stu-id="1dc18-114">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="1dc18-115">若要批量编辑现有位置, 请从管理门户中导出它们, 进行必要的编辑, 然后将其导入。</span><span class="sxs-lookup"><span data-stu-id="1dc18-115">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="1dc18-116">阻止导入错误</span><span class="sxs-lookup"><span data-stu-id="1dc18-116">Prevent import errors</span></span>  
<span data-ttu-id="1dc18-117">如果任何必需的数据丢失或无效, 则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="1dc18-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="1dc18-118">根据错误的不同, 可能会生成日志文件, 其中包含有关需要更正的行和列的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1dc18-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="1dc18-119">进行必要的编辑, 然后再次尝试导入文件。</span><span class="sxs-lookup"><span data-stu-id="1dc18-119">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dc18-120">在解决所有错误之前, 不能创建或编辑任何位置。</span><span class="sxs-lookup"><span data-stu-id="1dc18-120">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="1dc18-121">若要帮助防止错误, 请确保导入文件格式正确:</span><span class="sxs-lookup"><span data-stu-id="1dc18-121">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="1dc18-122">包含导入模板中的标题行</span><span class="sxs-lookup"><span data-stu-id="1dc18-122">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="1dc18-123">包含导入模板中的所有列</span><span class="sxs-lookup"><span data-stu-id="1dc18-123">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="1dc18-124">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="1dc18-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="1dc18-125">这些列可以为空: Id、上次修改时间、上次修改者和 Lat/长时间</span><span class="sxs-lookup"><span data-stu-id="1dc18-125">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="1dc18-126">我们将尝试根据地址 (如果该字段为空) 来确定 lat/长时间</span><span class="sxs-lookup"><span data-stu-id="1dc18-126">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="1dc18-127">"状态" 列不能为空, 此信息是必需的</span><span class="sxs-lookup"><span data-stu-id="1dc18-127">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="1dc18-128">根据 "省/市/自治区" 字段, 位置将保存为草稿、建议、计划或将自动发布。</span><span class="sxs-lookup"><span data-stu-id="1dc18-128">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="1dc18-129">此外, 如果您包含现有位置的 Id, 则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="1dc18-129">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="1dc18-130">对于具有多个租户的组织, 您可以从一个租户导出位置并将其导入到另一个租户。</span><span class="sxs-lookup"><span data-stu-id="1dc18-130">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another.</span></span> <span data-ttu-id="1dc18-131">但您必须在导入前删除 Id 列中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="1dc18-131">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="1dc18-132">若要了解有关必需字段和推荐字段的详细信息, 请参阅[添加位置](add-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="1dc18-132">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

