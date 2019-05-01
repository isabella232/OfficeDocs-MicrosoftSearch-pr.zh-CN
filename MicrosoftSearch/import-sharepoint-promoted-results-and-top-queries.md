---
title: 导入 SharePoint 推荐结果和热门查询
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/8/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
description: 使用 SharePoint 中的搜索查询创建 Microsoft search 的工作结果
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508751"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="4cc70-103">导入 SharePoint 推荐结果和热门查询</span><span class="sxs-lookup"><span data-stu-id="4cc70-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="4cc70-104">为了利用用户在 SharePoint 中创建的查询和最佳匹配, Microsoft Search 包含两个工具, 可将此信息作为建议的书签导入:</span><span class="sxs-lookup"><span data-stu-id="4cc70-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="4cc70-105">导入 SharePoint 升级的结果查询规则</span><span class="sxs-lookup"><span data-stu-id="4cc70-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="4cc70-106">将这些规则 (以前称为 "最佳匹配") 导入为建议的书签。</span><span class="sxs-lookup"><span data-stu-id="4cc70-106">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="4cc70-107">若要使其对用户可用, 请发布它们。</span><span class="sxs-lookup"><span data-stu-id="4cc70-107">To make them available to your users, publish them.</span></span> <span data-ttu-id="4cc70-108">发布时间根据您选择的书签数而变化。</span><span class="sxs-lookup"><span data-stu-id="4cc70-108">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="4cc70-109">使用 PowerShell 导入热门 SharePoint 查询</span><span class="sxs-lookup"><span data-stu-id="4cc70-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="4cc70-110">从你的 SharePoint 下载最热门的查询。</span><span class="sxs-lookup"><span data-stu-id="4cc70-110">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="4cc70-111">PowerShell 脚本将提示你输入 SharePoint 管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="4cc70-111">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="4cc70-112">对每个最上面的查询运行 SharePoint 搜索, 以获取最主要的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="4cc70-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="4cc70-113">将建议的书签添加到管理门户。</span><span class="sxs-lookup"><span data-stu-id="4cc70-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="4cc70-114">首要的 SharePoint 查询是书签的理想候选项。</span><span class="sxs-lookup"><span data-stu-id="4cc70-114">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="4cc70-115">使用 PowerShell 脚本将其作为建议的书签导入。</span><span class="sxs-lookup"><span data-stu-id="4cc70-115">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="4cc70-116">此脚本将:</span><span class="sxs-lookup"><span data-stu-id="4cc70-116">This script will:</span></span>
    
<span data-ttu-id="4cc70-117">若要了解有关要求、示例和可用参数的信息, 请下载脚本并查看自述文件。</span><span class="sxs-lookup"><span data-stu-id="4cc70-117">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="4cc70-118">运行 PowerShell 脚本后, 管理员或编辑器应查看建议的书签, 并在发布之前进行任何必要的编辑。</span><span class="sxs-lookup"><span data-stu-id="4cc70-118">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

