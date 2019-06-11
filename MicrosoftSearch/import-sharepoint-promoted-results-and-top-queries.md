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
ROBOTS: NOINDEX
description: 使用 SharePoint 中的搜索查询创建 Microsoft Search 的工作结果
ms.openlocfilehash: 59d133aceb15c8f1fa75ecc3f35522def4201d0a
ms.sourcegitcommit: 9a9d24b4b7a6f3e80b89086d29fd369ebded0619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "34810643"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="8f451-103">导入 SharePoint 推荐结果和热门查询</span><span class="sxs-lookup"><span data-stu-id="8f451-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f451-104">本文适用于 Bing 管理门户中的 Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="8f451-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="8f451-105">我们正在将门户移动到 Microsoft 365 管理中心, 然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="8f451-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="8f451-106">建议使用 Microsoft 365 管理中心开始。</span><span class="sxs-lookup"><span data-stu-id="8f451-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="8f451-107">[Microsoft Search 概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="8f451-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="8f451-108">为了利用用户在 SharePoint 中创建的查询和最佳匹配, Microsoft Search 包含两个工具, 可将此信息作为建议的书签导入:</span><span class="sxs-lookup"><span data-stu-id="8f451-108">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="8f451-109">导入 SharePoint 升级的结果查询规则</span><span class="sxs-lookup"><span data-stu-id="8f451-109">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="8f451-110">将这些规则 (以前称为 "最佳匹配") 导入为建议的书签。</span><span class="sxs-lookup"><span data-stu-id="8f451-110">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="8f451-111">若要使其对用户可用, 请发布它们。</span><span class="sxs-lookup"><span data-stu-id="8f451-111">To make them available to your users, publish them.</span></span> <span data-ttu-id="8f451-112">发布时间根据您选择的书签数而变化。</span><span class="sxs-lookup"><span data-stu-id="8f451-112">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="8f451-113">使用 PowerShell 导入热门 SharePoint 查询</span><span class="sxs-lookup"><span data-stu-id="8f451-113">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="8f451-114">从你的 SharePoint 下载最热门的查询。</span><span class="sxs-lookup"><span data-stu-id="8f451-114">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="8f451-115">PowerShell 脚本将提示你输入 SharePoint 管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="8f451-115">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="8f451-116">对每个最上面的查询运行 SharePoint 搜索, 以获取最主要的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="8f451-116">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="8f451-117">将建议的书签添加到管理门户。</span><span class="sxs-lookup"><span data-stu-id="8f451-117">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="8f451-118">首要的 SharePoint 查询是书签的理想候选项。</span><span class="sxs-lookup"><span data-stu-id="8f451-118">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="8f451-119">使用 PowerShell 脚本将其作为建议的书签导入。</span><span class="sxs-lookup"><span data-stu-id="8f451-119">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="8f451-120">此脚本将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="8f451-120">This script does the following work:</span></span>
    - <span data-ttu-id="8f451-121">添加基于 SharePoint top 查询建议的书签, 以改进 Microsoft 搜索书签覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="8f451-121">Adds suggested bookmarks based on SharePoint top queries to improve Microsoft Search bookmark coverage.</span></span> <span data-ttu-id="8f451-122">此脚本下载可从 SharePoint 管理门户访问的最前面的查询, 然后将它们作为建议的书签上传, 以供管理员在 Microsoft 搜索管理门户中进行审阅。</span><span class="sxs-lookup"><span data-stu-id="8f451-122">This script downloads the top queries accessible from SharePoint admin portal, and then uploads them as suggested bookmarks for an admin to review in the Microsoft Search admin portal.</span></span>
    - <span data-ttu-id="8f451-123">默认情况下, 该脚本会将建议的书签添加到给定租户中所有可用的月份。</span><span class="sxs-lookup"><span data-stu-id="8f451-123">By default, the script adds suggested bookmarks to given tenant for all available months.</span></span> <span data-ttu-id="8f451-124">它获取来自给定 SharePoint 管理网站的 top 查询, 并将它们作为建议的书签添加到 Microsoft Search 中。</span><span class="sxs-lookup"><span data-stu-id="8f451-124">It gets top queries from a given SharePoint admin website and adds them to Microsoft Search as suggested bookmarks.</span></span> <span data-ttu-id="8f451-125">建议的书签需要管理员/编辑器才能在发布之前在管理门户中批准它们。</span><span class="sxs-lookup"><span data-stu-id="8f451-125">Suggested bookmarks need an admin/editor to approve them in the admin portal before being published.</span></span> <span data-ttu-id="8f451-126">运行此脚本时, 系统会提示你提供用于访问 Microsoft Search 管理门户的凭据。</span><span class="sxs-lookup"><span data-stu-id="8f451-126">When you run this script, you are prompted for credentials to access the Microsoft Search admin portal.</span></span>
    - <span data-ttu-id="8f451-127">该脚本允许指定其他参数。</span><span class="sxs-lookup"><span data-stu-id="8f451-127">The script allows additional parameters to be specified.</span></span> <span data-ttu-id="8f451-128">例如, 您可以在每个可用月中将建议书签添加到给定租户中的前 N 个查询。</span><span class="sxs-lookup"><span data-stu-id="8f451-128">You can, for example, add suggested bookmarks to given tenant for top N queries in each of the available months.</span></span>
    - <span data-ttu-id="8f451-129">(可选) 可以在给定的一年中向给定租户添加建议的书签以查找月。</span><span class="sxs-lookup"><span data-stu-id="8f451-129">Optionally, you can add suggested bookmarks to given tenant for months in the given year.</span></span> <span data-ttu-id="8f451-130">此命令从 SharePoint 管理网站中获取给定时间段的 top 查询, 并将其作为建议书签添加到 Microsoft Search 中。</span><span class="sxs-lookup"><span data-stu-id="8f451-130">This command gets top queries for the given time period from SharePoint admin website and adds them to Microsoft Search as suggested bookmarks.</span></span>
    - <span data-ttu-id="8f451-131">此外, 还有许多其他选项和命令模式: 将顶部的查询从 SharePoint 下载到指定的文件夹, 在安全模式下运行脚本, 在详细模式下运行脚本, 并使用调试模式。</span><span class="sxs-lookup"><span data-stu-id="8f451-131">As well, there are numerous other options and command modes: download top queries from SharePoint to a specified folder, run the script in Safe mode, run the script in Verbose mode, and a Debug mode.</span></span>
    - <span data-ttu-id="8f451-132">[在此处](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip)下载脚本。</span><span class="sxs-lookup"><span data-stu-id="8f451-132">Download the script [here](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip).</span></span> 

<span data-ttu-id="8f451-133">若要了解有关要求、示例和可用参数的信息, 请下载脚本并查看自述文件。</span><span class="sxs-lookup"><span data-stu-id="8f451-133">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="8f451-134">运行 PowerShell 脚本后, 管理员或编辑器应查看建议的书签, 并在发布之前进行任何必要的编辑。</span><span class="sxs-lookup"><span data-stu-id="8f451-134">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>