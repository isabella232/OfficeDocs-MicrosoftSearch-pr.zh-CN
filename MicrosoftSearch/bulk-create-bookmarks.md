---
title: 批量创建书签
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
description: 使用 Microsoft Search administration portal 的导入工具一次创建大量书签
ms.openlocfilehash: 7c134784f0ca0d4cc84d5bce3a98f7e75aa6f441
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508616"
---
# <a name="bulk-create-bookmarks"></a>批量创建书签

下载并使用 .csv 模板以批量创建、编辑和保存书签。 若要批量编辑现有书签, 请从管理门户中导出它们, 进行必要的编辑, 然后将其导入。
  
1. 在 "书签" 部分的右上角, 单击 "**导入**"
    
2. 单击 "**下载书签模板 (.csv)** "
    
3. 保存并打开 .csv 文件
    
4. 添加书签内容和设置并保存文件

    .csv 文件应保存为 csv utf-8 文件, 其他文件类型和或编码可能导致导入错误
    
5. 在 "书签" 部分的右上角, 单击 "**导入**"
    
6. 在 "导入书签" 窗格中, 单击 "**浏览**" 并导航到要导入的 .csv 文件 
    
7. 单击 "**导入**

# <a name="prevent-import-errors"></a>阻止导入错误      
如果任何必需的数据丢失或无效, 则会出现错误。 根据错误的不同, 可能会生成日志文件, 其中包含有关需要更正的行和列的详细信息。 进行必要的编辑, 然后再次尝试导入文件。

> [!NOTE]
> 在解决所有错误之前, 不能创建或编辑任何书签。 

若要帮助防止错误, 请确保导入文件格式正确:
- 包含导入模板中的标题行
- 包含导入模板中的所有列
- 列顺序与导入模板相同
- 这些列可能为空: Id、上次修改时间和上次修改者
- "状态" 列不能为空, 此信息是必需的  
根据 "省/市/自治区" 字段, 书签将保存为草稿、建议、计划或将自动发布。

此外, 如果包括现有书签的 Id, 则会将其替换为导入文件中的信息。

对于具有多个租户的组织, 您可以从一个租户导出您的书签并将其导入到另一个租户。 但您必须在导入前删除 Id 列中的所有数据。

若要了解有关必需字段和推荐字段的详细信息, 请参阅[创建书签](create-bookmarks.md)。
