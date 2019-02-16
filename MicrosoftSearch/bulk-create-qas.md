---
title: 批量创建 Q&As
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
description: 使用 Microsoft Search administration portal 中的导入工具快速添加对常见问题的解答
ms.openlocfilehash: 53f1d167948f6b621ad139620553df51b0cb91c2
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068392"
---
# <a name="bulk-create-qas"></a>批量创建 Q&As

下载并使用 .csv 模板批量创建或批量编辑 Q&As。这也是批量保存草稿 Q&As 的简单方法, 需要进行其他编辑或更新。如果需要批量编辑现有 Q&As, 请将其从管理门户中导出, 进行必要的编辑, 然后将其导入。
  
1. 在 "Q&As" 部分的右上角, 单击 "**导入**"
    
2. 单击 "**下载 Q&A 模板 (.csv)** "
    
3. 保存并打开 .csv 文件
    
4. 添加 Q&A 内容和设置并保存文件
    
5. 在 "Q&As" 部分的右上角, 单击 "**导入**"
    
6. 在 "导入 Q&As" 窗格中, 单击 "**浏览**" 并导航到要导入的 .csv 文件 
    
7. 单击 "**导入**

# <a name="prevent-import-errors"></a>阻止导入错误      
如果任何必需的数据丢失或无效, 则会出现错误。根据错误的不同, 可能会生成日志文件, 其中包含有关需要更正的行和列的详细信息。进行必要的编辑, 然后再次尝试导入文件。

> [!NOTE]
> 在解决所有错误之前, 不能创建或编辑任何 Q&As。 

若要帮助防止错误, 请确保导入文件格式正确:
- 包含导入模板中的标题行
- 包含导入模板中的所有列
- 列顺序与导入模板相同
- 这些列可能为空: Id、上次修改时间和上次修改者
- "状态" 列不能为空, 此信息是必需的  
根据 "省/市/自治区" 字段, Q&As 将保存为草稿、建议、计划或将自动发布。

此外, 如果包括现有 Q&A 的 Id, 则会将其替换为导入文件中的信息。

对于具有多个租户的组织, 您可以从一个租户导出您的 Q&As, 然后将其导入到另一个租户。但您必须在导入前删除 Id 列中的所有数据。

若要了解有关必需字段和推荐字段的详细信息, 请参阅[Create Q&As](create-qas.md)。

  

