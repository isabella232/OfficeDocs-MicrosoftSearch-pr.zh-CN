---
title: 高级的 DNS 配置
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
description: 通过配置使用 CNAME DNS 服务器，确保您的用户进行无缝登录体验
ms.openlocfilehash: f08fc4c29c4c4356a1616faab67fdebdd6c85839
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378533"
---
# <a name="advanced-dns-configuration"></a>高级的 DNS 配置

若要确保 Bing 可以始终确定贵组织中的用户和成功登录其其工作或学校帐户，配置您的内部 DNS 服务器或代理服务器来解析从`www.bing.com`到`ms.bing.com`。若要执行此操作，创建的 DNS 条目`www.bing.com`是为 CNAME `ms.bing.com`。
  
****

|**名称**|**类型**|**值**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
使用 CNAME，而不是 IP 地址是首选，因为 CNAME 将继续工作如果 IP 地址会更改。做出此 DNS 更改后，结果将继续向用户显示就像它们来自`www.bing.com`。 
  
这不需要其他配置客户端计算机上的，并为用户提供无缝使用体验。当他们转到`bing.com`，它们将自动登录的详细信息一致，和如果他们不能自动登录，他们将提示您这样做。
