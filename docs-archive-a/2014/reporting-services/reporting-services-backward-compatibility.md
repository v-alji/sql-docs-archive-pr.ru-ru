---
title: Reporting Services обратной совместимости | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- SSRS, backward compatibility
- SQL Server Reporting Services, backward compatibility
- backward compatibility [Reporting Services]
ms.assetid: 675b0e0e-cfee-4790-9675-80fc3ea6d30f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7203740ba7f52dfc2cd3793a20fed9fecf5f9468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734981"
---
# <a name="reporting-services-backward-compatibility"></a><span data-ttu-id="5a363-102">Обратная совместимость служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5a363-102">Reporting Services Backward Compatibility</span></span>
  <span data-ttu-id="5a363-103">В этом разделе описываются изменения в поведении между версиями [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a363-103">This section describes changes in behavior between versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5a363-104">Здесь рассмотрены функции, которые больше не доступны или запланированы к удалению в следующем выпуске.</span><span class="sxs-lookup"><span data-stu-id="5a363-104">It covers features that are no longer available or are scheduled to be removed in a future release.</span></span> <span data-ttu-id="5a363-105">Также описаны фундаментальные изменения в продукте, которые полностью изменят пользовательское приложение, включающее службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a363-105">It also describes fundamental changes to the product that are known to break a custom application that includes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a363-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="5a363-106">In This Section</span></span>  
  
|<span data-ttu-id="5a363-107">Раздел</span><span class="sxs-lookup"><span data-stu-id="5a363-107">Topic</span></span>|<span data-ttu-id="5a363-108">Description</span><span class="sxs-lookup"><span data-stu-id="5a363-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5a363-109">Неподдерживаемые возможности в службах SQL Server Reporting Services в версии SQL Server "2014"</span><span class="sxs-lookup"><span data-stu-id="5a363-109">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)|<span data-ttu-id="5a363-110">Описание функций, существовавших в более ранних версиях служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и удаленных в позднейших версиях.</span><span class="sxs-lookup"><span data-stu-id="5a363-110">Describes features that existed in earlier versions of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] but that have been removed in later versions.</span></span>|  
|[<span data-ttu-id="5a363-111">Устаревшие функции служб SQL Server Reporting Services в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5a363-111">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>](deprecated-features-in-sql-server-reporting-services-ssrs.md)|<span data-ttu-id="5a363-112">Описание функций, сохраненных в данном выпуске в службах [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] для обеспечения обратной совместимости с предыдущими версиями; эти функции будут удалены в следующей версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a363-112">Describes features that exist this release of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] for backward compatibility, but which will be removed in a future version of SQL Server.</span></span>|  
|[<span data-ttu-id="5a363-113">Критические изменения в службах SQL Server Reporting Services в выпуске SQL Server «2014»</span><span class="sxs-lookup"><span data-stu-id="5a363-113">Breaking Changes in SQL Server Reporting Services in SQL Server 2014</span></span>](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="5a363-114">Описание проблем, которые могут возникнуть при обновлении версии служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a363-114">Describes issues that you might encounter when you upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="5a363-115">Изменения в работе служб SQL Server Reporting Services в выпуске SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5a363-115">Behavior Changes to SQL Server Reporting Services  in SQL Server 2014</span></span>](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="5a363-116">Описание функций, изменившихся в службах [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a363-116">Describes features that have changed in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a363-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a363-117">See Also</span></span>  
 <span data-ttu-id="5a363-118">[Обратная совместимость](../../2014/getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="5a363-118">[Backward Compatibility](../../2014/getting-started/backward-compatibility.md) </span></span>  
 [<span data-ttu-id="5a363-119">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="5a363-119">Analysis Services Backward Compatibility</span></span>](../../2014/analysis-services/analysis-services-backward-compatibility.md)  
  
  
