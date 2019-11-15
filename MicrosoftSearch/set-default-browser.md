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
# <a name="make-microsoft-edge-the-default-browser"></a><span data-ttu-id="148c6-103">将 Microsoft Edge 设为默认浏览器</span><span class="sxs-lookup"><span data-stu-id="148c6-103">Make Microsoft Edge the default browser</span></span>
  
<span data-ttu-id="148c6-104">为了向用户提供最佳的 Microsoft 搜索体验，可将 Microsoft Edge 设为默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="148c6-104">To give your users the best experience with Microsoft Search, you can make Microsoft Edge the default browser.</span></span> <span data-ttu-id="148c6-105">这仅对组织内部用户将 Microsoft Edge 设为默认浏览器，单独的用户仍可选择其他浏览器。</span><span class="sxs-lookup"><span data-stu-id="148c6-105">This will only set Microsoft Edge as the default browser for users in your org, individual users can still select a different browser.</span></span>
  
  
## <a name="windows-8-and-later"></a><span data-ttu-id="148c6-106">Windows 8 及更高版本</span><span class="sxs-lookup"><span data-stu-id="148c6-106">Windows 8 and later</span></span>

<span data-ttu-id="148c6-107">这些说明介绍了如何针对运行 Windows 8 或更高版本的计算机将 Microsoft Edge 或 Internet Explorer 设为默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="148c6-107">These instructions show you how to make Microsoft Edge or Internet Explorer as the default browser for computers running Windows 8 or later.</span></span> <span data-ttu-id="148c6-108">用户将能够在设置此策略后更改浏览器。</span><span class="sxs-lookup"><span data-stu-id="148c6-108">Users will be able to change the browser after this policy is set.</span></span>
  
### <a name="step-1-create-the-default-associations-file"></a><span data-ttu-id="148c6-109">第 1 步：添加默认关联文件</span><span class="sxs-lookup"><span data-stu-id="148c6-109">STEP 1: Create the default associations file</span></span>
<span data-ttu-id="148c6-110">在域控制器的 SYSVOL 文件夹中创建默认关联文件。</span><span class="sxs-lookup"><span data-stu-id="148c6-110">Create the default associations file in the SYSVOL folder of the domain controller.</span></span>

1. <span data-ttu-id="148c6-111">打开 PowerShell 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="148c6-111">Open an administrative PowerShell console.</span></span>
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a><span data-ttu-id="148c6-112">第 2 步：</span><span class="sxs-lookup"><span data-stu-id="148c6-112">STEP 2.</span></span> <span data-ttu-id="148c6-113">添加或编辑默认关联文件</span><span class="sxs-lookup"><span data-stu-id="148c6-113">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. <span data-ttu-id="148c6-114">编辑以下条目（.htm、.html、http、https），如果不需要，则删除其他条目。</span><span class="sxs-lookup"><span data-stu-id="148c6-114">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
  - <span data-ttu-id="148c6-115">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="148c6-115">**Microsoft Edge**</span></span>
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="148c6-116">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="148c6-116">**Internet Explorer**</span></span>
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a><span data-ttu-id="148c6-117">第 3 步：</span><span class="sxs-lookup"><span data-stu-id="148c6-117">Step 3.</span></span> <span data-ttu-id="148c6-118">编辑组策略</span><span class="sxs-lookup"><span data-stu-id="148c6-118">Edit the Group Policy</span></span>

1. <span data-ttu-id="148c6-119">打开**组策略管理控制台** (gpmc.msc)，并切换到编辑任何现有策略或新建一个策略。</span><span class="sxs-lookup"><span data-stu-id="148c6-119">Open **Group Policy Management Console** (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="148c6-120">导航到**计算机配置\管理模板\Windows 组件\文件资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="148c6-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**.</span></span>
1. <span data-ttu-id="148c6-121">双击“**设置默认关联配置文件**”，将其设置为“**已启用**”，并输入访问 AppAssoc.xml 的路径（例如 %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml）。通过将生成的 GPO 链接到适当的域来强制执行它。</span><span class="sxs-lookup"><span data-stu-id="148c6-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="windows-7"></a><span data-ttu-id="148c6-122">Windows 7</span><span class="sxs-lookup"><span data-stu-id="148c6-122">Windows 7</span></span>

1. <span data-ttu-id="148c6-123">配置将用于设置 GPO 的本地计算机。</span><span class="sxs-lookup"><span data-stu-id="148c6-123">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="148c6-124">打开“控制面板\程序\默认程序\设置默认程序”\*\*\*\* 并将 Internet Explorer 设置为默认程序。</span><span class="sxs-lookup"><span data-stu-id="148c6-124">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="148c6-125">打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。</span><span class="sxs-lookup"><span data-stu-id="148c6-125">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="148c6-126">导航到**\<计算机/用户\>配置\策略\偏好设置\Windows 设置**。</span><span class="sxs-lookup"><span data-stu-id="148c6-126">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="148c6-127">右键单击“注册表\新建”\*\*\*\* 然后选择“注册表向导”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="148c6-127">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="148c6-128">从注册表浏览器窗口中，选择“本地计算机”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="148c6-128">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="148c6-p105">导航到 **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** 并选择 ProgId 值。请确保值如下所示：</span><span class="sxs-lookup"><span data-stu-id="148c6-p105">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![在编辑字符串中选择 ProgID 值](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="148c6-p106">导航到 **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** 并选择 ProgId 值。请确保值如下所示：</span><span class="sxs-lookup"><span data-stu-id="148c6-p106">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![在编辑字符串中选择 HTTPS 的 ProgId](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="148c6-135">通过将生成的 GPO 链接到适当的域来强制执行此系列设置。</span><span class="sxs-lookup"><span data-stu-id="148c6-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
