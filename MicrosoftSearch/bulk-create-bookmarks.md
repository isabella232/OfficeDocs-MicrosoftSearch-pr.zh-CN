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
description: 使用 Microsoft 搜索管理门户的导入工具一次性创建大量书签
ms.openlocfilehash: 560cda6f94060d428f2d18cc61bd2430cb31b474
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968345"
---
# <a name="bulk-create-bookmarks"></a>批量创建书签

> [!IMPORTANT]
> Microsoft 365 管理中心现提供有 Microsoft 必应搜索设置。 从在管理中心[分配搜索管理员](https://docs.microsoft.com/zh-CN/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)开始入手。
    
下载和使用 .csv 模板，批量创建、编辑并保存书签。 若要批量编辑现有书签，请从管理门户将其导出，完成必要的编辑，然后再将其导入。
  
1. 在“书签”部分的右上角，单击“**导入**”
    
2. 单击“**下载书签模板 (.csv)**”
    
3. 保存并打开该 .csv 文件
    
4. 添加书签内容和设置，并保存文件

    .csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误
    
5. 在“书签”部分的右上角，单击“**导入**”
    
6. 在导入书签窗格中，单击“**浏览**”并导航至想要导入的 .csv 文件 
    
7. 单击“**导入**”

# <a name="prevent-import-errors"></a>防止导入错误      
若所需的任何数据缺失或无效，则会出现错误。 出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。 完成必要的编辑，并再次尝试导入该文件。

> [!NOTE]
> 更正所有错误后才能创建或编辑书签。 

为了帮助防止出错，请确保导入文件具有正确格式：
- 包含导入模板中的标题行
- 包含导入模板中的所有列
- 列顺序与导入模板相同
- 这些列可能为空：ID、上次修改时间和上次修改者
- “状态”列不能为空，因为此信息是必需的  
基于“状态”字段，书签会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。

此外，如果包含现有书签的 ID，则会将其替换为导入文件中的信息。

对于拥有多个租户的组织，你可以从某个租户导出书签并将其导入另一个租户。 但是，在导入之前，你必须删除 ID 列中的数据。

若要详细了解必填字段和建议填写的字段，请参阅[创建书签](create-bookmarks.md)。
