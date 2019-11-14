---
title: 批量创建问答
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
ROBOTS: NoIndex
description: 使用 Microsoft 搜索管理门户中的导入工具，快速添加常见问题的答案
ms.openlocfilehash: 660f5663ff6238f4ab59dab36d51f1311d5c7260
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311395"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="e6b62-103">批量创建问答</span><span class="sxs-lookup"><span data-stu-id="e6b62-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6b62-104">本文适用于必应中的 Microsoft 搜索管理门户。</span><span class="sxs-lookup"><span data-stu-id="e6b62-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="e6b62-105">我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将必应中的 Microsoft 搜索门户删除。</span><span class="sxs-lookup"><span data-stu-id="e6b62-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="e6b62-106">我们建议你使用 Microsoft 365 管理中心快速开始。</span><span class="sxs-lookup"><span data-stu-id="e6b62-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="e6b62-107">[Microsoft 搜索概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b62-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="e6b62-108">下载和使用 .csv 模板批量创建或批量编辑问答。</span><span class="sxs-lookup"><span data-stu-id="e6b62-108">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="e6b62-109">使用该模板也可轻松批量保存需要进一步编辑或更新的草稿问答。</span><span class="sxs-lookup"><span data-stu-id="e6b62-109">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="e6b62-110">若要批量编辑现有问答，请将它们从管理门户导出，完成必要的编辑，然后再导入它们。</span><span class="sxs-lookup"><span data-stu-id="e6b62-110">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="e6b62-111">在“问答”部分的右上角，单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="e6b62-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="e6b62-112">单击“**下载问答模板 (.csv)**”</span><span class="sxs-lookup"><span data-stu-id="e6b62-112">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="e6b62-113">保存并打开该 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="e6b62-113">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="e6b62-114">添加问答内容和设置，并保存文件</span><span class="sxs-lookup"><span data-stu-id="e6b62-114">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="e6b62-115">.csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误</span><span class="sxs-lookup"><span data-stu-id="e6b62-115">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="e6b62-116">在“问答”部分的右上角，单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="e6b62-116">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="e6b62-117">在导入问答窗格中，单击“**浏览**”并导航至想要导入的 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="e6b62-117">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="e6b62-118">单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="e6b62-118">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="e6b62-119">防止导入错误</span><span class="sxs-lookup"><span data-stu-id="e6b62-119">Prevent import errors</span></span>      
<span data-ttu-id="e6b62-120">若所需的任何数据缺失或无效，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="e6b62-120">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="e6b62-121">出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。</span><span class="sxs-lookup"><span data-stu-id="e6b62-121">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="e6b62-122">完成必要的编辑，并再次尝试导入该文件。</span><span class="sxs-lookup"><span data-stu-id="e6b62-122">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="e6b62-123">更正所有错误后才能创建或编辑任何问答。</span><span class="sxs-lookup"><span data-stu-id="e6b62-123">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="e6b62-124">为了帮助防止出错，请确保导入文件具有正确格式：</span><span class="sxs-lookup"><span data-stu-id="e6b62-124">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="e6b62-125">包含导入模板中的标题行</span><span class="sxs-lookup"><span data-stu-id="e6b62-125">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="e6b62-126">包含导入模板中的所有列</span><span class="sxs-lookup"><span data-stu-id="e6b62-126">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="e6b62-127">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="e6b62-127">The column order is the same as the import template</span></span>
- <span data-ttu-id="e6b62-128">这些列可能为空：ID、上次修改时间和上次修改者</span><span class="sxs-lookup"><span data-stu-id="e6b62-128">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="e6b62-129">“状态”列不能为空，因为此信息是必需的</span><span class="sxs-lookup"><span data-stu-id="e6b62-129">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="e6b62-130">基于状态字段，问答会保存为草稿问答、推荐问答、已计划问答或自动发布的问答。</span><span class="sxs-lookup"><span data-stu-id="e6b62-130">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="e6b62-131">此外，如果包含现有问答的 ID，则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="e6b62-131">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="e6b62-132">对于管理多个组织的合作伙伴，可以从一个组织中导出 Q&，并将其导入到另一个组织中。</span><span class="sxs-lookup"><span data-stu-id="e6b62-132">For partners who manage multiple organizations, you can export your Q&As from one org and import them into another.</span></span> <span data-ttu-id="e6b62-133">但是，在导入之前，你必须删除 ID 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="e6b62-133">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="e6b62-134">若要详细了解必填字段和建议填写的字段，请参阅[创建问答](create-qas.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b62-134">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

