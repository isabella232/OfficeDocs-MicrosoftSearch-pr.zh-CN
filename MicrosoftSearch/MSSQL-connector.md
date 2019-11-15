---
title: Microsoft SQL connector for Microsoft Search
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 设置 Microsoft SQL connector for Microsoft Search。
ms.openlocfilehash: a073a6d3f226e5f8b0ea297494a8889f1f50bab1
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626753"
---
# <a name="microsoft-sql-server-connector"></a><span data-ttu-id="57bad-103">Microsoft SQL server 连接器</span><span class="sxs-lookup"><span data-stu-id="57bad-103">Microsoft SQL server connector</span></span>

<span data-ttu-id="57bad-104">通过 Microsoft SQL server 连接器，您的组织可以发现并索引本地 SQL Server 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="57bad-104">With a Microsoft SQL server connector, your organization can discover and index data from an on-premises SQL Server database.</span></span> <span data-ttu-id="57bad-105">连接器将指定的内容索引到 Microsoft Search 中。</span><span class="sxs-lookup"><span data-stu-id="57bad-105">The connector indexes specified content into Microsoft Search.</span></span> <span data-ttu-id="57bad-106">若要使索引保持对源数据的最新，它支持定期完全爬网和增量爬网。</span><span class="sxs-lookup"><span data-stu-id="57bad-106">To keep the index up to date with source data, it supports periodic full and incremental crawls.</span></span> <span data-ttu-id="57bad-107">使用 SQL Server 连接器，您还可以限制对特定用户的搜索结果的访问。</span><span class="sxs-lookup"><span data-stu-id="57bad-107">With the SQL Server connector, you can also restrict access to search results for certain users.</span></span>

<span data-ttu-id="57bad-108">本文适用于 Microsoft 365 管理员或任何配置、运行和监控 Microsoft SQL server 连接器的人。</span><span class="sxs-lookup"><span data-stu-id="57bad-108">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a Microsoft SQL server connector.</span></span> <span data-ttu-id="57bad-109">它说明了如何配置连接器和连接器功能、限制和故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="57bad-109">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-a-data-gateway"></a><span data-ttu-id="57bad-110">安装 data gateway</span><span class="sxs-lookup"><span data-stu-id="57bad-110">Install a data gateway</span></span>
<span data-ttu-id="57bad-111">为了访问第三方数据，您必须安装和配置 Microsoft Power BI 网关。</span><span class="sxs-lookup"><span data-stu-id="57bad-111">In order to access your third-party data, you must install and configure a Microsoft Power BI gateway.</span></span> <span data-ttu-id="57bad-112">若要了解详细信息，请参阅[Install 和本地网关](https://docs.microsoft.com/data-integration/gateway/service-gateway-install)。</span><span class="sxs-lookup"><span data-stu-id="57bad-112">See [Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) to learn more.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="57bad-113">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="57bad-113">Connect to a data source</span></span>
<span data-ttu-id="57bad-114">若要将 Microsoft SQL server 连接器连接到数据源，必须配置要爬网的数据库服务器和本地网关。</span><span class="sxs-lookup"><span data-stu-id="57bad-114">To connect your Microsoft SQL server connector to a data source, you must configure the database server you want crawled and the on-premises gateway.</span></span> <span data-ttu-id="57bad-115">然后，您可以使用所需的身份验证方法连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="57bad-115">You can then connect to the database with the required authentication method.</span></span>

> [!NOTE]
> <span data-ttu-id="57bad-116">您的数据库必须运行 SQL server 版本2008或更高版本。</span><span class="sxs-lookup"><span data-stu-id="57bad-116">Your database must run SQL server version 2008 or later.</span></span>

<span data-ttu-id="57bad-117">若要搜索数据库内容，您必须在配置连接器时指定 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="57bad-117">To search your database content, you must specify SQL queries when you configure the connector.</span></span> <span data-ttu-id="57bad-118">这些 SQL 查询需要对要编制索引的所有数据库列（即源属性）进行命名，包括要获取所有列需要执行的任何 SQL 联接。</span><span class="sxs-lookup"><span data-stu-id="57bad-118">These SQL queries need to name all the database columns that you want to index (i.e. source properties), including any SQL joins that need to be performed to get all the columns.</span></span> <span data-ttu-id="57bad-119">若要限制对搜索结果的访问权限，您必须在配置 Microsoft SQL server 连接器时指定具有 SQL 查询的访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="57bad-119">To restrict access to search results, you must specify Access Control Lists (ACLs) with SQL queries when you configure the Microsoft SQL server connector.</span></span>

## <a name="full-crawl-required"></a><span data-ttu-id="57bad-120">完全爬网（必需）</span><span class="sxs-lookup"><span data-stu-id="57bad-120">Full crawl (Required)</span></span>
<span data-ttu-id="57bad-121">在此步骤中，将配置运行对数据库的完全爬网的 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="57bad-121">In this step, you configure the SQL query that runs a full crawl of the database.</span></span> <span data-ttu-id="57bad-122">完全爬网将选择要使其成为可**查询**、可**搜索**或可**检索**的所有列或属性。</span><span class="sxs-lookup"><span data-stu-id="57bad-122">The full crawl selects all the columns or properties you want to be made **queryable**, **searchable**, or **retrievable**.</span></span> <span data-ttu-id="57bad-123">您还可以指定 ACL 列，以限制对特定用户或组的搜索结果访问。</span><span class="sxs-lookup"><span data-stu-id="57bad-123">You can also specify ACL columns to restrict access of search results to specific users or groups.</span></span>

> [!Tip]
> <span data-ttu-id="57bad-124">若要获取所需的所有列，可以联接多个表。</span><span class="sxs-lookup"><span data-stu-id="57bad-124">To get all the columns that you need, you can join multiple tables.</span></span>

![显示带有示例属性的 OrderTable 和 AclTable 的脚本](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a><span data-ttu-id="57bad-126">选择数据列（必需）和 ACL 列（可选）</span><span class="sxs-lookup"><span data-stu-id="57bad-126">Select data columns (Required) and ACL columns (Optional)</span></span>
<span data-ttu-id="57bad-127">该示例演示如何选择包含用于搜索的数据的五个数据列：订单 Id、OrderTitle、OrderDesc、CreatedDateTime 和 IsDeleted。</span><span class="sxs-lookup"><span data-stu-id="57bad-127">The example demonstrates selection of five data columns that hold the data for the search: OrderId, OrderTitle, OrderDesc, CreatedDateTime, and IsDeleted.</span></span> <span data-ttu-id="57bad-128">若要设置每个数据行的查看权限，可以选择以下 ACL 列： AllowedUsers、AllowedGroups、DeniedUsers 和 DeniedGroups。</span><span class="sxs-lookup"><span data-stu-id="57bad-128">To set view permissions for each row of data, you can optionally select these ACL columns: AllowedUsers, AllowedGroups, DeniedUsers, and DeniedGroups.</span></span> <span data-ttu-id="57bad-129">所有这些数据列都可以进行**查询**、**搜索**或**检索**。</span><span class="sxs-lookup"><span data-stu-id="57bad-129">All these data columns can be made **queryable**, **searchable**, or **retrievable**.</span></span>

<span data-ttu-id="57bad-130">选择数据列，如以下示例查询所示：`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span><span class="sxs-lookup"><span data-stu-id="57bad-130">Select data columns as shown in this example query: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span></span>

### <a name="watermark-required"></a><span data-ttu-id="57bad-131">水印（必需）</span><span class="sxs-lookup"><span data-stu-id="57bad-131">Watermark (Required)</span></span>
<span data-ttu-id="57bad-132">为了防止对数据库进行过载，连接器使用完全爬网水印列为批次批处理和恢复完全爬网查询。</span><span class="sxs-lookup"><span data-stu-id="57bad-132">To prevent overloading the database, the connector batches and resumes full-crawl queries with a full-crawl watermark column.</span></span> <span data-ttu-id="57bad-133">通过使用 "水印" 列的值，将提取每个后续批处理，并从最后一个检查点恢复查询。</span><span class="sxs-lookup"><span data-stu-id="57bad-133">By using the value of the watermark column, each subsequent batch is fetched, and querying is resumed from the last checkpoint.</span></span> <span data-ttu-id="57bad-134">实际上，这是一种控制完全爬网的数据刷新的机制。</span><span class="sxs-lookup"><span data-stu-id="57bad-134">Essentially this is a mechanism to control data refresh for full crawls.</span></span>

<span data-ttu-id="57bad-135">创建水印的查询代码段，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="57bad-135">Create query snippets for watermarks as shown in these examples:</span></span>
* <span data-ttu-id="57bad-136">`WHERE (CreatedDateTime > @watermark)`.</span><span class="sxs-lookup"><span data-stu-id="57bad-136"></span></span> <span data-ttu-id="57bad-137">使用保留关键字`@watermark`引用水印列名称。</span><span class="sxs-lookup"><span data-stu-id="57bad-137">Cite the watermark column name with the reserved keyword `@watermark`.</span></span> <span data-ttu-id="57bad-138">如果水印列的排序次序为升序，请使用`>`;否则，请`<`使用。</span><span class="sxs-lookup"><span data-stu-id="57bad-138">If the sort order of the watermark column is ascending, use `>`; otherwise, use `<`.</span></span>
* <span data-ttu-id="57bad-139">`ORDER BY CreatedDateTime ASC`.</span><span class="sxs-lookup"><span data-stu-id="57bad-139"></span></span> <span data-ttu-id="57bad-140">在 "水印" 列上按升序或降序进行排序。</span><span class="sxs-lookup"><span data-stu-id="57bad-140">Sort on the watermark column in ascending or descending order.</span></span>

<span data-ttu-id="57bad-141">在下图所示的配置中， `CreatedDateTime`是选定的水印列。</span><span class="sxs-lookup"><span data-stu-id="57bad-141">In the configuration shown in the following image, `CreatedDateTime` is the selected watermark column.</span></span> <span data-ttu-id="57bad-142">若要提取第一批行，请指定水印列的数据类型。</span><span class="sxs-lookup"><span data-stu-id="57bad-142">To fetch the first batch of rows, specify the data type of the watermark column.</span></span> <span data-ttu-id="57bad-143">在这种情况下，数据类型`DateTime`为。</span><span class="sxs-lookup"><span data-stu-id="57bad-143">In this case, the data type is `DateTime`.</span></span>

![](media/MSSQL-watermark.png)

<span data-ttu-id="57bad-144">第一个查询使用： "CreatedDateTime > 1 月1日，1753 00:00:00" （DateTime 数据类型的最小值）提取前**N**行量。</span><span class="sxs-lookup"><span data-stu-id="57bad-144">The first query fetches the first **N** amount of rows by using: "CreatedDateTime > January 1, 1753 00:00:00" (min value of DateTime data type).</span></span> <span data-ttu-id="57bad-145">在提取第一个批处理后，如果按升序对`CreatedDateTime`行进行排序，则在批处理中返回的最大值将保存为检查点。</span><span class="sxs-lookup"><span data-stu-id="57bad-145">After the first batch is fetched, the highest value of `CreatedDateTime` returned in the batch is saved as the checkpoint if the rows are sorted in ascending order.</span></span> <span data-ttu-id="57bad-146">例如，2019 03:00:00 至3月1日。</span><span class="sxs-lookup"><span data-stu-id="57bad-146">An example is March 1, 2019 03:00:00.</span></span> <span data-ttu-id="57bad-147">然后，通过使用查询中的 "CreatedDateTime > 3 月1日，2019 03:00:00" 获取下一批**N**行。</span><span class="sxs-lookup"><span data-stu-id="57bad-147">Then the next batch of **N** rows is fetched by using "CreatedDateTime > March 1, 2019 03:00:00" in the query.</span></span>

### <a name="skipping-soft-deleted-rows-optional"></a><span data-ttu-id="57bad-148">跳过软删除行（可选）</span><span class="sxs-lookup"><span data-stu-id="57bad-148">Skipping soft-deleted rows (Optional)</span></span>
<span data-ttu-id="57bad-149">若要在数据库中排除软删除的行的索引，请指定软删除的列名称和值，该值指示行已删除。</span><span class="sxs-lookup"><span data-stu-id="57bad-149">To exclude soft-deleted rows in your database from being indexed, specify the soft-delete column name and value that indicates the row is deleted.</span></span>

![软删除设置： "软删除列" 和 "软删除列的值，表示删除的行"](media/MSSQL-softdelete.png)

## <a name="incremental-crawl-optional"></a><span data-ttu-id="57bad-151">增量爬网（可选）</span><span class="sxs-lookup"><span data-stu-id="57bad-151">Incremental crawl (Optional)</span></span>
<span data-ttu-id="57bad-152">在此可选步骤中，提供用于运行数据库的增量爬网的 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="57bad-152">In this optional step, provide a SQL query to run an incremental crawl of the database.</span></span> <span data-ttu-id="57bad-153">使用此查询，Microsoft SQL server 连接器将对自上次增量爬网以来的数据进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="57bad-153">With this query, the Microsoft SQL server connector makes any changes to the data since the last incremental crawl.</span></span> <span data-ttu-id="57bad-154">在完全爬网中，选择要使其成为可**查询**、可**搜索**或可**检索**的所有列。</span><span class="sxs-lookup"><span data-stu-id="57bad-154">As in the full crawl, select all columns that you want to be made **queryable**, **searchable**, or **retrievable**.</span></span> <span data-ttu-id="57bad-155">指定在完全爬网查询中指定的一组相同的 ACL 列。</span><span class="sxs-lookup"><span data-stu-id="57bad-155">Specify the same set of ACL columns that you specified in the full crawl query.</span></span>

<span data-ttu-id="57bad-156">下图中的组件与完全爬网组件类似，但有一个例外。</span><span class="sxs-lookup"><span data-stu-id="57bad-156">The components in the following image resemble the full crawl components with one exception.</span></span> <span data-ttu-id="57bad-157">在这种情况下，"ModifiedDateTime" 是选定的水印列。</span><span class="sxs-lookup"><span data-stu-id="57bad-157">In this case, "ModifiedDateTime" is the selected watermark column.</span></span> <span data-ttu-id="57bad-158">查看[完整的爬网步骤](#full-crawl-required)，了解如何编写增量爬网查询，并查看以下图像作为示例。</span><span class="sxs-lookup"><span data-stu-id="57bad-158">Review the [full crawl steps](#full-crawl-required) to learn how to write your incremental crawl query and see the following image as an example.</span></span>

![增量爬网脚本，显示可使用的 OrderTable、AclTable 和示例属性。](media/MSSQL-incrcrawl.png)

## <a name="limitations"></a><span data-ttu-id="57bad-160">限制</span><span class="sxs-lookup"><span data-stu-id="57bad-160">Limitations</span></span>
<span data-ttu-id="57bad-161">在预览版本中，Microsoft SQL server 连接器具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="57bad-161">The Microsoft SQL server connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="57bad-162">本地数据库必须运行 SQL server 版本2008或更高版本。</span><span class="sxs-lookup"><span data-stu-id="57bad-162">The on-premises database must run SQL server version 2008 or later.</span></span>
* <span data-ttu-id="57bad-163">仅通过使用用户主体名称（UPN）、Azure Active Directory （Azure AD）或 Active Directory 安全性来支持 Acl。</span><span class="sxs-lookup"><span data-stu-id="57bad-163">ACLs are only supported by using a User Principal Name (UPN), Azure Active Directory (Azure AD), or Active Directory Security.</span></span>
* <span data-ttu-id="57bad-164">不支持在数据库列中对多信息内容编制索引。</span><span class="sxs-lookup"><span data-stu-id="57bad-164">Indexing rich content inside database columns is not supported.</span></span> <span data-ttu-id="57bad-165">此类内容的示例包括 HTML、JSON、XML、blob 和文档 parsings，它们作为数据库列中的链接存在。</span><span class="sxs-lookup"><span data-stu-id="57bad-165">Examples of such content are HTML, JSON, XML, blobs, and document parsings that exist as links inside the database columns.</span></span>

