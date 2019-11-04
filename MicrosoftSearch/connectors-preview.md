---
title: 连接器预览
ms.author: v-pamcn
author: monaray
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
ms.openlocfilehash: 025b4f0d7ad4ecae2909f02687c66938d931a2fc
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949626"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="42994-103">Microsoft Graph 连接器预览</span><span class="sxs-lookup"><span data-stu-id="42994-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="42994-104">Microsoft Graph 连接器、索引 Api 和搜索 Api 当前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="42994-104">Microsoft Graph connectors, indexing APIs, and search APIs are currently in preview.</span></span> <span data-ttu-id="42994-105">若要获取对连接器功能的访问权限，您必须通过提交<a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">Microsoft Graph 连接器预览注册表单</a>来请求加入预览计划。</span><span class="sxs-lookup"><span data-stu-id="42994-105">To gain access to connectors functionality, you must request to join the preview program by submitting the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">Microsoft Graph Connectors Preview Sign up Form</a>.</span></span> <span data-ttu-id="42994-106">这是一个早期预览，没有服务级别保证。</span><span class="sxs-lookup"><span data-stu-id="42994-106">This is an early preview, and there is no service level guarantee.</span></span> <span data-ttu-id="42994-107">我们鼓励客户尝试连接器功能并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="42994-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="42994-108">在预览期间，我们不建议使用连接器来实现生产目的。</span><span class="sxs-lookup"><span data-stu-id="42994-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="42994-109">设置目标版本</span><span class="sxs-lookup"><span data-stu-id="42994-109">Set up targeted release</span></span>
<span data-ttu-id="42994-110">若要尝试连接器，必须为组织中的所有用户设置**目标 "发布**" 选项。</span><span class="sxs-lookup"><span data-stu-id="42994-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="42994-111">无论您选择以下哪种预览环境，目标发布要求均适用。</span><span class="sxs-lookup"><span data-stu-id="42994-111">The Targeted release requirement applies no matter which of the following preview environments you choose.</span></span>
<span data-ttu-id="42994-112">若要了解有关目标发布选项及其设置方式的详细信息，请参阅<a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">在 Office 365 中设置标准或目标发布选项</a>。</span><span class="sxs-lookup"><span data-stu-id="42994-112">To learn more about the Targeted release option and how to set it, see <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">Set up the Standard or Targeted release options in Office 365</a>.</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="42994-113">选择预览环境</span><span class="sxs-lookup"><span data-stu-id="42994-113">Choose a preview environment</span></span> 
<span data-ttu-id="42994-114">若要尝试连接器、索引 Api 和搜索 Api，我们建议采用以下两种方法：</span><span class="sxs-lookup"><span data-stu-id="42994-114">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>
1. <span data-ttu-id="42994-115">**测试租户**。</span><span class="sxs-lookup"><span data-stu-id="42994-115">**Test tenant**.</span></span>  <span data-ttu-id="42994-116">我们鼓励你使用测试租户尝试 Microsoft Graph 连接器预览。</span><span class="sxs-lookup"><span data-stu-id="42994-116">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>
2. <span data-ttu-id="42994-117">**测试网站集**。</span><span class="sxs-lookup"><span data-stu-id="42994-117">**Test site collection**.</span></span> <span data-ttu-id="42994-118">如果你没有测试租户，可以创建测试网站集以试用连接器功能。</span><span class="sxs-lookup"><span data-stu-id="42994-118">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="42994-119">若要在不影响组织中其他任何位置的搜索页的情况下显示连接器的结果，请自定义仅该网站集的搜索体验。</span><span class="sxs-lookup"><span data-stu-id="42994-119">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="42994-120">预览限制</span><span class="sxs-lookup"><span data-stu-id="42994-120">Preview limitations</span></span>
<span data-ttu-id="42994-121">预览版本具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="42994-121">The preview release has the following limitations:</span></span>
* <span data-ttu-id="42994-122">每秒大约4个项目会限制摄取吞吐量。</span><span class="sxs-lookup"><span data-stu-id="42994-122">Ingestion throughput is throttled at about four items per second.</span></span>
* <span data-ttu-id="42994-123">不支持架构更新。</span><span class="sxs-lookup"><span data-stu-id="42994-123">There's no support for schema updates.</span></span> <span data-ttu-id="42994-124">创建连接设置后，无法更新架构。</span><span class="sxs-lookup"><span data-stu-id="42994-124">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="42994-125">您只能删除并重新创建连接。</span><span class="sxs-lookup"><span data-stu-id="42994-125">You can only delete and re-create the connection.</span></span>
* <span data-ttu-id="42994-126">索引内容仅在 "自定义垂直" 下的 "搜索结果" 页面中显示。</span><span class="sxs-lookup"><span data-stu-id="42994-126">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="42994-127">此限制适用于具有自定义类型的内容。</span><span class="sxs-lookup"><span data-stu-id="42994-127">This restriction applies to content with custom types.</span></span>
* <span data-ttu-id="42994-128">在正式发行之前，您在预览期间设置的任何连接可能需要删除并重新创建。</span><span class="sxs-lookup"><span data-stu-id="42994-128">Before general availability, any connection you set up during the preview period may need to be deleted and re-created.</span></span> <span data-ttu-id="42994-129">如果这些连接与改进产品所做的更改不兼容，这些连接将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="42994-129">Those connections won't work anymore if they are incompatible with changes made to improve the product.</span></span>
* <span data-ttu-id="42994-130">连接限制。</span><span class="sxs-lookup"><span data-stu-id="42994-130">Connections limit.</span></span> <span data-ttu-id="42994-131">每个租户最长可创建10个连接。</span><span class="sxs-lookup"><span data-stu-id="42994-131">Each tenant can create up to 10 connections.</span></span>
