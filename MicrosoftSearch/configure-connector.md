---
title: 为 Microsoft 搜索配置 Microsoft 构建的 Graph 连接器
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
description: Microsoft Graph 连接器的安装概述
ms.openlocfilehash: e97b930f627a6336cc93b3a1f33e390cae4ff0aa
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508867"
---
<!-- Previous ms.author: monaray -->

<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Microsoft Graph 连接器的安装概述 

本文介绍了 Microsoft 在 **Microsoft** [365](https://admin.microsoft.com)管理中心设置 Graph 连接器所需的基本过程。 基本过程包括以下步骤：  
<!---Add links to each section in the doc--->

1. [在 Microsoft 365 管理中心添加 Graph 连接器](#step-1-add-a-graph-connector-in-the-microsoft-365-admin-center)
2. [命名连接](#step-2-name-the-connection)
3. [配置连接设置](#step-3-configure-the-connection-settings)
4. [管理搜索权限](#step-4-manage-search-permissions)
5. [分配属性标签](#step-5-assign-property-labels)
6. [管理架构](#step-6-manage-schema)
7. [刷新设置](#step-7-refresh-settings)
8. [查看连接](#step-8-review-connection)

本文还包括有关疑难解答、限制和以下步骤的信息：

* [疑难解答](#troubleshooting)
* [限制](#limitations)
* [后续步骤](#next-steps)

> [!NOTE]
> Microsoft 的所有 Graph 连接器的安装过程都类似，但不完全相同。 **除了阅读本文之外，还请务必阅读数据源的连接器特定信息。**  

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在 Microsoft 365 管理中心中添加 Graph 连接器

完成以下步骤以配置任何 Microsoft 构建的 Graph 连接器：

1. 登录 Microsoft [365 管理中心中的管理员帐户](https://admin.microsoft.com)。

2. 在导航窗格中，选择 **"** 设置"，然后选择"搜索&**智能。** 选择 ["连接线"选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。

3. 选择 **"+** 添加"，然后从可用选项的菜单中选择你选择的数据源。

   > [!div class="mx-imgBorder"]
   > ![可用的数据源包括：ADLS Gen2、企业网站、Microsoft SQL 服务器、Azure SQL、Oracle SQL 数据库、ServiceNow、文件共享、Azure DevOps 和 MediaWiki。](media/add-connector.png)

> [!NOTE]
> 最多可以向每个租户添加 10 个 Graph 连接。

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

指定以下属性：

* Name（必选）
* 连接 ID (必需) 
* 说明 (可选) 

连接 ID 为连接器创建隐式属性。 它只能包含字母数字字符，并且最多包含 32 个字符。

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

配置连接设置的过程因数据源类型而异。 请参阅要添加到租户的数据源类型的连接器特定信息，以在安装过程中完成此步骤。  

若要了解有关连接到本地数据源的更多信息，请参阅"安装[本地数据网关"。](https://aka.ms/configuregateway)

## <a name="step-4-manage-search-permissions"></a>步骤 4：管理搜索权限

访问控制列表 (ACL) 确定组织中哪些用户可以访问每一项数据。  

某些连接器（如 [Microsoft SQL](MSSQL-connector.md) 和 Azure Data Lake Storage [Gen2）](azure-data-lake-connector.md) 在本机支持 Azure Active [Directory (Azure AD) ](https://docs.microsoft.com/azure/active-directory/) ACL。

其他连接器（ [如 ServiceNow、Azure](servicenow-connector.md) [DevOps](azure-devops-connector.md)和 [Salesforce）](salesforce-connector.md) 支持同步非 Azure AD 用户和组。  

## <a name="step-5-assign-property-labels"></a>步骤 5：分配属性标签

可以在"分配属性标签"页上将语义标签分配给源属性。 标签是 Microsoft 提供的提供语义含义的已知标记。 它们允许 Microsoft 将连接器数据集成到 Microsoft 365 体验，如增强搜索、人员卡片、智能发现等。  

下表列出了当前支持的标签及其说明。  

标签 | 说明
--- | ---  
**title** | 您希望在搜索和其他体验中显示的项目的标题
**url** | 源系统中项的目标 URL
**createdBy** | 创建项目的人的名称
**lastModifiedBy** | 最近编辑项目的人的姓名
**authors** | 参与/协作项目人员的名称
**createdDateTime** | 项目创建时间
**lastModifiedDateTime** | 最近编辑的项目何时
**fileName** | 文件项的名称
**FileExtension** | 文件项的类型，如 .pdf 或 .word

此页上的属性基于数据源预先选择，但如果有更适合特定标签的不同属性，可以更改此选择。  

标签 **标题** 是最重要的标签。 强烈建议你 **为此** 标签分配一个属性，以便连接参与结果 [群集体验](result-cluster.md)。

映射标签不正确将导致搜索体验变错。 某些标签没有为其分配属性可以。  

## <a name="step-6-manage-schema"></a>步骤 6：管理架构

### <a name="content-property"></a>Content 属性

建议从选项的下拉菜单中选择一个 **Content 属性** ，或保留默认值（如果存在）。 此属性用于内容全文索引、搜索结果页面代码段生成、 [结果群集](result-cluster.md) 参与、语言检测、HTML/文本支持、排名和相关性以及查询整理。

如果选择内容属性，则当您创建结果类型时，可以选择使用系统生成的属性 **ResultSnippet。** [](customize-results-layout.md) 此属性充当查询时从内容属性生成的动态代码段的占位符。 如果在结果类型中使用此属性，将在搜索结果中生成代码段。

### <a name="creating-aliases-for-source-properties"></a>为源属性创建别名

可以在"管理架构"页上的"别名"列下向属性添加别名。 别名是属性的友好名称，也用于查询和筛选器的创建。 它们还用于规范化来自多个连接的源属性，这样它们具有相同的名称。 这样，你可以为具有多个连接的垂直创建单个筛选器。 有关详细信息，请参阅" [自定义搜索结果"页](customize-search-page.md)。  

### <a name="search-schema-attributes"></a>搜索架构属性

您可以设置搜索架构属性来控制每个源属性的搜索功能。 搜索架构可帮助确定搜索结果页上显示的结果以及最终用户可查看和访问的信息。

搜索架构属性包括 **查询、****搜索、****检索和** 优化 **的选项**。 下表列出了 Microsoft Graph 连接器支持的每个属性并说明了其功能。

搜索架构属性 | 函数 | 示例
--- | --- | ---
SEARCH | 使属性的文本内容可搜索。 属性内容包含在全文索引中。 | 如果该属性为 **标题**，则查询 **Enterprise** 将返回任何文本或标题中包含 **单词 Enterprise** 的答案。
QUERY | 通过查询来搜索特定属性的匹配项。 然后，可以在查询中以编程方式或详细指定属性名称。 |  如果可以查询 **Title** 属性，则支持查询 **Title： Enterprise。**
检索 | 在结果类型中只能使用可检索的属性，并显示在搜索结果中。 |
优化 | 可以像在 Microsoft 搜索结果页中一样使用精简选项。 | 如果在 [连接设置过程中](custom-filters.md) 标记了精简属性，则贵组织的用户可以在搜索结果页中按 **URL** 进行筛选

对于除文件共享连接器之外的所有连接器，必须手动设置自定义类型。 若要激活每个字段的搜索功能，您需要映射到属性列表的搜索架构。 连接向导根据选择的源属性集自动选择搜索架构。 您可以通过选中搜索架构页中每个属性和属性的复选框来修改此架构。

> [!div class="mx-imgBorder"]
> ![可以通过添加或删除查询、搜索和检索功能来自定义连接器的架构。](media/manageschema.png)

### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>搜索架构设置的限制和建议

* **内容** 属性只能搜索。 在下拉列表中选中后，此属性不能 **与选项检索** 或查询 **一起使用**。

* 当搜索结果使用内容属性呈现时，会发生 **重大** 性能问题。 例如 **，ServiceNow** 知识库文章的文本 [](https://www.servicenow.com)内容字段。

* 只有标记为可检索的属性在搜索结果中呈现，并且可用于在 MRT (创建) 。

* 只能将字符串属性标记为可搜索。

> [!NOTE]
> 创建连接后， **无法** 修改架构。 为此，需要删除连接并新建一个连接。

## <a name="step-7-refresh-settings"></a>步骤 7：刷新设置

刷新间隔确定数据在数据源和 Microsoft 搜索之间同步频率。 根据数据的修改频率和修改类型，每种类型的数据源都有一组不同的最佳刷新计划。

有两种类型的刷新间隔，即完全刷新和增量刷新，但增量刷新不适用于某些数据源。

完全刷新后，无论之前进行何种爬网，搜索引擎都会处理和索引内容源中的每个项目。 完全刷新最适合以下情形：

* 检测数据的删除。
* 增量刷新发现错误，但失败。
* ACL 已修改。
* 已修改爬网规则。
* 连接架构已更新， (架构更新不受支持) 。

使用 **增量刷新**，搜索引擎只能处理自上次成功爬网后创建或修改的项目并编制索引。 因此，并非所有内容源数据都重新索引。 增量刷新最适合检测内容、元数据、权限和其他更新。

增量刷新比完全刷新快得多，因为不会处理未更改的项目。 但是，如果您选择运行增量刷新，您仍然需要定期运行完全刷新，以保持内容源和搜索索引之间的正确数据同步。

> [!div class="mx-imgBorder"]
> ![增量爬网和完全爬网间隔设置显示增量为 15 分钟，完全爬网为 1 周。](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>步骤 8：查看连接

在完成连接之前，可以检查整个配置并根据需要编辑设置。 **如果尚未阅读数据源的连接器特定信息，请务必阅读此信息。** 在 **准备好完成** 连接时，选择"完成更新"。

### <a name="confirm-if-the-connection-setup-worked"></a>确认连接设置是否有效

转到管理中心的"连接器"选项卡下的已发布连接[列表](https://admin.microsoft.com)。 若要了解如何进行更新和删除，请参阅["管理连接器"。](manage-connector.md)

## <a name="troubleshooting"></a>疑难解答
<!---Insert troubleshooting recommendations for this data source-->
读取数据源的连接器特定信息。 

> [!NOTE]
> 目前，并非所有特定于连接器的文章都包括疑难解答建议。

## <a name="limitations"></a>限制
<!---Insert limitations for this data source-->
若要了解适用于所有数据源的限制，请参阅 [Microsoft Graph 连接器](connectors-overview.md) 概述文章。

请参阅数据源的连接器特定信息，了解该特定 Graph 连接器是否应用了其他限制。

## <a name="next-steps"></a>后续步骤

发布连接后，需要自定义搜索结果页。 若要了解有关自定义搜索结果的信息，请参阅"自定义 [搜索结果"页](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)。
