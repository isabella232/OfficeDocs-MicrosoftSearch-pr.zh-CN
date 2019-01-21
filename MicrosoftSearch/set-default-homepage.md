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
# <a name="set-default-homepage"></a><span data-ttu-id="16dd9-103">设置默认主页</span><span class="sxs-lookup"><span data-stu-id="16dd9-103">Set default homepage</span></span>

<span data-ttu-id="16dd9-104">配置默认浏览器、 默认搜索引擎和默认主页将帮助您发现 Microsoft 搜索功能，鼓励使用更多的并提供更流畅的用户。</span><span class="sxs-lookup"><span data-stu-id="16dd9-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="16dd9-105">若要设置您的组织的默认主页，按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="16dd9-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="16dd9-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="16dd9-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="16dd9-107">Internet Explorer 5.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="16dd9-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="16dd9-108">打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。</span><span class="sxs-lookup"><span data-stu-id="16dd9-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="16dd9-109">导航到**用户 Configuration\Preferences\Control 面板 Settings\Internet 设置**。</span><span class="sxs-lookup"><span data-stu-id="16dd9-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="16dd9-110">右键单击**Internet 设置**，然后选择**Internet Explorer 10**。</span><span class="sxs-lookup"><span data-stu-id="16dd9-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="16dd9-111">您需要选择的 Internet Explorer 10 相同的设置将应用于 Internet Explorer 11 应用 Internet Explorer 11 的设置的选项。</span><span class="sxs-lookup"><span data-stu-id="16dd9-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="16dd9-p101">带有红色下划线设置未配置在目标计算机，而在目标计算机配置设置绿色加下划线。若要更改下划线，请使用下面的功能键：</span><span class="sxs-lookup"><span data-stu-id="16dd9-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="16dd9-114">F5-启用当前选项卡上的所有设置</span><span class="sxs-lookup"><span data-stu-id="16dd9-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="16dd9-115">F6-启用当前选择的设置</span><span class="sxs-lookup"><span data-stu-id="16dd9-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="16dd9-116">F7-禁用当前选择的设置</span><span class="sxs-lookup"><span data-stu-id="16dd9-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="16dd9-117">F8-禁用当前选项卡上的所有设置</span><span class="sxs-lookup"><span data-stu-id="16dd9-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="16dd9-p102">按**F8**配置任何内容之前禁用所有设置。屏幕应如下所示：</span><span class="sxs-lookup"><span data-stu-id="16dd9-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Internet Explorer 10 属性对话框](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="16dd9-121">在主页上设置按**F6** ，并输入`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="16dd9-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="16dd9-122">通过将其链接到适当的域中强制产生的 GPO。</span><span class="sxs-lookup"><span data-stu-id="16dd9-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="16dd9-123">此策略设置后，用户仍可以更改主页。</span><span class="sxs-lookup"><span data-stu-id="16dd9-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="16dd9-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="16dd9-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="16dd9-125">Windows 10，1511 或更高版本</span><span class="sxs-lookup"><span data-stu-id="16dd9-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="16dd9-126">打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。</span><span class="sxs-lookup"><span data-stu-id="16dd9-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="16dd9-127">导航到**管理 \windows Components\Microsoft 边缘**</span><span class="sxs-lookup"><span data-stu-id="16dd9-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="16dd9-128">双击**配置起始页**，将其设置为**启用**，然后输入`https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="16dd9-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="16dd9-129">通过将其链接到适当的域中强制产生的 GPO。</span><span class="sxs-lookup"><span data-stu-id="16dd9-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="16dd9-130">用户将无法更改搜索提供程序后设置此策略。</span><span class="sxs-lookup"><span data-stu-id="16dd9-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="16dd9-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="16dd9-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="16dd9-132">Windows XP SP2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="16dd9-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="16dd9-133">上管理 ADMX 文件和最新的 ADMX 文件的不同版本的 Windows 可找到[Microsoft 支持](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)的 Windows 支持文章。</span><span class="sxs-lookup"><span data-stu-id="16dd9-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="16dd9-134">您还将需要的最新的 Google 策略文件，可以找到该上[Google Chrome 企业帮助](https://support.google.com/chrome/a/answer/187202)。</span><span class="sxs-lookup"><span data-stu-id="16dd9-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="16dd9-p103">如果在 GPMC 找不到本节中所述的设置，请下载相应 ADMX 并将其复制到[中央存储](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。在控制器上的中央存储是具有以下命名约定的文件夹：</span><span class="sxs-lookup"><span data-stu-id="16dd9-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="16dd9-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="16dd9-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="16dd9-p104">每个域控制器处理应获得一个单独的文件夹。下面的命令可用于从命令提示符处复制 ADMX 文件：</span><span class="sxs-lookup"><span data-stu-id="16dd9-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="16dd9-140">打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。</span><span class="sxs-lookup"><span data-stu-id="16dd9-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="16dd9-141">确保在两个*用户/计算机配置*的**管理模板**部分中显示以下文件夹： Google Chrome 和 Google Chrome-默认设置 （用户可以重写）。</span><span class="sxs-lookup"><span data-stu-id="16dd9-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="16dd9-142">已解决的第一节的设置和本地管理员不能更改它们。</span><span class="sxs-lookup"><span data-stu-id="16dd9-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="16dd9-p105">可以由用户在其浏览器设置中更改的后一节的策略的设置。您应确定用户可以覆盖默认设置。在下列步骤中，向您的组织策略和需求更改中的设置相对应的文件夹中。执行以下步骤使用 Google Chrome 中的默认设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="16dd9-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="16dd9-147">导航到**&lt;计算机/用户配置&gt;\Administrative Templates\Google Chrome-默认 Settings\Home 页**。</span><span class="sxs-lookup"><span data-stu-id="16dd9-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="16dd9-148">双击**主页以使用新选项卡页**上，并将其设置为**已启用**。</span><span class="sxs-lookup"><span data-stu-id="16dd9-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="16dd9-149">导航到**&lt;计算机/用户配置&gt;\Administrative Templates\Google Chrome-默认 Settings\New 选项卡页**。</span><span class="sxs-lookup"><span data-stu-id="16dd9-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="16dd9-150">双击**配置新选项卡页的 URL**，将其设置为**启用**，然后输入`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="16dd9-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="16dd9-151">通过将其链接到适当的域中强制产生的 GPO。</span><span class="sxs-lookup"><span data-stu-id="16dd9-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="16dd9-152">用户将能够更改主页上后设置此策略。</span><span class="sxs-lookup"><span data-stu-id="16dd9-152">Users will be able to change the home page after this policy is set.</span></span>