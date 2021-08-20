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
ms.openlocfilehash: f80e3e1b86a120981c4dafd95715c00cd766f5e9
ms.sourcegitcommit: 17cc660ec51bea11ab65f62655584c65c84a1d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2021
ms.locfileid: "58406942"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a>Azure SQL 和 Microsoft SQL Server Graph 连接器

借助 Microsoft SQL Server 或 Azure SQL Graph 连接器，组织可以发现本地 SQL Server 数据库或托管在云中的 Azure SQL 实例中的数据库的数据，并编制索引。
该Graph连接器将指定内容索引到Microsoft 搜索。 若要使索引与源数据保持最新，它支持定期完全爬网和增量爬网。 使用这些SQL连接器，还可以限制某些用户对搜索结果的访问。

> [!NOTE]
> 阅读 [**Setup your Graph connector**](configure-connector.md)一文，了解 Graph 连接器的一般设置说明。

本文适用于配置、运行和监视 Azure SQL 和 Microsoft SQL 服务器Graph连接器。 它补充了常规安装过程，并显示了仅适用于 Azure SQL 和 Microsoft SQL 服务器Graph说明。 本文还包括有关 Microsoft [](#limitations) SQL 和 Azure SQL连接器的限制的信息。

## <a name="before-you-get-started"></a>在开始使用之前

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>仅Graph本地 (连接器所需的 Microsoft SQL Server 连接器代理) 

若要访问本地第三方数据，必须安装和配置 Graph 连接器代理。 有关详细信息[，请参阅](graph-connector-agent.md)Graph连接器代理。

>[!NOTE]
>如果在配置 Microsoft SQL Server Graph 连接器时使用 Windows 身份验证，则尝试登录的用户需要具有安装 Graph 连接器代理的计算机的交互式登录权限。 请参阅有关 [登录策略管理的文档](/windows/security/threat-protection/security-policy-settings/allow-log-on-locally#policy-management) 以检查登录权限。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在Graph中添加连接器Microsoft 365 管理中心

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

### <a name="register-an-app-for-azure-sql-connector-only"></a>仅为 Azure (连接器SQL应用) 

对于 Azure SQL 连接器，必须在 Azure Active Directory 注册应用，Microsoft 搜索访问数据进行索引。 若要了解有关注册应用的信息，请参阅 Microsoft Graph注册[应用的文档](/graph/auth-register-app-v2)。

完成应用注册并记下应用名称、应用程序 (客户端) ID 和租户 ID 后，需要生成一 [个新的客户端密码](/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret)。 客户端密码将只显示一次。 请记住，&安全存储客户端密码。 在客户端 ID 和客户端密码中配置新连接时，Microsoft 搜索。

若要将注册的应用添加到Azure SQL 数据库，你需要：

- 登录到 Azure SQL DB
- 打开新的查询窗口
- 通过运行命令"CREATE USER [app name] FROM EXTERNAL PROVIDER"创建新用户
- 通过运行命令"exec sp_addrolemember"db_datareader，[应用名称]"或"ALTER ROLE db_datareader ADD MEMBER [app name]"将用户添加到角色

>[!NOTE]
>若要撤销对在 Azure Active Directory 中注册的任何应用的访问权限，请参阅有关删除已注册应用的 Azure[文档](/azure/active-directory/develop/quickstart-remove-app)。

### <a name="connection-settings"></a>连接设置

若要将Microsoft SQL Server连接器连接到数据源，必须配置数据库服务器爬网的连接器和本地代理。 然后，您可以使用所需的身份验证方法连接到数据库。

> [!NOTE]
> - 您的数据库必须SQL Server 2008 或更高版本，Microsoft SQL Server连接器才能连接。
> - Azure SQL图形连接器仅允许从 Azure SQL实例（自 Microsoft 365 起在同一租户中）。 [](/azure/active-directory/develop/quickstart-create-new-tenant) 不支持跨租户数据流。

对于 Azure SQL 连接器，只需指定要连接到的服务器名称或 IP 地址。 Azure SQL 连接器仅Azure Active Directory打开 ID (OIDC) 身份验证连接到数据库。

为了增加安全性，你可以为 Azure 服务器或数据库SQL Server IP 防火墙规则。 若要了解有关设置 IP 防火墙规则的信息，请参阅有关 [IP 防火墙规则的文档](/azure/azure-sql/database/firewall-configure)。 在防火墙设置中添加以下客户端 IP 范围。

| 地区 | IP 范围 |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

若要搜索数据库内容，必须在配置连接器SQL指定查询。 这些SQL查询需要命名要索引的所有数据库列 (即源属性) ，包括获取所有列需要执行的任何 SQL 联接。 若要限制对搜索结果的访问，必须在配置连接器时 (在) 查询SQL访问控制列表和 ACL。

## <a name="step-3a-full-crawl-required"></a>步骤 3a：必需 (完全) 

在此步骤中，配置SQL数据库完全爬网的查询。 完全爬网将选择要选择选项"查询、搜索"或"检索"的所有列或 **属性**。  还可以指定 ACL 列以将搜索结果的访问限制到特定用户或组。

> [!Tip]
> 若要获取所需的所有列，可以联接多个表。

![显示 OrderTable 和 AclTable 以及示例属性的脚本](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Select data columns (Required) and ACL columns (Optional) 

该示例演示保存搜索数据的五个数据列的选择：OrderId、OrderTitle、OrderDesc、CreatedDateTime 和 IsDeleted。 若要设置每行数据的查看权限，可以选择以下 ACL 列：AllowedUsers、AllowedGroups、DeniedUsers 和 DeniedGroups。 所有这些数据列还具有查询、**搜索或** 检索 **的选项**。 

选择数据列，如此示例查询中所示： `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

请注意，SQL连接器不允许 SELECT 子句中具有非字母数字字符的列名。 使用别名从列名称中删除任何非字母数字字符。 示例 - SELECT *column_name* AS *columnName*

若要管理对搜索结果的访问，可以在查询中指定一个或多个 ACL 列。 利用SQL连接器，您可以控制每个记录级别的访问。 您可以选择对表中的所有记录具有相同的访问控制。 如果 ACL 信息存储在单独的表中，您可能必须执行与查询中这些表的联接。

下面介绍了上述查询中每个 ACL 列的使用。 以下列表说明了四 **种访问控制机制**。

- **AllowedUsers：** 此列指定可以访问搜索结果的用户 ID 列表。 在下面的示例中，用户列表：john@contoso.com、keith@contoso.com 和 lisa@contoso.com 只能访问 OrderId = 12 的记录。
- **AllowedGroups：** 此列指定能够访问搜索结果的一组用户。 在下面的示例中，组 sales-team@contoso.com 只能访问 OrderId = 12 的记录。
- **DeniedUsers：** 此列指定无法访问搜索结果的用户的列表。  在下面的示例中，john@contoso.com 和 keith@contoso.com 用户无法访问 OrderId = 13 的记录，而其他人则有权访问此记录。
- **DeniedGroups：** 此列指定无法访问搜索结果的一组用户。  在下面的示例中，engg-team@contoso.com 和 pm-team@contoso.com 组不能访问 OrderId = 15 的记录，而其他人则有权访问此记录。  

![显示 OrderTable 和 AclTable 的示例数据（包含示例属性）](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>支持的数据类型

下表总结了 MS SQL 连接器和 Azure SQL 支持SQL数据类型。 该表还汇总了受支持数据类型索引索引SQL 数据类型。 若要了解有关 Microsoft 连接器Graph索引支持的数据类型的信息，请参阅有关属性[资源类型的文档](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties)。

| 类别 | 源数据类型 | 索引数据类型 |
| ------------ | ------------ | ------------ |
| 日期和时间 | date <br> datetime <br> datetime2 <br> smalldatetime | datetime |
| 精确数字 | bigint <br> int <br> smallint <br> tinyint | int64 |
| 精确数字 | bit | boolean |
| 近似数值 | float <br> real | double |
| 字符串 | char <br> varchar <br> text | string |
| Unicode 字符字符串 | nchar <br> nvarchar <br> ntext | string |
| 其他数据类型 | uniqueidentifier | string |

对于当前数据类型不支持的其他任何字段，需要将列显式强制转换到受支持的数据类型。

### <a name="watermark-required"></a>水印 (必需) 

为了防止数据库过载，连接器批处理和恢复具有完全爬网水印列的完全爬网查询。 通过使用水印列的值，将提取每个后续批次，并且从最后一个检查点恢复查询。 实质上，此机制控制完全爬网的数据刷新。

为水印创建查询代码段，如以下示例所示：

- `WHERE (CreatedDateTime > @watermark)`. 使用保留的关键字 引用水印列名称 `@watermark` 。 如果水印列的排序顺序为升序，请使用 `>` ;否则，请使用 `<` 。
- `ORDER BY CreatedDateTime ASC`. 按水印列的升序或降序排序。

在下图所示的配置中，是 `CreatedDateTime` 选定的水印列。 若要提取第一批行，请数据类型列的名称。 在这种情况下，数据类型为 `DateTime` 。

![水印列配置](media/MSSQL-watermark.png)

第一个查询使用"CreatedDateTime > January 1， 1753 00：00：00" (DateTime 数据类型) 的最小值提取前 **N** 个行。 获取第一个批次后，如果行按升序排序，批处理中返回的最高级别值将另存为 `CreatedDateTime` 检查点。 例如，2019 年 3 月 1 日 03：00：00。 然后，使用查询中的"CreatedDateTime > 2019 年 3 月 1 日 03：00：00"提取下一批 **N** 行。

### <a name="skipping-soft-deleted-rows-optional"></a>跳过软删除的行 (可选) 

若要排除对数据库中的软删除行编制索引，请指定软删除列的名称和值，以指示该行已被删除。

![软删除设置："软删除列"和"指示已删除行的软删除列的值"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>完全爬网：管理搜索权限

选择 **"管理权限** "以选择各种访问控制 (ACL) 指定访问控制机制的列。 Select the column name you specified in the full crawl SQL query.

每个 ACL 列应都是一个多值列。 这些多个 ID 值可以使用分隔符分隔，如分号 (;) 、逗号 (、) 等。 需要在值分隔符字段中指定 **此分隔** 符。

支持将以下 ID 类型用作 ACL：

- **用户主体名称 (UPN) ：** 用户主体名称 (UPN) 是电子邮件地址格式的系统用户的名称。 UPN (例如：john.doe@domain.com) 由用户名 (logon name) 、separator (the @ symbol) 和 domain name (UPN suffix) 组成。
- **Azure Active Directory (AAD) ID：** 在 Azure AD 中，每个用户或组都有类似于"e0d3ad3d-0000-1111-2222-3c5f5c52ab9b"的对象 ID。
- **Active Directory (AD) 安全 ID：** 在本地 AD 设置中，每个用户和组都有一个不可变的唯一安全标识符，类似于"S-1-5-21-3878594291-2115959936-132693609-65242"。

![用于配置访问控制列表的搜索权限设置](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>步骤 3b：增量爬网 (可选) 

在此可选步骤中，提供SQL查询以运行数据库的增量爬网。 通过此查询，SQL连接器可确定自上次增量爬网以来对数据进行的任何更改。 与在完全爬网中一样，选择要选择选项"查询、搜索"或"检索"的所有 **列**。 指定在完全爬网查询中指定的同一组 ACL 列。

下图中的组件类似于完全爬网组件，但只有一个例外。 在这种情况下，"ModifiedDateTime"为选定的水印列。 查看 [完全爬网步骤](#step-3a-full-crawl-required) ，了解如何编写增量爬网查询，并查看下图作为示例。

![显示可以使用的 OrderTable、AclTable 和示例属性的增量爬网脚本。](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>步骤 4：分配属性标签

按照常规 [设置说明操作](./configure-connector.md)。

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a>步骤 5：管理架构

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a>步骤 6：管理搜索权限

可以选择使用在完全爬网 [屏幕中指定的 ACL，](#full-crawl-manage-search-permissions) 也可以覆盖它们，使内容对所有人都可见。

## <a name="step-7-choose-refresh-settings"></a>步骤 7：选择刷新设置

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a>步骤 8：查看连接

按照常规 [设置说明操作](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).-->

## <a name="troubleshooting"></a>疑难解答

以下是配置连接器时观察到的常见错误及其可能的原因。

| 配置步骤 | 错误消息 | 可能 (原因)  |
| ------------ | ------------ | ------------ |
| 完全爬网 | `Error from database server: A transport level error has occurred when receiving results from the server.` | 由于网络问题，导致出现此错误。 建议使用 Microsoft 网络监视器检查网络日志 [，](https://www.microsoft.com/download/details.aspx?id=4865) 并联系 Microsoft 客户支持。 |
| 完全爬网 | `Column column_name returned from full crawl SQL query contains non-alphanumeric character` | SELECT 子句的列名称中不允许 (非字母数字字符，) 下划线字符等。 使用别名重命名列并删除非字母数字字符 (示例 - SELECT column_name AS columnName) 。 |

## <a name="limitations"></a>限制

预览SQL连接器有以下限制：

- Microsoft SQL Server连接器：本地数据库必须运行 SQL Server 2008 或更高版本。
- 托管 Azure Microsoft 365 数据库 (的 SQL 订阅) Azure 订阅和 Azure Azure Active Directory。
- ACL 仅支持使用用户主体名称 (UPN) 、Azure Active Directory (Azure AD) 或 Active Directory 安全性。
- 不支持对数据库列内的丰富内容编制索引。 此类内容的示例包括作为数据库列内的链接存在的 HTML、JSON、XML、blob 和文档分析。
