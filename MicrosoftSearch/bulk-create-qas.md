---
title: 批量创建 Q&As
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
description: 使用 Microsoft Search administration portal 中的导入工具快速添加对常见问题的解答
ms.openlocfilehash: 53f1d167948f6b621ad139620553df51b0cb91c2
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068392"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="ebb03-103">批量创建 Q&As</span><span class="sxs-lookup"><span data-stu-id="ebb03-103">Bulk create Q&As</span></span>

<span data-ttu-id="ebb03-p101">下载并使用 .csv 模板批量创建或批量编辑 Q&As。这也是批量保存草稿 Q&As 的简单方法, 需要进行其他编辑或更新。如果需要批量编辑现有 Q&As, 请将其从管理门户中导出, 进行必要的编辑, 然后将其导入。</span><span class="sxs-lookup"><span data-stu-id="ebb03-p101">Download and use the .csv template to bulk create or bulk edit Q&As. It's also a simple way to bulk save draft Q&As that need additional edits or updates. If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="ebb03-107">在 "Q&As" 部分的右上角, 单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="ebb03-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="ebb03-108">单击 "**下载 Q&A 模板 (.csv)** "</span><span class="sxs-lookup"><span data-stu-id="ebb03-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="ebb03-109">保存并打开 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="ebb03-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="ebb03-110">添加 Q&A 内容和设置并保存文件</span><span class="sxs-lookup"><span data-stu-id="ebb03-110">Add the Q&A content and settings and save the file</span></span>
    
5. <span data-ttu-id="ebb03-111">在 "Q&As" 部分的右上角, 单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="ebb03-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="ebb03-112">在 "导入 Q&As" 窗格中, 单击 "**浏览**" 并导航到要导入的 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="ebb03-112">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="ebb03-113">单击 "**导入**</span><span class="sxs-lookup"><span data-stu-id="ebb03-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="ebb03-114">阻止导入错误</span><span class="sxs-lookup"><span data-stu-id="ebb03-114">Prevent import errors</span></span>      
<span data-ttu-id="ebb03-p102">如果任何必需的数据丢失或无效, 则会出现错误。根据错误的不同, 可能会生成日志文件, 其中包含有关需要更正的行和列的详细信息。进行必要的编辑, 然后再次尝试导入文件。</span><span class="sxs-lookup"><span data-stu-id="ebb03-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="ebb03-118">在解决所有错误之前, 不能创建或编辑任何 Q&As。</span><span class="sxs-lookup"><span data-stu-id="ebb03-118">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="ebb03-119">若要帮助防止错误, 请确保导入文件格式正确:</span><span class="sxs-lookup"><span data-stu-id="ebb03-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="ebb03-120">包含导入模板中的标题行</span><span class="sxs-lookup"><span data-stu-id="ebb03-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="ebb03-121">包含导入模板中的所有列</span><span class="sxs-lookup"><span data-stu-id="ebb03-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="ebb03-122">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="ebb03-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="ebb03-123">这些列可能为空: Id、上次修改时间和上次修改者</span><span class="sxs-lookup"><span data-stu-id="ebb03-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="ebb03-124">"状态" 列不能为空, 此信息是必需的</span><span class="sxs-lookup"><span data-stu-id="ebb03-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="ebb03-125">根据 "省/市/自治区" 字段, Q&As 将保存为草稿、建议、计划或将自动发布。</span><span class="sxs-lookup"><span data-stu-id="ebb03-125">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="ebb03-126">此外, 如果包括现有 Q&A 的 Id, 则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="ebb03-126">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="ebb03-p103">对于具有多个租户的组织, 您可以从一个租户导出您的 Q&As, 然后将其导入到另一个租户。但您必须在导入前删除 Id 列中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="ebb03-p103">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="ebb03-129">若要了解有关必需字段和推荐字段的详细信息, 请参阅[Create Q&As](create-qas.md)。</span><span class="sxs-lookup"><span data-stu-id="ebb03-129">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

