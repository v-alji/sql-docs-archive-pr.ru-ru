---
title: Руководство. Просмотр отчета советника по переходу | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- viewing reports
- Upgrade Advisor [SQL Server], reports
- SQL Server Upgrade Advisor, reports
- reports [Upgrade Advisor], viewing
ms.assetid: d13b38af-0ac3-4030-83cd-e7d7825dd09f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e6df35b869186a601458889c348153093ccbce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668052"
---
# <a name="how-to-view-an-upgrade-advisor-report"></a><span data-ttu-id="d35b6-102">Просмотр отчета помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="d35b6-102">How to: View an Upgrade Advisor Report</span></span>
  <span data-ttu-id="d35b6-103">Помощник по обновлению создает отчеты по каждому компоненту, выбранному для анализа.</span><span class="sxs-lookup"><span data-stu-id="d35b6-103">Upgrade Advisor creates reports for each component that you select to analyze.</span></span> <span data-ttu-id="d35b6-104">В этом разделе рассказывается о том, как просмотреть отчет помощника по обновлению с начальной страницы помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="d35b6-104">This topic describes how to view an Upgrade Advisor report from the Upgrade Advisor start page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d35b6-105">Средство просмотра отчетов загружает файлы, предполагая, что они имеют стандартные имена.</span><span class="sxs-lookup"><span data-stu-id="d35b6-105">The report viewer loads files based on standard file names.</span></span> <span data-ttu-id="d35b6-106">Если файлы переименованы, средство просмотра отчетов их не загрузит.</span><span class="sxs-lookup"><span data-stu-id="d35b6-106">If the files have been renamed, the report viewer will not load them.</span></span>  
  
### <a name="to-view-a-report"></a><span data-ttu-id="d35b6-107">Просмотр отчета</span><span class="sxs-lookup"><span data-stu-id="d35b6-107">To view a report</span></span>  
  
1.  <span data-ttu-id="d35b6-108">Нажмите кнопку **Пуск**, выберите пункт **все программы**, затем **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]** , а затем выберите \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] советник по переходу\*\*.</span><span class="sxs-lookup"><span data-stu-id="d35b6-108">Click **Start**, click **All Programs**, click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**, and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
2.  <span data-ttu-id="d35b6-109">На начальной странице советника по переходу щелкните **запустить средство просмотра отчетов помощника по обновлению**.</span><span class="sxs-lookup"><span data-stu-id="d35b6-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
3.  <span data-ttu-id="d35b6-110">Чтобы выбрать отчет в каталоге по умолчанию на данном компьютере, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d35b6-110">To select a report in the default location on your computer:</span></span>  
  
    1.  <span data-ttu-id="d35b6-111">В списке **сервер** выберите сервер.</span><span class="sxs-lookup"><span data-stu-id="d35b6-111">In the **Server** list, select a server.</span></span>  
  
    2.  <span data-ttu-id="d35b6-112">В списке **экземпляр или компонент** выберите сочетание компонента или компонента или экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d35b6-112">In the **Instance or component** list, select a component or component/instance combination.</span></span>  
  
     <span data-ttu-id="d35b6-113">Чтобы выбрать отчет в другом каталоге, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d35b6-113">To select a report at another location:</span></span>  
  
    1.  <span data-ttu-id="d35b6-114">Щелкните ссылку **открыть отчет** .</span><span class="sxs-lookup"><span data-stu-id="d35b6-114">Click the **Open Report** link.</span></span>  
  
    2.  <span data-ttu-id="d35b6-115">Перейдите в каталог, содержащий отчет, и дважды щелкните XML-файл.</span><span class="sxs-lookup"><span data-stu-id="d35b6-115">Browse to the report location and then double-click the XML file.</span></span>  
  
     <span data-ttu-id="d35b6-116">Помощник по обновлению сохраняет до пяти отчетов, сформированных по итогам предыдущих анализов.</span><span class="sxs-lookup"><span data-stu-id="d35b6-116">Upgrade Advisor stores up to five reports from previous analysis as history.</span></span> <span data-ttu-id="d35b6-117">Чтобы просмотреть эти отчеты, щелкните раскрывающийся список **отчет** и выберите отчет.</span><span class="sxs-lookup"><span data-stu-id="d35b6-117">To view these reports, click the **Report** drop-down list box, and select a report.</span></span> <span data-ttu-id="d35b6-118">Отчеты перечислены по меткам времени их создания.</span><span class="sxs-lookup"><span data-stu-id="d35b6-118">The reports are listed by the timestamp from when they were generated.</span></span>  
  
     <span data-ttu-id="d35b6-119">Отчет содержит следующие дополнительные сведения по всем обнаруженным проблемам.</span><span class="sxs-lookup"><span data-stu-id="d35b6-119">The report contains the following details for all detected issues:</span></span>  
  
    -   <span data-ttu-id="d35b6-120">**Важность**, которая указывает, насколько важно устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="d35b6-120">**Importance**, which indicates how important it is to fix the issue.</span></span>  
  
    -   <span data-ttu-id="d35b6-121">**Когда следует исправить**, это указывает, следует ли (или необходимо) исправить проблему до или после обновления до до [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] или после миграции приложения или данных или в любое время.</span><span class="sxs-lookup"><span data-stu-id="d35b6-121">**When to fix**, which indicates if you should (or must) fix the issue before or after upgrading to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], before or after migrating the application or data, or anytime.</span></span>  
  
    -   <span data-ttu-id="d35b6-122">Краткое описание проблемы.</span><span class="sxs-lookup"><span data-stu-id="d35b6-122">A brief description of the issue.</span></span>  
  
4.  <span data-ttu-id="d35b6-123">Если отчет содержит более 20 элементов, щелкните зеленую стрелку «вперед» в верхней или нижней части отчета, чтобы просмотреть следующий набор элементов.</span><span class="sxs-lookup"><span data-stu-id="d35b6-123">If the report contains more than 20 items, click the green forward arrow at the top or bottom of the report to view the next set of items.</span></span> <span data-ttu-id="d35b6-124">Щелкните зеленую стрелку «назад», чтобы просмотреть предыдущие 20 элементов.</span><span class="sxs-lookup"><span data-stu-id="d35b6-124">Click the green back button to view the previous 20 items.</span></span>  
  
5.  <span data-ttu-id="d35b6-125">Чтобы отсортировать отчет, щелкните заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="d35b6-125">To sort the report, click a column heading.</span></span>  
  
6.  <span data-ttu-id="d35b6-126">Чтобы просмотреть дополнительные сведения по конкретному элементу, щелкните этот элемент.</span><span class="sxs-lookup"><span data-stu-id="d35b6-126">To view details for a specific item, click the item.</span></span> <span data-ttu-id="d35b6-127">При этом появится описание проблемы и дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="d35b6-127">A description of the issue appears, along with additional options:</span></span>  
  
    -   <span data-ttu-id="d35b6-128">Чтобы просмотреть объекты, в которых обнаружена эта проблема, нажмите кнопку **Показать затронутые объекты**.</span><span class="sxs-lookup"><span data-stu-id="d35b6-128">To view the objects where this issue was found, click **Show affected objects**.</span></span>  
  
    -   <span data-ttu-id="d35b6-129">Чтобы просмотреть справку по этой неполадке, щелкните **Дополнительные сведения об этой неполадке и способах ее устранения**.</span><span class="sxs-lookup"><span data-stu-id="d35b6-129">To view help for the issue, click **Tell me more about this issue and how to resolve it**.</span></span>  
  
    -   <span data-ttu-id="d35b6-130">Чтобы отметить проблему как разрешенную, которая скрывает проблему при повторном просмотре отчета, выберите **эту проблему устранена**.</span><span class="sxs-lookup"><span data-stu-id="d35b6-130">To mark the issue as resolved, which hides the issue when you view the report again, select **This issue has been resolved**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d35b6-131">Отчет может содержать элементы, указывающие на необнаруживаемые проблемы.</span><span class="sxs-lookup"><span data-stu-id="d35b6-131">The report may contain an item for undetectable issues.</span></span> <span data-ttu-id="d35b6-132">Это проблемы, которые не могут быть обнаружены или формируют слишком много ложных положительных результатов.</span><span class="sxs-lookup"><span data-stu-id="d35b6-132">These are issues that cannot be detected or that would generate too many false-positive results.</span></span> <span data-ttu-id="d35b6-133">Щелкните **Дополнительные сведения об этой неполадке и разрешите ее** , чтобы просмотреть список необнаруживаемых проблем компонента.</span><span class="sxs-lookup"><span data-stu-id="d35b6-133">Click the **Tell me more about this issue and how to resolve it** link to see a list of undetectable issues for the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d35b6-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="d35b6-134">See Also</span></span>  
 <span data-ttu-id="d35b6-135">[Руководство. экспорт отчетов](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="d35b6-135">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="d35b6-136">[Как запустить мастер анализа помощника по обновлению](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="d35b6-136">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="d35b6-137">[Устранение проблем с обновлением](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="d35b6-137">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 <span data-ttu-id="d35b6-138">[Инструкции по советнику по переходу](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="d35b6-138">[Upgrade Advisor How-to Topics](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span></span>  
 [<span data-ttu-id="d35b6-139">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="d35b6-139">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
