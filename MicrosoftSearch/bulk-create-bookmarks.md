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
ROBOTS: NoIndex
description: 使用 Microsoft Search Administration portal 的导入工具一次创建大量书签
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948921"
---
# <a name="bulk-create-bookmarks"></a>批量创建书签

> [!IMPORTANT]
> 本文适用于必应中的 Microsoft 搜索管理门户。 我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将必应中的 Microsoft 搜索门户删除。 我们建议你使用 Microsoft 365 管理中心快速开始。 [Microsoft 搜索概述](overview-microsoft-search.md)。
    
下载并使用 .csv 模板以批量创建、编辑和保存书签。 若要批量编辑现有书签，请从管理门户中导出它们，进行必要的编辑，然后将其导入。
  
1. 在 "书签" 部分的右上角，单击 "**导入**"
    
2. 单击 "**下载书签模板（.csv）** "
    
3. 保存并打开该 .csv 文件
    
4. 添加书签内容和设置并保存文件

    .csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误
    
5. 在 "书签" 部分的右上角，单击 "**导入**"
    
6. 在 "导入书签" 窗格中，单击 "**浏览**" 并导航到要导入的 .csv 文件 
    
7. 单击“**导入**”

## <a name="prevent-import-errors"></a>防止导入错误      
若所需的任何数据缺失或无效，则会出现错误。 出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。 完成必要的编辑，并再次尝试导入该文件。

> [!NOTE]
> 在解决所有错误之前，不能创建或编辑任何书签。 

为了帮助防止出错，请确保导入文件具有正确格式：
- 包含导入模板中的标题行
- 包含导入模板中的所有列
- 列顺序与导入模板相同
- 这些列可能为空：ID、上次修改时间和上次修改者
- “状态”列不能为空，因为此信息是必需的  
基于“状态”字段，书签会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。

此外，如果包括现有书签的 Id，则会将其替换为导入文件中的信息。

对于管理多个组织的合作伙伴，您可以从一个组织中导出您的书签并将其导入到另一个组织中。 但是，在导入之前，你必须删除 ID 列中的数据。

若要了解有关必需字段和推荐字段的详细信息，请参阅[创建书签](create-bookmarks.md)。
