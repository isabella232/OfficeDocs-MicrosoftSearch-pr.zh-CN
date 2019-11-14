---
title: Microsoft Search 的文件共享连接器
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置用于 Microsoft 搜索的文件共享连接器。
ms.openlocfilehash: 9791ee3460eb174fd7a478baa6a9beb45f1b1aab
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2019
ms.locfileid: "38310713"
---
# <a name="file-share-connector"></a>文件共享连接器

使用文件共享连接器，组织中的用户可以搜索内部部署文件共享。 这些共享中的搜索结果将与 SharePoint 和 Microsoft OneDrive for Business 中的结果合并。

本文适用于 Microsoft 365 管理员或任何配置、运行和监视文件共享连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。

## <a name="install-a-data-gateway"></a>安装 data gateway
为了访问第三方数据，您必须安装和配置 Microsoft Power BI 网关。 若要了解详细信息，请参阅[安装本地网关](https://docs.microsoft.com/data-integration/gateway/service-gateway-install)。  

## <a name="content-requirements"></a>内容要求
**文件类型**。 只有这些格式的文件可以编制索引和搜索： DOC、.DOCM、.DOCX、DOT、.DOTX、.EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、.OBD、.OBT、ODP、ODS、ODT、、、、、XLS、.XLSX、.XLT、.pptm、XML、XPS 和 ZIP。 仅对这些格式的文本内容编制索引。 忽略所有多媒体内容。
 
**文件大小限制**。 支持的最大文件大小为 100 MB。 将从索引中跳过超过 100 MB 的文件。 后处理的最大大小限制为 4 MB。 当文件的大小达到 4 MB 时处理停止。 因此，文件中存在的某些短语可能不适用于搜索。

## <a name="connect-to-a-data-source"></a>连接到数据源
在 "**连接到数据源**" 页上，选择 "**文件共享**" 并提供名称、连接 ID 和说明。 在下一页中，提供文件共享的路径，然后选择您以前安装的网关。 输入具有对共享中所有文件的读取访问权限的 Windows 用户帐户的凭据。 请浏览其余设置并发布连接。

## <a name="set-the-refresh-schedule"></a>设置刷新计划
建议的默认刷新计划间隔为15分钟，但您可以将其更改为您喜欢的其他间隔。

## <a name="set-up-your-search-results-page"></a>设置您的搜索结果页
若要在 "**全部**" 和 "**文件**" 选项卡中显示不同的文件连接结果，您需要设置 SharePoint 搜索引擎结果页：
- **All**表显示文件连接、SharePoint 文件、OneDrive 文件和 SharePoint 网站的合并结果。 
- "**文件**垂直" 显示来自连接、SharePoint 和 OneDrive 的所有文件结果。
将文件连接中的结果添加到 "**全部**" 和 "**文件**" 行业中已有的结果。

若要设置搜索结果页面，请执行以下步骤：
1. 使用新式搜索页面创建 SharePoint 网站集。

2. 安装[SharePoint Online 命令行管理](https://www.microsoft.com/download/details.aspx?id=35588)程序。

3. 以管理员身份打开 SharePoint Online 命令行管理程序，并导入位于`C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`的**Microsoft. .dll**模块。

> [!NOTE]
> 对于所有用户而言，此路径可能不相同。

若要导入模块，请在 SharePoint Online 命令行管理程序中运行以下命令：
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. 现在运行以下脚本：
```bash
$orgName = Read-Host -prompt 'Please enter your org name'
$userName = Read-Host -prompt 'Enter user name'
$userCreds = Get-Credential -UserName $userName -Message "Type the password"
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCreds

$url = Read-Host -Prompt 'Please enter the site url'
$site = Get-SPOSite -Identity $url
Set-SPOSite $url -DenyAddAndCustomizePages 0

$pwd = Read-Host -AsSecureString 'type the password'
$context = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credential = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $pwd)
$context.Credentials = $credential
$web = $context.Web
$context.Load($web)
$web.AllProperties["AllVerticalContent"] = "Combined"
$web.Update()
$context.ExecuteQuery()
$web.AllProperties["FilesVerticalContent"] = "ConnectorsOnly"
$web.Update()
$context.ExecuteQuery()
Set-SPOSite $url -DenyAddAndCustomizePages 1

Write-Host "Success" -ForegroundColor Cyan
Read-Host -Prompt 'Press enter to exit'
```

5. 在 PowerShell 中输入所需的值，例如 "组织名称"、"用户名"、"密码" 和 "网站 URL"。 **例如**，如果您的管理员凭据为`admin@a830edad9050849823J19081300.onmicrosoft.com`，则您的组织名称为**a830edad9050849823J19081300**，而您的网站 URL `https:// a830edad9050849823J19081300.sharepoint.com`为。

> [!NOTE]
> 仅可在网站集级别（团队/Comms 网站）上执行**AllProperties**设置。

6. 现在，您可以搜索已编制索引的文件，并在 "**全部**" 和 "**文件**" 选项卡中查看结果。

## <a name="search-for-file-share-content-in-the-search-results-page"></a>在搜索结果页中搜索文件共享内容
若要搜索已编制索引的内容，请转到测试租户的 SharePoint 主页。 结果将显示在 "**所有**" 和 "**文件**" 选项卡中。

由于浏览器限制，无法从本地文件共享搜索中选择要查看或打开文件的文件结果。 若要打开这些文件，请复制文件结果的链接，并将其粘贴到系统浏览器的地址栏中。 对于 Windows，请使用 Windows 资源管理器。 然后，您可以在系统上打开该文件。

![使用 "复制链接" 对话框打开 SharePoint 搜索。](media/fileshare-search.png)

## <a name="troubleshooting"></a>故障排除
如果连接出现严重错误，其状态将显示为 "**失败**"。 若要获取有关三种错误类型的详细信息，请转到**错误详细信息**页面，然后选择 "失败的连接"。 请参阅[管理连接器](manage-connector.md)以了解详细信息。
1. **网关不可访问（错误代码：11）**。 连接的网关计算机已关闭。 验证 Microsoft Power BI 进程是否在网关计算机上运行。
2. **身份验证错误（错误代码：12）**。 用于创建连接的凭据已过期或已不再有效。 若要解决此错误，请输入有效的凭据。
3. **内部错误（错误代码：11或12之外的任何内容）**。 连接器基础结构中存在错误。 若要了解如何报告这些错误，请参阅[反馈](connectors-feedback.md)文章。

## <a name="limitations"></a>限制
文件共享连接器在预览版本中具有以下限制：
* 只能使用固定属性（而不是使用自定义属性的文件）对文件编制索引。
* 目前不支持文件共享访问控制列表（Acl）。 仅支持文件 NTFS Acl。
* 不支持外部标识。 它们必须映射到 Azure Active Directory 标识。
