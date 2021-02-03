---
title: 用于 Microsoft 搜索的 Oracle SQL Graph 连接器
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: 为 Microsoft 搜索设置 Oracle SQL Graph 连接器。
ms.openlocfilehash: a13c9ea71b115e84d313489214d424f77337a062
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084971"
---
<!---Previous ms.author:vivg --->

# <a name="oracle-sql-graph-connector"></a><span data-ttu-id="2f584-103">Oracle SQL Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="2f584-103">Oracle SQL Graph connector</span></span>

<span data-ttu-id="2f584-104">Oracle SQL Graph 连接器允许组织发现本地 Oracle 数据库中的数据并编制索引。</span><span class="sxs-lookup"><span data-stu-id="2f584-104">The Oracle SQL Graph connector allows your organization to discover and index data from an on-premises Oracle database.</span></span> <span data-ttu-id="2f584-105">连接器将指定内容索引到 Microsoft 搜索中。</span><span class="sxs-lookup"><span data-stu-id="2f584-105">The connector indexes specified content into Microsoft Search.</span></span> <span data-ttu-id="2f584-106">若要使索引与源数据保持最新，它支持定期完全爬网和增量爬网。</span><span class="sxs-lookup"><span data-stu-id="2f584-106">To keep the index up to date with source data, it supports periodic full and incremental crawls.</span></span> <span data-ttu-id="2f584-107">使用 Oracle SQL连接器，您还可以限制对某些用户的搜索结果的访问。</span><span class="sxs-lookup"><span data-stu-id="2f584-107">With the Oracle SQL connector, you can also restrict access to search results for certain users.</span></span>

> [!NOTE]
> <span data-ttu-id="2f584-108">阅读 [**Graph 连接器的安装程序**](configure-connector.md) 文章，了解一般的 Graph 连接器设置过程。</span><span class="sxs-lookup"><span data-stu-id="2f584-108">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="2f584-109">本文适用于配置、运行和监视 ServiceNow Graph 连接器的任何人。</span><span class="sxs-lookup"><span data-stu-id="2f584-109">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="2f584-110">它补充了常规安装过程，并显示了仅适用于 ServiceNow Graph 连接器的说明。</span><span class="sxs-lookup"><span data-stu-id="2f584-110">It supplements the general setup process, and shows instructions that apply only for the ServiceNow Graph connector.</span></span> <span data-ttu-id="2f584-111">本文还包括有关疑难[解答和](#troubleshooting)[限制的信息](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="2f584-111">This article also includes information about [Troubleshooting](#troubleshooting) and [Limitations](#limitations).</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="2f584-112">在开始使用之前</span><span class="sxs-lookup"><span data-stu-id="2f584-112">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="2f584-113">安装 Graph 连接器代理</span><span class="sxs-lookup"><span data-stu-id="2f584-113">Install the Graph connector agent</span></span>

<span data-ttu-id="2f584-114">若要访问本地第三方数据，必须安装和配置 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="2f584-114">In order to access your on-premises third-party data, you must install and configure the Graph connector agent.</span></span> <span data-ttu-id="2f584-115">请参阅 ["安装 Graph 连接器代理"](on-prem-agent.md) 了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="2f584-115">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2f584-116">步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器</span><span class="sxs-lookup"><span data-stu-id="2f584-116">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="2f584-117">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2f584-117">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="2f584-118">步骤 2：命名连接</span><span class="sxs-lookup"><span data-stu-id="2f584-118">Step 2: Name the connection</span></span>

<span data-ttu-id="2f584-119">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2f584-119">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="2f584-120">步骤 3：配置连接设置</span><span class="sxs-lookup"><span data-stu-id="2f584-120">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="2f584-121">若要将 Oracle SQL连接器连接到数据源，必须配置要数据库服务器的连接器和本地 Graph 连接器代理。</span><span class="sxs-lookup"><span data-stu-id="2f584-121">To connect your Oracle SQL connector to a data source, you must configure the database server you want crawled and the on-premises Graph connector agent.</span></span> <span data-ttu-id="2f584-122">然后，可以使用所需的身份验证方法连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="2f584-122">You can then connect to the database with the required authentication method.</span></span>

<span data-ttu-id="2f584-123">对于 Oracle SQL 连接器，您需要指定主机名、端口和服务 (数据库) 名称以及首选的身份验证方法、用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="2f584-123">For Oracle SQL connector, you need to specify the Hostname, Port and Service (database) name along with the preferred authentication method, username, and password.</span></span>

> [!NOTE]
> <span data-ttu-id="2f584-124">您的数据库必须运行 Oracle 数据库版本 11g 或更高版本，连接器才能连接。</span><span class="sxs-lookup"><span data-stu-id="2f584-124">Your database must run Oracle database version 11g or later for the connector to be able to connect.</span></span> <span data-ttu-id="2f584-125">该连接器支持在 Windows、Linux 和 Azure VM 平台上托管的 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="2f584-125">The connector supports Oracle database hosted on Windows, Linux and Azure VM platforms.</span></span>

<span data-ttu-id="2f584-126">若要搜索数据库内容，必须在配置连接器SQL指定查询。</span><span class="sxs-lookup"><span data-stu-id="2f584-126">To search your database content, you must specify SQL queries when you configure the connector.</span></span> <span data-ttu-id="2f584-127">这些SQL查询需要命名要编制索引的所有数据库列 (即源属性) ，包括获取所有列需要执行的任何 SQL 联接。</span><span class="sxs-lookup"><span data-stu-id="2f584-127">These SQL queries need to name all the database columns that you want to index (that is, source properties), including any SQL joins that need to be performed to get all the columns.</span></span> <span data-ttu-id="2f584-128">若要限制对搜索结果的访问，您必须在配置连接器 (在) 查询SQL访问控制列表和 ACL。</span><span class="sxs-lookup"><span data-stu-id="2f584-128">To restrict access to search results, you must specify Access Control Lists (ACLs) within SQL queries when you configure the connector.</span></span>

## <a name="step-3a-full-crawl-required"></a><span data-ttu-id="2f584-129">步骤 3a：完全爬网 (必需) </span><span class="sxs-lookup"><span data-stu-id="2f584-129">Step 3a: Full crawl (Required)</span></span>

<span data-ttu-id="2f584-130">在此步骤中，配置SQL数据库完全爬网的查询。</span><span class="sxs-lookup"><span data-stu-id="2f584-130">In this step, you configure the SQL query that runs a full crawl of the database.</span></span> <span data-ttu-id="2f584-131">完全爬网将选择要选择"查询"、"搜索"或"检索"选项的所有列或 **属性**。</span><span class="sxs-lookup"><span data-stu-id="2f584-131">The full crawl selects all the columns or properties where you want to select the options **Query**, **Search**, or **Retrieve**.</span></span> <span data-ttu-id="2f584-132">还可以指定 ACL 列以限制特定用户或组对搜索结果的访问。</span><span class="sxs-lookup"><span data-stu-id="2f584-132">You can also specify ACL columns to restrict access of search results to specific users or groups.</span></span>

> [!Tip]
> <span data-ttu-id="2f584-133">若要获取所需的所有列，可以联接多个表。</span><span class="sxs-lookup"><span data-stu-id="2f584-133">To get all the columns that you need, you can join multiple tables.</span></span>

![显示 OrderTable 和 AclTable 以及示例属性的脚本](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a><span data-ttu-id="2f584-135">Select data columns (Required) and ACL columns (Optional) </span><span class="sxs-lookup"><span data-stu-id="2f584-135">Select data columns (Required) and ACL columns (Optional)</span></span>

<span data-ttu-id="2f584-136">该示例演示了五个数据列的选择，这些列保存了搜索的数据：OrderId、OrderTitle、OrderDesc、CreatedDateTime 和 IsDeleted。</span><span class="sxs-lookup"><span data-stu-id="2f584-136">The example demonstrates selection of five data columns that hold the data for the search: OrderId, OrderTitle, OrderDesc, CreatedDateTime, and IsDeleted.</span></span> <span data-ttu-id="2f584-137">若要设置每行数据的查看权限，可以选择以下 ACL 列：AllowedUsers、AllowedGroups、DeniedUsers 和 DeniedGroups。</span><span class="sxs-lookup"><span data-stu-id="2f584-137">To set view permissions for each row of data, you can optionally select these ACL columns: AllowedUsers, AllowedGroups, DeniedUsers, and DeniedGroups.</span></span> <span data-ttu-id="2f584-138">对于所有这些数据列，可以选择"查询"、"搜索"**或**"检索"**选项**。</span><span class="sxs-lookup"><span data-stu-id="2f584-138">For all these data columns you can select the options to **Query**, **Search**, or **Retrieve**.</span></span>

<span data-ttu-id="2f584-139">选择数据列，如此示例查询所示： `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span><span class="sxs-lookup"><span data-stu-id="2f584-139">Select data columns as shown in this example query: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span></span>

<span data-ttu-id="2f584-140">若要管理对搜索结果的访问，可以在查询中指定一个或多个 ACL 列。</span><span class="sxs-lookup"><span data-stu-id="2f584-140">To manage access to the search results, you can specify one or more ACL columns in the query.</span></span> <span data-ttu-id="2f584-141">利用SQL连接器，您可以控制每个记录级别的访问。</span><span class="sxs-lookup"><span data-stu-id="2f584-141">The SQL connector allows you to control access at per record level.</span></span> <span data-ttu-id="2f584-142">您可以选择对表中的所有记录具有相同的访问控制。</span><span class="sxs-lookup"><span data-stu-id="2f584-142">You can choose to have the same access control for all records in a table.</span></span> <span data-ttu-id="2f584-143">如果 ACL 信息存储在单独的表中，您可能需要在查询中与这些表进行联接。</span><span class="sxs-lookup"><span data-stu-id="2f584-143">If the ACL information is stored in a separate table, you might have to do a join with those tables in your query.</span></span>

<span data-ttu-id="2f584-144">下面介绍了上述查询中每个 ACL 列的使用。</span><span class="sxs-lookup"><span data-stu-id="2f584-144">The use of each of the ACL columns in the above query is described below.</span></span> <span data-ttu-id="2f584-145">以下列表说明了四 **种访问控制机制**。</span><span class="sxs-lookup"><span data-stu-id="2f584-145">The following list explains the four **access control mechanisms**.</span></span>

* <span data-ttu-id="2f584-146">**AllowedUsers：** 此选项指定能够访问搜索结果的用户 ID 列表。</span><span class="sxs-lookup"><span data-stu-id="2f584-146">**AllowedUsers**: This option specifies the list of user IDs who will be able to access the search results.</span></span> <span data-ttu-id="2f584-147">在下面的示例中，用户列表：john@contoso.com、keith@contoso.com 和 lisa@contoso.com 只能访问 OrderId = 12 的记录。</span><span class="sxs-lookup"><span data-stu-id="2f584-147">In the following example, list of users: john@contoso.com, keith@contoso.com, and lisa@contoso.com would only have access to a record with OrderId = 12.</span></span>
* <span data-ttu-id="2f584-148">**AllowedGroups：** 此选项指定能够访问搜索结果的一组用户。</span><span class="sxs-lookup"><span data-stu-id="2f584-148">**AllowedGroups**: This option specifies the group of users who will be able to access the search results.</span></span> <span data-ttu-id="2f584-149">在下面的示例中，组sales-team@contoso.com只能访问 OrderId = 12 的记录。</span><span class="sxs-lookup"><span data-stu-id="2f584-149">In the following example, group sales-team@contoso.com would only have access to record with OrderId = 12.</span></span>
* <span data-ttu-id="2f584-150">**DeniedUsers：** 此选项指定无法访问搜索结果的用户的列表。 </span><span class="sxs-lookup"><span data-stu-id="2f584-150">**DeniedUsers**: This option specifies the list of users who do **not** have access to the search results.</span></span> <span data-ttu-id="2f584-151">在下面的示例中，john@contoso.com和keith@contoso.com用户无法访问 OrderId = 13 的记录，而其他人则有权访问此记录。</span><span class="sxs-lookup"><span data-stu-id="2f584-151">In the following example, users john@contoso.com and keith@contoso.com do not have access to record with OrderId = 13, whereas everyone else has access to this record.</span></span>
* <span data-ttu-id="2f584-152">**DeniedGroups**：此选项指定对搜索结果没有访问权限的一组用户。</span><span class="sxs-lookup"><span data-stu-id="2f584-152">**DeniedGroups**: This option specifies the group of users who do **not** have access to the search results.</span></span> <span data-ttu-id="2f584-153">在下面的示例中，engg-team@contoso.com组pm-team@contoso.com组不能访问 OrderId = 15 的记录，而其他人则有权访问此记录。</span><span class="sxs-lookup"><span data-stu-id="2f584-153">In the following example, groups engg-team@contoso.com and pm-team@contoso.com do not have access to record with OrderId = 15, whereas everyone else has access to this record.</span></span>  

![显示 OrderTable 和 AclTable 的示例数据以及示例属性](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a><span data-ttu-id="2f584-155">支持的数据类型</span><span class="sxs-lookup"><span data-stu-id="2f584-155">Supported data types</span></span>

<span data-ttu-id="2f584-156">下表汇总了 Oracle 连接器支持的SQL类型。</span><span class="sxs-lookup"><span data-stu-id="2f584-156">The below table summarizes the data types that are supported by the Oracle SQL connector.</span></span> <span data-ttu-id="2f584-157">该表还汇总了受支持数据类型索引索引SQL 数据类型。</span><span class="sxs-lookup"><span data-stu-id="2f584-157">The table also summarizes the indexing data type for the supported SQL data type.</span></span> <span data-ttu-id="2f584-158">若要了解有关 Microsoft Graph 连接器支持的索引数据类型，请参阅有关属性资源 [类型的文档](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="2f584-158">To learn more about Microsoft Graph connectors supported data types for indexing, refer documentation on [property resource types](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true).</span></span>

| <span data-ttu-id="2f584-159">类别</span><span class="sxs-lookup"><span data-stu-id="2f584-159">Category</span></span> | <span data-ttu-id="2f584-160">源数据类型</span><span class="sxs-lookup"><span data-stu-id="2f584-160">Source data type</span></span> | <span data-ttu-id="2f584-161">索引数据类型</span><span class="sxs-lookup"><span data-stu-id="2f584-161">Indexing data type</span></span> |
| ------------ | ------------ | ------------ |
| <span data-ttu-id="2f584-162">数字数据类型</span><span class="sxs-lookup"><span data-stu-id="2f584-162">Number datatype</span></span> | <span data-ttu-id="2f584-163">NUMBER (p，0) </span><span class="sxs-lookup"><span data-stu-id="2f584-163">NUMBER(p,0)</span></span> | <span data-ttu-id="2f584-164">int64 (p <= 18) </span><span class="sxs-lookup"><span data-stu-id="2f584-164">int64 (for p <= 18)</span></span> <br> <span data-ttu-id="2f584-165">p (18 >的双精度) </span><span class="sxs-lookup"><span data-stu-id="2f584-165">double (for p > 18)</span></span> |
| <span data-ttu-id="2f584-166">浮点数数据类型</span><span class="sxs-lookup"><span data-stu-id="2f584-166">Floating-point number datatype</span></span> | <span data-ttu-id="2f584-167">NUMBER (p，s) </span><span class="sxs-lookup"><span data-stu-id="2f584-167">NUMBER(p,s)</span></span> <br> <span data-ttu-id="2f584-168">FLOAT (p) </span><span class="sxs-lookup"><span data-stu-id="2f584-168">FLOAT(p)</span></span> | <span data-ttu-id="2f584-169">double</span><span class="sxs-lookup"><span data-stu-id="2f584-169">double</span></span> |
| <span data-ttu-id="2f584-170">日期数据类型</span><span class="sxs-lookup"><span data-stu-id="2f584-170">Date datatype</span></span> | <span data-ttu-id="2f584-171">DATE</span><span class="sxs-lookup"><span data-stu-id="2f584-171">DATE</span></span> <br> <span data-ttu-id="2f584-172">TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="2f584-172">TIMESTAMP</span></span> <br> <span data-ttu-id="2f584-173">TIMESTAMP (n) </span><span class="sxs-lookup"><span data-stu-id="2f584-173">TIMESTAMP(n)</span></span> | <span data-ttu-id="2f584-174">datetime</span><span class="sxs-lookup"><span data-stu-id="2f584-174">datetime</span></span> |
| <span data-ttu-id="2f584-175">字符数据类型</span><span class="sxs-lookup"><span data-stu-id="2f584-175">Character datatype</span></span> | <span data-ttu-id="2f584-176">CHAR (n) </span><span class="sxs-lookup"><span data-stu-id="2f584-176">CHAR(n)</span></span> <br> <span data-ttu-id="2f584-177">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="2f584-177">VARCHAR</span></span> <br> <span data-ttu-id="2f584-178">VARCHAR2</span><span class="sxs-lookup"><span data-stu-id="2f584-178">VARCHAR2</span></span> <br> <span data-ttu-id="2f584-179">LONG</span><span class="sxs-lookup"><span data-stu-id="2f584-179">LONG</span></span> <br> <span data-ttu-id="2f584-180">一些</span><span class="sxs-lookup"><span data-stu-id="2f584-180">CLOB</span></span> <br> <span data-ttu-id="2f584-181">NCLOB</span><span class="sxs-lookup"><span data-stu-id="2f584-181">NCLOB</span></span> | <span data-ttu-id="2f584-182">string</span><span class="sxs-lookup"><span data-stu-id="2f584-182">string</span></span> |
| <span data-ttu-id="2f584-183">Unicode 字符数据类型</span><span class="sxs-lookup"><span data-stu-id="2f584-183">Unicode character datatype</span></span> | <span data-ttu-id="2f584-184">NCHAR</span><span class="sxs-lookup"><span data-stu-id="2f584-184">NCHAR</span></span> <br> <span data-ttu-id="2f584-185">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="2f584-185">NVARCHAR</span></span> | <span data-ttu-id="2f584-186">string</span><span class="sxs-lookup"><span data-stu-id="2f584-186">string</span></span> |
| <span data-ttu-id="2f584-187">RowID 数据类型</span><span class="sxs-lookup"><span data-stu-id="2f584-187">RowID datatype</span></span> | <span data-ttu-id="2f584-188">ROWID</span><span class="sxs-lookup"><span data-stu-id="2f584-188">ROWID</span></span> <br> <span data-ttu-id="2f584-189">UROWID</span><span class="sxs-lookup"><span data-stu-id="2f584-189">UROWID</span></span> | <span data-ttu-id="2f584-190">string</span><span class="sxs-lookup"><span data-stu-id="2f584-190">string</span></span> |

<span data-ttu-id="2f584-191">对于当前数据类型不支持的其他任何字段，需要将列显式强制转换到受支持的数据类型。</span><span class="sxs-lookup"><span data-stu-id="2f584-191">For any other data type currently not directly supported, the column needs to be explicitly cast to a supported data type.</span></span>

### <a name="watermark-required"></a><span data-ttu-id="2f584-192">需要 (水印) </span><span class="sxs-lookup"><span data-stu-id="2f584-192">Watermark (Required)</span></span>

<span data-ttu-id="2f584-193">为了防止数据库过载，连接器批处理和恢复具有完全爬网水印列的完全爬网查询。</span><span class="sxs-lookup"><span data-stu-id="2f584-193">To prevent overloading the database, the connector batches and resumes full-crawl queries with a full-crawl watermark column.</span></span> <span data-ttu-id="2f584-194">通过使用水印列的值，将提取每个后续批次，并且从最后一个检查点恢复查询。</span><span class="sxs-lookup"><span data-stu-id="2f584-194">By using the value of the watermark column, each subsequent batch is fetched, and querying is resumed from the last checkpoint.</span></span> <span data-ttu-id="2f584-195">实质上，这是一种用于控制完全爬网的数据刷新的机制。</span><span class="sxs-lookup"><span data-stu-id="2f584-195">Essentially this is a mechanism to control data refresh for full crawls.</span></span>

<span data-ttu-id="2f584-196">为水印创建查询代码段，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="2f584-196">Create query snippets for watermarks as shown in these examples:</span></span>

* <span data-ttu-id="2f584-197">`WHERE (CreatedDateTime > @watermark)`.</span><span class="sxs-lookup"><span data-stu-id="2f584-197">`WHERE (CreatedDateTime > @watermark)`.</span></span> <span data-ttu-id="2f584-198">使用保留的关键字引用水印列名称 `@watermark` 。</span><span class="sxs-lookup"><span data-stu-id="2f584-198">Cite the watermark column name with the reserved keyword `@watermark`.</span></span> <span data-ttu-id="2f584-199">只能按升序对水印列进行排序。</span><span class="sxs-lookup"><span data-stu-id="2f584-199">You can only sort the watermark column in ascending order.</span></span>
* <span data-ttu-id="2f584-200">`ORDER BY CreatedDateTime ASC`.</span><span class="sxs-lookup"><span data-stu-id="2f584-200">`ORDER BY CreatedDateTime ASC`.</span></span> <span data-ttu-id="2f584-201">按升序对水印列进行排序。</span><span class="sxs-lookup"><span data-stu-id="2f584-201">Sort on the watermark column in ascending order.</span></span>

<span data-ttu-id="2f584-202">在下图所示的配置中，是 `CreatedDateTime` 选定的水印列。</span><span class="sxs-lookup"><span data-stu-id="2f584-202">In the configuration shown in the following image, `CreatedDateTime` is the selected watermark column.</span></span> <span data-ttu-id="2f584-203">若要获取第一批行，请数据类型列的名称。</span><span class="sxs-lookup"><span data-stu-id="2f584-203">To fetch the first batch of rows, specify the data type of the watermark column.</span></span> <span data-ttu-id="2f584-204">在这种情况下，数据类型 `DateTime` 为 。</span><span class="sxs-lookup"><span data-stu-id="2f584-204">In this case, the data type is `DateTime`.</span></span>

![水印列配置](media/MSSQL-watermark.png)

<span data-ttu-id="2f584-206">第一个查询使用："CreatedDateTime > January 1， 1753 00：00：00" (DateTime 数据类型) 的最小值。 </span><span class="sxs-lookup"><span data-stu-id="2f584-206">The first query fetches the first **N** number of rows by using: "CreatedDateTime > January 1, 1753 00:00:00" (min value of DateTime data type).</span></span> <span data-ttu-id="2f584-207">获取第一个批次后，如果行按升序排序，批处理中返回的最高值将另存为 `CreatedDateTime` 检查点。</span><span class="sxs-lookup"><span data-stu-id="2f584-207">After the first batch is fetched, the highest value of `CreatedDateTime` returned in the batch is saved as the checkpoint if the rows are sorted in ascending order.</span></span> <span data-ttu-id="2f584-208">例如，2019 年 3 月 1 日 03：00：00。</span><span class="sxs-lookup"><span data-stu-id="2f584-208">An example is March 1, 2019 03:00:00.</span></span> <span data-ttu-id="2f584-209">然后，使用查询中的"CreatedDateTime > 2019 年 3 月 1 日 03：00：00"获取下一批 **N** 行。</span><span class="sxs-lookup"><span data-stu-id="2f584-209">Then the next batch of **N** rows is fetched by using "CreatedDateTime > March 1, 2019 03:00:00" in the query.</span></span>

### <a name="skipping-soft-deleted-rows-optional"></a><span data-ttu-id="2f584-210">跳过软删除的行 (可选) </span><span class="sxs-lookup"><span data-stu-id="2f584-210">Skipping soft-deleted rows (Optional)</span></span>

<span data-ttu-id="2f584-211">若要将数据库中软删除的行排除在索引中，请指定软删除列名称和值，以指示该行已被删除。</span><span class="sxs-lookup"><span data-stu-id="2f584-211">To exclude soft-deleted rows in your database from being indexed, specify the soft-delete column name and value that indicates the row is deleted.</span></span>

![软删除设置："软删除列"和"指示已删除行的软删除列的值"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a><span data-ttu-id="2f584-213">完全爬网：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="2f584-213">Full crawl: Manage search permissions</span></span>

<span data-ttu-id="2f584-214">选择 **"管理权限** "，选择指定访问控制机制 (ACL) 中的各种访问控制。</span><span class="sxs-lookup"><span data-stu-id="2f584-214">Select **Manage permissions** to choose the various access control (ACL) columns that specify the access control mechanism.</span></span> <span data-ttu-id="2f584-215">Select the column name you specified in the full crawl SQL query.</span><span class="sxs-lookup"><span data-stu-id="2f584-215">Select the column name you specified in the full crawl SQL query.</span></span>

<span data-ttu-id="2f584-216">每个 ACL 列应都是一个多值列。</span><span class="sxs-lookup"><span data-stu-id="2f584-216">Each of the ACL columns is expected to be a multi-valued column.</span></span> <span data-ttu-id="2f584-217">这些多个 ID 值可以使用分隔符（如分号 (;) 、逗号 (、) 等）分隔。</span><span class="sxs-lookup"><span data-stu-id="2f584-217">These multiple ID values can be separated by separators such as semicolon (;), comma (,), and so on.</span></span> <span data-ttu-id="2f584-218">需要在值分隔符字段中指定 **此分隔** 符。</span><span class="sxs-lookup"><span data-stu-id="2f584-218">You need to specify this separator in the **value separator** field.</span></span>

<span data-ttu-id="2f584-219">支持将以下 ID 类型用作 ACL：</span><span class="sxs-lookup"><span data-stu-id="2f584-219">The following ID types are supported for using as ACLs:</span></span>

* <span data-ttu-id="2f584-220">**用户主体名称 (UPN) ：** 用户主体名称 (UPN) 是电子邮件地址格式的系统用户的名称。</span><span class="sxs-lookup"><span data-stu-id="2f584-220">**User Principal Name (UPN)**: A User Principal Name (UPN) is the name of a system user in an email address format.</span></span> <span data-ttu-id="2f584-221">例如，UPN (：john.doe@domain.com) 包含用户名 (登录名) 、 (@ 符号) 分隔符和域名 (UPN 后缀) 。</span><span class="sxs-lookup"><span data-stu-id="2f584-221">A UPN (for example: john.doe@domain.com) consists of the username (logon name), separator (the @ symbol), and domain name (UPN suffix).</span></span>
* <span data-ttu-id="2f584-222">**Azure Active Directory (AAD) ID：** 在 Azure AD 中，每个用户或组都有类似于"e0d3ad3d-0000-1111-2222-3c5f5c52ab9b"的对象 ID</span><span class="sxs-lookup"><span data-stu-id="2f584-222">**Azure Active Directory (AAD) ID**: In Azure AD, every user or group has an object ID that looks something like ‘e0d3ad3d-0000-1111-2222-3c5f5c52ab9b’</span></span>
* <span data-ttu-id="2f584-223">**Active Directory (AD)** 安全 ID：在本地 AD 设置中，每个用户和组都有一个不可变的唯一安全标识符，类似于"S-1-5-21-3878594291-2115959936-132693609-65242"。</span><span class="sxs-lookup"><span data-stu-id="2f584-223">**Active Directory (AD) Security ID**: In an on-premises AD setup, every user and group have an immutable, unique security identifier that looks something like ‘S-1-5-21-3878594291-2115959936-132693609-65242.’</span></span>

![用于配置访问控制列表的搜索权限设置](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a><span data-ttu-id="2f584-225">步骤 3b：增量爬网 (可选) </span><span class="sxs-lookup"><span data-stu-id="2f584-225">Step 3b: Incremental crawl (Optional)</span></span>

<span data-ttu-id="2f584-226">在此可选步骤中，提供SQL查询以运行数据库的增量爬网。</span><span class="sxs-lookup"><span data-stu-id="2f584-226">In this optional step, provide a SQL query to run an incremental crawl of the database.</span></span> <span data-ttu-id="2f584-227">通过此查询，SQL连接器可确定自上次增量爬网以来对数据的任何更改。</span><span class="sxs-lookup"><span data-stu-id="2f584-227">With this query, the SQL connector determines any changes to the data since the last incremental crawl.</span></span> <span data-ttu-id="2f584-228">与在完全爬网中一样，选择"查询、**搜索"** 或"检索"**选项**。</span><span class="sxs-lookup"><span data-stu-id="2f584-228">As in the full crawl, select between the options **Query**, **Search**, or **Retrieve**.</span></span> <span data-ttu-id="2f584-229">指定在完全爬网查询中指定的同一组 ACL 列。</span><span class="sxs-lookup"><span data-stu-id="2f584-229">Specify the same set of ACL columns that you specified in the full crawl query.</span></span>

<span data-ttu-id="2f584-230">下图中的组件类似于完全爬网组件，但出现一个异常。</span><span class="sxs-lookup"><span data-stu-id="2f584-230">The components in the following image resemble the full crawl components with one exception.</span></span> <span data-ttu-id="2f584-231">在这种情况下，"ModifiedDateTime"是选定的水印列。</span><span class="sxs-lookup"><span data-stu-id="2f584-231">In this case, "ModifiedDateTime" is the selected watermark column.</span></span> <span data-ttu-id="2f584-232">查看 [完全爬网步骤](#step-3a-full-crawl-required) ，了解如何编写增量爬网查询，并查看下图作为示例。</span><span class="sxs-lookup"><span data-stu-id="2f584-232">Review the [full crawl steps](#step-3a-full-crawl-required) to learn how to write your incremental crawl query and see the following image as an example.</span></span>

![显示可以使用的 OrderTable、AclTable 和示例属性的增量爬网脚本。](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="2f584-234">步骤 4：分配属性标签</span><span class="sxs-lookup"><span data-stu-id="2f584-234">Step 4: Assign property labels</span></span>

<span data-ttu-id="2f584-235">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2f584-235">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-5-manage-schema"></a><span data-ttu-id="2f584-236">步骤 5：管理架构</span><span class="sxs-lookup"><span data-stu-id="2f584-236">Step 5: Manage schema</span></span>

<span data-ttu-id="2f584-237">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2f584-237">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="2f584-238">步骤 6：管理搜索权限</span><span class="sxs-lookup"><span data-stu-id="2f584-238">Step 6: Manage search permissions</span></span>

<span data-ttu-id="2f584-239">可以选择使用在完全爬网 [屏幕中指定的 ACL，](#full-crawl-manage-search-permissions) 也可以替代它们，使内容对所有人都可见。</span><span class="sxs-lookup"><span data-stu-id="2f584-239">You can choose to use the [ACLs specified in the full crawl screen](#full-crawl-manage-search-permissions) or you can override them to make your content visible to everyone.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="2f584-240">步骤 7：选择刷新设置</span><span class="sxs-lookup"><span data-stu-id="2f584-240">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="2f584-241">Oracle SQL 连接器支持完全爬网和增量爬网的刷新计划。</span><span class="sxs-lookup"><span data-stu-id="2f584-241">The Oracle SQL connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="2f584-242">我们建议您同时设置这两者。</span><span class="sxs-lookup"><span data-stu-id="2f584-242">We recommend that you set both.</span></span>

<span data-ttu-id="2f584-243">完全爬网计划可查找以前同步到 Microsoft 搜索索引的已删除行和从同步筛选器中移动的任何行。</span><span class="sxs-lookup"><span data-stu-id="2f584-243">A full crawl schedule finds deleted rows that were previously synced to the Microsoft Search index and any rows that moved out of the sync filter.</span></span> <span data-ttu-id="2f584-244">首次连接到数据库时，将运行完全爬网以同步从完全爬网查询检索到的所有行。</span><span class="sxs-lookup"><span data-stu-id="2f584-244">When you first connect to the database, a full crawl runs to sync all the rows retrieved from the full crawl query.</span></span> <span data-ttu-id="2f584-245">若要同步新行并进行更新，您需要计划增量爬网。</span><span class="sxs-lookup"><span data-stu-id="2f584-245">To sync new rows and make updates, you need to schedule incremental crawls.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="2f584-246">步骤 8：查看连接</span><span class="sxs-lookup"><span data-stu-id="2f584-246">Step 8: Review connection</span></span>

<span data-ttu-id="2f584-247">按照常规 [设置说明操作](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2f584-247">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="next-steps-customize-the-search-results-page"></a><span data-ttu-id="2f584-248">下一步：自定义搜索结果页面</span><span class="sxs-lookup"><span data-stu-id="2f584-248">Next steps: Customize the search results page</span></span>

<span data-ttu-id="2f584-249">创建自己的垂直和结果类型，以便最终用户可以从新连接查看搜索结果。</span><span class="sxs-lookup"><span data-stu-id="2f584-249">Create your own verticals and result types, so end users can view search results from new connections.</span></span> <span data-ttu-id="2f584-250">如果不执行此步骤，连接数据将不会显示在搜索结果页上。</span><span class="sxs-lookup"><span data-stu-id="2f584-250">Without this step, data from your connection won’t show up on the search results page.</span></span>

<span data-ttu-id="2f584-251">若要详细了解如何创建垂直和 MRT，请参阅 [搜索结果页面自定义](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2f584-251">To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2f584-252">故障排除</span><span class="sxs-lookup"><span data-stu-id="2f584-252">Troubleshooting</span></span>

<span data-ttu-id="2f584-253">下面列出了配置连接器时观察到的常见错误及其可能的原因。</span><span class="sxs-lookup"><span data-stu-id="2f584-253">Underneath is a list of common errors observed while configuring the connector and their possible reasons.</span></span>

| <span data-ttu-id="2f584-254">配置步骤</span><span class="sxs-lookup"><span data-stu-id="2f584-254">Configuration step</span></span> | <span data-ttu-id="2f584-255">错误消息</span><span class="sxs-lookup"><span data-stu-id="2f584-255">Error message</span></span> | <span data-ttu-id="2f584-256">可能 (原因) </span><span class="sxs-lookup"><span data-stu-id="2f584-256">Possible reason(s)</span></span> |
| ------------ | ------------ | ------------ |
| <span data-ttu-id="2f584-257">数据库设置</span><span class="sxs-lookup"><span data-stu-id="2f584-257">Database settings</span></span> | <span data-ttu-id="2f584-258">错误数据库服务器：连接请求已退出</span><span class="sxs-lookup"><span data-stu-id="2f584-258">Error from database server: Connection request timed out</span></span> | <span data-ttu-id="2f584-259">主机名无效</span><span class="sxs-lookup"><span data-stu-id="2f584-259">Invalid Hostname</span></span> <br> <span data-ttu-id="2f584-260">主机不可到达</span><span class="sxs-lookup"><span data-stu-id="2f584-260">Host not reachable</span></span> |
| <span data-ttu-id="2f584-261">数据库设置</span><span class="sxs-lookup"><span data-stu-id="2f584-261">Database settings</span></span> | <span data-ttu-id="2f584-262">错误来自数据库服务器：ORA-12541：TNS：无侦听器</span><span class="sxs-lookup"><span data-stu-id="2f584-262">Error from database server: ORA-12541: TNS: No listener</span></span> | <span data-ttu-id="2f584-263">无效的端口</span><span class="sxs-lookup"><span data-stu-id="2f584-263">Invalid Port</span></span> |
| <span data-ttu-id="2f584-264">数据库设置</span><span class="sxs-lookup"><span data-stu-id="2f584-264">Database settings</span></span> | <span data-ttu-id="2f584-265">来自 数据库服务器 的错误：ORA-12514：TNS：侦听器当前不知道连接器描述符中请求的服务</span><span class="sxs-lookup"><span data-stu-id="2f584-265">Error from database server: ORA-12514: TNS: listener does not currently know of service requested in connector descriptor</span></span> | <span data-ttu-id="2f584-266">无效的服务 (数据库) 名称</span><span class="sxs-lookup"><span data-stu-id="2f584-266">Invalid service (database) name</span></span> |
| <span data-ttu-id="2f584-267">数据库设置</span><span class="sxs-lookup"><span data-stu-id="2f584-267">Database settings</span></span> | <span data-ttu-id="2f584-268">错误来自数据库服务器：用户''登录 `user` 失败。</span><span class="sxs-lookup"><span data-stu-id="2f584-268">Error from database server: Login failed for user '`user`'.</span></span> | <span data-ttu-id="2f584-269">用户名或密码无效</span><span class="sxs-lookup"><span data-stu-id="2f584-269">Invalid username or password</span></span> |

## <a name="limitations"></a><span data-ttu-id="2f584-270">限制</span><span class="sxs-lookup"><span data-stu-id="2f584-270">Limitations</span></span>

<span data-ttu-id="2f584-271">Oracle SQL 连接器在预览版本中有以下限制：</span><span class="sxs-lookup"><span data-stu-id="2f584-271">The Oracle SQL connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="2f584-272">内部部署数据库必须运行 Oracle 数据库版本 11g 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2f584-272">The on-premises database must run Oracle Database version 11g or later.</span></span>
* <span data-ttu-id="2f584-273">ACL 仅支持通过使用用户主体名称 (UPN) 、Azure Active Directory (Azure AD) 或 Active Directory 安全性。</span><span class="sxs-lookup"><span data-stu-id="2f584-273">ACLs are only supported by using a User Principal Name (UPN), Azure Active Directory (Azure AD), or Active Directory Security.</span></span>
* <span data-ttu-id="2f584-274">不支持对数据库列内的丰富内容编制索引。</span><span class="sxs-lookup"><span data-stu-id="2f584-274">Indexing rich content inside database columns is not supported.</span></span> <span data-ttu-id="2f584-275">此类内容的示例包括作为数据库列内的链接存在的 HTML、JSON、XML、blob 和文档分析。</span><span class="sxs-lookup"><span data-stu-id="2f584-275">Examples of such content are HTML, JSON, XML, blobs, and document parsings that exist as links inside the database columns.</span></span>
