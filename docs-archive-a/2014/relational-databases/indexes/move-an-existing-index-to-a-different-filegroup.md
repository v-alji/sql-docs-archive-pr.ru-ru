---
title: Перемещение существующего индекса в другую файловую группу | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- moving tables
- switching filegroups for index
- moving indexes
- indexes [SQL Server], moving
- filegroups [SQL Server], switching
ms.assetid: 167ebe77-487d-4ca8-9452-4b2c7d5cb96e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c99847dcb8d4d65272dd3660c7fd60d3efb8d951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668311"
---
# <a name="move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="e2fed-102">Перемещение существующего индекса в другую файловую группу</span><span class="sxs-lookup"><span data-stu-id="e2fed-102">Move an Existing Index to a Different Filegroup</span></span>
  <span data-ttu-id="e2fed-103">В этом разделе описывается, как переместить текущий индекс из текущей файловой группы в другую файловую группу в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2fed-103">This topic describes how to move an existing index from its current filegroup to a different filegroup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e2fed-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="e2fed-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e2fed-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="e2fed-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e2fed-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e2fed-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e2fed-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e2fed-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e2fed-108">**Для перемещения существующего индекса в другую файловую группу используется:**</span><span class="sxs-lookup"><span data-stu-id="e2fed-108">**To move an existing index to a different filegroup, using:**</span></span>  
  
     [<span data-ttu-id="e2fed-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e2fed-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e2fed-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2fed-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e2fed-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e2fed-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e2fed-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e2fed-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e2fed-113">Если таблица имеет кластеризованный индекс, то перемещение кластеризованного индекса в новую файловую группу перемещает в эту файловую группу саму таблицу.</span><span class="sxs-lookup"><span data-stu-id="e2fed-113">If a table has a clustered index, moving the clustered index to a new filegroup moves the table to that filegroup.</span></span>  
  
-   <span data-ttu-id="e2fed-114">В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]нельзя перемещать индексы, созданные с помощью ограничения UNIQUE или PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="e2fed-114">You cannot move indexes created using a UNIQUE or PRIMARY KEY constraint using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="e2fed-115">Для перемещения этих индексов используйте инструкцию [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) с параметром (DROP_EXISTING=ON) в [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2fed-115">To move these indexes use the [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) statement with the (DROP_EXISTING=ON) option in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e2fed-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="e2fed-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e2fed-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="e2fed-117">Permissions</span></span>  
 <span data-ttu-id="e2fed-118">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="e2fed-118">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="e2fed-119">Пользователь должен быть членом предопределенной роли сервера **sysadmin** или предопределенных ролей базы данных **db_ddladmin** и **db_owner**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-119">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e2fed-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e2fed-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-using-table-designer"></a><span data-ttu-id="e2fed-121">Перемещение существующего индекса в другую файловую группу с помощью конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="e2fed-121">To move an existing index to a different filegroup using Table Designer</span></span>  
  
1.  <span data-ttu-id="e2fed-122">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, где находится индекс, который нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="e2fed-122">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="e2fed-123">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="e2fed-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e2fed-124">Щелкните правой кнопкой мыши таблицу, содержащую индекс, который нужно переместить, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-124">Right-click the table containing the index that you want to move and select **Design**.</span></span>  
  
4.  <span data-ttu-id="e2fed-125">В меню **Конструктор таблиц** выберите пункт **Индексы и ключи**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-125">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="e2fed-126">Выберите индекс, который нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="e2fed-126">Select the index that you want to move.</span></span>  
  
6.  <span data-ttu-id="e2fed-127">В основной сетке разверните узел **Спецификация пространства данных**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-127">In the main grid, expand **Data Space Specification**.</span></span>  
  
7.  <span data-ttu-id="e2fed-128">Выберите значение **Имя файловой группы или схемы секционирования** и выберите из списка файловую группу или схему секционирования, в которую нужно переместить индекс.</span><span class="sxs-lookup"><span data-stu-id="e2fed-128">Select **Filegroup or Partition Scheme Name** and select from the list the filegroup or partition scheme to where you want to move the index.</span></span>  
  
8.  <span data-ttu-id="e2fed-129">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-129">Click **Close**.</span></span>  
  
9. <span data-ttu-id="e2fed-130">В меню **Файл** выберите пункт **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="e2fed-130">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-in-object-explorer"></a><span data-ttu-id="e2fed-131">Перемещение существующего индекса в другую файловую группу в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="e2fed-131">To move an existing index to a different filegroup in Object Explorer</span></span>  
  
1.  <span data-ttu-id="e2fed-132">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, где находится индекс, который нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="e2fed-132">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="e2fed-133">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="e2fed-133">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e2fed-134">Щелкните знак «плюс», чтобы развернуть таблицу, содержащую индекс, который необходимо переместить.</span><span class="sxs-lookup"><span data-stu-id="e2fed-134">Click the plus sign to expand the table containing the index that you want to move.</span></span>  
  
4.  <span data-ttu-id="e2fed-135">Чтобы развернуть папку **Индексы** , щелкните знак «плюс» (+).</span><span class="sxs-lookup"><span data-stu-id="e2fed-135">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="e2fed-136">Щелкните правой кнопкой мыши индекс, который нужно переместить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-136">Right-click the index that you want to move and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="e2fed-137">В разделе **Выбор страницы**выберите пункт **Хранение**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-137">Under **Select a page**, select **Storage**.</span></span>  
  
7.  <span data-ttu-id="e2fed-138">Выберите файловую группу, в которую необходимо переместить индекс.</span><span class="sxs-lookup"><span data-stu-id="e2fed-138">Select the filegroup in which to move the index.</span></span>  
  
     <span data-ttu-id="e2fed-139">если таблица или индекс секционированы, выберите схему секционирования, в которую переместить индекс.</span><span class="sxs-lookup"><span data-stu-id="e2fed-139">If the table or index is partitioned, select the partition scheme in which to move the index.</span></span> <span data-ttu-id="e2fed-140">Дополнительные сведения о секционированных индексах см. в разделе [Секционированные таблицы и индексы](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e2fed-140">For more information about partitioned indexes, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
     <span data-ttu-id="e2fed-141">если перемещается кластеризованный индекс, можно использовать обработку в сети.</span><span class="sxs-lookup"><span data-stu-id="e2fed-141">If you are moving a clustered index, you can use online processing.</span></span> <span data-ttu-id="e2fed-142">Обработка в сети разрешает одновременный доступ пользователей к основным данным и к некластеризованным индексам в течение операции с индексами.</span><span class="sxs-lookup"><span data-stu-id="e2fed-142">Online processing allows concurrent user access to the underlying data and to nonclustered indexes during the index operation.</span></span> <span data-ttu-id="e2fed-143">Дополнительные сведения см. в статье [Выполнение операции с индексами в сети](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="e2fed-143">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
     <span data-ttu-id="e2fed-144">На многопроцессорных компьютерах с [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]можно настроить количество ЦП, используемых для выполнения инструкции индекса, указав значение максимальной степени параллелизма.</span><span class="sxs-lookup"><span data-stu-id="e2fed-144">On multiprocessor computers using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can configure the number of processors used to execute the index statement by specifying a maximum degree of parallelism value.</span></span> <span data-ttu-id="e2fed-145">Параллельные операции с индексами доступны не во всех выпусках [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2fed-145">The Parallel indexed operations feature is not available in every edition of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e2fed-146">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="e2fed-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="e2fed-147">Дополнительные сведения о параллельных операциях с индексами см. в статье [Настройка параллельных операций с индексами](configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="e2fed-147">For more information about Parallel indexed operations, see [Configure Parallel Index Operations](configure-parallel-index-operations.md).</span></span>  
  
8.  <span data-ttu-id="e2fed-148">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-148">Click **OK**.</span></span>  
  
 <span data-ttu-id="e2fed-149">На странице **Хранение** диалогового окна **Свойства индекса ―** _имя_индекса_ доступны следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="e2fed-149">The following information is available on the **Storage** page of the **Index Properties -** _index_name_ dialog box:</span></span>  
  
 <span data-ttu-id="e2fed-150">**Файловая группа**</span><span class="sxs-lookup"><span data-stu-id="e2fed-150">**Filegroup**</span></span>  
 <span data-ttu-id="e2fed-151">Сохраняет индекс в указанной файловой группе.</span><span class="sxs-lookup"><span data-stu-id="e2fed-151">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="e2fed-152">Этот список содержит только стандартные файловые группы (ROW).</span><span class="sxs-lookup"><span data-stu-id="e2fed-152">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="e2fed-153">По умолчанию из этого списка выбирается первичная файловая группа (PRIMARY) текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="e2fed-153">The default list selection is the PRIMARY filegroup of the database.</span></span>  
  
 <span data-ttu-id="e2fed-154">**Файловая группа файлового потока**</span><span class="sxs-lookup"><span data-stu-id="e2fed-154">**Filestream filegroup**</span></span>  
 <span data-ttu-id="e2fed-155">Задает файловую группу для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e2fed-155">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="e2fed-156">Этот список содержит только файловые группы FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e2fed-156">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="e2fed-157">По умолчанию из этого списка выбирается файловая группа PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e2fed-157">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span>  
  
 <span data-ttu-id="e2fed-158">**Схема секционирования**</span><span class="sxs-lookup"><span data-stu-id="e2fed-158">**Partition scheme**</span></span>  
 <span data-ttu-id="e2fed-159">Хранит индекс в схеме секционирования.</span><span class="sxs-lookup"><span data-stu-id="e2fed-159">Stores the index in a partition scheme.</span></span> <span data-ttu-id="e2fed-160">Если нажать кнопку **Схема секционирования** , активируется сетка внизу.</span><span class="sxs-lookup"><span data-stu-id="e2fed-160">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="e2fed-161">По умолчанию из списка выбирается схема секционирования, использованная для хранения данных таблицы.</span><span class="sxs-lookup"><span data-stu-id="e2fed-161">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="e2fed-162">При выборе из списка другой схемы секционирования данные в сетке обновляются.</span><span class="sxs-lookup"><span data-stu-id="e2fed-162">When you select a different partition scheme in the list, the information in the grid is updated.</span></span>  
  
 <span data-ttu-id="e2fed-163">Параметр схемы секционирования недоступен, если в базе данных нет ни одной схемы секционирования.</span><span class="sxs-lookup"><span data-stu-id="e2fed-163">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="e2fed-164">**Схема секционирования файлового потока**</span><span class="sxs-lookup"><span data-stu-id="e2fed-164">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="e2fed-165">Задает схему секционирования для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e2fed-165">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="e2fed-166">Схема секционирования должна быть симметрична схеме, указанной в параметре **Схема секционирования** .</span><span class="sxs-lookup"><span data-stu-id="e2fed-166">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="e2fed-167">Если таблица не секционирована, это поле пусто.</span><span class="sxs-lookup"><span data-stu-id="e2fed-167">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="e2fed-168">**Параметр схемы секционирования**</span><span class="sxs-lookup"><span data-stu-id="e2fed-168">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="e2fed-169">Отображает имя столбца, участвующего в схеме секционирования.</span><span class="sxs-lookup"><span data-stu-id="e2fed-169">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="e2fed-170">**Столбец таблицы**</span><span class="sxs-lookup"><span data-stu-id="e2fed-170">**Table Column**</span></span>  
 <span data-ttu-id="e2fed-171">Выберите таблицу или представление для сопоставления схеме секционирования.</span><span class="sxs-lookup"><span data-stu-id="e2fed-171">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="e2fed-172">**Тип данных столбца**</span><span class="sxs-lookup"><span data-stu-id="e2fed-172">**Column Data Type**</span></span>  
 <span data-ttu-id="e2fed-173">Выводит сведения о типах данных для данного столбца.</span><span class="sxs-lookup"><span data-stu-id="e2fed-173">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2fed-174">Если это вычисляемый столбец, в поле **Тип данных столбца** отображается отметка "вычисляемый столбец".</span><span class="sxs-lookup"><span data-stu-id="e2fed-174">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="e2fed-175">**Разрешить обработку в сети DML-инструкций во время переноса индекса**</span><span class="sxs-lookup"><span data-stu-id="e2fed-175">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="e2fed-176">Параметр дает пользователям возможность получать доступ к данным базовой таблицы или кластеризованного индекса, а также к любым связанным с ними некластеризованным индексам при операциях с индексами.</span><span class="sxs-lookup"><span data-stu-id="e2fed-176">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2fed-177">Этот параметр недоступен для XML-индексов, а также в случае, если индекс является отключенным кластеризованным индексом.</span><span class="sxs-lookup"><span data-stu-id="e2fed-177">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="e2fed-178">**Укажите максимальную степень параллелизма**</span><span class="sxs-lookup"><span data-stu-id="e2fed-178">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="e2fed-179">Ограничивает число процессоров, используемых в одновременном исполнении планов.</span><span class="sxs-lookup"><span data-stu-id="e2fed-179">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="e2fed-180">При значении по умолчанию 0 используется реальное число доступных ЦП.</span><span class="sxs-lookup"><span data-stu-id="e2fed-180">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="e2fed-181">При установке значения 1 создание параллельных планов становится невозможным; при установке значения больше 1 ограничивается максимальное число процессоров, используемых для выполнения одного запроса.</span><span class="sxs-lookup"><span data-stu-id="e2fed-181">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="e2fed-182">Этот параметр становится доступным только в случае, если диалоговое окно находится в состоянии **Перестроение** или **Повторное создание** .</span><span class="sxs-lookup"><span data-stu-id="e2fed-182">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2fed-183">Если задано значение, превышающее число доступных ЦП, используется фактическое число доступных ЦП.</span><span class="sxs-lookup"><span data-stu-id="e2fed-183">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e2fed-184">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2fed-184">Using Transact-SQL</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="e2fed-185">Перемещение существующего индекса в другую файловую группу</span><span class="sxs-lookup"><span data-stu-id="e2fed-185">To move an existing index to a different filegroup</span></span>  
  
1.  <span data-ttu-id="e2fed-186">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2fed-186">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e2fed-187">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-187">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e2fed-188">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e2fed-188">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the TransactionsFG1 filegroup on the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP TransactionsFG1;  
    GO  
    /* Adds the TransactionsFG1dat3 file to the TransactionsFG1 filegroup. Please note that you will have to change the filename parameter in this statement to execute it without errors.  
    */  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = TransactionsFG1dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\TransactionsFG1dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP TransactionsFG1;  
    GO  
    /*Creates the IX_Employee_OrganizationLevel_OrganizationNode index  
      on the TransactionsPS1 filegroup and drops the original IX_Employee_OrganizationLevel_OrganizationNode index.  
    */  
    CREATE NONCLUSTERED INDEX IX_Employee_OrganizationLevel_OrganizationNode  
        ON HumanResources.Employee (OrganizationLevel, OrganizationNode)  
        WITH (DROP_EXISTING = ON)  
        ON TransactionsFG1;  
    GO  
    ```  
  
 <span data-ttu-id="e2fed-189">Дополнительные сведения см. в разделе [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e2fed-189">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
