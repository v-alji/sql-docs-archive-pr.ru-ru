---
title: На сайте сервера отчетов обнаружены фильтры ISAPI (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- ISAPI filters
- report servers [Reporting Services], upgrade issues
ms.assetid: dd30560d-9e16-47c7-ba68-a9743a657e4e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: bff1834ddf1b8f90787a47a8fd58a240d2b715d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749615"
---
# <a name="isapi-filters-detected-on-the-report-server-site-upgrade-advisor"></a><span data-ttu-id="515d6-102">На сайте сервера отчетов обнаружены фильтры ISAPI (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="515d6-102">ISAPI filters detected on the report server site (Upgrade Advisor)</span></span>
  <span data-ttu-id="515d6-103">Помощник по обновлению обнаружил на веб-сайте, на котором размещен сервер отчетов и виртуальные каталоги диспетчера отчетов, один или несколько фильтров ISAPI.</span><span class="sxs-lookup"><span data-stu-id="515d6-103">Upgrade Advisor detected one or more ISAPI filters on the Web site that hosts the report server and Report Manager virtual directories.</span></span> <span data-ttu-id="515d6-104">Фильтры ISAPI не поддерживаются в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="515d6-104">ISAPI filters are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="515d6-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственной.</span><span class="sxs-lookup"><span data-stu-id="515d6-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native .</span></span>|  
  
## <a name="component"></a><span data-ttu-id="515d6-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="515d6-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="515d6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="515d6-107">Description</span></span>  
 <span data-ttu-id="515d6-108">Перед обновлением проверьте, используются ли приложениями служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] фильтры ISAPI на сайте.</span><span class="sxs-lookup"><span data-stu-id="515d6-108">Before upgrading, verify whether the ISAPI filters on the Web site are used by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applications.</span></span> <span data-ttu-id="515d6-109">Если фильтр ISAPI не требуется, сервер отчетов можно обновлять.</span><span class="sxs-lookup"><span data-stu-id="515d6-109">If you do not require the ISAPI filter, you can upgrade the report server.</span></span> <span data-ttu-id="515d6-110">Программа установки создаст URL-адреса по умолчанию без поддержки фильтров ISAPI, выполняющихся на сервере IIS.</span><span class="sxs-lookup"><span data-stu-id="515d6-110">Setup will create the default URLs, without support for the ISAPI filter that runs in IIS.</span></span> <span data-ttu-id="515d6-111">Если фильтр ISAPI необходим, не производите обновление, пока не найдете альтернативный способ размещения фильтра ISAPI (например, можно использовать сервер ISA или продолжить размещение фильтра ISA на сервере IIS).</span><span class="sxs-lookup"><span data-stu-id="515d6-111">If you require the ISAPI filter, do not upgrade until you find an alternative way of hosting the ISAPI filter (for example, using ISA Server or continuing to host the ISAPI filter in IIS).</span></span> <span data-ttu-id="515d6-112">Сервер отчетов поддерживает использование HTTP-модулей ASP.NET в качестве замены для фильтров ISAPI в некоторых сценариях.</span><span class="sxs-lookup"><span data-stu-id="515d6-112">The report server supports ASP.NET HTTPModules as a replacement for ISAPI filters in certain scenarios.</span></span> <span data-ttu-id="515d6-113">Дополнительные сведения см. в документации Windows или в MSDN.</span><span class="sxs-lookup"><span data-stu-id="515d6-113">For more information, see the ASP.NET documentation on MSDN.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="515d6-114">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="515d6-114">Corrective Action</span></span>  
 <span data-ttu-id="515d6-115">Найдите и используйте отдельное решение для размещения фильтров ISAPI, необходимых для работы развертывания.</span><span class="sxs-lookup"><span data-stu-id="515d6-115">Evaluate and use a separate solution for hosting ISAPI filters required by your deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515d6-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="515d6-116">See Also</span></span>  
 [<span data-ttu-id="515d6-117">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="515d6-117">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
