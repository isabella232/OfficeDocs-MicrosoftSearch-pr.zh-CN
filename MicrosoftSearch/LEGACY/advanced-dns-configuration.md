---
title: 高级 DNS 配置
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: 通过使用 CNAME 配置 DNS 服务器，确保为用户提供无缝登录体验
ms.openlocfilehash: 062c43cfbc8d25c263eb2402bd05191e385411b2
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311394"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="a3f8a-103">高级 DNS 配置</span><span class="sxs-lookup"><span data-stu-id="a3f8a-103">Advanced DNS configuration</span></span>

<span data-ttu-id="a3f8a-p101">为了确保必应始终能够识别组织中的用户并使他们成功登录到其工作或学校帐户，请配置内部 DNS 服务器或代理服务器，以从 `www.bing.com` 解析到 `ms.bing.com`。若要执行此操作，为 `www.bing.com`创建一个 DNS 条目，使其成为 `ms.bing.com` 的 CNAME。</span><span class="sxs-lookup"><span data-stu-id="a3f8a-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="a3f8a-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="a3f8a-106">**Name**</span></span>|<span data-ttu-id="a3f8a-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="a3f8a-107">**Type**</span></span>|<span data-ttu-id="a3f8a-108">**值**</span><span class="sxs-lookup"><span data-stu-id="a3f8a-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="a3f8a-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="a3f8a-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="a3f8a-p102">首选使用 CNAME 而不是 IP 地址，因为如果 IP 地址发生变化，CNAME 将继续工作。更改 DNS 之后，结果将继续显示给用户，就像来自 `www.bing.com` 一样。</span><span class="sxs-lookup"><span data-stu-id="a3f8a-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="a3f8a-p103">这不需要在客户端上进行额外的配置，并为用户提供无缝体验。当用户访问 `bing.com` 时，他们会更一致地自动登录，如果无法自动登录，则会提示他们执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a3f8a-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
