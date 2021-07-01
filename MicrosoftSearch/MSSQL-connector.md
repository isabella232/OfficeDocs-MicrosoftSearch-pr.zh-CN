---
title: Azure SQL 和 Microsoft SQL Server Graph 连接器Microsoft 搜索
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置 Azure SQL 和 Microsoft SQL Graph 连接器Microsoft 搜索。
ms.openlocfilehash: 0f8501e36754235b43846b80d60d4b0156a504b9
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230913"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a><span data-ttu-id="16179-103">Azure SQL 和 Microsoft SQL Server Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="16179-103">Azure SQL and Microsoft SQL Server Graph connectors</span></span>

<span data-ttu-id="16179-104">借助 Microsoft SQL Server 或 Azure SQL Graph 连接器，组织可以发现本地 SQL Server 数据库或托管在云中的 Azure SQL 实例中的数据库的数据，并编制索引。</span><span class="sxs-lookup"><span data-stu-id="16179-104">The Microsoft SQL Server or Azure SQL Graph connector allows your organization to discover and index data from an on-premises SQL Server database, or a database hosted in your Azure SQL instance in the cloud.</span></span>
<span data-ttu-id="16179-105">该Graph连接器将指定内容索引到Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="16179-105">The Graph connector indexes specified content into Microsoft Search.</span></span> <span data-ttu-id="16179-106">若要使索引与源数据保持最新，它支持定期完全爬网和增量爬网。</span><span class="sxs-lookup"><span data-stu-id="16179-106">To keep the index up to date with source data, it supports periodic full and incremental crawls.</span></span> <span data-ttu-id="16179-107">使用这些SQL连接器，还可以限制某些用户对搜索结果的访问。</span><span class="sxs-lookup"><span data-stu-id="16179-107">With these SQL connectors, you can also restrict access to search results for certain users.</span></span>

> [!NOTE]
> <span data-ttu-id="16179-108">阅读 [**Setup your Graph connector**](configure-connector.md)一文，了解 Graph 连接器的一般设置说明。</span><span class="sxs-lookup"><span data-stu-id="16179-108">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="16179-109">本文适用于配置、运行和监视 Azure SQL 和 Microsoft SQL 服务器Graph连接器。</span><span class="sxs-lookup"><span data-stu-id="16179-109">This article is for anyone who configures, runs, and monitors an Azure SQL and Microsoft SQL server Graph connector.</span></span> <span data-ttu-id="16179-110">它补充了常规安装过程，并显示了仅适用于 Azure SQL 和 Microsoft SQL 服务器Graph说明。</span><span class="sxs-lookup"><span data-stu-id="16179-110">It supplements the general setup process, and shows instructions that apply only for the Azure SQL and Microsoft SQL server Graph connector.</span></span> <span data-ttu-id="16179-111">本文还包括有关 Microsoft [](#limitations) SQL 和 Azure SQL连接器的限制的信息。</span><span class="sxs-lookup"><span data-stu-id="16179-111">This article also includes information about [Limitations](#limitations) for the Microsoft SQL server and Azure SQL connectors.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="16179-112">在开始使用之前</span><span class="sxs-lookup"><span data-stu-id="16179-112">Before you get started</span></span>

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a><span data-ttu-id="16179-113">仅Graph本地 (连接器所需的 Microsoft SQL Server 连接器代理) </span><span class="sxs-lookup"><span data-stu-id="16179-113">Install the Graph connector agent (required for on-premises Microsoft SQL Server connector only)</span></span>

<span data-ttu-id="16179-114">若要访问本地第三方数据，必须安装和配置 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="16179-114">In order to access your on-premises third-party data, you must install and configure the Graph connector agent.</span></span> <span data-ttu-id="16179-115">有关详细信息[，请参阅](on-prem-agent.md)Graph连接器代理。</span><span class="sxs-lookup"><span data-stu-id="16179-115">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="16179-116">步骤 1：在Graph中添加一个Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="16179-116">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="16179-117">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="16179-117">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="16179-118">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="16179-118">Step 2: Name the connection</span></span>

<span data-ttu-id="16179-119">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="16179-119">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="16179-120">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="16179-120">Step 3: Configure the connection settings</span></span>

### <a name="register-an-app-for-azure-sql-connector-only"></a><span data-ttu-id="16179-121">仅为 Azure (连接器SQL应用) </span><span class="sxs-lookup"><span data-stu-id="16179-121">Register an app (for Azure SQL connector only)</span></span>

<span data-ttu-id="16179-122">对于 Azure SQL 连接器，必须在 Azure Active Directory 注册应用，Microsoft 搜索访问数据进行索引。</span><span class="sxs-lookup"><span data-stu-id="16179-122">For Azure SQL connector, you must register an app in Azure Active Directory to allow Microsoft Search app to access data for indexing.</span></span> <span data-ttu-id="16179-123">若要了解有关注册应用的信息，请参阅 Microsoft Graph注册应用[的文档](/graph/auth-register-app-v2)。</span><span class="sxs-lookup"><span data-stu-id="16179-123">To learn more about registering an app, refer Microsoft Graph documentation on how to [register an app](/graph/auth-register-app-v2).</span></span>

<span data-ttu-id="16179-124">完成应用注册并记下应用名称、 (客户端) ID 和租户 ID 后，需要生成一 [个新的客户端密码](/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret)。</span><span class="sxs-lookup"><span data-stu-id="16179-124">After completing the app registration and taking note of the app name, application (client) ID and tenant ID, you need to [generate a new client secret](/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret).</span></span> <span data-ttu-id="16179-125">客户端密码将只显示一次。</span><span class="sxs-lookup"><span data-stu-id="16179-125">The client secret will only be displayed once.</span></span> <span data-ttu-id="16179-126">请记住，&安全存储客户端密码。</span><span class="sxs-lookup"><span data-stu-id="16179-126">Remember to note & store the client secret securely.</span></span> <span data-ttu-id="16179-127">在客户端 ID 和客户端密码中配置新连接时Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="16179-127">Use the client ID and client secret while configuring a new connection in Microsoft Search.</span></span>

<span data-ttu-id="16179-128">若要将注册的应用添加到Azure SQL 数据库，你需要：</span><span class="sxs-lookup"><span data-stu-id="16179-128">To add the registered app to your Azure SQL Database, you need to:</span></span>

- <span data-ttu-id="16179-129">登录到 Azure SQL DB</span><span class="sxs-lookup"><span data-stu-id="16179-129">Log in to your Azure SQL DB</span></span>
- <span data-ttu-id="16179-130">打开新的查询窗口</span><span class="sxs-lookup"><span data-stu-id="16179-130">Open a new query window</span></span>
- <span data-ttu-id="16179-131">通过运行命令"CREATE USER [app name] FROM EXTERNAL PROVIDER"创建新用户</span><span class="sxs-lookup"><span data-stu-id="16179-131">Create a new user by running the command 'CREATE USER [app name] FROM EXTERNAL PROVIDER'</span></span>
- <span data-ttu-id="16179-132">通过运行命令"exec sp_addrolemember"db_datareader，[应用名称]"或"ALTER ROLE db_datareader ADD MEMBER [app name]"将用户添加到角色</span><span class="sxs-lookup"><span data-stu-id="16179-132">Add user to role by running command 'exec sp_addrolemember 'db_datareader', [app name]'  Or  'ALTER ROLE db_datareader ADD MEMBER [app name]'</span></span>

>[!NOTE]
><span data-ttu-id="16179-133">若要撤销对在 Azure Active Directory 中注册的任何应用的访问权限，请参阅有关删除已注册应用的 Azure[文档](/azure/active-directory/develop/quickstart-remove-app)。</span><span class="sxs-lookup"><span data-stu-id="16179-133">To revoke access to any app registered in Azure Active Directory, refer the Azure documentation on [removing a registered app](/azure/active-directory/develop/quickstart-remove-app).</span></span>

### <a name="connection-settings"></a><span data-ttu-id="16179-134">连接设置</span><span class="sxs-lookup"><span data-stu-id="16179-134">Connection settings</span></span>

<span data-ttu-id="16179-135">若要将Microsoft SQL Server连接器连接到数据源，必须配置数据库服务器爬网的连接器和本地代理。</span><span class="sxs-lookup"><span data-stu-id="16179-135">To connect your Microsoft SQL Server connector to a data source, you must configure the database server you want crawled and the on-prem agent.</span></span> <span data-ttu-id="16179-136">然后，您可以使用所需的身份验证方法连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="16179-136">You can then connect to the database with the required authentication method.</span></span>

> [!NOTE] 
> <span data-ttu-id="16179-137">您的数据库必须SQL Server 2008 或更高版本，Microsoft SQL Server连接器才能连接。</span><span class="sxs-lookup"><span data-stu-id="16179-137">Your database must run SQL Server version 2008 or later for the Microsoft SQL Server connector to be able to connect.</span></span>

<span data-ttu-id="16179-138">对于 Azure SQL 连接器，只需指定要连接到的服务器名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="16179-138">For the Azure SQL connector, you only need to specify the server name or IP address you want to connect to.</span></span> <span data-ttu-id="16179-139">Azure SQL 连接器仅Azure Active Directory OIDC (OIDC) 打开 ID 连接以连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="16179-139">Azure SQL connector only supports Azure Active Directory Open ID connect (OIDC) authentication to connect to the database.</span></span>

<span data-ttu-id="16179-140">为了增加安全性，你可以为 Azure 服务器或数据库SQL Server IP 防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="16179-140">For added security, you may configure IP firewall rules for your Azure SQL Server or database.</span></span> <span data-ttu-id="16179-141">若要了解有关设置 IP 防火墙规则的信息，请参阅有关 [IP 防火墙规则的文档](/azure/azure-sql/database/firewall-configure)。</span><span class="sxs-lookup"><span data-stu-id="16179-141">To learn more about setting up IP firewall rules, refer documentation on [IP firewall rules](/azure/azure-sql/database/firewall-configure).</span></span> <span data-ttu-id="16179-142">在防火墙设置中添加以下客户端 IP 范围。</span><span class="sxs-lookup"><span data-stu-id="16179-142">Add the following client IP ranges in the firewall settings.</span></span>

| <span data-ttu-id="16179-143">区域</span><span class="sxs-lookup"><span data-stu-id="16179-143">Region</span></span> | <span data-ttu-id="16179-144">IP 范围</span><span class="sxs-lookup"><span data-stu-id="16179-144">IP Range</span></span> |
| ------------ | ------------ |
| <span data-ttu-id="16179-145">NAM</span><span class="sxs-lookup"><span data-stu-id="16179-145">NAM</span></span> | <span data-ttu-id="16179-146">52.250.92.252/30, 52.224.250.216/30</span><span class="sxs-lookup"><span data-stu-id="16179-146">52.250.92.252/30, 52.224.250.216/30</span></span> |
| <span data-ttu-id="16179-147">EUR</span><span class="sxs-lookup"><span data-stu-id="16179-147">EUR</span></span> | <span data-ttu-id="16179-148">20.54.41.208/30, 51.105.159.88/30</span><span class="sxs-lookup"><span data-stu-id="16179-148">20.54.41.208/30, 51.105.159.88/30</span></span> |
| <span data-ttu-id="16179-149">APC</span><span class="sxs-lookup"><span data-stu-id="16179-149">APC</span></span> | <span data-ttu-id="16179-150">52.139.188.212/30, 20.43.146.44/30</span><span class="sxs-lookup"><span data-stu-id="16179-150">52.139.188.212/30, 20.43.146.44/30</span></span> |

<span data-ttu-id="16179-151">若要搜索数据库内容，必须在配置连接器SQL指定查询。</span><span class="sxs-lookup"><span data-stu-id="16179-151">To search your database content, you must specify SQL queries when you configure the connector.</span></span> <span data-ttu-id="16179-152">这些SQL查询需要命名要索引的所有数据库列 (即源属性) ，包括获取所有列需要执行的任何 SQL 联接。</span><span class="sxs-lookup"><span data-stu-id="16179-152">These SQL queries need to name all the database columns that you want to index (that is, source properties), including any SQL joins that need to be performed to get all the columns.</span></span> <span data-ttu-id="16179-153">若要限制对搜索结果的访问，必须在配置连接器时 (在) 查询SQL访问控制列表和 ACL。</span><span class="sxs-lookup"><span data-stu-id="16179-153">To restrict access to search results, you must specify Access Control Lists (ACLs) within SQL queries when you configure the connector.</span></span>

## <a name="step-3a-full-crawl-required"></a><span data-ttu-id="16179-154">步骤 3a：必需 (完全) </span><span class="sxs-lookup"><span data-stu-id="16179-154">Step 3a: Full crawl (Required)</span></span>

<span data-ttu-id="16179-155">在此步骤中，配置SQL数据库完全爬网的查询。</span><span class="sxs-lookup"><span data-stu-id="16179-155">In this step, you configure the SQL query that runs a full crawl of the database.</span></span> <span data-ttu-id="16179-156">完全爬网将选择要选择选项"查询、搜索"或"检索"的所有列或 **属性**。 </span><span class="sxs-lookup"><span data-stu-id="16179-156">The full crawl selects all the columns or properties where you want to select the options **Query**, **Search**, or **Retrieve**.</span></span> <span data-ttu-id="16179-157">还可以指定 ACL 列以限制对特定用户或组的搜索结果的访问。</span><span class="sxs-lookup"><span data-stu-id="16179-157">You can also specify ACL columns to restrict access of search results to specific users or groups.</span></span>

> [!Tip]
> <span data-ttu-id="16179-158">若要获取所需的所有列，可以联接多个表。</span><span class="sxs-lookup"><span data-stu-id="16179-158">To get all the columns that you need, you can join multiple tables.</span></span>

![显示 OrderTable 和 AclTable 以及示例属性的脚本](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a><span data-ttu-id="16179-160">Select data columns (Required) and ACL columns (Optional) </span><span class="sxs-lookup"><span data-stu-id="16179-160">Select data columns (Required) and ACL columns (Optional)</span></span>

<span data-ttu-id="16179-161">该示例演示保留搜索数据的五个数据列的选择：OrderId、OrderTitle、OrderDesc、CreatedDateTime 和 IsDeleted。</span><span class="sxs-lookup"><span data-stu-id="16179-161">The example demonstrates a selection of five data columns that hold the data for the search: OrderId, OrderTitle, OrderDesc, CreatedDateTime, and IsDeleted.</span></span> <span data-ttu-id="16179-162">若要设置每行数据的查看权限，可以选择以下 ACL 列：AllowedUsers、AllowedGroups、DeniedUsers 和 DeniedGroups。</span><span class="sxs-lookup"><span data-stu-id="16179-162">To set view permissions for each row of data, you can optionally select these ACL columns: AllowedUsers, AllowedGroups, DeniedUsers, and DeniedGroups.</span></span> <span data-ttu-id="16179-163">所有这些数据列还具有查询、**搜索或** 检索 **的选项**。 </span><span class="sxs-lookup"><span data-stu-id="16179-163">All these data columns also have the options to **Query**, **Search**, or **Retrieve**.</span></span>

<span data-ttu-id="16179-164">选择数据列，如此示例查询中所示： `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span><span class="sxs-lookup"><span data-stu-id="16179-164">Select data columns as shown in this example query: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span></span>

<span data-ttu-id="16179-165">若要管理对搜索结果的访问，可以在查询中指定一个或多个 ACL 列。</span><span class="sxs-lookup"><span data-stu-id="16179-165">To manage access to the search results, you can specify one or more ACL columns in the query.</span></span> <span data-ttu-id="16179-166">利用SQL连接器，您可以控制每个记录级别的访问。</span><span class="sxs-lookup"><span data-stu-id="16179-166">The SQL connector allows you to control access at per record level.</span></span> <span data-ttu-id="16179-167">您可以选择对表中的所有记录具有相同的访问控制。</span><span class="sxs-lookup"><span data-stu-id="16179-167">You can choose to have the same access control for all records in a table.</span></span> <span data-ttu-id="16179-168">如果 ACL 信息存储在单独的表中，您可能必须执行与查询中这些表的联接。</span><span class="sxs-lookup"><span data-stu-id="16179-168">If the ACL information is stored in a separate table, you might have to do a join with those tables in your query.</span></span>

<span data-ttu-id="16179-169">下面介绍了上述查询中每个 ACL 列的使用。</span><span class="sxs-lookup"><span data-stu-id="16179-169">The use of each of the ACL columns in the above query is described below.</span></span> <span data-ttu-id="16179-170">以下列表说明了四 **种访问控制机制**。</span><span class="sxs-lookup"><span data-stu-id="16179-170">The following list explains the four **access control mechanisms**.</span></span>

- <span data-ttu-id="16179-171">**AllowedUsers：** 此列指定可以访问搜索结果的用户 ID 列表。</span><span class="sxs-lookup"><span data-stu-id="16179-171">**AllowedUsers**: This column specifies the list of user IDs who can access the search results.</span></span> <span data-ttu-id="16179-172">在下面的示例中，用户列表：john@contoso.com、keith@contoso.com 和 lisa@contoso.com 只能访问 OrderId = 12 的记录。</span><span class="sxs-lookup"><span data-stu-id="16179-172">In the following example, list of users: john@contoso.com, keith@contoso.com, and lisa@contoso.com would only have access to a record with OrderId = 12.</span></span>
- <span data-ttu-id="16179-173">**AllowedGroups：** 此列指定能够访问搜索结果的一组用户。</span><span class="sxs-lookup"><span data-stu-id="16179-173">**AllowedGroups**: This column specifies the group of users who will be able to access the search results.</span></span> <span data-ttu-id="16179-174">在下面的示例中，组 sales-team@contoso.com 只能访问 OrderId = 12 的记录。</span><span class="sxs-lookup"><span data-stu-id="16179-174">In the following example, group sales-team@contoso.com would only have access to record with OrderId = 12.</span></span>
- <span data-ttu-id="16179-175">**DeniedUsers：** 此列指定无法访问搜索结果的用户的列表。 </span><span class="sxs-lookup"><span data-stu-id="16179-175">**DeniedUsers**: This column specifies the list of users who do **not** have access to the search results.</span></span> <span data-ttu-id="16179-176">在下面的示例中，john@contoso.com 和 keith@contoso.com 用户无法访问 OrderId = 13 的记录，而其他人则有权访问此记录。</span><span class="sxs-lookup"><span data-stu-id="16179-176">In the following example, users john@contoso.com and keith@contoso.com do not have access to record with OrderId = 13, whereas everyone else has access to this record.</span></span>
- <span data-ttu-id="16179-177">**DeniedGroups：** 此列指定无法访问搜索结果的一组用户。 </span><span class="sxs-lookup"><span data-stu-id="16179-177">**DeniedGroups**: This column specifies the group of users who do **not** have access to the search results.</span></span> <span data-ttu-id="16179-178">在下面的示例中，engg-team@contoso.com 和 pm-team@contoso.com 组不能访问 OrderId = 15 的记录，而其他人则有权访问此记录。</span><span class="sxs-lookup"><span data-stu-id="16179-178">In the following example, groups engg-team@contoso.com and pm-team@contoso.com do not have access to record with OrderId = 15, whereas everyone else has access to this record.</span></span>  

![显示 OrderTable 和 AclTable 的示例数据（包含示例属性）](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a><span data-ttu-id="16179-180">支持的数据类型</span><span class="sxs-lookup"><span data-stu-id="16179-180">Supported data types</span></span>

<span data-ttu-id="16179-181">下表总结了 MS SQL 和 Azure SQL 连接器中支持SQL数据类型。</span><span class="sxs-lookup"><span data-stu-id="16179-181">The below table summarizes the SQL data types that are supported in the MS SQL and Azure SQL connectors.</span></span> <span data-ttu-id="16179-182">该表还汇总了数据类型索引索引SQL 数据类型。</span><span class="sxs-lookup"><span data-stu-id="16179-182">The table also summarizes the indexing data type for the supported SQL data type.</span></span> <span data-ttu-id="16179-183">若要了解有关 Microsoft 连接器Graph索引支持的数据类型的信息，请参阅有关属性[资源类型的文档](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties)。</span><span class="sxs-lookup"><span data-stu-id="16179-183">To learn more about Microsoft Graph connectors supported data types for indexing, refer documentation on [property resource types](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties).</span></span>

| <span data-ttu-id="16179-184">类别</span><span class="sxs-lookup"><span data-stu-id="16179-184">Category</span></span> | <span data-ttu-id="16179-185">源数据类型</span><span class="sxs-lookup"><span data-stu-id="16179-185">Source data type</span></span> | <span data-ttu-id="16179-186">索引数据类型</span><span class="sxs-lookup"><span data-stu-id="16179-186">Indexing data type</span></span> |
| ------------ | ------------ | ------------ |
| <span data-ttu-id="16179-187">日期和时间</span><span class="sxs-lookup"><span data-stu-id="16179-187">Date and time</span></span> | <span data-ttu-id="16179-188">date</span><span class="sxs-lookup"><span data-stu-id="16179-188">date</span></span> <br> <span data-ttu-id="16179-189">datetime</span><span class="sxs-lookup"><span data-stu-id="16179-189">datetime</span></span> <br> <span data-ttu-id="16179-190">datetime2</span><span class="sxs-lookup"><span data-stu-id="16179-190">datetime2</span></span> <br> <span data-ttu-id="16179-191">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="16179-191">smalldatetime</span></span> | <span data-ttu-id="16179-192">datetime</span><span class="sxs-lookup"><span data-stu-id="16179-192">datetime</span></span> |
| <span data-ttu-id="16179-193">精确数字</span><span class="sxs-lookup"><span data-stu-id="16179-193">Exact numeric</span></span> | <span data-ttu-id="16179-194">bigint</span><span class="sxs-lookup"><span data-stu-id="16179-194">bigint</span></span> <br> <span data-ttu-id="16179-195">int</span><span class="sxs-lookup"><span data-stu-id="16179-195">int</span></span> <br> <span data-ttu-id="16179-196">smallint</span><span class="sxs-lookup"><span data-stu-id="16179-196">smallint</span></span> <br> <span data-ttu-id="16179-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="16179-197">tinyint</span></span> | <span data-ttu-id="16179-198">int64</span><span class="sxs-lookup"><span data-stu-id="16179-198">int64</span></span> |
| <span data-ttu-id="16179-199">精确数字</span><span class="sxs-lookup"><span data-stu-id="16179-199">Exact numeric</span></span> | <span data-ttu-id="16179-200">bit</span><span class="sxs-lookup"><span data-stu-id="16179-200">bit</span></span> | <span data-ttu-id="16179-201">boolean</span><span class="sxs-lookup"><span data-stu-id="16179-201">boolean</span></span> |
| <span data-ttu-id="16179-202">近似数值</span><span class="sxs-lookup"><span data-stu-id="16179-202">Approximate numeric</span></span> | <span data-ttu-id="16179-203">float</span><span class="sxs-lookup"><span data-stu-id="16179-203">float</span></span> <br> <span data-ttu-id="16179-204">real</span><span class="sxs-lookup"><span data-stu-id="16179-204">real</span></span> | <span data-ttu-id="16179-205">double</span><span class="sxs-lookup"><span data-stu-id="16179-205">double</span></span> |
| <span data-ttu-id="16179-206">字符串</span><span class="sxs-lookup"><span data-stu-id="16179-206">Character string</span></span> | <span data-ttu-id="16179-207">char</span><span class="sxs-lookup"><span data-stu-id="16179-207">char</span></span> <br> <span data-ttu-id="16179-208">varchar</span><span class="sxs-lookup"><span data-stu-id="16179-208">varchar</span></span> <br> <span data-ttu-id="16179-209">text</span><span class="sxs-lookup"><span data-stu-id="16179-209">text</span></span> | <span data-ttu-id="16179-210">string</span><span class="sxs-lookup"><span data-stu-id="16179-210">string</span></span> |
| <span data-ttu-id="16179-211">Unicode 字符字符串</span><span class="sxs-lookup"><span data-stu-id="16179-211">Unicode character strings</span></span> | <span data-ttu-id="16179-212">nchar</span><span class="sxs-lookup"><span data-stu-id="16179-212">nchar</span></span> <br> <span data-ttu-id="16179-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="16179-213">nvarchar</span></span> <br> <span data-ttu-id="16179-214">ntext</span><span class="sxs-lookup"><span data-stu-id="16179-214">ntext</span></span> | <span data-ttu-id="16179-215">string</span><span class="sxs-lookup"><span data-stu-id="16179-215">string</span></span> |
| <span data-ttu-id="16179-216">其他数据类型</span><span class="sxs-lookup"><span data-stu-id="16179-216">Other data types</span></span> | <span data-ttu-id="16179-217">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="16179-217">uniqueidentifier</span></span> | <span data-ttu-id="16179-218">string</span><span class="sxs-lookup"><span data-stu-id="16179-218">string</span></span> |

<span data-ttu-id="16179-219">对于当前数据类型不支持的其他任何字段，需要将列显式强制转换到受支持的数据类型。</span><span class="sxs-lookup"><span data-stu-id="16179-219">For any other data type currently not directly supported, the column needs to be explicitly cast to a supported data type.</span></span>

### <a name="watermark-required"></a><span data-ttu-id="16179-220">需要 (水印) </span><span class="sxs-lookup"><span data-stu-id="16179-220">Watermark (Required)</span></span>

<span data-ttu-id="16179-221">为了防止数据库过载，连接器使用完全爬网水印列批处理和恢复完全爬网查询。</span><span class="sxs-lookup"><span data-stu-id="16179-221">To prevent overloading the database, the connector batches and resumes full-crawl queries with a full-crawl watermark column.</span></span> <span data-ttu-id="16179-222">通过使用水印列的值，将提取每个后续批次，并且从最后一个检查点恢复查询。</span><span class="sxs-lookup"><span data-stu-id="16179-222">By using the value of the watermark column, each subsequent batch is fetched, and querying is resumed from the last checkpoint.</span></span> <span data-ttu-id="16179-223">实质上，此机制控制完全爬网的数据刷新。</span><span class="sxs-lookup"><span data-stu-id="16179-223">Essentially this mechanisms controls data refresh for full crawls.</span></span>

<span data-ttu-id="16179-224">为水印创建查询代码段，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="16179-224">Create query snippets for watermarks as shown in these examples:</span></span>

- <span data-ttu-id="16179-225">`WHERE (CreatedDateTime > @watermark)`.</span><span class="sxs-lookup"><span data-stu-id="16179-225">`WHERE (CreatedDateTime > @watermark)`.</span></span> <span data-ttu-id="16179-226">使用保留的关键字 引用水印列名称 `@watermark` 。</span><span class="sxs-lookup"><span data-stu-id="16179-226">Cite the watermark column name with the reserved keyword `@watermark`.</span></span> <span data-ttu-id="16179-227">如果水印列的排序顺序为升序，请使用 `>` ;否则，请使用 `<` 。</span><span class="sxs-lookup"><span data-stu-id="16179-227">If the sort order of the watermark column is ascending, use `>`; otherwise, use `<`.</span></span>
- <span data-ttu-id="16179-228">`ORDER BY CreatedDateTime ASC`.</span><span class="sxs-lookup"><span data-stu-id="16179-228">`ORDER BY CreatedDateTime ASC`.</span></span> <span data-ttu-id="16179-229">按水印列的升序或降序排序。</span><span class="sxs-lookup"><span data-stu-id="16179-229">Sort on the watermark column in ascending or descending order.</span></span>

<span data-ttu-id="16179-230">在下图所示的配置中，是 `CreatedDateTime` 选定的水印列。</span><span class="sxs-lookup"><span data-stu-id="16179-230">In the configuration shown in the following image, `CreatedDateTime` is the selected watermark column.</span></span> <span data-ttu-id="16179-231">若要提取第一批行，请数据类型列的行号。</span><span class="sxs-lookup"><span data-stu-id="16179-231">To fetch the first batch of rows, specify the data type of the watermark column.</span></span> <span data-ttu-id="16179-232">在这种情况下，数据类型为 `DateTime` 。</span><span class="sxs-lookup"><span data-stu-id="16179-232">In this case, the data type is `DateTime`.</span></span>

![水印列配置](media/MSSQL-watermark.png)

<span data-ttu-id="16179-234">第一个查询使用"CreatedDateTime > January 1， 1753 00：00：00" 获取前 **N** (个行的最小值 DateTime 数据类型) 。</span><span class="sxs-lookup"><span data-stu-id="16179-234">The first query fetches the first **N** number of rows by using: "CreatedDateTime > January 1, 1753 00:00:00" (min value of DateTime data type).</span></span> <span data-ttu-id="16179-235">获取第一个批次后，如果行按升序排序，批处理中返回的最高级别值将另存为 `CreatedDateTime` 检查点。</span><span class="sxs-lookup"><span data-stu-id="16179-235">After the first batch is fetched, the highest value of `CreatedDateTime` returned in the batch is saved as the checkpoint if the rows are sorted in ascending order.</span></span> <span data-ttu-id="16179-236">例如，2019 年 3 月 1 日 03：00：00。</span><span class="sxs-lookup"><span data-stu-id="16179-236">An example is March 1, 2019 03:00:00.</span></span> <span data-ttu-id="16179-237">然后，使用查询中的"CreatedDateTime > 2019 年 3 月 1 日 03：00：00"提取下一批 **N** 行。</span><span class="sxs-lookup"><span data-stu-id="16179-237">Then the next batch of **N** rows is fetched by using "CreatedDateTime > March 1, 2019 03:00:00" in the query.</span></span>

### <a name="skipping-soft-deleted-rows-optional"></a><span data-ttu-id="16179-238">跳过软删除的行 (可选) </span><span class="sxs-lookup"><span data-stu-id="16179-238">Skipping soft-deleted rows (Optional)</span></span>

<span data-ttu-id="16179-239">若要排除对数据库中的软删除行编制索引，请指定软删除列名称和值，以指示该行已被删除。</span><span class="sxs-lookup"><span data-stu-id="16179-239">To exclude soft-deleted rows in your database from being indexed, specify the soft-delete column name and value that indicates the row is deleted.</span></span>

![软删除设置："软删除列"和"指示已删除行的软删除列的值"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a><span data-ttu-id="16179-241">完全爬网：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="16179-241">Full crawl: Manage search permissions</span></span>

<span data-ttu-id="16179-242">选择 **"管理权限** "以选择各种访问控制 (ACL) 指定访问控制机制的列。</span><span class="sxs-lookup"><span data-stu-id="16179-242">Select **Manage permissions** to choose the various access control (ACL) columns that specify the access control mechanism.</span></span> <span data-ttu-id="16179-243">Select the column name you specified in the full crawl SQL query.</span><span class="sxs-lookup"><span data-stu-id="16179-243">Select the column name you specified in the full crawl SQL query.</span></span>

<span data-ttu-id="16179-244">每个 ACL 列应都是一个多值列。</span><span class="sxs-lookup"><span data-stu-id="16179-244">Each of the ACL columns is expected to be a multi-valued column.</span></span> <span data-ttu-id="16179-245">这些多个 ID 值可以使用分隔符分隔，如分号 (;) 、逗号 (、) 等。</span><span class="sxs-lookup"><span data-stu-id="16179-245">These multiple ID values can be separated by separators such as semicolon (;), comma (,), and so on.</span></span> <span data-ttu-id="16179-246">需要在值分隔符字段中指定 **此分隔** 符。</span><span class="sxs-lookup"><span data-stu-id="16179-246">You need to specify this separator in the **value separator** field.</span></span>

<span data-ttu-id="16179-247">支持将以下 ID 类型用作 ACL：</span><span class="sxs-lookup"><span data-stu-id="16179-247">The following ID types are supported for using as ACLs:</span></span>

- <span data-ttu-id="16179-248">**用户主体名称 (UPN) ：** 用户主体名称 (UPN) 是电子邮件地址格式的系统用户的名称。</span><span class="sxs-lookup"><span data-stu-id="16179-248">**User Principal Name (UPN)**: A User Principal Name (UPN) is the name of a system user in an email address format.</span></span> <span data-ttu-id="16179-249">UPN (例如：john.doe@domain.com) 由用户名 (登录名) 、分隔符 (@ 符号) 和域名 (UPN 后缀) 组成。</span><span class="sxs-lookup"><span data-stu-id="16179-249">A UPN (for example: john.doe@domain.com) consists of the username (logon name), separator (the @ symbol), and domain name (UPN suffix).</span></span>
- <span data-ttu-id="16179-250">**Azure Active Directory (AAD) ID：** 在 Azure AD 中，每个用户或组都有类似于"e0d3ad3d-0000-1111-2222-3c5f5c52ab9b"的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="16179-250">**Azure Active Directory (AAD) ID**: In Azure AD, every user or group has an object ID that looks something like 'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b'.</span></span>
- <span data-ttu-id="16179-251">**Active Directory (AD) 安全 ID：在本地 AD** 设置中，每个用户和组都有一个不可变的唯一安全标识符，类似于"S-1-5-21-3878594291-2115959936-132693609-65242"。</span><span class="sxs-lookup"><span data-stu-id="16179-251">**Active Directory (AD) Security ID**: In an on-premises AD setup, every user and group have an immutable, unique security identifier that looks something like 'S-1-5-21-3878594291-2115959936-132693609-65242.'</span></span>

![用于配置访问控制列表的搜索权限设置](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a><span data-ttu-id="16179-253">步骤 3b：增量爬网 (可选) </span><span class="sxs-lookup"><span data-stu-id="16179-253">Step 3b: Incremental crawl (Optional)</span></span>

<span data-ttu-id="16179-254">在此可选步骤中，提供SQL查询以运行数据库的增量爬网。</span><span class="sxs-lookup"><span data-stu-id="16179-254">In this optional step, provide a SQL query to run an incremental crawl of the database.</span></span> <span data-ttu-id="16179-255">通过此查询，SQL连接器可确定自上次增量爬网以来对数据进行的任何更改。</span><span class="sxs-lookup"><span data-stu-id="16179-255">With this query, the SQL connector determines any changes to the data since the last incremental crawl.</span></span> <span data-ttu-id="16179-256">与在完全爬网中一样，选择要选择选项"查询、搜索"或"检索"的所有 **列**。</span><span class="sxs-lookup"><span data-stu-id="16179-256">As in the full crawl, select all columns where you want to select the options **Query**, **Search**, or **Retrieve**.</span></span> <span data-ttu-id="16179-257">指定在完全爬网查询中指定的同一组 ACL 列。</span><span class="sxs-lookup"><span data-stu-id="16179-257">Specify the same set of ACL columns that you specified in the full crawl query.</span></span>

<span data-ttu-id="16179-258">下图中的组件类似于完全爬网组件，但只有一个例外。</span><span class="sxs-lookup"><span data-stu-id="16179-258">The components in the following image resemble the full crawl components with one exception.</span></span> <span data-ttu-id="16179-259">在这种情况下，"ModifiedDateTime"为选定的水印列。</span><span class="sxs-lookup"><span data-stu-id="16179-259">In this case, "ModifiedDateTime" is the selected watermark column.</span></span> <span data-ttu-id="16179-260">查看 [完全爬网步骤](#step-3a-full-crawl-required) ，了解如何编写增量爬网查询，并查看下图作为示例。</span><span class="sxs-lookup"><span data-stu-id="16179-260">Review the [full crawl steps](#step-3a-full-crawl-required) to learn how to write your incremental crawl query and see the following image as an example.</span></span>

![显示可以使用的 OrderTable、AclTable 和示例属性的增量爬网脚本。](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="16179-262">步骤 4：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="16179-262">Step 4: Assign property labels</span></span>

<span data-ttu-id="16179-263">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="16179-263">Follow the general [setup instructions](./configure-connector.md).</span></span>

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a><span data-ttu-id="16179-264">步骤 5：管理架构</span><span class="sxs-lookup"><span data-stu-id="16179-264">Step 5: Manage schema</span></span>

<span data-ttu-id="16179-265">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="16179-265">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="16179-266">步骤 6：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="16179-266">Step 6: Manage search permissions</span></span>

<span data-ttu-id="16179-267">可以选择使用在完全爬网 [屏幕中指定的 ACL，](#full-crawl-manage-search-permissions) 也可以覆盖它们，使内容对所有人都可见。</span><span class="sxs-lookup"><span data-stu-id="16179-267">You can choose to use the [ACLs specified in the full crawl screen](#full-crawl-manage-search-permissions) or you can override them to make your content visible to everyone.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="16179-268">步骤 7：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="16179-268">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="16179-269">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="16179-269">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="16179-270">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="16179-270">Step 8: Review connection</span></span>

<span data-ttu-id="16179-271">按照常规 [设置说明操作](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="16179-271">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).-->

## <a name="troubleshooting"></a><span data-ttu-id="16179-272">疑难解答</span><span class="sxs-lookup"><span data-stu-id="16179-272">Troubleshooting</span></span>

<span data-ttu-id="16179-273">以下是配置连接器时观察到的常见错误及其可能的原因。</span><span class="sxs-lookup"><span data-stu-id="16179-273">The following is a common error observed while configuring the connector, and its possible reason.</span></span>

| <span data-ttu-id="16179-274">配置步骤</span><span class="sxs-lookup"><span data-stu-id="16179-274">Configuration step</span></span> | <span data-ttu-id="16179-275">错误消息</span><span class="sxs-lookup"><span data-stu-id="16179-275">Error message</span></span> | <span data-ttu-id="16179-276">可能 (原因) </span><span class="sxs-lookup"><span data-stu-id="16179-276">Possible reason(s)</span></span> |
| ------------ | ------------ | ------------ |
| <span data-ttu-id="16179-277">完全爬网</span><span class="sxs-lookup"><span data-stu-id="16179-277">Full crawl</span></span> | `Error from database server: A transport level error has occurred when receiving results from the server.` | <span data-ttu-id="16179-278">由于网络问题，导致出现此错误。</span><span class="sxs-lookup"><span data-stu-id="16179-278">This error arises due to network issues.</span></span> <span data-ttu-id="16179-279">建议使用 Microsoft 网络监视器检查网络日志 [，](https://www.microsoft.com/download/details.aspx?id=4865) 并联系 Microsoft 客户支持。</span><span class="sxs-lookup"><span data-stu-id="16179-279">It is recommended to check network logs using [Microsoft network monitor](https://www.microsoft.com/download/details.aspx?id=4865) and reach out to Microsoft customer support.</span></span> |

## <a name="limitations"></a><span data-ttu-id="16179-280">限制</span><span class="sxs-lookup"><span data-stu-id="16179-280">Limitations</span></span>

<span data-ttu-id="16179-281">预览SQL连接器有以下限制：</span><span class="sxs-lookup"><span data-stu-id="16179-281">The SQL connectors have these limitations in the preview release:</span></span>

- <span data-ttu-id="16179-282">Microsoft SQL Server连接器：内部部署数据库必须运行 SQL Server 2008 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="16179-282">Microsoft SQL Server connector: The on-premises database must run SQL Server version 2008 or later.</span></span>

- <span data-ttu-id="16179-283">托管 Azure Microsoft 365 数据库 (的 Azure SQL 订阅) 必须位于同一Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="16179-283">The Microsoft 365 subscription and Azure subscription (hosting Azure SQL database) must lie within the same Azure Active Directory.</span></span>
- <span data-ttu-id="16179-284">ACL 仅支持使用用户主体名称 (UPN) 、Azure Active Directory (Azure AD) 或 Active Directory 安全性。</span><span class="sxs-lookup"><span data-stu-id="16179-284">ACLs are only supported by using a User Principal Name (UPN), Azure Active Directory (Azure AD), or Active Directory Security.</span></span>
- <span data-ttu-id="16179-285">不支持对数据库列内的丰富内容编制索引。</span><span class="sxs-lookup"><span data-stu-id="16179-285">Indexing rich content inside database columns is not supported.</span></span> <span data-ttu-id="16179-286">此类内容的示例包括作为数据库列内的链接存在的 HTML、JSON、XML、blob 和文档分析。</span><span class="sxs-lookup"><span data-stu-id="16179-286">Examples of such content are HTML, JSON, XML, blobs, and document parsings that exist as links inside the database columns.</span></span>
