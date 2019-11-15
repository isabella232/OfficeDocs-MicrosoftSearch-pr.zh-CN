---
title: 设置默认浏览器
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: 对于 Microsoft 搜索用户，将默认浏览器设置为 Microsoft Edge 或 Internet Explorer。
ms.openlocfilehash: b99127411d070b37fe34a4f8468449f2354cb6be
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626933"
---
# <a name="make-microsoft-edge-the-default-browser"></a>将 Microsoft Edge 设为默认浏览器
  
为了向用户提供最佳的 Microsoft 搜索体验，可将 Microsoft Edge 设为默认浏览器。 这仅对组织内部用户将 Microsoft Edge 设为默认浏览器，单独的用户仍可选择其他浏览器。
  
  
## <a name="windows-8-and-later"></a>Windows 8 及更高版本

这些说明介绍了如何针对运行 Windows 8 或更高版本的计算机将 Microsoft Edge 或 Internet Explorer 设为默认浏览器。 用户将能够在设置此策略后更改浏览器。
  
### <a name="step-1-create-the-default-associations-file"></a>第 1 步：添加默认关联文件
在域控制器的 SYSVOL 文件夹中创建默认关联文件。

1. 打开 PowerShell 管理控制台。
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a>第 2 步： 添加或编辑默认关联文件

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. 编辑以下条目（.htm、.html、http、https），如果不需要，则删除其他条目。
  - **Microsoft Edge**
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a>第 3 步： 编辑组策略

1. 打开**组策略管理控制台** (gpmc.msc)，并切换到编辑任何现有策略或新建一个策略。
1. 导航到**计算机配置\管理模板\Windows 组件\文件资源管理器**。
1. 双击“**设置默认关联配置文件**”，将其设置为“**已启用**”，并输入访问 AppAssoc.xml 的路径（例如 %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml）。通过将生成的 GPO 链接到适当的域来强制执行它。

  
## <a name="windows-7"></a>Windows 7

1. 配置将用于设置 GPO 的本地计算机。
    
1. 打开“控制面板\程序\默认程序\设置默认程序”**** 并将 Internet Explorer 设置为默认程序。 
    
2. 打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。
    
1. 导航到**\<计算机/用户\>配置\策略\偏好设置\Windows 设置**。
    
2. 右键单击“注册表\新建”**** 然后选择“注册表向导”****。
    
3. 从注册表浏览器窗口中，选择“本地计算机”****，然后单击“下一步”****。
    
4. 导航到 **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** 并选择 ProgId 值。请确保值如下所示： 
    
    ![在编辑字符串中选择 ProgID 值](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. 导航到 **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** 并选择 ProgId 值。请确保值如下所示： 
    
    ![在编辑字符串中选择 HTTPS 的 ProgId](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. 通过将生成的 GPO 链接到适当的域来强制执行此系列设置。
    
