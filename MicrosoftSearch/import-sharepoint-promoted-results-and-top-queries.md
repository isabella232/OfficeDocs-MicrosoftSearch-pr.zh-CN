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
description: 使用 SharePoint 中的搜索查询为 Microsoft 搜索创建工作结果
ms.openlocfilehash: 1538c57a7b4138b36fe62e3076feb58d746b2b3e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591599"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="c7433-103">导入 SharePoint 推荐结果和热门查询</span><span class="sxs-lookup"><span data-stu-id="c7433-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7433-104">本文适用于 Microsoft 必应搜索管理门户。</span><span class="sxs-lookup"><span data-stu-id="c7433-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="c7433-105">我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将其删除。</span><span class="sxs-lookup"><span data-stu-id="c7433-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="c7433-106">我们建议你使用 Microsoft 365 管理中心快速开始。</span><span class="sxs-lookup"><span data-stu-id="c7433-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="c7433-107">[Microsoft 搜索概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="c7433-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="c7433-108">为了利用用户的查询和 SharePoint​​ 中已创建的最佳匹配，Microsoft 搜索包含两种工具，以便将此类信息导入为推荐书签：</span><span class="sxs-lookup"><span data-stu-id="c7433-108">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="c7433-109">导入 SharePoint​​ 推荐结果查询规则</span><span class="sxs-lookup"><span data-stu-id="c7433-109">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="c7433-110">将这些规则（之前称为“最佳匹配”）导入为推荐书签。</span><span class="sxs-lookup"><span data-stu-id="c7433-110">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="c7433-111">要让用户能使用这些书签，需发布书签。</span><span class="sxs-lookup"><span data-stu-id="c7433-111">To make them available to your users, publish them.</span></span> <span data-ttu-id="c7433-112">发布时间取决于选择的书签数量。</span><span class="sxs-lookup"><span data-stu-id="c7433-112">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="c7433-113">使用 PowerShell 导入热门 SharePoint​​ 查询</span><span class="sxs-lookup"><span data-stu-id="c7433-113">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="c7433-114">从 SharePoint​​ 下载热门查询。</span><span class="sxs-lookup"><span data-stu-id="c7433-114">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="c7433-115">PowerShell 脚本会提示提供 SharePoint​​ 管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="c7433-115">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="c7433-116">为每个热门查询运行 SharePoint 搜索以获取热门搜索结果。</span><span class="sxs-lookup"><span data-stu-id="c7433-116">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="c7433-117">将推荐书签添加至管理门户。</span><span class="sxs-lookup"><span data-stu-id="c7433-117">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="c7433-118">热门 SharePoint 查询是最佳备选书签。</span><span class="sxs-lookup"><span data-stu-id="c7433-118">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="c7433-119">使用 PowerShell 脚本将它们导入为推荐书签。</span><span class="sxs-lookup"><span data-stu-id="c7433-119">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="c7433-120">此脚本将起到以下作用：</span><span class="sxs-lookup"><span data-stu-id="c7433-120">This script will:</span></span>
    
<span data-ttu-id="c7433-121">若要详细了解要求、示例和可用参数，请下载该脚本并查看自述文件。</span><span class="sxs-lookup"><span data-stu-id="c7433-121">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="c7433-122">在 PowerShell 脚本运行后，管理员或编辑者应查看推荐书签，并在发布之前完成必要的编辑。</span><span class="sxs-lookup"><span data-stu-id="c7433-122">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

