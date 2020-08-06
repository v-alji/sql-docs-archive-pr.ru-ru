---
title: Настройка параллельных операций с индексами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index parallel operations [SQL Server]
- processors [SQL Server], parallel index operations
- max degree of parallelism option
- MAXDOP index option, parallel index operations
- parallel index operations [SQL Server]
ms.assetid: 8ec8c71e-5fc1-443a-92da-136ee3fc7f88
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8831aadae15af03a05f4ab03cfe514e54566df1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655153"
---
# <a name="configure-parallel-index-operations"></a><span data-ttu-id="2d19f-102">Настройка параллельных операций с индексами</span><span class="sxs-lookup"><span data-stu-id="2d19f-102">Configure Parallel Index Operations</span></span>
  <span data-ttu-id="2d19f-103">В этом разделе определяется параметр max degree of parallelism и описывается порядок изменения этого параметра в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d19f-103">This topic defines max degree of parallelism and explains how to modify this setting in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2d19f-104">На многопроцессорных компьютерах, где установлен выпуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Edition или более многофункциональный, индексные инструкции могут использовать несколько процессоров для выполнения операций просмотра, сортировки и операций с индексами, связанных с индексной инструкцией, аналогично другим запросам.</span><span class="sxs-lookup"><span data-stu-id="2d19f-104">On multiprocessor computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise or higher, index statements may use multiple processors to perform the scan, sort, and index operations associated with the index statement just like other queries do.</span></span> <span data-ttu-id="2d19f-105">Число процессоров, задействованных при выполнении одной индексной инструкции, определяется параметром конфигурации [max degree of parallelism](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) , текущей рабочей нагрузкой и статистикой индекса.</span><span class="sxs-lookup"><span data-stu-id="2d19f-105">The number of processors used to run a single index statement is determined by the [max degree of parallelism](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) configuration option, the current workload, and the index statistics.</span></span> <span data-ttu-id="2d19f-106">Параметр max degree of parallelism определяет максимальное число процессоров, используемых при параллельном выполнении плана.</span><span class="sxs-lookup"><span data-stu-id="2d19f-106">The max degree of parallelism option determines the maximum number of processors to use in parallel plan execution.</span></span> <span data-ttu-id="2d19f-107">Если компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] определяет, что система загружена, степень параллелизма операции с индексами автоматически уменьшается перед началом выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="2d19f-107">If the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] detects that the system is busy, the degree of parallelism of the index operation is automatically reduced before statement execution starts.</span></span> <span data-ttu-id="2d19f-108">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] уменьшает также степень параллелизма, если ведущий ключевой столбец несекционированного индекса имеет ограниченное число различных значений или частота появления таких значений существенно изменяется.</span><span class="sxs-lookup"><span data-stu-id="2d19f-108">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can also reduce the degree of parallelism if the leading key column of a non-partitioned index has a limited number of distinct values or the frequency of each distinct value varies significantly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d19f-109">Параллельные операции с индексами доступны не во всех выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d19f-109">Parallel index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="2d19f-110">Дополнительные сведения см. [в разделе функции, поддерживаемые различными Выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="2d19f-110">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="2d19f-111">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2d19f-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2d19f-112">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2d19f-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2d19f-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2d19f-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2d19f-114">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2d19f-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2d19f-115">**Для настройки параметра max degree of parallelism используется:**</span><span class="sxs-lookup"><span data-stu-id="2d19f-115">**To set the max degree of parallelism, using:**</span></span>  
  
     [<span data-ttu-id="2d19f-116">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d19f-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2d19f-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d19f-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d19f-118">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2d19f-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2d19f-119">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2d19f-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2d19f-120">Число процессоров, используемых оптимизатором запросов, как правило, обеспечивает оптимальную производительность.</span><span class="sxs-lookup"><span data-stu-id="2d19f-120">The number of processors that are used by the query optimizer typically provides optimal performance.</span></span> <span data-ttu-id="2d19f-121">Однако некоторые операции, например создание, перестроение или удаление очень больших индексов, требуют большого количества ресурсов и могут привести к нехватке ресурсов для других приложений и операций базы данных на время выполнения операции с индексами.</span><span class="sxs-lookup"><span data-stu-id="2d19f-121">However, operations such as creating, rebuilding, or dropping very large indexes are resource intensive and can cause insufficient resources for other applications and database operations for the duration of the index operation.</span></span> <span data-ttu-id="2d19f-122">При возникновении этой проблемы можно вручную установить максимальное количество процессоров, которые используются при выполнении индексной инструкции, ограничив число процессоров, используемых в операции с индексами.</span><span class="sxs-lookup"><span data-stu-id="2d19f-122">When this problem occurs, you can manually configure the maximum number of processors that are used to run the index statement by limiting the number of processors to use for the index operation.</span></span>  
  
-   <span data-ttu-id="2d19f-123">Параметр индекса MAXDOP замещает параметр конфигурации max degree of parallelism только для запросов, указывающих этот параметр.</span><span class="sxs-lookup"><span data-stu-id="2d19f-123">The MAXDOP index option overrides the max degree of parallelism configuration option only for the query specifying this option.</span></span> <span data-ttu-id="2d19f-124">В следующей таблице перечислены действительные целочисленные значения, которые могут быть установлены для параметра конфигурации максимальной степени параллелизма и параметра индекса MAXDOP.</span><span class="sxs-lookup"><span data-stu-id="2d19f-124">The following table lists the valid integer values that can be specified with the max degree of parallelism configuration option and the MAXDOP index option.</span></span>  
  
    |<span data-ttu-id="2d19f-125">Значение</span><span class="sxs-lookup"><span data-stu-id="2d19f-125">Value</span></span>|<span data-ttu-id="2d19f-126">Описание</span><span class="sxs-lookup"><span data-stu-id="2d19f-126">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="2d19f-127">0</span><span class="sxs-lookup"><span data-stu-id="2d19f-127">0</span></span>|<span data-ttu-id="2d19f-128">Указывает, что сервер определяет число используемых процессоров в зависимости от текущей рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2d19f-128">Specifies that the server determines the number of CPUs that are used, depending on the current system workload.</span></span> <span data-ttu-id="2d19f-129">Это значение по умолчанию, которое рекомендуется использовать.</span><span class="sxs-lookup"><span data-stu-id="2d19f-129">This is the default value and recommended setting.</span></span>|  
    |<span data-ttu-id="2d19f-130">1</span><span class="sxs-lookup"><span data-stu-id="2d19f-130">1</span></span>|<span data-ttu-id="2d19f-131">Подавляет формирование параллельных планов.</span><span class="sxs-lookup"><span data-stu-id="2d19f-131">Suppresses parallel plan generation.</span></span> <span data-ttu-id="2d19f-132">Операция будет выполнена последовательно.</span><span class="sxs-lookup"><span data-stu-id="2d19f-132">The operation will be executed serially.</span></span>|  
    |<span data-ttu-id="2d19f-133">2–64</span><span class="sxs-lookup"><span data-stu-id="2d19f-133">2-64</span></span>|<span data-ttu-id="2d19f-134">Ограничивает число процессоров указанным значением.</span><span class="sxs-lookup"><span data-stu-id="2d19f-134">Limits the number of processors to the specified value.</span></span> <span data-ttu-id="2d19f-135">Может быть использовано меньше процессоров, в зависимости от рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2d19f-135">Fewer processors may be used depending on the current workload.</span></span> <span data-ttu-id="2d19f-136">Если указано значение, превышающее количество доступных процессоров, будет использоваться реальное количество доступных процессоров.</span><span class="sxs-lookup"><span data-stu-id="2d19f-136">If a value larger than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>|  
  
-   <span data-ttu-id="2d19f-137">Параллельное выполнение индексов и параметр индекса MAXDOP применяются в следующих инструкциях [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="2d19f-137">Parallel index execution and the MAXDOP index option apply to the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    -   <span data-ttu-id="2d19f-138">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="2d19f-138">CREATE INDEX</span></span>  
  
    -   <span data-ttu-id="2d19f-139">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="2d19f-139">ALTER INDEX REBUILD</span></span>  
  
    -   <span data-ttu-id="2d19f-140">DROP INDEX (применяется только для кластеризованных индексов)</span><span class="sxs-lookup"><span data-stu-id="2d19f-140">DROP INDEX (This applies to clustered indexes only.)</span></span>  
  
    -   <span data-ttu-id="2d19f-141">ALTER TABLE ADD (индекс) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="2d19f-141">ALTER TABLE ADD (index) CONSTRAINT</span></span>  
  
    -   <span data-ttu-id="2d19f-142">ALTER TABLE DROP (кластеризованный индекс) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="2d19f-142">ALTER TABLE DROP (clustered index) CONSTRAINT</span></span>  
  
-   <span data-ttu-id="2d19f-143">Параметр индекса MAXDOP не может быть задан в инструкции ALTER INDEX REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="2d19f-143">The MAXDOP index option cannot be specified in the ALTER INDEX REORGANIZE statement.</span></span>  
  
-   <span data-ttu-id="2d19f-144">Операции с секционированными индексами, для которых необходима сортировка, могут требовать больше памяти, если оптимизатор запросов применяет степени параллелизма к операциям построения.</span><span class="sxs-lookup"><span data-stu-id="2d19f-144">Memory requirements for partitioned index operations that require sorting can be greater if the query optimizer applies degrees of parallelism to the build operation.</span></span> <span data-ttu-id="2d19f-145">Чем выше степень параллелизма, тем больше требуется памяти.</span><span class="sxs-lookup"><span data-stu-id="2d19f-145">The higher the degrees of parallelism, the greater the memory requirement is.</span></span> <span data-ttu-id="2d19f-146">Дополнительные сведения см. в разделе [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="2d19f-146">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d19f-147">безопасность</span><span class="sxs-lookup"><span data-stu-id="2d19f-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d19f-148">Permissions</span><span class="sxs-lookup"><span data-stu-id="2d19f-148">Permissions</span></span>  
 <span data-ttu-id="2d19f-149">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="2d19f-149">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2d19f-150">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d19f-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-index"></a><span data-ttu-id="2d19f-151">Задание параметра max degree of parallelism для индекса</span><span class="sxs-lookup"><span data-stu-id="2d19f-151">To set max degree of parallelism on an index</span></span>  
  
1.  <span data-ttu-id="2d19f-152">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо указать параметр max degree of parallelism для индекса.</span><span class="sxs-lookup"><span data-stu-id="2d19f-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to set max degree of parallelism for an index.</span></span>  
  
2.  <span data-ttu-id="2d19f-153">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="2d19f-153">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="2d19f-154">Щелкните знак «плюс», чтобы развернуть таблицу, в которой необходимо указать параметр max degree of parallelism для индекса.</span><span class="sxs-lookup"><span data-stu-id="2d19f-154">Click the plus sign to expand the table on which you want to set max degree of parallelism for an index.</span></span>  
  
4.  <span data-ttu-id="2d19f-155">Разверните папку **Индексы**.</span><span class="sxs-lookup"><span data-stu-id="2d19f-155">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="2d19f-156">Щелкните правой кнопкой мыши индекс, для которого нужно задать параметр max degree of parallelism, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2d19f-156">Right-click the index for which you want to set the max degree of parallelism and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="2d19f-157">В разделе **Выбор страницы**щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="2d19f-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="2d19f-158">Выберите свойство **Максимальная степень параллелизма**и введите значение от 1 до 64.</span><span class="sxs-lookup"><span data-stu-id="2d19f-158">Select **Maximum degree of parallelism**, and then enter some value between 1 and 64.</span></span>  
  
8.  <span data-ttu-id="2d19f-159">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2d19f-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2d19f-160">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d19f-160">Using Transact-SQL</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-existing-index"></a><span data-ttu-id="2d19f-161">Задание параметра max degree of parallelism для существующего индекса</span><span class="sxs-lookup"><span data-stu-id="2d19f-161">To set max degree of parallelism on an existing index</span></span>  
  
1.  <span data-ttu-id="2d19f-162">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d19f-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2d19f-163">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2d19f-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2d19f-164">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2d19f-164">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Alters the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table so that, if the server has eight or more processors, the Database Engine will limit the execution of the index operation to eight or fewer processors.  
    */  
    ALTER INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor  
    REBUILD WITH (MAXDOP=8);   
    GO  
    ```  
  
 <span data-ttu-id="2d19f-165">Дополнительные сведения см. в разделе [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d19f-165">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
#### <a name="set-max-degree-of-parallelism-on-a-new-index"></a><span data-ttu-id="2d19f-166">Задание параметра max degree of parallelism для нового индекса</span><span class="sxs-lookup"><span data-stu-id="2d19f-166">Set max degree of parallelism on a new index</span></span>  
  
1.  <span data-ttu-id="2d19f-167">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d19f-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2d19f-168">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2d19f-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2d19f-169">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2d19f-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE INDEX IX_ProductVendor_NewVendorID   
    ON Purchasing.ProductVendor (BusinessEntityID)  
    WITH (MAXDOP=8);  
    GO  
    ```  
  
 <span data-ttu-id="2d19f-170">Дополнительные сведения см. в разделе [CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d19f-170">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
