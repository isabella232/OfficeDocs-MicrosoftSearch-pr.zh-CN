---
title: 管理 Q&As
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
description: 查找和逐个更新答案或使用可用的 Microsoft 搜索工具来一次性彻底对其进行编辑
ms.openlocfilehash: c0f6b42aa1e0ad8c4736d37ec4dcc8cff6025dbc
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378536"
---
# <a name="manage-qas"></a>管理 Q&As

随时间推移，您可能需要更新 Q&A 状态和保留相关的内容。
  
## <a name="filter-qas"></a>筛选器 Q&As

使用 Q&As 页面的右上角的筛选器选项的日期和修改者查找 Q&As。例如，设置为 30 天的日期滑块，然后选择管理员或编辑器 Q&As 他们已创建或更改该时间的列表，请参阅。
  
## <a name="change-qa-content-or-settings"></a>更改内容的 Q&A 或设置

1. 转到 Microsoft 搜索管理门户
    
2. 在导航窗格中，单击**Q&As**
    
3. 若要查找 Q&A、 搜索、 筛选器，或单击 Q&A 状态缩小结果的范围
    
4. 若要更改或更新 Q&A，请单击标题
    
5. 对内容或设置和显示方式将的预览进行任何更改或更新
    
6. 单击“保存”****
    
## <a name="bulk-export-and-edit-qas"></a>批量导出和编辑 Q&As

从不编辑这些字段中的数据：
  
- Id
    
- 上次修改时间
    
- 上次修改者
    
Id 是每个 Q&A 的唯一标识符，应永远不会进行编辑。仅应使用上次修改时间和上次修改者字段进行排序和查找 Q&As。
  
1. 如果您想要导出的您 Q&As 子集，对其进行筛选
    
2. 在 Q&As 页的右上角，单击**导出**
    
3. 保存或打开的.csv 文件
    
4. 编辑任何这些字段的数据：
    
   - 问题
    
   - URL
      
   - 关键字
    
   - State
    
   - 应答说明
    
   - 保留的关键字
    
   - 开始日期
    
   - 结束日期
    
   - 国家/地区
    
   - 组
    
   - 设备&amp;OS
    
   - 目标变体
    
5. 保存.csv 文件
    
6. 在 Q&As 页面的右上角，单击**导入**
    
7. 在导入 Q&As 窗格中，单击**浏览**并选择已编辑的.csv 文件 
    
8. 单击**导入**
    
如果任何所需的数据丢失或无效，您将收到错误。根据此错误，可能的行和列的需要更正的详细信息会生成日志文件。进行任何必要的编辑，并再次尝试导入该文件。
  
> [!NOTE]
> 直到解决所有错误，您无法创建或编辑任何 Q&As。 
  
并非所有的字段是必需的和必填的字段取决于 Q&A 状态。根据状态字段，Q&As 将保存为草稿、 建议，安排，或将自动发布。了解更多有关中[创建 Q&As](create-qas.md)必需和建议的字段。

  

