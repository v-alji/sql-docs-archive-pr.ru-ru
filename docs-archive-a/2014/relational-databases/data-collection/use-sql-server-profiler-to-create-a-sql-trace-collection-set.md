---
title: Создание набора элементов сбора трассировки SQL (SQL Server Management Studio) с помощью SQL Server Profiler | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace collector set
ms.assetid: b6941dc0-50f5-475d-82eb-ce7c68117489
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e9c9514fef8069cef615d1480aad1e0acd1582cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667231"
---
# <a name="use-sql-server-profiler-to-create-a-sql-trace-collection-set-sql-server-management-studio"></a><span data-ttu-id="eb343-102">Использование приложения SQL Server Profiler для создания набора элементов сбора трассировки SQL (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="eb343-102">Use SQL Server Profiler to Create a SQL Trace Collection Set (SQL Server Management Studio)</span></span>
  <span data-ttu-id="eb343-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно использовать возможности серверной трассировки приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , чтобы экспортировать определение трассировки для создания набора элементов сбора, использующего общий тип сборщика трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="eb343-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] you can exploit the server-side trace capabilities of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to export a trace definition that you can use to create a collection set that uses the Generic SQL Trace collector type.</span></span> <span data-ttu-id="eb343-104">Этот процесс состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="eb343-104">There are two parts to this process:</span></span>  
  
1.  <span data-ttu-id="eb343-105">Создание и экспорт трассировки приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb343-105">Create and export a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace.</span></span>  
  
2.  <span data-ttu-id="eb343-106">Создание скрипта нового набора сбора на основе экспортированной трассировки.</span><span class="sxs-lookup"><span data-stu-id="eb343-106">Script a new collection set based on an exported trace.</span></span>  
  
 <span data-ttu-id="eb343-107">Сценарий следующих процедур включает сбор данных о любой хранимой процедуре, требующей для выполнения 80 миллисекунд и более.</span><span class="sxs-lookup"><span data-stu-id="eb343-107">The scenario for the following procedures involves collecting data about any stored procedure that requires 80 milliseconds or longer to complete.</span></span> <span data-ttu-id="eb343-108">Для выполнения этих процедур необходимо уметь следующее.</span><span class="sxs-lookup"><span data-stu-id="eb343-108">In order to complete these procedures you should be able to:</span></span>  
  
-   <span data-ttu-id="eb343-109">Использовать приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] для создания и настройки трассировки.</span><span class="sxs-lookup"><span data-stu-id="eb343-109">Use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create and configure a trace.</span></span>  
  
-   <span data-ttu-id="eb343-110">Использовать среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для открытия, изменения и выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="eb343-110">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to open, edit, and execute a query.</span></span>  
  
### <a name="create-and-export-a-sql-server-profiler-trace"></a><span data-ttu-id="eb343-111">Создание и экспорт трассировки приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="eb343-111">Create and export a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="eb343-112">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb343-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="eb343-113">(В меню **Инструменты** выберите приложение **SQL Server Profiler**.)</span><span class="sxs-lookup"><span data-stu-id="eb343-113">(On the **Tools** menu, click **SQL Server Profiler**.)</span></span>  
  
2.  <span data-ttu-id="eb343-114">В диалоговом окне **Соединения с сервером** нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="eb343-114">In the **Connect to Server** dialog box, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="eb343-115">В данном случае убедитесь, что настроено отображение значений продолжительности в миллисекундах (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="eb343-115">For this scenario, ensure that duration values are configured to display in milliseconds (the default).</span></span> <span data-ttu-id="eb343-116">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="eb343-116">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="eb343-117">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="eb343-117">On the **Tools** menu, click **Options**.</span></span>  
  
    2.  <span data-ttu-id="eb343-118">Убедитесь, что в области **Параметры отображения** флажок «Показывать значения в столбце "Продолжительность" в микросекундах» не установлен.</span><span class="sxs-lookup"><span data-stu-id="eb343-118">In the **Display Options** area, ensure that the Show values in Duration column in microseconds check box is cleared.</span></span>  
  
    3.  <span data-ttu-id="eb343-119">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Общие параметры** .</span><span class="sxs-lookup"><span data-stu-id="eb343-119">Click **OK** to close the **General Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="eb343-120">В меню **Файл** выберите **Создать трассировку**.</span><span class="sxs-lookup"><span data-stu-id="eb343-120">On the **File** menu, click **New Trace**.</span></span>  
  
5.  <span data-ttu-id="eb343-121">В диалоговом окне **Подключение к серверу** выберите нужный сервер и нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="eb343-121">In the **Connect to Server** dialog box, select the server that you want to connect to, and then click **Connect**.</span></span>  
  
     <span data-ttu-id="eb343-122">отображается диалоговое окно **Свойства трассировки** .</span><span class="sxs-lookup"><span data-stu-id="eb343-122">The **Trace Properties** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="eb343-123">На вкладке **Общие** выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="eb343-123">On the **General** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="eb343-124">В поле **Имя трассировки** введите требуемое имя трассировки.</span><span class="sxs-lookup"><span data-stu-id="eb343-124">In the **Trace name** box, type the name that you want to use for the trace.</span></span> <span data-ttu-id="eb343-125">В этом примере используется имя `SPgt80`.</span><span class="sxs-lookup"><span data-stu-id="eb343-125">For this example, the trace name is `SPgt80`.</span></span>  
  
    2.  <span data-ttu-id="eb343-126">В списке **Использовать шаблон**выберите шаблон для трассировки.</span><span class="sxs-lookup"><span data-stu-id="eb343-126">In the **Use the template list**, select the template to use for the trace.</span></span> <span data-ttu-id="eb343-127">В этом примере выберите **TSQL_SPs**.</span><span class="sxs-lookup"><span data-stu-id="eb343-127">For this example, click **TSQL_SPs**.</span></span>  
  
7.  <span data-ttu-id="eb343-128">На вкладке **Выбор событий** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="eb343-128">On the **Events Selection** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="eb343-129">Определите события для трассировки.</span><span class="sxs-lookup"><span data-stu-id="eb343-129">Identify the events to use for the trace.</span></span> <span data-ttu-id="eb343-130">Например, снимите все флажки в столбце **События** , кроме **ExistingConnection** и **SP:Completed**.</span><span class="sxs-lookup"><span data-stu-id="eb343-130">For this example, clear all check boxes in the **Events** column, except for **ExistingConnection** and **SP:Completed**.</span></span>  
  
    2.  <span data-ttu-id="eb343-131">В правом нижнем углу установите флажок **Показать все столбцы** .</span><span class="sxs-lookup"><span data-stu-id="eb343-131">In the lower-right corner, select the **Show all columns** check box.</span></span>  
  
    3.  <span data-ttu-id="eb343-132">Щелкните строку **SP:Completed** .</span><span class="sxs-lookup"><span data-stu-id="eb343-132">Click the **SP:Completed** row.</span></span>  
  
    4.  <span data-ttu-id="eb343-133">Прокрутите строку до столбца **Продолжительность** и установите флажок **Продолжительность** .</span><span class="sxs-lookup"><span data-stu-id="eb343-133">Scroll across the row to the **Duration** column, and then select the **Duration** check box.</span></span>  
  
8.  <span data-ttu-id="eb343-134">В правом нижнем углу щелкните **Фильтры столбцов** . Откроется диалоговое окно **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="eb343-134">In the lower-right corner, click **Column Filters** to open the **Edit Filter** dialog box.</span></span> <span data-ttu-id="eb343-135">В окне **Изменение фильтра** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="eb343-135">In the **Edit Filter** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="eb343-136">В списке фильтров выберите **Продолжительность:** .</span><span class="sxs-lookup"><span data-stu-id="eb343-136">In the filter list, click **Duration**.</span></span>  
  
    2.  <span data-ttu-id="eb343-137">В окне логический оператор разверните узел **больше или равно** , введите в `80` качестве значения и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb343-137">In the Boolean operator window, expand the **Greater than or equal** node, type `80` as the value, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="eb343-138">Чтобы запустить трассировку, нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="eb343-138">Click **Run** to start the trace.</span></span>  
  
10. <span data-ttu-id="eb343-139">На панели инструментов щелкните **Остановить выбранную трассировку** или **Приостановить выбранную трассировку**.</span><span class="sxs-lookup"><span data-stu-id="eb343-139">On the toolbar, click **Stop Selected Trace** or **Pause Selected Trace**.</span></span>  
  
11. <span data-ttu-id="eb343-140">В меню **Файл** укажите пункт **Экспорт**, затем **Создать определение трассировки**и щелкните **Для набора элементов сбора трассировки SQL**.</span><span class="sxs-lookup"><span data-stu-id="eb343-140">On the **File** menu, point to **Export**, point to **Script Trace Definition**, and then click **For SQL Trace Collection Set**.</span></span>  
  
12. <span data-ttu-id="eb343-141">В диалоговом окне **Сохранить как** введите имя определения трассировки в поле **Имя файла** и сохраните файл в требуемом расположении.</span><span class="sxs-lookup"><span data-stu-id="eb343-141">In the **Save As** dialog box, type the name that you want to use for the trace definition in the **File name** box, and then save it in the location that you want.</span></span> <span data-ttu-id="eb343-142">В данном примере имя файла совпадает с именем трассировки (SPgt80).</span><span class="sxs-lookup"><span data-stu-id="eb343-142">For this example, the file name is the same as the trace name (SPgt80).</span></span>  
  
13. <span data-ttu-id="eb343-143">Нажмите кнопку **ОК** при появлении сообщения об успешном сохранении файла и закройте приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb343-143">Click **OK** when you receive a message that the file was successfully saved, and then close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="script-a-new-collection-set-from-a-sql-server-profiler-trace"></a><span data-ttu-id="eb343-144">Создание скрипта нового набора элементов сбора из трассировки приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="eb343-144">Script a new collection set from a SQL Server Profiler trace</span></span>  
  
1.  <span data-ttu-id="eb343-145">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Файл** выберите команду **Открыть** , а затем **Файл**.</span><span class="sxs-lookup"><span data-stu-id="eb343-145">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, point to **Open,** and then click **File**.</span></span>  
  
2.  <span data-ttu-id="eb343-146">В диалоговом окне **Открытие файла** найдите и откройте файл, созданный в предыдущей процедуре (SPgt80).</span><span class="sxs-lookup"><span data-stu-id="eb343-146">In the **Open File** dialog box, locate and then open the file that you created in the previous procedure (SPgt80).</span></span>  
  
     <span data-ttu-id="eb343-147">Сохраненная информация о трассировке открывается в окне «Запрос» и объединяется в скрипт, который можно запустить для создания новых наборов элементов сбора.</span><span class="sxs-lookup"><span data-stu-id="eb343-147">The trace information that you saved is opened in a Query window and merged into a script that you can run to create the new collection set.</span></span>  
  
3.  <span data-ttu-id="eb343-148">Прокрутите скрипт и выполните следующие замены, отмеченные в текстовом комментарии скрипта.</span><span class="sxs-lookup"><span data-stu-id="eb343-148">Scroll through the script and make the following replacements, which are noted in the script comment text:</span></span>  
  
    -   <span data-ttu-id="eb343-149">Замените строку **Имя набора сбора SQLTrace** именем, которое будет использоваться для набора элементов сбора.</span><span class="sxs-lookup"><span data-stu-id="eb343-149">Replace **SQLTrace Collection Set Name Here** with the name that you want to use for the collection set.</span></span> <span data-ttu-id="eb343-150">В данном примере имя набора элементов сбора — `SPROC_CollectionSet`.</span><span class="sxs-lookup"><span data-stu-id="eb343-150">For this example, name the collection set `SPROC_CollectionSet`.</span></span>  
  
    -   <span data-ttu-id="eb343-151">Замените строку **Имя элемента сбора SQLTrace** именем, которое будет использоваться для элемента сбора.</span><span class="sxs-lookup"><span data-stu-id="eb343-151">Replace **SQLTrace Collection Item Name Here** with the name that you want to use for the collection item.</span></span> <span data-ttu-id="eb343-152">В данном примере имя элемента сбора — `SPROC_Collection_Item`.</span><span class="sxs-lookup"><span data-stu-id="eb343-152">For this example, name the collection item `SPROC_Collection_Item`.</span></span>  
  
4.  <span data-ttu-id="eb343-153">Нажмите кнопку **Выполнить** , чтобы запустить запрос и создать набор элементов сбора.</span><span class="sxs-lookup"><span data-stu-id="eb343-153">Click **Execute** to run the query and to create the collection set.</span></span>  
  
5.  <span data-ttu-id="eb343-154">В обозревателе объектов проверьте успешность создания набора элементов сбора.</span><span class="sxs-lookup"><span data-stu-id="eb343-154">In Object Explorer, verify that the collection set was created.</span></span> <span data-ttu-id="eb343-155">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="eb343-155">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="eb343-156">Щелкните правой кнопкой мыши узел **Управление**и выберите команду **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="eb343-156">Right-click **Management**, and then click **Refresh**.</span></span>  
  
    2.  <span data-ttu-id="eb343-157">Разверните узел **Управление**, затем **Сбор данных**.</span><span class="sxs-lookup"><span data-stu-id="eb343-157">Expand **Management**, and then expand **Data Collection**.</span></span>  
  
     <span data-ttu-id="eb343-158">`SPROC_CollectionSet`Набор сбора отображается на том же уровне, что и узел **наборы сбора системных данных** .</span><span class="sxs-lookup"><span data-stu-id="eb343-158">The `SPROC_CollectionSet` collection set appears at the same level as the **System Data Collection Sets** node.</span></span> <span data-ttu-id="eb343-159">По умолчанию этот набор элементов сбора отключен.</span><span class="sxs-lookup"><span data-stu-id="eb343-159">By default, the collection set is disabled.</span></span>  
  
6.  <span data-ttu-id="eb343-160">С помощью обозревателя объектов измените свойства набора SPROC_CollectionSet, например режим сбора и расписание передачи.</span><span class="sxs-lookup"><span data-stu-id="eb343-160">Use Object Explorer to edit the properties of SPROC_CollectionSet, such as the collection mode and upload schedule.</span></span> <span data-ttu-id="eb343-161">Остальные действия аналогичны тем, что выполнялись бы с наборами сбора системных данных, поставляемыми в составе поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="eb343-161">Follow the same procedures that you would for the System Data collection sets that are provided with the data collector.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb343-162">Пример</span><span class="sxs-lookup"><span data-stu-id="eb343-162">Example</span></span>  
 <span data-ttu-id="eb343-163">Следующий образец кода содержит скрипт, созданный в результате выполнения шагов, описанных в предыдущих процедурах.</span><span class="sxs-lookup"><span data-stu-id="eb343-163">The following code sample is the final script resulting from the steps documented in the preceding procedures.</span></span>  
  
```  
/*************************************************************/  
-- SQL Trace collection set generated from SQL Server Profiler  
-- Date: 11/19/2007  12:55:31 AM  
/*************************************************************/  
  
USE msdb  
GO  
  
BEGIN TRANSACTION  
BEGIN TRY  
  
-- Define collection set  
-- ***  
-- *** Replace 'SqlTrace Collection Set Name Here' in the   
-- *** following script with the name you want  
-- *** to use for the collection set.  
-- ***  
DECLARE @collection_set_id int;  
EXEC [dbo].[sp_syscollector_create_collection_set]  
    @name = N'SPROC_CollectionSet',  
    @schedule_name = N'CollectorSchedule_Every_15min',  
    @collection_mode = 0, -- cached mode needed for Trace collections  
    @logging_level = 0, -- minimum logging  
    @days_until_expiration = 5,  
    @description = N'Collection set generated by SQL Server Profiler',  
    @collection_set_id = @collection_set_id output;  
SELECT @collection_set_id;  
  
-- Define input and output variables for the collection item.  
DECLARE @trace_definition xml;  
DECLARE @collection_item_id int;  
  
-- Define the trace parameters as an XML variable  
SELECT @trace_definition = convert(xml,   
N'<ns:SqlTraceCollector xmlns:ns"DataCollectorType" use_default="0">  
<Events>  
  <EventType name="Sessions">  
    <Event id="17" name="ExistingConnection" columnslist="1,2,14,26,3,35,12" />  
  </EventType>  
  <EventType name="Stored Procedures">  
    <Event id="43" name="SP:Completed" columnslist="1,2,26,34,3,35,12,13,14,22" />  
  </EventType>  
</Events>  
<Filters>  
  <Filter columnid="13" columnname="Duration" logical_operator="AND" comparison_operator="GE" value="80000L" />  
</Filters>  
</ns:SqlTraceCollector>  
');  
  
-- Retrieve the collector type GUID for the trace collector type.  
DECLARE @collector_type_GUID uniqueidentifier;  
SELECT @collector_type_GUID = collector_type_uid FROM [dbo].[syscollector_collector_types] WHERE name = N'Generic SQL Trace Collector Type';  
  
-- Create the trace collection item.  
-- ***  
-- *** Replace 'SqlTrace Collection Item Name Here' in   
-- *** the following script with the name you want to  
-- *** use for the collection item.  
-- ***  
EXEC [dbo].[sp_syscollector_create_collection_item]  
   @collection_set_id = @collection_set_id,  
   @collector_type_uid = @collector_type_GUID,  
   @name = N'SPROC_Collection_Item',  
   @frequency = 900, -- specified the frequency for checking to see if trace is still running  
   @parameters = @trace_definition,  
   @collection_item_id = @collection_item_id output;  
SELECT @collection_item_id;  
  
COMMIT TRANSACTION;  
END TRY  
  
BEGIN CATCH  
ROLLBACK TRANSACTION;  
DECLARE @ErrorMessage nvarchar(4000);  
DECLARE @ErrorSeverity int;  
DECLARE @ErrorState int;  
DECLARE @ErrorNumber int;  
DECLARE @ErrorLine int;  
DECLARE @ErrorProcedure nvarchar(200);  
SELECT @ErrorLine = ERROR_LINE(),  
       @ErrorSeverity = ERROR_SEVERITY(),  
       @ErrorState = ERROR_STATE(),  
       @ErrorNumber = ERROR_NUMBER(),  
       @ErrorMessage = ERROR_MESSAGE(),  
       @ErrorProcedure = ISNULL(ERROR_PROCEDURE(), '-');  
RAISERROR (14684, @ErrorSeverity, 1 , @ErrorNumber, @ErrorSeverity, @ErrorState, @ErrorProcedure, @ErrorLine, @ErrorMessage);  
END CATCH;  
GO  
```  
  
  
