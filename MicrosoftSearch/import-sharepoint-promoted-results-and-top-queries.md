---
title: 导入 SharePoint 推荐结果和热门查询
ms.author: dawholl
author: dawholl
manager: kellis
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
ms.openlocfilehash: ae3535e322c4d06505595018669d8bd87171b9a9
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699868"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>导入 SharePoint 推荐结果和热门查询

> [!IMPORTANT]
> 本文适用于 Bing 管理门户中的 Microsoft 搜索。 我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将必应中的 Microsoft 搜索门户删除。 我们建议你使用 Microsoft 365 管理中心快速开始。 [Microsoft 搜索概述](overview-microsoft-search.md)。
    
为了利用用户在 SharePoint 中创建的查询和最佳匹配，Microsoft Search 包含两个工具，可将此信息作为建议的书签导入： 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>导入 SharePoint 升级的结果查询规则

将这些规则（以前称为 "最佳匹配"）导入为建议的书签。 若要使其对用户可用，请发布它们。 发布时间根据您选择的书签数而变化。
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>使用 PowerShell 导入热门 SharePoint 查询

- 从你的 SharePoint 下载最热门的查询。 PowerShell 脚本将提示你输入 SharePoint 管理员凭据。
    
- 对每个最上面的查询运行 SharePoint 搜索，以获取最主要的搜索结果。
    
- 将建议的书签添加到管理门户。
    
- 首要的 SharePoint 查询是书签的理想候选项。 使用 PowerShell 脚本将其作为建议的书签导入。 此脚本将执行以下操作：
    - 添加基于 SharePoint top 查询建议的书签，以改进 Microsoft 搜索书签覆盖范围。 此脚本下载可从 SharePoint 管理门户访问的最前面的查询，然后将它们作为建议的书签上传，以供管理员在 Microsoft 搜索管理门户中进行审阅。
    - 默认情况下，该脚本会将建议的书签添加到给定租户中所有可用的月份。 它获取来自给定 SharePoint 管理网站的 top 查询，并将它们作为建议的书签添加到 Microsoft Search 中。 建议的书签需要管理员/编辑器才能在发布之前在管理门户中批准它们。 运行此脚本时，系统会提示你提供用于访问 Microsoft Search 管理门户的凭据。
    - 该脚本允许指定其他参数。 例如，您可以在每个可用月中将建议书签添加到给定租户中的前 N 个查询。
    - （可选）可以在给定的一年中向给定租户添加建议的书签以查找月。 此命令从 SharePoint 管理网站中获取给定时间段的 top 查询，并将其作为建议书签添加到 Microsoft Search 中。
    - 此外，还有许多其他选项和命令模式：将顶部的查询从 SharePoint 下载到指定的文件夹，在安全模式下运行脚本，在详细模式下运行脚本，并使用调试模式。
    - [在此处](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip)下载脚本。 

若要了解有关要求、示例和可用参数的信息，请下载脚本并查看自述文件。 运行 PowerShell 脚本后，管理员或编辑器应查看建议的书签，并在发布之前进行任何必要的编辑。