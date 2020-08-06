---
title: Настройка свойств выполнения для отчета (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- reports [Reporting Services], properties
- reports [Reporting Services], execution options
ms.assetid: 73cc8dcc-ef80-40d7-9739-d33bba0eb28a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51cd7b5db225b39f5a061ed750b2ef5cdd265b9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669273"
---
# <a name="configure-execution-properties-for-a-report--report-manager"></a><span data-ttu-id="e8e0f-102">Настройка свойств выполнения для отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="e8e0f-102">Configure Execution Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="e8e0f-103">Параметры обработки отчета можно настроить для указания получения данных для отчета.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-103">You can set report processing options to specify when data is retrieved for a report.</span></span> <span data-ttu-id="e8e0f-104">Планирование обработки данных для отчета становится целесообразным, если обновление внешнего источника данных происходит в определенные моменты времени (пример: хранилище данных, которое обновляется ежедневно или еженедельно) и необходимо избежать издержек, связанных с выборкой одних и тех же данных при каждом запросе отчета.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-104">It is useful to schedule data processing for a report if the external data source is refreshed at specific times (for example, a data warehouse that is refreshed daily or weekly) and you want to avoid the overhead of retrieving the same data each time a report is requested.</span></span> <span data-ttu-id="e8e0f-105">Планирование обработки данных становится также необходимым, если требуется управлять рабочей нагрузкой сервера внешней базы данных или обеспечить предоставление согласованных результатов для многочисленных пользователей, которым приходится работать с идентичными наборами данных.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-105">Scheduling data processing is also useful if you want to control the processing load on the external database server or when you want to provide consistent results for multiple users who must work with identical sets of data.</span></span> <span data-ttu-id="e8e0f-106">Для быстро изменяющихся данных отчеты по требованию могут каждую минуту выдавать различные результаты.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-106">With volatile data, an on-demand report can produce different results from one minute to the next.</span></span> <span data-ttu-id="e8e0f-107">Моментальный снимок отчета, напротив, позволяет сопоставить данные различных отчетов и средств аналитики, действительные на один и тот же момент времени.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-107">A report snapshot, by contrast, allows you to make valid comparisons against other reports or analytical tools that contain data from the same point in time.</span></span>  
  
 <span data-ttu-id="e8e0f-108">Моментальный снимок отчета — это отчет, содержащий инструкции макета и результаты запроса, полученные в определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-108">A report snapshot is a report that contains layout instructions and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="e8e0f-109">В отличие от отчетов по требованию, при открытии которых производится получение актуальных, действительных на текущий момент данных, моментальные снимки отчета выполняются по расписанию и сохраняются на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-109">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="e8e0f-110">Если для просмотра выбирается моментальный снимок отчета, сервер отчетов извлекает сохраненный отчет из базы данных сервера отчетов и отображает макет и данные, которые были действительны на момент создания моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-110">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
 <span data-ttu-id="e8e0f-111">Моментальные снимки отчета не сохраняются в каком-то определенном формате отображения,</span><span class="sxs-lookup"><span data-stu-id="e8e0f-111">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="e8e0f-112">а преобразуются в него (например, в HTML) только при запросе пользователя или приложения.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-112">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="e8e0f-113">Отложенное форматирование делает моментальные снимки отчетов переносимыми,</span><span class="sxs-lookup"><span data-stu-id="e8e0f-113">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="e8e0f-114">поскольку отчет может быть сформирован для просмотра в формате, необходимом для веб-браузера или другого устройства отображения.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-114">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
### <a name="to-configure-report-processing-options"></a><span data-ttu-id="e8e0f-115">Настройка параметров обработки отчета</span><span class="sxs-lookup"><span data-stu-id="e8e0f-115">To configure report processing options</span></span>  
  
1.  <span data-ttu-id="e8e0f-116">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e8e0f-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="e8e0f-117">Перейдите и откройте отчет, для которого необходимо настроить параметры обработки.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-117">Navigate to and open the report for which you want to set processing options.</span></span>  
  
 <span data-ttu-id="e8e0f-118">Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
1.  <span data-ttu-id="e8e0f-119">В раскрывающемся меню выберите **Управление** , а затем вкладку **Параметры обработки** .</span><span class="sxs-lookup"><span data-stu-id="e8e0f-119">In the drop-down menu, click **Manage** and then select the **Processing Options** tab.</span></span>  
  
2.  <span data-ttu-id="e8e0f-120">Щелкните **Подготовить этот отчет для просмотра, используя снимок состояния выполнения отчета**, а затем выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-120">Click **Render this report from an execution snapshot, and then select one of the following options:**</span></span>  
  
    -   <span data-ttu-id="e8e0f-121">Если необходимо создать моментальный снимок, выберите **Использовать следующее расписание создания снимков состояния выполнения отчета**и либо определите расписание для отчета, либо выберите расписание из списка **Общее расписание** .</span><span class="sxs-lookup"><span data-stu-id="e8e0f-121">If you want to create a snapshot, select **Use the following schedule to create report execution snapshots**, and then either define a report-specific schedule or select from the **Shared schedule** list.</span></span>  
  
    -   <span data-ttu-id="e8e0f-122">Если нужно создать моментальный снимок немедленно, выберите **Создать моментальный снимок отчета при нажатии кнопки «Применить» на этой странице**.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-122">If you want to create a snapshot immediately, select **Create a report snapshot when you click the Apply button on this page**.</span></span>  
  
3.  <span data-ttu-id="e8e0f-123">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="e8e0f-123">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e0f-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8e0f-124">See Also</span></span>  
 <span data-ttu-id="e8e0f-125">[Установка свойств обработки отчета](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e8e0f-125">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="e8e0f-126">[Открытие и закрытие диспетчер отчетов &#40;отчетов&#41;](../reports/open-and-close-a-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e8e0f-126">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) </span></span>  
 <span data-ttu-id="e8e0f-127">[Страница "Содержимое" (диспетчер отчетов)](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e8e0f-127">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="e8e0f-128">[Управление содержимым сервера отчетов (службы Reporting Services в основном режиме)](../report-server/report-server-content-management-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="e8e0f-128">[Report Server Content Management &#40;SSRS Native Mode&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="e8e0f-129">Страница "Свойства параметров обработки" (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="e8e0f-129">Processing Options Properties Page &#40;Report Manager&#41;</span></span>](../processing-options-properties-page-report-manager.md)  
  
  
