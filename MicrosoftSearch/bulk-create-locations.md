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
description: 利用 Microsoft 搜索管理门户中的导入工具一次添加多个位置
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968289"
---
# <a name="bulk-create-locations"></a>批量创建位置

> [!IMPORTANT]
> Microsoft 365 管理中心现提供有 Microsoft 必应搜索设置。 从在管理中心[分配搜索管理员](https://docs.microsoft.com/zh-CN/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)开始入手。
    
下载和使用 .csv 模板，批量创建、编辑并保存位置。 
  
1. 在“位置”部分的右上角，单击“**导入**”
    
2. 单击“**下载位置模板 (.csv)**”
    
3. 保存并打开该 .csv 文件
    
4. 添加位置内容并保存文件

    .csv 文件应保存为 CSV UTF-8 文件，其他文件类型和/或编码可能会导致导入错误
    
5. 在“位置”部分的右上角，单击“**导入**”
    
6. 在导入位置窗格中，单击“**浏览**”并导航至想要导入的 .csv 文件 
    
7. 单击“**导入**”

导入问答和导出位置模板中的字段相同。 可以导出、批量编辑和导入编辑内容，也可使用空白模板批量创建新位置。 若要批量编辑现有位置，请从管理门户将其导出，完成必要的编辑，然后再将其导入。

# <a name="prevent-import-errors"></a>防止导入错误  
若所需的任何数据缺失或无效，则会出现错误。 出错时，视具体错误而定，可能会生成包含详细信息的日志文件，其中指出需要更正的行和列。 完成必要的编辑，并再次尝试导入该文件。
  
> [!NOTE]
> 更正所有错误后才能创建或编辑位置。 

为了帮助防止出错，请确保导入文件具有正确格式：
- 包含导入模板中的标题行
- 包含导入模板中的所有列
- 列顺序与导入模板相同
- 这些列可能为空：ID、上次修改时间、上次修改者和纬度/经度  
如果该字段为空，则我们将会尝试根据地址确定纬度/经度
- “状态”列不能为空，因为此信息是必需的  
基于“状态”字段，位置会保存为草稿书签、推荐书签、已计划书签或自动发布的书签。

此外，如果包含现有位置的 ID，则会将其替换为导入文件中的信息。

对于拥有多个租户的组织，你可以从某个租户导出位置并将其导入另一个租户。 但是，在导入之前，你必须删除 ID 列中的数据。
  
若要详细了解必填字段和建议填写的字段，请参阅[添加位置](add-a-location.md)。

  

