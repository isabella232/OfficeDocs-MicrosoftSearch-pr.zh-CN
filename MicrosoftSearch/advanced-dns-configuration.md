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
ROBOTS: NoIndex
description: 通过使用 CNAME 配置 DNS 服务器，确保为用户提供无缝登录体验
ms.openlocfilehash: 6a291165df33f8acc99d247104e8e88cd35c3a0e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591356"
---
# <a name="advanced-dns-configuration"></a>高级 DNS 配置

> [!IMPORTANT]
> 本文适用于 Microsoft 必应搜索管理门户。 我们正在将该门户迁移至 Microsoft 365 管理中心，并且会在迁移后将其删除。 我们建议你使用 Microsoft 365 管理中心快速开始。 [Microsoft 搜索概述](overview-microsoft-search.md)。
    
为了确保必应始终能够识别组织中的用户并使他们成功登录到其工作或学校帐户，请配置内部 DNS 服务器或代理服务器，以从 `www.bing.com` 解析到 `ms.bing.com`。若要执行此操作，为 `www.bing.com`创建一个 DNS 条目，使其成为 `ms.bing.com` 的 CNAME。
  
****

|**名称**|**Type**|**值**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
首选使用 CNAME 而不是 IP 地址，因为如果 IP 地址发生变化，CNAME 将继续工作。更改 DNS 之后，结果将继续显示给用户，就像来自 `www.bing.com` 一样。 
  
这不需要在客户端上进行额外的配置，并为用户提供无缝体验。当用户访问 `bing.com` 时，他们会更一致地自动登录，如果无法自动登录，则会提示他们执行此操作。
