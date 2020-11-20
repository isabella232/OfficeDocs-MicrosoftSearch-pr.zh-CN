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
ms.openlocfilehash: 592e108fe0333e4faf8ff2e4618f9d5216847b8a
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367664"
---
# <a name="microsoft-graph-connectors-preview-release-and-features"></a><span data-ttu-id="a4315-103">Microsoft Graph 连接器预览版本和功能</span><span class="sxs-lookup"><span data-stu-id="a4315-103">Microsoft Graph connectors preview release and features</span></span>

<span data-ttu-id="a4315-104">Microsoft Graph 连接器和 Microsoft Search Api 现已正式推出。</span><span class="sxs-lookup"><span data-stu-id="a4315-104">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="a4315-105">初始部署将面向为目标版本配置的客户。</span><span class="sxs-lookup"><span data-stu-id="a4315-105">The initial rollout will be to customers configured for Targeted Release.</span></span> <span data-ttu-id="a4315-106">在完成向所有租户的部署后，连接器内容中的索引配额使用率将成为计费的依据。</span><span class="sxs-lookup"><span data-stu-id="a4315-106">Upon rollout completion to all tenants, index quota utilization from connectors content will become subject to billing.</span></span> <span data-ttu-id="a4315-107">有关详细信息，请参阅 [许可要求和定价](licensing.md) 。</span><span class="sxs-lookup"><span data-stu-id="a4315-107">See [Licensing requirements and pricing](licensing.md) for more information.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="a4315-108">设置目标版本</span><span class="sxs-lookup"><span data-stu-id="a4315-108">Set up Targeted release</span></span>

<span data-ttu-id="a4315-109">如果要在部署过程中在租户中使用 Graph 连接器，则必须选择目标版本。</span><span class="sxs-lookup"><span data-stu-id="a4315-109">If you want to use Graph connectors in your tenant during rollout, you must opt into Targeted release.</span></span> <span data-ttu-id="a4315-110">若要了解有关目标发布选项及其设置方式的详细信息，请参阅 [在 Office 365 中设置标准或目标发布选项](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="a4315-110">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="preview-features"></a><span data-ttu-id="a4315-111">预览功能</span><span class="sxs-lookup"><span data-stu-id="a4315-111">Preview features</span></span>

<span data-ttu-id="a4315-112">虽然 Microsoft Graph 连接器和 Microsoft 搜索 Api 现在现已推出，但在预览中仍有几项功能会保留。</span><span class="sxs-lookup"><span data-stu-id="a4315-112">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that will remain in preview.</span></span>

<span data-ttu-id="a4315-113">预览中的连接器和功能集包括：</span><span class="sxs-lookup"><span data-stu-id="a4315-113">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="a4315-114">Azure DevOps 连接器</span><span class="sxs-lookup"><span data-stu-id="a4315-114">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="a4315-115">Salesforce 连接器</span><span class="sxs-lookup"><span data-stu-id="a4315-115">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="a4315-116">具有使用源 Acl 的搜索权限的[ServiceNow 连接器](servicenow.md)</span><span class="sxs-lookup"><span data-stu-id="a4315-116">[ServiceNow connector](servicenow.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="a4315-117">管理结果群集</span><span class="sxs-lookup"><span data-stu-id="a4315-117">Manage result cluster</span></span>](result-cluster.md)