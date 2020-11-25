---
title: 在本地代理上
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: 本地代理
ms.openlocfilehash: 487c5b179e09fd99fa26ae7a237e89ca38b7be4d
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408939"
---
# <a name="on-prem-agent"></a>本地代理

## <a name="graph-connector-agent"></a>图形连接器代理

本地 Graph 连接器要求您安装 *graph 连接器代理* 软件。 它允许在本地数据和云服务之间进行快速且安全的数据传输。 本文将指导您完成安装和配置软件的步骤。 配置完成后，将可以从 [Microsoft 365 管理中心](https://admin.microsoft.com)创建到本地数据源的连接。

## <a name="installation"></a>安装

使用 [此链接](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) 下载 Graph 连接器代理的最新版本，并使用安装向导安装该软件。 使用下面所述的计算机的推荐配置，软件可以无缝处理最高三个连接。 超过此范围的任何连接可能会降低性能。

建议的配置：

* Windows 10、Windows Server 2012 R2 及更高版本
* 8核，3GHz
* 16 GB RAM，1GB 磁盘空间
* 通过443对数据源和 internet 的网络访问

## <a name="creating-app-for-the-agent"></a>创建代理的应用程序  

在创建连接之前，需要对代理实例进行多个重要的关键参数馈送。 这些参数包括使用 Graph 摄取 Api 所需的身份验证详细信息。  

为代理创建应用程序的步骤。

1. 转到 [Azure 门户](https://portal.azure.com) ，并使用管理员凭据登录租户。
2. 从导航窗格导航到 " **Azure Active Directory**  ->  **应用程序注册**"，然后选择 "**新建注册**"。
3. 提供应用程序的名称并选择 " **注册**"。
4. 记下应用程序 (客户端) ID。
5. 从导航窗格中打开 **API 权限** ，并选择 " **添加权限**"。
6. 依次选择 " **Microsoft Graph** " 和 " **应用程序权限**"。
7. 从权限中搜索 "ExternalItem" 和 "Directory. All" 并选择 " **添加权限**"。
8. 选择 " **授予管理员同意 [TenantName]** " 并通过选择 **"是"** 进行确认。
9. 检查权限是否处于 "已授予" 状态。
     ![权限显示为 "在右侧绿色中授予" 列。](media/onprem-agent/granted-state.png)

## <a name="configuring-graph-connector-agent"></a>配置 Graph 连接器代理

为代理创建应用后，必须使用适当的身份验证详细信息配置代理。

可以按以下形式之一提供身份验证详细信息。

### <a name="configuring-the-client-secret-for-authentication"></a>配置客户端机密以进行身份验证

1. 转到 [Azure 门户](https://portal.azure.com) ，并使用管理员凭据登录租户。
2. 从导航窗格中打开 " **应用注册** "，然后转到相应的应用程序。 在 " **管理**" 下，选择 " **证书和密码**"。
3. 选择 " **新建客户端密码** "，然后选择密码的有效期。 复制生成的机密并将其保存，因为它将不会再次显示。
4. 使用此客户端密码和应用程序 ID 配置代理。 不要在代理的 " **名称** " 字段中使用任何空格。 接受字母数字字符。

## <a name="using-thumbprint-certificate-for-authentication"></a>使用指纹证书进行身份验证

如果已通过 [配置客户端密码进行身份验证](#configuring-the-client-secret-for-authentication) 来配置身份验证详细信息，则可以直接跳转到 [安装程序概述](configure-connector.md)。

1. 打开 " **应用注册** "，然后从导航窗格中选择 " **证书和密码** "。 复制证书指纹。
![在左窗格中选择了 "证书和密码" 时的 thumbrint 证书列表](media/onprem-agent/certificates.png)
2. 使用客户端密码或指纹来注册 Graph 连接器代理。
![注册表单，询问名称、应用程序 id、凭据类型和证书](media/onprem-agent/register.png)
