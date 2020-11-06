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
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="84a2f-103">创建布局以自定义搜索结果</span><span class="sxs-lookup"><span data-stu-id="84a2f-103">Create a layout to customize search results</span></span>

<span data-ttu-id="84a2f-104">您可以使用搜索布局设计器来设计自定义垂直布局的结果布局。</span><span class="sxs-lookup"><span data-stu-id="84a2f-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="84a2f-105">您可以通过选择布局设计器中提供的模板来开始设计布局，并在它们满足您的要求时使用它们。</span><span class="sxs-lookup"><span data-stu-id="84a2f-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="84a2f-106">或者，您可以选择以多种方式编辑这些模板以满足您的要求。</span><span class="sxs-lookup"><span data-stu-id="84a2f-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="84a2f-107">例如，添加/删除图像、添加/删除文本和修改文本。</span><span class="sxs-lookup"><span data-stu-id="84a2f-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="84a2f-108">如果所有模板都无法满足您的要求，则可以选择使用空白模板开始设计布局。</span><span class="sxs-lookup"><span data-stu-id="84a2f-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

<span data-ttu-id="84a2f-109">布局准备就绪后，使用 [自适应卡片模板语言](https://docs.microsoft.com/adaptive-cards/templating/language) 创建用于定义结果类型的结果布局 JSON。</span><span class="sxs-lookup"><span data-stu-id="84a2f-109">After the layout is ready, use the [Adaptive Cards Template language](https://docs.microsoft.com/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="84a2f-110">您可以使用布局设计器中的映射步骤将结果属性映射到布局。</span><span class="sxs-lookup"><span data-stu-id="84a2f-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="84a2f-111">自己创建布局</span><span class="sxs-lookup"><span data-stu-id="84a2f-111">Create a layout on your own</span></span>

<span data-ttu-id="84a2f-112">您自己创建布局需要了解 [自适应卡片](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) 及其 [架构](https://adaptivecards.io/explorer/)。</span><span class="sxs-lookup"><span data-stu-id="84a2f-112">Creating a layout on your own requires knowledge of [adaptive cards](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="84a2f-113">搜索结果布局使用自适应卡片提供的元素的子集，您可以使用布局设计器了解支持的一组元素。</span><span class="sxs-lookup"><span data-stu-id="84a2f-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="84a2f-114">创建自己的布局时，使用连接器中的数据创建自适应卡片布局，然后完成布局。</span><span class="sxs-lookup"><span data-stu-id="84a2f-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="84a2f-115">创建自己的布局有两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="84a2f-115">There are two main steps in creating your own layout:</span></span>

- <span data-ttu-id="84a2f-116">设计布局。</span><span class="sxs-lookup"><span data-stu-id="84a2f-116">Design the layout.</span></span>
- <span data-ttu-id="84a2f-117">将数据与模板分离。</span><span class="sxs-lookup"><span data-stu-id="84a2f-117">Separate the data from the template.</span></span>

### <a name="design-the-layout"></a><span data-ttu-id="84a2f-118">设计布局</span><span class="sxs-lookup"><span data-stu-id="84a2f-118">Design the layout</span></span>

<span data-ttu-id="84a2f-119">在此示例中，我们显示了一个包含标题、链接和说明性文本的布局。</span><span class="sxs-lookup"><span data-stu-id="84a2f-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![包含标头、链接和说明的布局的示例。](media/Verts-ExampleLayout.png)

<span data-ttu-id="84a2f-121">以下是布局的关联 JSON 文件：</span><span class="sxs-lookup"><span data-stu-id="84a2f-121">And here's the layout's associated JSON file:</span></span>

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

### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="84a2f-122">将数据与布局分离</span><span class="sxs-lookup"><span data-stu-id="84a2f-122">Separate the data from the layout</span></span>

<span data-ttu-id="84a2f-123">您可以将数据与布局分开，并绑定数据。</span><span class="sxs-lookup"><span data-stu-id="84a2f-123">You can separate the data from the layout and bind the data.</span></span>

<span data-ttu-id="84a2f-124">下面是绑定数据后的布局 JSON：</span><span class="sxs-lookup"><span data-stu-id="84a2f-124">Here's Layout JSON after binding the data:</span></span>

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

<span data-ttu-id="84a2f-125">示例数据：在 **预览模式下** ，在 **示例数据编辑器** 中指定示例数据以查看数据绑定卡。</span><span class="sxs-lookup"><span data-stu-id="84a2f-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="84a2f-126">将布局映射到结果属性</span><span class="sxs-lookup"><span data-stu-id="84a2f-126">Map the layout to the result properties</span></span>

<span data-ttu-id="84a2f-127">您必须将布局的每个字段映射到一个 result 属性或一个连接器属性，以生成结果布局 JSON。</span><span class="sxs-lookup"><span data-stu-id="84a2f-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

!["搜索布局设计器" 页上的示例布局的屏幕截图，其中选定了一个字段并打开了属性窗格。](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="84a2f-129">在布局中选择一个字段，以突出显示需要映射的变量。</span><span class="sxs-lookup"><span data-stu-id="84a2f-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="84a2f-130">您可以将多个变量用于单个字段，并且所有字段都必须映射到 result 属性。</span><span class="sxs-lookup"><span data-stu-id="84a2f-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

### <a name="show-snippet-on-search-result"></a><span data-ttu-id="84a2f-131">在搜索结果中显示代码段</span><span class="sxs-lookup"><span data-stu-id="84a2f-131">Show snippet on search result</span></span>  

<span data-ttu-id="84a2f-132">在连接器结果的 **content** 属性上生成的动态代码段可以显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="84a2f-132">Dynamic snippets generated on the **content** property of the connector result can be shown on the search result.</span></span> <span data-ttu-id="84a2f-133">**ResultSnippet** 是系统属性，充当为每个连接器结果生成的代码段的占位符属性。</span><span class="sxs-lookup"><span data-stu-id="84a2f-133">**ResultSnippet** is the system property that acts as a placeholder property for the snippets generated for each Connector result.</span></span> <span data-ttu-id="84a2f-134">若要在结果布局上显示代码段，则必须将 **ResultSnippet** system 属性映射到搜索结果布局中的相应字段（例如 "说明"）。</span><span class="sxs-lookup"><span data-stu-id="84a2f-134">To show the snippets on the result layout, the **ResultSnippet** system property must be mapped to an appropriate field, for example Description, in the search result layout.</span></span> <span data-ttu-id="84a2f-135">在每个结果上生成的代码段还突出显示代码片段中用户输入的查询词的匹配项。</span><span class="sxs-lookup"><span data-stu-id="84a2f-135">Snippets generated on each result also highlight the matches in the Snippet with the query term entered by the user.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="84a2f-136">注意事项</span><span class="sxs-lookup"><span data-stu-id="84a2f-136">Things to consider</span></span>

<span data-ttu-id="84a2f-137">在开始之前，应执行一些操作，并应避免使用以下操作，以确保布局将会成功。</span><span class="sxs-lookup"><span data-stu-id="84a2f-137">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="84a2f-138">允许事项</span><span class="sxs-lookup"><span data-stu-id="84a2f-138">Do</span></span>

- <span data-ttu-id="84a2f-139">如果要对徽标使用静态链接而不是结果属性，请编辑模板以在布局中提供徽标链接。</span><span class="sxs-lookup"><span data-stu-id="84a2f-139">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>
- <span data-ttu-id="84a2f-140">在结果 JSON 中使用的 result 属性未返回任何数据的情况下，验证结果布局。</span><span class="sxs-lookup"><span data-stu-id="84a2f-140">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="84a2f-141">`$when`如果属性不包含数据，则使用条件来隐藏元素。</span><span class="sxs-lookup"><span data-stu-id="84a2f-141">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="84a2f-142">请确保 `$when` condition 和 result 属性的数据类型匹配。</span><span class="sxs-lookup"><span data-stu-id="84a2f-142">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="84a2f-143">例如，不要 `Number` `Text` 在条件中进行比较 `$when` 。</span><span class="sxs-lookup"><span data-stu-id="84a2f-143">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="84a2f-144">设计结果布局时，请考虑主题要求。</span><span class="sxs-lookup"><span data-stu-id="84a2f-144">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="84a2f-145">请确保该 `Textblock`   元素可以处理动态内容。</span><span class="sxs-lookup"><span data-stu-id="84a2f-145">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="84a2f-146">您可以使用 `wrap` 和 `maxLines` 元素属性来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="84a2f-146">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span>
- <span data-ttu-id="84a2f-147">在 Markdown 中使用时正确设置日期格式 `{DATE()}` 。</span><span class="sxs-lookup"><span data-stu-id="84a2f-147">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="84a2f-148">禁止事项</span><span class="sxs-lookup"><span data-stu-id="84a2f-148">Don't</span></span>

- <span data-ttu-id="84a2f-149">绑定值时，请勿定义无效的数据类型。</span><span class="sxs-lookup"><span data-stu-id="84a2f-149">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="84a2f-150">有关数据类型的详细信息，请参阅 [管理搜索架构](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema)。</span><span class="sxs-lookup"><span data-stu-id="84a2f-150">For more information about data types, see [Manage the Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="84a2f-151">避免通过遵循结果布局 JSON 的最大高度来裁剪结果页上的结果。</span><span class="sxs-lookup"><span data-stu-id="84a2f-151">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="84a2f-152">如果超出结果布局的最大高度，则结果页上的结果将被裁剪。</span><span class="sxs-lookup"><span data-stu-id="84a2f-152">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="84a2f-153">不使用 `px` 元素属性中的值。</span><span class="sxs-lookup"><span data-stu-id="84a2f-153">Don't use `px` values in element properties.</span></span>
- <span data-ttu-id="84a2f-154">请勿在结果布局中将 markdown 与 **ResultSnippet** 属性一起使用，以在搜索结果中突出显示查询匹配项。</span><span class="sxs-lookup"><span data-stu-id="84a2f-154">Don't use markdown with the **ResultSnippet** property in the result layout to highlight query match in the search result.</span></span>

## <a name="resources"></a><span data-ttu-id="84a2f-155">资源</span><span class="sxs-lookup"><span data-stu-id="84a2f-155">Resources</span></span>

[<span data-ttu-id="84a2f-156">自定义搜索结果页面</span><span class="sxs-lookup"><span data-stu-id="84a2f-156">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="84a2f-157">自适应卡片</span><span class="sxs-lookup"><span data-stu-id="84a2f-157">Adaptive cards</span></span>](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="84a2f-158">自适应卡片模板语言</span><span class="sxs-lookup"><span data-stu-id="84a2f-158">Adaptive Cards Template language</span></span>](https://docs.microsoft.com/adaptive-cards/templating/language)

[<span data-ttu-id="84a2f-159">自适应卡片架构</span><span class="sxs-lookup"><span data-stu-id="84a2f-159">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)