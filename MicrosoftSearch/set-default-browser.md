---
title: 设置默认浏览器
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
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: 了解如何为您的公司与 Microsoft 搜索配置默认浏览器。
ms.openlocfilehash: 160dbbef9981127b74c51f54f86428667ecd4471
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612471"
---
# <a name="set-default-browser"></a><span data-ttu-id="6c701-103">设置默认浏览器</span><span class="sxs-lookup"><span data-stu-id="6c701-103">Set default browser</span></span>

<span data-ttu-id="6c701-104">配置默认浏览器、 默认搜索引擎和默认主页将帮助您发现 Microsoft 搜索功能，鼓励使用更多的并提供更流畅的用户。</span><span class="sxs-lookup"><span data-stu-id="6c701-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="6c701-105">要设置您的组织的默认浏览器，请按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="6c701-105">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="6c701-106">Windows 8 及以上</span><span class="sxs-lookup"><span data-stu-id="6c701-106">Windows 8 and above</span></span>

<span data-ttu-id="6c701-107">将 Internet Explorer 或 Microsoft 边缘设置为默认浏览器，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="6c701-107">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="6c701-108">创建默认关联的文件</span><span class="sxs-lookup"><span data-stu-id="6c701-108">Create default associations file</span></span>

1. <span data-ttu-id="6c701-109">打开管理 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="6c701-109">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="6c701-110">这些步骤尝试和域控制器的 SYSVOL 文件夹中创建的默认关联文件。</span><span class="sxs-lookup"><span data-stu-id="6c701-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="6c701-111">添加或编辑默认关联文件</span><span class="sxs-lookup"><span data-stu-id="6c701-111">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="6c701-112">编辑以下条目 （.htm、.html、 http、 https），并删除其他条目，如果您不需要它们。</span><span class="sxs-lookup"><span data-stu-id="6c701-112">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="6c701-113">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="6c701-113">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="6c701-114">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="6c701-114">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="6c701-115">打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。</span><span class="sxs-lookup"><span data-stu-id="6c701-115">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="6c701-116">导航到\**计算机 Components\File 配置 \**</span><span class="sxs-lookup"><span data-stu-id="6c701-116">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="6c701-117">双击**设置默认关联配置文件**，将其设置为**已启用**，并输入 AppAssoc.xml 的路径 (例如 %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="6c701-117">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="6c701-118">通过将其链接到适当的域中强制产生的 GPO。</span><span class="sxs-lookup"><span data-stu-id="6c701-118">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="6c701-119">用户将能够更改浏览器后设置此策略。</span><span class="sxs-lookup"><span data-stu-id="6c701-119">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="6c701-120">Windows 7</span><span class="sxs-lookup"><span data-stu-id="6c701-120">Windows 7</span></span>

1. <span data-ttu-id="6c701-121">配置用于将 GPO 设置在本地计算机。</span><span class="sxs-lookup"><span data-stu-id="6c701-121">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="6c701-122">打开**控件 Panel\Programs\Default Programs\Set 默认程序**并将 Internet Explorer 设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="6c701-122">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="6c701-123">打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。</span><span class="sxs-lookup"><span data-stu-id="6c701-123">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="6c701-124">导航到**\<计算机/用户\>Configuration\Policies\Preferences\Windows 设置**。</span><span class="sxs-lookup"><span data-stu-id="6c701-124">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="6c701-125">**Registry\New**右键单击并选择**注册表向导**。</span><span class="sxs-lookup"><span data-stu-id="6c701-125">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="6c701-126">从注册表浏览器窗口中，选择**本地计算机**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6c701-126">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="6c701-p101">导航到**HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**并选择的 ProgId 值。确保值看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c701-p101">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![在编辑字符串中选择 ProgID 值](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="6c701-p102">导航到**HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**并选择的 ProgId 值。确保值如下之一下：</span><span class="sxs-lookup"><span data-stu-id="6c701-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![选择 ProgId 编辑字符串中的 https](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="6c701-133">通过将其链接到适当的域中强制产生的 GPO。</span><span class="sxs-lookup"><span data-stu-id="6c701-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="6c701-134">用户将能够更改浏览器后设置此策略。</span><span class="sxs-lookup"><span data-stu-id="6c701-134">Users will be able to change the browser after this policy is set.</span></span>