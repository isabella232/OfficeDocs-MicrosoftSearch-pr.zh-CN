---
title: Microsoft 搜索功能的安全性
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: 保护您的企业数据和用户，同时提供 Microsoft 搜索信息授权用户
ms.openlocfilehash: 65cf1d49e32edbb8061a06f8da7ba644c2145e24
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378543"
---
# <a name="security-for-microsoft-search"></a>Microsoft 搜索功能的安全性

企业级安全 Microsoft 搜索始终保留您的用户和受保护的数据。
  
## <a name="secure-by-default"></a>默认情况下保护

Microsoft Search 始终确保通过 HTTPS 发出请求。此保护确保连接加密的端到端为了增强安全性。
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>身份验证和授权与 Azure Active Directory

Microsoft Search 身份验证与 Azure Active Directory。当 Microsoft 搜索用户转到 Bing 时，Bing 标头将显示为 Microsoft 帐户登录选项以及工作或学校帐户。如果 Bing 无法确定用户是否符合条件的参与者，用户可以转到[浏览 Microsoft 搜索](https://www.bing.com/business/explore)页上，其中他们将被自动重定向到组织的登录页。 
  
用户可以访问 Microsoft 搜索仅通过工作或学校帐户。他们需要使用用于访问 Office 365 服务，例如 SharePoint 或 Outlook 相同的凭据登录。不能使用个人 Microsoft 帐户登录到 Microsoft 搜索。
  
用户无法登录到 Bing 使用 Microsoft 帐户和工作或学校帐户同时。
  
## <a name="single-sign-on"></a>单一登录

如果用户已通过身份验证与中其他服务，如 Outlook 或 SharePoint，其工作或学校帐户他们将自动登录到 Microsoft 搜索在转至时 Bing 的相同浏览器中。此外，当用户注销利用 Microsoft 搜索，它们将自动注销从的相同浏览器中的其他服务。
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>与从浏览器中的受信任的云进行通信

当用户登录与其工作或学校帐户，Bing 将将必要的客户端库下载到浏览器以启用 Microsoft 搜索结果。然后，当他们搜索时，在浏览器代码调用 Office 365 云获取工作结果。若要执行此操作，Microsoft 搜索，请使用层 c (SOC2 类型 1) 符合 Office 365[的行业标准和法规合规性框架](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)（PDF 下载） 的保密协议专用的 API。这意味着工作结果和工作数据从不流通过不符合标准的 Bing 系统。 
  
## <a name="permissions"></a>权限

在源修整工作检索从 Office 365 工作负载，如 SharePoint 和 OneDrive for Business 是安全的结果。用户无法看到如 Word 文档或 PowerPoint 演示文稿他们不能看到并通过 Office 365 访问的资源。他们只能看到他们自己的文件和已与共享其作者显式或隐式的文件 （通过组成员身份，例如） SharePoint 中。
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Bing 的公共部分可防止用户查询

与工作相关搜索可能写，因为 Microsoft 搜索已实现一组信任的公共 web 结果一部分 Bing 如何处理这些的度量值。
  
是否用户查询包含一个或多个工作结果中返回的响应，无论是采取以下措施：
  
- Logging
    
  - 与 Microsoft 搜索通信相关的所有搜索日志的注销标识和存储分开公用，Microsoft 搜索通信。它们保留 18 个月，并限制仅用于调试目的的访问。
    
  - 这些日志中的查询不使用到模型或公共功能，如 autosuggest 或相关搜索公共 web 的培训。
    
  - 通过各种安全机制，包括安全组和工程系统中的其他层管理受限制的访问。
    
- 搜索历史记录
    
  - 当使用的单位电话或学校帐户登录，用户的搜索历史记录不会在其他计算机或设备上可用。
    
- 广告
    
  - 企业级搜索查询从不与共享或给广告商建议。
    
  - 与 Microsoft 搜索相关的搜索广告日志公用通信分开存储。
    
  - 广告从不针对基于其工作标识或组织的用户。
    
## <a name="gdpr"></a>GDPR

[5 月 21 2018年博客文章](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)从 Microsoft 反映了我们承诺 GDPR 合规性和 Microsoft 如何帮助企业和组织自己 GDPR 合规性义务。Microsoft[信任中心常见问题](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)中，您可以找到更多详细信息。针对组织客户的客户数据联机服务内运行的 Microsoft 搜索查询还能满足按照文章 28，具体体现在[信任中心 FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)中的处理器承诺。转到公共 Bing 来自 Microsoft 的搜索查询，对于 Microsoft 数据控制器，并已实现措施以消除标识查询 GDPR 下所述。


