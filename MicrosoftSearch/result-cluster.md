---
title: 连接器结果群集
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 连接器结果群集体验的详细信息
ms.openlocfilehash: fa6ac2dc720ed43e40454b952526734accd45ea4
ms.sourcegitcommit: a328b9764abf5cd0c1c0a8c7def0c6e334da9a1d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477110"
---
# <a name="graph-connectors-result-cluster"></a>图形连接器结果群集

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>图形连接器结果群集 (预览的概述)   

通过 Graph 连接器的结果群集，企业可以在其默认视图中搜索第三方数据源中的内容， (SharePoint 和 Office.com 中的所有选项卡) 。

结果群集可帮助用户发现所有第三方内容 (previoulsy 绑定到一个位置中的单个连接器和垂直) 。 结果群集中显示的结果根据租户管理员在垂直搜索中配置它们的方式分组在一起。  

## <a name="how-connector-results-are-selected-and-displayed"></a>如何选择和显示连接器结果

结果群集中提供的连接器结果派生自各个搜索带连接器内容的纵向。 每个垂直搜索提供一组相关结果，这些结果将成为候选结果群集。 根据每个项目的 "title" 属性、结果代码段和内容组件选择相关结果。

为确保从搜索纵向发现内容，我们建议为您的项目提供有意义的标题。 这将影响结果群集候选人的仲裁，以及你的内容在结果群集中显示的可能性。 例如，除非用户使用 Id 查找内容，否则请避免使用 Id 作为属性 "title" 的值。

结果群集显示的频率因各种因素（如您配置的搜索纵向数量和内容类型）而异。 通过选择或忽略结果群集结果，您将隐式提供一些提示，这些提示将调整对结果群集触发的时间。

结果群集中显示的连接器项目的搜索结果体验是系统生成的，不使用自定义的结果布局。 如果希望结果群集中显示结果，则必须在连接注册过程中声明 "title" 属性和项目内容。

## <a name="enable-result-clusters"></a>启用结果群集
  
默认情况下，结果群集体验处于关闭状态。  

按照以下步骤在组织级别启用体验：

1. 在 [Microsoft 365 管理中心](https://admin.microsoft.com/)，转到 "**设置**  >  **搜索 & 智能**  >  **自定义**  >  **纵向**"。  
2. 选择 " **全部** 垂直"，然后按 "启用 **显示连接器结果**"。 


按照以下步骤在网站级别启用体验：

1. 在您希望结果群集体验的 SharePoint 网站上，转到 " **设置**"。
2. 转到 "**网站信息**" > **查看所有网站设置**。
3. 转到 "Microsoft Search" 部分，然后为 **此网站集选择 "配置 Microsoft search**"。
4. 在导航窗格中，转到 " **自定义体验**"，然后选择 " **纵向**"。
5. 选择 " **全部** 垂直"，然后按 "启用 **显示连接器结果**"。

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>启用后查看结果群集体验

打开结果群集体验后，可能需要几分钟的时间才能查看。 如果你想要立即体验，可以将 *cacheClear = true* 追加到 SharePoint 和 Office 中的 URL。
