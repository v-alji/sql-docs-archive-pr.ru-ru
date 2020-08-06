---
title: Запуск помощника по обновлению (пользовательский интерфейс) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Report Viewer
- Upgrade Advisor [SQL Server], running
- launching Upgrade Advisor
- Upgrade Advisor Analysis Wizard
- starting Upgrade Advisor
- SQL Server Upgrade Advisor, running
ms.assetid: 7f47c9b3-88d3-43d6-837e-f157b49a55ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a5e47ef2b8183823dff884e114adc420e371adf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668605"
---
# <a name="running-upgrade-advisor-user-interface"></a><span data-ttu-id="d0d5d-102">Запуск помощника по обновлению (пользовательский интерфейс)</span><span class="sxs-lookup"><span data-stu-id="d0d5d-102">Running Upgrade Advisor (User Interface)</span></span>
  <span data-ttu-id="d0d5d-103">Советник по переходу может быть запущен для анализа локальных или удаленных компонентов в процессе планирования обновления.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-103">You can run Upgrade Advisor to analyze local or remote components during upgrade planning.</span></span> <span data-ttu-id="d0d5d-104">Для каждого проанализированного компонента и экземпляра помощник по обновлению создает отчет.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-104">Upgrade Advisor produces a report for each component and instance that is analyzed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d0d5d-105">Помощник по обновлению не анализирует удаленные экземпляры служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0d5d-105">Upgrade Advisor does not analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="d0d5d-106">Чтобы выполнить анализ экземпляра служб [!INCLUDE[ssRS](../../includes/ssrs.md)], необходимо установить помощник по обновлению на компьютере, где установлены службы [!INCLUDE[ssRS](../../includes/ssrs.md)].</span><span class="sxs-lookup"><span data-stu-id="d0d5d-106">To analyze an instance of [!INCLUDE[ssRS](../../includes/ssrs.md)], Upgrade Advisor must be installed on the computer where [!INCLUDE[ssRS](../../includes/ssrs.md)] is installed.</span></span>  
>   
>  <span data-ttu-id="d0d5d-107">Для анализа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services на одном компьютере должны быть [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] установлены и [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] установлены.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-107">To analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, you must have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] installed and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed on the same computer.</span></span>  
  
## <a name="running-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="d0d5d-108">Мастер анализа помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="d0d5d-108">Running the Upgrade Advisor Analysis Wizard</span></span>  
 <span data-ttu-id="d0d5d-109">Работа мастера анализа помощника по обновлению включает шесть этапов.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-109">Running the Upgrade Advisor Analysis Wizard has six steps:</span></span>  
  
1.  <span data-ttu-id="d0d5d-110">Запустите мастер с начальной страницы помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-110">Launch the wizard from the Upgrade Advisor start page.</span></span>  
  
2.  <span data-ttu-id="d0d5d-111">Определите анализируемый сервер и компоненты.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-111">Identify server and components to analyze.</span></span>  
  
3.  <span data-ttu-id="d0d5d-112">Соберите сведения для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-112">Gather authentication information.</span></span>  
  
4.  <span data-ttu-id="d0d5d-113">Определите дополнительные параметры в зависимости от типа компонентов.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-113">Gather additional parameters based on component type.</span></span>  
  
5.  <span data-ttu-id="d0d5d-114">Выполните анализ выбранных компонентов.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-114">Analyze selected components.</span></span>  
  
6.  <span data-ttu-id="d0d5d-115">Создайте отчет о выявленных проблемах обновления.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-115">Generate report of upgrade issues.</span></span>  
  
 <span data-ttu-id="d0d5d-116">Дополнительные сведения о мастере анализа помощника по обновлению см. в разделе [инструкции. Запуск мастера анализа помощника по обновлению](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d0d5d-116">For more information about the Upgrade Advisor Analysis Wizard, see [How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span></span>  
  
 <span data-ttu-id="d0d5d-117">Конкретные сведения, необходимые для каждого шага, см. в разделе [Справочник по пользовательскому интерфейсу помощника по обновлению](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d0d5d-117">For specific information that is required for each step, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
## <a name="running-the-upgrade-advisor-report-viewer"></a><span data-ttu-id="d0d5d-118">Средство просмотра отчетов помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="d0d5d-118">Running the Upgrade Advisor Report Viewer</span></span>  
 <span data-ttu-id="d0d5d-119">Средство просмотра отчетов помощника по обновлению используется для просмотра отчетов, созданных мастером анализа помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-119">You use the Upgrade Advisor Report Viewer to view reports generated by the Upgrade Advisor Analysis Wizard.</span></span> <span data-ttu-id="d0d5d-120">После загрузки отчета его компоненты можно отфильтровать по следующим параметрам:</span><span class="sxs-lookup"><span data-stu-id="d0d5d-120">When the report is loaded, you can filter the components of the report by the following factors:</span></span>  
  
-   <span data-ttu-id="d0d5d-121">все проблемы;</span><span class="sxs-lookup"><span data-stu-id="d0d5d-121">All issues</span></span>  
  
-   <span data-ttu-id="d0d5d-122">все проблемы, связанные с обновлением;</span><span class="sxs-lookup"><span data-stu-id="d0d5d-122">All upgrade issues</span></span>  
  
-   <span data-ttu-id="d0d5d-123">проблемы, связанные с подготовкой к обновлению;</span><span class="sxs-lookup"><span data-stu-id="d0d5d-123">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="d0d5d-124">все проблемы, связанные с миграцией;</span><span class="sxs-lookup"><span data-stu-id="d0d5d-124">All migration issues</span></span>  
  
-   <span data-ttu-id="d0d5d-125">устраненные проблемы.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-125">Resolved issues</span></span>  
  
-   <span data-ttu-id="d0d5d-126">Неустраненные проблемы</span><span class="sxs-lookup"><span data-stu-id="d0d5d-126">Unresolved issues</span></span>  
  
 <span data-ttu-id="d0d5d-127">Пошаговые инструкции по использованию средства просмотра отчетов см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d0d5d-127">For step-by-step instructions for using the report viewer, see the following topics:</span></span>  
  
-   [<span data-ttu-id="d0d5d-128">Просмотр отчета помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="d0d5d-128">How to: View an Upgrade Advisor Report</span></span>](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md)  
  
-   [<span data-ttu-id="d0d5d-129">Фильтрация отчетов</span><span class="sxs-lookup"><span data-stu-id="d0d5d-129">How to: Filter Reports</span></span>](../../../2014/sql-server/install/how-to-filter-reports.md)  
  
-   [<span data-ttu-id="d0d5d-130">Экспорт отчетов</span><span class="sxs-lookup"><span data-stu-id="d0d5d-130">How to: Export Reports</span></span>](../../../2014/sql-server/install/how-to-export-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="d0d5d-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0d5d-131">See Also</span></span>  
 <span data-ttu-id="d0d5d-132">[Как запустить мастер анализа помощника по обновлению](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="d0d5d-132">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="d0d5d-133">[Справочник по пользовательскому интерфейсу помощника по обновлению](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d0d5d-133">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 <span data-ttu-id="d0d5d-134">[Устранение проблем с обновлением](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="d0d5d-134">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="d0d5d-135">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="d0d5d-135">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
