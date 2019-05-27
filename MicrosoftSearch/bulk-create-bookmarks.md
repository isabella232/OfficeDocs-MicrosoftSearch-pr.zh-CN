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
description: 使用 Microsoft 搜索管理门户的导入工具一次性创建大量书签
ms.openlocfilehash: 560cda6f94060d428f2d18cc61bd2430cb31b474
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968345"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="52c0c-103">批量创建书签</span><span class="sxs-lookup"><span data-stu-id="52c0c-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52c0c-104">Microsoft 365 管理中心现提供有 Microsoft 必应搜索设置。</span><span class="sxs-lookup"><span data-stu-id="52c0c-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="52c0c-105">从在管理中心[分配搜索管理员](https://docs.microsoft.com/zh-CN/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)开始入手。</span><span class="sxs-lookup"><span data-stu-id="52c0c-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="52c0c-106">下载和使用 .csv 模板，批量创建、编辑并保存书签。</span><span class="sxs-lookup"><span data-stu-id="52c0c-106">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="52c0c-107">若要批量编辑现有书签，请从管理门户将其导出，完成必要的编辑，然后再将其导入。</span><span class="sxs-lookup"><span data-stu-id="52c0c-107">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="52c0c-108">在“书签”部分的右上角，单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="52c0c-108">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="52c0c-109">单击“**下载书签模板 (.csv)**”</span><span class="sxs-lookup"><span data-stu-id="52c0c-109">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="52c0c-110">保存并打开该 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="52c0c-110">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="52c0c-111">添加书签内容和设置，并保存文件</span><span class="sxs-lookup"><span data-stu-id="52c0c-111">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="52c0c-112">.csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误</span><span class="sxs-lookup"><span data-stu-id="52c0c-112">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="52c0c-113">在“书签”部分的右上角，单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="52c0c-113">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="52c0c-114">在导入书签窗格中，单击“**浏览**”并导航至想要导入的 .csv 文件</span><span class="sxs-lookup"><span data-stu-id="52c0c-114">In the Import bookmarks pane, select **Browse** and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="52c0c-115">单击“**导入**”</span><span class="sxs-lookup"><span data-stu-id="52c0c-115">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="52c0c-116">防止导入错误</span><span class="sxs-lookup"><span data-stu-id="52c0c-116">Prevent import errors</span></span>      
<span data-ttu-id="52c0c-117">若所需的任何数据缺失或无效，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="52c0c-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="52c0c-118">出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。</span><span class="sxs-lookup"><span data-stu-id="52c0c-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="52c0c-119">完成必要的编辑，并再次尝试导入该文件。</span><span class="sxs-lookup"><span data-stu-id="52c0c-119">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="52c0c-120">更正所有错误后才能创建或编辑书签。</span><span class="sxs-lookup"><span data-stu-id="52c0c-120">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="52c0c-121">为了帮助防止出错，请确保导入文件具有正确格式：</span><span class="sxs-lookup"><span data-stu-id="52c0c-121">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="52c0c-122">包含导入模板中的标题行</span><span class="sxs-lookup"><span data-stu-id="52c0c-122">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="52c0c-123">包含导入模板中的所有列</span><span class="sxs-lookup"><span data-stu-id="52c0c-123">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="52c0c-124">列顺序与导入模板相同</span><span class="sxs-lookup"><span data-stu-id="52c0c-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="52c0c-125">这些列可能为空：ID、上次修改时间和上次修改者</span><span class="sxs-lookup"><span data-stu-id="52c0c-125">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="52c0c-126">“状态”列不能为空，因为此信息是必需的</span><span class="sxs-lookup"><span data-stu-id="52c0c-126">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="52c0c-127">基于“状态”字段，书签会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。</span><span class="sxs-lookup"><span data-stu-id="52c0c-127">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="52c0c-128">此外，如果包含现有书签的 ID，则会将其替换为导入文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="52c0c-128">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="52c0c-129">对于拥有多个租户的组织，你可以从某个租户导出书签并将其导入另一个租户。</span><span class="sxs-lookup"><span data-stu-id="52c0c-129">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="52c0c-130">但是，在导入之前，你必须删除 ID 列中的数据。</span><span class="sxs-lookup"><span data-stu-id="52c0c-130">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="52c0c-131">若要详细了解必填字段和建议填写的字段，请参阅[创建书签](create-bookmarks.md)。</span><span class="sxs-lookup"><span data-stu-id="52c0c-131">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
