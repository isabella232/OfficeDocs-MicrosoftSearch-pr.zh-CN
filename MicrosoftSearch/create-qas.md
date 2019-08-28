---
title: 创建问答
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: d432b9d9-3792-47a0-9a13-30a1a83caabc
ROBOTS: NoIndex
description: 为 Microsoft 搜索工作结果创建常见问题解答的方法
ms.openlocfilehash: 78bbd6aa64c9bc2e1890e33beee645b0a9c61ef3
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639781"
---
# <a name="create-qas"></a>创建问答

> [!IMPORTANT]
> 本文适用于必应中的 Microsoft 搜索管理门户。 我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将必应中的 Microsoft 搜索门户删除。 我们建议你使用 Microsoft 365 管理中心快速开始。 [Microsoft 搜索概述](overview-microsoft-search.md)。

问答向用户提供包含可选链接的答案或信息。理想情况下，问答包括用户查找的所有详细信息，这样他们就不需要访问源。可以对问答内容进行格式设置，包括图像、列表和表格。
  
## <a name="create-a-qa"></a>创建问答

有关创建有效标题、说明、关键字的详细信息信息，请参阅[规划内容](plan-your-content.md)。
  
1. 转到 Microsoft 搜索管理门户
    
2. 在导航窗格中，单击“问答”****
    
3. 在页面顶部，单击“添加问答”****。
    
    随即出现“编辑问答”页，包含问答在必应上的预览显示。当添加所需信息时，预览将自动更新。
    
4. 输入**标题**
    
    标题是出现在结果中的标题。可长达 120 个字符，建议使用问题格式。
    
5. 如果需要，输入书签将链接到的页面、网站或位置的 **URL** 
    
    这使得需要额外信息的用户可以轻松访问内容源以阅读更多信息。
    
6. 输入**回答说明**
    
    这应该能回答标题中提及的问题。可以复制现有的 HTML 内容并粘贴在此处。任何不受支持的标记都将被忽略。
    
7. 使用 HTML 标记和内置选项设置文本格式，添加图像、列表、表格等
    
    使用页面顶部的预览来查看标记和格式将如何显示在必应上。有关信息：
    
  - HTML 标记，参见下面支持的 HTML 标记列表
    
  - 内置选项，请单击“Markdown 指南”****（问号图标） 
    
8. 输入要触发此问答的**关键字** 
    
    和书签一样，当用户搜索你包含的任何关键字时，此问答将包含在他们的工作结果中。尝试添加尽可能多的变体，包括问答标题。
    
9. 选择“自动匹配类似关键字”**** 展开关键字集 
    
    这样可以更广泛地匹配搜索词，并帮助确保将此问答包含在相关工作结果中。
    
10. 输入**保留的关键字**
    
    如果一个关键字触发多个问答，Microsoft 搜索将把最热门的一个置顶，并显示其他相关链接。使用一个或多个保留的关键字来确保问答始终显示为置顶结果。保留的关键字不能在问答之间共享。另外，不建议在问答和书签之间共享保留的关键字。如果书签和问答共享关键字或保留的关键字，书签将始终优先，问答不会出现。
    
## <a name="add-qa-settings"></a>添加问答设置

问答设置让你进一步控制问答何时出现以及谁可以看到它。
  
- 日期
    
    设置开始日期和可选的结束日期，以控制问答何时发布或过期。
    
- 国家/地区
    
    如果选择国家或地区，仅这些位置中的用户会看到该问答。
    
- 组
    
    使用组设置使问答结果仅对选定组的成员可用。例如，如果创建的问答仅适用于人力资源部门的员工，可以将该设置映射到适当的人力资源安全组。
    
- 设备 &amp; OS
    
    如果选择设备类型或操作系统，只有在这些设备上搜索或使用这些系统的用户才会看到问答。
    
- 目标变体
    
    使用此设置可以根据用户的设备和位置更改问答内容。
    
## <a name="use-a-browser-extension-to-create-content"></a>使用浏览器扩展来创建内容

从管理门户的“工具”部分，下载并安装 Microsoft Edge 或 Chrome 的内容创建程序浏览器扩展。要使用扩展，请登录并进入希望作为问答添加的网站或页面。查看并更改建议的内容（包括关键字）、添加任何其他内容，并保存问答。
  
如果发现多个问答，请检查每个问答，并确定是要发布、保存到草稿还是全部保存到草稿。
  
## <a name="supported-html-tags"></a>受支持的 HTML 标记

可以使用现有的 HTML 内容或向答案说明添加 HTML 标记。不支持的标记将被忽略。
  
- blockquote
    
- div
    
- em
    
- h1、h2、h3 和 h4
    
- ol、ul 和 li
    
- p
    
- pre
    
- span
    
- strong
    
- table、thead、tbody、tr、th 和 td
    
- u
    
- a
    
- code
    
- br
    
- hr
    
- img

  

