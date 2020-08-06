---
title: Применение изменений в назначении | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],applying changes
ms.assetid: 338a56db-cb14-4784-a692-468eabd30f41
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dd7ab93a299ffaab2259c3d462a5c0a69160ad5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669014"
---
# <a name="apply-the-changes-to-the-destination"></a><span data-ttu-id="ae759-102">Применение изменений в назначении</span><span class="sxs-lookup"><span data-stu-id="ae759-102">Apply the Changes to the Destination</span></span>
  <span data-ttu-id="ae759-103">В потоке данных пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , который выполняет добавочную загрузку информации об измененных данных, третьей и последней задачей является применение изменений к назначению.</span><span class="sxs-lookup"><span data-stu-id="ae759-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to apply the changes to your destination.</span></span> <span data-ttu-id="ae759-104">Один компонент потребуется для применения вставок, один — для применения обновлений и один — для применения удалений.</span><span class="sxs-lookup"><span data-stu-id="ae759-104">You will need one component to apply inserts, one to apply updates, and one to apply deletes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae759-105">Второй задачей в проектировании потока данных пакета, выполняющего добавочную загрузку информации об измененных данных, является разделение вставок, обновлений и удалений.</span><span class="sxs-lookup"><span data-stu-id="ae759-105">The second task in designing the data flow of a package that performs an incremental load of change data is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="ae759-106">Дополнительные сведения об этом компоненте см. в разделе [Обработка операций вставки, обновления и удаления](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="ae759-106">For more information about this component, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span> <span data-ttu-id="ae759-107">Описание общего процесса создания пакета, выполняющего добавочную загрузку информации об изменениях, см. в разделе [Система отслеживания измененных данных (SSIS)](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="ae759-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="applying-inserts"></a><span data-ttu-id="ae759-108">Применение вставок</span><span class="sxs-lookup"><span data-stu-id="ae759-108">Applying Inserts</span></span>  
 <span data-ttu-id="ae759-109">Для применения вставок используется назначение «OLE DB», поскольку новые строки не требуют специальной обработки.</span><span class="sxs-lookup"><span data-stu-id="ae759-109">To apply inserts, you use an OLE DB destination because the new rows do not require any special handling.</span></span>  
  
#### <a name="to-process-inserts-by-using-an-ole-db-destination"></a><span data-ttu-id="ae759-110">Обработка вставок с использованием назначения «OLE DB»</span><span class="sxs-lookup"><span data-stu-id="ae759-110">To process inserts by using an OLE DB Destination</span></span>  
  
1.  <span data-ttu-id="ae759-111">На вкладке **Поток данных** добавьте назначение «OLE DB».</span><span class="sxs-lookup"><span data-stu-id="ae759-111">On the **Data flow** tab, add an OLE DB destination.</span></span>  
  
2.  <span data-ttu-id="ae759-112">Соедините выход, содержащий вставки из преобразования «Условное разбиение», с назначением «OLE DB».</span><span class="sxs-lookup"><span data-stu-id="ae759-112">Connect the output that contains inserts from the Conditional Split transformation to the OLE DB destination.</span></span>  
  
3.  <span data-ttu-id="ae759-113">В **Редакторе назначения «OLE DB»** на странице **Диспетчер соединений** выберите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="ae759-113">In the **OLE DB Destination Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="ae759-114">Выберите или создайте диспетчер соединений «OLE DB» для целевой базы данных.</span><span class="sxs-lookup"><span data-stu-id="ae759-114">Select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
    2.  <span data-ttu-id="ae759-115">Выберите параметр **Режим доступа к данным** , а затем выберите целевую таблицу или введите инструкцию SQL, содержащую целевые столбцы.</span><span class="sxs-lookup"><span data-stu-id="ae759-115">Select a **Data access mode** option, and then select the destination table or enter a SQL statement that contains the destination columns.</span></span>  
  
4.  <span data-ttu-id="ae759-116">На странице **Сопоставления** в редакторе сопоставьте соответствующие столбцы из измененных данных со столбцами целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="ae759-116">On the **Mappings** page of the editor, map the appropriate columns from the change data to the destination table.</span></span>  
  
## <a name="applying-updates"></a><span data-ttu-id="ae759-117">Применение обновлений</span><span class="sxs-lookup"><span data-stu-id="ae759-117">Applying Updates</span></span>  
 <span data-ttu-id="ae759-118">Для применения обновлений используется преобразование «Команда OLE DB».</span><span class="sxs-lookup"><span data-stu-id="ae759-118">To apply updates, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="ae759-119">Это преобразование используется потому, что для обновления новыми значениями столбцов по одной строке за раз требуется параметризованная инструкция UPDATE.</span><span class="sxs-lookup"><span data-stu-id="ae759-119">You use this transformation because you have to use a parameterized UPDATE statement to update one row at a time with the new column values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae759-120">Для применения обновлений можно также использовать компоненты назначения.</span><span class="sxs-lookup"><span data-stu-id="ae759-120">You can also use destination components to apply updates.</span></span> <span data-ttu-id="ae759-121">Этот способ подразумевает использование компонентов назначения для сохранения строк в специально созданных временных таблицах.</span><span class="sxs-lookup"><span data-stu-id="ae759-121">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="ae759-122">Затем с помощью задач «Выполнение SQL» проводятся массовые операции обновления и удаления строк, перенося данные из временных таблиц в объекты целевой базы данных.</span><span class="sxs-lookup"><span data-stu-id="ae759-122">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-updates-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="ae759-123">Обработка обновлений с помощью преобразования «Команда OLE DB»</span><span class="sxs-lookup"><span data-stu-id="ae759-123">To process updates by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="ae759-124">На вкладке **Поток данных** добавьте преобразование «Команда OLE DB».</span><span class="sxs-lookup"><span data-stu-id="ae759-124">On the **Data flow** tab, add an OLE DB Command transformation.</span></span>  
  
2.  <span data-ttu-id="ae759-125">Соедините выход, содержащий обновления преобразования «Условное разбиение», с преобразованием «Команда OLE DB».</span><span class="sxs-lookup"><span data-stu-id="ae759-125">Connect the output that contains updates from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="ae759-126">В окне **Расширенный редактор команды OLE DB**на вкладке **Диспетчер соединений** выберите существующий или создайте новый диспетчер соединений OLE DB для целевой базы данных.</span><span class="sxs-lookup"><span data-stu-id="ae759-126">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
4.  <span data-ttu-id="ae759-127">В **Расширенном редакторе команды OLE DB**на вкладке **Свойства компонента** для **SqlCommand**введите параметризованную инструкцию UPDATE.</span><span class="sxs-lookup"><span data-stu-id="ae759-127">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab, for **SqlCommand**, enter a parameterized UPDATE statement.</span></span>  
  
     <span data-ttu-id="ae759-128">Например, инструкция UPDATE для таблицы «Заказчики» может иметь следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ae759-128">For example, an UPDATE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    update CDCSample.Customer  
    set TerritoryID  = ?,  
        CustomerType  = ?,  
        rowguid  = ?,  
        ModifiedDate  = ?  
    where CustomerID = ?  
  
    ```  
  
5.  <span data-ttu-id="ae759-129">На вкладке **Сопоставления столбцов** в редакторе сопоставьте соответствующие столбцы из измененных данных с параметрами инструкции UPDATE.</span><span class="sxs-lookup"><span data-stu-id="ae759-129">On the **Column Mappings** tab of the editor, map the appropriate columns from the change data to the parameters in the UPDATE statement.</span></span>  
  
## <a name="applying-deletes"></a><span data-ttu-id="ae759-130">Применение удалений</span><span class="sxs-lookup"><span data-stu-id="ae759-130">Applying Deletes</span></span>  
 <span data-ttu-id="ae759-131">Для применения удалений используется преобразование «Команда OLE DB».</span><span class="sxs-lookup"><span data-stu-id="ae759-131">To apply deletes, you use an OLE DB Command transformation.</span></span> <span data-ttu-id="ae759-132">Это преобразование используется потому, что для удаления по одной строке за раз на основании значения столбца, однозначно определяющего строку, требуется параметризованная инструкция UPDATE.</span><span class="sxs-lookup"><span data-stu-id="ae759-132">You use this transformation because you have to use a parameterized DELETE statement that deletes a single row at a time based on the column value that uniquely identifies the row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae759-133">Для применения удалений можно также использовать целевые компоненты.</span><span class="sxs-lookup"><span data-stu-id="ae759-133">You can also use destination components to apply deletes.</span></span> <span data-ttu-id="ae759-134">Этот способ подразумевает использование компонентов назначения для сохранения строк в специально созданных временных таблицах.</span><span class="sxs-lookup"><span data-stu-id="ae759-134">When using this approach, you use the destination components to save the rows to temporary tables that you create for this purpose.</span></span> <span data-ttu-id="ae759-135">Затем с помощью задач «Выполнение SQL» проводятся массовые операции обновления и удаления строк, перенося данные из временных таблиц в объекты целевой базы данных.</span><span class="sxs-lookup"><span data-stu-id="ae759-135">Then, you use Execute SQL tasks to perform bulk update and bulk delete operations against the destination from the temporary tables.</span></span>  
  
#### <a name="to-process-deletes-by-using-an-ole-db-command-transformation"></a><span data-ttu-id="ae759-136">Обработка удалений с помощью преобразования «Команда OLE DB»</span><span class="sxs-lookup"><span data-stu-id="ae759-136">To process deletes by using an OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="ae759-137">На вкладке **Поток данных** добавьте преобразование «Команда OLE DB» в поток данных.</span><span class="sxs-lookup"><span data-stu-id="ae759-137">On the **Data flow** tab, add an OLE DB Command transformation to the data flow.</span></span>  
  
2.  <span data-ttu-id="ae759-138">Соедините выход, содержащий удаления из преобразования «Условное разбиение», с преобразованием «Команда OLE DB».</span><span class="sxs-lookup"><span data-stu-id="ae759-138">Connect the output that contains deletes from the Conditional Split transformation to the OLE DB Command transformation.</span></span>  
  
3.  <span data-ttu-id="ae759-139">Откройте расширенный редактор, чтобы настроить преобразование.</span><span class="sxs-lookup"><span data-stu-id="ae759-139">Open the Advanced Editor to configure the transformation.</span></span>  
  
4.  <span data-ttu-id="ae759-140">В окне **Расширенный редактор команды OLE DB**на вкладке **Диспетчер соединений** выберите существующий или создайте новый диспетчер соединений OLE DB для целевой базы данных.</span><span class="sxs-lookup"><span data-stu-id="ae759-140">In the **Advanced Editor for OLE DB Command**, on the **Connection Manager** tab, select or create an OLE DB Connection Manager for the destination database.</span></span>  
  
5.  <span data-ttu-id="ae759-141">В **Расширенном редакторе команды OLE DB**на вкладке **Свойства компонента** редактора для **SqlCommand**введите параметризованную инструкцию DELETE.</span><span class="sxs-lookup"><span data-stu-id="ae759-141">In the **Advanced Editor for OLE DB Command**, on the **Component Properties** tab of the editor, for **SqlCommand**, enter a parameterized DELETE statement.</span></span>  
  
     <span data-ttu-id="ae759-142">Например, инструкция DELETE для таблицы «Заказчики» может иметь следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ae759-142">For example, a DELETE statement for a Customer table might have the following syntax:</span></span>  
  
    ```  
    delete from Customer where CustomerID = ?  
  
    ```  
  
6.  <span data-ttu-id="ae759-143">На вкладке **Сопоставления столбцов** в редакторе сопоставьте соответствующий столбец из измененных данных с параметром инструкции DELETE.</span><span class="sxs-lookup"><span data-stu-id="ae759-143">On the **Column Mappings** tab of the editor, map the appropriate column from the change data to the parameter in the DELETE statement.</span></span>  
  
## <a name="optimizing-inserts-and-updates-by-using-merge-functionality"></a><span data-ttu-id="ae759-144">Оптимизация вставок и обновлений с помощью функции MERGE</span><span class="sxs-lookup"><span data-stu-id="ae759-144">Optimizing Inserts and Updates by Using MERGE Functionality</span></span>  
 <span data-ttu-id="ae759-145">Обработку вставок и обновлений можно оптимизировать, объединив определенные параметры системы отслеживания измененных данных с помощью ключевого слова Transact-SQL MERGE.</span><span class="sxs-lookup"><span data-stu-id="ae759-145">You can optimize the processing of inserts and updates by combining certain change data capture options with the use of the Transact-SQL MERGE keyword.</span></span> <span data-ttu-id="ae759-146">Дополнительные сведения о ключевом слове MERGE см. в разделе [MERGE (Transact-SQL)](/sql/t-sql/statements/merge-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae759-146">For more information about the MERGE keyword, see [MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql).</span></span>  
  
 <span data-ttu-id="ae759-147">В инструкции Transact-SQL, получающей измененные данные, в качестве значения параметра *row_filter_option* при вызове функции **cdc.fn_cdc_get_net_changes_<экземпляр_отслеживания_изменений>** можно указать *all with merge*.</span><span class="sxs-lookup"><span data-stu-id="ae759-147">In the Transact-SQL statement that retrieves the change data, you can specify *all with merge* as the value of the *row_filter_option* parameter when you call the **cdc.fn_cdc_get_net_changes_<capture_instance>** function.</span></span> <span data-ttu-id="ae759-148">Эта система отслеживания измененных данных работает более эффективно, если не требуется дополнительная обработка для различения вставок и обновлений.</span><span class="sxs-lookup"><span data-stu-id="ae759-148">This change data capture function operates more efficiently when it does not have to perform the extra processing that is required to distinguish inserts from updates.</span></span> <span data-ttu-id="ae759-149">Если параметр получает значение *all with merge* , значение **__$operation** измененных данных равно 1 для удалений или 5 для изменений, вызванных вставками или обновлениями.</span><span class="sxs-lookup"><span data-stu-id="ae759-149">When you specify the *all with merge* parameter value, the **__$operation** value of the change data is 1 for deletes or 5 for changes that were caused by inserts or updates.</span></span> <span data-ttu-id="ae759-150">Дополнительные сведения о функции Transact-SQL, используемой для получения измененных данных, см. в разделе [Получение и интерпретация измененных данных](retrieve-and-understand-the-change-data.md). После получения изменений с параметром *all with merge* можно применить удаления и вывести оставшиеся строки во временную или промежуточную таблицу.</span><span class="sxs-lookup"><span data-stu-id="ae759-150">For more information about the Transact-SQL function that is used to retrieve the change data, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).After retrieving changes with the *all with merge* parameter value, you can apply deletes, and output the remaining rows to a temporary table or a staging table.</span></span> <span data-ttu-id="ae759-151">Затем в нисходящей задаче «Выполнение SQL» можно использовать одну инструкцию MERGE для применения всех вставок или обновлений из промежуточной таблицы к назначению.</span><span class="sxs-lookup"><span data-stu-id="ae759-151">Then, in a downstream Execute SQL Task, you can use a single MERGE statement to apply all the inserts or updates from the staging table to the destination.</span></span>  
  
  
