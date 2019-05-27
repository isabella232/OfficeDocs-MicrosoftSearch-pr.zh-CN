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
description: 使用 SharePoint 中的搜索查询为 Microsoft 搜索创建工作结果
ms.openlocfilehash: 6e55e2000792bdb576a18a0efeb353dc3ea13605
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968449"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>导入 SharePoint 推荐结果和热门查询

> [!IMPORTANT]
> Microsoft 365 管理中心现提供有 Microsoft 必应搜索设置。 从在管理中心[分配搜索管理员](https://docs.microsoft.com/zh-CN/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)开始入手。
    
为了利用用户的查询和 SharePoint​​ 中已创建的最佳匹配，Microsoft 搜索包含两种工具，以便将此类信息导入为推荐书签： 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>导入 SharePoint​​ 推荐结果查询规则

将这些规则（之前称为“最佳匹配”）导入为推荐书签。 要让用户能使用这些书签，需发布书签。 发布时间取决于选择的书签数量。
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>使用 PowerShell 导入热门 SharePoint​​ 查询

- 从 SharePoint​​ 下载热门查询。 PowerShell 脚本会提示提供 SharePoint​​ 管理员凭据。
    
- 为每个热门查询运行 SharePoint 搜索以获取热门搜索结果。
    
- 将推荐书签添加至管理门户。
    
- 热门 SharePoint 查询是最佳备选书签。 使用 PowerShell 脚本将它们导入为推荐书签。 此脚本将起到以下作用：
    
若要详细了解要求、示例和可用参数，请下载该脚本并查看自述文件。 在 PowerShell 脚本运行后，管理员或编辑者应查看推荐书签，并在发布之前完成必要的编辑。

  

