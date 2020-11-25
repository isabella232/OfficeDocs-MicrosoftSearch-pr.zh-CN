---
title: 用于 Microsoft 搜索的 Oracle SQL 连接器
ms.author: vivg
author: Vivek
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: 设置 Oracle SQL connector for Microsoft Search。
ms.openlocfilehash: 794ba81778ae5acf30c539f78390872579ac5467
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408912"
---
# <a name="oracle-sql-connector"></a>Oracle SQL 连接器

通过 Oracle SQL 连接器，你的组织可以发现本地 Oracle 数据库中的数据并对其编制索引。 连接器将指定的内容索引到 Microsoft Search 中。 若要使索引保持对源数据的最新，它支持定期完全爬网和增量爬网。 使用 Oracle SQL 连接器，您还可以限制对特定用户的搜索结果的访问。

本文适用于 Microsoft 365 管理员或任何配置、运行和监视 Oracle SQL 连接器的人。 它说明了如何配置连接器和连接器功能、限制和故障排除技术。

## <a name="install-the-graph-connector-agent"></a>安装图形连接器代理

为了访问本地第三方数据，您必须安装和配置 Graph 连接器代理。 请参阅 [安装 Graph 连接器代理](on-prem-agent.md) 以了解详细信息。  

## <a name="connect-to-a-data-source"></a>连接到数据源

若要将 Oracle SQL 连接器连接到数据源，必须配置要爬网的数据库服务器和内部部署图形连接器代理。 然后，您可以使用所需的身份验证方法连接到数据库。

对于 Oracle SQL 连接器，您需要指定主机名、端口和服务 (数据库) 名称以及首选的身份验证方法、用户名和密码。

> [!NOTE]
> 您的数据库必须运行 Oracle 数据库版本11g 或更高版本，连接器才能够连接。 连接器支持托管在 Windows、Linux 和 Azure VM 平台上的 Oracle 数据库。

若要搜索数据库内容，您必须在配置连接器时指定 SQL 查询。 这些 SQL 查询需要将要编制索引的所有数据库列命名 (即 source properties) ，包括要获取所有列所需执行的任何 SQL 联接。 若要限制对搜索结果的访问权限，您必须在配置连接器时指定 SQL 查询中 (Acl) 的访问控制列表。

## <a name="full-crawl-required"></a>必需的完全爬网 () 

在此步骤中，将配置运行对数据库的完全爬网的 SQL 查询。 完全爬网将选择要使其成为可 **查询**、可 **搜索** 或可 **检索** 的所有列或属性。 您还可以指定 ACL 列，以限制对特定用户或组的搜索结果访问。

> [!Tip]
> 若要获取所需的所有列，可以联接多个表。

![显示带有示例属性的 OrderTable 和 AclTable 的脚本](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>选择 "数据列" (必需的) 和 ACL 列 (可选的) 

该示例演示如何选择包含用于搜索的数据的五个数据列：订单 Id、OrderTitle、OrderDesc、CreatedDateTime 和 IsDeleted。 若要设置每个数据行的查看权限，可以选择以下 ACL 列： AllowedUsers、AllowedGroups、DeniedUsers 和 DeniedGroups。 所有这些数据列都可以进行 **查询**、 **搜索** 或 **检索**。

选择数据列，如以下示例查询所示： `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

若要管理对搜索结果的访问权限，您可以指定查询中的一个或多个 ACL 列。 SQL 连接器允许您控制每个记录级别的访问权限。 您可以选择对表中的所有记录具有相同的访问控制。 如果 ACL 信息存储在单独的表中，则可能必须在查询中执行与这些表的联接。

下面介绍了上述查询中的每个 ACL 列的用法。 下面的列表介绍了4种 **访问控制机制**。

* **AllowedUsers**：此选项指定将能够访问搜索结果的用户 id 的列表。 在下面的示例中，用户列表为： john@contoso.com、keith@contoso.com 和 lisa@contoso.com 只能访问订单 Id 为12的记录。
* **AllowedGroups**：此选项指定将能够访问搜索结果的用户组。 在下面的示例中，group sales-team@contoso.com 将只有具有订单 Id = 12 的记录可供访问。
* **DeniedUsers**：此选项指定 **不** 具有对搜索结果的访问权限的用户的列表。 在以下示例中，用户 john@contoso.com 和 keith@contoso.com 无权使用订单 Id 为13的记录访问权限，而其他所有人都有权访问此记录。
* **DeniedGroups**：此选项指定 **不** 具有对搜索结果的访问权限的用户组。 在以下示例中，组 engg-team@contoso.com 和 pm-team@contoso.com 无权访问订单 Id 为15的记录，而其他人有权访问此记录。  

![显示带有示例属性的 OrderTable 和 AclTable 的示例数据](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>支持的数据类型

下表汇总了 Oracle SQL 连接器支持的数据类型。 该表还汇总了受支持的 SQL 数据类型的索引数据类型。 若要了解有关 Microsoft Graph 连接器支持编制索引的数据类型的详细信息，请参阅 [属性资源类型](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties)的文档。

| 类别 | 源数据类型 | 索引数据类型 |
| ------------ | ------------ | ------------ |
| Number datatype | 数字 (p，0)  | p <的 int64 (= 18)  <br> p > 18 的双 ()  |
| 浮点数字数据类型 | 数字 (p，s)  <br>  (p) 的 FLOAT | double |
| 日期数据类型 | 结束 <br> TIMESTAMP <br> 时间戳 (n)  | datetime |
| 字符数据类型 | CHAR (n)  <br> VARCHAR <br> VARCHAR2 <br> 大量 <br> CLOB <br> NCLOB | string |
| Unicode 字符数据类型 | NCHAR <br> NVARCHAR | string |
| RowID 数据类型 | ROWID <br> UROWID | string |

对于目前不直接支持的任何其他数据类型，需要将该列显式转换为受支持的数据类型。

### <a name="watermark-required"></a> (必需的水印) 

为了防止对数据库进行过载，连接器使用完全爬网水印列为批次批处理和恢复完全爬网查询。 通过使用 "水印" 列的值，将提取每个后续批处理，并从最后一个检查点恢复查询。 实际上，这是一种控制完全爬网的数据刷新的机制。

创建水印的查询代码段，如以下示例所示：

* `WHERE (CreatedDateTime > @watermark)`. 使用保留关键字引用水印列名称 `@watermark` 。 您只能按升序对水印列进行排序。
* `ORDER BY CreatedDateTime ASC`. 按升序对水印列进行排序。

在下图所示的配置中， `CreatedDateTime` 是选定的水印列。 若要提取第一批行，请指定水印列的数据类型。 在这种情况下，数据类型为 `DateTime` 。

![水印列配置](media/MSSQL-watermark.png)

第一个查询使用 "CreatedDateTime > 1 月1日，1753 00:00:00" (日期时间数据类型的最小值) 来提取前 **N** 行数。 在提取第一个批处理后，如果按升序对 `CreatedDateTime` 行进行排序，则在批处理中返回的最大值将保存为检查点。 例如，2019 03:00:00 至3月1日。 然后，通过使用查询中的 "CreatedDateTime > 3 月1日，2019 03:00:00" 获取下一批 **N** 行。

### <a name="skipping-soft-deleted-rows-optional"></a> (可选) 跳过软删除的行

若要在数据库中排除软删除的行的索引，请指定软删除的列名称和值，该值指示行已删除。

![软删除设置： "软删除列" 和 "软删除列的值，表示删除的行"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>完全爬网：管理搜索权限

单击 " **管理权限** " 以选择用于指定访问控制机制的各种访问控制 (ACL) 列。 选择您在完全爬网 SQL 查询中指定的列名称。

每个 ACL 列都应为多值列。 可以通过分隔符（如分号）分隔这些多个 ID 值 (; ) 、逗号 (、) 等等。 您需要在 " **值分隔符** " 字段中指定此分隔符。

支持使用以下 ID 类型作为 Acl：

* **用户主体名称 (upn)**：用户主体名称 (UPN) 是电子邮件地址格式的系统用户的名称。 UPN (例如： john.doe@domain.com) 由用户名 (登录名) 、分隔符 (@ 符号) 和域名 (UPN 后缀) 组成。
* **Azure Active Directory (AAD) ID**：在 Azure AD 中，每个用户或组都有一个对象 ID，它看起来像 "e0d3ad3d-0000-1111-2222-3c5f5c52ab9b" 这样的内容。
* **Active Directory (AD) 安全 ID**：在本地 AD 安装中，每个用户和组都具有一个不可变的唯一安全标识符，其外观类似于-1-5-21-3878594291-2115959936-132693609-65242。 '

![用于配置访问控制列表的搜索权限设置](media/MSSQL-ACL2.png)

## <a name="incremental-crawl-optional"></a>增量爬网 (可选) 

在此可选步骤中，提供用于运行数据库的增量爬网的 SQL 查询。 使用此查询，SQL 连接器可确定自上次增量爬网以来对数据所做的任何更改。 在完全爬网中，选择要使其成为可 **查询**、可 **搜索** 或可 **检索** 的所有列。 指定在完全爬网查询中指定的一组相同的 ACL 列。

下图中的组件与完全爬网组件类似，但有一个例外。 在这种情况下，"ModifiedDateTime" 是选定的水印列。 查看 [完整的爬网步骤](#full-crawl-required) ，了解如何编写增量爬网查询，并查看以下图像作为示例。

![增量爬网脚本，显示可使用的 OrderTable、AclTable 和示例属性。](media/MSSQL-incrcrawl.png)

## <a name="manage-search-permissions"></a>管理搜索权限

您可以选择使用 [完全爬网屏幕中指定的 acl](#full-crawl-manage-search-permissions) ，也可以将其覆盖以使您的内容对所有人可见。

## <a name="set-the-refresh-schedule"></a>设置刷新计划

Oracle SQL 连接器支持完全爬网和增量爬网的刷新计划。 我们建议您同时设置这两个。

完全爬网计划将查找以前同步到 Microsoft 搜索索引的已删除行以及从同步筛选器移出的任何行。 首次连接到数据库时，将运行完全爬网以同步从完全爬网查询检索到的所有行。 若要同步新行并进行更新，需要安排增量爬网。

## <a name="next-steps-customize-the-search-results-page"></a>后续步骤：自定义搜索结果页

创建您自己的纵向和结果类型，以便最终用户可以查看来自新连接的搜索结果。 如果不执行此步骤，则连接中的数据不会显示在搜索结果页上。

若要了解有关如何创建您的纵向和 MRTs 的详细信息，请参阅 [搜索结果页面自定义](customize-search-page.md)。

## <a name="limitations"></a>限制

Oracle SQL 连接器在预览版本中有以下限制：

* 本地数据库必须运行 Oracle 数据库版本11g 或更高版本。
* 仅通过使用用户主体名称 (UPN) 、Azure Active Directory (Azure AD) 或 Active Directory 安全性来支持 Acl。
* 不支持在数据库列中对多信息内容编制索引。 此类内容的示例包括 HTML、JSON、XML、blob 和文档 parsings，它们作为数据库列中的链接存在。

## <a name="troubleshooting-guide"></a>故障排除指南

下表列出了配置连接器时看到的常见错误及其可能的原因。
| 配置步骤 | 错误消息 |  (s 的可能原因)  |
| ------------ | ------------ | ------------ |
| 数据库设置 | 来自数据库服务器的错误：连接请求超时 | 主机名称无效 <br> 无法到达主机 |
| 数据库设置 | 来自数据库服务器的错误： ORA-12541： TNS：无 listner | 端口无效 |
| 数据库设置 | 来自数据库服务器的错误： ORA-12514： TNS： listner 当前不知道连接器描述符中请求的服务 | 服务 (数据库) 名称无效 |
| 数据库设置 | 来自数据库服务器的错误：用户 ' ' 登录失败 `user` 。 | 用户名或密码无效 |
