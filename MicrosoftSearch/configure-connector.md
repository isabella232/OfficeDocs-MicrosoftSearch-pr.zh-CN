---
title: 配置 Microsoft 为 Microsoft 搜索Graph连接器
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
description: Microsoft Graph连接器的设置概述
ms.openlocfilehash: ef94d530af63d8b8b33dfae3c4b411164ef31feb
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720940"
---
<!-- Previous ms.author: monaray -->

<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Microsoft Graph连接器的设置概述 

本文介绍了在管理中心中Graph **Microsoft** 设置 Microsoft 365 [连接器所需的基本过程](https://admin.microsoft.com)。 基本流程包括以下步骤:  
<!---Add links to each section in the doc--->

1. [在 Graph 管理中心Microsoft 365连接器](#step-1-add-a-graph-connector-in-the-microsoft-365-admin-center)
2. [命名连接](#step-2-name-the-connection)
3. [配置连接设置](#step-3-configure-the-connection-settings)
4. [管理搜索权限](#step-4-manage-search-permissions)
5. [分配属性标签](#step-5-assign-property-labels)
6. [管理架构](#step-6-manage-schema)
7. [刷新设置](#step-7-refresh-settings)
8. [查看连接](#step-8-review-connection)

本文还包括有关疑难解答、限制和下一步步骤的信息：

* [疑难解答](#troubleshooting)
* [限制](#limitations)
* [后续步骤](#next-steps)

> [!NOTE]
> Microsoft 的所有连接器的安装过程Graph类似，但不完全相同。 **除了阅读本文之外，还请务必阅读数据源的连接器特定信息。**  

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>步骤 1：在Graph管理中心中添加Microsoft 365连接器

完成以下步骤以配置任何 Microsoft 构建Graph连接器：

1. 在管理中心 中Microsoft 365[管理员帐户](https://admin.microsoft.com)。

2. 在导航窗格中，**选择**"设置"，然后选择"搜索&**智能"。** 选择" [连接器"选项卡](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。

3. 选择 **"+** 添加"，然后从可用选项的菜单中选择你选择的数据源。

   > [!div class="mx-imgBorder"]
   > ![可用的数据源包括：ADLS Gen2、Enterprise 网站、Microsoft SQL 服务器、Azure SQL、Oracle SQL 数据库、ServiceNow、文件共享、Azure DevOps 和 MediaWiki。](media/add-connector.png)

> [!NOTE]
> 最多可以向每个租户添加 10 Graph连接。

## <a name="step-2-name-the-connection"></a>步骤 2：命名连接

指定以下属性：

* Name（必选）
* 连接 ID (是必需的) 
* 说明 (可选) 

连接 ID 为连接器创建隐式属性。 它只能包含字母数字字符，并且最多包含 32 个字符。

## <a name="step-3-configure-the-connection-settings"></a>步骤 3：配置连接设置

配置连接设置的过程因数据源的类型而异。 有关要添加到租户的数据源类型，请参阅特定于连接器的信息，以在设置过程中完成此步骤。  

若要了解有关连接到本地数据源的更多信息，请参阅安装 [本地数据网关](/data-integration/gateway/service-gateway-install)。

## <a name="step-4-manage-search-permissions"></a>步骤 4：管理搜索权限

访问控制列表 (ACL) 确定组织中哪些用户可以访问每一项数据。  

一些连接器（如[Microsoft SQL](MSSQL-connector.md)和 Azure Data Lake[存储 Gen2）](azure-data-lake-connector.md)在本机Azure Active Directory ([Azure AD) ](/azure/active-directory/) ACL。

其他连接器（如[ServiceNow、Azure DevOps](servicenow-connector.md)和[](azure-devops-connector.md)[Salesforce）](salesforce-connector.md)支持同步非 Azure AD 用户和组。  

## <a name="step-5-assign-property-labels"></a>步骤 5：分配属性标签

可以在"分配属性标签"页上将语义标签分配给源属性。 标签是 Microsoft 提供的已知标记，可提供语义含义。 它们允许 Microsoft 将连接器数据集成到Microsoft 365体验，如增强的搜索、人员卡片、智能发现等。  

下表列出了当前支持的标签及其说明。  

标签 | 说明
--- | ---  
**title** | 您希望在搜索和其他体验中显示的项目的标题
**url** | 源系统中项的目标 URL
**createdBy** | 创建项目的人的名称
**lastModifiedBy** | 最近编辑项目的人的姓名
**authors** | 参与/协作项目人员的姓名
**createdDateTime** | 项目创建时间
**lastModifiedDateTime** | 最近编辑的项目何时
**fileName** | 文件项的名称
**FileExtension** | 文件项的类型，如 .pdf 或 .word

此页上的属性根据数据源预先选择，但如果有更适合特定标签的不同属性，可以更改此选择。  

标签 **标题** 是最重要的标签。 强烈建议 **你为此** 标签分配一个属性，以便你的连接参与结果 [群集体验](result-cluster.md)。

映射标签不正确会导致搜索体验下降。 可以不为某些标签分配属性。  

## <a name="step-6-manage-schema"></a>步骤 6：管理架构

### <a name="content-property"></a>Content 属性

建议从选项的下拉菜单中选择" **内容** 属性"，或保留默认值（如果存在）。 此属性用于内容全文索引编制、搜索结果页面代码段生成、结果 [群集参与、](result-cluster.md) 语言检测、HTML/文本支持、排名和相关性以及查询整理。

如果选择内容属性，则创建结果类型时，可以选择使用系统生成的属性 **ResultSnippet。** [](customize-results-layout.md) 此属性充当查询时从 content 属性生成的动态代码段的占位符。 如果在结果类型中使用此属性，将在搜索结果中生成代码段。

### <a name="creating-aliases-for-source-properties"></a>为源属性创建别名

您可以在"管理架构"页上的"别名"列下向属性添加别名。 别名是属性的友好名称，也用于查询和筛选器创建。 它们还用于规范化来自多个连接的源属性，这样它们具有相同的名称。 这样，你可以为具有多个连接的垂直创建单个筛选器。 有关详细信息，请参阅 [自定义搜索结果页面](customize-search-page.md)。  

### <a name="search-schema-attributes"></a>搜索架构属性

您可以设置搜索架构属性来控制每个源属性的搜索功能。 搜索架构可帮助确定搜索结果页面上显示哪些结果，以及最终用户可以查看和访问的信息。

搜索架构属性包括查询、**搜索、****检索和** 优化 **的选项**。 下表列出了 Microsoft 连接器支持的每个Graph并解释了它们的功能。

搜索架构属性 | 函数 | 示例
--- | --- | ---
SEARCH | 使属性的文本内容可搜索。 属性内容包含在全文索引中。 | 如果属性为 **title**，则查询Enterprise返回包含单词 **Enterprise文本** 或标题中的结果。
QUERY | 通过查询来搜索特定属性的匹配项。 然后，可以在查询中以编程方式或详细方式指定属性名称。 |  如果可以查询 **Title** 属性，则支持查询 **Title： Enterprise。**
检索 | 结果类型中只能使用可检索属性，并显示在搜索结果中。 |
优化 | 精简选项可在"Microsoft 搜索结果"页中一样使用。 | 如果在连接设置 [过程中](custom-filters.md) 标记了精简属性，则贵组织的用户可以在搜索结果页中按 **URL** 进行筛选

对于除文件共享连接器之外的所有连接器，必须手动设置自定义类型。 若要激活每个字段的搜索功能，您需要映射到属性列表的搜索架构。 连接向导根据选择的源属性集自动选择搜索架构。 您可以通过选中搜索架构页中每个属性和属性的复选框来修改此架构。

> [!div class="mx-imgBorder"]
> ![连接器的架构可以通过添加或删除查询、搜索和检索功能来自定义。](media/manageschema.png)

### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>搜索架构设置的限制和建议

* **content** 属性只能搜索。 在下拉列表中选中后，此属性不能与检索或查询 **选项****一起使用**。

* 当使用 content 属性呈现搜索结果时，会发生 **重大** 性能问题。 例如 **，ServiceNow** 知识库文章的文本 [](https://www.servicenow.com)内容字段。

* 只有标记为可检索的属性才能呈现在搜索结果中，并可用于在 MRT 中 (新式) 。

* 只能将字符串属性标记为可搜索。

> [!NOTE]
> 创建连接后， **无法修改** 架构。 为此，需要删除连接并创建一个新连接。

## <a name="step-7-refresh-settings"></a>步骤 7：刷新设置

刷新间隔确定数据在数据源和 Microsoft 搜索之间同步频率。 根据数据的修改频率和修改类型，每种类型的数据源都有一组不同的最佳刷新计划。

有两种类型的刷新间隔，即"完全刷新"和"增量刷新"，但增量刷新不适用于某些数据源。

在完全刷新后，搜索引擎将处理和索引内容源中已更改的项目，而不考虑以前的爬网。 完全刷新最适合以下情形：

* 检测数据的删除。
* 增量刷新发现错误，但失败。
* ACL 已修改。
* 已修改爬网规则。
* 连接架构已更新， (架构更新不受支持) 。

使用 **增量刷新**，搜索引擎只能处理自上次成功爬网后创建或修改的项目并编制索引。 因此，并非所有内容源中的数据都重新索引。 增量刷新最能够检测内容、元数据、权限和其他更新。

增量刷新比完全刷新快得多，因为不会处理未更改的项目。 但是，如果您选择运行增量刷新，您仍然需要定期运行完全刷新，以在内容源和搜索索引之间保持正确的数据同步。

> [!div class="mx-imgBorder"]
> ![增量爬网和完全爬网间隔设置显示"增量为 15 分钟"和"完全爬网为 1 周"。](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>步骤 8：查看连接

可以在完成连接前查看整个配置并根据需要编辑设置。 **如果尚未阅读，请务必阅读数据源的连接器特定信息。** 准备好 **完成连接** 后，选择"完成更新"。

### <a name="confirm-if-the-connection-setup-worked"></a>确认连接设置是否有效

转到管理中心中"连接器"选项卡下的已发布连接[列表](https://admin.microsoft.com)。 若要了解如何进行更新和删除，请参阅 [管理连接器](manage-connector.md)。

## <a name="troubleshooting"></a>疑难解答
<!---Insert troubleshooting recommendations for this data source-->
读取数据源的连接器特定信息。 

> [!NOTE]
> 此时，并非所有特定于连接器的文章都包括疑难解答建议。

## <a name="limitations"></a>限制
<!---Insert limitations for this data source-->
若要了解适用于所有数据源的限制，请参阅 Microsoft Graph[概述](connectors-overview.md)文章。

请参阅数据源的特定于连接器的信息，了解该特定连接器是否Graph限制。

## <a name="next-steps"></a>后续步骤

发布连接后，需要自定义搜索结果页面。 若要了解如何自定义搜索结果，请参阅自定义 [搜索结果页面](customize-search-page.md)。