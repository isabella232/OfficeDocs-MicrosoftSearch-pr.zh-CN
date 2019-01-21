---
title: 设置默认主页
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: 了解如何为 Microsoft 搜索与贵公司将 Bing 设置为默认主页。
ms.openlocfilehash: 9190e607f5e17a0b898ab131886de12cb300a74c
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378505"
---
# <a name="set-default-homepage"></a>设置默认主页

配置默认浏览器、 默认搜索引擎和默认主页将帮助您发现 Microsoft 搜索功能，鼓励使用更多的并提供更流畅的用户。
  
若要设置您的组织的默认主页，按照以下步骤。
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-50-or-later"></a>Internet Explorer 5.0 或更高版本

1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。
    
2. 导航到**用户 Configuration\Preferences\Control 面板 Settings\Internet 设置**。
    
3. 右键单击**Internet 设置**，然后选择**Internet Explorer 10**。
    
    > [!NOTE]
    > 您需要选择的 Internet Explorer 10 相同的设置将应用于 Internet Explorer 11 应用 Internet Explorer 11 的设置的选项。 
  
4. 带有红色下划线设置未配置在目标计算机，而在目标计算机配置设置绿色加下划线。若要更改下划线，请使用下面的功能键：
    
    F5-启用当前选项卡上的所有设置
    
    F6-启用当前选择的设置
    
    F7-禁用当前选择的设置
    
    F8-禁用当前选项卡上的所有设置
    
5. 按**F8**配置任何内容之前禁用所有设置。屏幕应如下所示： 
    
    ![Internet Explorer 10 属性对话框](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. 在主页上设置按**F6** ，并输入`https://www.bing.com/business?form=BFBSPR`
    
7. 通过将其链接到适当的域中强制产生的 GPO。
    
> [!NOTE]
> 此策略设置后，用户仍可以更改主页。 
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1511-or-later"></a>Windows 10，1511 或更高版本

1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。
    
2. 导航到**管理 \windows Components\Microsoft 边缘**
    
1. 双击**配置起始页**，将其设置为**启用**，然后输入`https://www.bing.com/business`
    
3. 通过将其链接到适当的域中强制产生的 GPO。
    
> [!CAUTION]
> 用户将无法更改搜索提供程序后设置此策略。 
  
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 或更高版本

上管理 ADMX 文件和最新的 ADMX 文件的不同版本的 Windows 可找到[Microsoft 支持](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)的 Windows 支持文章。

您还将需要的最新的 Google 策略文件，可以找到该上[Google Chrome 企业帮助](https://support.google.com/chrome/a/answer/187202)。
  
如果在 GPMC 找不到本节中所述的设置，请下载相应 ADMX 并将其复制到[中央存储](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。在控制器上的中央存储是具有以下命名约定的文件夹：
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
每个域控制器处理应获得一个单独的文件夹。下面的命令可用于从命令提示符处复制 ADMX 文件：
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。
    
2. 确保在两个*用户/计算机配置*的**管理模板**部分中显示以下文件夹： Google Chrome 和 Google Chrome-默认设置 （用户可以重写）。
    
   - 已解决的第一节的设置和本地管理员不能更改它们。
    
   - 可以由用户在其浏览器设置中更改的后一节的策略的设置。您应确定用户可以覆盖默认设置。在下列步骤中，向您的组织策略和需求更改中的设置相对应的文件夹中。执行以下步骤使用 Google Chrome 中的默认设置为默认值。
    
3. 导航到**&lt;计算机/用户配置&gt;\Administrative Templates\Google Chrome-默认 Settings\Home 页**。
    
4. 双击**主页以使用新选项卡页**上，并将其设置为**已启用**。
    
5. 导航到**&lt;计算机/用户配置&gt;\Administrative Templates\Google Chrome-默认 Settings\New 选项卡页**。
    
6. 双击**配置新选项卡页的 URL**，将其设置为**启用**，然后输入`https://www.bing.com/business?form=BFBSPR`
    
7. 通过将其链接到适当的域中强制产生的 GPO。
    
用户将能够更改主页上后设置此策略。