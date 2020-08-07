---
title: Производительность, моментальные снимки, кэширование (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- performance [Reporting Services]
- Reporting Services, performance
ms.assetid: 85afd00f-e8d7-4ef7-9174-2ff84d82f960
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f171586e136b36bd694fa40b15272f62e1cb1378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732410"
---
# <a name="performance-snapshots-caching-reporting-services"></a><span data-ttu-id="473b7-102">Производительность, моментальные снимки, кэширование (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="473b7-102">Performance, Snapshots, Caching (Reporting Services)</span></span>
  <span data-ttu-id="473b7-103">Производительность сервера отчетов зависит от сочетания факторов, которые включают оборудование, количество пользователей, одновременно обращающихся к отчетам, объем данных в отчетах и формат вывода.</span><span class="sxs-lookup"><span data-stu-id="473b7-103">Report server performance is affected by a combination of factors that include hardware, number of concurrent users accessing reports, the amount of data in a report, and output format.</span></span> <span data-ttu-id="473b7-104">Чтобы понять, какие факторы производительности характерны для конкретной установки, и какие меры позволят достичь требуемых результатов, необходимо получить базовые данные и выполнить тесты.</span><span class="sxs-lookup"><span data-stu-id="473b7-104">To understand the performance factors that are specific to your installation and which remedies will produce the results you want, you will need to get baseline data and run tests.</span></span> <span data-ttu-id="473b7-105">Дополнительные сведения о средствах и рекомендациях см. в следующих публикациях MSDN: [Reporting Services Performance Optimization](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) (Оптимизация производительности служб Reporting Services) и [Using Visual Studio 2005 to Perform Load Testing on a SQL Server 2005 Reporting Services Report Server](https://go.microsoft.com/fwlink/?LinkID=77519)(Нагрузочное тестирование сервера отчетов служб Reporting Services SQL Server 2005 в среде Visual Studio 2005).</span><span class="sxs-lookup"><span data-stu-id="473b7-105">For more information about tools and guidelines, see the following publications on MSDN: [Reporting Services Performance Optimization](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) and [Using Visual Studio 2005 to Perform Load Testing on a SQL Server 2005 Reporting Services Report Server](https://go.microsoft.com/fwlink/?LinkID=77519).</span></span>  
  
 <span data-ttu-id="473b7-106">Общие принципы, которыми необходимо руководствоваться, включают следующее.</span><span class="sxs-lookup"><span data-stu-id="473b7-106">General principles to consider include the following:</span></span>  
  
-   <span data-ttu-id="473b7-107">Операции обработки и подготовки к просмотру отчетов требуют много памяти.</span><span class="sxs-lookup"><span data-stu-id="473b7-107">Report processing and rendering are memory intensive operations.</span></span> <span data-ttu-id="473b7-108">По возможности выбирайте компьютер со значительным объемом памяти.</span><span class="sxs-lookup"><span data-stu-id="473b7-108">When possible, choose a computer that has a lot of memory.</span></span>  
  
-   <span data-ttu-id="473b7-109">Размещение сервера отчетов и базы данных сервера отчетов на отдельных компьютерах, как правило, позволяет достичь более высокой производительности по сравнению с тем вариантом, когда они размещаются на одном компьютере, пусть даже высокого класса.</span><span class="sxs-lookup"><span data-stu-id="473b7-109">Hosting the report server and the report server database on separate computers tends to provide better performance than hosting both on a single high-end computer.</span></span>  
  
-   <span data-ttu-id="473b7-110">Если все отчеты обрабатываются медленно, рассмотрите возможность масштабного развертывания, в котором несколько экземпляров сервера отчетов поддерживают единственную базу данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="473b7-110">If all reports are processing slowly, consider a scale-out deployment where multiple report server instances support a single report server database.</span></span> <span data-ttu-id="473b7-111">Для достижения наилучших результатов используйте подсистему балансировки загрузки, чтобы равномерно распределить запросы по всему развертыванию.</span><span class="sxs-lookup"><span data-stu-id="473b7-111">For best results, use load balancing software to distribute requests evenly across the deployment.</span></span>  
  
-   <span data-ttu-id="473b7-112">Если единственный отчет обрабатывается медленно, то необходимо настроить запросы набора данных отчета, если этот отчет должен выполняться по запросу.</span><span class="sxs-lookup"><span data-stu-id="473b7-112">If a single report is processing slowly, tune report dataset queries if the report must run on demand.</span></span> <span data-ttu-id="473b7-113">Можно также рассмотреть возможность использования общих наборов данных, которые можно кэшировать, кэшируя отчет или запуская отчет в качестве моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="473b7-113">You might also consider using shared datasets that you can cache, caching the report, or running the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="473b7-114">Если медленно обрабатываются все отчеты в конкретном формате (например, на этапе подготовки к просмотру в формате PDF), рассмотрите возможность доставки в общую папку, добавления большего объема памяти или выбора другого формата.</span><span class="sxs-lookup"><span data-stu-id="473b7-114">If all reports process slowly in a specific format (for example, while rendering to PDF), consider file share delivery, adding more memory, or choosing a different format.</span></span>  
  
-   <span data-ttu-id="473b7-115">Чтобы узнать, сколько времени занимает обработка отчета, и ознакомиться с другими показателями производительности, просмотрите журнал выполнения сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="473b7-115">To find out how long it takes to process a report and other usage metrics, review the report server execution log.</span></span> <span data-ttu-id="473b7-116">Дополнительные сведения см. [в разделе Журнал выполнения сервера отчетов и представление ExecutionLog3](report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="473b7-116">For more information, see [Report Server Execution Log and the ExecutionLog3 View](report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
-   <span data-ttu-id="473b7-117">Дополнительные сведения о снижении остроты проблем производительности путем настройки конфигурации управления памятью см. в разделе [Настройка доступной памяти для приложений сервера отчетов](../report-server/configure-available-memory-for-report-server-applications.md).</span><span class="sxs-lookup"><span data-stu-id="473b7-117">For more information about how to mitigate performance issues by tuning memory management configuration settings, see [Configure Available Memory for Report Server Applications](../report-server/configure-available-memory-for-report-server-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="473b7-118">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="473b7-118">In This Section</span></span>  
 [<span data-ttu-id="473b7-119">Мониторинг производительности сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="473b7-119">Monitoring Report Server Performance</span></span>](monitoring-report-server-performance.md)  
 <span data-ttu-id="473b7-120">Описывает объекты производительности, которые можно использовать для слежения за рабочей нагрузкой сервера.</span><span class="sxs-lookup"><span data-stu-id="473b7-120">Describes the performance objects you can use to track the processing load on your server.</span></span>  
  
 [<span data-ttu-id="473b7-121">Определение свойств обработки отчетов</span><span class="sxs-lookup"><span data-stu-id="473b7-121">Set Report Processing Properties</span></span>](set-report-processing-properties.md)  
 <span data-ttu-id="473b7-122">Описывает способы настройки отчета для запуска по запросу, из кэша или по расписанию в качестве моментального снимка отчета.</span><span class="sxs-lookup"><span data-stu-id="473b7-122">Describes ways of configuring a report to run on demand, from cache, or on a schedule as a report snapshot.</span></span>  
  
 [<span data-ttu-id="473b7-123">Настройка доступной памяти для приложений сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="473b7-123">Configure Available Memory for Report Server Applications</span></span>](../report-server/configure-available-memory-for-report-server-applications.md)  
 <span data-ttu-id="473b7-124">Рассматривается переопределение поведения управления памятью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="473b7-124">Describes how you can override default memory management behavior.</span></span>  
  
 [<span data-ttu-id="473b7-125">Кэширование отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="473b7-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
 <span data-ttu-id="473b7-126">Описывает поведение кэширования отчета на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="473b7-126">Describes report caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="473b7-127">Общие наборы данных в кэше (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="473b7-127">Cache Shared Datasets &#40;SSRS&#41;</span></span>](cache-shared-datasets-ssrs.md)  
 <span data-ttu-id="473b7-128">Описывает работу кэширования общего набора данных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="473b7-128">Describes shared dataset caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="473b7-129">Обработка больших отчетов</span><span class="sxs-lookup"><span data-stu-id="473b7-129">Process Large Reports</span></span>](process-large-reports.md)  
 <span data-ttu-id="473b7-130">Содержит рекомендации о настройке и распределении большого отчета.</span><span class="sxs-lookup"><span data-stu-id="473b7-130">Provides recommendations on how to configure and distribute a large report.</span></span>  
  
 [<span data-ttu-id="473b7-131">Задание значений времени ожидания при обработке отчетов и общих наборов данных (SSRS)</span><span class="sxs-lookup"><span data-stu-id="473b7-131">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
 <span data-ttu-id="473b7-132">Объясняет, как устанавливаются истечения времени ожидания при обработке запросов и отчетов.</span><span class="sxs-lookup"><span data-stu-id="473b7-132">Explains how to set time outs on query and report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="473b7-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="473b7-133">See Also</span></span>  
 <span data-ttu-id="473b7-134">[Управление запущенным процессом](../subscriptions/manage-a-running-process.md) </span><span class="sxs-lookup"><span data-stu-id="473b7-134">[Manage a Running Process](../subscriptions/manage-a-running-process.md) </span></span>  
 [<span data-ttu-id="473b7-135">Проверка запуска отчета</span><span class="sxs-lookup"><span data-stu-id="473b7-135">Verifying a Report Run</span></span>](verifying-a-report-run.md)  
  
  
