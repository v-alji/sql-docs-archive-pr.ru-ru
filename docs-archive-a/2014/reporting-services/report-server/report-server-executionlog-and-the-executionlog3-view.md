---
title: Журнал выполнения сервера отчетов и представление ExecutionLog3 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- logs [Reporting Services], execution
- execution logs [Reporting Services]
ms.assetid: a7ead67d-1404-4e67-97e7-4c7b0d942070
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 868f8497e61c17662cb621850cdb8aee74c82706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657016"
---
# <a name="report-server-execution-log-and-the-executionlog3-view"></a><span data-ttu-id="d5c6b-102">Журнал выполнения сервера отчетов и представление ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="d5c6b-102">Report Server Execution Log and the ExecutionLog3 View</span></span>
  <span data-ttu-id="d5c6b-103">Журнал выполнения для сервера отчетов содержит сведения об отчетах, выполняемых на сервере или на нескольких серверах при использовании масштабного развертывания в собственном режиме или фермы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-103">The report server execution log contains information about the reports that execute on the server or on multiple servers in a native mode scale-out deployment or a SharePoint farm.</span></span> <span data-ttu-id="d5c6b-104">Журнал выполнения отчетов можно использовать для изучения частоты, с которой запрашивается отчет, частоты использования различных форматов вывода и времени обработки в миллисекундах, занимаемого каждой фазой обработки.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-104">You can use the report execution log to find out how often a report is requested, what output formats are used the most, and how many milliseconds of processing time is spent on each processing phase.</span></span> <span data-ttu-id="d5c6b-105">Журнал содержит сведения о продолжительности времени, затраченного на выполнение запроса набора данных отчета, и времени, затраченного на обработку данных.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-105">The log contains information on the length of time spent executing a report's dataset query and the time spent processing the data.</span></span> <span data-ttu-id="d5c6b-106">Администраторы сервера отчетов могут просматривать информацию журнала, выявлять задачи, выполняющиеся продолжительное время, и вносить предложения для разработчиков отчетов в тех областях организации отчета (набор данных или обработка), в которых они могут проводить улучшения.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-106">If you are a report server administrator, you can review the log information and identify long running tasks and make suggestions to the report authors on the areas of the report (dataset or processing) they may be able to improve.</span></span>  
  
 <span data-ttu-id="d5c6b-107">На серверах отчетов, настроенных для режима SharePoint, можно также использовать журналы ULS SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-107">Report servers configured for SharePoint mode, can also utilize the SharePoint ULS logs.</span></span> <span data-ttu-id="d5c6b-108">Дополнительные сведения см. в разделе [Включение событий служб Reporting Services для журнала трассировки SharePoint (ULS)](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span><span class="sxs-lookup"><span data-stu-id="d5c6b-108">For more information, see [Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span></span>  
  
##  <a name="viewing-log-information"></a><a name="bkmk_top"></a> <span data-ttu-id="d5c6b-109">Просмотр данных журнала</span><span class="sxs-lookup"><span data-stu-id="d5c6b-109">Viewing Log Information</span></span>  
 <span data-ttu-id="d5c6b-110">Сервер отчетов записывает данные о выполнении отчетов во внутреннюю таблицу базы данных.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-110">The report server execution logs data about report execution into an internal database table.</span></span> <span data-ttu-id="d5c6b-111">Сведения, содержащиеся в этой таблице, могут быть получены из представлений SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-111">The information from the table is available from SQL Server views.</span></span>  
  
 <span data-ttu-id="d5c6b-112">Журнал выполнения отчета хранится в базе данных сервера отчетов, которая по умолчанию носит имя **ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-112">The report execution log is stored in the report server database that by default is named **ReportServer**.</span></span> <span data-ttu-id="d5c6b-113">Представления SQL отображают сведения журналов выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-113">The SQL views provide the execution log information.</span></span> <span data-ttu-id="d5c6b-114">Представления "2" и "3" были добавлены в последних выпусках и содержат новые поля или поля с более удобными именами, чем в предыдущих выпусках.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-114">The "2" and "3" views were added in more recent releases and contain new fields or they contain fields with friendlier names than the previous releases.</span></span> <span data-ttu-id="d5c6b-115">Существовавшие ранее представления не исключены из состава продукта, поэтому зависящие от них пользовательские приложения не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-115">The older views remain in the product so custom applications that depend on them are not impacted.</span></span> <span data-ttu-id="d5c6b-116">При отсутствии зависимости от более старого представления, например ExecutionLog, рекомендуется использовать последнее по времени представление, ExecutionLog**3**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-116">If you do not have a dependence on an older view, for example ExecutionLog, it is recommended you use the most recent view, ExecutionLog**3**.</span></span>  
  
 <span data-ttu-id="d5c6b-117">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-117">In this topic:</span></span>  
  
-   [<span data-ttu-id="d5c6b-118">Значения параметров конфигурации для сервера отчетов с режимом SharePoint</span><span class="sxs-lookup"><span data-stu-id="d5c6b-118">Configuration Settings for a SharePoint mode Report Server</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="d5c6b-119">Значения параметров конфигурации для сервера отчетов с собственным режимом</span><span class="sxs-lookup"><span data-stu-id="d5c6b-119">Configuration Settings for a Native Mode Report Server</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="d5c6b-120">Поля журнала (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="d5c6b-120">Log Fields (ExecutionLog3)</span></span>](#bkmk_executionlog3)  
  
-   [<span data-ttu-id="d5c6b-121">Поле AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="d5c6b-121">The AdditionalInfo Field</span></span>](#bkmk_additionalinfo)  
  
-   [<span data-ttu-id="d5c6b-122">Поля журнала (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="d5c6b-122">Log Fields (ExecutionLog2)</span></span>](#bkmk_executionlog2)  
  
-   [<span data-ttu-id="d5c6b-123">Поля журнала (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="d5c6b-123">Log Fields (ExecutionLog)</span></span>](#bkmk_executionlog)  
  
##  <a name="configuration-settings-for-a-sharepoint-mode-report-server"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="d5c6b-124">Значения параметров конфигурации для сервера отчетов с режимом SharePoint</span><span class="sxs-lookup"><span data-stu-id="d5c6b-124">Configuration Settings for a SharePoint mode Report Server</span></span>  
 <span data-ttu-id="d5c6b-125">Предусмотрена возможность включать и отключать ведение журнала выполнения отчета с помощью параметров настройки системы для приложения службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5c6b-125">You can turn report execution logging on or off from the system settings of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
 <span data-ttu-id="d5c6b-126">По умолчанию записи журнала хранятся 60 суток.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-126">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="d5c6b-127">Записи с истекшим сроком хранения удаляются в 02:00</span><span class="sxs-lookup"><span data-stu-id="d5c6b-127">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="d5c6b-128">ежедневно.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-128">every day.</span></span> <span data-ttu-id="d5c6b-129">При готовой установке в заданный момент времени доступны данные только за последние 60 дней.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-129">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="d5c6b-130">Возможность ограничения количества строк или типа элементов, вносимых в журнал, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-130">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="d5c6b-131">**Включение ведения журнала выполнения.**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-131">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="d5c6b-132">В центре администрирования SharePoint щелкните **Управление приложениями службы** в группе **Управление приложениями** .</span><span class="sxs-lookup"><span data-stu-id="d5c6b-132">From SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="d5c6b-133">Щелкните имя приложения службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , которое требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-133">Click the name of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application you want to configure.</span></span>  
  
3.  <span data-ttu-id="d5c6b-134">Нажмите кнопку **Системные параметры**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-134">Click **System Settings**.</span></span>  
  
4.  <span data-ttu-id="d5c6b-135">Выберите **Включить ведение журнала выполнения** в разделе **Ведение журнала** .</span><span class="sxs-lookup"><span data-stu-id="d5c6b-135">Select **Enable Execution Logging** in the **Logging** section.</span></span>  
  
5.  <span data-ttu-id="d5c6b-136">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-136">Click **OK**.</span></span>  
  
 <span data-ttu-id="d5c6b-137">**Включение подробного ведения журнала.**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-137">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="d5c6b-138">Необходимо включить ведение журнала, как описано в предыдущих шагах, а затем выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-138">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="d5c6b-139">На странице **Системные параметры** приложения служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] найдите раздел **Определяемые пользователем** .</span><span class="sxs-lookup"><span data-stu-id="d5c6b-139">From the **System Settings** page of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] services application, find the **User-defined** section.</span></span>  
  
2.  <span data-ttu-id="d5c6b-140">Измените значение параметра **ExecutionLogLevel** на **подробный**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-140">Change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="d5c6b-141">Это поле представляет собой поле ввода текста, и двумя возможными значениями являются **подробный** и **обычный**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-141">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="configuration-settings-for-a-native-mode-report-server"></a><a name="bkmk_native"></a> <span data-ttu-id="d5c6b-142">Значения параметров конфигурации для сервера отчетов с собственным режимом</span><span class="sxs-lookup"><span data-stu-id="d5c6b-142">Configuration Settings for a Native Mode Report Server</span></span>  
 <span data-ttu-id="d5c6b-143">Предусмотрена возможность включать или отключать ведение журнала выполнения отчета на странице «Свойства сервера» в среде SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-143">You can turn report execution logging on or off from the Server Properties page in SQL Server Management Studio.</span></span> <span data-ttu-id="d5c6b-144">Свойство **EnableExecutionLogging** является расширенным.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-144">The **EnableExecutionLogging** is and Advanced property.</span></span>  
  
 <span data-ttu-id="d5c6b-145">По умолчанию записи журнала хранятся 60 суток.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-145">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="d5c6b-146">Записи с истекшим сроком хранения удаляются в 02:00</span><span class="sxs-lookup"><span data-stu-id="d5c6b-146">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="d5c6b-147">ежедневно.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-147">every day.</span></span> <span data-ttu-id="d5c6b-148">При готовой установке в заданный момент времени доступны данные только за последние 60 дней.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-148">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="d5c6b-149">Возможность ограничения количества строк или типа элементов, вносимых в журнал, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-149">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="d5c6b-150">**Включение ведения журнала выполнения.**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-150">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="d5c6b-151">Запустите среду SQL Server Management Studio с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-151">Start SQL Server Management Studio with administrative privileges.</span></span> <span data-ttu-id="d5c6b-152">Например, щелкните правой кнопкой мыши значок среды Management Studio и выберите команду "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="d5c6b-152">For example right-click the Management Studio icon and click 'Run as administrator'.</span></span>  
  
2.  <span data-ttu-id="d5c6b-153">Установите соединение с требуемым сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-153">Connect to the desired report server.</span></span>  
  
3.  <span data-ttu-id="d5c6b-154">Щелкните правой кнопкой мыши имя сервера и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-154">Right-click the server name and click **Properties**.</span></span> <span data-ttu-id="d5c6b-155">Если параметр «Свойства» отключен, убедитесь в том, что запуск среды SQL Server Management Studio был выполнен с административными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-155">If the Properties option is disabled, verify you ran SQL Server Management Studio with administrative privileges.</span></span>  
  
4.  <span data-ttu-id="d5c6b-156">Перейдите на страницу **Ведение журнала** .</span><span class="sxs-lookup"><span data-stu-id="d5c6b-156">Click the **Logging** page.</span></span>  
  
5.  <span data-ttu-id="d5c6b-157">Выберите **Включить ведение журнала выполнения отчета**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-157">Select **Enable report execution Logging**.</span></span>  
  
 <span data-ttu-id="d5c6b-158">**Включение подробного ведения журнала.**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-158">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="d5c6b-159">Необходимо включить ведение журнала, как описано в предыдущих шагах, а затем выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-159">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="d5c6b-160">В окне **Свойства сервера** перейдите на страницу **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="d5c6b-160">From the **Server Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="d5c6b-161">В разделе **Определяемый пользователем** измените значение **ExecutionLogLevel** на **подробный**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-161">In the **User-defined** section, change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="d5c6b-162">Это поле представляет собой поле ввода текста, и двумя возможными значениями являются **подробный** и **обычный**.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-162">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="log-fields-executionlog3"></a><a name="bkmk_executionlog3"></a> <span data-ttu-id="d5c6b-163">Поля журнала (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="d5c6b-163">Log Fields (ExecutionLog3)</span></span>  
 <span data-ttu-id="d5c6b-164">Это представление добавило дополнительный узел диагностики производительности в столбец на основе XML **AdditionalInfo** .</span><span class="sxs-lookup"><span data-stu-id="d5c6b-164">This view added additional performance diagnostics node inside the XML based **AdditionalInfo** column.</span></span> <span data-ttu-id="d5c6b-165">Столбец AdditionalInfo содержит XML-структуру дополнительных полей данных вида «один ко многим».</span><span class="sxs-lookup"><span data-stu-id="d5c6b-165">The AdditionalInfo column contains an XML structure of 1 to many additional fields of information.</span></span> <span data-ttu-id="d5c6b-166">Ниже приведен пример инструкции Transact SQL для выборки строк из представления ExecutionLog3.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-166">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog3.</span></span> <span data-ttu-id="d5c6b-167">В этом образце предполагается, что база данных сервера отчетов носит имя **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-167">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog3 order by TimeStart DESC  
```  
  
 <span data-ttu-id="d5c6b-168">В следующей таблице описаны данные, которые перехватываются в журнале выполнения отчетов</span><span class="sxs-lookup"><span data-stu-id="d5c6b-168">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="d5c6b-169">Столбец</span><span class="sxs-lookup"><span data-stu-id="d5c6b-169">Column</span></span>|<span data-ttu-id="d5c6b-170">Description</span><span class="sxs-lookup"><span data-stu-id="d5c6b-170">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d5c6b-171">InstanceName</span><span class="sxs-lookup"><span data-stu-id="d5c6b-171">InstanceName</span></span>|<span data-ttu-id="d5c6b-172">Имя экземпляра сервера отчетов, обработавшего запрос.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-172">Name of the report server instance that handled the request.</span></span> <span data-ttu-id="d5c6b-173">Если в применяемой среде имеется больше одного сервера отчетов, можно анализировать распределение InstanceName для контроля и определения того, распределяет ли программа уравновешивания сетевой нагрузки запросы по серверам отчетов в соответствии с ожидаемым.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-173">If your environment has more than one report server, you can analyze the InstanceName distribution to monitor and determine if your network-load balancer distributes requests across report servers as expected.</span></span>|  
|<span data-ttu-id="d5c6b-174">ItemPath</span><span class="sxs-lookup"><span data-stu-id="d5c6b-174">ItemPath</span></span>|<span data-ttu-id="d5c6b-175">Путь, по которому сохраняется отчет или элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-175">Path of where a report or report item is stored.</span></span>|  
|<span data-ttu-id="d5c6b-176">UserName</span><span class="sxs-lookup"><span data-stu-id="d5c6b-176">UserName</span></span>|<span data-ttu-id="d5c6b-177">Идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-177">User identifier.</span></span>|  
|<span data-ttu-id="d5c6b-178">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="d5c6b-178">ExecutionID</span></span>|<span data-ttu-id="d5c6b-179">Внутренний идентификатор, связанный с запросом.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-179">The internal identifier associated with a request.</span></span> <span data-ttu-id="d5c6b-180">Запросы, выполняемые в рамках одного сеанса пользователя, имеют одинаковый идентификатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-180">Requests on the same user sessions share the same execution id.</span></span>|  
|<span data-ttu-id="d5c6b-181">RequestType</span><span class="sxs-lookup"><span data-stu-id="d5c6b-181">RequestType</span></span>|<span data-ttu-id="d5c6b-182">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-182">Possible Values:</span></span><br /><span data-ttu-id="d5c6b-183">**Интерактивный**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-183">**Interactive**</span></span><br /><span data-ttu-id="d5c6b-184">**Подписка**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-184">**Subscription**</span></span><br /><br /> <br /><br /> <span data-ttu-id="d5c6b-185">Анализ данных журнала, отфильтрованных по значению RequestType=Subscription и отсортированных по значению TimeStart, может показать периоды интенсивной нагрузки на подписку, и может потребоваться изменить параметры некоторых подписок на отчет для другого вызова.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-185">Analyzing log data filtered by RequestType=Subscription and sorted by TimeStart may reveal periods of heavy subscription usage and you may want to modify some of the report subscriptions to a different time.</span></span>|  
|<span data-ttu-id="d5c6b-186">Формат</span><span class="sxs-lookup"><span data-stu-id="d5c6b-186">Format</span></span>|<span data-ttu-id="d5c6b-187">Формат подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-187">Rendering format.</span></span>|  
|<span data-ttu-id="d5c6b-188">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5c6b-188">Parameters</span></span>|<span data-ttu-id="d5c6b-189">Значения параметров, используемых при выполнении отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-189">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="d5c6b-190">ItemAction</span><span class="sxs-lookup"><span data-stu-id="d5c6b-190">ItemAction</span></span>|<span data-ttu-id="d5c6b-191">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-191">Possible values:</span></span><br /><br /> <span data-ttu-id="d5c6b-192">**Прорисовка**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-192">**Render**</span></span><br /><br /> <span data-ttu-id="d5c6b-193">**Sort**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-193">**Sort**</span></span><br /><br /> <span data-ttu-id="d5c6b-194">**BookMarkNavigation**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-194">**BookMarkNavigation**</span></span><br /><br /> <span data-ttu-id="d5c6b-195">**DocumentNavigation**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-195">**DocumentNavigation**</span></span><br /><br /> <span data-ttu-id="d5c6b-196">**GetDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-196">**GetDocumentMap**</span></span><br /><br /> <span data-ttu-id="d5c6b-197">**FindString**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-197">**Findstring**</span></span><br /><br /> <span data-ttu-id="d5c6b-198">**Execute**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-198">**Execute**</span></span><br /><br /> <span data-ttu-id="d5c6b-199">**RenderEdit**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-199">**RenderEdit**</span></span>|  
|<span data-ttu-id="d5c6b-200">TimeStart</span><span class="sxs-lookup"><span data-stu-id="d5c6b-200">TimeStart</span></span>|<span data-ttu-id="d5c6b-201">Время начала и завершения обработки отчета, указывающее на его продолжительность.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-201">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="d5c6b-202">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="d5c6b-202">TimeEnd</span></span>||  
|<span data-ttu-id="d5c6b-203">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="d5c6b-203">TimeDataRetrieval</span></span>|<span data-ttu-id="d5c6b-204">Количество миллисекунд, затраченных на выборку данных.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-204">Number of milliseconds spent retrieving the data.</span></span>|  
|<span data-ttu-id="d5c6b-205">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="d5c6b-205">TimeProcessing</span></span>|<span data-ttu-id="d5c6b-206">Количество миллисекунд, затраченных на обработку отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-206">Number of milliseconds spent processing the report.</span></span>|  
|<span data-ttu-id="d5c6b-207">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="d5c6b-207">TimeRendering</span></span>|<span data-ttu-id="d5c6b-208">Количество миллисекунд, затраченных на подготовку отчета к просмотру.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-208">Number of milliseconds spent rendering the report.</span></span>|  
|<span data-ttu-id="d5c6b-209">Источник</span><span class="sxs-lookup"><span data-stu-id="d5c6b-209">Source</span></span>|<span data-ttu-id="d5c6b-210">Источник выполнения отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-210">Source of the report execution.</span></span> <span data-ttu-id="d5c6b-211">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-211">Possible values:</span></span><br /><br /> <span data-ttu-id="d5c6b-212">**В реальном времени**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-212">**Live**</span></span><br /><br /> <span data-ttu-id="d5c6b-213">**Кэш**: указывает на кэшированное выполнение, например, запросы к набору данных не выполняются в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-213">**Cache**: Indicates a cached execution, for example, dataset queries are not executed live.</span></span><br /><br /> <span data-ttu-id="d5c6b-214">**Моментальный снимок**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-214">**Snapshot**</span></span><br /><br /> <span data-ttu-id="d5c6b-215">**Журнал**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-215">**History**</span></span><br /><br /> <span data-ttu-id="d5c6b-216">**Нерегламентированный** : указывает либо динамически формируемый детализированный отчет на основе модели отчета, либо отчет построитель отчетов, который предварительно отображается на клиенте, использующем сервер отчетов для обработки и подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-216">**AdHoc** : Indicates either a dynamically generated report model based drill through report, or a Report Builder report that is previewed on a client utilizing the report server for processing and rendering.</span></span><br /><br /> <span data-ttu-id="d5c6b-217">**Сеанс**: указывает на запрос к исполнению в уже установленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-217">**Session**: Indicates a follow up request within an already established session.</span></span>  <span data-ttu-id="d5c6b-218">Например, первоначальный запрос был на просмотр страницы 1, а последующий ― на экспорт в Excel с текущим состоянием сеанса.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-218">For example the initial request is to view page 1, and the follow up request is to export to Excel with the current session state.</span></span><br /><br /> <span data-ttu-id="d5c6b-219">**RDCE**: Указывает расширение настройки определения отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-219">**Rdce**:  Indicates a Report Definition Customization Extension.</span></span> <span data-ttu-id="d5c6b-220">Пользовательское расширение RDCE позволяет динамически настраивать определение отчета до передачи его в модуль обработки при выполнении отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-220">An RDCE custom extension can dynamically customize a report definition before it is passed to the processing engine upon report execution.</span></span>|  
|<span data-ttu-id="d5c6b-221">Состояние</span><span class="sxs-lookup"><span data-stu-id="d5c6b-221">Status</span></span>|<span data-ttu-id="d5c6b-222">Состояние (либо rsSuccess, либо код ошибки. Если ошибок несколько, то записывается только первая).</span><span class="sxs-lookup"><span data-stu-id="d5c6b-222">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="d5c6b-223">ByteCount</span><span class="sxs-lookup"><span data-stu-id="d5c6b-223">ByteCount</span></span>|<span data-ttu-id="d5c6b-224">Размер отчетов, готовых для просмотра (в байтах).</span><span class="sxs-lookup"><span data-stu-id="d5c6b-224">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="d5c6b-225">RowCount</span><span class="sxs-lookup"><span data-stu-id="d5c6b-225">RowCount</span></span>|<span data-ttu-id="d5c6b-226">Количество возвращенных по запросам строк.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-226">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="d5c6b-227">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="d5c6b-227">AdditionalInfo</span></span>|<span data-ttu-id="d5c6b-228">Контейнер свойств XML, содержащий дополнительные сведения о выполнении.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-228">An XML property bag containing additional information about the execution.</span></span> <span data-ttu-id="d5c6b-229">Содержимое может быть разным для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-229">The contents can be different for each row.</span></span>|  
  
##  <a name="the-additionalinfo-field"></a><a name="bkmk_additionalinfo"></a> <span data-ttu-id="d5c6b-230">Поле AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="d5c6b-230">The AdditionalInfo Field</span></span>  
 <span data-ttu-id="d5c6b-231">Поле AdditionalInfo представляет собой контейнер свойств XML или структуру, содержащую дополнительные сведения о выполнении.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-231">The AdditionalInfo field is an XML property bag or structure containing additional information about the execution.</span></span> <span data-ttu-id="d5c6b-232">Содержимое может быть разным для каждой строки журнала.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-232">The contents can be different for each row in the log.</span></span>  
  
 <span data-ttu-id="d5c6b-233">Следующие таблицы являются примерами содержимого поля AddtionalInfo для стандартного ведения журнала и подробного ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-233">The following tables are examples  of the contents of the AddtionalInfo field for both standard and verbose logging:</span></span>  
  
 <span data-ttu-id="d5c6b-234">**Пример столбца AddtionalInfo при стандартном ведении журнала**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-234">**Standard logging example of AddtionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>147</ConnectionOpenTime>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>642</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>63</ExecuteReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>157</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>60</ExecuteReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="d5c6b-235">**Пример столбца AddtionalInfo при подробном ведении журнала**</span><span class="sxs-lookup"><span data-stu-id="d5c6b-235">**Verbose logging example of AdditionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>127</ConnectionOpenTime>  
      <DataSource>  
        <Name>DataSource1</Name>  
        <DataExtension>SQL</DataExtension>  
      </DataSource>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>33</ExecuteReaderTime>  
          <DataReaderMappingTime>30</DataReaderMappingTime>  
          <DisposeDataReaderTime>1</DisposeDataReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>1</ExecuteReaderTime>  
          <DataReaderMappingTime>0</DataReaderMappingTime>  
          <DisposeDataReaderTime>0</DisposeDataReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="d5c6b-236">Ниже описаны некоторые свойства, которые вы увидите в поле AdditionalInfo:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-236">The following describes some of the properties you will see in the AdditionalInfo field:</span></span>  
  
-   <span data-ttu-id="d5c6b-237">**Процессинженгине**: 1 = SQL Server 2005, 2 = новый обработчик обработки по требованию.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-237">**ProcessingEngine**: 1=SQL Server 2005, 2=The new On-demand Processing Engine.</span></span> <span data-ttu-id="d5c6b-238">Если в большинстве отчетов все еще отображается значение 1, можно изучить вопрос о том, как их перепроектировать в целях применения более нового и более эффективного ядра обработки по требованию.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-238">If a majority of your reports are still showing the value of 1, you may investigate how to redesign them so they utilize the newer and more efficient on-demand processing engine.</span></span>  
  
     `<ProcessingEngine>2</ProcessingEngine>`  
  
-   <span data-ttu-id="d5c6b-239">**Скалабилититиме**: количество миллисекунд, затраченных на выполнение операций, связанных с масштабированием, в обработчике обработки.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-239">**ScalabilityTime**: The number of milliseconds spent performing scale related operations in the processing engine.</span></span> <span data-ttu-id="d5c6b-240">Значение 0 указывает, что на операции масштабирования не было затрачено дополнительное время, а также свидетельствует о том, что запрос не выполнялся в условиях нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-240">A value of 0 indicates that no additional time was spent on scale operations and a 0 also indicates the request was not under memory pressure.</span></span>  
  
    ```  
    <ScalabilityTime>  
        <Processing>0</Processing>  
    </ScalabilityTime>  
    ```  
  
-   <span data-ttu-id="d5c6b-241">**Естиматедмеморюсажекб**: Оценка пикового объема памяти (в килобайтах), потребляемого каждым компонентом во время конкретного запроса.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-241">**EstimatedMemoryUsageKB**: An estimate of the peak amount of memory, in kilobytes, consumed by each component during a particular request.</span></span>  
  
    ```  
    <EstimatedMemoryUsageKB>  
        <Processing>38</Processing>  
    </EstimatedMemoryUsageKB>  
    ```  
  
-   <span data-ttu-id="d5c6b-242">**Extension**: типы модулей обработки данных или источников данных, используемых в отчете.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-242">**DataExtension**: The types of data extensions or data sources used in the report.</span></span> <span data-ttu-id="d5c6b-243">Это число показывает количество вхождений конкретного источника данных.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-243">The number is a count of the number of occurrences of the particular data source.</span></span>  
  
    ```  
    <DataExtension>  
       <DAX>2</DAX>  
    </DataExtension>  
    ```  
  
-   <span data-ttu-id="d5c6b-244">**Екстерналимажес** Значение находится в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-244">**ExternalImages**The value is in miliseconds.</span></span> <span data-ttu-id="d5c6b-245">Эти данные могут использоваться для диагностики проблем производительности.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-245">This data can be used to diagnose performance issues.</span></span> <span data-ttu-id="d5c6b-246">Время, необходимое для получения изображений от внешнего веб-сервера, может замедлить выполнение отчета в целом.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-246">The time needed to retrieve images from an external webserver may slow the overall report execution.</span></span> <span data-ttu-id="d5c6b-247">Добавлено в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5c6b-247">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <ExternalImages>  
        <Count>3</Count>  
        <ByteCount>9268</ByteCount>  
        <ResourceFetchTime>9</ResourceFetchTime>  
    </ExternalImages>  
    ```  
  
-   <span data-ttu-id="d5c6b-248">**Connections**: многоуровневая структура.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-248">**Connections**: A multi-leveled structure.</span></span> <span data-ttu-id="d5c6b-249">Добавлено в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5c6b-249">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <Connections>  
        <Connection>  
          <ConnectionOpenTime>127</ConnectionOpenTime>  
          <DataSource>  
            <Name>DataSource1</Name>  
            <DataExtension>SQL</DataExtension>  
          </DataSource>  
          <DataSets>  
            <DataSet>  
              <Name>DataSet1</Name>  
              <RowsRead>16</RowsRead>  
              <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>33</ExecuteReaderTime>  
              <DataReaderMappingTime>30</DataReaderMappingTime>  
              <DisposeDataReaderTime>1</DisposeDataReaderTime>  
            </DataSet>  
            <DataSet>  
              <Name>DataSet2</Name>  
              <RowsRead>3</RowsRead>  
              <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>1</ExecuteReaderTime>  
              <DataReaderMappingTime>0</DataReaderMappingTime>  
              <DisposeDataReaderTime>0</DisposeDataReaderTime>  
            </DataSet>  
          </DataSets>  
        </Connection>  
    </Connections>  
  
    ```  
  
##  <a name="log-fields-executionlog2"></a><a name="bkmk_executionlog2"></a> <span data-ttu-id="d5c6b-250">Поля журнала (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="d5c6b-250">Log Fields (ExecutionLog2)</span></span>  
 <span data-ttu-id="d5c6b-251">В этом представлении добавлено несколько новых полей, а некоторые другие поля переименованы.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-251">This view added a few new fields and renamed a few others.</span></span> <span data-ttu-id="d5c6b-252">Ниже приведен пример инструкции Transact SQL для выборки строк из представления ExecutionLog2.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-252">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog2.</span></span> <span data-ttu-id="d5c6b-253">В этом образце предполагается, что база данных сервера отчетов носит имя **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-253">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog2 order by TimeStart DESC  
```  
  
 <span data-ttu-id="d5c6b-254">В следующей таблице описаны данные, которые перехватываются в журнале выполнения отчетов</span><span class="sxs-lookup"><span data-stu-id="d5c6b-254">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="d5c6b-255">Столбец</span><span class="sxs-lookup"><span data-stu-id="d5c6b-255">Column</span></span>|<span data-ttu-id="d5c6b-256">Описание</span><span class="sxs-lookup"><span data-stu-id="d5c6b-256">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d5c6b-257">InstanceName</span><span class="sxs-lookup"><span data-stu-id="d5c6b-257">InstanceName</span></span>|<span data-ttu-id="d5c6b-258">Имя экземпляра сервера отчетов, обработавшего запрос.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-258">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="d5c6b-259">ReportPath</span><span class="sxs-lookup"><span data-stu-id="d5c6b-259">ReportPath</span></span>|<span data-ttu-id="d5c6b-260">Структура пути к отчету.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-260">The path structure to the report.</span></span>  <span data-ttu-id="d5c6b-261">Например, отчет с именем test, который находится в корневом каталоге в диспетчере отчетов, будет иметь значение ReportPath, равное "/test".</span><span class="sxs-lookup"><span data-stu-id="d5c6b-261">For example a report named "test" which is the in root folder in Report Manager, would have a ReportPath of "/test".</span></span><br /><br /> <span data-ttu-id="d5c6b-262">Отчет с именем test, который сохранен в папке samples в диспетчере отчетов, будет иметь значение ReportPath, равное "/Samples/test/".</span><span class="sxs-lookup"><span data-stu-id="d5c6b-262">A report named "test" that is saved in the folder "samples" on Report Manager , will have a ReportPath of "/Samples/test/"</span></span>|  
|<span data-ttu-id="d5c6b-263">UserName</span><span class="sxs-lookup"><span data-stu-id="d5c6b-263">UserName</span></span>|<span data-ttu-id="d5c6b-264">Идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-264">User identifier.</span></span>|  
|<span data-ttu-id="d5c6b-265">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="d5c6b-265">ExecutionID</span></span>||  
|<span data-ttu-id="d5c6b-266">RequestType</span><span class="sxs-lookup"><span data-stu-id="d5c6b-266">RequestType</span></span>|<span data-ttu-id="d5c6b-267">Тип запроса (пользовательский или системный).</span><span class="sxs-lookup"><span data-stu-id="d5c6b-267">Request type (either user or system).</span></span>|  
|<span data-ttu-id="d5c6b-268">Формат</span><span class="sxs-lookup"><span data-stu-id="d5c6b-268">Format</span></span>|<span data-ttu-id="d5c6b-269">Формат подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-269">Rendering format.</span></span>|  
|<span data-ttu-id="d5c6b-270">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5c6b-270">Parameters</span></span>|<span data-ttu-id="d5c6b-271">Значения параметров, используемых при выполнении отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-271">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="d5c6b-272">ReportAction</span><span class="sxs-lookup"><span data-stu-id="d5c6b-272">ReportAction</span></span>|<span data-ttu-id="d5c6b-273">Возможные значения: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span><span class="sxs-lookup"><span data-stu-id="d5c6b-273">Possible values: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span></span>|  
|<span data-ttu-id="d5c6b-274">TimeStart</span><span class="sxs-lookup"><span data-stu-id="d5c6b-274">TimeStart</span></span>|<span data-ttu-id="d5c6b-275">Время начала и завершения обработки отчета, указывающее на его продолжительность.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-275">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="d5c6b-276">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="d5c6b-276">TimeEnd</span></span>||  
|<span data-ttu-id="d5c6b-277">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="d5c6b-277">TimeDataRetrieval</span></span>|<span data-ttu-id="d5c6b-278">Число миллисекунд, затраченных на получение данных, обработку запроса и его подготовку.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-278">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="d5c6b-279">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="d5c6b-279">TimeProcessing</span></span>||  
|<span data-ttu-id="d5c6b-280">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="d5c6b-280">TimeRendering</span></span>||  
|<span data-ttu-id="d5c6b-281">Источник</span><span class="sxs-lookup"><span data-stu-id="d5c6b-281">Source</span></span>|<span data-ttu-id="d5c6b-282">Источник выполнения запроса (1 = напрямую, 2 = кэш, 3 = моментальный снимок, 4 = журнал).</span><span class="sxs-lookup"><span data-stu-id="d5c6b-282">Source of the report execution (1=Live, 2=Cache, 3=Snapshot, 4=History).</span></span>|  
|<span data-ttu-id="d5c6b-283">Состояние</span><span class="sxs-lookup"><span data-stu-id="d5c6b-283">Status</span></span>|<span data-ttu-id="d5c6b-284">Состояние (либо rsSuccess, либо код ошибки. Если ошибок несколько, то записывается только первая).</span><span class="sxs-lookup"><span data-stu-id="d5c6b-284">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="d5c6b-285">ByteCount</span><span class="sxs-lookup"><span data-stu-id="d5c6b-285">ByteCount</span></span>|<span data-ttu-id="d5c6b-286">Размер отчетов, готовых для просмотра (в байтах).</span><span class="sxs-lookup"><span data-stu-id="d5c6b-286">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="d5c6b-287">RowCount</span><span class="sxs-lookup"><span data-stu-id="d5c6b-287">RowCount</span></span>|<span data-ttu-id="d5c6b-288">Количество возвращенных по запросам строк.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-288">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="d5c6b-289">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="d5c6b-289">AdditionalInfo</span></span>|<span data-ttu-id="d5c6b-290">Контейнер свойств XML, содержащий дополнительные сведения о выполнении.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-290">An XML property bag containing additional information about the execution.</span></span>|  
  
##  <a name="log-fields-executionlog"></a><a name="bkmk_executionlog"></a> <span data-ttu-id="d5c6b-291">Поля журнала (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="d5c6b-291">Log Fields (ExecutionLog)</span></span>  
 <span data-ttu-id="d5c6b-292">Ниже приведен пример инструкции Transact SQL для выборки строк из представления ExecutionLog.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-292">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog.</span></span> <span data-ttu-id="d5c6b-293">В этом образце предполагается, что база данных сервера отчетов носит имя **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-293">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog order by TimeStart DESC  
  
```  
  
 <span data-ttu-id="d5c6b-294">В следующей таблице описаны данные, которые перехватываются в журнале выполнения отчетов</span><span class="sxs-lookup"><span data-stu-id="d5c6b-294">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="d5c6b-295">Столбец</span><span class="sxs-lookup"><span data-stu-id="d5c6b-295">Column</span></span>|<span data-ttu-id="d5c6b-296">Описание</span><span class="sxs-lookup"><span data-stu-id="d5c6b-296">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d5c6b-297">InstanceName</span><span class="sxs-lookup"><span data-stu-id="d5c6b-297">InstanceName</span></span>|<span data-ttu-id="d5c6b-298">Имя экземпляра сервера отчетов, обработавшего запрос.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-298">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="d5c6b-299">ReportID</span><span class="sxs-lookup"><span data-stu-id="d5c6b-299">ReportID</span></span>|<span data-ttu-id="d5c6b-300">Идентификатор отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-300">Report identifier.</span></span>|  
|<span data-ttu-id="d5c6b-301">UserName</span><span class="sxs-lookup"><span data-stu-id="d5c6b-301">UserName</span></span>|<span data-ttu-id="d5c6b-302">Идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-302">User identifier.</span></span>|  
|<span data-ttu-id="d5c6b-303">RequestType</span><span class="sxs-lookup"><span data-stu-id="d5c6b-303">RequestType</span></span>|<span data-ttu-id="d5c6b-304">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-304">Possible values:</span></span><br /><br /> <span data-ttu-id="d5c6b-305">True = запрос на подписку</span><span class="sxs-lookup"><span data-stu-id="d5c6b-305">True = A Subscription request</span></span><br /><br /> <span data-ttu-id="d5c6b-306">False= интерактивный запрос</span><span class="sxs-lookup"><span data-stu-id="d5c6b-306">False= An Interactive request</span></span>|  
|<span data-ttu-id="d5c6b-307">Формат</span><span class="sxs-lookup"><span data-stu-id="d5c6b-307">Format</span></span>|<span data-ttu-id="d5c6b-308">Формат подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-308">Rendering format.</span></span>|  
|<span data-ttu-id="d5c6b-309">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5c6b-309">Parameters</span></span>|<span data-ttu-id="d5c6b-310">Значения параметров, используемых при выполнении отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-310">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="d5c6b-311">TimeStart</span><span class="sxs-lookup"><span data-stu-id="d5c6b-311">TimeStart</span></span>|<span data-ttu-id="d5c6b-312">Время начала и завершения обработки отчета, указывающее на его продолжительность.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-312">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="d5c6b-313">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="d5c6b-313">TimeEnd</span></span>||  
|<span data-ttu-id="d5c6b-314">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="d5c6b-314">TimeDataRetrieval</span></span>|<span data-ttu-id="d5c6b-315">Число миллисекунд, затраченных на получение данных, обработку запроса и его подготовку.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-315">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="d5c6b-316">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="d5c6b-316">TimeProcessing</span></span>||  
|<span data-ttu-id="d5c6b-317">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="d5c6b-317">TimeRendering</span></span>||  
|<span data-ttu-id="d5c6b-318">Источник</span><span class="sxs-lookup"><span data-stu-id="d5c6b-318">Source</span></span>|<span data-ttu-id="d5c6b-319">Источник выполнения отчета.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-319">Source of the report execution.</span></span> <span data-ttu-id="d5c6b-320">Возможные значения: (1=реальные данные, 2=кэш, 3=моментальный снимок, 4=журнал, 5=нерегламентированные данные, 6=сеанс, 7=RDCE).</span><span class="sxs-lookup"><span data-stu-id="d5c6b-320">Possible values: (1=Live, 2=Cache, 3=Snapshot, 4=History, 5=Adhoc, 6=Session, 7=RDCE).</span></span>|  
|<span data-ttu-id="d5c6b-321">Состояние</span><span class="sxs-lookup"><span data-stu-id="d5c6b-321">Status</span></span>|<span data-ttu-id="d5c6b-322">Возможные значения: rsSuccess, rsProcessingAborted или код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-322">Possible values: rsSuccess, rsProcessingAborted, or an error code.</span></span> <span data-ttu-id="d5c6b-323">Если происходит несколько ошибок, регистрируется только первая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-323">If multiple errors occur, only the first error is recorded.</span></span>|  
|<span data-ttu-id="d5c6b-324">ByteCount</span><span class="sxs-lookup"><span data-stu-id="d5c6b-324">ByteCount</span></span>|<span data-ttu-id="d5c6b-325">Размер отчетов, готовых для просмотра (в байтах).</span><span class="sxs-lookup"><span data-stu-id="d5c6b-325">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="d5c6b-326">RowCount</span><span class="sxs-lookup"><span data-stu-id="d5c6b-326">RowCount</span></span>|<span data-ttu-id="d5c6b-327">Количество возвращенных по запросам строк.</span><span class="sxs-lookup"><span data-stu-id="d5c6b-327">Number of rows returned from queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5c6b-328">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5c6b-328">See Also</span></span>  
 <span data-ttu-id="d5c6b-329">[Включение Reporting Services событий для журнала трассировки SharePoint &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span><span class="sxs-lookup"><span data-stu-id="d5c6b-329">[Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span></span>  
 <span data-ttu-id="d5c6b-330">[Файлы и источники журналов служб Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="d5c6b-330">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="d5c6b-331">Справочник по ошибкам и событиям (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="d5c6b-331">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](../troubleshooting/errors-and-events-reference-reporting-services.md)  
  
  
