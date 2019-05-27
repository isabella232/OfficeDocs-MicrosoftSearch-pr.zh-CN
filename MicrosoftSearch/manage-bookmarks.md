---
title: 管理书签
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: 查找需要更新的书签及如何批量编辑 Microsoft 搜索的书签结果
ms.openlocfilehash: d5cebbfd5779bc8a6aa25cdbcdedb6e9b18f242e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968481"
---
# <a name="manage-bookmarks"></a>管理书签

> [!IMPORTANT]
> Microsoft 365 管理中心现提供有 Microsoft 必应搜索设置。 从在管理中心[分配搜索管理员](https://docs.microsoft.com/zh-CN/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)开始入手。
    
随着时间推移，可能需要更新书签状态和内容以保持其相关性。 
  
## <a name="filter-bookmarks"></a>筛选书签

使用“书签”页面右上角的筛选器选项，可以按日期和修改人来查找书签。 例如，将日期滑块设置为 30 天并选择一位管理员或编辑者，即可查看他在该时间段内创建或更改过的书签列表。
  
## <a name="change-bookmark-content-or-settings"></a>更改书签内容或设置

1. 转到 Microsoft 搜索管理门户
    
2. 在导航窗格中，单击“书签”****
    
3. 若要查找书签，请搜索、筛选或单击某个书签状态来细化自己的结果
    
4. 若要更改或更新书签，请单击其标题
    
5. 更改或更新内容或设置，并预览其显示效果 
    
6. 单击“**保存**”
    
## <a name="bulk-export-and-edit-bookmarks"></a>批量导出和编辑书签

请勿编辑以下字段中的数据：
  
- ID
    
- 上次修改时间
    
- 上次修改者
    
ID 是每个书签的唯一标识符，请勿编辑。 “上次修改时间”和“上次修改者”字段应仅用于排序和查找书签。
  
1. 若想导出书签的子集，请对书签进行筛选
    
2. 在“书签”页面的右上角，单击“**导出**”
    
3. 保存或打开该 .csv 文件
    
4. 可编辑以下字段中的数据：
   - 标题
    
   - URL
    
   - 关键字
    
   - 状态
    
   - 说明
    
   - 保留关键字
    
   - 开始日期
    
   - 结束日期
    
   - 国家/地区
    
   - 组
    
   - 设备&amp;操作系统
    
   - 目标变体
    
5. 保存 .csv 文件

    .csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误
    
6. 在“书签”页面的右上角，单击“**导入**”
    
7. 在导入书签窗格中，单击“**浏览**”并选择编辑过的 .csv 文件 
    
8. 单击“**导入**”