---
title: Analysis Services обратной совместимости | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- installing Analysis Services, backward compatibility
- backward compatibility [Analysis Services]
- compatibility [Analysis Services]
- Analysis Services, backward compatibility
- upgrading Analysis Services
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
ms.assetid: 618b6c3a-e20d-47a9-b2c6-6d848dfba05a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44a5296bfbd2bae746eb9936d416fd696de16cb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656929"
---
# <a name="analysis-services-backward-compatibility"></a><span data-ttu-id="b6ad4-102">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="b6ad4-102">Analysis Services Backward Compatibility</span></span>
  <span data-ttu-id="b6ad4-103">В подразделах этого раздела описываются изменения в поведении между версиями [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6ad4-103">The topics in this section describe the changes in behavior between versions of  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6ad4-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="b6ad4-104">In This Section</span></span>  
  
|<span data-ttu-id="b6ad4-105">Разделы</span><span class="sxs-lookup"><span data-stu-id="b6ad4-105">Topics</span></span>|<span data-ttu-id="b6ad4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b6ad4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6ad4-107">Устаревшие функции служб Analysis Services в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b6ad4-107">Deprecated Analysis Services Features in SQL Server 2014</span></span>](deprecated-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="b6ad4-108">Описание функций, сохраненных в текущей версии для обеспечения совместимости с предыдущими версиями; эти функции будут удалены в следующей версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6ad4-108">Describes features that have been retained in the current version to maintain backward compatibility,  but which will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="b6ad4-109">Неподдерживаемые функции служб Analysis Services в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b6ad4-109">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>](discontinued-analysis-services-functionality-in-sql-server-2014.md)|<span data-ttu-id="b6ad4-110">Описание функций, существовавших в более ранних версиях служб  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и удаленных в позднейших версиях.</span><span class="sxs-lookup"><span data-stu-id="b6ad4-110">Describes features that existed in earlier versions of  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] but that have since been removed in later versions.</span></span>|  
|[<span data-ttu-id="b6ad4-111">Критические изменения функций служб Analysis Services в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b6ad4-111">Breaking Changes to Analysis Services Features in SQL Server 2014</span></span>](breaking-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="b6ad4-112">Описание изменений кода, представленных в этом выпуске [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , которые потенциально могут приводить к сбоям в работе модели, пользовательских приложений или сценария, созданных в предыдущих версиях программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b6ad4-112">Describes code changes introduced in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that could potentially break a model or custom applications or script created in previous versions of the software .</span></span>|  
|[<span data-ttu-id="b6ad4-113">Изменение работы функций служб Analysis Services в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b6ad4-113">Behavior Changes to Analysis Services Features in SQL Server 2014</span></span>](behavior-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="b6ad4-114">Описание существующих компонентов, которые функционируют иным образом в рамках данного выпуска [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6ad4-114">Describes existing features that have different behaviors in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="b6ad4-115">Распространенные примеры включают изменение значений по умолчанию и присвоение параметрам новых или других значений, которые делают невозможным выполнение ранее допустимых операций или конфигураций, или возникновение необходимости вручную изменять параметр или конфигурацию, которые могли быть удалены во время обновления.</span><span class="sxs-lookup"><span data-stu-id="b6ad4-115">Common examples include changing a default to a new or different value, disallowing a previously allowable operation or configuration, or a introducing a requirement to manually revise or replace a setting or configuration that is lost during upgrade.</span></span><br /> <span data-ttu-id="b6ad4-116">.</span><span class="sxs-lookup"><span data-stu-id="b6ad4-116">.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6ad4-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="b6ad4-117">See Also</span></span>  
 <span data-ttu-id="b6ad4-118">[Новые возможности Analysis Services и бизнес-аналитики](what-s-new-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="b6ad4-118">[What's New in Analysis Services and Business Intelligence](what-s-new-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="b6ad4-119">Обновление служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b6ad4-119">Upgrade Analysis Services</span></span>](../database-engine/install-windows/upgrade-analysis-services.md)  
  
  
