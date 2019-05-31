---
title: 设置默认搜索引擎
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
ROBOTS: NOINDEX
description: 了解如何使用 Microsoft 搜索将必应设置为公司的默认搜索引擎。
ms.openlocfilehash: 77a8ea884f4df26fc8f7661fb9a9b8791b2f0f18
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591113"
---
# <a name="set-default-search-engine"></a>设置默认搜索引擎

> [!IMPORTANT]
> 本文适用于 Microsoft 必应搜索管理门户。 我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将其删除。 我们建议你使用 Microsoft 365 管理中心快速开始。 [Microsoft 搜索概述](overview-microsoft-search.md)。
    
配置默认浏览器、默认搜索引擎和默认主页将帮助用户发现 Microsoft 搜索功能、鼓励更多用户使用，并提供更流畅的体验。
  
若要为组织设置默认搜索引擎，请按照下面步骤操作。
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-11"></a>Internet Explorer 11

用户可以在设置此策略后更改搜索提供程序。
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>1. 配置将用于设置 GPO 的本地计算机

将以下文本粘贴到 reg (\*.reg) 文件中。
  
Windows 注册表编辑器版本 5.00
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"SuggestionsURL_JSON"="https://business.ing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA"
"ShowSearchSuggestions"=dword:00000001
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
双击创建的文件并按照步骤导入文件。成功导入后应该会出现如下对话框：
  
![注册表编辑器成功导入消息](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>2. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有策略或新建一个策略

1. 导航到**用户配置\策略\首选项\Windows 设置**。
    
2. 右键单击“注册表\新建”****，然后选择“注册表向导”****。从注册表浏览器窗口中选择“本地计算机”****，然后单击“下一步”****。
    
3. 导航到 **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**。
    
4. 从此项中确保选择 DefaultScope。
    
    ![选中 DefaultScope 的注册表浏览器](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. 检查必应中包含 Microsoft 搜索 GUID 的所有子项，以及该项下的所有值（任何用户配置文件路径除外）。向下滚动以选择其他项。
    
    ![选中其他值的注册表浏览器](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. 单击“完成”以完成此配置。
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>3. 设置用户首选项，以帮助消除用户在执行 DefaultScope 搜索时可能收到的警告

此警告是设计使然，提醒用户有程序尝试修改其设置。
  
1. 在相同 GPO 中，右键单击“注册表\新建”**** 然后选择“注册表向导”****。
    
2. 导航到 **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\用户首选项**。
    
3. 选择“用户首选项”**** 键。
    
4. 单击“完成”****。
    
5. 单击新创建的对象。在右侧窗格中双击“用户首选项”对象，将“操作”**** 更改为“删除并保存”****。
    
通过将生成的 GPO 链接到适当的域来强制执行此系列设置。
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1703-or-later"></a>Windows 10 版本 1703 或更高版本

用户可以在设置此策略后更改搜索提供程序。
  
有关各种 Windows 版本的最新 ADMX 文件，请参阅[如何在 Windows 中为组策略管理模板创建和管理中央存储](https://support.microsoft.com/zh-CN/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)。
  
如果在 GPMC 内找不到本部分中介绍的设置，下载相应 ADMX 并将其复制到中央存储。有关详细信息，请参阅[使用 ADMX 文件编辑基于域的 GPO](https://docs.microsoft.com/zh-CN/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。控制器上的中央存储是具有以下命名约定的文件夹：
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
控制器处理的每个域都应有一个单独的文件夹。以下命令可用于从命令提示符复制 ADMX 文件：
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有策略或新建一个策略。
    
2. 导航到**&lt;计算机/用户配置&gt;\管理模板\Windows 组件\Microsoft Edge**。
    
1. 双击“设置默认搜索引擎”****，设置为“启用”****，并输入 `https://www.bing.com/sa/osd/bfb.xml`
    
3. 通过将生成的 GPO 链接到适当的域来强制执行此系列设置。
    
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 或更高版本

用户无法在设置此策略后更改搜索提供程序。
  
Chrome 自带一组组策略设置，可以从 [Google Chrome Enterprise 帮助](https://support.google.com/chrome/a/answer/187202)以 ADMX 文件格式下载。如果使用操作系统 Windows Vista/Server 2008 或更高版本来管理域的 GPO，此包中提供的 ADMX 文件将负责 Windows XP SP2 或更高版本上的 Chrome 设置。
  
将模板文件复制到域控制器上 ADMX 文件的中央存储。有关详细信息，请参阅[使用 ADMX 文件编辑基于域的 GPO](https://docs.microsoft.com/zh-CN/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。控制器上的中央存储是具有以下命名约定的文件夹：
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
控制器处理的每个域都应有一个单独的文件夹。以下命令可用于从命令提示符复制 ADMX 文件：
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。
    
2. 请确保以下文件夹显示在用户/计算机配置的“管理模板”部分：Google Chrome 和 Google Chrome - 默认设置。
    
  - 第一个部分的设置是固定的，本地管理员无法在浏览器中进行更改。
    
  - 用户可以在浏览器设置中更改后一部分策略的设置。
    
3. 导航到**\<计算机/用户\>配置\管理模板\Google Chrome\默认搜索提供程序**
    
4. 双击“启用默认搜索提供程序”****，并将其设置为“启用”****。
    
5. 双击“默认搜索提供程序”图标****，将其设置为“启用”****，并输入 `https://www.bing.com/sa/simg/bb.ico`
    
6. 双击“默认搜索提供程序即时 URL”****，并输入 `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
7. 双击“默认搜索提供程序名称”****，将其设置为“启用”，然后输入“必应中的 Microsoft 搜索”
    
8. 双击“默认搜索提供程序搜索 URL”****，并将其设置为“启用”****，然后输入 `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
9. 双击“默认搜索提供程序建议 URL”****，并将其设置为“启用”****，然后输入 `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`
    
10. 通过将生成的 GPO 链接到适当的域来强制执行此系列设置。
    
设置默认搜索引擎将在浏览器地址栏中添加 Microsoft 搜索建议功能。目前，它只支持书签。当用户在地址栏键入内容时，他们会在公共 Web 建议上方看到前两个书签建议。