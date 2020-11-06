---
title: 管理搜索结果布局
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 使用自适应卡片，创建布局以查看自定义搜索结果
ms.openlocfilehash: 425e5404c14d500f6ecd84ad449dafb05bbfd31b
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927177"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a>创建布局以自定义搜索结果

您可以使用搜索布局设计器来设计自定义垂直布局的结果布局。 您可以通过选择布局设计器中提供的模板来开始设计布局，并在它们满足您的要求时使用它们。 或者，您可以选择以多种方式编辑这些模板以满足您的要求。 例如，添加/删除图像、添加/删除文本和修改文本。 如果所有模板都无法满足您的要求，则可以选择使用空白模板开始设计布局。  

布局准备就绪后，使用 [自适应卡片模板语言](https://docs.microsoft.com/adaptive-cards/templating/language) 创建用于定义结果类型的结果布局 JSON。 您可以使用布局设计器中的映射步骤将结果属性映射到布局。  

## <a name="create-a-layout-on-your-own"></a>自己创建布局

您自己创建布局需要了解 [自适应卡片](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) 及其 [架构](https://adaptivecards.io/explorer/)。 搜索结果布局使用自适应卡片提供的元素的子集，您可以使用布局设计器了解支持的一组元素。  

创建自己的布局时，使用连接器中的数据创建自适应卡片布局，然后完成布局。
创建自己的布局有两个主要步骤：

- 设计布局。
- 将数据与模板分离。

### <a name="design-the-layout"></a>设计布局

在此示例中，我们显示了一个包含标题、链接和说明性文本的布局。

![包含标头、链接和说明的布局的示例。](media/Verts-ExampleLayout.png)

以下是布局的关联 JSON 文件：

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
     "body": [
{

            "type": "ColumnSet",
             "columns": [
                 {
                     "type": "Column",
                     "width": 8,
                     "items": [
                         {
                             "type": "TextBlock",
                             "text": "Contoso Marketing Analysis - Q3 FY18",
                             "color": "Accent",
                             "size": "Medium",
                             "spacing": "None",
                             "$when": "{title != \"\"}",
                             "weight": "Bolder"
                        },
                        {
                        "type": "TextBlock",  
                        "text": "https://contoso.com/hr/link",
                        "spacing": "None",  
                        "color": "Dark",
                        "weight": "Bolder"

                        },

                        {  
                        "type": "TextBlock",
                        "text": "Marketing team at Contoso.., and looking at the Contoso Marketing documents on the team site. This contains the data from FY20 and will taken over to FY21...Marketing Planning is ongoing for FY20..",  
                        "wrap": true,
                        "maxLines": 2,
                        "spacing": "Medium"
                        }
                        ],

                    "horizontalAlignment": "Center",
                    "spacing": "None"

                }

            ]

        }
        ],

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
}
```

### <a name="separate-the-data-from-the-layout"></a>将数据与布局分离

您可以将数据与布局分开，并绑定数据。

下面是绑定数据后的布局 JSON：

```json
{

    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
    {
    "type": "ColumnSet",
"columns": [

                {
                "type": "Column",
                "width": 8,
                "items": [
                {
                "type": "TextBlock",
                "text": "[{title}]({titleUrl})",
                "color": "Accent",
                "size": "Medium",
                "spacing": "None",
                "weight": "Bolder"

                 },
                 {
                 "type": "TextBlock",
                 "text": "{link}",
                 "spacing": "None",
                 "color": "Dark",
                 "weight": "Bolder"
                 },
                 {
                 "type": "TextBlock",
                 "text": "{description}",
                 "wrap": true,
                 "maxLines": 2,
                 "spacing": "Medium"
                 }
                 ],
                 "horizontalAlignment": "Center",
                 "spacing": "None"
                 }
                 ]

        }

    ],

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
}
```

示例数据：在 **预览模式下** ，在 **示例数据编辑器** 中指定示例数据以查看数据绑定卡。

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a>将布局映射到结果属性

您必须将布局的每个字段映射到一个 result 属性或一个连接器属性，以生成结果布局 JSON。

!["搜索布局设计器" 页上的示例布局的屏幕截图，其中选定了一个字段并打开了属性窗格。](media/Verts-SearchLayoutDesigner.png)

在布局中选择一个字段，以突出显示需要映射的变量。 您可以将多个变量用于单个字段，并且所有字段都必须映射到 result 属性。

### <a name="show-snippet-on-search-result"></a>在搜索结果中显示代码段  

在连接器结果的 **content** 属性上生成的动态代码段可以显示在搜索结果中。 **ResultSnippet** 是系统属性，充当为每个连接器结果生成的代码段的占位符属性。 若要在结果布局上显示代码段，则必须将 **ResultSnippet** system 属性映射到搜索结果布局中的相应字段（例如 "说明"）。 在每个结果上生成的代码段还突出显示代码片段中用户输入的查询词的匹配项。

## <a name="things-to-consider"></a>注意事项

在开始之前，应执行一些操作，并应避免使用以下操作，以确保布局将会成功。

### <a name="do"></a>允许事项

- 如果要对徽标使用静态链接而不是结果属性，请编辑模板以在布局中提供徽标链接。
- 在结果 JSON 中使用的 result 属性未返回任何数据的情况下，验证结果布局。 `$when`如果属性不包含数据，则使用条件来隐藏元素。  
- 请确保 `$when` condition 和 result 属性的数据类型匹配。 例如，不要 `Number` `Text` 在条件中进行比较 `$when` 。  
- 设计结果布局时，请考虑主题要求。  
- 请确保该 `Textblock`   元素可以处理动态内容。 您可以使用 `wrap` 和 `maxLines` 元素属性来实现此目的。
- 在 Markdown 中使用时正确设置日期格式 `{DATE()}` 。  

### <a name="dont"></a>禁止事项

- 绑定值时，请勿定义无效的数据类型。 有关数据类型的详细信息，请参阅 [管理搜索架构](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema)。
- 避免通过遵循结果布局 JSON 的最大高度来裁剪结果页上的结果。 如果超出结果布局的最大高度，则结果页上的结果将被裁剪。
- 不使用 `px` 元素属性中的值。
- 请勿在结果布局中将 markdown 与 **ResultSnippet** 属性一起使用，以在搜索结果中突出显示查询匹配项。

## <a name="resources"></a>资源

[自定义搜索结果页面](customize-search-page.md)

[自适应卡片](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[自适应卡片模板语言](https://docs.microsoft.com/adaptive-cards/templating/language)

[自适应卡片架构](https://adaptivecards.io/explorer/)