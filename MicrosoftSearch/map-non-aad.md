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
# <a name="map-your-non-azure-ad-identities"></a><span data-ttu-id="8ee23-103">映射你的非 Azure AD 标识</span><span class="sxs-lookup"><span data-stu-id="8ee23-103">Map your non-Azure AD Identities</span></span>  

<span data-ttu-id="8ee23-104">本文将引导您完成将非 Azure AD 标识映射到 Azure AD 标识的步骤，以便访问控制列表中的人员 (具有非 Azure AD 标识的 ACL) 可以查看连接器搜索结果的范围。</span><span class="sxs-lookup"><span data-stu-id="8ee23-104">This article walks you through the steps of mapping your non-Azure AD identities to your Azure AD identities so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="8ee23-105">这些步骤仅适用于使用搜索权限为 Microsoft 设置 [ServiceNow](servicenow-connector.md) 或 [Salesforce](salesforce-connector.md) 连接器的搜索管理员，其中 "仅具有访问此数据源的人员" 和 "非 AAD" 标识类型。</span><span class="sxs-lookup"><span data-stu-id="8ee23-105">These steps are only relevant to search administrators who are setting up a [ServiceNow](servicenow-connector.md) or [Salesforce](salesforce-connector.md) connectors by Microsoft with search permissions for "Only people with access to this data source" and identity type "Non-AAD."</span></span>

>[!NOTE]
><span data-ttu-id="8ee23-106">如果您正在设置 Salesforce 连接器，并且仅选择 " **具有此数据源访问权限的用户** " 和 "在搜索权限屏幕上标识类型为 **AAD** "，请参阅 [映射 azure ad 标识](map-aad.md) 一文，了解如何映射 azure ad 标识的步骤。</span><span class="sxs-lookup"><span data-stu-id="8ee23-106">If you are setting up a Salesforce connector and select **Only people with access to this data source** and identity type **AAD** on the search permissions screen, refer to the [Map your Azure AD Identities](map-aad.md) article for steps on how to map Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a><span data-ttu-id="8ee23-107">映射非 Azure AD 属性的步骤</span><span class="sxs-lookup"><span data-stu-id="8ee23-107">Steps for mapping your non-Azure AD properties</span></span>

### <a name="1-select-an-azure-ad-user-property"></a><span data-ttu-id="8ee23-108">1. 选择 Azure AD 用户属性</span><span class="sxs-lookup"><span data-stu-id="8ee23-108">1. Select an Azure AD user property</span></span>  

<span data-ttu-id="8ee23-109">您可以选择要为其创建映射的 Azure AD 用户属性。</span><span class="sxs-lookup"><span data-stu-id="8ee23-109">You can select the Azure AD user property you are creating the mapping for.</span></span> <span data-ttu-id="8ee23-110">这是您想要将非 Azure AD 标识映射到的目标属性。</span><span class="sxs-lookup"><span data-stu-id="8ee23-110">This is the target property you are aiming to map your non-Azure AD identities to.</span></span>  

<span data-ttu-id="8ee23-111">你可以选择以下 Azure AD 属性之一：</span><span class="sxs-lookup"><span data-stu-id="8ee23-111">You can select one of the following Azure AD properties:</span></span>

| <span data-ttu-id="8ee23-112">Azure AD 属性</span><span class="sxs-lookup"><span data-stu-id="8ee23-112">Azure AD property</span></span>    | <span data-ttu-id="8ee23-113">定义</span><span class="sxs-lookup"><span data-stu-id="8ee23-113">Definition</span></span>           | <span data-ttu-id="8ee23-114">示例</span><span class="sxs-lookup"><span data-stu-id="8ee23-114">Example</span></span>         |
| :------------------- | :------------------- |:--------------- |
| <span data-ttu-id="8ee23-115">用户主体名称 (UPN)</span><span class="sxs-lookup"><span data-stu-id="8ee23-115">User Principal Name (UPN)</span></span>  | <span data-ttu-id="8ee23-116">UPN 由 UPN 前缀 (用户帐户名称) 和 (DNS 域名) 的 UPN 后缀组成。</span><span class="sxs-lookup"><span data-stu-id="8ee23-116">A UPN consists of a UPN prefix (the user account name) and a UPN suffix (a DNS domain name).</span></span> <span data-ttu-id="8ee23-117">使用 "@" 符号将前缀与后缀联接起来。</span><span class="sxs-lookup"><span data-stu-id="8ee23-117">The prefix is joined with the suffix using the "@" symbol.</span></span> | <span data-ttu-id="8ee23-118">us1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8ee23-118">us1@contoso.onmicrosoft.com</span></span> |
| <span data-ttu-id="8ee23-119">Azure AD ID</span><span class="sxs-lookup"><span data-stu-id="8ee23-119">Azure AD ID</span></span>                 | <span data-ttu-id="8ee23-120">给定用户的 Azure AD ID 是用户的唯一 GUID。</span><span class="sxs-lookup"><span data-stu-id="8ee23-120">An Azure AD ID for a given user is the unique GUID of the user.</span></span>                 | <span data-ttu-id="8ee23-121">58006c96-9e6e-45ea-8c88-4a56851eefad</span><span class="sxs-lookup"><span data-stu-id="8ee23-121">58006c96-9e6e-45ea-8c88-4a56851eefad</span></span>            |
| <span data-ttu-id="8ee23-122"> (SID) 的 Active Directory 安全 ID</span><span class="sxs-lookup"><span data-stu-id="8ee23-122">Active Directory Security ID (SID)</span></span>                  | <span data-ttu-id="8ee23-123">SID (安全标识符) 是 Active Directory 用于将对象标识为安全主体的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8ee23-123">SID (Security Identifier) is a unique identifier that Active Directory uses to identify objects as security principal.</span></span>                  | <span data-ttu-id="8ee23-124">S-1-5-21-453406510-812318184-4183662089</span><span class="sxs-lookup"><span data-stu-id="8ee23-124">S-1-5-21-453406510-812318184-4183662089</span></span>             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a><span data-ttu-id="8ee23-125">2. 选择要映射的非 Azure AD 用户属性</span><span class="sxs-lookup"><span data-stu-id="8ee23-125">2. Select non-Azure AD user properties to map</span></span>

<span data-ttu-id="8ee23-126">您可以从您的数据源中选择要应用正则表达式的非 Azure AD 属性。</span><span class="sxs-lookup"><span data-stu-id="8ee23-126">You can select non-Azure AD properties pulled from your data source to apply regular expressions on.</span></span> <span data-ttu-id="8ee23-127">若要了解有关在数据源中查找这些属性的位置的详细信息，请参阅 [ServiceNow](servicenow-connector.md) 和 [Salesforce](salesforce-connector.md) 页面。</span><span class="sxs-lookup"><span data-stu-id="8ee23-127">To learn more about where to find these properties in your data source, see the [ServiceNow](servicenow-connector.md) and [Salesforce](salesforce-connector.md) pages.</span></span>  

<span data-ttu-id="8ee23-128">您可以从下拉列表中选择非 Azure AD 用户属性，并提供要应用于这些用户属性值的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="8ee23-128">You can select a non-Azure AD user property from the dropdown and provide a regular expression to be applied on those user property values.</span></span> <span data-ttu-id="8ee23-129">若要了解有关正则表达式的详细信息，请参阅 [正则表达式引用]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference)。</span><span class="sxs-lookup"><span data-stu-id="8ee23-129">To learn more about regular expressions, see [regular expression reference]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>  

<span data-ttu-id="8ee23-130">下面是应用于示例字符串的正则表达式和输出的一些示例：</span><span class="sxs-lookup"><span data-stu-id="8ee23-130">Below are some examples of regular expressions and their outputs applied to a sample string:</span></span> 

| <span data-ttu-id="8ee23-131">示例字符串</span><span class="sxs-lookup"><span data-stu-id="8ee23-131">Sample String</span></span>                  | <span data-ttu-id="8ee23-132">正则表达式</span><span class="sxs-lookup"><span data-stu-id="8ee23-132">Regular expression</span></span>                 | <span data-ttu-id="8ee23-133">示例字符串上的正则表达式的输出</span><span class="sxs-lookup"><span data-stu-id="8ee23-133">Output of regular expression on sample string</span></span>           |
| :------------------- | :------------------- |:---------------|
| <span data-ttu-id="8ee23-134">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="8ee23-134">Alexis Vasquez</span></span>  | <span data-ttu-id="8ee23-135">.\*</span><span class="sxs-lookup"><span data-stu-id="8ee23-135">.\*</span></span> | <span data-ttu-id="8ee23-136">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="8ee23-136">Alexis Vasquez</span></span> |
| <span data-ttu-id="8ee23-137">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="8ee23-137">Alexis Vasquez</span></span>                 | <span data-ttu-id="8ee23-138">..$</span><span class="sxs-lookup"><span data-stu-id="8ee23-138">..$</span></span>                 | <span data-ttu-id="8ee23-139">ez</span><span class="sxs-lookup"><span data-stu-id="8ee23-139">ez</span></span>            |
| <span data-ttu-id="8ee23-140">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="8ee23-140">Alexis Vasquez</span></span>                  | <span data-ttu-id="8ee23-141"> ( \w +) $</span><span class="sxs-lookup"><span data-stu-id="8ee23-141">(\w+)$</span></span>                  | <span data-ttu-id="8ee23-142">Vasquez</span><span class="sxs-lookup"><span data-stu-id="8ee23-142">Vasquez</span></span>             |

<span data-ttu-id="8ee23-143">您可以添加任意多个非 Azure AD 用户属性，就像您喜欢的表达式一样。</span><span class="sxs-lookup"><span data-stu-id="8ee23-143">You can add as many non-Azure AD user properties as you would like expressions for.</span></span> <span data-ttu-id="8ee23-144">如果最终公式保证，可以将不同的正则表达式应用于相同的用户属性。</span><span class="sxs-lookup"><span data-stu-id="8ee23-144">You can apply different regular expressions to the same user property if your final formula warrants that.</span></span>  

### <a name="3-create-formula-to-complete-mapping"></a><span data-ttu-id="8ee23-145">3. 创建用于完成映射的公式</span><span class="sxs-lookup"><span data-stu-id="8ee23-145">3. Create formula to complete mapping</span></span>

<span data-ttu-id="8ee23-146">您可以将应用于每个非 Azure AD 用户属性的正则表达式的输出组合起来，以构成在步骤1中选择的 Azure AD 属性。</span><span class="sxs-lookup"><span data-stu-id="8ee23-146">You can combine the outputs of the regular expressions applied to each of your non-Azure AD user properties to form the Azure AD property selected in step 1.</span></span>

<span data-ttu-id="8ee23-147">在 "公式" 框中，" {0} " 对应于应用于所选的 *第一个* 非 Azure AD 属性的正则表达式的输出。</span><span class="sxs-lookup"><span data-stu-id="8ee23-147">In the formula box, "{0}" corresponds to the output of the regular expression applied to the *first* non-Azure AD property you selected.</span></span> <span data-ttu-id="8ee23-148">" {1} " 对应于应用于所选的 *第二个* 非 Azure AD 属性的正则表达式的输出。</span><span class="sxs-lookup"><span data-stu-id="8ee23-148">"{1}" corresponds to the output of the regular expression applied to the *second* non-Azure AD property you selected.</span></span> <span data-ttu-id="8ee23-149">" {2} " 对应于应用于 *第三个* 非 Azure AD 属性的正则表达式的输出，依此类推。</span><span class="sxs-lookup"><span data-stu-id="8ee23-149">"{2}" corresponds to the output of the regular expression applied to the *third* non-Azure AD property, and so on.</span></span>  

<span data-ttu-id="8ee23-150">下面是示例正则表达式输出和公式输出的一些公式示例：</span><span class="sxs-lookup"><span data-stu-id="8ee23-150">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span> 

| <span data-ttu-id="8ee23-151">示例公式</span><span class="sxs-lookup"><span data-stu-id="8ee23-151">Sample formula</span></span>                  | <span data-ttu-id="8ee23-152">{0}示例用户的值</span><span class="sxs-lookup"><span data-stu-id="8ee23-152">Value of {0} on sample user</span></span>                 | <span data-ttu-id="8ee23-153">{1}示例用户的值</span><span class="sxs-lookup"><span data-stu-id="8ee23-153">Value of {1} on sample user</span></span>           | <span data-ttu-id="8ee23-154">公式的输出</span><span class="sxs-lookup"><span data-stu-id="8ee23-154">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="8ee23-155">{0}.{1}@contoso .com</span><span class="sxs-lookup"><span data-stu-id="8ee23-155">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="8ee23-156">段</span><span class="sxs-lookup"><span data-stu-id="8ee23-156">firstname</span></span> | <span data-ttu-id="8ee23-157">lastname</span><span class="sxs-lookup"><span data-stu-id="8ee23-157">lastname</span></span> |<span data-ttu-id="8ee23-158">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ee23-158">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="8ee23-159">{0}@domain .com</span><span class="sxs-lookup"><span data-stu-id="8ee23-159">{0}@domain.com</span></span>                 | <span data-ttu-id="8ee23-160">userid</span><span class="sxs-lookup"><span data-stu-id="8ee23-160">userid</span></span>                 |             |<span data-ttu-id="8ee23-161">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="8ee23-161">userid@domain.com</span></span>

<span data-ttu-id="8ee23-162">在提供公式之后，您可以选择单击 " **预览** " 以查看数据源中5个随机用户的预览，并应用各自的用户映射。</span><span class="sxs-lookup"><span data-stu-id="8ee23-162">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="8ee23-163">预览的输出包括在步骤2中为这些用户选择的非 Azure AD 用户属性的值，以及针对该用户的步骤3中提供的最后一个公式的输出。</span><span class="sxs-lookup"><span data-stu-id="8ee23-163">The output of the preview includes the value of the non-Azure AD user properties selected in step 2 for those users and the output of the final formula provided in step 3 for that user.</span></span> <span data-ttu-id="8ee23-164">它还指示是否可以通过 "成功" 或 "失败" 图标将公式的输出解析为租户中的 Azure AD 用户。</span><span class="sxs-lookup"><span data-stu-id="8ee23-164">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="8ee23-165">如果单击 " **预览**" 后，如果一个或多个用户映射的状态为 "失败"，则仍可以继续创建连接。</span><span class="sxs-lookup"><span data-stu-id="8ee23-165">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="8ee23-166">预览显示5个随机用户及其从您的数据源的映射。</span><span class="sxs-lookup"><span data-stu-id="8ee23-166">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="8ee23-167">如果您提供的映射不会映射所有用户，则可能会遇到这种情况。</span><span class="sxs-lookup"><span data-stu-id="8ee23-167">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-non-azure-ad-mapping"></a><span data-ttu-id="8ee23-168">非 Azure AD 映射示例</span><span class="sxs-lookup"><span data-stu-id="8ee23-168">Sample non-Azure AD mapping</span></span>

<span data-ttu-id="8ee23-169">有关非 Azure AD 映射示例，请参阅下面的快照。</span><span class="sxs-lookup"><span data-stu-id="8ee23-169">See the snapshot below for a sample non-Azure AD mapping.</span></span>

![如何填写非 Azure AD 映射页的示例快照](media/non-aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="8ee23-171">限制</span><span class="sxs-lookup"><span data-stu-id="8ee23-171">Limitations</span></span>  

- <span data-ttu-id="8ee23-172">所有用户仅支持一个映射。</span><span class="sxs-lookup"><span data-stu-id="8ee23-172">Only one mapping is supported for all users.</span></span> <span data-ttu-id="8ee23-173">不支持条件映射。</span><span class="sxs-lookup"><span data-stu-id="8ee23-173">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="8ee23-174">一旦发布连接，便无法更改映射。</span><span class="sxs-lookup"><span data-stu-id="8ee23-174">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="8ee23-175">对于转换，目前仅支持针对非 AAD 用户属性的基于 regex 的表达式。</span><span class="sxs-lookup"><span data-stu-id="8ee23-175">Only regex-based expressions against the non-AAD user properties are currently supported for the transformation.</span></span>

- <span data-ttu-id="8ee23-176">只有3个 Azure AD 标识可以选择映射到 (UPN、Azure AD ID 和 AD SID) 。</span><span class="sxs-lookup"><span data-stu-id="8ee23-176">There are only 3 Azure AD identities you can choose to map to (UPN, Azure AD ID, and AD SID).</span></span>