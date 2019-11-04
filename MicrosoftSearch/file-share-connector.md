---
title: Microsoft Search 的文件共享连接器
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.date: 10/08/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置用于 Microsoft 搜索的文件共享连接器。
ms.openlocfilehash: d5fbc1af2868ce7baa70017f617a9731340fb19a
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949597"
---
# <a name="file-share-connector"></a><span data-ttu-id="5b570-103">文件共享连接器</span><span class="sxs-lookup"><span data-stu-id="5b570-103">File share connector</span></span>

<span data-ttu-id="5b570-104">使用文件共享连接器，组织中的用户可以搜索内部部署文件共享。</span><span class="sxs-lookup"><span data-stu-id="5b570-104">With the File share connector, users in your organization can search on-premises file shares.</span></span> <span data-ttu-id="5b570-105">这些共享中的搜索结果将与 SharePoint 和 Microsoft OneDrive for Business 中的结果合并。</span><span class="sxs-lookup"><span data-stu-id="5b570-105">The search results from these shares merge with the results from SharePoint and Microsoft OneDrive for Business.</span></span>

<span data-ttu-id="5b570-106">本文适用于 Microsoft 365 管理员或任何配置、运行和监视文件共享连接器的人。</span><span class="sxs-lookup"><span data-stu-id="5b570-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a File share connector.</span></span> <span data-ttu-id="5b570-107">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="5b570-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-a-data-gateway"></a><span data-ttu-id="5b570-108">安装 data gateway</span><span class="sxs-lookup"><span data-stu-id="5b570-108">Install a data gateway</span></span>
<span data-ttu-id="5b570-109">为了访问第三方数据，您必须安装和配置 Microsoft Power BI 网关。</span><span class="sxs-lookup"><span data-stu-id="5b570-109">In order to access your third-party data, you must install and configure a Microsoft Power BI gateway.</span></span> <span data-ttu-id="5b570-110">若要了解详细信息，请参阅[Install 和本地网关](https://docs.microsoft.com/data-integration/gateway/service-gateway-install)。</span><span class="sxs-lookup"><span data-stu-id="5b570-110">See [Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) to learn more.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="5b570-111">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="5b570-111">Connect to a data source</span></span>
<span data-ttu-id="5b570-112">在 "**连接到数据源**" 页上，创建一个文件夹并提供文件共享的路径。</span><span class="sxs-lookup"><span data-stu-id="5b570-112">On the **Connect to data source** page, create a folder and provide a path to the file share.</span></span> <span data-ttu-id="5b570-113">然后选择以前安装的网关。</span><span class="sxs-lookup"><span data-stu-id="5b570-113">Then select your previously installed gateway.</span></span> <span data-ttu-id="5b570-114">输入具有对共享中所有文件的**读取访问权限**的 Windows 用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="5b570-114">Enter the credentials for a Windows user account with **read access** to all the files in the share.</span></span> <span data-ttu-id="5b570-115">然后，您可以验证共享中存在的文件，并查看所有获取的元数据。</span><span class="sxs-lookup"><span data-stu-id="5b570-115">You can then verify the files present in the share and see all the fetched metadata.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="5b570-116">管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="5b570-116">Manage search permissions</span></span>
<span data-ttu-id="5b570-117">文件共享连接器仅支持**所有人都**能看到的搜索权限。</span><span class="sxs-lookup"><span data-stu-id="5b570-117">The File share connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="5b570-118">索引数据显示在搜索结果中，并对组织中的所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="5b570-118">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="5b570-119">设置刷新计划</span><span class="sxs-lookup"><span data-stu-id="5b570-119">Set the refresh schedule</span></span>
<span data-ttu-id="5b570-120">建议的默认刷新计划间隔为15分钟，但您可以将其更改为您喜欢的其他间隔。</span><span class="sxs-lookup"><span data-stu-id="5b570-120">The recommended default refresh schedule interval is 15 minutes, but you can change it to another interval that you prefer.</span></span>

## <a name="set-up-your-search-results-page"></a><span data-ttu-id="5b570-121">设置您的搜索结果页</span><span class="sxs-lookup"><span data-stu-id="5b570-121">Set up your search results page</span></span>
<span data-ttu-id="5b570-122">若要在 "**全部**" 和 "**文件**" 选项卡中显示不同的文件连接结果，您需要设置 SharePoint 搜索引擎结果页：</span><span class="sxs-lookup"><span data-stu-id="5b570-122">To display different file connection results in the **All** and **Files** tabs, you need to set up a SharePoint search engine results page:</span></span>
- <span data-ttu-id="5b570-123">**All**表显示文件连接、SharePoint 文件、OneDrive 文件和 SharePoint 网站的合并结果。</span><span class="sxs-lookup"><span data-stu-id="5b570-123">The **All** table shows combined results from your file connections, SharePoint files, OneDrive files, and SharePoint sites.</span></span> 
- <span data-ttu-id="5b570-124">"**文件**垂直" 显示来自连接、SharePoint 和 OneDrive 的所有文件结果。</span><span class="sxs-lookup"><span data-stu-id="5b570-124">The **Files** vertical shows all file results from your connections, SharePoint, and OneDrive.</span></span>
<span data-ttu-id="5b570-125">将文件连接中的结果添加到 "**全部**" 和 "**文件**" 行业中已有的结果。</span><span class="sxs-lookup"><span data-stu-id="5b570-125">Results from file connections are added to already existing results in both the **All** and **Files** verticals.</span></span>

<span data-ttu-id="5b570-126">若要设置搜索结果页面，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5b570-126">To set up your search results page, take these steps:</span></span>
1. <span data-ttu-id="5b570-127">使用新式搜索页面创建 SharePoint 网站集。</span><span class="sxs-lookup"><span data-stu-id="5b570-127">Create a SharePoint site collection with a modern search page.</span></span>

2. <span data-ttu-id="5b570-128">安装[SharePoint Online 命令行管理](https://www.microsoft.com/download/details.aspx?id=35588)程序。</span><span class="sxs-lookup"><span data-stu-id="5b570-128">Install a [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

3. <span data-ttu-id="5b570-129">以管理员身份打开 SharePoint Online 命令行管理程序，并导入位于`C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`的**Microsoft. .dll**模块。</span><span class="sxs-lookup"><span data-stu-id="5b570-129">Open SharePoint Online Management Shell as an administrator and import the **Microsoft.SharePoint.Client.dll** module present at `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.</span></span>

> [!NOTE]
> <span data-ttu-id="5b570-130">对于所有用户而言，此路径可能不相同。</span><span class="sxs-lookup"><span data-stu-id="5b570-130">This path might not be the same for all users.</span></span>

<span data-ttu-id="5b570-131">若要导入模块，请在 SharePoint Online 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5b570-131">To import the module, run this command in SharePoint Online Management Shell:</span></span>
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. <span data-ttu-id="5b570-132">现在运行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="5b570-132">Now run this script:</span></span>
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

5. <span data-ttu-id="5b570-133">在 PowerShell 中输入所需的值，例如 "组织名称"、"用户名"、"密码" 和 "网站 URL"。</span><span class="sxs-lookup"><span data-stu-id="5b570-133">Enter the required values in PowerShell, such as organization name, username, password, and site URL.</span></span> <span data-ttu-id="5b570-134">**例如**，如果您的管理员凭据为`admin@a830edad9050849823J19081300.onmicrosoft.com`，则您的组织名称为**a830edad9050849823J19081300**，而您的网站 URL `https:// a830edad9050849823J19081300.sharepoint.com`为。</span><span class="sxs-lookup"><span data-stu-id="5b570-134">As an **example**, if your admin credentials are `admin@a830edad9050849823J19081300.onmicrosoft.com`, then your organization name is **a830edad9050849823J19081300**, and your site URL is `https:// a830edad9050849823J19081300.sharepoint.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="5b570-135">仅可在网站集级别（团队/Comms 网站）上执行**AllProperties**设置。</span><span class="sxs-lookup"><span data-stu-id="5b570-135">The **AllProperties** setting can only be done at a site collection level (Teams/Comms site).</span></span>

6. <span data-ttu-id="5b570-136">现在，您可以搜索已编制索引的文件，并在 "**全部**" 和 "**文件**" 选项卡中查看结果。</span><span class="sxs-lookup"><span data-stu-id="5b570-136">Now you can search for indexed files and see results in both the **All** and **Files** tabs.</span></span>

## <a name="search-for-file-share-content-in-the-search-results-page"></a><span data-ttu-id="5b570-137">在搜索结果页中搜索文件共享内容</span><span class="sxs-lookup"><span data-stu-id="5b570-137">Search for file share content in the search results page</span></span>
<span data-ttu-id="5b570-138">若要搜索已编制索引的内容，请转到测试租户的 SharePoint 主页。</span><span class="sxs-lookup"><span data-stu-id="5b570-138">To search for indexed content, go to the SharePoint home page of your test tenant.</span></span> <span data-ttu-id="5b570-139">结果将显示在 "**所有**" 和 "**文件**" 选项卡中。</span><span class="sxs-lookup"><span data-stu-id="5b570-139">Results will be displayed in the **All** and **Files** tabs.</span></span>

<span data-ttu-id="5b570-140">由于浏览器限制，无法从本地文件共享搜索中选择要查看或打开文件的文件结果。</span><span class="sxs-lookup"><span data-stu-id="5b570-140">Because of browser restrictions, you can't select a file result to view or open files from local file share searches.</span></span> <span data-ttu-id="5b570-141">若要打开这些文件，请复制文件结果的链接，并将其粘贴到系统浏览器的地址栏中。</span><span class="sxs-lookup"><span data-stu-id="5b570-141">To open these files, copy the file result's link and paste it into the address bar of your system's browser.</span></span> <span data-ttu-id="5b570-142">对于 Windows，请使用 Windows 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="5b570-142">For Windows, use Windows Explorer.</span></span> <span data-ttu-id="5b570-143">然后，您可以在系统上打开该文件。</span><span class="sxs-lookup"><span data-stu-id="5b570-143">Then you can open the file on your system.</span></span>

![使用 "复制链接" 对话框打开 SharePoint 搜索。](media/fileshare-search.png)

## <a name="troubleshooting"></a><span data-ttu-id="5b570-145">疑难解答</span><span class="sxs-lookup"><span data-stu-id="5b570-145">Troubleshooting</span></span>
<span data-ttu-id="5b570-146">如果连接出现严重错误，其状态将显示为 "**失败**"。</span><span class="sxs-lookup"><span data-stu-id="5b570-146">If something is critically wrong with a connection, its status shows as **failed**.</span></span> <span data-ttu-id="5b570-147">若要获取有关三种错误类型的详细信息，请转到**错误详细信息**页面，然后选择 "失败的连接"。</span><span class="sxs-lookup"><span data-stu-id="5b570-147">To get more information on the three types of errors, go to the **error details** page and select the failing connection.</span></span> <span data-ttu-id="5b570-148">请参阅[管理连接器](manage-connector.md)以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="5b570-148">See [Manage your connector](manage-connector.md) to learn more.</span></span>
1. <span data-ttu-id="5b570-149">**网关不可访问（错误代码：11）**。</span><span class="sxs-lookup"><span data-stu-id="5b570-149">**Gateway not reachable (error code: 11)**.</span></span> <span data-ttu-id="5b570-150">连接的网关计算机已关闭。</span><span class="sxs-lookup"><span data-stu-id="5b570-150">The gateway machine for the connection is down.</span></span> <span data-ttu-id="5b570-151">验证 Microsoft Power BI 进程是否在网关计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="5b570-151">Verify if the Microsoft Power BI process runs on the gateway machine.</span></span>
2. <span data-ttu-id="5b570-152">**身份验证错误（错误代码：12）**。</span><span class="sxs-lookup"><span data-stu-id="5b570-152">**Authentication error (error code: 12)**.</span></span> <span data-ttu-id="5b570-153">用于创建连接的凭据已过期或已不再有效。</span><span class="sxs-lookup"><span data-stu-id="5b570-153">The credentials that were used for creating the connection expired or are no longer valid.</span></span> <span data-ttu-id="5b570-154">若要解决此错误，请输入有效的凭据。</span><span class="sxs-lookup"><span data-stu-id="5b570-154">To resolve this error, enter valid credentials.</span></span>
3. <span data-ttu-id="5b570-155">**内部错误（错误代码：11或12之外的任何内容）**。</span><span class="sxs-lookup"><span data-stu-id="5b570-155">**Internal error (error code: anything other than 11 or 12)**.</span></span> <span data-ttu-id="5b570-156">连接器基础结构中存在错误。</span><span class="sxs-lookup"><span data-stu-id="5b570-156">There's an error in the connector infrastructure.</span></span> <span data-ttu-id="5b570-157">若要了解如何报告这些错误，请参阅[反馈](connectors-feedback.md)文章。</span><span class="sxs-lookup"><span data-stu-id="5b570-157">See the [Feedback](connectors-feedback.md) article to find out how to report these errors.</span></span>

## <a name="limitations"></a><span data-ttu-id="5b570-158">限制</span><span class="sxs-lookup"><span data-stu-id="5b570-158">Limitations</span></span>
<span data-ttu-id="5b570-159">文件共享连接器在预览版本中具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="5b570-159">The File share connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="5b570-160">只能使用固定属性（而不是使用自定义属性的文件）对文件编制索引。</span><span class="sxs-lookup"><span data-stu-id="5b570-160">You can only index files with fixed properties, not files with custom properties.</span></span>
* <span data-ttu-id="5b570-161">目前不支持文件共享访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="5b570-161">File share Access Control Lists (ACLs) aren't currently supported.</span></span>
* <span data-ttu-id="5b570-162">不支持外部标识。</span><span class="sxs-lookup"><span data-stu-id="5b570-162">External identities aren't supported.</span></span> <span data-ttu-id="5b570-163">它们必须映射到 Azure Active Directory 标识。</span><span class="sxs-lookup"><span data-stu-id="5b570-163">They must be mapped to Azure Active Directory identities.</span></span>