---
title: 高级 DNS 配置
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
description: 通过配置使用 CNAME DNS 服务器，确保您的用户进行无缝登录体验
ms.openlocfilehash: fa797b95f346d6d03bd020da146bb330c715e392
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612433"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="d28db-103">高级 DNS 配置</span><span class="sxs-lookup"><span data-stu-id="d28db-103">Advanced DNS configuration</span></span>

<span data-ttu-id="d28db-p101">若要确保 Bing 可以始终确定贵组织中的用户和成功登录其其工作或学校帐户，配置您的内部 DNS 服务器或代理服务器来解析从`www.bing.com`到`ms.bing.com`。若要执行此操作，创建的 DNS 条目`www.bing.com`是为 CNAME `ms.bing.com`。</span><span class="sxs-lookup"><span data-stu-id="d28db-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="d28db-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="d28db-106">**Name**</span></span>|<span data-ttu-id="d28db-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="d28db-107">**Type**</span></span>|<span data-ttu-id="d28db-108">**值**</span><span class="sxs-lookup"><span data-stu-id="d28db-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="d28db-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="d28db-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="d28db-p102">使用 CNAME，而不是 IP 地址是首选，因为 CNAME 将继续工作如果 IP 地址会更改。做出此 DNS 更改后，结果将继续向用户显示就像它们来自`www.bing.com`。</span><span class="sxs-lookup"><span data-stu-id="d28db-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="d28db-p103">这不需要其他配置客户端计算机上的，并为用户提供无缝使用体验。当他们转到`bing.com`，它们将自动登录的详细信息一致，和如果他们不能自动登录，他们将提示您这样做。</span><span class="sxs-lookup"><span data-stu-id="d28db-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
