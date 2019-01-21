---
title: 设置默认搜索引擎
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: 了解如何将 Bing 设置为使用 Microsoft 搜索公司的默认搜索引擎。
ms.openlocfilehash: 1102c4c58b1e46e450276430a1e79b34964b4ad4
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378534"
---
# <a name="set-default-search-engine"></a><span data-ttu-id="bb6a9-103">设置默认搜索引擎</span><span class="sxs-lookup"><span data-stu-id="bb6a9-103">Set default search engine</span></span>

<span data-ttu-id="bb6a9-104">配置默认浏览器、 默认搜索引擎和默认主页将帮助您发现 Microsoft 搜索功能，鼓励使用更多的并提供更流畅的用户。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="bb6a9-105">要设置您的组织的默认搜索引擎，请按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-105">To set the default search engine for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="bb6a9-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="bb6a9-106">Internet Explorer</span></span>

### <a name="internet-explorer-11"></a><span data-ttu-id="bb6a9-107">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="bb6a9-107">Internet Explorer 11</span></span>

<span data-ttu-id="bb6a9-108">用户将能够后设置此策略更改搜索提供程序。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-108">Users will be able to change the search provider after this policy is set.</span></span>
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="bb6a9-109">1.配置用于将 GPO 设置在本地计算机</span><span class="sxs-lookup"><span data-stu-id="bb6a9-109">1. Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="bb6a9-110">将以下文本粘贴到注册表 (\*.reg) 文件。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-110">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="bb6a9-111">Windows Registry Editor Version 5.00</span><span class="sxs-lookup"><span data-stu-id="bb6a9-111">Windows Registry Editor Version 5.00</span></span>
  
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
  
<span data-ttu-id="bb6a9-p101">双击创建的文件，并按照导入文件的步骤操作。成功导入应产生以下对话框：</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p101">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![注册表编辑器成功导入消息](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="bb6a9-115">2.打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有策略或创建一个新</span><span class="sxs-lookup"><span data-stu-id="bb6a9-115">2. Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="bb6a9-116">导航到**用户 Configuration\Policies\Preferences\Windows 设置**。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-116">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="bb6a9-p102">**Registry\New**右键单击并选择**注册表向导**。从注册表浏览器窗口中，选择**本地计算机**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p102">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="bb6a9-119">导航到**HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-119">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="bb6a9-120">从此项，请确保选择 DefaultScope。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-120">From this key, make sure to select DefaultScope.</span></span>
    
    ![与选定的 DefaultScope 注册表浏览器](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="bb6a9-p103">检查所有 sub 注册表项包含在 Bing 和项除外向用户配置文件的任何路径下的每个值中的 Microsoft 搜索的 GUID。向下滚动以选择其他项目。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p103">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![具有选中其他值的注册表浏览器](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="bb6a9-125">单击完成以完成此配置。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-125">Click Finish to complete this configuration.</span></span>
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="bb6a9-126">3.设置用户首选项来帮助消除实施 DefaultScope 搜索时，用户可能会收到一条警告</span><span class="sxs-lookup"><span data-stu-id="bb6a9-126">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="bb6a9-127">该警告是设计使然，通知用户尝试修改其设置的程序。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-127">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="bb6a9-128">在相同的 GPO 中，右键单击**Registry\New** ，然后选择**注册表向导**。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-128">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="bb6a9-129">导航到**HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User 首选项**。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-129">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="bb6a9-130">选择**用户首选项**项。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-130">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="bb6a9-131">单击" **完成**"。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-131">Click **Finish**.</span></span>
    
5. <span data-ttu-id="bb6a9-p104">单击新创建的对象。在右侧窗格中双击用户首选项对象上，为**删除并保存**更改的**操作**。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p104">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
    
<span data-ttu-id="bb6a9-134">通过将其链接到适当的域中强制产生的 GPO。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-134">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
  
## <a name="microsoft-edge"></a><span data-ttu-id="bb6a9-135">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bb6a9-135">Microsoft Edge</span></span>

### <a name="windows-10-version-1703-or-later"></a><span data-ttu-id="bb6a9-136">Windows 10，1703 或更高版本</span><span class="sxs-lookup"><span data-stu-id="bb6a9-136">Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="bb6a9-137">用户将能够后设置此策略更改搜索提供程序。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-137">Users will be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="bb6a9-138">有关不同版本的 Windows 的最新 ADMX 文件，请参阅[如何创建和管理的 Windows 中的组策略管理模板中央存储](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-138">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="bb6a9-p105">如果在 GPMC 找不到本节中所述的设置，请下载相应 ADMX 并将其复制到中央存储。有关详细信息，请参阅[参阅 Gpo 使用 ADMX 文件](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。在控制器上的中央存储是具有以下命名约定的文件夹：</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p105">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="bb6a9-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="bb6a9-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="bb6a9-p106">您的控制器处理的每个域应获得一个单独的文件夹。下面的命令可用于从命令提示符处复制 ADMX 文件：</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p106">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="bb6a9-145">打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有策略或创建一个新。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-145">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="bb6a9-146">导航到**&lt;计算机/用户配置&gt;\Administrative Templates\Windows Components\Microsoft 边缘**。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-146">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="bb6a9-147">双击**设置默认搜索引擎**，设置为**启用**，然后输入`https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="bb6a9-147">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="bb6a9-148">通过将其链接到适当的域中强制产生的 GPO。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-148">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
## <a name="google-chrome"></a><span data-ttu-id="bb6a9-149">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="bb6a9-149">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="bb6a9-150">Windows XP SP2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="bb6a9-150">Windows XP SP2 or later</span></span>

<span data-ttu-id="bb6a9-151">用户将无法更改搜索提供程序后设置此策略。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-151">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="bb6a9-p107">部件版式附带其自己的可从[Google Chrome 企业帮助](https://support.google.com/chrome/a/answer/187202)ADMX 文件的形式下载组策略设置集。如果 Windows Vista 操作系统/Server 2008 或更高版本用于管理 GPO 的域，请在 Windows XP SP2 或更高版本的 Chrome 设置负责提供此程序包中的 ADMX 文件。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p107">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="bb6a9-p108">将模板文件复制到域控制器上的 ADMX 文件的中央存储中。有关详细信息，请参阅[参阅 Gpo 使用 ADMX 文件](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)。在控制器上的中央存储是具有以下命名约定的文件夹：</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p108">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="bb6a9-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="bb6a9-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="bb6a9-p109">您的控制器处理的每个域应获得一个单独的文件夹。下面的命令可用于从命令提示符处复制 ADMX 文件：</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p109">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="bb6a9-160">打开组策略管理控制台 (gpmc.msc) 并切换到编辑现有的任何策略或创建一个新。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-160">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="bb6a9-161">确保在两个用户/计算机配置的管理模板部分中显示以下文件夹： Google Chrome 和 Google Chrome-默认设置。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-161">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="bb6a9-162">已解决的第一节的设置和本地管理员不能在浏览器中更改它们。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-162">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="bb6a9-163">浏览器设置中的用户可以更改的后一节的策略设置。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-163">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="bb6a9-164">导航到**\<计算机/用户\>配置 Templates\Google Chrome\Default 搜索提供程序**</span><span class="sxs-lookup"><span data-stu-id="bb6a9-164">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="bb6a9-165">双击**启用默认搜索提供程序**，并将其设置为**已启用**。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-165">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="bb6a9-166">双击**默认搜索提供程序图标**，将其设置为**启用**，然后输入`https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="bb6a9-166">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="bb6a9-167">双击**默认即时搜索提供程序的 URL**，然后输入`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="bb6a9-167">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="bb6a9-168">双击**默认搜索提供程序名称**，将其设置为启用，然后输入 Bing 中的 Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="bb6a9-168">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="bb6a9-169">双击**默认搜索提供程序搜索 URL**，将其设置为**启用**，然后输入`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="bb6a9-169">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="bb6a9-170">双击**默认搜索提供程序提供建议的 URL**，将其设置为**启用**，然后输入`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span><span class="sxs-lookup"><span data-stu-id="bb6a9-170">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="bb6a9-171">通过将其链接到适当的域中强制产生的 GPO。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-171">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="bb6a9-p110">设置默认搜索引擎将在浏览器地址栏中添加 Microsoft 搜索搜索建议功能。目前，这支持仅书签。在地址栏中键入时，用户将看到上方公共 web 建议的顶部两个书签建议。</span><span class="sxs-lookup"><span data-stu-id="bb6a9-p110">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>