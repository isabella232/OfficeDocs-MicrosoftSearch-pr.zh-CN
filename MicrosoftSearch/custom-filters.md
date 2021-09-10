---
title: 管理筛选器
ms.author: v-revathib
author: revathi-b
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 管理用于 SERP 的筛选器
ms.openlocfilehash: c614d4b60c746f2e18fdb3352281891ea5134373
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973381"
---
# <a name="manage-filters"></a>管理筛选器

筛选器允许用户优化其查询结果并显示优化的结果。 可以在自定义体验中自定义可供Microsoft 搜索筛选器。

搜索页面上有两种类型的筛选器可用。

- 开箱后筛选器
- 自定义筛选器

> [!NOTE]
> 自定义筛选器当前在定向发布中对管理员和最终用户处于预览阶段。 有关预览的详细信息，请参阅 [连接器预览功能](connectors-overview.md#what-are-the-preview-features)。

## <a name="out-of-the-box-filters"></a>开箱后筛选器

默认情况下，"全部"、"文件"、图像和"新闻"等垂直搜索中提供开箱即用筛选器。 在"All"和"File"垂直方向上，可以看到 FileType 属性上的"文件类型"筛选器，LastModifiedTime 属性上的"Last modified"筛选器。 这些筛选器在 SharePoint 主页、Office.com、SharePoint 网站和工作纵向必应。

## <a name="custom-filters"></a>自定义筛选器

筛选器可以添加到组织和网站级别的自定义垂直搜索。 可精简的托管属性用于在垂直管理向导中配置筛选器。  然后，可以基于连接属性在垂直方向创建自定义筛选器。 例如，可以在垂直方向为 ServiceNow 连接创建"发布时间"筛选器。

在组织范围内为纵向配置的筛选器将在组织范围内可用。 还可以在网站范围内配置筛选器。  

## <a name="create-organization-level-filters"></a>创建组织级别筛选器

1. 在  [Microsoft 365 管理中心](https://admin.microsoft.com/)中，转到  [**"垂直"**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. 选择要创建筛选器的首选垂直方向，然后单击"编辑 **"。**  
3. 导航到垂直向导中的"筛选器"步骤。
4. 单击 **"添加筛选器"** 以配置可精简托管属性的筛选器。
5. 添加筛选器后，你可以查看并保存垂直。

## <a name="create-sharepoint-site-level-filters"></a>创建SharePoint级别筛选器

1. 在 [SharePoint中心中](https://sharepoint.com/)，转到"设置"。
2. 查找"Microsoft 搜索"部分，然后选择"为此 **Microsoft 搜索配置网站集"。**
3. 在导航窗格中，转到"自定义体验"，然后选择" **垂直"。**
4. 选择您首选的垂直方向以创建筛选器，然后单击"编辑 **"。**
5. 导航到垂直向导中的"筛选器"步骤。
6. 单击 **"添加筛选器"** 以配置可精简托管属性的筛选器。
7. 添加筛选器后，你可以查看并保存垂直。

## <a name="filter-across-multiple-properties"></a>跨多个属性筛选

使用一个或多个内容源可创建垂直。 当使用多个内容源配置垂直时，精简程序的属性列表将显示每个可精简属性属于哪个内容源。 常用托管属性将基于名称或别名 (和) 数据类型。 还可以在这些常见属性上配置筛选器。 这是通过创建常见别名的筛选器，该筛选器对不同连接中的源属性进行别名设置。 例如，可以通过创建别名跨 ServiceNow **和** Jira 连接创建 Author 筛选器，如下所示：

 | Connection | 属性 | 别名 |
 | --- | --- | --- |
 | 服务现在 | 所有者 | 作者 |
 | Jira | Publisher | 作者 |

## <a name="important-details"></a>重要详细信息

- 筛选器只能添加到自定义垂直方向。 无法将新筛选器添加到"全部"、"文件"、"人员"、"网站"和"新闻"等开箱即用垂直位置。
- 筛选器可以针对 Text 和 DateTime 属性进行配置。
- 您总共只能有 50 个筛选器。
- 无法调整开箱即用筛选器的顺序。
- 内容不支持筛选器OneDrive筛选器。 与搜索结果对应的筛选器值OneDrive内容不会显示在筛选器上。
- 自定义筛选器值将显示来自内容SharePoint而不是 One Drive 内容的选项。例如，如果为"Author"创建自定义筛选器，并且 SharePoint 内容仅包含来自作者"Amy"的结果，并且 OneDrive 内容仅包含来自名为"John"的作者的结果，则"作者"自定义筛选器将显示"Amy"作为唯一选项。
- 为内容显示的SharePoint值将应用于OneDrive内容。
