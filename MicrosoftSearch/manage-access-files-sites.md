---
title: 管理对文件和网站的访问
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 概述管理员如何确保在其组织中正确限制对网站和文件的访问权限。
ms.openlocfilehash: c19442e1d89ddfe65a772213a8b0225ca680d699
ms.sourcegitcommit: 3e069fd920b5fcdfe97a0261930447e9e87d9013
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973775"
---
# <a name="manage-access-to-files-and-sites"></a>管理对文件和网站的访问

并非每个文件或网站都应该可供您组织中的每个人使用。 管理员和用户可以使用可最好地解决其特定问题的解决方案管理对敏感或机密信息的访问。 如果没有足够的访问控制不一致地应用，则可能会导致我们称其为"过度共享"。 通过更轻松地查找在组织中共享的信息，可能会无意中使用非正确限制访问具有不正确限制的文件Microsoft 搜索。

搜索管理员无法解决这些过度共享问题。 没有受限访问权限的文件和网站将显示于内部搜索结果中，并通过其他发现途径显示。 但是，当防止过度共享的控制已就位时，所有方法（包括搜索）都将关闭。

## <a name="solutions-to-prevent-oversharing"></a>防止过度共享的解决方案

使用以下工具、策略和技术来限制或模糊处理对信息的访问，以帮助防止过度共享。 实施这些解决方案可能需要全局、合规性或安全管理员访问权限。 我们还建议进行内部市场活动，以向用户介绍如何正确保护、标记和授予其网站和文件的安全、标签和权限。

### <a name="public-sites-or-sites-with-public-groups-as-owners"></a>公共网站或具有公共组作为所有者的网站

与所有人共享文件的一种方式是通过公共网站或具有公共组作为所有者的网站。 敏感度标签可阻止用户创建公共组或网站。 有关配置所有标签以创建专用组/网站和为组/网站管理标签的详细信息，请参阅使用敏感度标签保护[Microsoft Teams、Microsoft 365 组](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)和 SharePoint 网站中的内容。

另一个选项是控制谁可以在Microsoft 365组。 有关详细信息，请参阅[为需要创建组的用户](/microsoft-365/solutions/manage-creation-of-groups#step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups)创建Microsoft 365组。

实施上述任一解决方案时，我们还建议您为用户设置一个流程，以请求创建公共组并通知用户更改。

如果组织无法限制创建组的能力，则可以通过审核监视活动，包括组创建。 有关基本和高级审核的详细信息，请参阅审核[解决方案Microsoft 365。](/microsoft-365/compliance/auditing-solutions-overview)

### <a name="shared-files"></a>共享文件

若要限制对分类为业务敏感的所有文件的访问，您可以为组织定义和应用数据分类。 需要收集示例数据以帮助训练新的分类器。 有关先决条件和权限的详细信息，请参阅 [了解数据分类](/microsoft-365/compliance/data-classification-overview)。

若要限制对特定组的成员（如主管人员）的文件访问，可以创建范围限定为安全组的自定义标签。 然后，当安全组的成员应用标签时，它会自动限制对组的访问。 若要详细了解自定义标签，请参阅创建和[](/microsoft-365/compliance/create-sensitivity-labels)配置敏感度标签及其策略和使用敏感度标签应用加密来[限制对内容的访问](/microsoft-365/compliance/encryption-sensitivity-labels)。

为了确保文档和电子邮件正确标记，管理员还可以设置默认标签策略，并要求用户标记它们。 有关详细信息，请参阅[要求用户为其电子邮件和文档应用标签](/microsoft-365/compliance/sensitivity-labels-office-apps#require-users-to-apply-a-label-to-their-email-and-documents)。

通过阻止搜索时显示最近使用的文件，还可以最大程度地减少文件过度共享。 可以在组级别或为组织中的每个人完成此操作。 若要停止为组显示最近使用的文件，请参阅自定义 Microsoft Graph[中的项目见解隐私](/graph/insights-customize-item-insights-privacy)。 一个组的成员将能够查看他们自己的最近文件，但其他人将看到一条消息，指出未找到任何结果。 若要为组织中的每个人关闭最近使用的文件，你需要关闭Delve。 有关详细信息，请参阅[控制对 Delve 的访问](/sharepoint/delve-for-office-365-admins#control-access-to-delve)。

> [!Note]
> 用户仍可在结果中查找与用户Microsoft 搜索文件。 自定义项目见解或关闭Delve仅阻止文件显示在用户的最近文件列表中。

### <a name="sites-and-files-between-groups"></a>组之间的网站和文件

若要限制组之间的文件和网站共享，例如，由营销团队管理机密项目的财务团队，您可以定义和实施信息屏障策略。 这些障碍还会阻止通信和协作在Microsoft Teams、SharePoint和OneDrive。 有关详细信息，请参阅[了解Microsoft 365。](/microsoft-365/compliance/information-barriers)

## <a name="get-access-insights"></a>获取访问见解

访问管理提供有关组织中具有最敏感文档和过度共享网站的网站的见解。 有关概述，请参阅安全与合规中的新增功能[SharePoint OneDrive。](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-new-in-security-and-compliance-in-sharepoint-and-onedrive/ba-p/1696705) 你需要为此预览 [指定](https://forms.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) 你的组织。
