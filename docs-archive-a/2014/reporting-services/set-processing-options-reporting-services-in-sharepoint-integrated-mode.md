---
title: Настройка параметров обработки (Reporting Services в режиме интеграции с SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], content management
- snapshots [Reporting Services], creating
ms.assetid: 453b19a1-739a-4b67-aeea-2069b52204e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8c33b205a702d4ab77abf74154232990da9840b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732386"
---
# <a name="set-processing-options-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="c3ab8-102">установить параметры обработки (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c3ab8-102">Set Processing Options (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="c3ab8-103">Можно установить параметры обработки для отчета [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , определяющие время обработки данных.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-103">You can set processing options on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report to determine when data processing occurs.</span></span> <span data-ttu-id="c3ab8-104">Также при обработке отчета можно определить интервал ожидания и задать параметры, определяющие порядок создания журнала отчета для текущего отчета.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-104">You can also set a time-out value for report processing, and options that determine whether report history is enabled for the current report.</span></span>  
  
-   <span data-ttu-id="c3ab8-105">Отчет можно выполнять как моментальный снимок отчета, чтобы предотвратить его выполнение в произвольные моменты времени (например, во время резервного копирования по расписанию).</span><span class="sxs-lookup"><span data-stu-id="c3ab8-105">You can run a report as a report snapshot to prevent the report from being run at arbitrary times (for example, during a scheduled backup).</span></span> <span data-ttu-id="c3ab8-106">Обычно моментальный снимок отчета создается и в дальнейшем обновляется по расписанию, что позволяет точно планировать время, когда будет выполняться обработка отчета и данных.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-106">A report snapshot is usually created and subsequently refreshed on a schedule, allowing you to time exactly when report and data processing will occur.</span></span> <span data-ttu-id="c3ab8-107">Если отчет основан на запросах, требующих длительного выполнения, или на запросах, использующих данные из источника данных, доступ к которому в определенные часы желательно запретить, отчет следует выполнять как моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-107">If a report is based on queries that take a long time to run, or on queries that use data from a data source that you prefer no one access during certain hours, you should run the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="c3ab8-108">Сервер отчетов может кэшировать копию обработанного отчета и вернуть эту копию при открытии отчета пользователем.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-108">A report server can cache a copy of a processed report and return that copy when a user opens the report.</span></span> <span data-ttu-id="c3ab8-109">Кэширование — технология улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-109">Caching is a performance-enhancement technique.</span></span> <span data-ttu-id="c3ab8-110">Кэширование может сократить время, необходимое для поиска отчета, если отчет большого размера или к нему часто обращаются.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-110">Caching can shorten the time required to retrieve a report if the report is large or accessed frequently.</span></span>  
  
-   <span data-ttu-id="c3ab8-111">Журнал отчета — это коллекция ранее созданных копий отчета.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-111">Report history is a collection of previously run copies of a report.</span></span> <span data-ttu-id="c3ab8-112">Журнал отчетов можно использовать для отслеживания отчета во времени.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-112">You can use report history to maintain a record of a report over time.</span></span> <span data-ttu-id="c3ab8-113">Журнал отчета не используется для отчетов, содержащих конфиденциальные или личные данные.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-113">Report history is not intended for reports that contain confidential or personal data.</span></span> <span data-ttu-id="c3ab8-114">По этой причине журнал отчета может охватывать только те отчеты, которые обращаются к источнику данных с помощью только одного набора учетных данных (сохраненных учетных данных или учетных данных, используемых для автоматического выполнения отчета), доступного для всех пользователей, выполняющих отчет.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-114">For this reason, report history can include only those reports that query a data source using a single set of credentials (either stored credentials or credentials used for unattended report execution) that are available to all users who run a report.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="c3ab8-115">в режиме интеграции с SharePoint используют функции управления содержимым SharePoint (извлечение и возврат) для сохранения обновлений в типы содержимого служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3ab8-115">integration with SharePoint uses the check out and check in content management features of SharePoint to save updates to [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="c3ab8-116">Это включает создание моментальных снимков отчетов.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-116">This includes the creation of report snapshots.</span></span> <span data-ttu-id="c3ab8-117">Поэтому, если включено управление версиями в библиотеке документов, то при создании нового моментального снимка журнала отчета версия отчета будет обновлена.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-117">Therefore if you have enabled versioning on a document library, you will see the report version updated when a new report history snapshot is created.</span></span> <span data-ttu-id="c3ab8-118">Это является побочным результатом обновления моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-118">This is a side-effect of updating snapshots.</span></span> <span data-ttu-id="c3ab8-119">Обновление моментального снимка приводит к изменению свойства LastExecution, что вызывает изменение версии отчета.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-119">When a snapshot is updated it causes the LastExecution property of the report to change and that will cause a change in the version of the report.</span></span>  
  
-   <span data-ttu-id="c3ab8-120">Можно указать значения времени ожидания, чтобы ограничить использование системных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-120">You can specify time-out values to set limits on how system resources are used.</span></span>  
  
||  
|-|  
|<span data-ttu-id="c3ab8-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Режим интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="c3ab8-121">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|  
  
 <span data-ttu-id="c3ab8-122">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="c3ab8-122">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="c3ab8-123">Задание параметров обновления данных</span><span class="sxs-lookup"><span data-stu-id="c3ab8-123">To set data refresh options</span></span>](#bkmk_set_data_refresh)  
  
-   [<span data-ttu-id="c3ab8-124">Задание параметров кэширования отчета</span><span class="sxs-lookup"><span data-stu-id="c3ab8-124">To set report caching options</span></span>](#bkmk_set_report_caching)  
  
-   [<span data-ttu-id="c3ab8-125">Обработка значений времени ожидания</span><span class="sxs-lookup"><span data-stu-id="c3ab8-125">To set processing time-out values</span></span>](#bkmk_set_processing)  
  
-   [<span data-ttu-id="c3ab8-126">Настройка параметров и ограничений журнала отчета</span><span class="sxs-lookup"><span data-stu-id="c3ab8-126">To set report history options and limits</span></span>](#bkmk_set_report_history)  
  
-   [<span data-ttu-id="c3ab8-127">Задать время ожидания базы данных</span><span class="sxs-lookup"><span data-stu-id="c3ab8-127">Set database timeout</span></span>](#bkmk_set_database_timeout)  
  
##  <a name="to-set-data-refresh-options"></a><a name="bkmk_set_data_refresh"></a><span data-ttu-id="c3ab8-128">Задание параметров обновления данных</span><span class="sxs-lookup"><span data-stu-id="c3ab8-128">To set data refresh options</span></span>  
  
1.  <span data-ttu-id="c3ab8-129">Укажите необходимый отчет в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-129">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="c3ab8-130">Нажмите стрелку вниз и выберите **Управление параметрами обработки**.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-130">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="c3ab8-131">В меню **Параметры обновления данных**выберите команду **Использовать данные моментальных снимков**.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-131">In **Data Refresh Options**, click **Use snapshot data**.</span></span> <span data-ttu-id="c3ab8-132">Если появится сообщение «Данный отчет не может быть запущен из моментального снимка, так как учетные данные источников не были сохранены», отчет не может быть запущен автоматически. Поэтому перед заданием указанного параметра необходимо настроить источники данных на использование сохраненных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-132">If you see "This report can not run from a snapshot because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="c3ab8-133">В меню **Параметры моментальных снимков данных**выберите команду **Расписание обработки данных**.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-133">In **Data Snapshot Options**, select **Schedule data processing**.</span></span>  
  
5.  <span data-ttu-id="c3ab8-134">Если нужно использовать существующее общее расписание, выберите **По общему расписанию** , в противном случае выберите **По нестандартному расписанию**и нажмите кнопку **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-134">Select **On a shared schedule** if you have an existing shared schedule that you want to use, otherwise click **On a custom schedule**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="c3ab8-135">Выберите частоту, расписание, начальную и конечную даты, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-135">Select frequency, schedule, and start and end dates, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="c3ab8-136">Если необходимо немедленно создать моментальный снимок отчета, не дожидаясь его сохранения по расписанию, в меню **Параметры моментальных снимков данных**выберите команду **Создать или обновить снимок после сохранения страницы** .</span><span class="sxs-lookup"><span data-stu-id="c3ab8-136">In **Data Snapshot Options**, select **Create or update the snapshot when this page is saved** if you want to immediately create snapshot data to use with the report, without waiting for the scheduled data processing to occur.</span></span>  
  
##  <a name="to-set-report-caching-options"></a><a name="bkmk_set_report_caching"></a><span data-ttu-id="c3ab8-137">Установка параметров кэширования отчета</span><span class="sxs-lookup"><span data-stu-id="c3ab8-137">To set report caching options</span></span>  
  
1.  <span data-ttu-id="c3ab8-138">Укажите необходимый отчет в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-138">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="c3ab8-139">Нажмите стрелку вниз и выберите **Управление параметрами обработки**.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-139">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="c3ab8-140">В меню **Параметры обновления данных**выберите команду **Использовать кэшированные данные**.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-140">In **Data Refresh Options**, click **Use cached data**.</span></span> <span data-ttu-id="c3ab8-141">Если появится сообщение «Данный отчет не может быть кэширован, так как учетные данные источников не были сохранены», отчет не может быть запущен автоматически. Поэтому перед заданием указанного параметра необходимо настроить источники данных для использования сохраненных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-141">If you see "This report can not be cached because one or more of the data sources credentials are not stored", the report is not configured to run unattended and you must modify the data sources to use stored credentials before setting this option.</span></span>  
  
4.  <span data-ttu-id="c3ab8-142">В меню **Параметры кэша**укажите параметры истечения срока действия кэша.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-142">In **Cache Options**, specify how the cache will expire:</span></span>  
  
    -   <span data-ttu-id="c3ab8-143">Укажите время в минутах, по прошествии которого истекает срок действия кэша.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-143">Enter a number of minutes after which the cache will expire.</span></span>  
  
    -   <span data-ttu-id="c3ab8-144">Для указания времени очистки кэша рекомендуется использовать общее расписание.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-144">Use a shared schedule to clear the cache at times specified in the schedule.</span></span>  
  
    -   <span data-ttu-id="c3ab8-145">Также для очистки кэша можно создать пользовательское расписание.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-145">Create a custom schedule to clear the cache at a time that you specify.</span></span>  
  
##  <a name="to-set-processing-time-out-values"></a><a name="bkmk_set_processing"></a><span data-ttu-id="c3ab8-146">Установка значений времени ожидания обработки</span><span class="sxs-lookup"><span data-stu-id="c3ab8-146">To set processing time-out values</span></span>  
  
1.  <span data-ttu-id="c3ab8-147">Укажите необходимый отчет в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-147">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="c3ab8-148">Нажмите стрелку вниз и выберите **Управление параметрами обработки**.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-148">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="c3ab8-149">Чтобы использовать значение, указанное на уровне сервера отчетов, необходимо в списке **Время ожидания обработки**выбрать **Использовать параметры по умолчанию для сайта** .</span><span class="sxs-lookup"><span data-stu-id="c3ab8-149">In **Processing Time-out**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="c3ab8-150">В противном случае, если необходимо указать отсутствие истечения времени ожидания или указать другое значение времени ожидания, выберите **Не ограничивать время обработки отчета** или **Максимальное время обработки отчета (в секундах)** .</span><span class="sxs-lookup"><span data-stu-id="c3ab8-150">Otherwise, select **Do not time out report processing** or **Limit report processing in seconds** if you want to override that value with no time-out or different time-out values.</span></span>  
  
##  <a name="to-set-report-history-options-and-limits"></a><a name="bkmk_set_report_history"></a><span data-ttu-id="c3ab8-151">Установка параметров и ограничений журнала отчета</span><span class="sxs-lookup"><span data-stu-id="c3ab8-151">To set report history options and limits</span></span>  
  
1.  <span data-ttu-id="c3ab8-152">Укажите необходимый отчет в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-152">Point to a report in the library.</span></span>  
  
2.  <span data-ttu-id="c3ab8-153">Нажмите стрелку вниз и выберите **Управление параметрами обработки**.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-153">Click the down arrow, and select **Manage processing options**.</span></span>  
  
3.  <span data-ttu-id="c3ab8-154">В меню **Параметры моментальных снимков в журнале**укажите порядок и сроки обработки и сохранения.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-154">In **History Snapshot Options**, specify how and when data processing occurs and is saved.</span></span>  
  
4.  <span data-ttu-id="c3ab8-155">Чтобы использовать значение, указанное на уровне сервера отчетов, необходимо в меню **Количество моментальных снимков в журнале**выбрать команду **Использовать настройку веб-сайта по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="c3ab8-155">In **History Snapshot Limits**, select **Use site default setting** if you want to use the value specified at the report server level.</span></span> <span data-ttu-id="c3ab8-156">В противном случае выберите **Не ограничивать количество моментальных снимков** или **Ограничить количество моментальных снимков** и укажите значение.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-156">Otherwise, select **Do not limit the number of snapshots** or **Limit number of snapshots** to specify a custom value.</span></span>  
  
##  <a name="set-database-timeout"></a><a name="bkmk_set_database_timeout"></a><span data-ttu-id="c3ab8-157">Задать время ожидания базы данных</span><span class="sxs-lookup"><span data-stu-id="c3ab8-157">Set database timeout</span></span>  
  
1.  <span data-ttu-id="c3ab8-158">Задать время ожидания базы данных сервера отчетов SharePoint с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-158">Use Windows PowerShell to set the database timeout of a SharePoint report server.</span></span> <span data-ttu-id="c3ab8-159">Дополнительные сведения см. в разделе "Получение и задание свойств базы данных приложения Reporting Service" статьи [PowerShell cmdlets for Reporting Services SharePoint Mode](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md) (Командлеты PowerShell для режима совместимости с SharePoint служб Reporting Services).</span><span class="sxs-lookup"><span data-stu-id="c3ab8-159">For more information, see the "Get and set Properties of the Reporting Service Application Database" section of [PowerShell cmdlets for Reporting Services SharePoint Mode](../../2014/reporting-services/powershell-cmdlets-for-reporting-services-sharepoint-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ab8-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3ab8-160">See Also</span></span>  
 <span data-ttu-id="c3ab8-161">[Установка свойств обработки отчета](report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c3ab8-161">[Set Report Processing Properties](report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="c3ab8-162">[Кэширование отчетов (службы SSRS)](report-server/caching-reports-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c3ab8-162">[Caching Reports &#40;SSRS&#41;](report-server/caching-reports-ssrs.md) </span></span>  
 [<span data-ttu-id="c3ab8-163">Задание значений времени ожидания при обработке отчетов и общих наборов данных (SSRS)</span><span class="sxs-lookup"><span data-stu-id="c3ab8-163">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
  
  
