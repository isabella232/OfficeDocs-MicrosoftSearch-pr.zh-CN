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
description: 使用自适应卡片，创建用于查看自定义搜索结果的布局
ms.openlocfilehash: d29b1a45f11079f4b71f71a387cf43cbf2f48e7d
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031734"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="81283-103">创建布局以自定义搜索结果</span><span class="sxs-lookup"><span data-stu-id="81283-103">Create a layout to customize search results</span></span>

<span data-ttu-id="81283-104">可以使用搜索布局设计器为自定义垂直方向设计结果布局。</span><span class="sxs-lookup"><span data-stu-id="81283-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="81283-105">你可以开始设计布局，方法为选择布局设计器中提供的模板，并使用它们（如果它们符合你的要求）。</span><span class="sxs-lookup"><span data-stu-id="81283-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="81283-106">或者，你可以选择以各种方式编辑这些模板以满足你的要求。</span><span class="sxs-lookup"><span data-stu-id="81283-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="81283-107">例如，添加/删除图像、添加/删除文本和修改文本。</span><span class="sxs-lookup"><span data-stu-id="81283-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="81283-108">如果没有一个模板符合你的要求，你可以选择开始使用空白模板设计布局。</span><span class="sxs-lookup"><span data-stu-id="81283-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

<span data-ttu-id="81283-109">布局准备就绪后，使用自适应 [卡片模板](/adaptive-cards/templating/language) 语言创建用于定义结果类型的结果布局 JSON。</span><span class="sxs-lookup"><span data-stu-id="81283-109">After the layout is ready, use the [Adaptive Cards Template language](/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="81283-110">使用布局设计器中的"映射"步骤将结果属性映射到布局。</span><span class="sxs-lookup"><span data-stu-id="81283-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="81283-111">自行创建布局</span><span class="sxs-lookup"><span data-stu-id="81283-111">Create a layout on your own</span></span>

<span data-ttu-id="81283-112">自行创建布局需要了解自适应[卡片及其](/adaptive-cards/authoring-cards/getting-started)[架构](https://adaptivecards.io/explorer/)。</span><span class="sxs-lookup"><span data-stu-id="81283-112">Creating a layout on your own requires knowledge of [adaptive cards](/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="81283-113">搜索结果布局使用自适应卡片提供的部分元素，并且可以使用布局设计器了解受支持的元素集。</span><span class="sxs-lookup"><span data-stu-id="81283-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="81283-114">创建你自己的布局时，使用连接器的数据创建自适应卡片布局，然后完成布局。</span><span class="sxs-lookup"><span data-stu-id="81283-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="81283-115">创建你自己的布局有两个主要步骤：</span><span class="sxs-lookup"><span data-stu-id="81283-115">There are two main steps in creating your own layout:</span></span>

- <span data-ttu-id="81283-116">设计布局。</span><span class="sxs-lookup"><span data-stu-id="81283-116">Design the layout.</span></span>
- <span data-ttu-id="81283-117">将数据与模板分开。</span><span class="sxs-lookup"><span data-stu-id="81283-117">Separate the data from the template.</span></span>

### <a name="design-the-layout"></a><span data-ttu-id="81283-118">设计布局</span><span class="sxs-lookup"><span data-stu-id="81283-118">Design the layout</span></span>

<span data-ttu-id="81283-119">本示例中，我们显示了包含标题、链接和描述性文本的布局。</span><span class="sxs-lookup"><span data-stu-id="81283-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![包含标题、链接和说明的布局示例。](media/Verts-ExampleLayout.png)

<span data-ttu-id="81283-121">下面是布局的关联 JSON 文件：</span><span class="sxs-lookup"><span data-stu-id="81283-121">And here's the layout's associated JSON file:</span></span>

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

### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="81283-122">将数据与布局分开</span><span class="sxs-lookup"><span data-stu-id="81283-122">Separate the data from the layout</span></span>

<span data-ttu-id="81283-123">你可以将数据与布局分开并绑定数据。</span><span class="sxs-lookup"><span data-stu-id="81283-123">You can separate the data from the layout and bind the data.</span></span>

<span data-ttu-id="81283-124">下面是绑定数据后的布局 JSON：</span><span class="sxs-lookup"><span data-stu-id="81283-124">Here's Layout JSON after binding the data:</span></span>

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

<span data-ttu-id="81283-125">示例数据：在示例数据编辑器中指定 **示例** 数据，以在预览模式下查看数据 **绑定卡片**。</span><span class="sxs-lookup"><span data-stu-id="81283-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="81283-126">将布局映射到结果属性</span><span class="sxs-lookup"><span data-stu-id="81283-126">Map the layout to the result properties</span></span>

<span data-ttu-id="81283-127">必须将布局的每个字段映射到结果属性或连接器属性，以生成结果布局 JSON。</span><span class="sxs-lookup"><span data-stu-id="81283-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

!["搜索布局设计器"页上的示例布局的屏幕截图，其中选定了一个字段，并且属性窗格已打开。](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="81283-129">选择布局中的字段以突出显示需要映射的变量。</span><span class="sxs-lookup"><span data-stu-id="81283-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="81283-130">您可以对一个字段使用多个变量，并且所有字段都必须映射到结果属性。</span><span class="sxs-lookup"><span data-stu-id="81283-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

### <a name="show-snippet-on-search-result"></a><span data-ttu-id="81283-131">在搜索结果上显示代码段</span><span class="sxs-lookup"><span data-stu-id="81283-131">Show snippet on search result</span></span>  

<span data-ttu-id="81283-132">在连接器结果 **的内容属性** 上生成的动态代码段可以显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="81283-132">Dynamic snippets generated on the **content** property of the connector result can be shown on the search result.</span></span> <span data-ttu-id="81283-133">**ResultSnippet** 是一个系统属性，它充当针对每个 Connector 结果生成的代码段的占位符属性。</span><span class="sxs-lookup"><span data-stu-id="81283-133">**ResultSnippet** is the system property that acts as a placeholder property for the snippets generated for each Connector result.</span></span> <span data-ttu-id="81283-134">若要在结果布局上显示代码段 **，ResultSnippet** 系统属性必须映射到搜索结果布局中的相应字段，例如 Description。</span><span class="sxs-lookup"><span data-stu-id="81283-134">To show the snippets on the result layout, the **ResultSnippet** system property must be mapped to an appropriate field, for example Description, in the search result layout.</span></span> <span data-ttu-id="81283-135">在每个结果上生成的代码段还使用用户输入的查询词突出显示代码段中的匹配项。</span><span class="sxs-lookup"><span data-stu-id="81283-135">Snippets generated on each result also highlight the matches in the Snippet with the query term entered by the user.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="81283-136">注意事项</span><span class="sxs-lookup"><span data-stu-id="81283-136">Things to consider</span></span>

<span data-ttu-id="81283-137">在开始使用之前，应做一些操作，以及避免执行一些操作以确保布局成功。</span><span class="sxs-lookup"><span data-stu-id="81283-137">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="81283-138">允许事项</span><span class="sxs-lookup"><span data-stu-id="81283-138">Do</span></span>

- <span data-ttu-id="81283-139">如果要将静态链接用于徽标而不是结果属性，请编辑模板以在布局中提供徽标链接。</span><span class="sxs-lookup"><span data-stu-id="81283-139">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>
- <span data-ttu-id="81283-140">验证结果 JSON 中使用的结果属性未返回任何数据的方案的结果布局。</span><span class="sxs-lookup"><span data-stu-id="81283-140">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="81283-141">如果 `$when` 属性不包含数据，则使用 条件隐藏元素。</span><span class="sxs-lookup"><span data-stu-id="81283-141">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="81283-142">确保条件的数据类型 `$when` 与结果属性匹配。</span><span class="sxs-lookup"><span data-stu-id="81283-142">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="81283-143">例如，请勿在 `Number` 条件 `Text` 中 `$when` 进行比较。</span><span class="sxs-lookup"><span data-stu-id="81283-143">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="81283-144">在设计结果布局时考虑主题要求。</span><span class="sxs-lookup"><span data-stu-id="81283-144">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="81283-145">确保元素 `Textblock`   可以处理动态内容。</span><span class="sxs-lookup"><span data-stu-id="81283-145">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="81283-146">可以使用 和 `wrap` `maxLines` 元素属性来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="81283-146">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span>
- <span data-ttu-id="81283-147">在 Markdown 中使用时 `{DATE()}` 正确设置日期格式。</span><span class="sxs-lookup"><span data-stu-id="81283-147">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="81283-148">禁止事项</span><span class="sxs-lookup"><span data-stu-id="81283-148">Don't</span></span>

- <span data-ttu-id="81283-149">绑定值时不要定义无效的数据类型。</span><span class="sxs-lookup"><span data-stu-id="81283-149">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="81283-150">有关数据类型详细信息，请参阅 [管理搜索架构](/sharepoint/search/manage-the-search-schema)。</span><span class="sxs-lookup"><span data-stu-id="81283-150">For more information about data types, see [Manage the Search schema](/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="81283-151">避免按照结果布局 JSON 的最大高度在结果页面上裁剪结果。</span><span class="sxs-lookup"><span data-stu-id="81283-151">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="81283-152">如果超过结果布局的最大高度，将在结果页上裁剪结果。</span><span class="sxs-lookup"><span data-stu-id="81283-152">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="81283-153">不要在元素 `px` 属性中使用值。</span><span class="sxs-lookup"><span data-stu-id="81283-153">Don't use `px` values in element properties.</span></span>
- <span data-ttu-id="81283-154">不要在结果布局中将 markdown 与 **ResultSnippet** 属性一同用于突出显示搜索结果中的查询匹配。</span><span class="sxs-lookup"><span data-stu-id="81283-154">Don't use markdown with the **ResultSnippet** property in the result layout to highlight query match in the search result.</span></span>

## <a name="resources"></a><span data-ttu-id="81283-155">资源</span><span class="sxs-lookup"><span data-stu-id="81283-155">Resources</span></span>

[<span data-ttu-id="81283-156">自定义搜索结果页面</span><span class="sxs-lookup"><span data-stu-id="81283-156">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="81283-157">自适应卡片</span><span class="sxs-lookup"><span data-stu-id="81283-157">Adaptive cards</span></span>](/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="81283-158">自适应卡片模板语言</span><span class="sxs-lookup"><span data-stu-id="81283-158">Adaptive Cards Template language</span></span>](/adaptive-cards/templating/language)

[<span data-ttu-id="81283-159">自适应卡片架构</span><span class="sxs-lookup"><span data-stu-id="81283-159">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)