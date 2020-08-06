---
title: Создание функции для получения информации об изменениях | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],creating function
ms.assetid: 55dd0946-bd67-4490-9971-12dfb5b9de94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc1d5af0a64225aca4ff54570ad6504d25d62812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740232"
---
# <a name="create-the-function-to-retrieve-the-change-data"></a><span data-ttu-id="1ce09-102">Создание функции для получения информации об изменениях</span><span class="sxs-lookup"><span data-stu-id="1ce09-102">Create the Function to Retrieve the Change Data</span></span>
  <span data-ttu-id="1ce09-103">После завершения потока управления для пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , выполняющего добавочную загрузку информации об изменениях, нужно выполнить следующую задачу: создать функцию с табличным значением, которая получает измененные данные.</span><span class="sxs-lookup"><span data-stu-id="1ce09-103">After completing the control flow for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the next task is to create a table-valued function that retrieves the change data.</span></span> <span data-ttu-id="1ce09-104">Создавать эту функцию необходимо только один раз — перед первой добавочной загрузкой.</span><span class="sxs-lookup"><span data-stu-id="1ce09-104">You only have to create this function one time before the first incremental load.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ce09-105">Создание функции для получения измененных данных — второй этап процесса формирования пакета, который выполняет добавочную загрузку измененных данных.</span><span class="sxs-lookup"><span data-stu-id="1ce09-105">The creation of a function to retrieve the change data is the second step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="1ce09-106">Общее описание процесса формирования этого пакета см. в разделе [Система отслеживания измененных данных (службы SSIS)](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="1ce09-106">For a description of the overall process for creating this package, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations-for-change-data-capture-functions"></a><span data-ttu-id="1ce09-107">Вопросы проектирования функций системы отслеживания измененных данных</span><span class="sxs-lookup"><span data-stu-id="1ce09-107">Design Considerations for Change Data Capture Functions</span></span>  
 <span data-ttu-id="1ce09-108">Чтобы получить измененные данные, исходный компонент в потоке данных пакета вызывает одну из следующих функций запроса системы отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="1ce09-108">To retrieve change data, a source component in the data flow of the package calls one of the following change data capture query functions:</span></span>  
  
-   <span data-ttu-id="1ce09-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** . Этот запрос возвращает для каждой операции обновления одну строку, которая содержит окончательное состояние каждой измененной строки.</span><span class="sxs-lookup"><span data-stu-id="1ce09-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** For this query, the single row returned for each update contains the final state of each changed row.</span></span> <span data-ttu-id="1ce09-110">В большинстве случаев требуются только данные, возвращаемые запросом для конечных изменений.</span><span class="sxs-lookup"><span data-stu-id="1ce09-110">In most cases, you only need the data returned by a query for net changes.</span></span> <span data-ttu-id="1ce09-111">Дополнительные сведения см. в разделе [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; (Transact-SQL)](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ce09-111">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
-   <span data-ttu-id="1ce09-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** . Этот запрос возвращает все изменения для каждой строки за весь период отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ce09-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** This query returns all the changes that have occurred in each row during the capture interval.</span></span> <span data-ttu-id="1ce09-113">Дополнительные сведения см. в разделе [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; (Transact-SQL)](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ce09-113">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="1ce09-114">Затем исходный компонент получает результаты, возвращенные функцией, и передает их нисходящим преобразованиям и назначениям, которые применяют измененные данные к конечному назначению.</span><span class="sxs-lookup"><span data-stu-id="1ce09-114">The source component then takes the results returned by the function and passes them to downstream transformations and destinations, which apply the change data to the final destination.</span></span>  
  
 <span data-ttu-id="1ce09-115">Однако исходный компонент служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] не может напрямую вызывать эти функции системы отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="1ce09-115">However, an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component cannot call these change data capture functions directly.</span></span> <span data-ttu-id="1ce09-116">Исходному компоненту служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] необходимы метаданные, касающиеся столбцов, возвращаемых запросом.</span><span class="sxs-lookup"><span data-stu-id="1ce09-116">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component requires metadata about the columns that the query returns.</span></span> <span data-ttu-id="1ce09-117">Функции системы отслеживания измененных данных не определяют столбцы своей выходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="1ce09-117">The change data capture functions do not define the columns of their output table.</span></span> <span data-ttu-id="1ce09-118">Таким образом, эти функции не возвращают достаточного объема метаданных для исходного компонента служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ce09-118">Thus, these functions do not return sufficient metadata for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
 <span data-ttu-id="1ce09-119">Вместо этого используется возвращающая табличное значение функция-оболочка, так как в предложениях RETURN функций этого типа явным образом определяются столбцы выходных таблиц.</span><span class="sxs-lookup"><span data-stu-id="1ce09-119">Instead, you use a table-valued wrapper function because this kind of function explicitly defines the columns of its output table in its RETURNS clause.</span></span> <span data-ttu-id="1ce09-120">В этом явном определении столбцов содержатся метаданные, необходимые для исходного компонента служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ce09-120">This explicit definition of columns provides the metadata that an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component needs.</span></span> <span data-ttu-id="1ce09-121">Эту функцию нужно создавать для каждой таблицы, для которой необходимо получить измененные данные.</span><span class="sxs-lookup"><span data-stu-id="1ce09-121">You have to create this function for each table for which you want to retrieve change data.</span></span>  
  
 <span data-ttu-id="1ce09-122">Существует два способа создания возвращающей табличное значение функции-оболочки, которая вызывает функцию запроса системы отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="1ce09-122">You have two options for creating the table-valued wrapper function that calls the change data capture query function:</span></span>  
  
-   <span data-ttu-id="1ce09-123">Чтобы создать функции с табличным значением, можно вызвать системную хранимую процедуру **sys.sp_cdc_generate_wrapper_function** .</span><span class="sxs-lookup"><span data-stu-id="1ce09-123">You can call the **sys.sp_cdc_generate_wrapper_function** system stored procedure to create the table-valued functions for you.</span></span>  
  
-   <span data-ttu-id="1ce09-124">Можно написать собственную возвращающую табличное значение функцию на основе рекомендаций и примера данного раздела.</span><span class="sxs-lookup"><span data-stu-id="1ce09-124">You can write your own table-valued function by using the guidelines and the example in this topic.</span></span>  
  
## <a name="calling-a-stored-procedure-to-create-the-table-valued-function"></a><span data-ttu-id="1ce09-125">Вызов хранимой процедуры для создания возвращающей табличное значение функции</span><span class="sxs-lookup"><span data-stu-id="1ce09-125">Calling a Stored Procedure to Create the Table-valued Function</span></span>  
 <span data-ttu-id="1ce09-126">Самый быстрый и простой способ создания функций с табличным значением — вызов системной хранимой процедуры **sys.sp_cdc_generate_wrapper_function** .</span><span class="sxs-lookup"><span data-stu-id="1ce09-126">The quickest and easiest way to create the table-valued functions that you need is to call the **sys.sp_cdc_generate_wrapper_function** system stored procedure.</span></span> <span data-ttu-id="1ce09-127">Хранимая процедура формирует скрипты для создания функций-оболочек, построенных специально с учетом требований компонента источника служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ce09-127">This stored procedure generates scripts to create wrapper functions that are designed specifically to meet the needs of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1ce09-128">Системная хранимая процедура **sys.sp_cdc_generate_wrapper_function** не создает функции-оболочки напрямую.</span><span class="sxs-lookup"><span data-stu-id="1ce09-128">The **sys.sp_cdc_generate_wrapper_function** system stored procedure does not directly create the wrapper functions.</span></span> <span data-ttu-id="1ce09-129">Вместо этого она создает скрипты CREATE для функций-оболочек.</span><span class="sxs-lookup"><span data-stu-id="1ce09-129">Instead, the stored procedure generates the CREATE scripts for the wrapper functions.</span></span> <span data-ttu-id="1ce09-130">Разработчик должен запустить созданные хранимой процедурой скрипты CREATE, прежде чем добавочный пакет загрузки сможет вызывать эти функции-оболочки.</span><span class="sxs-lookup"><span data-stu-id="1ce09-130">The developer must run the CREATE scripts that the stored procedure generates before an incremental load package can call the wrapper functions.</span></span>  
  
 <span data-ttu-id="1ce09-131">Чтобы понять, как использовать хранимую процедуру, следует понять, что она делает, какие скрипты создает и какие функции-оболочки создаются этими скриптами.</span><span class="sxs-lookup"><span data-stu-id="1ce09-131">To understand how to use this system stored procedure, you should understand what the procedure does, what scripts the procedure generates, and what wrapper functions the scripts create.</span></span>  
  
### <a name="understanding-and-using-the-stored-procedure"></a><span data-ttu-id="1ce09-132">Основные сведения о хранимой процедуре и ее использование</span><span class="sxs-lookup"><span data-stu-id="1ce09-132">Understanding and Using the Stored Procedure</span></span>  
 <span data-ttu-id="1ce09-133">Системная хранимая процедура **sys.sp_cdc_generate_wrapper_function** формирует скрипты для создания функций-оболочек, используемых пакетами служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ce09-133">The **sys.sp_cdc_generate_wrapper_function** system stored procedure generates scripts to create wrapper functions for use by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="1ce09-134">Ниже приведены первые несколько строк определения хранимой процедуры:</span><span class="sxs-lookup"><span data-stu-id="1ce09-134">Here are the first few lines of the definition of the stored procedure:</span></span>  
  
 `CREATE PROCEDURE sys.sp_cdc_generate_wrapper_function`  
  
 `(`  
  
 `@capture_instance sysname = null`  
  
 `@closed_high_end_point bit = 1,`  
  
 `@column_list = null,`  
  
 `@update_flag_list = null`  
  
 `)`  
  
 <span data-ttu-id="1ce09-135">Все параметры для хранимой процедуры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="1ce09-135">All the parameters for the stored procedure are optional.</span></span> <span data-ttu-id="1ce09-136">Если вызвать хранимую процедуру, не указывая какие-либо параметры, процедура создаст функцию-оболочку для всех экземпляров системы отслеживания, к которым пользователь имеет доступ.</span><span class="sxs-lookup"><span data-stu-id="1ce09-136">If you call the stored procedure without supplying values for any of the parameters, the stored procedure creates wrapper functions for all the capture instances to which you have access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ce09-137">Дополнительные сведения о синтаксисе этой хранимой процедуры и ее параметрах см. в разделе [sys.sp_cdc_generate_wrapper_function (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ce09-137">For more information about the syntax of this stored procedure and its parameters, see [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span></span>  
  
 <span data-ttu-id="1ce09-138">Хранимая процедура всегда создает функцию-оболочку для возвращения всех изменений из каждого экземпляра системы отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ce09-138">The stored procedure always generates a wrapper function to return all changes from each capture instance.</span></span> <span data-ttu-id="1ce09-139">Если *@supports_net_changes* параметр был задан при создании экземпляра системы отслеживания, то хранимая процедура также создает функцию-оболочку для возврата суммарных изменений из каждого применимого экземпляра системы отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ce09-139">If the *@supports_net_changes* parameter was set when the capture instance was created, the stored procedure also generates a wrapper function to return net changes from each applicable capture instance.</span></span>  
  
 <span data-ttu-id="1ce09-140">Хранимая процедура возвращает результирующий набор с двумя столбцами.</span><span class="sxs-lookup"><span data-stu-id="1ce09-140">The stored procedure returns a result set with two columns:</span></span>  
  
-   <span data-ttu-id="1ce09-141">Имя функции-оболочки, созданной хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="1ce09-141">The name of the wrapper function that the stored procedure has generated.</span></span> <span data-ttu-id="1ce09-142">Эта хранимая процедура присваивает функции имя на основе имени экземпляра системы отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ce09-142">This stored procedure derives the function name from the name of the capture instance name.</span></span> <span data-ttu-id="1ce09-143">Имя функции состоит из префикса «fn_all_changes_», за которым следует имя экземпляра системы отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ce09-143">(The function name is 'fn_all_changes_' followed by the capture instance name.</span></span> <span data-ttu-id="1ce09-144">Для функции суммарных изменений используется префикс «fn_net_changes_».</span><span class="sxs-lookup"><span data-stu-id="1ce09-144">The prefix used for the net changes function, if it is created, is 'fn_net_changes_'.)</span></span>  
  
-   <span data-ttu-id="1ce09-145">Инструкция CREATE для функции-оболочки.</span><span class="sxs-lookup"><span data-stu-id="1ce09-145">The CREATE statement for the wrapper function.</span></span>  
  
### <a name="understanding-and-using-the-scripts-created-by-the-stored-procedure"></a><span data-ttu-id="1ce09-146">Основные сведения о скриптах, созданных хранимой процедурой, и их использование</span><span class="sxs-lookup"><span data-stu-id="1ce09-146">Understanding and Using the Scripts Created by the Stored Procedure</span></span>  
 <span data-ttu-id="1ce09-147">Обычно для вызова хранимой процедуры **sys.sp_cdc_generate_wrapper_function** используется инструкция INSERT...EXEC, а созданные процедурой скрипты сохраняются во временной таблице.</span><span class="sxs-lookup"><span data-stu-id="1ce09-147">Typically, a developer would use an INSERT...EXEC statement to call the **sys.sp_cdc_generate_wrapper_function** stored procedure and save the scripts that the stored procedure creates to a temporary table.</span></span> <span data-ttu-id="1ce09-148">Затем каждый скрипт можно выбрать отдельно и создать с его помощью соответствующую функцию-оболочку.</span><span class="sxs-lookup"><span data-stu-id="1ce09-148">Each script could then be individually selected and run to create the corresponding wrapper function.</span></span> <span data-ttu-id="1ce09-149">Однако разработчик также может воспользоваться набором команд SQL для запуска всех скриптов CREATE, как показано в приведенном ниже образце кода:</span><span class="sxs-lookup"><span data-stu-id="1ce09-149">However, a developer could also use one set of SQL commands to run all the CREATE scripts, as shown in the following sample code:</span></span>  
  
```  
create table #wrapper_functions  
      (function_name sysname, create_stmt nvarchar(max))  
insert into #wrapper_functions  
exec sys.sp_cdc_generate_wrapper_function  
  
declare @stmt nvarchar(max)  
declare #hfunctions cursor local fast_forward for   
      select create_stmt from #wrapper_functions  
open #hfunctions  
fetch #hfunctions into @stmt  
while (@@fetch_status <> -1)  
begin  
      exec sp_executesql @stmt  
      fetch #hfunctions into @stmt  
end  
close #hfunctions  
deallocate #hfunctions  
```  
  
### <a name="understanding-and-using-the-functions-created-by-the-stored-procedure"></a><span data-ttu-id="1ce09-150">Основные сведения о функциях, созданных хранимой процедурой, и их использование</span><span class="sxs-lookup"><span data-stu-id="1ce09-150">Understanding and Using the Functions Created by the Stored Procedure</span></span>  
 <span data-ttu-id="1ce09-151">Для систематического анализа временной шкалы захваченных данных изменений созданные функции-оболочки предполагают, что *@end_time* параметр для одного интервала будет *@start_time* параметром для следующего интервала.</span><span class="sxs-lookup"><span data-stu-id="1ce09-151">To systematically walk the timeline of captured change data, the generated wrapper functions expect that the *@end_time* parameter for one interval will be the *@start_time* parameter for the subsequent interval.</span></span> <span data-ttu-id="1ce09-152">Если это условие выполняется, созданные функции-оболочки могут выполнять следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="1ce09-152">When this convention is followed, the generated wrapper functions can do the following tasks:</span></span>  
  
-   <span data-ttu-id="1ce09-153">Сопоставлять значения даты-времени со значениями номеров LSN, используемых внутри функций.</span><span class="sxs-lookup"><span data-stu-id="1ce09-153">Map the date/time values to the LSN values that are used internally.</span></span>  
  
-   <span data-ttu-id="1ce09-154">Гарантировать, что никакие данные не потеряны и не повторяются.</span><span class="sxs-lookup"><span data-stu-id="1ce09-154">Ensure that no data is lost or repeated.</span></span>  
  
 <span data-ttu-id="1ce09-155">Чтобы упростить запросы ко всем строкам таблицы изменений, функции-оболочки также поддерживают следующие соглашения.</span><span class="sxs-lookup"><span data-stu-id="1ce09-155">To make querying for all rows of a change table simpler, the generated wrapper functions also support the following conventions:</span></span>  
  
-   <span data-ttu-id="1ce09-156">Если параметр @start_time имеет значение NULL, функции-оболочки используют наименьшее значение номера LSN в экземпляре системы отслеживания в качестве нижней границы запроса.</span><span class="sxs-lookup"><span data-stu-id="1ce09-156">If the @start_time parameter is null, the wrapper functions use the lowest LSN value in the capture instance as the lower bound of the query.</span></span>  
  
-   <span data-ttu-id="1ce09-157">Если параметр @end_time имеет значение NULL, функции-оболочки используют наибольшее значение номера LSN в экземпляре системы отслеживания в качестве верхней границы запроса.</span><span class="sxs-lookup"><span data-stu-id="1ce09-157">If the @end_time parameter is null, the wrapper functions use the highest LSN value in the capture instance as the upper bound of the query.</span></span>  
  
 <span data-ttu-id="1ce09-158">Большинство пользователей смогут использовать функции-оболочки, созданные хранимой процедурой **sys.sp_cdc_generate_wrapper_function** , без изменений.</span><span class="sxs-lookup"><span data-stu-id="1ce09-158">Most users should be able to use the wrapper functions that the **sys.sp_cdc_generate_wrapper_function** system stored procedure creates without modification.</span></span> <span data-ttu-id="1ce09-159">Однако, чтобы настроить эти функции-оболочки, перед запуском скриптов CREATE необходимо их настроить.</span><span class="sxs-lookup"><span data-stu-id="1ce09-159">However, to customize the wrapper functions, you have to customize the CREATE scripts before you run the scripts.</span></span>  
  
 <span data-ttu-id="1ce09-160">При вызове пакетом функции-оболочки он должен передать значения для трех параметров.</span><span class="sxs-lookup"><span data-stu-id="1ce09-160">When your package calls the wrapper functions, the package must supply values for three parameters.</span></span> <span data-ttu-id="1ce09-161">Эти три параметра похожи на три параметра, используемые функциями системы отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="1ce09-161">These three parameters are like the three parameters that the change data capture functions use.</span></span> <span data-ttu-id="1ce09-162">Это следующие три параметра.</span><span class="sxs-lookup"><span data-stu-id="1ce09-162">These three parameters are as follows:</span></span>  
  
-   <span data-ttu-id="1ce09-163">Значения даты-времени начала и окончания интервала.</span><span class="sxs-lookup"><span data-stu-id="1ce09-163">The starting date/time value and the ending date/time value for the interval.</span></span> <span data-ttu-id="1ce09-164">В то время как функции-оболочки используют значения даты-времени в качестве конечных точек для интервала запроса, функции системы отслеживания измененных данных используют в качестве двух конечных точек два номера LSN.</span><span class="sxs-lookup"><span data-stu-id="1ce09-164">While the wrapper functions use date/time values as the end points for the query interval, the change data capture functions use two LSN values as the end points.</span></span>  
  
-   <span data-ttu-id="1ce09-165">Фильтр строк.</span><span class="sxs-lookup"><span data-stu-id="1ce09-165">The row filter.</span></span> <span data-ttu-id="1ce09-166">Для функций-оболочек и функций системы отслеживания измененных данных параметр совпадает *@row_filter_option* .</span><span class="sxs-lookup"><span data-stu-id="1ce09-166">For both the wrapper functions and the change data capture functions, the *@row_filter_option* parameter is the same.</span></span> <span data-ttu-id="1ce09-167">Дополнительные сведения см. в разделах [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  (Transact-SQL)](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) и [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; (Transact-SQL)](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ce09-167">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) and [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="1ce09-168">Результирующий набор, возвращаемый функциями-оболочками, включает следующие данные.</span><span class="sxs-lookup"><span data-stu-id="1ce09-168">The result set returned by the wrapper functions includesthe following data:</span></span>  
  
-   <span data-ttu-id="1ce09-169">Все запрошенные столбцы информации об изменениях.</span><span class="sxs-lookup"><span data-stu-id="1ce09-169">All of the requested columns of change data.</span></span>  
  
-   <span data-ttu-id="1ce09-170">Столбец с именем __CDC_OPERATION, в котором используется одно- или двухсимвольное поле, идентифицирующее операцию, связанную со строкой.</span><span class="sxs-lookup"><span data-stu-id="1ce09-170">A column named __CDC_OPERATION that uses a one- or two-character field to identify the operation that is associated with the row.</span></span> <span data-ttu-id="1ce09-171">Для этого поля допустимы следующие значения: "I" — вставка, "D" — удаление, "UO" — обновление старых значений, "UN" — обновление новых значений.</span><span class="sxs-lookup"><span data-stu-id="1ce09-171">The valid values for this field are as follows: 'I' for insert, 'D' for delete, 'UO' for update old values, and 'UN' for update new values.</span></span>  
  
-   <span data-ttu-id="1ce09-172">Флаги обновления. при запросе они отображаются как битовые столбцы после кода операции и в порядке, указанном в *@update_flag_list* параметре.</span><span class="sxs-lookup"><span data-stu-id="1ce09-172">Update flags, when you request them, that appear as bit columns after the operation code and in the order that is specified in the *@update_flag_list* parameter.</span></span> <span data-ttu-id="1ce09-173">Имена этим столбцам присваиваются путем добавления "_uflag" к имени соответствующего столбца.</span><span class="sxs-lookup"><span data-stu-id="1ce09-173">These columns are named by appending '_uflag' to the associated column name.</span></span>  
  
 <span data-ttu-id="1ce09-174">Если пакет вызывает функцию-оболочку, которая запрашивает все изменения, эта функция также возвращает столбцы __CDC_STARTLSN и \__CDC_SEQVAL.</span><span class="sxs-lookup"><span data-stu-id="1ce09-174">If your package calls a wrapper function that queries for all changes, the wrapper function also returns the columns, __CDC_STARTLSN and \__CDC_SEQVAL.</span></span> <span data-ttu-id="1ce09-175">Эти два столбца становятся соответственно первым и вторым в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="1ce09-175">These two columns become the first and second columns, respectively, of the result set.</span></span> <span data-ttu-id="1ce09-176">Функция-оболочка также сортирует результирующий набор на основе этих двух столбцов.</span><span class="sxs-lookup"><span data-stu-id="1ce09-176">The wrapper function also sorts the result set based on these two columns.</span></span>  
  
## <a name="writing-your-own-table-value-function"></a><span data-ttu-id="1ce09-177">Написание собственной функции, возвращающей табличное значение</span><span class="sxs-lookup"><span data-stu-id="1ce09-177">Writing Your Own Table-Value Function</span></span>  
 <span data-ttu-id="1ce09-178">Также можно использовать среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], чтобы написать функцию-оболочку с табличным значением, которая вызывает функцию запроса системы отслеживания измененных данных, и сохранить эту функцию-оболочку с табличным значением в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ce09-178">You can also use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to write your own table-valued wrapper function that calls the change data capture query function, and store the table-valued wrapper function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1ce09-179">Дополнительные сведения о создании функций Transact-SQL см. в разделе [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ce09-179">For more information about how to create a Transact-SQL function, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
 <span data-ttu-id="1ce09-180">В следующем примере определяется возвращающая табличное значение функция, которая получает из таблицы Customer данные об изменениях за указанный период изменений.</span><span class="sxs-lookup"><span data-stu-id="1ce09-180">The following example defines a table-valued function that retrieves changes from a Customer table for the specified change interval.</span></span> <span data-ttu-id="1ce09-181">Эта функция применяет систему отслеживания измененных данных для сопоставления значений `datetime` с двоичными значениями регистрационных номеров транзакций в журнале (номеров LSN), которые используются внутренними механизмами таблиц изменений.</span><span class="sxs-lookup"><span data-stu-id="1ce09-181">This function uses change data capture functions to map the `datetime` values to the binary log sequence number (LSN) values that the change tables use internally.</span></span> <span data-ttu-id="1ce09-182">Кроме того, эта функция обрабатывает некоторые особые ситуации.</span><span class="sxs-lookup"><span data-stu-id="1ce09-182">This function also handles several special conditions:</span></span>  
  
-   <span data-ttu-id="1ce09-183">Если для времени начала передается значение NULL, функция использует самое раннее из доступных значений.</span><span class="sxs-lookup"><span data-stu-id="1ce09-183">When a null value is passed for the starting time, this function uses the earliest available value.</span></span>  
  
-   <span data-ttu-id="1ce09-184">Если для времени окончания передается значение NULL, функция использует самое позднее из доступных значений.</span><span class="sxs-lookup"><span data-stu-id="1ce09-184">When a null value is passed for the ending time, this function uses the latest available value.</span></span>  
  
-   <span data-ttu-id="1ce09-185">Если начальное значение номера LSN равняется конечному значению номера LSN, что обычно указывает на отсутствие записей в выбранном интервале времени, выполнение этой функции прекращается.</span><span class="sxs-lookup"><span data-stu-id="1ce09-185">When the starting LSN is equal to the ending LSN, which usually indicates that there are no records for the selected interval, this function exits.</span></span>  
  
### <a name="example-of-a-table-value-function-that-queries-for-change-data"></a><span data-ttu-id="1ce09-186">Пример возвращающей табличное значение функции, запрашивающей измененные данные</span><span class="sxs-lookup"><span data-stu-id="1ce09-186">Example of a Table-Value Function that Queries for Change Data</span></span>  
  
```  
CREATE function CDCSample.uf_Customer (  
     @start_time datetime  
    ,@end_time datetime  
)  
returns @Customer table (  
     CustomerID int  
    ,TerritoryID int  
    ,CustomerType nchar(1)  
    ,rowguid uniqueidentifier  
    ,ModifiedDate datetime  
    ,CDC_OPERATION varchar(1)  
) as  
begin  
    declare @from_lsn binary(10), @to_lsn binary(10)  
  
    if (@start_time is null)  
        select @from_lsn = sys.fn_cdc_get_min_lsn('Customer')  
    else  
        select @from_lsn = sys.fn_cdc_increment_lsn(sys.fn_cdc_map_time_to_lsn('largest less than or equal',@start_time))  
  
    if (@end_time is null)  
        select @to_lsn = sys.fn_cdc_get_max_lsn()  
    else  
        select @to_lsn = sys.fn_cdc_map_time_to_lsn('largest less than or equal',@end_time)  
  
    if (@from_lsn = sys.fn_cdc_increment_lsn(@to_lsn))  
        return  
  
    -- Query for change data  
    insert into @Customer  
    select   
        CustomerID,      
        TerritoryID,   
        CustomerType,   
        rowguid,   
        ModifiedDate,   
        case __$operation  
                when 1 then 'D'  
                when 2 then 'I'  
                when 4 then 'U'  
                else null  
         end as CDC_OPERATION  
    from   
        cdc.fn_cdc_get_net_changes_Customer(@from_lsn, @to_lsn, 'all')  
  
    return  
end   
go  
  
```  
  
### <a name="retrieving-additional-metadata-with-the-change-data"></a><span data-ttu-id="1ce09-187">Получение дополнительных метаданных с помощью информации об изменениях</span><span class="sxs-lookup"><span data-stu-id="1ce09-187">Retrieving Additional Metadata with the Change Data</span></span>  
 <span data-ttu-id="1ce09-188">Показанная ранее пользовательская функция с табличным значением использует только столбец **__$operation**, но функция **cdc.fn_cdc_get_net_changes_<capture_instance>** возвращает четыре столбца метаданных для каждой строки изменений.</span><span class="sxs-lookup"><span data-stu-id="1ce09-188">Although the user-created table-valued function shown earlier uses only the **__$operation** column, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns four columns of metadata for each change row.</span></span> <span data-ttu-id="1ce09-189">Если нужно использовать эти значения в потоке данных, можете возвратить их как дополнительные столбцы с помощью возвращающей табличное значение функции оболочки.</span><span class="sxs-lookup"><span data-stu-id="1ce09-189">If you want to use these values in your data flow, you can return them as additional columns from the table-valued wrapper function.</span></span>  
  
|<span data-ttu-id="1ce09-190">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="1ce09-190">Column name</span></span>|<span data-ttu-id="1ce09-191">Тип данных</span><span class="sxs-lookup"><span data-stu-id="1ce09-191">Data type</span></span>|<span data-ttu-id="1ce09-192">Описание</span><span class="sxs-lookup"><span data-stu-id="1ce09-192">Description</span></span>|  
|-----------------|---------------|-----------------|  
|<span data-ttu-id="1ce09-193">**__$start_lsn**</span><span class="sxs-lookup"><span data-stu-id="1ce09-193">**__$start_lsn**</span></span>|`binary(10)`|<span data-ttu-id="1ce09-194">Номер LSN, связанный с фиксацией транзакции изменения.</span><span class="sxs-lookup"><span data-stu-id="1ce09-194">LSN associated with the commit transaction for the change.</span></span><br /><br /> <span data-ttu-id="1ce09-195">Все изменения, зафиксированные в одной транзакции, имеют общий номер LSN фиксации.</span><span class="sxs-lookup"><span data-stu-id="1ce09-195">All changes committed in the same transaction share the same commit LSN.</span></span> <span data-ttu-id="1ce09-196">Например, если операция обновления в исходной таблице изменяет две различные строки, таблица изменений будет содержать четыре строки (две со старыми значениями и две с новыми), каждая с одним и тем же значением **__$start_lsn** .</span><span class="sxs-lookup"><span data-stu-id="1ce09-196">For example, if an update operation on the source table modifies two different rows, the change table will contain four rows (two with the old values and two with the new values), each with the same **__$start_lsn** value.</span></span>|  
|<span data-ttu-id="1ce09-197">**__$seqval**</span><span class="sxs-lookup"><span data-stu-id="1ce09-197">**__$seqval**</span></span>|`binary(10)`|<span data-ttu-id="1ce09-198">Значение последовательности, используемое для упорядочивания изменений строк в пределах транзакции.</span><span class="sxs-lookup"><span data-stu-id="1ce09-198">Sequence value that is used to order the row changes in a transaction.</span></span>|  
|<span data-ttu-id="1ce09-199">**__$operation**</span><span class="sxs-lookup"><span data-stu-id="1ce09-199">**__$operation**</span></span>|`int`|<span data-ttu-id="1ce09-200">Операция языка обработки данных (DML), связанная с изменением.</span><span class="sxs-lookup"><span data-stu-id="1ce09-200">The data manipulation language (DML) operation associated with the change.</span></span> <span data-ttu-id="1ce09-201">Может применяться один из перечисленных ниже типов.</span><span class="sxs-lookup"><span data-stu-id="1ce09-201">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="1ce09-202">1 = удаление</span><span class="sxs-lookup"><span data-stu-id="1ce09-202">1 = delete</span></span><br /><br /> <span data-ttu-id="1ce09-203">2 = вставка</span><span class="sxs-lookup"><span data-stu-id="1ce09-203">2 = insert</span></span><br /><br /> <span data-ttu-id="1ce09-204">3 = обновление (Значения перед операцией обновления.)</span><span class="sxs-lookup"><span data-stu-id="1ce09-204">3 = update (Values before the update operation.)</span></span><br /><br /> <span data-ttu-id="1ce09-205">4 = обновление (Значения после операции обновления.)</span><span class="sxs-lookup"><span data-stu-id="1ce09-205">4 = update (Values after the update operation.)</span></span>|  
|<span data-ttu-id="1ce09-206">**__$update_mask**</span><span class="sxs-lookup"><span data-stu-id="1ce09-206">**__$update_mask**</span></span>|`varbinary(128)`|<span data-ttu-id="1ce09-207">Битовая маска, основанная на порядковых номерах столбцов в таблице изменений, идентифицирующих эти измененные столбцы.</span><span class="sxs-lookup"><span data-stu-id="1ce09-207">A bitmask that is based on the column ordinals of the change table identifying those columns that changed.</span></span> <span data-ttu-id="1ce09-208">Это значение можно проанализировать, если необходимо установить, какие столбцы были изменены.</span><span class="sxs-lookup"><span data-stu-id="1ce09-208">You could examine this value if you had to determine which columns have changed.</span></span>|  
|**\<captured source table columns>**|<span data-ttu-id="1ce09-209">непостоянно</span><span class="sxs-lookup"><span data-stu-id="1ce09-209">varies</span></span>|<span data-ttu-id="1ce09-210">Остальные столбцы, возвращенные функцией, — это столбцы из исходной таблицы, определенные как отслеживаемые при создании экземпляра отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1ce09-210">The remaining columns returned by the function are the columns from the source table that were identified as captured columns when the capture instance was created.</span></span> <span data-ttu-id="1ce09-211">Если в списке отслеживаемых столбцов первоначально не было указано ни одного столбца, возвращаются все столбцы исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="1ce09-211">If no columns were originally specified in the captured column list, all columns in the source table are returned.</span></span>|  
  
 <span data-ttu-id="1ce09-212">Дополнительные сведения см. в разделе [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; (Transact-SQL)](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ce09-212">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="1ce09-213">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="1ce09-213">Next Step</span></span>  
 <span data-ttu-id="1ce09-214">После создания возвращающей табличное значение функции, запрашивающей измененные данные, начинается проектирование потока данных в пакете.</span><span class="sxs-lookup"><span data-stu-id="1ce09-214">After you have created the table-valued function that queries for change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="1ce09-215">**Следующая статья:** [Получение и интерпретация информации об изменениях данных](retrieve-and-understand-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="1ce09-215">**Next topic:** [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md)</span></span>  
  
  
