---
title: На компьютере сервера отчетов обнаружены устаревшие расширения (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 40d245a2-0631-470e-81b3-1feb47e028cb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 9da9c47285bf809fdf6c89d67e847304d7d29a81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668037"
---
# <a name="obsolete-extensions-were-detected-on-the-report-server-computer-upgrade-advisor"></a><span data-ttu-id="9a220-102">На компьютере сервера отчетов обнаружены устаревшие модули (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="9a220-102">Obsolete extensions were detected on the report server computer (Upgrade Advisor)</span></span>
  <span data-ttu-id="9a220-103">Советник по переходу обнаружил один или несколько модулей подготовки отчетов, которые в текущей версии недоступны.</span><span class="sxs-lookup"><span data-stu-id="9a220-103">Upgrade Advisor detected one or more rendering extensions that are no longer available in the current release.</span></span>  
  
||  
|-|  
|<span data-ttu-id="9a220-104">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Режим интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9a220-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="9a220-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="9a220-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="9a220-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9a220-106">Description</span></span>  
 <span data-ttu-id="9a220-107">Сервер отчетов настроен для использования одного или нескольких модулей, неподдерживаемых в этой версии.</span><span class="sxs-lookup"><span data-stu-id="9a220-107">The report server is configured to use one or more extensions that have been discontinued in this release.</span></span> <span data-ttu-id="9a220-108">В число неподдерживаемых модулей входят:</span><span class="sxs-lookup"><span data-stu-id="9a220-108">Discontinued extensions include:</span></span>  
  
-   <span data-ttu-id="9a220-109">модуль в формате HTML подготовки отчетов к просмотру для веб-компонентов Office;</span><span class="sxs-lookup"><span data-stu-id="9a220-109">HTML OWC rendering extension</span></span>  
  
-   <span data-ttu-id="9a220-110">модуль в формате HTML 3.2. подготовки отчетов к просмотру</span><span class="sxs-lookup"><span data-stu-id="9a220-110">HTML 3.2 rendering extension</span></span>  
  
 <span data-ttu-id="9a220-111">Процесс обновления может быть продолжен, но функции, которые не поддерживаются, на обновленном сервере отчетов доступны не будут.</span><span class="sxs-lookup"><span data-stu-id="9a220-111">Upgrade can continue, but the unsupported functionality will no longer be available on the upgraded report server.</span></span>  
  
 <span data-ttu-id="9a220-112">Если эти модули все еще необходимы, не выполняйте обновление до тех пор, пока не найдете альтернативного решения.</span><span class="sxs-lookup"><span data-stu-id="9a220-112">If you require these extensions, do not upgrade until you find an alternate solution to these requirements.</span></span> <span data-ttu-id="9a220-113">Вероятно, может потребоваться получение или создание пользовательского модуля подготовки отчетов к просмотру, предоставляющего идентичные или схожие функции.</span><span class="sxs-lookup"><span data-stu-id="9a220-113">You might need to obtain or build a custom rendering extension that provides the same or similar functionality.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9a220-114">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="9a220-114">Corrective Action</span></span>  
 <span data-ttu-id="9a220-115">Оцените существующий набор функций служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], чтобы определить, выполняют ли поддерживаемые функции необходимые требования.</span><span class="sxs-lookup"><span data-stu-id="9a220-115">Evaluate the current set of features that are included in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] to determine whether supported functionality meets your requirements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a220-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a220-116">See Also</span></span>  
 [<span data-ttu-id="9a220-117">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="9a220-117">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
