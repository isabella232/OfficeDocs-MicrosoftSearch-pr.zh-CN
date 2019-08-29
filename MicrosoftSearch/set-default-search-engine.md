---
title: 设置默认搜索引擎
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
ROBOTS: NOINDEX
description: 了解如何使用 Microsoft 搜索将必应设置为公司的默认搜索引擎。
ms.openlocfilehash: cc03e3aa280ea621702ce99c2cc8eb530b310251
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639835"
---
# <a name="make-bing-the-default-search-engine"></a><span data-ttu-id="85820-103">将必应设置为默认搜索引擎</span><span class="sxs-lookup"><span data-stu-id="85820-103">Make Bing the default search engine</span></span>
  
<span data-ttu-id="85820-104">本文介绍如何将必应设置为 Microsoft Edge、Google Chrome 和 Internet Explorer 的默认搜索引擎。</span><span class="sxs-lookup"><span data-stu-id="85820-104">This article explains how to make Bing the default search engine for Microsoft Edge, Google Chrome, and Internet Explorer.</span></span> 
  
## <a name="microsoft-edge-on-windows-10-version-1703-or-later"></a><span data-ttu-id="85820-105">Windows 10 版本 1703 或更高版本上的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="85820-105">Microsoft Edge on Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="85820-106">虽然你将把必应设置为默认搜索引擎，但 Microsoft Edge 允许用户将其设置更改为使用其他搜索引擎。</span><span class="sxs-lookup"><span data-stu-id="85820-106">Although you'll set Bing as the default search engine, Microsoft Edge allows users to change their settings to use a different search engine.</span></span>
  
<span data-ttu-id="85820-107">有关各种 Windows 版本的最新 ADMX 文件，请参阅[如何在 Windows 中为组策略管理模板创建和管理中央存储](https://support.microsoft.com/zh-CN/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)。</span><span class="sxs-lookup"><span data-stu-id="85820-107">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="85820-p101">如果在 GPMC 内找不到本部分中介绍的设置，下载相应 ADMX 并将其复制到中央存储。有关详细信息，请参阅[使用 ADMX 文件编辑基于域的 GPO](https://docs.microsoft.com/zh-CN/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。控制器上的中央存储是具有以下命名约定的文件夹：</span><span class="sxs-lookup"><span data-stu-id="85820-p101">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="85820-111">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="85820-111">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="85820-p102">控制器处理的每个域都应有一个单独的文件夹。以下命令可用于从命令提示符复制 ADMX 文件：</span><span class="sxs-lookup"><span data-stu-id="85820-p102">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="85820-114">打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有策略或新建一个策略。</span><span class="sxs-lookup"><span data-stu-id="85820-114">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="85820-115">导航到**&lt;计算机/用户配置&gt;\管理模板\Windows 组件\Microsoft Edge**。</span><span class="sxs-lookup"><span data-stu-id="85820-115">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="85820-116">双击“设置默认搜索引擎”\*\*\*\*，设置为“启用”\*\*\*\*，并输入 `https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="85820-116">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="85820-117">通过将生成的 GPO 链接到适当的域来强制执行此系列设置。</span><span class="sxs-lookup"><span data-stu-id="85820-117">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>


## <a name="google-chrome-on-windows-xp-sp2-or-later"></a><span data-ttu-id="85820-118">Windows XP SP2 或更高版本上的 Google Chrome</span><span class="sxs-lookup"><span data-stu-id="85820-118">Google Chrome on Windows XP SP2 or later</span></span>

<span data-ttu-id="85820-119">设置此策略后，用户无法更改默认搜索引擎。</span><span class="sxs-lookup"><span data-stu-id="85820-119">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="85820-p103">Chrome 自带一组组策略设置，可以从 [Google Chrome Enterprise 帮助](https://support.google.com/chrome/a/answer/187202)以 ADMX 文件格式下载。如果使用操作系统 Windows Vista/Server 2008 或更高版本来管理域的 GPO，此包中提供的 ADMX 文件将负责 Windows XP SP2 或更高版本上的 Chrome 设置。</span><span class="sxs-lookup"><span data-stu-id="85820-p103">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="85820-p104">将模板文件复制到域控制器上 ADMX 文件的中央存储。有关详细信息，请参阅[使用 ADMX 文件编辑基于域的 GPO](https://docs.microsoft.com/zh-CN/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。控制器上的中央存储是具有以下命名约定的文件夹：</span><span class="sxs-lookup"><span data-stu-id="85820-p104">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="85820-125">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="85820-125">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="85820-p105">控制器处理的每个域都应有一个单独的文件夹。以下命令可用于从命令提示符复制 ADMX 文件：</span><span class="sxs-lookup"><span data-stu-id="85820-p105">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="85820-128">打开组策略管理控制台 (gpmc.msc) 并切换到编辑任何现有策略或新建一个策略。</span><span class="sxs-lookup"><span data-stu-id="85820-128">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="85820-129">请确保以下文件夹显示在用户/计算机配置的“管理模板”部分：Google Chrome 和 Google Chrome - 默认设置。</span><span class="sxs-lookup"><span data-stu-id="85820-129">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="85820-130">第一个部分的设置是固定的，本地管理员无法在浏览器中进行更改。</span><span class="sxs-lookup"><span data-stu-id="85820-130">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="85820-131">用户可以在浏览器设置中更改后一部分策略的设置。</span><span class="sxs-lookup"><span data-stu-id="85820-131">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="85820-132">导航到**\<计算机/用户\>配置\管理模板\Google Chrome\默认搜索提供程序**</span><span class="sxs-lookup"><span data-stu-id="85820-132">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="85820-133">双击“启用默认搜索提供程序”\*\*\*\*，并将其设置为“启用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85820-133">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="85820-134">双击“默认搜索提供程序”图标\*\*\*\*，将其设置为“启用”\*\*\*\*，并输入 `https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="85820-134">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="85820-135">双击“默认搜索提供程序即时 URL”\*\*\*\*，并输入 `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="85820-135">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="85820-136">双击“默认搜索提供程序名称”\*\*\*\*，将其设置为“启用”，然后输入“必应中的 Microsoft 搜索”</span><span class="sxs-lookup"><span data-stu-id="85820-136">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="85820-137">双击“默认搜索提供程序搜索 URL”\*\*\*\*，并将其设置为“启用”\*\*\*\*，然后输入 `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="85820-137">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="85820-138">双击“默认搜索提供程序建议 URL”\*\*\*\*，并将其设置为“启用”\*\*\*\*，然后输入 `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span><span class="sxs-lookup"><span data-stu-id="85820-138">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="85820-139">通过将生成的 GPO 链接到适当的域来强制执行此系列设置。</span><span class="sxs-lookup"><span data-stu-id="85820-139">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="85820-p106">设置默认搜索引擎将在浏览器地址栏中添加 Microsoft 搜索建议功能。目前，它只支持书签。当用户在地址栏键入内容时，他们会在公共 Web 建议上方看到前两个书签建议。</span><span class="sxs-lookup"><span data-stu-id="85820-p106">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>

## <a name="internet-explorer-11-or-later"></a><span data-ttu-id="85820-143">Internet Explorer 11 或更高版本</span><span class="sxs-lookup"><span data-stu-id="85820-143">Internet Explorer 11 or later versions</span></span>

<span data-ttu-id="85820-144">设置此策略后，用户可以更改搜索提供程序。</span><span class="sxs-lookup"><span data-stu-id="85820-144">Users will be able to change the search provider after this policy is set.</span></span>
  
### <a name="step-1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="85820-145">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="85820-145">Step 1</span></span> <span data-ttu-id="85820-146">配置将用于设置 GPO 的本地计算机</span><span class="sxs-lookup"><span data-stu-id="85820-146">Configure the local machine that will be used to set the GPO.</span></span>

<span data-ttu-id="85820-147">将以下文本粘贴到 reg (\*.reg) 文件中。</span><span class="sxs-lookup"><span data-stu-id="85820-147">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="85820-148">Windows 注册表编辑器版本 5.00</span><span class="sxs-lookup"><span data-stu-id="85820-148">Windows Registry Editor Version 5.00</span></span>
  
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
  
<span data-ttu-id="85820-p108">双击创建的文件并按照步骤导入文件。成功导入后应该会出现如下对话框：</span><span class="sxs-lookup"><span data-stu-id="85820-p108">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![注册表编辑器成功导入消息](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
### <a name="step-2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="85820-152">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="85820-152">Step 2</span></span> <span data-ttu-id="85820-153">打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有策略或新建一个策略</span><span class="sxs-lookup"><span data-stu-id="85820-153">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>

1. <span data-ttu-id="85820-154">导航到**用户配置\策略\首选项\Windows 设置**。</span><span class="sxs-lookup"><span data-stu-id="85820-154">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="85820-p110">右键单击“注册表\新建”\*\*\*\*，然后选择“注册表向导”\*\*\*\*。从注册表浏览器窗口中选择“本地计算机”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85820-p110">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="85820-157">导航到 **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**。</span><span class="sxs-lookup"><span data-stu-id="85820-157">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="85820-158">从此项中确保选择 DefaultScope。</span><span class="sxs-lookup"><span data-stu-id="85820-158">From this key, make sure to select DefaultScope.</span></span>
    
    ![选中 DefaultScope 的注册表浏览器](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="85820-p111">检查必应中包含 Microsoft 搜索 GUID 的所有子项，以及该项下的所有值（任何用户配置文件路径除外）。向下滚动以选择其他项。</span><span class="sxs-lookup"><span data-stu-id="85820-p111">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![选中其他值的注册表浏览器](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="85820-163">单击“完成”以完成此配置。</span><span class="sxs-lookup"><span data-stu-id="85820-163">Click Finish to complete this configuration.</span></span>
    
### <a name="step-3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="85820-164">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="85820-164">Step 3</span></span> <span data-ttu-id="85820-165">设置“用户首选项”，避免用户在强制实施 DefaultScope 时收到警告</span><span class="sxs-lookup"><span data-stu-id="85820-165">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="85820-166">此警告是设计使然，提醒用户有程序尝试修改其设置。</span><span class="sxs-lookup"><span data-stu-id="85820-166">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="85820-167">在相同 GPO 中，右键单击“注册表\新建”\*\*\*\* 然后选择“注册表向导”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85820-167">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="85820-168">导航到 **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\用户首选项**。</span><span class="sxs-lookup"><span data-stu-id="85820-168">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="85820-169">选择“用户首选项”\*\*\*\* 键。</span><span class="sxs-lookup"><span data-stu-id="85820-169">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="85820-170">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85820-170">Click **Finish**.</span></span>
    
5. <span data-ttu-id="85820-p113">单击新创建的对象。在右侧窗格中双击“用户首选项”对象，将“操作”\*\*\*\* 更改为“删除并保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85820-p113">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
1. <span data-ttu-id="85820-173">通过将生成的 GPO 链接到适当的域来强制执行此系列设置。</span><span class="sxs-lookup"><span data-stu-id="85820-173">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>