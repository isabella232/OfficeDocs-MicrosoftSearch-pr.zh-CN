---
title: 管理问答
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: 查找和更新单个解答或使用可用的 Microsoft 搜索工具同时编辑所有解答
ms.openlocfilehash: ee239aa73d4e650289f39d33c63c3e2df4f100cc
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968465"
---
# <a name="manage-qas"></a>管理问答

> [!IMPORTANT]
> Microsoft 365 管理中心现提供有 Microsoft 必应搜索设置。 从在管理中心[分配搜索管理员](https://docs.microsoft.com/zh-CN/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)开始入手。
    
随着时间推移，你可能需要更新问答的状态和内容以保持它的相关性。
  
## <a name="filter-qas"></a>筛选问答

使用“问答”页面右上角的筛选器选项，可以按日期和修改人来查找问答。 例如，将日期滑块设置为 30 天并选择一位管理员或编辑者，即可查看他在该时间段内创建或更改过的问答列表。
  
## <a name="change-qa-content-or-settings"></a>更改问答内容或设置

1. 转到 Microsoft 搜索管理门户
    
2. 在导航窗格中，单击“问答”****
    
3. 若要查找问答，请搜索、筛选或单击某个问答状态来细化自己的结果
    
4. 若要更改或更新问答，请单击其标题
    
5. 更改或更新内容或设置，并预览其显示效果
    
6. 单击“**保存**”
    
## <a name="bulk-export-and-edit-qas"></a>批量导出和编辑问答

请勿编辑以下字段中的数据：
  
- ID
    
- 上次修改时间
    
- 上次修改者
    
ID 是每个问答的唯一标识符，请勿编辑。 上次修改时间和上次修改者应仅用于排序和查找问答。
  
1. 若想导出问答的子集，请对它们进行筛选
    
2. 在“问答”页面的右上角，单击“**导出**”
    
3. 保存或打开该 .csv 文件
    
4. 可编辑以下字段中的数据：
    
   - 问题
    
   - URL
      
   - 关键字
    
   - 状态
    
   - 解答说明
    
   - 保留关键字
    
   - 开始日期
    
   - 结束日期
    
   - 国家/地区
    
   - 组
    
   - 设备&amp;操作系统
    
   - 目标变体
    
5. 保存 .csv 文件

    .csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误
    
6. 在“问答”页面的右上角，单击“**导入**”
    
7. 在“导入问答”窗格中，单击“**浏览**”并选择编辑过的 .csv 文件 
    
8. 单击“**导入**”
    
若所需的任何数据缺失或无效，则会出现错误。 出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。 完成必要的编辑，并再次尝试导入该文件。
  
> [!NOTE]
> 更正所有错误后才能创建或编辑任何问答。 
  
无需填写所有字段，且必填字段会因问答的状态而有所不同。 基于状态字段，问答会保存为草稿问答、推荐问答、已计划问答或自动发布的问答。 若要详细了解必填字段和建议填写的字段，请参阅[创建问答](create-qas.md)。

  

