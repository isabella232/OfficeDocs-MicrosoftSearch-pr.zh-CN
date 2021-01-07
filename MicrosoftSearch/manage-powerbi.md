---
title: 管理 Power BI 答案
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: 管理 Power BI 报告和数据在搜索结果中的显示方式
ms.openlocfilehash: e78b8b5d22f7a91d80832fb4f5b536afc277fb6c
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773042"
---
# <a name="manage-power-bi-answers"></a>管理 Power BI 答案

为了便于用户查找他们做出明智决定所需的数据和分析，Microsoft 搜索增加了对 Power BI 仪表板和报告的支持。 以下是 Power BI 搜索的一些优势：

* **易于使用：** 此开箱即用搜索体验可帮助用户轻松快速地查找整个组织的 Power BI 仪表板和报告。
* **更丰富的内容：** 若要使 Power BI 搜索结果更有用，它们包括内容类型（仪表板或报表）以及拥有它的团队或人员等关键信息。
* **内置数据保护：** Power BI 结果将仅为有权访问仪表板或报表的用户显示。
* **统一搜索体验：** 为了保持一致的体验，Power BI 结果在所有搜索入口点都是一致的。 无论您在何处搜索，您都具有相同的外观和感觉。

## <a name="what-users-experience"></a>用户体验

Microsoft 搜索用户可以通过从 Windows 搜索框、SharePoint、Office 365 和必应进行搜索来查找 Power BI 结果。 用户可以使用如下所示的查询搜索报告和仪表板：

* Power BI about `<topic>`
* Power BI for `<topic>`
* `<topic>` Power BI 仪表板或 Power BI 仪表板 `<topic>`
* `<topic>` Power BI 报表或 Power BI 报表 `<topic>`
* `<topic>` Power BI 指标或 Power BI 指标 `<topic>`
* `<topic>` Power BI 记分卡或 Power BI 记分卡 `<topic>`

将上面的示例中替换为要查找的信息（如销售、使用情况、容量 `<topic>` 、2021、Q1 等）以查看 Power BI 的相关结果。

:::image type="content" source="media/powerbi-answers/powerbi-serp.png" alt-text="带 Power BI 答案和垂直的 SERP 屏幕截图" border="true":::

## <a name="turn-power-bi-search-on-or-off"></a>打开或关闭 Power BI 搜索

默认情况下，为组织启用 Power BI 结果。 Power BI 管理员可以随时禁用它们。 在 Power BI 管理门户中，转到"租户设置"并禁用"对 **Power BI 使用** 全局搜索"设置。 若要了解更多信息，请参阅[管理门户中的管理 Power BI。](https://docs.microsoft.com/power-bi/admin/service-admin-portal#use-global-search-for-power-bi-preview)

:::image type="content" source="media/powerbi-answers/powerbi-admin.png" alt-text="用于打开或关闭 Power BI 答案的设置屏幕截图" border="true":::

## <a name="frequently-asked-questions"></a>常见问题解答

**问：默认情况下是否启用 Power BI 搜索？**

**答：** 是的。 默认情况下，为 Microsoft 搜索启用 Power BI 搜索。 租户管理员无需首次设置此功能。

**问：能否为特定组或用户启用或禁用 Power BI 搜索？**

**答：** 目前，只能为整个组织启用或禁用它。

**问：如果禁用 Power BI 搜索，是否隐藏 Power BI 搜索结果页面？**

**答：** 不。 Power BI 搜索结果页面将显示一条消息，通知用户当前不适用于其组织。

**问：如果没有 Power BI 许可证，我会看到 Power BI 搜索结果页面吗？**

**答：** 不。 如果搜索用户没有 Power BI 许可证，Power BI 搜索结果页将不会显示在 Microsoft 搜索结果中。

**问：我能否看到无法访问的 Power BI 搜索结果？**

**答：** 不。 Microsoft 搜索将仅返回你有权访问的 Power BI 结果。

**问：我能否自定义 Power BI 搜索结果 (例如，报告类型或报告所有者) ？**

**答：** 目前，我们不支持自定义 Power BI 搜索结果中包含的字段。
