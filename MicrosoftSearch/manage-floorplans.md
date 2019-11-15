---
title: 管理基底计划
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 中的平面布置图功能可帮助用户在大楼中查找人员、办公室和其他有用的功能。
ms.openlocfilehash: 9871cda3790f210dc0c406d1d29abe2c571c1085
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626789"
---
# <a name="manage-floor-plans"></a><span data-ttu-id="17f6a-103">管理基底计划</span><span class="sxs-lookup"><span data-stu-id="17f6a-103">Manage floor plans</span></span>

<span data-ttu-id="17f6a-104">Microsoft Search 平面图计划可帮助用户在大楼中查找人员和会议室。</span><span class="sxs-lookup"><span data-stu-id="17f6a-104">Microsoft Search floor plans help users find people and meeting rooms within a building.</span></span> <span data-ttu-id="17f6a-105">平面图计划回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="17f6a-105">Floor plans answer these questions:</span></span>
- <span data-ttu-id="17f6a-106">Allan Deyoung 的办公室在哪里？</span><span class="sxs-lookup"><span data-stu-id="17f6a-106">Where is Allan Deyoung's office?</span></span>
- <span data-ttu-id="17f6a-107">会议室 C1 在什么位置？</span><span class="sxs-lookup"><span data-stu-id="17f6a-107">Where is meeting room C1?</span></span>

![平面图在大楼中对用户的办公室位置进行了分布规划。](media/floorplans-officelocation.png)

<span data-ttu-id="17f6a-109">为了便于查找类似这些问题的答案，有关组织建筑物、办公室和设施的信息需要提供，并可供搜索。</span><span class="sxs-lookup"><span data-stu-id="17f6a-109">To make it easy to find answers to questions like these, information about an organization's buildings, offices, and facilities needs to be available and made searchable.</span></span> <span data-ttu-id="17f6a-110">大型组织通常具有设施或空间管理团队，并且可能已提供此信息。</span><span class="sxs-lookup"><span data-stu-id="17f6a-110">Larger organizations usually have facilities or space management teams and might already have this info available.</span></span> <span data-ttu-id="17f6a-111">在小型组织中，搜索管理员可能需要创建并添加它。</span><span class="sxs-lookup"><span data-stu-id="17f6a-111">In a smaller organization, the Search admin might have to create and add it.</span></span>

## <a name="48-hours-before-you-begin"></a><span data-ttu-id="17f6a-112">开始之前的48小时</span><span class="sxs-lookup"><span data-stu-id="17f6a-112">48 hours before you begin</span></span>
<span data-ttu-id="17f6a-113">开始上载平面布置图之前，需要为用户的办公室位置编制索引。</span><span class="sxs-lookup"><span data-stu-id="17f6a-113">Before you start to upload floor plans, you need to index the users' office locations.</span></span> <span data-ttu-id="17f6a-114">根据组织的规模，最长可能需要48个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="17f6a-114">Depending on the size of your organization, it can take up to 48 hours to complete.</span></span> <span data-ttu-id="17f6a-115">如果忽略此步骤，则会在执行过程时收到错误。</span><span class="sxs-lookup"><span data-stu-id="17f6a-115">If you ignore this step, you get errors while performing the procedure.</span></span>

!["平面布置图" 页面的屏幕截图，其中包含 "Microsoft 需要先收集和组织办公室位置，然后才能上载平面布置图" 通知。](media/floorplans_hydrationstep.png)

<span data-ttu-id="17f6a-117">在 microsoft 365[管理中心](https://admin.microsoft.com)，转到 "**设置** > **Microsoft Search** > **平面计划**"，然后选择 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="17f6a-117">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Floor plans**, and then select **Get started**.</span></span>

<span data-ttu-id="17f6a-118">如果看不到此通知，则你或你的组织中的某个人已启动此步骤。</span><span class="sxs-lookup"><span data-stu-id="17f6a-118">If you don't see this notice, then you or someone in your organization has already initiated this step.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="17f6a-119">注意事项</span><span class="sxs-lookup"><span data-stu-id="17f6a-119">Things to consider</span></span>
<span data-ttu-id="17f6a-120">若要帮助用户查找有关办公室和建筑设施的信息，您需要添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="17f6a-120">To help users to find information about offices and building facilities, you need to add:</span></span>

|<span data-ttu-id="17f6a-121">方面</span><span class="sxs-lookup"><span data-stu-id="17f6a-121">Consideration</span></span>     |<span data-ttu-id="17f6a-122">这一点为什么重要？</span><span class="sxs-lookup"><span data-stu-id="17f6a-122">Why is this important?</span></span>  |
|---------|---------|
|<span data-ttu-id="17f6a-123">建筑物位置</span><span class="sxs-lookup"><span data-stu-id="17f6a-123">Building location</span></span>    |    <span data-ttu-id="17f6a-124">你需要将每个建筑物添加到 Microsoft 搜索位置。</span><span class="sxs-lookup"><span data-stu-id="17f6a-124">You'll need to add each building into Microsoft Search locations.</span></span> <span data-ttu-id="17f6a-125">应为每个建筑物提供标准命名格式。</span><span class="sxs-lookup"><span data-stu-id="17f6a-125">You should come up with a standard naming format for each building.</span></span> <span data-ttu-id="17f6a-126">您可以使用街道地址或地图坐标添加建筑物。</span><span class="sxs-lookup"><span data-stu-id="17f6a-126">You can add the building by using a street address or map coordinates.</span></span>     |
|<span data-ttu-id="17f6a-127">所有用户帐户上的**Office**属性</span><span class="sxs-lookup"><span data-stu-id="17f6a-127">**Office** property on all user accounts</span></span>     |    <span data-ttu-id="17f6a-128">每个用户帐户都需要将**office**属性与其办公室位置相关。</span><span class="sxs-lookup"><span data-stu-id="17f6a-128">Each user account needs to have the **office** property with their office location.</span></span> <span data-ttu-id="17f6a-129">并且办公室位置应遵循标准格式，包括建筑物、楼层和会议室信息。</span><span class="sxs-lookup"><span data-stu-id="17f6a-129">And office locations should follow a standard format and include building, floor and room info.</span></span>   <br> <span data-ttu-id="17f6a-130">在 Azure AD 中，此属性称为 " **PhysicalDeliveryOfficeName**"。</span><span class="sxs-lookup"><span data-stu-id="17f6a-130">In Azure AD, this property is called **PhysicalDeliveryOfficeName**.</span></span>    |
|<span data-ttu-id="17f6a-131">DWG 格式的楼面平面图文件</span><span class="sxs-lookup"><span data-stu-id="17f6a-131">Floor plan file in DWG format</span></span>     |   <span data-ttu-id="17f6a-132">您需要对建筑物的每个楼层或翼形使用单独的平面图，并将 office 信息包含在用户的 Office 属性中使用的相同格式。</span><span class="sxs-lookup"><span data-stu-id="17f6a-132">You need a separate floor plan for each floor or wing of your building and include the office information in the same format that you used in the user's Office property.</span></span> <span data-ttu-id="17f6a-133">文件必须采用 AutoCAD 绘图 DWG 格式。</span><span class="sxs-lookup"><span data-stu-id="17f6a-133">The file needs to be in AutoCAD drawing DWG format.</span></span> |

<span data-ttu-id="17f6a-134">有关详细信息，请参阅[Microsoft Search 平面图计划的最佳实践](floorplans-bestpractices.md)。</span><span class="sxs-lookup"><span data-stu-id="17f6a-134">For more information, see [Best practices for Microsoft Search floor plans](floorplans-bestpractices.md).</span></span>

## <a name="building-location"></a><span data-ttu-id="17f6a-135">建筑物位置</span><span class="sxs-lookup"><span data-stu-id="17f6a-135">Building location</span></span>

<span data-ttu-id="17f6a-136">确定需要作为位置添加的建筑物。</span><span class="sxs-lookup"><span data-stu-id="17f6a-136">Identify the buildings that need to be added as locations.</span></span> <span data-ttu-id="17f6a-137">建筑物的位置地址和映射坐标是第一个标识点。</span><span class="sxs-lookup"><span data-stu-id="17f6a-137">The location address and map coordinates of a building are the first point of identification.</span></span> <span data-ttu-id="17f6a-138">如果尚未将建筑物添加为位置，管理员需要添加它。</span><span class="sxs-lookup"><span data-stu-id="17f6a-138">If the building isn't added yet as a location, the admin needs to add it.</span></span> <span data-ttu-id="17f6a-139">有关详细信息，请参阅[管理位置](manage-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="17f6a-139">See [Manage Locations](manage-locations.md) for more details.</span></span>

## <a name="floor-plans-files"></a><span data-ttu-id="17f6a-140">平面布置图文件</span><span class="sxs-lookup"><span data-stu-id="17f6a-140">Floor plans files</span></span>

<span data-ttu-id="17f6a-141">在构建已确定后，您可以添加其楼面计划。</span><span class="sxs-lookup"><span data-stu-id="17f6a-141">After a building is identified, you can add its floor plans.</span></span> <span data-ttu-id="17f6a-142">所有平面布置图的文件必须采用 DWG 格式。</span><span class="sxs-lookup"><span data-stu-id="17f6a-142">All floor plan files must be in DWG format.</span></span> <span data-ttu-id="17f6a-143">如果您的组织尚不具备这些计划，则需要在与 DWG 兼容的应用中创建平面布置图。</span><span class="sxs-lookup"><span data-stu-id="17f6a-143">If your organization doesn't already have them, you need to create the floor plans in a DWG-compatible app.</span></span> <span data-ttu-id="17f6a-144">平面布置图必须正确映射所有聊天室，包括会议或会议室、restrooms、kitchens、邮件室和建筑物的每个基底的其他设施，以启用搜索。</span><span class="sxs-lookup"><span data-stu-id="17f6a-144">Floor plans must correctly map all rooms, including conference or meeting rooms, restrooms, kitchens, mail rooms, and other facilities on each floor of the building to enable search.</span></span>

### <a name="office-locations"></a><span data-ttu-id="17f6a-145">办公室位置</span><span class="sxs-lookup"><span data-stu-id="17f6a-145">Office locations</span></span>

<span data-ttu-id="17f6a-146">若要映射到平面布置图，所有办公地点和员工办公室数据都必须在用户帐户中。</span><span class="sxs-lookup"><span data-stu-id="17f6a-146">To be mapped to floor plans, all office locations and employee office data must be in the user's account.</span></span> <span data-ttu-id="17f6a-147">在平面图中，办公室位置必须是唯一的，并且不能重复。</span><span class="sxs-lookup"><span data-stu-id="17f6a-147">In the floor plan, the office locations must be unique and cannot repeat.</span></span> <span data-ttu-id="17f6a-148">例如，如果两个人共享 office 2/1173，则**2/1173**在你的平面布置图中只能有一个唯一的实例，但 Azure AD 中的用户帐户将具有相同的办公室位置。</span><span class="sxs-lookup"><span data-stu-id="17f6a-148">For example, if two people share office 2/1173, **2/1173** can only have one unique instance in your floor plans, but the user accounts in Azure AD will both have the same office location.</span></span>

![floorplans-peoplecard](media/floorplans-peoplecard.png)

 > [!Note] 
 > <span data-ttu-id="17f6a-150">当用户搜索同事的会议室或办公地点时，平面布置图中的房间号码将与 Azure AD 中的 office 位置相匹配。</span><span class="sxs-lookup"><span data-stu-id="17f6a-150">When a user searches for a room or office location of a colleague, the room numbers in floor plans are matched with office locations in Azure AD.</span></span> <span data-ttu-id="17f6a-151">如果找到匹配项，则显示地图。</span><span class="sxs-lookup"><span data-stu-id="17f6a-151">If a match is found, then the map is shown.</span></span>

## <a name="add-floor-plan"></a><span data-ttu-id="17f6a-152">添加楼面计划</span><span class="sxs-lookup"><span data-stu-id="17f6a-152">Add floor plan</span></span>

 <span data-ttu-id="17f6a-153">第一次转到平面图时，您可能会在页面顶部看到一条注释，指出， *Microsoft 需要先收集和组织办公室位置，然后才能上载平面布置图*。</span><span class="sxs-lookup"><span data-stu-id="17f6a-153">The first time you go to floor plans, you might see a note at the top of the page that says, *Microsoft needs to gather and organize office locations before you can upload floor plans*.</span></span> <span data-ttu-id="17f6a-154">选择 "**开始**"，为 Azure AD 办事处位置编制索引。</span><span class="sxs-lookup"><span data-stu-id="17f6a-154">Select **Get started** to index your Azure AD office locations.</span></span> 

1. <span data-ttu-id="17f6a-155">在[管理中心](https://admin.microsoft.com)中，转到 "**设置** > **Microsoft Search** >**平面计划**"，然后选择 "**添加平面图**"。</span><span class="sxs-lookup"><span data-stu-id="17f6a-155">In the [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** >**Floor plans**, and then select **Add floor plans**.</span></span>
4. <span data-ttu-id="17f6a-156">在下拉箭头中选择建筑物，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="17f6a-156">Select the building in the drop-down and select **Next**.</span></span> <span data-ttu-id="17f6a-157">如果未列出建筑物，则需要将其添加到 "位置"。</span><span class="sxs-lookup"><span data-stu-id="17f6a-157">If the building isn't listed, you need to add it in Locations.</span></span> <span data-ttu-id="17f6a-158">有关详细信息，请参阅[管理位置](manage-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="17f6a-158">See [Manage Locations](manage-locations.md) for more info.</span></span>
6. <span data-ttu-id="17f6a-159">选择 "**上载文件**"，然后选择要上传的平面布置图。</span><span class="sxs-lookup"><span data-stu-id="17f6a-159">Select **Upload files**, and then select the floor plan you want to upload.</span></span> 
1. <span data-ttu-id="17f6a-160">文件上载成功后，您需要确定楼层号或翼号如何表示。</span><span class="sxs-lookup"><span data-stu-id="17f6a-160">After the file uploads successfully, you need to identify how the floor number or wing is represented.</span></span> 
7. <span data-ttu-id="17f6a-161">输入标识建筑物的代码。</span><span class="sxs-lookup"><span data-stu-id="17f6a-161">Enter the code that identifies the building.</span></span> <span data-ttu-id="17f6a-162">可以在**Office location**属性中的用户帐户上找到生成代码。</span><span class="sxs-lookup"><span data-stu-id="17f6a-162">The building code can be found on the user's account in the **Office location** property.</span></span> <span data-ttu-id="17f6a-163">例如，如果用户的办公室位置是**2/1173**，则生成代码为**2**。</span><span class="sxs-lookup"><span data-stu-id="17f6a-163">For example, if the user's office location is **2/1173**, then building code is **2**.</span></span> 
9. <span data-ttu-id="17f6a-164">查看并确定所有上载的平面布置图的位置模式，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="17f6a-164">Review and identify the location patterns for all uploaded floor plans, and then select **Next**.</span></span>
10. <span data-ttu-id="17f6a-165">准备就绪后，请选择 "**发布**" 以使平面布置图可供搜索。</span><span class="sxs-lookup"><span data-stu-id="17f6a-165">When you're ready, select **Publish** to make the floor plan searchable.</span></span>

> [!Note] 
> <span data-ttu-id="17f6a-166">当平面图处于草稿状态时，该计划不完整。</span><span class="sxs-lookup"><span data-stu-id="17f6a-166">When a floor plan is in a draft state, it's incomplete.</span></span> <span data-ttu-id="17f6a-167">草稿允许风险承担者在上载和创建平面布置图时进行协调。</span><span class="sxs-lookup"><span data-stu-id="17f6a-167">A draft lets stakeholders coordinate in uploading and creating floor plans.</span></span> <span data-ttu-id="17f6a-168">它还允许您分阶段部署平面布置计划。</span><span class="sxs-lookup"><span data-stu-id="17f6a-168">It also allows you to deploy floor plans in stages.</span></span>

## <a name="edit-floor-plans"></a><span data-ttu-id="17f6a-169">编辑平面布置图</span><span class="sxs-lookup"><span data-stu-id="17f6a-169">Edit floor plans</span></span>

1. <span data-ttu-id="17f6a-170">在[管理中心](https://admin.microsoft.com)中，转到 "**设置** > **Microsoft Search** > **平面计划**"。</span><span class="sxs-lookup"><span data-stu-id="17f6a-170">In the [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Floor plans**.</span></span> 
1. <span data-ttu-id="17f6a-171">选择 "**已发布**" 或 "**草稿**"，选择要更改的平面布置图，然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="17f6a-171">Select **Published** or **Draft**, select the floor plan you want to change, and then select **Edit**.</span></span>
5. <span data-ttu-id="17f6a-172">进行更改，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="17f6a-172">Make your changes, and then select **Save**.</span></span>

## <a name="troubleshoot-errors"></a><span data-ttu-id="17f6a-173">错误疑难解答</span><span class="sxs-lookup"><span data-stu-id="17f6a-173">Troubleshoot errors</span></span>

<span data-ttu-id="17f6a-174">在解决所有错误之前，不能转到下一步来定义楼层、翼形和会议室信息。</span><span class="sxs-lookup"><span data-stu-id="17f6a-174">You can't go to the next step of defining floor, wing, and room information until all errors are fixed.</span></span> <span data-ttu-id="17f6a-175">下表列出了用于修复问题的文件上载错误消息和操作。</span><span class="sxs-lookup"><span data-stu-id="17f6a-175">The following table lists file upload error messages and actions for fixing the issues.</span></span>

| <span data-ttu-id="17f6a-176">错误消息</span><span class="sxs-lookup"><span data-stu-id="17f6a-176">Error message</span></span>   | <span data-ttu-id="17f6a-177">类型</span><span class="sxs-lookup"><span data-stu-id="17f6a-177">Type</span></span>    | <span data-ttu-id="17f6a-178">Action</span><span class="sxs-lookup"><span data-stu-id="17f6a-178">Action</span></span>       |
|:----------------| :--------- | :-------------- |
| <span data-ttu-id="17f6a-179">无法读取 CC_1 dwg。</span><span class="sxs-lookup"><span data-stu-id="17f6a-179">Unable to read CC_1.dwg.</span></span> <span data-ttu-id="17f6a-180">请重新上载或删除楼面计划。</span><span class="sxs-lookup"><span data-stu-id="17f6a-180">Please re-upload or delete the floor plan.</span></span> | <span data-ttu-id="17f6a-181">Error</span><span class="sxs-lookup"><span data-stu-id="17f6a-181">Error</span></span> |  <span data-ttu-id="17f6a-182">请再次尝试上载文件。</span><span class="sxs-lookup"><span data-stu-id="17f6a-182">Try uploading the file again.</span></span> <span data-ttu-id="17f6a-183">如果不起作用，请删除该文件，然后再试一次。</span><span class="sxs-lookup"><span data-stu-id="17f6a-183">If that doesn't work, delete the file, and then try again.</span></span> |
| <span data-ttu-id="17f6a-184">有两个名为 CC_1 的文件。</span><span class="sxs-lookup"><span data-stu-id="17f6a-184">There are two files named CC_1.dwg.</span></span> <span data-ttu-id="17f6a-185">请删除其中一个名称，或使用另一个名称重新上载。</span><span class="sxs-lookup"><span data-stu-id="17f6a-185">Please delete one of them or re-upload with another name.</span></span>| <span data-ttu-id="17f6a-186">Error</span><span class="sxs-lookup"><span data-stu-id="17f6a-186">Error</span></span> | <span data-ttu-id="17f6a-187">如果文件名不正确，请通过添加 floor 或翼形信息来使文件名成为唯一的，然后重新上传文件。</span><span class="sxs-lookup"><span data-stu-id="17f6a-187">If the file name is incorrect, make the file name unique by adding floor or wing information, and then upload the file again.</span></span> <br><br><span data-ttu-id="17f6a-188">如果意外添加了同一文件两次，只需将其删除即可。</span><span class="sxs-lookup"><span data-stu-id="17f6a-188">If you accidentally added the same file twice, just delete it.</span></span> |
| <span data-ttu-id="17f6a-189">找不到数据。</span><span class="sxs-lookup"><span data-stu-id="17f6a-189">No data found.</span></span> | <span data-ttu-id="17f6a-190">Error</span><span class="sxs-lookup"><span data-stu-id="17f6a-190">Error</span></span> | <span data-ttu-id="17f6a-191">请检查您的文件以确保其正确无误，然后重新上传，或将其删除。</span><span class="sxs-lookup"><span data-stu-id="17f6a-191">Check your file to make sure it's the correct one, and then upload it again, or delete it.</span></span> |
| <span data-ttu-id="17f6a-192">此文件中缺少外部引用。</span><span class="sxs-lookup"><span data-stu-id="17f6a-192">External references are missing in this file.</span></span> <span data-ttu-id="17f6a-193">请上载 "CC_1_furniture dwg" 或删除此文件。</span><span class="sxs-lookup"><span data-stu-id="17f6a-193">Either upload "CC_1_furniture.dwg" or delete this file.</span></span> | <span data-ttu-id="17f6a-194">警告</span><span class="sxs-lookup"><span data-stu-id="17f6a-194">Warning</span></span> | <span data-ttu-id="17f6a-195">上载外部引用文件或删除。</span><span class="sxs-lookup"><span data-stu-id="17f6a-195">Upload external reference files or delete.</span></span>|
| <span data-ttu-id="17f6a-196">无法读取 DWG 文件中的会议室编号或标签。</span><span class="sxs-lookup"><span data-stu-id="17f6a-196">Could not read room numbers or tags in the DWG file.</span></span> <span data-ttu-id="17f6a-197">请删除此文件。</span><span class="sxs-lookup"><span data-stu-id="17f6a-197">Please delete  this file.</span></span> | <span data-ttu-id="17f6a-198">警告</span><span class="sxs-lookup"><span data-stu-id="17f6a-198">Warning</span></span> | <span data-ttu-id="17f6a-199">请检查 DWG 文件以确保包含数据，然后删除该文件，然后重试。</span><span class="sxs-lookup"><span data-stu-id="17f6a-199">Check your DWG file to make sure the data is included, and then delete the file and try again.</span></span> |
