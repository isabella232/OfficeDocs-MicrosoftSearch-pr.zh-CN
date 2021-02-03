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
ms.openlocfilehash: fb29fb9c14811698fb7c5d043853b57231c76a0b
ms.sourcegitcommit: d1bc6c41ecf47584373ce57543502bed55753d0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080834"
---
# <a name="graph-connectors-result-cluster"></a>图形连接器结果群集

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Graph 连接器结果群集 (预览)   

借助 Graph 连接器结果群集，企业可以在默认视图"所有"选项卡（SharePoint、Office.com 和必应中的 Microsoft 搜索）中搜索第三方数据源中的内容。

结果群集可帮助用户在一个地方发现所有第三方内容。 结果群集中显示的结果根据垂直搜索配置分组在一起。

## <a name="how-connector-results-are-selected-and-displayed"></a>如何选择和显示连接器结果

结果群集中提供的连接器结果派生自具有连接器内容的单个垂直搜索。 每个垂直搜索都提供一组成为候选结果群集的相关结果。 根据每个项目的"title"属性和"content"属性选择相关结果。 内容属性在架构上 *标记为 isContent=true。*

为了确保从垂直搜索发现内容，我们建议为项目提供有意义的标题。 这会对结果群集候选项的仲裁和内容在结果群集中出现的可能性产生积极的影响。 例如，避免将 ID 用作"title"属性的值，除非你的用户使用 ID 来查找内容。

显示结果群集的频繁程度因因素而异，例如配置垂直搜索的数量和内容类型。 通过交互或忽略结果群集，用户将隐式提供将随着时间的推移调整其触发的提示。

结果群集中显示的连接器项的搜索结果体验使用 [您定义](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) 的结果类型。 如果未配置结果类型，则使用 [系统生成的](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) 布局。 

我们建议将"title"属性用作搜索结果标题，将"content"属性用作搜索说明。 这将通过准确触发结果群集和群集中最相关的结果为用户提供最佳体验。 

## <a name="enable-result-clusters"></a>启用结果群集
  
默认情况下，结果群集体验已关闭。  

按照以下步骤在组织级别启用体验：

1. 在 [Microsoft 365 管理中心](https://admin.microsoft.com)中，转到 [**"垂直"。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. 选择"**全部** 垂直"，然后启用 **"显示连接器结果"。** 


请按照以下步骤在 SharePoint 网站级别打开体验：

1. 在想要获得结果群集体验的 SharePoint 网站上，转到"**设置"。**
2. 转到"**网站信息** > **查看所有网站设置"。**
3. 转到"Microsoft 搜索"部分，然后为此 **网站集选择"配置 Microsoft 搜索"。**
4. 在导航窗格中，转到"**自定义体验"，** 然后选择 **"垂直"。**
5. 选择"**全部** 垂直"，然后启用 **"显示连接器结果"。**

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>启用后查看结果群集体验

打开结果群集体验后，可能需要 12 小时才能查看它。 如果您需要立即体验，可以将 *cacheClear=true* 追加到 SharePoint 和 Office 中的 URL。
