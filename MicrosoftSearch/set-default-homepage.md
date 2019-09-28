---
title: 设置默认主页
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
ROBOTS: NOINDEX
description: 了解如何使用 Microsoft 搜索将必应设置为公司的默认主页。
ms.openlocfilehash: c3302863fab8888b8304b909c2c74ce71b391ade
ms.sourcegitcommit: 3da22a2e09830672ebf199e05a32fa89b75c083b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "37289006"
---
# <a name="make-bingcom-the-default-home-page"></a>将 Bing.com 设置为默认主页

本文介绍如何将 Bing.com 设置为 Microsoft Edge、Google Chrome 和 Internet Explorer 浏览器的默认主页。 
  
 
## <a name="microsoft-edge-on-windows-10-version-1511-or-later"></a>Windows 10 版本 1511 或更高版本上的 Microsoft Edge

此策略一旦设置完成，用户便无法再更改此内容。 

1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。 
1. 导航到**管理模板\Windows 组件\Microsoft Edge**。    
1. 双击“配置起始页”****，将其设置为“启用”****，并输入 `https://www.bing.com/business`
1.  通过将生成的 GPO 链接到适当的域来强制执行此系列设置。

  
## <a name="google-chrome-on-windows-xp-sp2-or-later"></a>Windows XP SP2 或更高版本上的 Google Chrome


有关为不同版本的 Windows 管理 ADMX 文件和最新 ADMX 文件的 Windows 支持文章，请参阅 [Microsoft 支持](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)。

还需要最新的 Google 策略文件，可在 [Google Chrome Enterprise 帮助](https://support.google.com/chrome/a/answer/187202)上找到。
  
如果在 GPMC 内找不到本部分中介绍的设置，下载相应 ADMX 并将其复制到[中央存储](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。控制器上的中央存储是具有以下命名约定的文件夹：
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
控制器处理的每个域都应有一个单独的文件夹。以下命令可用于从命令提示符复制 ADMX 文件：
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。
1. 请确保以下文件夹显示在*用户/计算机配置*的**管理模板**部分中：Google Chrome 和 Google Chrome - 默认设置（用户可以覆盖）。
   - 第一个部分的设置是固定的，本地管理员无法进行更改。
   - 用户可以在其浏览器设置中更改后一部分策略的设置。应决定用户是否可以覆盖默认设置。在以下步骤中，更改文件夹中与组织策略和需求相对应的设置。下面的步骤使用 Google Chrome - 默认设置为默认值。

1. 导航到**&lt;计算机/用户配置&gt;\管理模板\Google Chrome - 默认设置\主页**。 
1. 双击“使用新选项卡页作为主页”****，并将其设置为“启用”****。 
1. 导航到**&lt;计算机/用户配置&gt;\管理模板\Google Chrome - 默认设置\新选项卡页**。 
1. 双击“配置新选项卡页 URL”****，将其设置为“启用”****，并输入 `https://www.bing.com/business?form=BFBSPR` 
1. 通过将生成的 GPO 链接到适当的域来强制执行此系列设置。

## <a name="internet-explorer-50-or-later"></a>Internet Explorer 5.0 或更高版本
设置此策略后，用户仍可以更改主页。 

1. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。
    
2. 导航到**用户配置\偏好设置\控制面板设置\Internet 设置**。
    
3. 右键单击“Internet 设置”****，然后选择“Internet Explorer 10”****。
    
    > [!NOTE]
    > 需要选择 Internet Explorer 10 选项来应用 Internet Explorer 11 设置，就像应用于 Internet Explorer 11 的设置一样。 
  
4. 带红色下划线的设置不在目标计算机上配置，而带绿色下划线的设置在目标计算机上配置。若要更改下划线，请使用以下功能键：
    
    F5 - 启用当前选项卡上的所有设置
    
    F6 - 启用当前选择的设置
    
    F7 - 禁用当前选择的设置
    
    F8 - 禁用当前选项卡上的所有设置
    
5. 按 F8**** 在配置任何内容之前禁用所有设置。屏幕应如下所示： 
    
    ![Internet Explorer 10 属性对话框](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. 在主页设置上按 **F6**，然后输入 `https://www.bing.com/business?form=BFBSPR`
    
7. 通过将生成的 GPO 链接到适当的域来强制执行此系列设置。