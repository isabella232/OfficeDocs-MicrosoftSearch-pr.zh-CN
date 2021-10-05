---
title: 管理结果类型
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
ROBOTS: NOINDEX
description: 在搜索结果页上管理结果类型
ms.openlocfilehash: ea6926a8923f4436f21047c9ac4cb95625ecb163
ms.sourcegitcommit: 967a02ee932f8a6cee70cfd78bb0c8b1b78d07c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127757"
---
# <a name="manage-result-types"></a>管理结果类型

您可以通过使用结果类型设计布局来定义搜索结果在 [搜索结果页面上的](customize-results-layout.md) 显示方式。 结果布局使您可以直接在搜索结果中显示有用的信息，以便用户可以快速找到他们所需要的信息。

内置内容类型（如文件和用户）具有无法修改的标准布局。 结果类型用于Graph[连接器](connectors-overview.md)内容。 使用属性映射配置连接器时，Microsoft 搜索将使用连接器搜索结果的默认搜索结果布局。 标签 *标题* 最重要;应始终为此标签分配一个属性，以使用默认的结果布局。 但是，为连接器内容创建自定义结果类型会使这些结果对用户产生更显著的影响。

使用垂直和连接器内容时，必须创建结果类型或执行默认布局的映射。 如果不这样做，垂直方向将不会显示任何搜索结果。

## <a name="understanding-result-types"></a>了解结果类型

创建您自己的 [搜索结果布局，](customize-results-layout.md) 然后通过创建结果类型覆盖默认搜索结果布局。 搜索结果类型是导致不同类型的搜索结果以不同方式显示的规则。 它由以下参数组成：

- **一个或多个条件**  比较每个搜索结果。 条件的示例包括内容源和标题。
-  **用于满足**   条件的搜索结果的结果布局。 生成的布局控制满足条件的结果在搜索结果页面上的显示方式。

您可以对垂直显示的内容使用多个结果类型。 当您将多个内容源组合到一个垂直方向时，这可能很重要。 它还可用于影响更大的布局，即使只有一个内容类型。 例如，在显示事件详细信息的垂直方向上，您可以将"高严重性"事件自定义为比"低严重性"事件更醒目的颜色。 可通过在"规则"部分中的"严重性"属性定义条件 **来** 完成此操作。

## <a name="create-or-update-result-types"></a>创建或更新结果类型

结果类型管理体验由向导驱动，指导你完成定义名称、内容源、规则和布局的步骤。 结果类型可以在组织级别和网站级别SharePoint自定义。

### <a name="manage-organization-level-result-types"></a>管理组织级别的结果类型

1. 在  [Microsoft 365 管理中心](https://admin.microsoft.com/)中，转到"[**自定义"部分**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)中的"结果 **类型"** 页。
2. 若要创建新的结果类型，请单击" **添加** "或选择一个现有结果类型进行编辑。
3. 配置结果类型后，你可以查看并保存它。

### <a name="manage-site-level-result-types"></a>管理网站级别结果类型

1. 在要管理结果类型的 Sharepoint 网站中，单击齿轮打开设置面板。
2. 选择 **"网站信息**"，然后选择"**查看所有网站设置"。**  
3. 查找"Microsoft 搜索"部分，然后选择" **配置搜索设置"。**
4. 在导航窗格中，转到"自定义体验"，然后选择"结果 **类型"。**
5. 若要添加结果类型，请单击"添加 **"。** 或者，若要编辑结果类型，请在列表中选择结果类型。
6. 修改结果类型后，可以审阅并保存结果类型。

## <a name="troubleshooting"></a>疑难解答

下面列出了你可能会看到的常见问题以及解决这些问题的操作。

|问题  |操作  |
|---------|---------|
| 我在搜索页面上看不到我的结果布局，尽管我创建了一个结果布局。 | 由于缓存了这些设置，因此可能有几分钟的延迟。 请等待几分钟，然后重试。        |
| 我在结果类型页面上看不到任何内容源。 | 确保已配置连接器和索引数据。   |
