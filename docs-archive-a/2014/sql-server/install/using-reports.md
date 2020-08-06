---
title: Использование отчетов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- overriding reports
- Upgrade Advisor Report Viewer
- reports [Upgrade Advisor], about reports
- formatting reports
- resolved issues [Upgrade Advisor]
- distributing reports [Reporting Services]
- filtering reports [Reporting Services]
- removing report items
- viewing reports
- rerunning analysis
- information issues [Upgrade Advisor]
- deleting report items
- icons [Upgrade Advisor]
- Upgrade Advisor [SQL Server], reports
- sending reports
- blocking issues [Upgrade Advisor]
- sharing reports
- reports [Upgrade Advisor]
- SQL Server Upgrade Advisor, reports
- modifying reports
- distributing reports [Reporting Services], about report distribution
- warnings [Upgrade Advisor]
- analyzing system [Upgrade Advisor], reports
ms.assetid: 4a3cb94a-a7ac-4cec-94c7-db26fcf6d161
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f52afcfdaa7de33d83d64a049f9a350f0463b4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751655"
---
# <a name="using-reports"></a><span data-ttu-id="2aa6c-102">Использование отчетов</span><span class="sxs-lookup"><span data-stu-id="2aa6c-102">Using Reports</span></span>
  <span data-ttu-id="2aa6c-103">Для каждого компонента и, если необходимо, для каждого экземпляра, проанализированного мастером анализа помощника по обновлению на сервере, создается свой отчет.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-103">A separate report is generated for each component, and, where necessary, each instance, that the Upgrade Advisor Analysis Wizard analyzes on a server.</span></span> <span data-ttu-id="2aa6c-104">В отчете содержатся сведения об известных проблемах, влияющих на обновление.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-104">The report provides details about known issues that affect an upgrade.</span></span> <span data-ttu-id="2aa6c-105">В отчете содержатся также ссылки на сведения и предлагаются действия по решению выявленных проблем.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-105">It also provides links to information and suggested actions for addressing the identified issues.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2aa6c-106">Если средство просмотра отчетов советника по переходу не обнаруживает отчеты в каталоге Reports по умолчанию, можно загрузить отчет из другого каталога, используя ссылку **открыть отчет** .</span><span class="sxs-lookup"><span data-stu-id="2aa6c-106">If the Upgrade Advisor Report Viewer does not find any reports in the default reports directory, you can load a report from a different directory by using the **Open Report** link.</span></span>  
  
## <a name="viewing-reports"></a><span data-ttu-id="2aa6c-107">Просмотр отчетов</span><span class="sxs-lookup"><span data-stu-id="2aa6c-107">Viewing Reports</span></span>  
 <span data-ttu-id="2aa6c-108">Средство просмотра отчетов помощника по обновлению используется для просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-108">You use the Upgrade Advisor Report Viewer to view Upgrade Advisor reports.</span></span> <span data-ttu-id="2aa6c-109">Чтобы просмотреть отчеты, на начальной странице советника по переходу щелкните **запустить средство просмотра отчетов советника по переходу**.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-109">To view reports, on the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
 <span data-ttu-id="2aa6c-110">После загрузки отчета для сервера можно выбрать компонент, для которого необходимо просмотреть проблемы обновления.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-110">After you load a report for a server, you can select a component for which you want to see upgrade issues.</span></span> <span data-ttu-id="2aa6c-111">Фильтр можно применить в поле **Фильтровать по,** чтобы увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="2aa6c-111">You can apply a filter from the **Filter By** box to see the following:</span></span>  
  
-   <span data-ttu-id="2aa6c-112">все проблемы;</span><span class="sxs-lookup"><span data-stu-id="2aa6c-112">All issues</span></span>  
  
-   <span data-ttu-id="2aa6c-113">все проблемы, связанные с обновлением;</span><span class="sxs-lookup"><span data-stu-id="2aa6c-113">All upgrade issues</span></span>  
  
-   <span data-ttu-id="2aa6c-114">проблемы, связанные с подготовкой к обновлению;</span><span class="sxs-lookup"><span data-stu-id="2aa6c-114">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="2aa6c-115">все проблемы, связанные с миграцией;</span><span class="sxs-lookup"><span data-stu-id="2aa6c-115">All migration issues</span></span>  
  
-   <span data-ttu-id="2aa6c-116">устраненные проблемы.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-116">Resolved issues</span></span>  
  
-   <span data-ttu-id="2aa6c-117">Неустраненные проблемы</span><span class="sxs-lookup"><span data-stu-id="2aa6c-117">Unresolved issues</span></span>  
  
 <span data-ttu-id="2aa6c-118">Если отчет содержит более 20 проблем, можно перейти к следующей или предыдущей группе проблем, нажав кнопку **Далее 20** или **выше 20** в верхней или нижней части списка проблем.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-118">If your report has more than 20 issues, you can move to the next or previous group of issues by clicking **Next 20** or **Previous 20** at the top or bottom of the issues list.</span></span>  
  
 <span data-ttu-id="2aa6c-119">Можно просмотреть до пяти сохраненных отчетов, выбрав отчеты из раскрывающегося списка **отчет** .</span><span class="sxs-lookup"><span data-stu-id="2aa6c-119">You can view up to five saved reports by selecting the reports from the **Report** drop-down list box.</span></span> <span data-ttu-id="2aa6c-120">Отчеты перечислены по меткам времени их создания.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-120">The reports are listed by the timestamp from when they were generated.</span></span>  
  
## <a name="report-format"></a><span data-ttu-id="2aa6c-121">Формат отчета</span><span class="sxs-lookup"><span data-stu-id="2aa6c-121">Report Format</span></span>  
 <span data-ttu-id="2aa6c-122">Средство просмотра отчетов выводит информацию о проблемах в три столбца.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-122">The report viewer displays report issues in three columns.</span></span> <span data-ttu-id="2aa6c-123">Каждую проблему можно свернуть, спрятав ее описание и оставив только основную информацию.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-123">Each issue is collapsible so that you can hide the description and view only the key information.</span></span>  
  
 <span data-ttu-id="2aa6c-124">Первый столбец является столбцом **важности** .</span><span class="sxs-lookup"><span data-stu-id="2aa6c-124">The first column is the **Importance** column.</span></span> <span data-ttu-id="2aa6c-125">Значками показана важность каждой проблемы: красный круг с символом Х — для блокирующих, или важных проблем; желтый треугольник с восклицательным знаком — для предупреждений и информационных сообщений.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-125">Icons indicate the importance for each issue by displaying either a red circle with an X for blocking or important issues or a yellow triangle with an exclamation mark for Warning and Information issues.</span></span> <span data-ttu-id="2aa6c-126">Во втором столбце, **когда следует исправить**, указывается, когда необходимо устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-126">The second column, **When to fix**, indicates when you must resolve the issue.</span></span> <span data-ttu-id="2aa6c-127">Отчет можно отсортировать по **важности** или **при исправлении** столбца.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-127">You can sort the report on either the **Importance** or **When to fix** column.</span></span> <span data-ttu-id="2aa6c-128">Третий столбец, **Описание**, содержит название проблемы.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-128">The third column, **Description**, lists the title of the issue.</span></span>  
  
 <span data-ttu-id="2aa6c-129">Проблему можно развернуть, чтобы вывести дополнительную информацию, ссылку на дополнительную информацию о решении проблемы и ссылку на подробные данные о проблеме.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-129">You can expand an issue to display additional information, a link to detailed information about resolving the issue, and a link to show issue details.</span></span> <span data-ttu-id="2aa6c-130">Если щелкнуть ссылку на подробные сведения о проблеме, откроется раздел справки с описанием проблемы и инструкциями по ее устранению.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-130">When you click the link to get detailed information for the issue, a Help topic with information about the issue and instructions for addressing the issue is displayed.</span></span> <span data-ttu-id="2aa6c-131">После устранения проблемы или управления элементами действий можно пометить проблемы как завершенные, установив флажок **проблема устранена** .</span><span class="sxs-lookup"><span data-stu-id="2aa6c-131">After you have fixed an issue, or to manage your action items, you can mark issues as complete by selecting the **This issue has been resolved** check box.</span></span> <span data-ttu-id="2aa6c-132">Если вы хотите удалить разрешенные проблемы из списка проблем с обновлением, нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-132">If you want to remove the resolved issues from the list of upgrade issues, click **Refresh**.</span></span> <span data-ttu-id="2aa6c-133">Эта проблема не отображается снова, пока мастер анализа советника по переходу не будет запущен на том же компоненте или не примените фильтр **разрешенных проблем** из параметра **Фильтровать по** .</span><span class="sxs-lookup"><span data-stu-id="2aa6c-133">The issue is not displayed again until you either run the Upgrade Advisor Analysis Wizard against the same component or apply the **Resolved Issues** filter from the **Filter By** option.</span></span>  
  
## <a name="report-files"></a><span data-ttu-id="2aa6c-134">Файлы отчетов</span><span class="sxs-lookup"><span data-stu-id="2aa6c-134">Report Files</span></span>  
 <span data-ttu-id="2aa6c-135">Мастер анализа помощника по обновлению создает отчеты в каталоге обновления "Мои документы" \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Advisor\110\Reports и создает подкаталог для каждого анализируемого сервера.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-135">The Upgrade Advisor Analysis Wizard creates reports in the My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports directory and creates a subdirectory for each server that you analyze.</span></span> <span data-ttu-id="2aa6c-136">Файлы отчетов — это XML-файлы, использующие определенное соглашение об именах.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-136">The report files are XML files that follow a specific naming convention.</span></span> <span data-ttu-id="2aa6c-137">При запуске средства просмотра отчетов помощника по обновлению выводятся файлы отчетов, расположенные в каталоге по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-137">When you launch the Upgrade Advisor Report Viewer, the report files in the default directory are displayed.</span></span> <span data-ttu-id="2aa6c-138">При копировании файлов отчетов в этот каталог необходимо убедиться, что для них выполняется соглашение об именах, иначе средство просмотра отчетов не сможет их автоматически отобразить.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-138">If you copy report files into this folder, they must adhere to the naming convention or the report viewer will not display them automatically.</span></span>  
  
 <span data-ttu-id="2aa6c-139">Если нужно передавать информацию другим лицам, можно отправить им отчет в формате XML.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-139">If you want to share the information with other people, you can send them the XML report.</span></span> <span data-ttu-id="2aa6c-140">Или, если необходимо использовать другое приложение, можно экспортировать отчет в файл значений с разделителями-запятыми, который можно использовать, чтобы создать электронную таблицу, текстовый файл или сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="2aa6c-140">Or, if you want to use another application, you can export the report into a comma-separated value file that you can use to create a spreadsheet, text file, or e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa6c-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="2aa6c-141">See Also</span></span>  
 <span data-ttu-id="2aa6c-142">[Руководство. Просмотр отчета советника по переходу](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span><span class="sxs-lookup"><span data-stu-id="2aa6c-142">[How to: View an Upgrade Advisor Report](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span></span>  
 <span data-ttu-id="2aa6c-143">[Руководство. экспорт отчетов](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="2aa6c-143">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="2aa6c-144">[Как фильтровать отчеты](../../../2014/sql-server/install/how-to-filter-reports.md) </span><span class="sxs-lookup"><span data-stu-id="2aa6c-144">[How to: Filter Reports](../../../2014/sql-server/install/how-to-filter-reports.md) </span></span>  
 <span data-ttu-id="2aa6c-145">[Устранение проблем с обновлением](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2aa6c-145">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2aa6c-146">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="2aa6c-146">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
