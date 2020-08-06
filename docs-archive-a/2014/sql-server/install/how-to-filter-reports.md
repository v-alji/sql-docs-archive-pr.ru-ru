---
title: Как фильтровать отчеты | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reports [Upgrade Advisor], filtering
- filtering reports [Reporting Services]
ms.assetid: bc3dbe16-f6c1-4f07-8d88-2b8e86302c7e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4946b9ea208c0fad98426b7c7fc4247cfaa47680
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668066"
---
# <a name="how-to-filter-reports"></a><span data-ttu-id="7d311-102">Фильтрация отчетов</span><span class="sxs-lookup"><span data-stu-id="7d311-102">How to: Filter Reports</span></span>
  <span data-ttu-id="7d311-103">В этом разделе описывается использование средства просмотра отчетов помощника по обновлению для фильтрации отчетов.</span><span class="sxs-lookup"><span data-stu-id="7d311-103">This topic describes how you can use the Upgrade Advisor Report Viewer to apply filters to a report.</span></span>  
  
### <a name="to-filter-reports"></a><span data-ttu-id="7d311-104">Фильтрация отчетов</span><span class="sxs-lookup"><span data-stu-id="7d311-104">To filter reports</span></span>  
  
1.  <span data-ttu-id="7d311-105">Откройте в средстве просмотра отчетов отчет, который необходимо отфильтровать.</span><span class="sxs-lookup"><span data-stu-id="7d311-105">In the report viewer, display the report that you want to filter.</span></span> <span data-ttu-id="7d311-106">Инструкции см. в разделе Пошаговое [руководство. Просмотр отчета советника по переходу](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md).</span><span class="sxs-lookup"><span data-stu-id="7d311-106">For instructions, see [How to: View an Upgrade Advisor Report](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md).</span></span>  
  
2.  <span data-ttu-id="7d311-107">В списке **Фильтровать по** выберите тип проблемы для просмотра.</span><span class="sxs-lookup"><span data-stu-id="7d311-107">In the **Filter by** list, select a type of issue to view:</span></span>  
  
    -   <span data-ttu-id="7d311-108">**Все проблемы**.</span><span class="sxs-lookup"><span data-stu-id="7d311-108">**All issues**.</span></span> <span data-ttu-id="7d311-109">В этом случае отображаются все проблемы, не помеченные как решенные.</span><span class="sxs-lookup"><span data-stu-id="7d311-109">This displays all issues that have not been marked as resolved.</span></span>  
  
    -   <span data-ttu-id="7d311-110">**Все проблемы с обновлением**.</span><span class="sxs-lookup"><span data-stu-id="7d311-110">**All upgrade issues**.</span></span> <span data-ttu-id="7d311-111">Отображаются все проблемы, связанные с обновлением до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d311-111">This displays all issues that are related to upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
    -   <span data-ttu-id="7d311-112">**Проблемы перед обновлением**.</span><span class="sxs-lookup"><span data-stu-id="7d311-112">**Pre-upgrade issues**.</span></span> <span data-ttu-id="7d311-113">Отображаются все проблемы, которые необходимо решить перед обновлением до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d311-113">This displays all issues that should or must be fixed before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
    -   <span data-ttu-id="7d311-114">**Все проблемы с миграцией**.</span><span class="sxs-lookup"><span data-stu-id="7d311-114">**All migration issues**.</span></span> <span data-ttu-id="7d311-115">Отображаются все проблемы, связанные с переносом данных или приложений на [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d311-115">This displays all issues that are related to migrating data or applications to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
    -   <span data-ttu-id="7d311-116">**Устраненные проблемы**.</span><span class="sxs-lookup"><span data-stu-id="7d311-116">**Resolved Issues**.</span></span> <span data-ttu-id="7d311-117">Отображаются все проблемы, помеченные как решенные.</span><span class="sxs-lookup"><span data-stu-id="7d311-117">This displays all issues that have been marked as resolved.</span></span>  
  
    -   <span data-ttu-id="7d311-118">**Неразрешенные проблемы**.</span><span class="sxs-lookup"><span data-stu-id="7d311-118">**Unresolved Issues**.</span></span> <span data-ttu-id="7d311-119">Отображаются все проблемы, которые еще не были решены.</span><span class="sxs-lookup"><span data-stu-id="7d311-119">This displays all issues that have not yet been resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d311-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d311-120">See Also</span></span>  
 <span data-ttu-id="7d311-121">[Как запустить мастер анализа помощника по обновлению](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="7d311-121">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="7d311-122">[Устранение проблем с обновлением](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="7d311-122">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 <span data-ttu-id="7d311-123">[Инструкции по советнику по переходу](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="7d311-123">[Upgrade Advisor How-to Topics](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span></span>  
 [<span data-ttu-id="7d311-124">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="7d311-124">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
