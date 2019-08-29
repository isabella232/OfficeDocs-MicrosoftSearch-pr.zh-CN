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
ROBOTS: NOINDEX
description: 减少提示 Windows 10 用户登录 Microsoft 搜索和 Office 365 的次数
ms.openlocfilehash: 5dbceb070a469d1a8b3808a07a0972978a909f8a
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639368"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="0787d-103">测试单一登录</span><span class="sxs-lookup"><span data-stu-id="0787d-103">Test single sign-on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0787d-104">本文适用于必应中的 Microsoft 搜索管理门户。</span><span class="sxs-lookup"><span data-stu-id="0787d-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="0787d-105">我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将必应中的 Microsoft 搜索门户删除。</span><span class="sxs-lookup"><span data-stu-id="0787d-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="0787d-106">我们建议你使用 Microsoft 365 管理中心快速开始。</span><span class="sxs-lookup"><span data-stu-id="0787d-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="0787d-107">[Microsoft 搜索概述](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="0787d-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="0787d-p102">单一登录可减少提示用户登录的次数。通过一小群用户测试单一登录将有助于识别任何阻止配置问题。</span><span class="sxs-lookup"><span data-stu-id="0787d-p102">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="0787d-110">对于 Windows 10 上的 Chrome 用户，只有安装了 Windows 10 和 Chrome AAD 登录扩展后，单一登录才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="0787d-110">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="0787d-111">下载 Windows 10 和 Chrome AAD 登录扩展</span><span class="sxs-lookup"><span data-stu-id="0787d-111">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="0787d-112">建议创建组策略来自动安装此扩展。</span><span class="sxs-lookup"><span data-stu-id="0787d-112">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="0787d-113">转到 Microsoft 搜索管理门户</span><span class="sxs-lookup"><span data-stu-id="0787d-113">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="0787d-114">在导航窗格中，单击“工具”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0787d-114">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="0787d-115">在工具列表中，下载“Windows 10 和 Chrome AAD 登录扩展”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0787d-115">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="0787d-116">与 Windows 10 上的 Chrome 用户共享扩展</span><span class="sxs-lookup"><span data-stu-id="0787d-116">Share the extension with Chrome users on Windows 10</span></span>

  

