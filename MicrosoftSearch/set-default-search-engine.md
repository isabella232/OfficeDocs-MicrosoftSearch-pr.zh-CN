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
description: 了解如何将 Bing 设置为使用 Microsoft 搜索公司的默认搜索引擎。
ms.openlocfilehash: a0798da94f4433bb754c71b9e0d00e09ba5a543b
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612527"
---
# <a name="set-default-search-engine"></a>设置默认搜索引擎

配置默认浏览器、 默认搜索引擎和默认主页将帮助您发现 Microsoft 搜索功能，鼓励使用更多的并提供更流畅的用户。
  
要设置您的组织的默认搜索引擎，请按照以下步骤。
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-11"></a>Internet Explorer 11

用户将能够后设置此策略更改搜索提供程序。
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>1.配置用于将 GPO 设置在本地计算机

将以下文本粘贴到注册表 (\*.reg) 文件。
  
Windows Registry Editor Version 5.00
  
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
  
双击创建的文件，并按照导入文件的步骤操作。成功导入应产生以下对话框：
  
![注册表编辑器成功导入消息](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>2.打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有策略或创建一个新

1. 导航到**用户 Configuration\Policies\Preferences\Windows 设置**。
    
2. **Registry\New**右键单击并选择**注册表向导**。从注册表浏览器窗口中，选择**本地计算机**，然后单击**下一步**。
    
3. 导航到**HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**。
    
4. 从此项，请确保选择 DefaultScope。
    
    ![与选定的 DefaultScope 注册表浏览器](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. 检查所有 sub 注册表项包含在 Bing 和项除外向用户配置文件的任何路径下的每个值中的 Microsoft 搜索的 GUID。向下滚动以选择其他项目。
    
    ![具有选中其他值的注册表浏览器](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. 单击完成以完成此配置。
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>3.设置用户首选项来帮助消除实施 DefaultScope 搜索时，用户可能会收到一条警告

该警告是设计使然，通知用户尝试修改其设置的程序。
  
1. 在相同的 GPO 中，右键单击**Registry\New** ，然后选择**注册表向导**。
    
2. 导航到**HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User 首选项**。
    
3. 选择**用户首选项**项。
    
4. 单击" **完成**"。
    
5. 单击新创建的对象。在右侧窗格中双击用户首选项对象上，为**删除并保存**更改的**操作**。
    
通过将其链接到适当的域中强制产生的 GPO。
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1703-or-later"></a>Windows 10，1703 或更高版本

用户将能够后设置此策略更改搜索提供程序。
  
有关不同版本的 Windows 的最新 ADMX 文件，请参阅[如何创建和管理的 Windows 中的组策略管理模板中央存储](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)。
  
如果在 GPMC 找不到本节中所述的设置，请下载相应 ADMX 并将其复制到中央存储。有关详细信息，请参阅[参阅 Gpo 使用 ADMX 文件](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。在控制器上的中央存储是具有以下命名约定的文件夹：
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
您的控制器处理的每个域应获得一个单独的文件夹。下面的命令可用于从命令提示符处复制 ADMX 文件：
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有策略或创建一个新。
    
2. 导航到**&lt;计算机/用户配置&gt;\Administrative Templates\Windows Components\Microsoft 边缘**。
    
1. 双击**设置默认搜索引擎**，设置为**启用**，然后输入`https://www.bing.com/sa/osd/bfb.xml`
    
3. 通过将其链接到适当的域中强制产生的 GPO。
    
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 或更高版本

用户将无法更改搜索提供程序后设置此策略。
  
部件版式附带其自己的可从[Google Chrome 企业帮助](https://support.google.com/chrome/a/answer/187202)ADMX 文件的形式下载组策略设置集。如果 Windows Vista 操作系统/Server 2008 或更高版本用于管理 GPO 的域，请在 Windows XP SP2 或更高版本的 Chrome 设置负责提供此程序包中的 ADMX 文件。
  
将模板文件复制到域控制器上的 ADMX 文件的中央存储中。有关详细信息，请参阅[参阅 Gpo 使用 ADMX 文件](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。在控制器上的中央存储是具有以下命名约定的文件夹：
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
您的控制器处理的每个域应获得一个单独的文件夹。下面的命令可用于从命令提示符处复制 ADMX 文件：
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。
    
2. 确保在两个用户/计算机配置的管理模板部分中显示以下文件夹： Google Chrome 和 Google Chrome-默认设置。
    
  - 已解决的第一节的设置和本地管理员不能在浏览器中更改它们。
    
  - 浏览器设置中的用户可以更改的后一节的策略设置。
    
3. 导航到**\<计算机/用户\>配置 Templates\Google Chrome\Default 搜索提供程序**
    
4. 双击**启用默认搜索提供程序**，并将其设置为**已启用**。
    
5. 双击**默认搜索提供程序图标**，将其设置为**启用**，然后输入`https://www.bing.com/sa/simg/bb.ico`
    
6. 双击**默认即时搜索提供程序的 URL**，然后输入`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
7. 双击**默认搜索提供程序名称**，将其设置为启用，然后输入 Bing 中的 Microsoft 搜索
    
8. 双击**默认搜索提供程序搜索 URL**，将其设置为**启用**，然后输入`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
9. 双击**默认搜索提供程序提供建议的 URL**，将其设置为**启用**，然后输入`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`
    
10. 通过将其链接到适当的域中强制产生的 GPO。
    
设置默认搜索引擎将在浏览器地址栏中添加 Microsoft 搜索搜索建议功能。目前，这支持仅书签。在地址栏中键入时，用户将看到上方公共 web 建议的顶部两个书签建议。