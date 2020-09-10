---
title: 连接器预览
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 了解 microsoft Search 的 Microsoft Graph 连接器预览。
ms.openlocfilehash: 81d169074a316b6ab07f47156e0f057e50c12e3e
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422889"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="3a175-103">Microsoft Graph 连接器预览</span><span class="sxs-lookup"><span data-stu-id="3a175-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="3a175-104">Microsoft Graph 连接器和 Microsoft Search Api (查询和索引) 当前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="3a175-104">Microsoft Graph connectors and Microsoft Search APIs (query and index) are currently in preview status.</span></span> <span data-ttu-id="3a175-105">若要获取对连接器功能的访问权限，必须在租户中启用目标发布选项。</span><span class="sxs-lookup"><span data-stu-id="3a175-105">To gain access to connectors functionality, you must turn on the Targeted release option in your tenant.</span></span> <span data-ttu-id="3a175-106">这是一个早期预览，没有服务级别保证。</span><span class="sxs-lookup"><span data-stu-id="3a175-106">This is an early preview, and there's no service level guarantee.</span></span> <span data-ttu-id="3a175-107">我们鼓励客户尝试连接器功能并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="3a175-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="3a175-108">在预览期间，我们不建议使用连接器来实现生产目的。</span><span class="sxs-lookup"><span data-stu-id="3a175-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="3a175-109">设置目标版本</span><span class="sxs-lookup"><span data-stu-id="3a175-109">Set up Targeted release</span></span>

<span data-ttu-id="3a175-110">若要尝试连接器，必须为组织中的所有用户设置 **目标 "发布** " 选项。</span><span class="sxs-lookup"><span data-stu-id="3a175-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="3a175-111">若要了解有关目标发布选项及其设置方式的详细信息，请参阅 [在 Office 365 中设置标准或目标发布选项](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="3a175-111">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="3a175-112">选择预览环境</span><span class="sxs-lookup"><span data-stu-id="3a175-112">Choose a preview environment</span></span>

<span data-ttu-id="3a175-113">若要尝试连接器、索引 Api 和搜索 Api，我们建议采用以下两种方法：</span><span class="sxs-lookup"><span data-stu-id="3a175-113">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>

1. <span data-ttu-id="3a175-114">**测试租户**。</span><span class="sxs-lookup"><span data-stu-id="3a175-114">**Test tenant**.</span></span>  <span data-ttu-id="3a175-115">我们鼓励你使用测试租户尝试 Microsoft Graph 连接器预览。</span><span class="sxs-lookup"><span data-stu-id="3a175-115">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>

2. <span data-ttu-id="3a175-116">**测试网站集**。</span><span class="sxs-lookup"><span data-stu-id="3a175-116">**Test site collection**.</span></span> <span data-ttu-id="3a175-117">如果你没有测试租户，可以创建测试网站集以试用连接器功能。</span><span class="sxs-lookup"><span data-stu-id="3a175-117">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="3a175-118">若要在不影响组织中其他任何位置的搜索页的情况下显示连接器的结果，请自定义仅该网站集的搜索体验。</span><span class="sxs-lookup"><span data-stu-id="3a175-118">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="3a175-119">预览限制</span><span class="sxs-lookup"><span data-stu-id="3a175-119">Preview limitations</span></span>

<span data-ttu-id="3a175-120">预览版本具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="3a175-120">The preview release has the following limitations:</span></span>

* <span data-ttu-id="3a175-121">每秒大约4个项目会限制摄取吞吐量。</span><span class="sxs-lookup"><span data-stu-id="3a175-121">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="3a175-122">不支持架构更新。</span><span class="sxs-lookup"><span data-stu-id="3a175-122">There's no support for schema updates.</span></span> <span data-ttu-id="3a175-123">创建连接设置后，无法更新架构。</span><span class="sxs-lookup"><span data-stu-id="3a175-123">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="3a175-124">您只能删除并重新创建连接。</span><span class="sxs-lookup"><span data-stu-id="3a175-124">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="3a175-125">索引内容仅在 "自定义垂直" 下的 "搜索结果" 页面中显示。</span><span class="sxs-lookup"><span data-stu-id="3a175-125">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="3a175-126">此限制适用于具有自定义类型的内容。</span><span class="sxs-lookup"><span data-stu-id="3a175-126">This restriction applies to content with custom types.</span></span>

* <span data-ttu-id="3a175-127">可能需要删除并重新创建在预览期间设置的任何连接。</span><span class="sxs-lookup"><span data-stu-id="3a175-127">Any connection you set up during the preview period might need to be deleted and re-created.</span></span> <span data-ttu-id="3a175-128">如果这些连接与改进产品所做的更改不兼容，这些连接将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="3a175-128">Those connections won't work anymore if they're incompatible with changes made to improve the product.</span></span>

* <span data-ttu-id="3a175-129">有一个连接限制。</span><span class="sxs-lookup"><span data-stu-id="3a175-129">There's a connections limit.</span></span> <span data-ttu-id="3a175-130">每个租户最长可创建10个连接。</span><span class="sxs-lookup"><span data-stu-id="3a175-130">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="3a175-131">源存储库大小。</span><span class="sxs-lookup"><span data-stu-id="3a175-131">Source repository size.</span></span> <span data-ttu-id="3a175-132">我们建议您预览具有大约200000项目的来源库的连接器，因为这是我们经过测试的搜索比例限制。</span><span class="sxs-lookup"><span data-stu-id="3a175-132">We recommend that you preview connectors with a source repository of about 200,000 items as this is our tested search scale limit.</span></span> <span data-ttu-id="3a175-133">我们正在努力改进搜索性能，我们希望在不久的将来支持更大的存储库大小。</span><span class="sxs-lookup"><span data-stu-id="3a175-133">We are working on improving the performance of search, and we expect to support for larger repository sizes in the near future.</span></span>

* <span data-ttu-id="3a175-134">"编辑对连接的支持" 不可用。</span><span class="sxs-lookup"><span data-stu-id="3a175-134">Edit support for connection is not available.</span></span> <span data-ttu-id="3a175-135">一旦创建了连接，就不能再对其进行编辑或更改。</span><span class="sxs-lookup"><span data-stu-id="3a175-135">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="3a175-136">如果需要更改任何详细信息，则必须删除并重新创建连接。</span><span class="sxs-lookup"><span data-stu-id="3a175-136">If you need to change any details, you must delete and recreate the connection.</span></span>

* <span data-ttu-id="3a175-137">仅可在自定义纵向搜索连接器内容。</span><span class="sxs-lookup"><span data-stu-id="3a175-137">Connector content can only be searched on custom verticals.</span></span>

* <span data-ttu-id="3a175-138">仅一个连接中的连接器内容可以在每个自定义垂直中显示，并且需要创建结果类型。</span><span class="sxs-lookup"><span data-stu-id="3a175-138">Connector content from only one connection can be displayed in each custom vertical and requires result type creation.</span></span>
