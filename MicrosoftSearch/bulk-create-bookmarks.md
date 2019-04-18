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
description: 使用 Microsoft Search administration portal 的导入工具一次创建大量书签
ms.openlocfilehash: 7c134784f0ca0d4cc84d5bce3a98f7e75aa6f441
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901790"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="d6949-103">批量创建书签</span><span class="sxs-lookup"><span data-stu-id="d6949-103">Bulk create bookmarks</span></span>

<span data-ttu-id="d6949-104">下载并使用 .csv 模板以批量创建、编辑和保存书签。</span><span class="sxs-lookup"><span data-stu-id="d6949-104">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="d6949-105">若要批量编辑现有书签, 请从管理门户中导出它们, 进行必要的编辑, 然后将其导入。</span><span class="sxs-lookup"><span data-stu-id="d6949-105">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="d6949-106">在 "书签" 部分的右上角, 单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="d6949-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="d6949-107">单击 "**下载书签模板 (.csv)** "</span><span class="sxs-lookup"><span data-stu-id="d6949-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="d6949-108">保存并打开 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="d6949-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="d6949-109">添加书签内容和设置并保存文件</span><span class="sxs-lookup"><span data-stu-id="d6949-109">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="d6949-110">.csv 文件应保存为 csv utf-8 文件, 其他文件类型和或编码可能导致导入错误</span><span class="sxs-lookup"><span data-stu-id="d6949-110">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="d6949-111">在 "书签" 部分的右上角, 单击 "**导入**"</span><span class="sxs-lookup"><span data-stu-id="d6949-111">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="d6949-112">在 "导入书签" 窗格中, 单击 "**浏览**" 并导航到要导入的 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="d6949-112">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="d6949-113">单击 "**导入**</span><span class="sxs-lookup"><span data-stu-id="d6949-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="d6949-114">阻止导入错误</span><span class="sxs-lookup"><span data-stu-id="d6949-114">Prevent import errors</span></span>      
<span data-ttu-id="d6949-115">如果任何必需的数据丢失或无效, 则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="d6949-115">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="d6949-116">根据错误的不同, 可能会生成日志文件, 其中包含有关需要更正的行和列的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d6949-116">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="d6949-117">进行必要的编辑, 然后再次尝试导入文件。</span><span class="sxs-lookup"><span data-stu-id="d6949-117">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="d6949-118">在解决所有错误之前, 不能创建或编辑任何书签。</span><span class="sxs-lookup"><span data-stu-id="d6949-118">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="d6949-119">若要帮助防止错误, 请确保导入文件格式正确:</span><span class="sxs-lookup"><span data-stu-id="d6949-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="d6949-120">包含导入模板中的标题行</span><span class="sxs-lookup"><span data-stu-id="d6949-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="d6949-121">包含导入模板中的所有列</span><span class="sxs-lookup"><span data-stu-id="d6949-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="d6949-122">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="d6949-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="d6949-123">这些列可能为空: Id、上次修改时间和上次修改者</span><span class="sxs-lookup"><span data-stu-id="d6949-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="d6949-124">"状态" 列不能为空, 此信息是必需的</span><span class="sxs-lookup"><span data-stu-id="d6949-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="d6949-125">根据 "省/市/自治区" 字段, 书签将保存为草稿、建议、计划或将自动发布。</span><span class="sxs-lookup"><span data-stu-id="d6949-125">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="d6949-126">此外, 如果包括现有书签的 Id, 则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="d6949-126">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="d6949-127">对于具有多个租户的组织, 您可以从一个租户导出您的书签并将其导入到另一个租户。</span><span class="sxs-lookup"><span data-stu-id="d6949-127">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="d6949-128">但您必须在导入前删除 Id 列中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="d6949-128">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="d6949-129">若要了解有关必需字段和推荐字段的详细信息, 请参阅[创建书签](create-bookmarks.md)。</span><span class="sxs-lookup"><span data-stu-id="d6949-129">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
