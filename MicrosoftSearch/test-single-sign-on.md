---
title: 测试单一登录
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
description: 减少提示 Windows 10 用户登录 Microsoft 搜索和 Office 365 的次数
ms.openlocfilehash: 55d359edac36020ec8cf2aad6b64ca9737ee1066
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612347"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="c3b7e-103">测试单一登录</span><span class="sxs-lookup"><span data-stu-id="c3b7e-103">Test single sign-on</span></span>

<span data-ttu-id="c3b7e-p101">单一登录可减少提示用户登录的次数。通过一小群用户测试单一登录将有助于识别任何阻止配置问题。</span><span class="sxs-lookup"><span data-stu-id="c3b7e-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="c3b7e-106">对于 Windows 10 上的 Chrome 用户，只有安装了 Windows 10 和 Chrome AAD 登录扩展后，单一登录才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="c3b7e-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="c3b7e-107">下载 Windows 10 和 Chrome AAD 登录扩展</span><span class="sxs-lookup"><span data-stu-id="c3b7e-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="c3b7e-108">建议创建组策略来自动安装此扩展。</span><span class="sxs-lookup"><span data-stu-id="c3b7e-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="c3b7e-109">转到 Microsoft 搜索管理门户</span><span class="sxs-lookup"><span data-stu-id="c3b7e-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="c3b7e-110">在导航窗格中，单击“工具”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c3b7e-110">In the navigation pane, click **ADSI Edit**.</span></span>
    
3. <span data-ttu-id="c3b7e-111">在工具列表中，下载“Windows 10 和 Chrome AAD 登录扩展”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c3b7e-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="c3b7e-112">与 Windows 10 上的 Chrome 用户共享扩展</span><span class="sxs-lookup"><span data-stu-id="c3b7e-112">Share the extension with Chrome users on Windows 10</span></span>

  

