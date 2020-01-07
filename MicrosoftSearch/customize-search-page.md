---
title: 自定义 Microsoft Search 页面
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 添加搜索纵向和自定义搜索结果
ms.openlocfilehash: 852622c0c66afb996f941c609980a0d792af7364
ms.sourcegitcommit: c41334350654daef3a4cd45b5b18ea4401286997
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2020
ms.locfileid: "40947023"
---
# <a name="customize-the-search-results-page"></a>自定义搜索结果页

通过创建搜索纵向和结果类型，可以自定义在[Bing](https://Bing.com)中的[SharePoint](http://sharepoint.com/)、 [microsoft Office](https://Office.com)和 microsoft 搜索中搜索时向用户显示的搜索结果。 纵向使用户能够更轻松地查找他们有权查看的信息。 例如，您可以为市场营销部门的用户从第三方软件为市场营销分析数据创建纵向搜索。 您还可以定义结果类型并自定义此数据的布局。  

您可以在以下级别创建纵向和结果类型： 

- **组织级别**–如果您在组织级别添加垂直，则当用户从[SharePoint](http://sharepoint.com/)起始页、 [Office](https://Office.com)和[Bing](https://Bing.com)搜索时，它将显示在搜索结果页上。 
- **网站级别**–例如，您可能希望允许客户服务员工直接从其部门的 SharePoint 网站搜索**严重级别为 1**的事件。 

## <a name="whats-a-search-vertical"></a>垂直搜索是什么？

在 Microsoft 搜索结果页面的顶部是搜索纵向的一排选项卡。 垂直搜索仅显示特定类型或特定内容的结果。 例如，仅文件或新闻。 默认情况下，Microsoft Search 将显示**所有**行业、**人员**、**文件**、**网站**和**新闻**。  

您可以添加与您的组织相关的搜索纵向。 这些将显示在[SharePoint](http://sharepoint.com/)、 [Office](https://Office.com)和[Bing](https://Bing.com)中的 Microsoft 搜索结果页面上。 例如，您可以为与市场营销相关的内容创建一个垂直的，并根据每个组要拥有的信息类型创建另一个销售。 您可以将纵向添加到仅显示通过连接器索引的内容中的结果。  

**免责声明：** 在 Microsoft Graph 连接器预览中，纵向和结果类型当前处于预览阶段。 无法为驻留在[SharePoint](http://sharepoint.com/)中的内容或由[文件共享连接器](file-share-connector.md)编制索引的内容创建垂直。 若要了解有关预览的详细信息，请参阅[连接器预览](connectors-preview.md)。 若要参与预览，必须先提交[Microsoft Graph 连接器预览注册表单](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)。

## <a name="things-to-consider"></a>要考虑的事项 .。。

开始之前，请确保已对连接器编制索引。 它最长可能需要48个小时，具体取决于文件大小。

无法为驻留在[SharePoint](http://sharepoint.com/)中的内容或由[文件共享连接器](file-share-connector.md)编制索引的内容创建垂直。 了解如何为[内容编制索引](configure-connector.md)。

在高级别中，添加垂直的主要步骤有三个： 

1. 创建垂直。 在此步骤中，您将定义要搜索的内容的垂直名称、内容源和范围。 
2. 定义此垂直外观的效果。  
3. 启用垂直列表页中的垂直（显示）。   

## <a name="step-1-create-the-search-vertical"></a>步骤1：创建垂直搜索

启动向导后，您将通过这些步骤来定义要搜索的内容的垂直名称、内容源和范围。 垂直在禁用状态中创建。 稍后将启用垂直。

您可以使用一组有限的[关键字查询语言（KQL）](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)来缩小范围，并在页面中列出可供您使用的属性。 建议使用带有用于创建 KQL 的布尔运算符的自由文本关键字和属性限制。 

### <a name="create-a-vertical-at-the-organization-level"></a>在组织级别创建垂直

若要在[SharePoint](http://sharepoint.com/)主页、 [Office](https://Office.com)或[Bing](https://Bing.com)中的 Microsoft 搜索上创建垂直，请按照以下步骤操作：

1. 在 microsoft 365 [管理中心](https://admin.microsoft.com)，转到 " **设置** > **Microsoft Search** > **纵向**"。
1. 选择 " **添加**" 以开始。  

### <a name="create-a-vertical-at-the-site-level"></a>在网站级别创建垂直

1. 在要创建垂直的[SharePoint](http://sharepoint.com/)网站上，转到 "**设置**"。
1. 选择 "**网站信息**"，然后**查看 "所有网站设置**"。
1. 查找 " **Microsoft search** " 部分，然后为**此网站集选择 "配置 Microsoft search**"。
1. 在导航窗格中，转到 " **自定义体验**"，然后选择 "**纵向**" 选项卡。
1. 若要添加垂直，请选择 " **添加**"。 <br>
或 <br>若要编辑垂直，请在列表中选择它。

请记住，将在禁用状态下创建纵向。 您仍需要先启用它们，然后用户才能看到纵向。

## <a name="step-2-create-the-result-types"></a>步骤2：创建结果类型

您可以通过使用结果类型设计布局来定义结果在垂直方向的显示方式。 结果布局使您可以直接在搜索结果中显示重要信息，以便用户无需选择每个结果即可查看他们是否找到了要查找的内容。

搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。它包含以下几个方面：

- 用于比较每个搜索结果的**一个或多个条件**，例如搜索结果的内容源。  
- 要用于满足条件的搜索结果的**结果布局**。 结果布局控制满足条件的所有结果在搜索结果页面上的显示和行为的方式。

**必须至少创建一个结果类型，才能在垂直方向上显示。** 您可以为每个垂直创建多个结果类型，从而允许您对不同类型的结果使用不同的布局。 例如，您可以自定义**严重级别 1**事件，使其具有更突出的颜色和与**严重级别 3**事件相比较大的字体。 

启动向导后，您可以通过步骤来定义结果类型的名称、内容源和条件。 您可以从列表视图定义结果类型的优先级。 
  
### <a name="create-a-result-type-at-the-organization-level"></a>在组织级别创建结果类型

1. 在[管理中心](https://admin.microsoft.com)中，转到 "**设置** > **Microsoft Search**"，然后选择 "**结果类型**"。
1. 若要添加**结果类型**，请选择 " **添加**"。 若要编辑结果类型，请选择相关列表中的 "结果类型"。
 
### <a name="create-a-results-type-at-the-site-level"></a>在网站级别创建结果类型

1. 在要创建结果类型的[SharePoint](http://sharepoint.com/)网站上，转到 "**设置**"。
1. 选择 "**网站信息**"，然后**查看 "所有网站设置**"。 
1. 查找 "Microsoft Search" 部分，然后为**此网站集选择 "配置 Microsoft search**"。
1. 在导航窗格中，转到 " **自定义体验**"，然后选择 "**结果类型**" 选项卡。
1. 若要添加结果类型，请选择 " **添加**"。 <br> 或 <br>若要编辑结果类型，请在列表中选择 "结果类型"。

### <a name="view-the-vertical-after-enabling"></a>启用后查看垂直

在启用垂直后，可能需要一段时间才能进行查看。
如果要在启用后等待，请将**cacheClear = true**追加到[SharePoint](http://sharepoint.com/)和[Office](https://Office.com)中的 URL，以便立即查看垂直方向。

## <a name="troubleshooting"></a>故障排除

下面列出了您可能遇到的常见问题和解决这些问题的操作。


|Error  |Action  |
|---------|---------|
|我看到在垂直方向上*出现了错误的错误*。 |   需要直排和结果类型才能完成设置。 请确保已为相同的内容源创建了这两个。      |
|为什么我看不到结果布局，尽管我已经创建了一个？ | 要使用的结果类型需要几分钟时间，通常会缓存这些设置。 请等待几分钟，然后重试。        |
|在 "垂直" 或 "结果类型" 页上看不到任何内容源。     |      请确保已配置连接器和索引数据。   |



## <a name="next-steps"></a>后续步骤
[步骤3：自定义结果布局](customize-results-layout.md)
