---
title: 自定义 Microsoft Search 页面
ms.author: jypal6
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
description: 添加搜索纵向和自定义搜索结果
ms.openlocfilehash: 60ab3423db0a86982df9c4332f0f22267c49dc04
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996055"
---
# <a name="customize-the-search-results-page"></a>自定义搜索结果页

您可以创建搜索纵向和结果类型，以自定义用户在[Bing](https://bing.com)中的 microsoft [SharePoint](https://sharepoint.com/)、 [microsoft Office](https://office.com)和 microsoft 搜索中进行搜索时看到的搜索结果。 纵向使用户能够更轻松地查找他们有权查看的信息。 例如，可以为市场营销部门中的用户创建从第三方软件到第三方软件的市场营销分析数据的垂直搜索。 您还可以定义结果类型并自定义此数据的布局。  

您可以在以下级别创建纵向和结果类型：

- **组织级别**–如果在组织级别添加垂直，则当用户从[SharePoint](https://sharepoint.com/)起始页、 [Office](https://office.com)或[Bing](https://bing.com)进行搜索时，它将显示在搜索结果页上。
- **网站级别**–例如，您可能希望使客户服务员工能够直接从其部门的 SharePoint 网站搜索*严重级别为 1*的事件。

## <a name="search-verticals-explained"></a>介绍的搜索纵向

在 Microsoft 搜索结果页面的顶部有一排选项卡。 这些是搜索纵向。 垂直搜索仅显示特定类型或特定内容的结果。 例如，**文件**或**新闻**。 默认情况下，Microsoft Search 将显示**所有**行业、**人员**、**文件**、**网站**和**新闻**。  

您可以添加与您的组织相关的搜索纵向。 这些将显示在[SharePoint](https://sharepoint.com/)、 [Office](https://Office.com)和[Bing](https://bing.com)中的 Microsoft 搜索结果页面上。 例如，您可以为与市场营销相关的内容创建一个垂直的，并根据每个组需要的信息类型创建另一个销售。 您可以将纵向添加到仅显示通过连接器索引的内容中的结果。  

>[!NOTE]
> 在 Microsoft Graph 连接器预览中，纵向和结果类型当前处于预览阶段。 有关预览的详细信息，请参阅[连接器预览](connectors-preview.md)。 若要参与预览，必须先提交[Microsoft Graph 连接器预览注册表单](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)。

## <a name="things-to-consider"></a>注意事项

开始之前，请确保已对连接器编制索引。 这可能最长为48个小时，具体取决于文件大小。

无法为驻留在[SharePoint](https://sharepoint.com/)中的内容或由[文件共享连接器](file-share-connector.md)编制索引的内容创建垂直。 了解如何为[内容编制索引](configure-connector.md)。

有三个基本步骤可添加垂直：

1. 创建垂直。 在此步骤中，您将定义要搜索的内容的垂直名称、内容源和范围。
2. 定义此垂直外观的效果。  
3. 启用垂直列表页中的垂直（显示）。

## <a name="step-1-create-the-search-vertical"></a>步骤1：创建垂直搜索

启动向导后，您可以通过步骤来定义要搜索的内容的垂直名称、内容源和范围。 垂直在禁用状态中创建。 你将在稍后启用它。

您可以使用一组有限的[关键字查询语言（KQL）](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)来缩小范围。 此页列出了可用的属性。 我们建议您将 freetext 关键字和属性限制用于用于创建 KQL 的布尔运算符。

### <a name="create-a-vertical-at-the-organization-level"></a>在组织级别创建垂直

若要在[SharePoint](https://sharepoint.com/)主页、 [Office](https://office.com)或[Bing](https://bing.com)中的 Microsoft 搜索上创建垂直，请按照以下步骤操作：

1. 在 microsoft 365 [管理中心](https://admin.microsoft.com)，转到 " **设置**   >  **Microsoft Search**   >  **自定义**  >  [**纵向**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)"。
1. 选择 " **添加**" 以开始。  

### <a name="create-a-vertical-at-the-site-level"></a>在网站级别创建垂直

1. 在您希望垂直的[SharePoint](https://sharepoint.com/)网站上，转到 "**设置**"。
1. 选择 "**网站信息**"，然后**查看 "所有网站设置**"。
1. 查找 " **Microsoft search** " 部分，然后为**此网站集选择 "配置 Microsoft search**"。
1. 在导航窗格中，转到 " **自定义体验**"，然后选择 "**纵向**" 选项卡。
1. 若要添加垂直，请选择 " **添加**"。
  或者，若要编辑垂直，请在列表中选择它。

请记住，将在禁用状态下创建纵向。 必须先启用它们，然后用户才能看到它们。

## <a name="step-2-create-the-result-types"></a>步骤2：创建结果类型

您可以通过使用结果类型设计布局来定义结果在垂直方向的显示方式。 结果布局可让您直接在搜索结果中显示重要信息，因此用户无需选择每个结果即可查看他们是否找到了要查找的内容。

搜索结果类型是使不同类型的搜索结果以不同方式显示的规则。它包含以下几个方面：

- 用于比较每个搜索结果的**一个或多个条件**，例如搜索结果的内容源。  
- 要用于满足条件的搜索结果的**结果布局**。 结果布局控制满足条件的所有结果在搜索结果页面上的显示和行为方式。

**必须至少创建一个结果类型，才能在垂直方向上显示。** 您可以为每个垂直创建多个结果类型，从而允许您对不同类型的结果使用不同的布局。 例如，您可以自定义*严重级别 1*事件，使其具有更突出的颜色和与*严重级别 3*事件相比较大的字体。

启动向导后，您可以通过步骤来定义结果类型的名称、内容源和条件。 您可以从列表视图定义结果类型的优先级。
  
### <a name="create-a-result-type-at-the-organization-level"></a>在组织级别创建结果类型

1. 在[管理中心](https://admin.microsoft.com)中，转到 "**设置**  >  **Microsoft Search**  >  **自定义项**  >  [**结果类型**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)"。
1. 若要添加**结果类型**，请选择 " **添加**"。 若要编辑结果类型，请选择相关列表中的 "结果类型"。

### <a name="create-a-results-type-at-the-site-level"></a>在网站级别创建结果类型

1. 在要创建结果类型的[SharePoint](https://sharepoint.com/)网站上，转到 "**设置**"。
1. 选择 "**网站信息**"，然后**查看 "所有网站设置**"。
1. 查找 "Microsoft Search" 部分，然后为**此网站集选择 "配置 Microsoft search**"。
1. 在导航窗格中，转到 " **自定义体验**"，然后选择 "**结果类型**" 选项卡。
2. 若要添加结果类型，请选择 " **添加**"。  或者，若要编辑结果类型，请在列表中选择 "结果类型"。

### <a name="view-the-vertical-after-its-enabled"></a>在已启用时查看垂直

在启用垂直后，可能需要一段时间才能进行查看。 如果您不希望在启用后等待，则可以将**cacheClear = true**追加到[SharePoint](https://sharepoint.com/)和[Office](https://office.com)中的 URL，以便立即查看垂直方向。

## <a name="troubleshooting"></a>疑难解答

下面列出了你可能遇到的常见问题和解决这些问题的措施。

|错误  |Action  |
|---------|---------|
| 我在垂直处看到 "出现了错误" 错误消息。 | 需要垂直和结果类型才能完成设置。 请确保已为相同的内容源创建了这两个。 |
| 我看不到结果布局，尽管我创建了它。 | 此过程需要几分钟时间，因为通常会缓存这些设置。 请等待几分钟，然后重试。        |
| 在 "垂直" 或 "结果类型" 页上看不到任何内容源。 | 请确保已配置连接器和索引数据。   |

## <a name="next-steps"></a>后续步骤

[步骤3：自定义结果布局](customize-results-layout.md)
