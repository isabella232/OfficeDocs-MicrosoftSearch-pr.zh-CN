---
title: 'Dynamics 365 联合搜索 (预览) '
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: 管理 Dynamics 365 内容在搜索结果中的显示方式
ms.openlocfilehash: d2874febe39abf68653fa82d6a50121ebd1a357b
ms.sourcegitcommit: fbe565b1a8994425b4f7ff0114a69044659e3892
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2021
ms.locfileid: "58380030"
---
# <a name="dynamics-365-federation-search-preview"></a>Dynamics 365 联合搜索 (预览) 

## <a name="microsoft-search-federation-and-connectors"></a>Microsoft 搜索联合身份验证和连接器

为了帮助使Microsoft 搜索更有用，我们引入了联合Microsoft 搜索联合。 通过联合搜索，组织可以在以下网站中访问这些方案Microsoft 搜索：

* 系统符合严格合规性要求的数据
* 无法离开系统边界的数据
* 存储在你的组织不希望在云上编制索引的敏感数据

通过联合搜索连接访问的数据在索引中Microsoft 搜索。 此外，使用 Microsoft 的内置连接器可轻松设置联合搜索连接。 我们的 Dynamics 365 连接器目前处于预览阶段。 如果你对加入预览版感兴趣，请通过 以下版本[aka.ms/D365FederationSearchPreview。](https://aka.ms/D365FederationSearchPreview) 有关发布时间框架，请参阅Microsoft 搜索[路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Search)。

## <a name="dynamics-365-federation-connector"></a>Dynamics 365 联合连接器

Microsoft Dynamics 365 是一系列智能业务应用程序，设计用于企业资源规划和客户关系管理。 借助 Dynamics 365 联合身份验证，Microsoft 搜索提供无缝搜索体验，使用户能够轻松找到存储在 Dynamics 365 中的最相关的客户和业务数据。 Dynamics 365 联合连接器提供了一些关键优势：

* **易于管理：** 配置和维护与 Dynamics 365 实例的搜索连接的简化过程。
* **易于使用：** 用户可以轻松快速地找到存储在 Dynamics 365 中的关键信息，包括帐户、联系人、打开的机会等。
* **更丰富的内容：** 若要使 Dynamics 365 搜索结果更有用，它们包括主要信息，如潜在客户、联系人和帐户详细信息。
* **内置数据保护：** Dynamics 365 结果将仅为有权访问已连接实例的用户显示。
* **统一搜索体验：** 为了保持一致的体验，Dynamics 365 结果在所有搜索入口点中保持一致。 无论您在何处搜索，您都具有相同的外观和感觉。

## <a name="what-users-experience"></a>用户体验

Dynamics 365 答案将显示在所有 Microsoft 搜索 画布的搜索结果中，包括 SharePoint Online、必应 和 Office。

:::image type="content" alt-text="SharePoint、必应 和 Office 上的 Dynamics 365 Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

从答案中，使用"更多 Dynamics 365 结果"链接可以轻松查看更多 **Dynamics 365** 搜索结果。 它将用户带进专用 Dynamics 365 结果页，该页面包含更多与查询相关的结果。

:::image type="content" alt-text="Dynamics 365 垂直版和 SharePoint、必应 和 Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

单击或点击任何结果将打开 Dynamics 365，然后显示详细信息。

:::image type="content" alt-text="Dynamics 365 中详细信息页面的屏幕截图" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

无论用户在何处开始搜索，他们的体验都将保持一致，并使用户能够快速找到最相关的 Dynamics 365 结果。 请查看我们的 Microsoft Build 2021 视频进行演示。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4P83t]

## <a name="supported-query-patterns"></a>支持的查询模式

当使用自然语言和产品名称查询来查找 Dynamics 365 Microsoft 搜索支持自然语言和产品名称查询。 此外，Dynamics 365 查询不区分大小写。 使用自然语言模式（按客户名称或位置）和其他常用查询查找联系人、帐户和机会。 下面是一些示例：

* Who是 Contoso 的联系人
* Contoso 的打开机会
* 西雅图的打开机会是什么
* 西雅图的帐户是什么
* 西雅图的联系人是什么
* 我本月结束的潜在客户是什么
* 高优先级电话呼叫
* 联系缺少的电子邮件

产品名称模式支持一系列 Dynamics 365 应用程序，并且将触发 Dynamics 365 结果，而不管它们在查询中的显示位置如何：

* D365
* Dynamics 365
* Dynamics365
* Dynamics CRM
* Dynamics Sales
* Dynamics Customer Service
* Dynamics Service
* Dynamics Field Service

## <a name="configure-the-dynamics-365-connector"></a>配置 Dynamics 365 连接器

通过此简单配置，您可以为组织人员启用 Dynamics 365 联合搜索体验。

1. 在Microsoft 365 管理中心[中](https://admin.microsoft.com)，转到"[数据源"。](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors)

2. 在"Microsoft 应用和服务"部分中的"Microsoft Dynamics 365"下，选择"管理"以打开 Microsoft Dynamics 365 面板。 

3. 为组织启用连接器。

4. 在" **终结点"** 列表中，选择 Dynamics 365 环境。

5. 在" **连接 ID"** 中，为此连接输入唯一 ID。

6. 查看并选中同意复选框。

7. 选择 **"保存** "完成连接设置。

:::image type="content" alt-text="Dynamics 365 设置面板的屏幕截图Microsoft 365 管理中心" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

设置完成后，只有具有有效 Dynamics 365 许可证的用户以及访问连接的 Dynamics 365 环境时，Dynamics 365 回答和垂直显示。 您随时都可以返回到这些设置，并更改连接终结点环境或停用连接。
