---
title: 设置默认主页
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
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: 了解如何使用 Microsoft 搜索将必应设置为公司的默认主页。
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612487"
---
# <a name="set-default-homepage"></a><span data-ttu-id="7a42c-103">设置默认主页</span><span class="sxs-lookup"><span data-stu-id="7a42c-103">Set default homepage</span></span>

<span data-ttu-id="7a42c-104">配置默认浏览器、默认搜索引擎和默认主页将帮助用户发现 Microsoft 搜索功能、鼓励更多用户使用，并提供更流畅的体验。</span><span class="sxs-lookup"><span data-stu-id="7a42c-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="7a42c-105">若要为组织设置默认主页，请按照下面步骤操作。</span><span class="sxs-lookup"><span data-stu-id="7a42c-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="7a42c-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="7a42c-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="7a42c-107">Internet Explorer 5.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7a42c-107">Internet Explorer 7.0 or later</span></span>

1. <span data-ttu-id="7a42c-108">打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。</span><span class="sxs-lookup"><span data-stu-id="7a42c-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="7a42c-109">导航到**用户配置\偏好设置\控制面板设置\Internet 设置**。</span><span class="sxs-lookup"><span data-stu-id="7a42c-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="7a42c-110">右键单击“Internet 设置”\*\*\*\*，然后选择“Internet Explorer 10”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7a42c-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7a42c-111">需要选择 Internet Explorer 10 选项来应用 Internet Explorer 11 设置，就像应用于 Internet Explorer 11 的设置一样。</span><span class="sxs-lookup"><span data-stu-id="7a42c-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="7a42c-p101">带红色下划线的设置不在目标计算机上配置，而带绿色下划线的设置在目标计算机上配置。若要更改下划线，请使用以下功能键：</span><span class="sxs-lookup"><span data-stu-id="7a42c-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="7a42c-114">F5 - 启用当前选项卡上的所有设置</span><span class="sxs-lookup"><span data-stu-id="7a42c-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="7a42c-115">F6 - 启用当前选择的设置</span><span class="sxs-lookup"><span data-stu-id="7a42c-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="7a42c-116">F7 - 禁用当前选择的设置</span><span class="sxs-lookup"><span data-stu-id="7a42c-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="7a42c-117">F8 - 禁用当前选项卡上的所有设置</span><span class="sxs-lookup"><span data-stu-id="7a42c-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="7a42c-p102">按 F8\*\*\*\* 在配置任何内容之前禁用所有设置。屏幕应如下所示：</span><span class="sxs-lookup"><span data-stu-id="7a42c-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Internet Explorer 10 属性对话框](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="7a42c-121">在主页设置上按 **F6**，然后输入 `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="7a42c-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="7a42c-122">通过将生成的 GPO 链接到适当的域来强制执行此系列设置。</span><span class="sxs-lookup"><span data-stu-id="7a42c-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7a42c-123">设置此策略后，用户仍可以更改主页。</span><span class="sxs-lookup"><span data-stu-id="7a42c-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="7a42c-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7a42c-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="7a42c-125">Windows 10 版本 1511 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7a42c-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="7a42c-126">打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。</span><span class="sxs-lookup"><span data-stu-id="7a42c-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="7a42c-127">导航到**管理模板\Windows 组件\Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="7a42c-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="7a42c-128">双击“配置起始页”\*\*\*\*，将其设置为“启用”\*\*\*\*，并输入 `https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="7a42c-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="7a42c-129">通过将生成的 GPO 链接到适当的域来强制执行此系列设置。</span><span class="sxs-lookup"><span data-stu-id="7a42c-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="7a42c-130">用户无法在设置此策略后更改搜索提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a42c-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="7a42c-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="7a42c-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="7a42c-132">Windows XP SP2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7a42c-132">Windows Vista SP2 or later</span></span>

<span data-ttu-id="7a42c-133">有关为不同版本的 Windows 管理 ADMX 文件和最新 ADMX 文件的 Windows 支持文章，请参阅 [Microsoft 支持](https://support.microsoft.com/zh-CN/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)。</span><span class="sxs-lookup"><span data-stu-id="7a42c-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/zh-CN/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="7a42c-134">还需要最新的 Google 策略文件，可在 [Google Chrome Enterprise 帮助](https://support.google.com/chrome/a/answer/187202)上找到。</span><span class="sxs-lookup"><span data-stu-id="7a42c-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="7a42c-p103">如果在 GPMC 内找不到本部分中介绍的设置，下载相应 ADMX 并将其复制到[中央存储](https://docs.microsoft.com/zh-CN/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。控制器上的中央存储是具有以下命名约定的文件夹：</span><span class="sxs-lookup"><span data-stu-id="7a42c-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/zh-CN/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="7a42c-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="7a42c-137">%systemroot% \sysvol\domain\policies\PolicyDefinitions</span></span>
  
<span data-ttu-id="7a42c-p104">控制器处理的每个域都应有一个单独的文件夹。以下命令可用于从命令提示符复制 ADMX 文件：</span><span class="sxs-lookup"><span data-stu-id="7a42c-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="7a42c-140">打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。</span><span class="sxs-lookup"><span data-stu-id="7a42c-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="7a42c-141">请确保以下文件夹显示在*用户/计算机配置*的**管理模板**部分中：Google Chrome 和 Google Chrome - 默认设置（用户可以覆盖）。</span><span class="sxs-lookup"><span data-stu-id="7a42c-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="7a42c-142">第一个部分的设置是固定的，本地管理员无法进行更改。</span><span class="sxs-lookup"><span data-stu-id="7a42c-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="7a42c-p105">用户可以在其浏览器设置中更改后一部分策略的设置。应决定用户是否可以覆盖默认设置。在以下步骤中，更改文件夹中与组织策略和需求相对应的设置。下面的步骤使用 Google Chrome - 默认设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="7a42c-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="7a42c-147">导航到**&lt;计算机/用户配置&gt;\管理模板\Google Chrome - 默认设置\主页**。</span><span class="sxs-lookup"><span data-stu-id="7a42c-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="7a42c-148">双击“使用新选项卡页作为主页”\*\*\*\*，并将其设置为“启用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7a42c-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="7a42c-149">导航到**&lt;计算机/用户配置&gt;\管理模板\Google Chrome - 默认设置\新选项卡页**。</span><span class="sxs-lookup"><span data-stu-id="7a42c-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="7a42c-150">双击“配置新选项卡页 URL”\*\*\*\*，将其设置为“启用”\*\*\*\*，并输入 `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="7a42c-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="7a42c-151">通过将生成的 GPO 链接到适当的域来强制执行此系列设置。</span><span class="sxs-lookup"><span data-stu-id="7a42c-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="7a42c-152">用户可以在设置此策略后更改主页。</span><span class="sxs-lookup"><span data-stu-id="7a42c-152">Users will be able to change the home page after this policy is set.</span></span>