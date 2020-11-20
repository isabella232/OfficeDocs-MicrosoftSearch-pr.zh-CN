---
title: 映射非 AAD 标识
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 如何映射非 AAD 标识的步骤
ms.openlocfilehash: cd7d0eb17678d69ec1966e4472b38c1f18c30809
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367655"
---
# <a name="map-your-non-azure-ad-identities"></a>映射你的非 Azure AD 标识  

本文将引导您完成将非 Azure AD 标识映射到 Azure AD 标识的步骤，以便访问控制列表中的人员 (具有非 Azure AD 标识的 ACL) 可以查看连接器搜索结果的范围。

这些步骤仅适用于使用搜索权限为 Microsoft 设置 [ServiceNow](servicenow-connector.md) 或 [Salesforce](salesforce-connector.md) 连接器的搜索管理员，其中 "仅具有访问此数据源的人员" 和 "非 AAD" 标识类型。

>[!NOTE]
>如果您正在设置 Salesforce 连接器，并且仅选择 " **具有此数据源访问权限的用户** " 和 "在搜索权限屏幕上标识类型为 **AAD** "，请参阅 [映射 azure ad 标识](map-aad.md) 一文，了解如何映射 azure ad 标识的步骤。  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a>映射非 Azure AD 属性的步骤

### <a name="1-select-an-azure-ad-user-property"></a>1. 选择 Azure AD 用户属性  

您可以选择要为其创建映射的 Azure AD 用户属性。 这是您想要将非 Azure AD 标识映射到的目标属性。  

你可以选择以下 Azure AD 属性之一：

| Azure AD 属性    | 定义           | 示例         |
| :------------------- | :------------------- |:--------------- |
| 用户主体名称 (UPN)  | UPN 由 UPN 前缀 (用户帐户名称) 和 (DNS 域名) 的 UPN 后缀组成。 使用 "@" 符号将前缀与后缀联接起来。 | us1@contoso.onmicrosoft.com |
| Azure AD ID                 | 给定用户的 Azure AD ID 是用户的唯一 GUID。                 | 58006c96-9e6e-45ea-8c88-4a56851eefad            |
|  (SID) 的 Active Directory 安全 ID                  | SID (安全标识符) 是 Active Directory 用于将对象标识为安全主体的唯一标识符。                  | S-1-5-21-453406510-812318184-4183662089             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a>2. 选择要映射的非 Azure AD 用户属性

您可以从您的数据源中选择要应用正则表达式的非 Azure AD 属性。 若要了解有关在数据源中查找这些属性的位置的详细信息，请参阅 [ServiceNow](servicenow-connector.md) 和 [Salesforce](salesforce-connector.md) 页面。  

您可以从下拉列表中选择非 Azure AD 用户属性，并提供要应用于这些用户属性值的正则表达式。 若要了解有关正则表达式的详细信息，请参阅 [正则表达式引用]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference)。  

下面是应用于示例字符串的正则表达式和输出的一些示例： 

| 示例字符串                  | 正则表达式                 | 示例字符串上的正则表达式的输出           |
| :------------------- | :------------------- |:---------------|
| Alexis Vasquez  | .* | Alexis Vasquez |
| Alexis Vasquez                 | ..$                 | ez            |
| Alexis Vasquez                  |  ( \w +) $                  | Vasquez             |

您可以添加任意多个非 Azure AD 用户属性，就像您喜欢的表达式一样。 如果最终公式保证，可以将不同的正则表达式应用于相同的用户属性。  

### <a name="3-create-formula-to-complete-mapping"></a>3. 创建用于完成映射的公式

您可以将应用于每个非 Azure AD 用户属性的正则表达式的输出组合起来，以构成在步骤1中选择的 Azure AD 属性。

在 "公式" 框中，" {0} " 对应于应用于所选的 *第一个* 非 Azure AD 属性的正则表达式的输出。 " {1} " 对应于应用于所选的 *第二个* 非 Azure AD 属性的正则表达式的输出。 " {2} " 对应于应用于 *第三个* 非 Azure AD 属性的正则表达式的输出，依此类推。  

下面是示例正则表达式输出和公式输出的一些公式示例： 

| 示例公式                  | {0}示例用户的值                 | {1}示例用户的值           | 公式的输出                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1}@contoso .com  | 段 | lastname |firstname.lastname@contoso.com
| {0}@domain .com                 | userid                 |             |userid@domain.com

在提供公式之后，您可以选择单击 " **预览** " 以查看数据源中5个随机用户的预览，并应用各自的用户映射。 预览的输出包括在步骤2中为这些用户选择的非 Azure AD 用户属性的值，以及针对该用户的步骤3中提供的最后一个公式的输出。 它还指示是否可以通过 "成功" 或 "失败" 图标将公式的输出解析为租户中的 Azure AD 用户。  

>[!NOTE]
>如果单击 " **预览**" 后，如果一个或多个用户映射的状态为 "失败"，则仍可以继续创建连接。 预览显示5个随机用户及其从您的数据源的映射。 如果您提供的映射不会映射所有用户，则可能会遇到这种情况。

## <a name="sample-non-azure-ad-mapping"></a>非 Azure AD 映射示例

有关非 Azure AD 映射示例，请参阅下面的快照。

![如何填写非 Azure AD 映射页的示例快照](media/non-aad-mapping.png)

## <a name="limitations"></a>限制  

- 所有用户仅支持一个映射。 不支持条件映射。  

- 一旦发布连接，便无法更改映射。  

- 对于转换，目前仅支持针对非 AAD 用户属性的基于 regex 的表达式。

- 只有3个 Azure AD 标识可以选择映射到 (UPN、Azure AD ID 和 AD SID) 。