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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>导入 SharePoint 推荐结果和热门查询

为了利用用户在 SharePoint 中创建的查询和最佳匹配, Microsoft Search 包含两个工具, 可将此信息作为建议的书签导入: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>导入 SharePoint 升级的结果查询规则

将这些规则 (以前称为 "最佳匹配") 导入为建议的书签。 若要使其对用户可用, 请发布它们。 发布时间根据您选择的书签数而变化。
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>使用 PowerShell 导入热门 SharePoint 查询

- 从你的 SharePoint 下载最热门的查询。 PowerShell 脚本将提示你输入 SharePoint 管理员凭据。
    
- 对每个最上面的查询运行 SharePoint 搜索, 以获取最主要的搜索结果。
    
- 将建议的书签添加到管理门户。
    
- 首要的 SharePoint 查询是书签的理想候选项。 使用 PowerShell 脚本将其作为建议的书签导入。 此脚本将:
    
若要了解有关要求、示例和可用参数的信息, 请下载脚本并查看自述文件。 运行 PowerShell 脚本后, 管理员或编辑器应查看建议的书签, 并在发布之前进行任何必要的编辑。

  

