---
title: Проверка запуска отчета | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- auditing [Reporting Services]
- verifying report execution
- logs [Reporting Services], verifying report run
- report execution data [Reporting Services]
- status information [Reporting Services]
- report processing [Reporting Services], verifying execution
- checking report execution
ms.assetid: 18a98f2f-6b40-454e-9b37-568ed1a96458
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c11c57f7c5f67b2557f5637ad10658abc9f80606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659328"
---
# <a name="verifying-a-report-run"></a><span data-ttu-id="5d682-102">Проверка запуска отчета</span><span class="sxs-lookup"><span data-stu-id="5d682-102">Verifying a Report Run</span></span>
  <span data-ttu-id="5d682-103">Чтобы просмотреть информацию о состоянии обработки отчета, можно использовать файлы журнала или просмотреть информацию о состоянии, отображаемую вместе с отчетом в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="5d682-103">To view information about the status of report processing, you can use log files or refer to status information that is displayed with the report in Report Manager.</span></span>  
  
## <a name="sources-of-report-execution-data"></a><span data-ttu-id="5d682-104">Источники данных выполнения отчета</span><span class="sxs-lookup"><span data-stu-id="5d682-104">Sources of Report Execution Data</span></span>  
 <span data-ttu-id="5d682-105">Журналы выполнения отчета обеспечивают всестороннюю информацию о выполнении отчета, включая имя отчета, имя пользователя, который выполнил отчет, время выполнения отчета и модуль доставки, используемый для распространения отчета.</span><span class="sxs-lookup"><span data-stu-id="5d682-105">The report execution logs provide comprehensive information about report execution, including the name of the report, the name of the user who ran the report, report execution time, and the delivery extension used to distribute the report.</span></span> <span data-ttu-id="5d682-106">Чтобы просматривать и анализировать эти данные, можно скопировать журнал выполнения отчета в таблицы базы данных, в которых легко делать запросы и на их основе создавать отчеты.</span><span class="sxs-lookup"><span data-stu-id="5d682-106">To view and analyze this data, you can copy the report execution log into database tables that are easy to query and report on.</span></span>  
  
 <span data-ttu-id="5d682-107">Файлы журнала содержат множество входных записей о выполнении отчета и о другой деятельности сервера.</span><span class="sxs-lookup"><span data-stu-id="5d682-107">Log files contain many entries about report execution and other server activity.</span></span> <span data-ttu-id="5d682-108">Поскольку файлы журнала содержат так много данных, можно использовать диспетчер отчетов, если хотите посмотреть только время последнего выполнения отчета.</span><span class="sxs-lookup"><span data-stu-id="5d682-108">Because log files contain so much data, you may want to use Report Manager if you only want to verify when the report last ran.</span></span> <span data-ttu-id="5d682-109">Если требуется дополнительная информация, следует просмотреть файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="5d682-109">If you require additional information, you must view the log files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d682-110">Диспетчер отчетов не показывает продолжительность обработки отчетов, которые были запущены по требованию.</span><span class="sxs-lookup"><span data-stu-id="5d682-110">Report Manager does not show the processing times of reports that run on demand.</span></span>  
  
 <span data-ttu-id="5d682-111">Следующая таблица описывает, как просмотреть дату и время обработки различных типов отчетов.</span><span class="sxs-lookup"><span data-stu-id="5d682-111">The following table describes how to view the processing date and time for various types of reports.</span></span>  
  
|<span data-ttu-id="5d682-112">Для отчета этого типа</span><span class="sxs-lookup"><span data-stu-id="5d682-112">For this type of report</span></span>|<span data-ttu-id="5d682-113">Местонахождение сведений о дате и времени</span><span class="sxs-lookup"><span data-stu-id="5d682-113">Date and time information is located here</span></span>|<span data-ttu-id="5d682-114">Для просмотра информации сделайте следующее</span><span class="sxs-lookup"><span data-stu-id="5d682-114">To view the information, do the following</span></span>|  
|-----------------------------|-----------------------------------------------|-----------------------------------------------|  
|<span data-ttu-id="5d682-115">Отчет, который выполняется как моментальный снимок отчета.</span><span class="sxs-lookup"><span data-stu-id="5d682-115">A report that runs as a report snapshot.</span></span>|<span data-ttu-id="5d682-116">На странице «Содержание».</span><span class="sxs-lookup"><span data-stu-id="5d682-116">On the Contents page.</span></span> <span data-ttu-id="5d682-117">Дополнительные сведения см. в разделе [Страница "Содержимое" (диспетчер отчетов)](../contents-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5d682-117">For more information, see [Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md).</span></span>|<span data-ttu-id="5d682-118">1. Определите расположение папки, которая содержит отчет.</span><span class="sxs-lookup"><span data-stu-id="5d682-118">1) Locate the folder that contains the report.</span></span><br /><span data-ttu-id="5d682-119">2. Укажите папку в представлении "Подробности".</span><span class="sxs-lookup"><span data-stu-id="5d682-119">2) Set the folder in Details view.</span></span><br /><span data-ttu-id="5d682-120">3) 3) Обратите внимание на дату и время в столбце **время выполнения** .</span><span class="sxs-lookup"><span data-stu-id="5d682-120">3) 3) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="5d682-121">Моментальный снимок журнала отчета.</span><span class="sxs-lookup"><span data-stu-id="5d682-121">A snapshot in report history.</span></span>|<span data-ttu-id="5d682-122">На странице «Свойства журнала».</span><span class="sxs-lookup"><span data-stu-id="5d682-122">On the History Properties page.</span></span> <span data-ttu-id="5d682-123">Дополнительные сведения см. в разделе [Страница "Свойства параметров моментального снимка" (диспетчер отчетов)](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5d682-123">For more information, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>|<span data-ttu-id="5d682-124">1. Откройте отчет.</span><span class="sxs-lookup"><span data-stu-id="5d682-124">1) Open the report.</span></span><br /><span data-ttu-id="5d682-125">2. Перейдите на страницу **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="5d682-125">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="5d682-126">3. Перейдите на вкладку **Журнал** .</span><span class="sxs-lookup"><span data-stu-id="5d682-126">3) Click the **History** tab.</span></span><br /><span data-ttu-id="5d682-127">4. Обратите внимание на дату и время в столбце **Время запуска** .</span><span class="sxs-lookup"><span data-stu-id="5d682-127">4) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="5d682-128">Кэшируемый отчет.</span><span class="sxs-lookup"><span data-stu-id="5d682-128">A cached report.</span></span>|<span data-ttu-id="5d682-129">В расписании, используемом для создания и обновления кэшируемого отчета.</span><span class="sxs-lookup"><span data-stu-id="5d682-129">In the schedule used to create and refresh the cached report.</span></span>|<span data-ttu-id="5d682-130">1. Откройте отчет.</span><span class="sxs-lookup"><span data-stu-id="5d682-130">1) Open the report.</span></span><br /><span data-ttu-id="5d682-131">2. Перейдите на страницу **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="5d682-131">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="5d682-132">3. Перейдите на вкладку **Выполнение** .</span><span class="sxs-lookup"><span data-stu-id="5d682-132">3) Click the **Execution** tab.</span></span><br /><span data-ttu-id="5d682-133">4. Откройте расписание.</span><span class="sxs-lookup"><span data-stu-id="5d682-133">4) Open the schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d682-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d682-134">See Also</span></span>  
 <span data-ttu-id="5d682-135">[Файлы и источники журналов служб Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="5d682-135">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="5d682-136">[Установка свойств обработки отчетов](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="5d682-136">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="5d682-137">Диспетчер отчетов (службы SSRS в собственном режиме)</span><span class="sxs-lookup"><span data-stu-id="5d682-137">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
