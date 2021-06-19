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
ms.openlocfilehash: 8818d2e6a412feb167c67f465f485b23e868a12a
ms.sourcegitcommit: be989950a7b63281c2348cfd9e6cc13e79b7c067
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53021831"
---
# <a name="dynamics-365-federation-search-preview"></a><span data-ttu-id="596e0-103">Dynamics 365 联合搜索 (预览) </span><span class="sxs-lookup"><span data-stu-id="596e0-103">Dynamics 365 federation search (preview)</span></span>

## <a name="microsoft-search-federation-and-connectors"></a><span data-ttu-id="596e0-104">Microsoft 搜索联合身份验证和连接器</span><span class="sxs-lookup"><span data-stu-id="596e0-104">Microsoft Search Federation and connectors</span></span>

<span data-ttu-id="596e0-105">为了帮助使Microsoft 搜索更有用，我们引入了联合Microsoft 搜索联合。</span><span class="sxs-lookup"><span data-stu-id="596e0-105">To help make Microsoft Search more useful, we're introducing Microsoft Search Federation.</span></span> <span data-ttu-id="596e0-106">通过联合搜索，组织可以在以下情况下访问Microsoft 搜索：</span><span class="sxs-lookup"><span data-stu-id="596e0-106">With federated search, organizations can make data in these scenarios accessible in Microsoft Search:</span></span>

* <span data-ttu-id="596e0-107">系统符合严格合规性要求的数据</span><span class="sxs-lookup"><span data-stu-id="596e0-107">Data in systems that are subject to strict compliance requirements</span></span>
* <span data-ttu-id="596e0-108">无法离开系统边界的数据</span><span class="sxs-lookup"><span data-stu-id="596e0-108">Data that can't leave system boundaries</span></span>
* <span data-ttu-id="596e0-109">存储在你的组织不希望在云上编制索引的敏感数据</span><span class="sxs-lookup"><span data-stu-id="596e0-109">Sensitive data stored on-prem that your organization doesn’t want indexed on the cloud</span></span>

<span data-ttu-id="596e0-110">通过联合搜索连接访问的数据在索引中Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="596e0-110">Data accessed through a federated search connection isn't indexed in Microsoft Search.</span></span> <span data-ttu-id="596e0-111">此外，使用 Microsoft 的内置连接器可轻松设置联合搜索连接。</span><span class="sxs-lookup"><span data-stu-id="596e0-111">Also, using built-in connectors from Microsoft, it's easy to set up federated search connections.</span></span> <span data-ttu-id="596e0-112">我们的 Dynamics 365 连接器目前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="596e0-112">Our Dynamics 365 connector is currently in preview.</span></span> <span data-ttu-id="596e0-113">如果你对加入预览版感兴趣，请通过 以下版本[aka.ms/D365FederationSearchPreview。](https://aka.ms/D365FederationSearchPreview)</span><span class="sxs-lookup"><span data-stu-id="596e0-113">If you're interested in joining the preview, let us know at [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span></span>

## <a name="dynamics-365-federation-connector"></a><span data-ttu-id="596e0-114">Dynamics 365 联合连接器</span><span class="sxs-lookup"><span data-stu-id="596e0-114">Dynamics 365 federation connector</span></span>

<span data-ttu-id="596e0-115">Microsoft Dynamics 365 是一系列智能业务应用程序，设计用于企业资源规划和客户关系管理。</span><span class="sxs-lookup"><span data-stu-id="596e0-115">Microsoft Dynamics 365 is a line of intelligent business applications designed for enterprise resource planning and customer relationship management.</span></span> <span data-ttu-id="596e0-116">借助 Dynamics 365 联合身份验证，Microsoft 搜索提供无缝搜索体验，使用户能够轻松找到存储在 Dynamics 365 中的最相关的客户和业务数据。</span><span class="sxs-lookup"><span data-stu-id="596e0-116">With Dynamics 365 federation, Microsoft Search provides a seamless search experience, enabling users to easily find the most relevant customer and business data stored in Dynamics 365.</span></span> <span data-ttu-id="596e0-117">Dynamics 365 联合连接器提供了一些关键优势：</span><span class="sxs-lookup"><span data-stu-id="596e0-117">The Dynamics 365 federation connector provides some key benefits:</span></span>

* <span data-ttu-id="596e0-118">**易于管理：** 配置和维护与 Dynamics 365 实例的搜索连接的简化过程。</span><span class="sxs-lookup"><span data-stu-id="596e0-118">**Easy to administer:** Streamlined process to configure and maintain the search connection to a Dynamics 365 instance.</span></span>
* <span data-ttu-id="596e0-119">**易于使用：** 用户可以轻松快速地找到存储在 Dynamics 365 中的关键信息，包括帐户、联系人、打开的机会等。</span><span class="sxs-lookup"><span data-stu-id="596e0-119">**Easy to use:** Users can easily and quickly find key information stored in Dynamics 365, including accounts, contacts, open opportunities, and more.</span></span>
* <span data-ttu-id="596e0-120">**更丰富的内容：** 若要使 Dynamics 365 搜索结果更有用，其中包括关键信息，如潜在客户、联系人和帐户详细信息。</span><span class="sxs-lookup"><span data-stu-id="596e0-120">**Richer content:** To make Dynamics 365 search results more useful, they include key information like leads, contacts, and account details.</span></span>
* <span data-ttu-id="596e0-121">**内置数据保护：** Dynamics 365 结果将仅为有权访问已连接实例的用户显示。</span><span class="sxs-lookup"><span data-stu-id="596e0-121">**Built-in data protection:** Dynamics 365 results will only appear for users that have access to the connected instance.</span></span>
* <span data-ttu-id="596e0-122">**统一搜索体验：** 为了保持一致的体验，Dynamics 365 结果在所有搜索入口点中保持一致。</span><span class="sxs-lookup"><span data-stu-id="596e0-122">**Unified search experience:** To maintain a cohesive experience, Dynamics 365 results are consistent across all search entry points.</span></span> <span data-ttu-id="596e0-123">无论您在何处搜索，您都具有相同的外观和感觉。</span><span class="sxs-lookup"><span data-stu-id="596e0-123">Wherever you search, you'll get the same results with the same look and feel.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="596e0-124">用户体验</span><span class="sxs-lookup"><span data-stu-id="596e0-124">What users experience</span></span>

<span data-ttu-id="596e0-125">Dynamics 365 答案将显示在所有 Microsoft 搜索 画布的搜索结果中，包括 SharePoint Online、必应 和 Office。</span><span class="sxs-lookup"><span data-stu-id="596e0-125">Dynamics 365 answers appear in search results across all Microsoft Search canvases, including SharePoint Online, Bing, and Office.</span></span>

:::image type="content" alt-text="SharePoint、必应 和 Office 上的 Dynamics 365 Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

<span data-ttu-id="596e0-127">从答案来看，使用"更多 Dynamics 365 结果"链接可以轻松查看更多 **Dynamics 365** 搜索结果。</span><span class="sxs-lookup"><span data-stu-id="596e0-127">From the answer, it's easy to see more Dynamics 365 search results by using the **More Dynamics 365 results** link.</span></span> <span data-ttu-id="596e0-128">它将用户带进专用 Dynamics 365 结果页，该页面包含更多与查询相关的结果。</span><span class="sxs-lookup"><span data-stu-id="596e0-128">It takes users to a dedicated Dynamics 365 results page with more results relevant to their query.</span></span>

:::image type="content" alt-text="Dynamics 365 垂直和 SharePoint、必应 和 Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

<span data-ttu-id="596e0-130">单击或点击任何结果将打开 Dynamics 365，然后显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="596e0-130">Clicking or tapping any result opens Dynamics 365 and shows the detailed information.</span></span>

:::image type="content" alt-text="Dynamics 365 中详细信息页面的屏幕截图" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

<span data-ttu-id="596e0-132">无论用户在何处开始搜索，他们的体验都将保持一致，并使用户能够快速找到最相关的 Dynamics 365 结果。</span><span class="sxs-lookup"><span data-stu-id="596e0-132">No matter where your users start their search their experience will be consistent and enable them to quickly find the most relevant Dynamics 365 results.</span></span> <span data-ttu-id="596e0-133">请查看我们的 [Microsoft Build 2021 视频](https://youtu.be/TH9QUkQoEJM) 进行演示。</span><span class="sxs-lookup"><span data-stu-id="596e0-133">Check out our [Microsoft Build 2021 video](https://youtu.be/TH9QUkQoEJM) for a demonstration.</span></span>

## <a name="supported-query-patterns"></a><span data-ttu-id="596e0-134">支持的查询模式</span><span class="sxs-lookup"><span data-stu-id="596e0-134">Supported query patterns</span></span>

<span data-ttu-id="596e0-135">当使用自然语言和产品名称查询来查找 Dynamics 365 Microsoft 搜索支持自然语言和产品名称查询。</span><span class="sxs-lookup"><span data-stu-id="596e0-135">Both natural language and product name queries are supported when using Microsoft Search to find Dynamics 365 results.</span></span> <span data-ttu-id="596e0-136">此外，Dynamics 365 查询不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="596e0-136">Also, Dynamics 365 queries aren't case sensitive.</span></span> <span data-ttu-id="596e0-137">使用自然语言模式（按客户名称或位置）和其他常用查询查找联系人、帐户和机会。</span><span class="sxs-lookup"><span data-stu-id="596e0-137">Use natural language patterns to find contact, account, and opportunities--by customer name or location--and other frequently used queries.</span></span> <span data-ttu-id="596e0-138">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="596e0-138">Here are a few examples:</span></span>

* <span data-ttu-id="596e0-139">Who是 Contoso 的联系人</span><span class="sxs-lookup"><span data-stu-id="596e0-139">Who is the contact for Contoso</span></span>
* <span data-ttu-id="596e0-140">Contoso 的打开机会</span><span class="sxs-lookup"><span data-stu-id="596e0-140">Open opportunities for Contoso</span></span>
* <span data-ttu-id="596e0-141">西雅图的打开机会是什么</span><span class="sxs-lookup"><span data-stu-id="596e0-141">What are open opportunities in Seattle</span></span>
* <span data-ttu-id="596e0-142">西雅图的帐户是什么</span><span class="sxs-lookup"><span data-stu-id="596e0-142">What are the accounts in Seattle</span></span>
* <span data-ttu-id="596e0-143">西雅图的联系人是什么</span><span class="sxs-lookup"><span data-stu-id="596e0-143">What are the contacts in Seattle</span></span>
* <span data-ttu-id="596e0-144">我本月结束的潜在客户是什么</span><span class="sxs-lookup"><span data-stu-id="596e0-144">What are my leads closing this month</span></span>
* <span data-ttu-id="596e0-145">高优先级电话呼叫</span><span class="sxs-lookup"><span data-stu-id="596e0-145">High priority phone call</span></span>
* <span data-ttu-id="596e0-146">联系缺少的电子邮件</span><span class="sxs-lookup"><span data-stu-id="596e0-146">Contact missing emails</span></span>

<span data-ttu-id="596e0-147">产品名称模式支持一系列 Dynamics 365 应用程序，并且将触发 Dynamics 365 结果，而不管它们在查询中的显示位置如何：</span><span class="sxs-lookup"><span data-stu-id="596e0-147">Product name patterns support a range of Dynamics 365 applications and will trigger Dynamics 365 results regardless of where they appear in a query:</span></span>

* <span data-ttu-id="596e0-148">D365</span><span class="sxs-lookup"><span data-stu-id="596e0-148">D365</span></span>
* <span data-ttu-id="596e0-149">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="596e0-149">Dynamics 365</span></span>
* <span data-ttu-id="596e0-150">Dynamics365</span><span class="sxs-lookup"><span data-stu-id="596e0-150">Dynamics365</span></span>
* <span data-ttu-id="596e0-151">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="596e0-151">Dynamics CRM</span></span>
* <span data-ttu-id="596e0-152">Dynamics Sales</span><span class="sxs-lookup"><span data-stu-id="596e0-152">Dynamics Sales</span></span>
* <span data-ttu-id="596e0-153">Dynamics Customer Service</span><span class="sxs-lookup"><span data-stu-id="596e0-153">Dynamics Customer Service</span></span>
* <span data-ttu-id="596e0-154">Dynamics Service</span><span class="sxs-lookup"><span data-stu-id="596e0-154">Dynamics Service</span></span>
* <span data-ttu-id="596e0-155">Dynamics Field Service</span><span class="sxs-lookup"><span data-stu-id="596e0-155">Dynamics Field Service</span></span>

## <a name="configure-the-dynamics-365-connector"></a><span data-ttu-id="596e0-156">配置 Dynamics 365 连接器</span><span class="sxs-lookup"><span data-stu-id="596e0-156">Configure the Dynamics 365 connector</span></span>

<span data-ttu-id="596e0-157">通过此简单配置，您可以为组织人员启用 Dynamics 365 联合搜索体验。</span><span class="sxs-lookup"><span data-stu-id="596e0-157">With this simple configuration, you can enable the Dynamics 365 federation search experience for people in your organization.</span></span>

1. <span data-ttu-id="596e0-158">在["Microsoft 365 管理中心"](https://admin.microsoft.com)中，转到["数据源"。](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors)</span><span class="sxs-lookup"><span data-stu-id="596e0-158">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [Data sources](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span></span>

2. <span data-ttu-id="596e0-159">在"Microsoft 应用和服务"部分中的"Microsoft Dynamics 365"下，选择"管理"以打开 Microsoft Dynamics 365 面板。 </span><span class="sxs-lookup"><span data-stu-id="596e0-159">In the Microsoft apps and services section, under Microsoft Dynamics 365, select **Manage** to open the Microsoft Dynamics 365 panel.</span></span>

3. <span data-ttu-id="596e0-160">为组织启用连接器。</span><span class="sxs-lookup"><span data-stu-id="596e0-160">Enable the connector for your organization.</span></span>

4. <span data-ttu-id="596e0-161">在" **终结点"** 列表中，选择 Dynamics 365 环境。</span><span class="sxs-lookup"><span data-stu-id="596e0-161">In the **Endpoints** list, select your Dynamics 365 environment.</span></span>

5. <span data-ttu-id="596e0-162">在" **连接 ID"** 中，为此连接输入唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="596e0-162">In the **Connection ID**, enter a unique ID for this connection.</span></span>

6. <span data-ttu-id="596e0-163">查看并选中同意复选框。</span><span class="sxs-lookup"><span data-stu-id="596e0-163">Review and select the consent check box.</span></span>

7. <span data-ttu-id="596e0-164">选择 **"保存** "完成连接设置。</span><span class="sxs-lookup"><span data-stu-id="596e0-164">Select **Save** to finish the connection setup.</span></span>

:::image type="content" alt-text="Dynamics 365 设置面板的屏幕截图Microsoft 365 管理中心" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

<span data-ttu-id="596e0-166">设置完成后，只有具有有效 Dynamics 365 许可证的用户以及访问连接的 Dynamics 365 环境时，Dynamics 365 回答和垂直显示。</span><span class="sxs-lookup"><span data-stu-id="596e0-166">When the setup is complete, Dynamics 365 answers and vertical will only appear for users with a valid Dynamics 365 license and access to the connected Dynamics 365 environment.</span></span> <span data-ttu-id="596e0-167">您随时都可以返回到这些设置，并更改连接终结点环境或停用连接。</span><span class="sxs-lookup"><span data-stu-id="596e0-167">At any time, you can return to these settings and change the connection endpoint environment or deactivate the connection.</span></span>
