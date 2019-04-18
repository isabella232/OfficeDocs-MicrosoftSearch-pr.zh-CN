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
description: 单独查找和更新答案, 或使用 Microsoft Search 工具随时编辑它们
ms.openlocfilehash: 47882deeb95133cfc19f4eec6417fc20fb7203de
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901830"
---
# <a name="manage-qas"></a>管理问答

随着时间的推移, 您可能需要更新 Q&A's 状态和内容, 以使其保持相关。
  
## <a name="filter-qas"></a>筛选 Q&As

使用 "Q&As" 页面右上角的 "筛选器" 选项按日期查找 Q&As, 并对其进行修改。 例如, 将 "日期" 滑块设置为30天, 然后选择 "管理员" 或 "编辑" 以查看在该时间内创建或更改的 Q&As 的列表。
  
## <a name="change-qa-content-or-settings"></a>更改 Q&A 内容或设置

1. 转到 Microsoft 搜索管理门户
    
2. 在导航窗格中，单击“问答”****
    
3. 查找 Q&A、搜索、筛选或单击 Q&A 状态以缩小结果范围
    
4. 若要更改或更新 Q&A, 请单击标题
    
5. 对内容或设置进行任何更改或更新, 并预览它们的显示方式
    
6. 单击“保存”****
    
## <a name="bulk-export-and-edit-qas"></a>批量导出和编辑 Q&As

从不编辑这些字段中的数据:
  
- Id
    
- 上次修改时间
    
- 上次修改者
    
Id 是每个 Q&A 的唯一标识符, 永远不应进行编辑。 "上次修改者" 和 "上次修改者" 字段只应用于排序和查找 Q&As。
  
1. 如果要导出 Q&As 的子集, 请对其进行筛选
    
2. 在 Q&As 页面的右上角, 单击 "**导出**"
    
3. 保存或打开 .csv 文件
    
4. 编辑以下任一字段中的数据:
    
   - Question
    
   - URL
      
   - 关键字
    
   - 状态
    
   - 答案说明
    
   - 保留关键字
    
   - Start Date
    
   - End Date
    
   - 国家/地区
    
   - 组
    
   - 设备&amp;OS
    
   - 目标变体
    
5. 保存 .csv 文件

    .csv 文件应保存为 csv utf-8 文件, 其他文件类型和或编码可能导致导入错误
    
6. 在 Q&As 页面的右上角, 单击 "**导入**"
    
7. 在 "导入 Q&As" 窗格中, 单击 "**浏览**", 然后选择编辑过的 .csv 文件。 
    
8. 单击 "**导入**
    
如果任何必需的数据丢失或无效, 则会出现错误。 根据错误的不同, 可能会生成日志文件, 其中包含有关需要更正的行和列的详细信息。 进行必要的编辑, 然后再次尝试导入文件。
  
> [!NOTE]
> 在解决所有错误之前, 不能创建或编辑任何 Q&As。 
  
并非所有字段都是必填字段, 必填字段根据 Q&A 状态的不同而不同。 根据 "省/市/自治区" 字段, Q&As 将保存为草稿、建议、计划或将自动发布。 在[create Q&As](create-qas.md)中查找有关必需字段和推荐字段的详细信息。

  

