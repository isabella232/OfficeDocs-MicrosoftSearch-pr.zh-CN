---
title: 映射 AAD 标识
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
ROBOTS: NOINDEX, NOFOLLOW
description: 有关如何映射 AAD 标识的步骤
ms.openlocfilehash: e373302314e3044f6bd6b874a341c8a1ada77556
ms.sourcegitcommit: 77ec27736f3c8434b2ac47e10897ac2606ee8a03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "48992842"
---
# <a name="map-your-azure-ad-identities"></a><span data-ttu-id="d555e-103">映射你的 Azure AD 标识</span><span class="sxs-lookup"><span data-stu-id="d555e-103">Map your Azure AD Identities</span></span>  

<span data-ttu-id="d555e-104">本文将引导您完成以下步骤：将 Azure AD 标识映射到数据源的唯一标识符 (非 Azure AD 标识) 以便您的访问控制列表中的人员 (具有非 Azure AD 标识的 ACL) 可以查看其范围内的连接器搜索结果。</span><span class="sxs-lookup"><span data-stu-id="d555e-104">This article walks you through the steps of mapping your Azure AD identities to a unique identifier for your data source (non-Azure AD identity) so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="d555e-105">这些步骤仅与使用搜索权限为 Microsoft 设置 [Salesforce](salesforce-connector.md) 连接器的搜索管理员（"仅有权访问此数据源的人" 和标识类型 "AAD"）相关。</span><span class="sxs-lookup"><span data-stu-id="d555e-105">These steps are only relevant to search administrators who are setting up a [Salesforce](salesforce-connector.md) connector by Microsoft with search permissions for "Only people with access to this data source" and identity type "AAD."</span></span> <span data-ttu-id="d555e-106">下面的步骤将引导您完成如何将 Azure AD 用户属性映射到用户的 **联合 id** 。</span><span class="sxs-lookup"><span data-stu-id="d555e-106">The following steps walk you through how to map your Azure AD user properties to your users' **Federation IDs**.</span></span>

>[!NOTE]
><span data-ttu-id="d555e-107">如果您正在设置 [Salesforce 连接器](salesforce-connector.md) ，并且仅选择 **具有此数据源访问权限的人员** 以及搜索权限屏幕上的标识类型 **非 AAD** ，请参阅 [映射您的非 azure ad 标识](map-non-aad.md) 一文，以了解有关如何映射非 azure ad 标识的步骤。</span><span class="sxs-lookup"><span data-stu-id="d555e-107">If you are setting up a [Salesforce connector](salesforce-connector.md) and select **Only people with access to this data source** and identity type **non-AAD** on the search permissions screen, refer to the [Map your non-Azure AD Identities](map-non-aad.md) article for steps on how to map non-Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-azure-ad-properties"></a><span data-ttu-id="d555e-108">映射 Azure AD 属性的步骤</span><span class="sxs-lookup"><span data-stu-id="d555e-108">Steps for mapping your Azure AD properties</span></span>

### <a name="1-select-azure-ad-user-properties-to-map"></a><span data-ttu-id="d555e-109">1. 选择要映射的 Azure AD 用户属性</span><span class="sxs-lookup"><span data-stu-id="d555e-109">1. Select Azure AD user properties to map</span></span>

<span data-ttu-id="d555e-110">你可以选择需要映射到联合 ID 的 Azure AD 属性。</span><span class="sxs-lookup"><span data-stu-id="d555e-110">You can select the Azure AD properties you need to map to the Federation ID.</span></span>

<span data-ttu-id="d555e-111">您可以从下拉列表中选择 Azure AD 用户属性。</span><span class="sxs-lookup"><span data-stu-id="d555e-111">You can select an Azure AD user property from the dropdown.</span></span> <span data-ttu-id="d555e-112">如果需要这些属性来创建组织的联合 ID 映射，则还可以添加任意数量的 Azure AD 用户属性。</span><span class="sxs-lookup"><span data-stu-id="d555e-112">You can also add as many Azure AD user properties as you would like if these properties are necessary to create the Federation ID mapping for your organization.</span></span>

### <a name="2-create-formula-to-complete-mapping"></a><span data-ttu-id="d555e-113">2. 创建用于完成映射的公式</span><span class="sxs-lookup"><span data-stu-id="d555e-113">2. Create formula to complete mapping</span></span>

<span data-ttu-id="d555e-114">你可以将 Azure AD 用户属性的值组合起来，以构成唯一联合 ID。</span><span class="sxs-lookup"><span data-stu-id="d555e-114">You can combine the values of the Azure AD user properties to form the unique Federation ID.</span></span>

<span data-ttu-id="d555e-115">在 "公式" 框中，" {0} " 对应于您选择的 *第一个* Azure AD 属性。</span><span class="sxs-lookup"><span data-stu-id="d555e-115">In the formula box, "{0}" corresponds to the *first* Azure AD property you selected.</span></span> <span data-ttu-id="d555e-116">" {1} " 对应于您选择的 *第二个* Azure AD 属性。</span><span class="sxs-lookup"><span data-stu-id="d555e-116">"{1}" corresponds to the *second* Azure AD property you selected.</span></span> <span data-ttu-id="d555e-117">" {2} " 对应于 *第三个* Azure AD 属性，依此类推。</span><span class="sxs-lookup"><span data-stu-id="d555e-117">"{2}" corresponds to the *third* Azure AD property, and so on.</span></span>  

<span data-ttu-id="d555e-118">下面是示例正则表达式输出和公式输出的一些公式示例：</span><span class="sxs-lookup"><span data-stu-id="d555e-118">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span>

| <span data-ttu-id="d555e-119">示例公式</span><span class="sxs-lookup"><span data-stu-id="d555e-119">Sample formula</span></span>                  | <span data-ttu-id="d555e-120">示例用户的属性值 {0}</span><span class="sxs-lookup"><span data-stu-id="d555e-120">Value of property {0} for a sample user</span></span>                 | <span data-ttu-id="d555e-121">示例用户的属性值 {1}</span><span class="sxs-lookup"><span data-stu-id="d555e-121">Value of property {1} for a sample user</span></span>           | <span data-ttu-id="d555e-122">公式的输出</span><span class="sxs-lookup"><span data-stu-id="d555e-122">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="d555e-123">{0}.{1}@contoso .com</span><span class="sxs-lookup"><span data-stu-id="d555e-123">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="d555e-124">段</span><span class="sxs-lookup"><span data-stu-id="d555e-124">firstname</span></span> | <span data-ttu-id="d555e-125">lastname</span><span class="sxs-lookup"><span data-stu-id="d555e-125">lastname</span></span> |<span data-ttu-id="d555e-126">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d555e-126">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="d555e-127">{0}@domain .com</span><span class="sxs-lookup"><span data-stu-id="d555e-127">{0}@domain.com</span></span>                 | <span data-ttu-id="d555e-128">userid</span><span class="sxs-lookup"><span data-stu-id="d555e-128">userid</span></span>                 |             |<span data-ttu-id="d555e-129">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="d555e-129">userid@domain.com</span></span>

<span data-ttu-id="d555e-130">在提供公式之后，您可以选择单击 " **预览** " 以查看数据源中5个随机用户的预览，并应用各自的用户映射。</span><span class="sxs-lookup"><span data-stu-id="d555e-130">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="d555e-131">预览的输出包括在步骤1中为这些用户选择的 Azure AD 用户属性的值，以及针对该用户的步骤2中提供的最后一个公式的输出。</span><span class="sxs-lookup"><span data-stu-id="d555e-131">The output of the preview includes the value of the Azure AD user properties selected in step 1 for those users and the output of the final formula provided in step 2 for that user.</span></span> <span data-ttu-id="d555e-132">它还指示是否可以通过 "成功" 或 "失败" 图标将公式的输出解析为租户中的 Azure AD 用户。</span><span class="sxs-lookup"><span data-stu-id="d555e-132">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="d555e-133">如果单击 " **预览** " 后，如果一个或多个用户映射的状态为 "失败"，则仍可以继续创建连接。</span><span class="sxs-lookup"><span data-stu-id="d555e-133">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="d555e-134">预览显示5个随机用户及其从您的数据源的映射。</span><span class="sxs-lookup"><span data-stu-id="d555e-134">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="d555e-135">如果您提供的映射不会映射所有用户，则可能会遇到这种情况。</span><span class="sxs-lookup"><span data-stu-id="d555e-135">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-azure-ad-mapping"></a><span data-ttu-id="d555e-136">示例 Azure AD 映射</span><span class="sxs-lookup"><span data-stu-id="d555e-136">Sample Azure AD mapping</span></span>

<span data-ttu-id="d555e-137">有关 Azure AD 映射的示例，请参阅下面的快照。</span><span class="sxs-lookup"><span data-stu-id="d555e-137">See the snapshot below for a sample Azure AD mapping.</span></span>

![如何填写 Azure AD 映射页的示例快照](media/aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="d555e-139">限制</span><span class="sxs-lookup"><span data-stu-id="d555e-139">Limitations</span></span>  

- <span data-ttu-id="d555e-140">所有用户仅支持一个映射。</span><span class="sxs-lookup"><span data-stu-id="d555e-140">Only one mapping is supported for all users.</span></span> <span data-ttu-id="d555e-141">不支持条件映射。</span><span class="sxs-lookup"><span data-stu-id="d555e-141">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="d555e-142">一旦发布连接，便无法更改映射。</span><span class="sxs-lookup"><span data-stu-id="d555e-142">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="d555e-143">Azure ad 用户属性的基于 Regex 的表达式不支持 Azure AD 到联合 ID 转换。</span><span class="sxs-lookup"><span data-stu-id="d555e-143">Regex-based expressions against the Azure AD user properties are not supported for the Azure AD to Federation ID transformation.</span></span>