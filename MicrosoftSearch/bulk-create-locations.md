---
title: 批量创建位置
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
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
description: 使用 Microsoft Search administration portal 的导入工具一次添加多个位置
ms.openlocfilehash: eb51b93ceaa560e5142ac46d316ba745c614fe34
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068408"
---
# <a name="bulk-create-locations"></a>批量创建位置

下载并使用 .csv 模板以批量创建、编辑和保存位置。 
  
1. 在 "位置" 部分的右上角, 单击 "**导入**"
    
2. 单击 "**下载位置" 模板 (.csv)**
    
3. 保存并打开 .csv 文件
    
4. 添加位置内容并保存文件
    
5. 在 "位置" 部分的右上角, 单击 "**导入**"
    
6. 在 "导入位置" 窗格中, 单击 "**浏览**" 并导航到要导入的 .csv 文件 
    
7. 单击 "**导入**

"导入" 和 "导出位置" 模板中的字段相同。您可以导出、批量编辑和导入编辑, 或从空模板开始, 以批量创建新位置。若要批量编辑现有位置, 请从管理门户中导出它们, 进行必要的编辑, 然后将其导入。

# <a name="prevent-import-errors"></a>阻止导入错误  
如果任何必需的数据丢失或无效, 则会出现错误。根据错误的不同, 可能会生成日志文件, 其中包含有关需要更正的行和列的详细信息。进行必要的编辑, 然后再次尝试导入文件。
  
> [!NOTE]
> 在解决所有错误之前, 不能创建或编辑任何位置。 

若要帮助防止错误, 请确保导入文件格式正确:
- 包含导入模板中的标题行
- 包含导入模板中的所有列
- 列顺序与导入模板相同
- 这些列可以为空: Id、上次修改时间、上次修改者和 Lat/长时间  
我们将尝试根据地址 (如果该字段为空) 来确定 lat/长时间
- "状态" 列不能为空, 此信息是必需的  
根据 "省/市/自治区" 字段, 位置将保存为草稿、建议、计划或将自动发布。

此外, 如果您包含现有位置的 Id, 则会将其替换为导入文件中的信息。

对于具有多个租户的组织, 您可以从一个租户导出位置并将其导入到另一个租户。但您必须在导入前删除 Id 列中的所有数据。
  
若要了解有关必需字段和推荐字段的详细信息, 请参阅[添加位置](add-a-location.md)。

  

