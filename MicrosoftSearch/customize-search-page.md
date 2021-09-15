---
title: 自定义Microsoft 搜索页面
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 添加垂直搜索并自定义搜索结果
ms.openlocfilehash: 1ca436a2617e32e285715e4fffd622dc7a571ca1
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375683"
---
# <a name="customize-the-search-results-page"></a>自定义搜索结果页面

您可以创建垂直 *搜索* 和结果类型，以自定义用户在 Microsoft [SharePoint、Microsoft Office](https://office.com)和 必应 中 [](https://sharepoint.com/)搜索时Microsoft 搜索 [看到的必应。](https://bing.com) 通过垂直方向，用户可以更轻松地找到他们有权查看的信息。

例如，您可以为市场营销部门用户的第三方软件中的营销分析数据创建垂直搜索。 还可以定义结果类型并为此数据自定义布局。

## <a name="about-search-verticals"></a>关于垂直搜索

在结果页的顶部有一行Microsoft 搜索选项卡。 这些是垂直搜索。 垂直搜索只显示某种类型或特定内容集的结果。 例如 **，Files** 或 **News**。 默认情况下，Microsoft 搜索显示"全部"、"人员"、"**文件**"、"**网站**"和"新闻 **"。**   

您可以添加与您的组织相关的垂直搜索。 这些将出现在Microsoft 搜索、SharePoint和Office结果必应。 例如，您可以根据每个部门需要的信息类型为与营销相关的内容创建一个垂直目录，为销售创建另一个垂直目录。 您可以添加垂直线来显示仅来自通过连接器编制索引的内容的结果。

您可以在两个级别创建垂直和结果类型：

- **组织级别**– 当用户从 SharePoint 起始页、Office 或 必应 中搜索时，[](https://sharepoint.com/)在组织级别创建的 [垂直搜索将显示在搜索结果页面上](https://bing.com)。 [](https://office.com)
- **网站** 级别 – 例如，您可能希望允许客户服务员工直接从其部门的网站搜索严重性 *1* SharePoint事件。

### <a name="multiple-connections-in-a-vertical"></a>垂直连接中的多个连接

垂直搜索可以显示来自多个连接器源的结果。 此选项可灵活地设计搜索结果页面。 垂直设置过程使管理员能够在"内容源"步骤中选择多个连接。

如果你准确地指定尽可能多 *的语义* 标签，则这种体验会得到增强。 在架构定义和引用点添加语义标签。 [请参阅有关如何创建和管理语义标签的更多内容](configure-connector.md#step-6-assign-property-labels)。
[下面是](configure-connector.md#step-6-assign-property-labels) 有关创建和管理语义标签的其他信息。

> [!NOTE]
> 垂直功能中的多个连接当前处于预览阶段。 有关详细信息，请参阅 [连接器预览功能](connectors-overview.md#what-are-the-preview-features)。

连接可以添加为单个垂直方向下的内容源。 不能在多个垂直方向使用连接。

若要为添加了多个连接源的垂直搜索设置查询，请使用常用源属性创建查询。

### <a name="before-you-create-verticals-and-result-types"></a>创建垂直和结果类型之前

请考虑以下因素：

- 确保连接器已编制索引。 这最多可能需要 48 小时，具体取决于文件大小。

- 无法为驻留在网站中的内容创建SharePoint。

以下为实现垂直方向的步骤：

1. 创建垂直。 在此步骤中，定义要搜索的内容的垂直名称、内容源和范围。
2. 定义此垂直方向的结果。  
3. 启用垂直 (从垂直) 显示垂直列表。

## <a name="step-1-create-the-search-vertical"></a>步骤 1：创建垂直搜索

启动向导后，将指导您完成定义要搜索的内容的垂直名称、内容源和范围的步骤。

>[!Note]
>垂直线处于禁用状态。 您可以启用它们使其可查看。

您可以使用一组有限的关键字查询语言 [ (KQL) ](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) 缩小范围。  (本文稍后将介绍您可以使用的属性。) 我们建议您将自定义文本关键字和属性限制与布尔运算符一同使用。 KQL 还 [支持配置文件查询变量](#profile-query-variables) 对垂直方向的结果进行微调。

### <a name="create-a-vertical-at-the-organization-level"></a>在组织级别创建垂直

若要在家庭Microsoft 搜索、SharePoint或Office必应创建垂直搜索，请按照以下步骤操作：

1. 在 ["Microsoft 365 管理中心](https://admin.microsoft.com)中，转到 [**"垂直"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. 选择 **"添加** "开始。  

### <a name="create-a-vertical-at-the-site-level"></a>在网站级别创建垂直

1. 在 [SharePoint](https://sharepoint.com/)垂直搜索的网站中，转到 **"设置"。**
2. 选择 **"网站信息**"，然后选择"**查看所有网站设置"。**
3. 找到 **"Microsoft 搜索"** 部分，然后选择"为此 **Microsoft 搜索配置网站集"。**
4. 在导航窗格中，转到" **自定义体验**"，然后选择" **垂直"** 选项卡。
5. 若要添加垂直，请选择"添加 **"。** 或者，若要编辑垂直方向，请从列表中选择它。

## <a name="step-2-create-result-types"></a>步骤 2：创建结果类型

可以使用结果 *类型* 定义结果在垂直方向上的显示方式。 结果布局使你可以直接在搜索结果中显示重要信息，因此用户不必选择每个结果来查看他们是否找到了要查找的内容。

### <a name="default-search-result-layout"></a>默认搜索结果布局

如果标签和内容属性在配置连接器时正确映射到源属性，将为连接器内容显示默认搜索结果布局。 标题 *标签* 是最重要的标签。 *强烈建议您* 分配有一个属性来使用此标签以使用默认搜索结果布局。

### <a name="create-your-own-result-type"></a>创建自己的结果类型

若要创建自己的搜索结果布局并覆盖默认搜索结果布局，请创建一个 *结果类型*。 搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。 这包括：

- **要比较每个** 搜索结果的一个或多个条件，例如搜索结果的内容源。  
- **用于满足** 条件的搜索结果的结果布局。 生成的布局控制满足条件的结果在搜索结果页面上的显示和行为方式。

*如果不执行适当的映射来显示默认搜索结果布局，则必须创建至少一个结果类型，以在垂直方向显示结果。* 

您可以为每个垂直类型创建多个结果类型，这允许您对不同类型的结果使用不同的布局。 例如，你可以自定义"严重性 *1"* 事件，以比"严重性 *3"* 事件更醒目的颜色和更大的字体。

启动向导后，将指导您完成定义结果类型的名称、内容源和条件的步骤。 可以从列表视图定义结果类型的优先级。
  
### <a name="create-a-result-type-at-the-organization-level"></a>在组织级别创建结果类型

1. 在 ["Microsoft 365 管理中心"](https://admin.microsoft.com)中，转到"[**结果类型"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)
2. 若要添加结果类型，请选择"添加 **"。** 若要编辑结果类型，请从相关列表中选择结果类型。

### <a name="create-a-result-type-at-the-site-level"></a>在网站级别创建结果类型

1. 在 [SharePoint](https://sharepoint.com/)结果类型的网站中，转到 **"设置"。**
2. 选择 **"网站信息**"，然后选择"**查看所有网站设置"。**
3. 查找 **"Microsoft 搜索"** 部分，然后选择"为此 **Microsoft 搜索配置网站集"。**
4. 在导航窗格中，转到" **自定义体验"，** 然后选择" **结果类型"** 选项卡。
5. 若要添加结果类型，请选择"添加 **"。**  或者，若要编辑结果类型，请在列表中选择结果类型。

## <a name="step-3-view-the-vertical-after-its-enabled"></a>步骤 3：启用后查看垂直方向

启用垂直方向后，将延迟几小时才能查看它。 但是，您可以追加到 SharePoint 中的 URL Office `cacheClear=true` 查看垂直方向。 例如必应，追加 `&features=uncachedVerticals` 到 `Work vertical URL` 以立即查看垂直方向。

> [!NOTE]
> 从移动 Web 浏览器查看时，SharePoint (和Office垂直 https://sharepoint.com/) 线不可见。 [](https://office.com)

## <a name="profile-query-variables"></a>配置文件查询变量

使用垂直方向的 KQL 查询节中的变量提供动态数据作为垂直查询的输入。 您可以使用配置文件查询变量使搜索结果与登录用户上下文相关。 配置文件查询变量从已登录用户的配置文件提取 [值](/graph/api/resources/profile)。

例如，若要为用户创建垂直"票证"以查找分配给他们的支持票证，您可以在管理页的垂直创建期间在"查询"部分指定以下查询：  

`AssignedTo:{Profile.accounts.userPrincipalName}`

此语言将缩小搜索结果范围，以只显示被分派人是运行搜索的用户的项目。

[配置文件资源](/graph/api/resources/profile) 将属性公开为集合。 例如，与电子邮件地址有关的信息通过电子邮件集合公开，工作职位作为职位集合，等等。 用户配置文件中提供的所有属性（将 AAD 作为源类型）都作为查询变量公开。


请考虑电子邮件集合中具有三个电子邮件地址的用户，如下所示：

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- 查询 `MyProperty: {Profile.emails.address}` 将解析为 *MyProperty："Megan.Bowen@contoso.com"。*  

- 若要解析 address 属性的所有值，请使用多值扩展语法。 查询将解析为 `{|MyProperty:{Profile.emails.address}}` *( (MyProperty："Megan.Bowen@contoso \. com")* 或 *(MyProperty： "meganb@hotmail \. com")* or  *(MyProperty："meganb@outlook \. com") )*。

使用"|"运算符可解析多值变量。 有关配置文件扩展的更多示例，请参阅下表。

| #         | 语法 |  返回的值  |
| --------- | ------ | --- |
| 1    | MyProperty：{Profile.emails.address}  |   "Megan \. Bowen@contoso.com"  |
| 2 | MyProperty：{Profile.emails}   |    {Profile.emails} 这无法解析， *因为电子邮件* 是对象。|
| 3    | {?MyProperty：{Profile.emails}}  |  这无法解决， *因为电子邮件* 是对象。 "？" 运算符忽略不解析的查询变量。 当进一步向下传递查询堆栈时，将删除此变量。   |
| 4  | {&#124;MyProperty： {Profile.emails.source.Type}}    |   ( (MyProperty："official") or (MyProperty："non-official") or (MyProperty："personal") )     |

> [!NOTE]
>
> - 配置文件查询变量仅受使用连接器作为内容源的自定义垂直搜索[](connectors-overview.md)的支持。
> - 配置文件查询变量在垂直设置过程的"查询" [部分中定义](customize-search-page.md#step-1-create-the-search-vertical)。
> - 配置文件查询变量功能当前处于预览阶段。 有关预览的详细信息，请参阅 [连接器预览功能](connectors-overview.md#what-are-the-preview-features)。

## <a name="troubleshooting"></a>疑难解答

下面列出了可能会遇到的常见问题以及解决这些问题的操作。

|问题  |操作  |
|---------|---------|
| 我在垂直方向看到一条"出错"错误消息。 | 完成设置需要垂直类型和结果类型。 确保为同一内容源创建了两者。 |
| 我看不到我的结果布局，尽管我创建了一个结果布局。 | 由于缓存了这些设置，因此可能有几分钟的延迟。 请等待几分钟，然后重试。        |
| 在垂直或结果类型页面上，我看不到任何内容源。 | 确保已配置连接器和索引数据。   |

## <a name="next-steps"></a>后续步骤

[自定义结果布局](customize-results-layout.md)
