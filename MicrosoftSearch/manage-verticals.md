---
title: 管理垂直搜索
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 管理结果页面上的垂直搜索
ms.openlocfilehash: 0396c1f67b22a77a39f78aa1f058ee4b2019a39c
ms.sourcegitcommit: 02d4f91210d992da080fd39d5b60f8cf30d8f0b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2021
ms.locfileid: "60238400"
---
# <a name="manage-search-verticals"></a>管理垂直搜索

垂直搜索是搜索结果页面上显示特定类型的结果或来自选定源的结果的选项卡。 例如，"文件"垂直显示分类为文件的结果，使查找文档的用户可以轻松找到文档。 您可以自定义组织中Microsoft 搜索，以满足组织或各个部门的需求。

您可以在两个级别管理垂直方向：

- **组织级别**– 当用户从用户的 SharePoint 起始页、Microsoft Office 和 Microsoft 搜索 [](https://sharepoint.com/)中搜索时，搜索结果页面上会显示 [](https://office.com)组织级别的 [垂直必应](https://bing.com)
- **网站级别**– 当用户在搜索结果页上搜索网站时，网站级别的垂直SharePoint显示。 例如，您可能希望允许客户服务员工直接从其部门的网站搜索严重性 1 SharePoint事件。

## <a name="understanding-search-verticals"></a>了解垂直搜索

Microsoft 搜索有两种类型的垂直线，即开箱即用和自定义垂直。 Out of the box verticals like All， Files， and People create easy access to the most commonly used search results.

其他配置选项在自定义垂直方向提供，可用于为用户创建最佳体验。

您可以添加与您的组织相关的垂直搜索。 例如，您可以根据每个部门需要的信息类型为与营销相关的内容创建一个垂直目录，为销售创建另一个垂直目录。 可以添加垂直线以显示由 Graph[连接器](connectors-overview.md)编制索引的内容的结果，但不能为驻留在 SharePoint 中的内容创建SharePoint。

## <a name="create-search-verticals"></a>创建垂直搜索

垂直管理体验由向导驱动，指导您完成定义要搜索的内容的垂直名称、内容源和范围的步骤。 您可以使用一组有限的关键字查询语言 [ (KQL ](#keyword-query-language-kql)) 定义给定内容源的垂直搜索范围。

以下是在 Microsoft 搜索、SharePoint、Office 或 必应 中创建自定义 [垂直必应。](https://bing.com/) [](https://sharepoint.com/) [](https://office.com/)  

### <a name="manage-organization-level-verticals"></a>管理组织级别的垂直

1. In the [Microsoft 365 管理中心，](https://admin.microsoft.com)go to the [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) page in the **Customization** section.
1. 单击 **"添加** "创建新的垂直方向。
1. 完成配置步骤后，你可以查看并保存垂直方向。  

### <a name="manage-site-level-verticals"></a>管理网站级别的垂直

1. 在SharePoint垂直管理的网站中，单击齿轮打开设置面板。
1. 选择 **"网站信息**"，然后选择"**查看所有网站设置"。**  
1. 查找"Microsoft 搜索"部分，然后选择"配置 **搜索设置"。**
1. 在导航窗格中，转到"自定义体验"，然后选择"**垂直"。**
1. 单击 **"添加** "创建新的垂直方向。
1. 设置配置后，你可以查看并保存垂直方向。  

## <a name="view-the-vertical-in-search-results"></a>查看搜索结果中的垂直方向

若要[在垂直搜索](manage-result-types.md)页面上Graph连接器结果，需要搜索结果布局。 在确保存在适当的结果布局时，可以启用垂直搜索。 启用垂直搜索后，将延迟几小时才能查看它。 可以将 cacheClear=true 追加到 SharePoint 中的 URL，Office查看垂直方向。 在必应中，&features=uncachedVerticals 追加到工作垂直 URL 以立即查看垂直方向。

> [!NOTE]
> 从移动 Web 浏览器查看时，SharePoint和Office垂直[](https://office.com)线不可见。 [](https://sharepoint.com/)

## <a name="advanced-configuration-options"></a>高级配置选项

### <a name="multiple-connections-in-a-vertical"></a>垂直连接中的多个连接

垂直搜索可以显示来自多个连接器源的结果。 此选项可灵活地设计搜索结果页面。 垂直设置过程使管理员能够在"内容源"步骤中选择多个连接。

如果你准确地指定尽可能多 *的语义* 标签，则这种体验会得到增强。 在架构定义和引用点添加语义标签。 [请参阅有关如何创建和管理语义标签的更多内容](configure-connector.md#step-6-assign-property-labels)。
[下面是](configure-connector.md#step-6-assign-property-labels) 有关创建和管理语义标签的其他信息。

> [!NOTE]
> - 垂直功能中的多个连接当前处于预览阶段。 有关详细信息，请参阅 [连接器预览功能](connectors-overview.md#what-are-the-preview-features)。
> - 连接可以添加为单个垂直方向下的内容源。 不能在多个垂直方向使用连接。

若要为添加了多个连接源的垂直搜索设置查询，请使用常用源属性创建查询。

### <a name="keyword-query-language-kql"></a>关键字查询语言 (KQL)

可以将查询添加到垂直搜索，以缩小使用关键字查询语言 [ (KQL ](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) (垂直搜索上显示的结果)  (有限的) 。 此页面列出了可用的属性。 建议您将自由文本关键字和属性限制与布尔运算符一起用于创建 KQL。 不支持动态排名运算符（如 XRANK、邻近运算符和字词）。

下面是一些查询示例。

|应用场景         | 查询   |  
| --------- | ------ |
|从存档网站排除结果           |NOT (path：http//contoso.sharepoint.com/archive OR path：http//contoso.sharepoint.com/CompanyArchive) |
| 基于文件类型属性排除结果 | NOT (FileType：htm) |  

#### <a name="profile-query-variables"></a>配置文件查询变量

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
> - 配置文件查询变量功能当前处于预览阶段。 有关预览的详细信息，请参阅 [连接器预览功能](connectors-overview.md#what-are-the-preview-features)。

## <a name="troubleshooting"></a>疑难解答

下面列出了可能会遇到的常见问题以及解决这些问题的操作。

|问题  |操作  |
|---------|---------|
| 我在垂直方向看到一条"出错"错误消息。 | 完成设置需要垂直类型和结果类型。 请确保为内容源设置这两者。 |
| 我在垂直页面上看不到任何内容源。 | 确保已配置连接器和索引数据。   |
