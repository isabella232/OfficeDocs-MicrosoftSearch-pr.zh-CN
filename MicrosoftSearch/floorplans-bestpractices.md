---
title: Microsoft 搜索层计划的最佳实践
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft 搜索层计划的最佳实践
ms.openlocfilehash: 47eb46df48f1871f6d34d4b00787cf11ccbac1ea
ms.sourcegitcommit: 6b1c6a4e502d95b42a030a963f9452c387d8a5cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "43571011"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="best-practices-for-microsoft-search-floor-plans"></a><span data-ttu-id="80152-103">Microsoft 搜索层计划的最佳实践</span><span class="sxs-lookup"><span data-stu-id="80152-103">Best practices for Microsoft Search floor plans</span></span>

<span data-ttu-id="80152-104">若要成功实现 Microsoft Search 平面图计划，您需要协调三个数据片段：</span><span class="sxs-lookup"><span data-stu-id="80152-104">To successfully implement Microsoft Search floor plans, you need to coordinate three pieces of data:</span></span>

- <span data-ttu-id="80152-105">**生成位置数据**：什么格式以及如何添加？</span><span class="sxs-lookup"><span data-stu-id="80152-105">**Building location data**: What format and how to add?</span></span>
- <span data-ttu-id="80152-106">**DWG 格式的平面布置图地图**：如何查看它包含哪些数据以获得最大成功？</span><span class="sxs-lookup"><span data-stu-id="80152-106">**Floor plan map in DWG format**: How to view and what data should it contain for maximum success?</span></span>
- <span data-ttu-id="80152-107">\*\* [Azure Active Directory （azure AD）](https://azure.microsoft.com/services/active-directory/)中的员工办公室位置\*\*：要使用什么格式以及如何添加？</span><span class="sxs-lookup"><span data-stu-id="80152-107">**Employee office location in [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/)**: What format to use and how to add?</span></span> <br>

<span data-ttu-id="80152-108">以下各节也介绍了部署 Microsoft 搜索平面布置图的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="80152-108">The best practices for deploying Microsoft Search floor plans are also described in the following sections.</span></span>

## <a name="building-location-data"></a><span data-ttu-id="80152-109">生成位置数据</span><span class="sxs-lookup"><span data-stu-id="80152-109">Building location data</span></span>

<span data-ttu-id="80152-110">在添加平面布置图之前，需要将建筑物添加到 Microsoft 搜索位置。</span><span class="sxs-lookup"><span data-stu-id="80152-110">Before you add floor plans, you need to add your buildings to Microsoft Search locations.</span></span> <span data-ttu-id="80152-111">提供以下所需的生成数据：</span><span class="sxs-lookup"><span data-stu-id="80152-111">Provide the following required building data:</span></span>

|<span data-ttu-id="80152-112">生成数据所需</span><span class="sxs-lookup"><span data-stu-id="80152-112">Required building data</span></span>  |<span data-ttu-id="80152-113">示例</span><span class="sxs-lookup"><span data-stu-id="80152-113">Example</span></span>  |
|---------|---------|
|<span data-ttu-id="80152-114">名称</span><span class="sxs-lookup"><span data-stu-id="80152-114">Name</span></span>     |    <span data-ttu-id="80152-115">建筑物1、纽约城市</span><span class="sxs-lookup"><span data-stu-id="80152-115">Building 1, New York City</span></span>     |
|<span data-ttu-id="80152-116">街道地址</span><span class="sxs-lookup"><span data-stu-id="80152-116">Street address</span></span>     |     <span data-ttu-id="80152-117">123任何途径，纽约，纽约州10118</span><span class="sxs-lookup"><span data-stu-id="80152-117">123 Any Avenue, New York, NY 10118</span></span>  |
|<span data-ttu-id="80152-118">纬度-经度（可选）</span><span class="sxs-lookup"><span data-stu-id="80152-118">Latitude-longitude  (optional)</span></span>   |    <span data-ttu-id="80152-119">40.760539，-73.975341</span><span class="sxs-lookup"><span data-stu-id="80152-119">40.760539, -73.975341</span></span>      |
|<span data-ttu-id="80152-120">关键字</span><span class="sxs-lookup"><span data-stu-id="80152-120">Keywords</span></span>     |    <span data-ttu-id="80152-121">纽约办事处，建筑物1，总公司，总部</span><span class="sxs-lookup"><span data-stu-id="80152-121">New York Office, Building 1, main office, headquarters</span></span>     |

<span data-ttu-id="80152-122">您可以通过使用 "**位置**" 选项卡中的 "**导入**" 功能，而不是一次添加一个位置，来一次添加多个建筑物。</span><span class="sxs-lookup"><span data-stu-id="80152-122">You can add many buildings at a time by using the **Import** feature in the **Locations** tab instead of adding locations one at a time.</span></span> <span data-ttu-id="80152-123">使用**导入**功能，可以指定纬度-经度。</span><span class="sxs-lookup"><span data-stu-id="80152-123">With the **Import** feature, you can specify the latitude-longitude.</span></span> <span data-ttu-id="80152-124">有关详细信息，请参阅[管理位置](manage-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="80152-124">For more information, see [Manage locations](manage-locations.md).</span></span>

## <a name="floor-plan-map-in-dwg-format"></a><span data-ttu-id="80152-125">DWG 格式的楼面平面图地图</span><span class="sxs-lookup"><span data-stu-id="80152-125">Floor plan map in DWG format</span></span>

<span data-ttu-id="80152-126">若要在 Microsoft Search 中构建地图，需要在 DWG 格式中上载包含特定信息的平面布置图。</span><span class="sxs-lookup"><span data-stu-id="80152-126">To build maps in Microsoft Search, you need to upload floor plans in DWG format with specific information.</span></span> <span data-ttu-id="80152-127">若要了解如何创建和查看 DWG 格式的文件，请参阅[Dwg 查看](https://www.autodesk.in/products/dwg)器。</span><span class="sxs-lookup"><span data-stu-id="80152-127">To learn how to create and view DWG-formatted files, see [DWG Viewers](https://www.autodesk.in/products/dwg).</span></span>

<span data-ttu-id="80152-128">楼面平面图地图显示四个元素：</span><span class="sxs-lookup"><span data-stu-id="80152-128">Floor plan maps display four elements:</span></span>

1. <span data-ttu-id="80152-129">**房间号码**：在以下示例中，房间号码定义为**B1 1001**和**b1 1002**。</span><span class="sxs-lookup"><span data-stu-id="80152-129">**Room numbers**: In the following example, room numbers are defined as **B1 1001** and **B1 1002**.</span></span> <span data-ttu-id="80152-130">**B1**是生成代码， **1001**包含底价号**1**和办公室号**001**。</span><span class="sxs-lookup"><span data-stu-id="80152-130">**B1** is the building code, and **1001** contains the floor number **1** and the office number **001**.</span></span>
1. <span data-ttu-id="80152-131">**会议室布局。**：若要帮助阐明多个用户共享 office 时的详细信息，您可以定义椅子和书桌等布局。</span><span class="sxs-lookup"><span data-stu-id="80152-131">**Room layouts.**: To help clarify details when multiple users share an office, you can define layouts like chairs and desk.</span></span>
1. <span data-ttu-id="80152-132">**会议室类型**：一些示例包括 office、corridor、开放式区域和抽水马桶。</span><span class="sxs-lookup"><span data-stu-id="80152-132">**Room types**: Some examples include office, corridor, open area, and toilet.</span></span>
1. <span data-ttu-id="80152-133">**资产信息**：如果用户在开放的空间中，则可以指示他们所在的办公桌。</span><span class="sxs-lookup"><span data-stu-id="80152-133">**Asset info**: If users are in an open space, you can denote which desk they sit at.</span></span> <span data-ttu-id="80152-134">在此示例中，办公桌由**TB1**和**TB2**表示。</span><span class="sxs-lookup"><span data-stu-id="80152-134">In this example, the desks are denoted by **TB1** and **TB2**.</span></span>

![简单的 office 地图，显示如何标记会议室编号、资产和会议室类型](media/Floorplans-LayoutwithCallouts.png)

<span data-ttu-id="80152-136">在此图中，房间号码是最重要的项。</span><span class="sxs-lookup"><span data-stu-id="80152-136">In this diagram, room numbers are the most important item.</span></span> <span data-ttu-id="80152-137">它们映射到用户帐户上的某个人的办公室位置，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="80152-137">They're mapped to a person’s office location on their user account as shown in the following image.</span></span>

![显示用户详细信息（包括 office 位置）的 "人员" 搜索结果卡片的 "概述" 选项卡](media/floorplans-peoplecard.png)

<span data-ttu-id="80152-139">此信息存储在[AZURE AD](https://azure.microsoft.com/services/active-directory/)中的**PhysicalDeliveryOfficeName**属性中。</span><span class="sxs-lookup"><span data-stu-id="80152-139">This information is stored in [Azure AD](https://azure.microsoft.com/services/active-directory/) in the **PhysicalDeliveryOfficeName** property.</span></span> <span data-ttu-id="80152-140">在 Microsoft 365[管理中心](https://admin.microsoft.com)，它称为**Office**属性，可在**活动用户**中添加。</span><span class="sxs-lookup"><span data-stu-id="80152-140">In the Microsoft 365 [admin center](https://admin.microsoft.com), it’s called the **Office** property and can be added in **Active users**.</span></span>

### <a name="dwg-files"></a><span data-ttu-id="80152-141">DWG 文件</span><span class="sxs-lookup"><span data-stu-id="80152-141">DWG files</span></span>

<span data-ttu-id="80152-142">Microsoft Search 需要 DWG 中的平面布置图文件，这是[AutoCAD](https://www.autodesk.com/autocad)绘图格式。</span><span class="sxs-lookup"><span data-stu-id="80152-142">Microsoft Search requires floor plan files in DWG, which is an [AutoCAD](https://www.autodesk.com/autocad) drawing format.</span></span> <span data-ttu-id="80152-143">这些文件必须包含**布局**和**标签**数据。</span><span class="sxs-lookup"><span data-stu-id="80152-143">The files must contain **layout** and **label** data.</span></span> <span data-ttu-id="80152-144">**房间号码**是平面布置图最重要的标签。</span><span class="sxs-lookup"><span data-stu-id="80152-144">**Room numbers** are the most important labels for floor plans.</span></span>

<span data-ttu-id="80152-145">建议使用下表中所示的完全匹配方法创建 office 编号系统。</span><span class="sxs-lookup"><span data-stu-id="80152-145">We recommend that you create your office numbering system with the exact-match method shown in the following table.</span></span> <span data-ttu-id="80152-146">但您并不局限于该标记。</span><span class="sxs-lookup"><span data-stu-id="80152-146">But you aren't limited to that labeling.</span></span> <span data-ttu-id="80152-147">例如，如果用户在[AZURE AD](https://azure.microsoft.com/services/active-directory/)中的办公室位置是**B1 1001**，则可以使用下面的任意选项在 DWG 文件中标记房间号码。</span><span class="sxs-lookup"><span data-stu-id="80152-147">For example, if the user's office location in [Azure AD](https://azure.microsoft.com/services/active-directory/) is **B1 1001**, you can label the room number in the DWG file with any of the options that follow.</span></span>

|<span data-ttu-id="80152-148">Match</span><span class="sxs-lookup"><span data-stu-id="80152-148">Match</span></span>  |<span data-ttu-id="80152-149">布局</span><span class="sxs-lookup"><span data-stu-id="80152-149">Layout</span></span>  |
|---------|---------|
|<span data-ttu-id="80152-150">与办公室位置的完全匹配（推荐）</span><span class="sxs-lookup"><span data-stu-id="80152-150">Exact match to office location (Recommended)</span></span> <br> <span data-ttu-id="80152-151">**B1 1001**</span><span class="sxs-lookup"><span data-stu-id="80152-151">**B1 1001**</span></span> <br> <span data-ttu-id="80152-152">生成代码： B1</span><span class="sxs-lookup"><span data-stu-id="80152-152">Building code: B1</span></span><br><span data-ttu-id="80152-153">基底：1</span><span class="sxs-lookup"><span data-stu-id="80152-153">Floor: 1</span></span> <br><span data-ttu-id="80152-154">会议室编号：001</span><span class="sxs-lookup"><span data-stu-id="80152-154">Room number: 001</span></span>    |    ![办公室编号为 "B1 1001" 的单一办公室平面布置图](media/floorplans-layoutexactmatch.png)     |
|<span data-ttu-id="80152-156">匹配楼层和房间号</span><span class="sxs-lookup"><span data-stu-id="80152-156">Match floor and room number</span></span> <br> <span data-ttu-id="80152-157">**1001**</span><span class="sxs-lookup"><span data-stu-id="80152-157">**1001**</span></span><br><span data-ttu-id="80152-158">基底：1</span><span class="sxs-lookup"><span data-stu-id="80152-158">Floor: 1</span></span> <br><span data-ttu-id="80152-159">会议室编号：001</span><span class="sxs-lookup"><span data-stu-id="80152-159">Room number: 001</span></span>    |   ![Office 编号为 "1001" 的单一办公室平面布置图](media/floorplans-layoutfloorroom.png)   |
|<span data-ttu-id="80152-161">仅匹配会议室号码</span><span class="sxs-lookup"><span data-stu-id="80152-161">Match room number only</span></span> <br> <span data-ttu-id="80152-162">**1**</span><span class="sxs-lookup"><span data-stu-id="80152-162">**1**</span></span><br><span data-ttu-id="80152-163">会议室编号：1</span><span class="sxs-lookup"><span data-stu-id="80152-163">Room number: 1</span></span>        |    ![Office 编号为 "1" 的单一办公室楼面地图](media/floorplans-layoutroomonly.png)     |

## <a name="user-account-office-location"></a><span data-ttu-id="80152-165">用户帐户办公地点</span><span class="sxs-lookup"><span data-stu-id="80152-165">User account office location</span></span>

<span data-ttu-id="80152-166">若要映射员工的位置，DWG 文件中的房间号码将映射到[AZURE AD](https://azure.microsoft.com/services/active-directory/)中的用户帐户中的办公室位置。</span><span class="sxs-lookup"><span data-stu-id="80152-166">To map an employee’s location, the room numbers in DWG files are mapped to office locations in the user’s account in [Azure AD](https://azure.microsoft.com/services/active-directory/).</span></span> <span data-ttu-id="80152-167">**Office location**属性需要与 DWG 文件中的 office 位置信息相匹配。</span><span class="sxs-lookup"><span data-stu-id="80152-167">The **Office location** property needs to match the office location information in the DWG file.</span></span>

<span data-ttu-id="80152-168">下表介绍了映射位置数据的最佳做法：</span><span class="sxs-lookup"><span data-stu-id="80152-168">The following table explains best practices for mapping location data:</span></span>

|<span data-ttu-id="80152-169">最佳做法</span><span class="sxs-lookup"><span data-stu-id="80152-169">Best practice</span></span>  |<span data-ttu-id="80152-170">说明</span><span class="sxs-lookup"><span data-stu-id="80152-170">Explanation</span></span> |
|---------|---------|
|<span data-ttu-id="80152-171">包括建筑物代码、基底和房间号。</span><span class="sxs-lookup"><span data-stu-id="80152-171">Include building code, floor, and room number.</span></span>     |   <span data-ttu-id="80152-172">此数据为您提供了完全匹配的最佳机会。</span><span class="sxs-lookup"><span data-stu-id="80152-172">This data gives you the best chance to make exact matches.</span></span>     |
|<span data-ttu-id="80152-173">生成代码和楼层后包含分隔符。</span><span class="sxs-lookup"><span data-stu-id="80152-173">Include a separator after building codes and floors.</span></span>     |  <span data-ttu-id="80152-174">使用分隔符或空格将建筑物代码从楼层和房间号分离，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="80152-174">Separate building codes from floor and room numbers with a separator or a space, as in these examples:</span></span><br> <span data-ttu-id="80152-175">B1 1001</span><span class="sxs-lookup"><span data-stu-id="80152-175">B1 1001</span></span><br> <span data-ttu-id="80152-176">B1/1001</span><span class="sxs-lookup"><span data-stu-id="80152-176">B1/1001</span></span> <br> <span data-ttu-id="80152-177">B1-1001。</span><span class="sxs-lookup"><span data-stu-id="80152-177">B1-1001.</span></span>   |
|<span data-ttu-id="80152-178">会议室编号始终遵循生成代码、翼和地板信息。</span><span class="sxs-lookup"><span data-stu-id="80152-178">Room number always follows building code, wing, and floor information.</span></span>     |  <span data-ttu-id="80152-179">如果房间号码是**1001**，则将办公地点设置为**b1 1001**、 **b1/1001**或**b1-1001**。</span><span class="sxs-lookup"><span data-stu-id="80152-179">If the room number is **1001**, then set the office location to **B1 1001**, **B1/1001**, or **B1-1001**.</span></span> <br> <span data-ttu-id="80152-180">如果房间号为**F1-001**，则将办公位置设置为**b1 F1-001**或**b1/F1-001**。</span><span class="sxs-lookup"><span data-stu-id="80152-180">If the room number is **F1-001**, then set the office location to **B1 F1-001** or **B1/F1-001**.</span></span> <br> <span data-ttu-id="80152-181">如果房间号为**1**，则将[Azure AD](https://azure.microsoft.com/services/active-directory/)位置设置为**b1 1001**、 **B1/1001**或**B1-001**。</span><span class="sxs-lookup"><span data-stu-id="80152-181">If the room number is **1**, then set the [Azure AD](https://azure.microsoft.com/services/active-directory/) location to **B1 1001**, **B1/1001**, or **B1-F1-001**.</span></span>       |
|

## <a name="next-steps"></a><span data-ttu-id="80152-182">后续步骤</span><span class="sxs-lookup"><span data-stu-id="80152-182">Next steps</span></span>

[<span data-ttu-id="80152-183">管理位置</span><span class="sxs-lookup"><span data-stu-id="80152-183">Manage locations</span></span>](manage-locations.md)<br>
[<span data-ttu-id="80152-184">管理基底计划</span><span class="sxs-lookup"><span data-stu-id="80152-184">Manage floor plans</span></span>](manage-floorplans.md)
