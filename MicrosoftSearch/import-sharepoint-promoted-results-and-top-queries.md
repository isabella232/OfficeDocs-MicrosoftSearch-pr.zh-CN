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
description: 使用搜索查询从SharePoint创建工作结果Microsoft 搜索
ms.openlocfilehash: cfd5fafd0529f537a55e436ef078800a4b9714177e04c63e65e968f16fcf322e
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533821"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>导入 SharePoint 推荐结果和热门查询

> [!IMPORTANT]
> 本文适用于管理Microsoft 搜索中的必应。 我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将必应中的 Microsoft 搜索门户删除。 我们建议你使用 Microsoft 365 管理中心快速开始。 [Microsoft 搜索概述](overview-microsoft-search.md)。
    
若要利用用户查询和在 SharePoint 中创建的最佳匹配，Microsoft 搜索两种工具将此信息导入为建议的书签： 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>导入SharePoint升级的结果查询规则

导入这些规则（以前称为最佳匹配）作为建议的书签。 若要使其可供用户使用，请发布它们。 发布时间因选择的书签数而异。
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>使用 PowerShell SharePoint热门查询

- 从应用程序下载SharePoint。 PowerShell 脚本将提示您输入SharePoint凭据。
    
- 针对SharePoint查询运行一个搜索，获取排名居首的搜索结果。
    
- 将建议的书签添加到管理门户。
    
- 您SharePoint查询是很好的书签候选项。 使用 PowerShell 脚本将其导入为建议的书签。 此脚本执行以下工作：
    - 根据热门查询添加SharePoint书签，以提高Microsoft 搜索范围。 此脚本下载可从 SharePoint 管理门户访问的热门查询，然后将这些查询作为建议书签上载，供管理员在 Microsoft 搜索 管理门户中查看。
    - 默认情况下，脚本会向给定租户添加所有可用月份的建议书签。 它从给定管理员网站获取SharePoint查询，并作为Microsoft 搜索添加到网站。 建议的书签需要管理员/编辑器在发布之前在管理门户中批准它们。 运行此脚本时，系统将提示你提供凭据，以访问Microsoft 搜索门户。
    - 该脚本允许指定其他参数。 例如，可以将建议的书签添加到每个可用月份中前 N 个查询的给定租户。
    - （可选）可以在给定年份的几个月内将建议书签添加到给定租户。 此命令从管理员网站获取给定时间段SharePoint查询，并将这些查询作为Microsoft 搜索书签添加到网站。
    - 此外，还有其他许多选项和命令模式：将热门查询从 SharePoint 下载到指定文件夹、在 保险箱 模式下运行脚本、在详细模式下运行脚本和调试模式。
    - 在此处下载 [脚本](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip)。 

有关要求、示例和可用参数的信息，请下载脚本并查看自述文件。 PowerShell 脚本运行后，管理员或编辑人员应在发布建议书签之前查看建议书签并进行必要的编辑。