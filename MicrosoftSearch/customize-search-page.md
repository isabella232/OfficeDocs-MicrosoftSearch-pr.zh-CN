---
title: 自定义 Microsoft 搜索页
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 添加垂直搜索并自定义搜索结果
ms.openlocfilehash: e5c4ab8d507e0e6096a5b9d52dc0e818faebefb6
ms.sourcegitcommit: a07c957dfa1d31542f0362379251bc9679dfae41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2021
ms.locfileid: "51639850"
---
# <a name="customize-the-search-results-page"></a>自定义搜索结果页面

您可以创建垂直搜索和结果类型，以自定义用户在必应中的 Microsoft [SharePoint、Microsoft Office](https://sharepoint.com/)和 Microsoft 搜索中搜索 [时](https://office.com)看到的 [搜索结果](https://bing.com)。 通过垂直方向，用户可以更轻松地找到他们有权查看的信息。 例如，您可以为市场营销部门用户的第三方软件中的营销分析数据创建垂直搜索。 还可以定义结果类型并为此数据自定义布局。  

您可以在以下级别创建垂直和结果类型：

- **组织级别** – 当您在组织级别添加垂直搜索时，当用户从 [SharePoint](https://sharepoint.com/) 起始页 [、Office](https://office.com)或必应上搜索时，它将显示在 [搜索结果页面上](https://bing.com)。
- **网站** 级别 – 例如，您可能希望允许客户服务员工直接从其部门的 SharePoint 网站搜索严重性 *1* 事件。

## <a name="search-verticals-explained"></a>说明的垂直搜索

在"Microsoft 搜索结果"页面顶部，有一行选项卡。 这些是垂直搜索。 垂直搜索只显示某种类型或特定内容的结果。 例如 **，Files** 或 **News**。 默认情况下，Microsoft 搜索显示垂直"全部 **"、"** 人员 **"、"文件****"、"网站**"和"**新闻"。**   

您可以添加与组织相关的垂直搜索。 这些将显示在[SharePoint、Office](https://sharepoint.com/)和必应中的 Microsoft[](https://Office.com)搜索结果[页面上](https://bing.com)。 例如，您可以根据每个组需要的信息类型，为与市场营销相关的内容创建一个垂直目录，为销售创建另一个垂直目录。 您可以添加垂直线来显示仅来自通过连接器编制索引的内容的结果。  

### <a name="multiple-connections-in-a-vertical"></a>垂直连接中的多个连接

垂直搜索现在可以显示来自多个连接器源的结果。 这样可更灵活地设计搜索结果页面。 通过垂直设置的现有管理体验，您可以在"内容源"步骤中选择多个连接。
如果准确指定尽可能多的语义标签，将会增强此体验。 你可以根据架构定义和引用添加语义标签。

[下面是](configure-connector.md#step-5-assign-property-labels) 有关创建和管理语义标签的其他信息。

> [!NOTE]
> 垂直连接中的多个连接当前处于预览阶段。 有关预览的详细信息，请参阅 [连接器预览功能](connectors-overview.md#what-are-the-preview-features)。

### <a name="things-you-should-know"></a>你应了解的一些内容

1. 连接只能在一个垂直方向添加为内容源。 不允许在多个垂直方向下重新使用连接。
2. 如果需要为添加了多个连接源的垂直搜索设置查询，则应当使用公共源属性创建此类查询。

## <a name="things-to-consider"></a>注意事项

在启动之前，请确保连接器已编制索引。 这最多可能需要 48 小时，具体取决于文件大小。

无法为驻留在 SharePoint 中的内容创建[垂直。](https://sharepoint.com/)

添加垂直方向有三个基本步骤：

1. 创建垂直。 在此步骤中，定义要搜索的内容的垂直名称、内容源和范围。
2. 定义此垂直方向的结果。  
3. 启用垂直 (从垂直) 显示垂直列表。

## <a name="step-1-create-the-search-vertical"></a>步骤 1：创建垂直搜索

启动向导后，将指导您完成定义要搜索的内容的垂直名称、内容源和范围的步骤。 垂直线处于禁用状态。 稍后将启用它。

您可以使用一组有限的关键字查询语言 [ (KQL) ](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) 范围。 此页面列出了可用的属性。 建议您将自由文本关键字和属性限制与布尔运算符一起用于创建 KQL。

### <a name="create-a-vertical-at-the-organization-level"></a>在组织级别创建垂直

若要在 [SharePoint](https://sharepoint.com/) 主页 [、Office](https://office.com)或 [必应](https://bing.com)中的 Microsoft 搜索上创建垂直搜索，请按照以下步骤操作：

1. 在 [Microsoft 365 管理中心中](https://admin.microsoft.com)，转到 [**"垂直"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. 选择 **"添加** "开始。  

### <a name="create-a-vertical-at-the-site-level"></a>在网站级别创建垂直

1. 在需要垂直方向的 [SharePoint](https://sharepoint.com/)网站上，转到"设置 **"。**
2. 选择 **"网站信息**"，然后选择 **"查看所有网站设置"。**
3. 查找 **"Microsoft 搜索"** 部分，然后为此网站集 **选择"配置 Microsoft 搜索"。**
4. 在导航窗格中，转到" **自定义体验**"，然后选择" **垂直"** 选项卡。
5. 若要添加垂直，请选择"添加 **"。**
  或者，若要编辑垂直方向，请在列表中选择它。

请记住，垂直是在禁用状态中创建的。 必须启用它们，用户才能看到它们。

## <a name="step-2-create-the-result-types"></a>步骤 2：创建结果类型

您可以通过使用结果类型设计布局来定义结果在垂直方向上的显示方式。 结果布局使你可以直接在搜索结果中显示重要信息，因此用户不必选择每个结果来查看他们是否找到了要查找的内容。

### <a name="default-search-result-layout"></a>默认搜索结果布局

如果在配置连接器时标签和 **内容** 属性已正确映射到源属性，将为连接器内容显示默认搜索结果布局。 标签 **标题** 是最重要的标签。 强烈建议 **您为此** 标签分配一个属性，以使用默认搜索结果布局。

### <a name="create-your-own-result-type"></a>创建自己的结果类型

您可以决定创建自己的搜索结果布局，然后通过创建结果类型覆盖默认 **搜索结果布局**。 搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。 它包含以下几个方面：

- **要比较每个** 搜索结果的一个或多个条件，例如搜索结果的内容源。  
- **用于满足** 条件的搜索结果的结果布局。 结果布局控制满足条件的所有结果在搜索结果页面上的显示和行为方式。

**如果未进行适当的映射以显示默认搜索结果布局，则必须为结果至少创建一个结果类型，以在垂直方向显示。** 您可以为每个垂直类型创建多个结果类型，这允许您对不同类型的结果使用不同的布局。 例如，你可以自定义"严重性 *1"* 事件，以比"严重性 *3"* 事件具有更醒目的颜色和更大的字体。

启动向导后，将指导您完成定义结果类型的名称、内容源和条件的步骤。 可以从列表视图定义结果类型的优先级。
  
### <a name="create-a-result-type-at-the-organization-level"></a>在组织级别创建结果类型

1. 在 [Microsoft 365 管理中心中](https://admin.microsoft.com)，转到"[**结果类型"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)
2. 若要添加结果 **类型，请选择**"添加 **"。** 若要编辑结果类型，请在相关列表中选择结果类型。

### <a name="create-a-results-type-at-the-site-level"></a>在网站级别创建结果类型

1. 在要创建结果类型的 [SharePoint](https://sharepoint.com/)网站上，转到"设置 **"。**
2. 选择 **"网站信息**"，然后选择 **"查看所有网站设置"。**
3. 查找"Microsoft 搜索"部分，然后为此网站集 **选择"配置 Microsoft 搜索"。**
4. 在导航窗格中，转到"自定义 **体验"，** 然后选择" **结果类型"** 选项卡。
5. 若要添加结果类型，请选择"添加 **"。**  或者，若要编辑结果类型，请在列表中选择结果类型。

## <a name="step-3-view-the-vertical-after-its-enabled"></a>步骤 3：启用后查看垂直方向

启用垂直方向后，需要几个小时才能查看。 如果不想在启用后等待，可以将 **cacheClear=true** 追加到 [SharePoint](https://sharepoint.com/) 和 [Office](https://office.com) 中的 URL，以便立即查看垂直方向。 对于 [必应](https://bing.com)，将 **&features=uncachedVerticals** 追加到"工作"垂直 URL 以立即查看垂直方向。 

> [!NOTE]
> 从移动 Web 浏览器查看时，添加的垂直方向在 [SharePoint](https://sharepoint.com/) 和 [Office](https://office.com) 上不可见。

## <a name="troubleshooting"></a>疑难解答

下面列出了可能会遇到的常见问题以及解决这些问题的操作。

|错误  |操作  |
|---------|---------|
| 我在垂直方向看到一条"出错"错误消息。 | 完成设置需要垂直类型和结果类型。 确保为同一内容源创建了两者。 |
| 我看不到我的结果布局，尽管我创建了一个结果布局。 | 由于通常缓存这些设置，因此需要几分钟时间。 请等待几分钟，然后重试。        |
| 在垂直或结果类型页面上，我看不到任何内容源。 | 确保已配置连接器和索引数据。   |

## <a name="next-steps"></a>后续步骤

[自定义结果布局](customize-results-layout.md)
