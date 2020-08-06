---
title: Порядковые номера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sequence number object, overview
- sequence [Database Engine]
- autonumbers, sequences
- sequence numbers [SQL Server]
- sequence number object
ms.assetid: c900e30d-2fd3-4d5f-98ee-7832f37e79d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6c65b4df915a85cf0ec7c7c0c8c0ff9f6607ad96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750584"
---
# <a name="sequence-numbers"></a><span data-ttu-id="8ebb5-102">Порядковые номера</span><span class="sxs-lookup"><span data-stu-id="8ebb5-102">Sequence Numbers</span></span>
  <span data-ttu-id="8ebb5-103">Последовательность представляет собой определяемый пользователем объект, привязанный к схеме, который формирует последовательность числовых значений в соответствии со спецификацией, с которой эта последовательность создавалась.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-103">A sequence is a user-defined schema-bound object that generates a sequence of numeric values according to the specification with which the sequence was created.</span></span> <span data-ttu-id="8ebb5-104">Последовательность числовых значений формируется в возрастающем или убывающем порядке с определенным интервалом и может повторяться запрошенным образом.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-104">The sequence of numeric values is generated in an ascending or descending order at a defined interval and may cycle (repeat) as requested.</span></span> <span data-ttu-id="8ebb5-105">В отличие от столбцов идентификаторов последовательности не связаны с таблицами.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-105">Sequences, unlike identity columns, are not associated with tables.</span></span> <span data-ttu-id="8ebb5-106">Приложение обращается к объекту последовательности, чтобы получить следующее значение.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-106">An application refers to a sequence object to receive its next value.</span></span> <span data-ttu-id="8ebb5-107">Приложения управляют связями между последовательностями и таблицами.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-107">The relationship between sequences and tables is controlled by the application.</span></span> <span data-ttu-id="8ebb5-108">Пользовательские приложения могут ссылаться на объект последовательности и координировать ключи значений между несколькими строками и таблицами.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-108">User applications can reference a sequence object and coordinate the values keys across multiple rows and tables.</span></span>  
  
 <span data-ttu-id="8ebb5-109">Последовательность создается независимо от таблиц с помощью инструкции **CREATE SEQUENCE** .</span><span class="sxs-lookup"><span data-stu-id="8ebb5-109">A sequence is created independently of the tables by using the **CREATE SEQUENCE** statement.</span></span> <span data-ttu-id="8ebb5-110">Параметры позволяют управлять приращением, максимальным и минимальным значением, начальной точкой, возможностью автоматического перезапуска и кэшированием для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-110">Options enable you to control the increment, maximum and minimum values, starting point, automatic restarting capability, and caching to improve performance.</span></span> <span data-ttu-id="8ebb5-111">Сведения о параметрах см. в разделе [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ebb5-111">For information about the options, see [CREATE SEQUENCE](/sql/t-sql/statements/create-sequence-transact-sql).</span></span>  
  
 <span data-ttu-id="8ebb5-112">В отличие от значений столбцов идентификаторов, которые создаются при вставке строк, приложение может получить следующий порядковый номер до вставки строки, вызвав функцию [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8ebb5-112">Unlike identity column values, which are generated when rows are inserted, an application can obtain the next sequence number before inserting the row by calling the [NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql) function.</span></span> <span data-ttu-id="8ebb5-113">Порядковый номер выделяется, когда вызывается функция NEXT VALUE FOR, даже если номер так и не вставляется в таблицу.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-113">The sequence number is allocated when NEXT VALUE FOR is called even if the number is never inserted into a table.</span></span> <span data-ttu-id="8ebb5-114">Функцию NEXT VALUE FOR можно использовать в качестве значения по умолчанию для столбца в определении таблицы.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-114">The NEXT VALUE FOR function can be used as the default value for a column in a table definition.</span></span> <span data-ttu-id="8ebb5-115">Сразу получить диапазон порядковых номеров можно с помощью процедуры [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8ebb5-115">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) to get a range of multiple sequence numbers at once.</span></span>  
  
 <span data-ttu-id="8ebb5-116">Последовательность может быть определена с любым типом данных integer.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-116">A sequence can be defined as any integer data type.</span></span> <span data-ttu-id="8ebb5-117">Если тип данных не указан, по умолчанию для последовательности используется тип `bigint`.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-117">If the data type is not specified, a sequence defaults to `bigint`.</span></span>  
  
## <a name="using-sequences"></a><span data-ttu-id="8ebb5-118">Использование последовательностей</span><span class="sxs-lookup"><span data-stu-id="8ebb5-118">Using Sequences</span></span>  
 <span data-ttu-id="8ebb5-119">Последовательности используются вместо столбцов идентификаторов в следующих сценариях.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-119">Use sequences instead of identity columns in the following scenarios:</span></span>  
  
-   <span data-ttu-id="8ebb5-120">Приложению требуется номер до выполнения вставки в таблицу.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-120">The application requires a number before the insert into the table is made.</span></span>  
  
-   <span data-ttu-id="8ebb5-121">Приложению требуется единая нумерация для нескольких таблиц или нескольких столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-121">The application requires sharing a single series of numbers between multiple tables or multiple columns within a table.</span></span>  
  
-   <span data-ttu-id="8ebb5-122">Приложение должно перезапускать последовательность номеров по достижении определенного номера.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-122">The application must restart the number series when a specified number is reached.</span></span> <span data-ttu-id="8ebb5-123">Например, после назначения значений от 1 до 10 приложение вновь начинает назначать значения от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-123">For example, after assigning values 1 through 10, the application starts assigning values 1 through 10 again.</span></span>  
  
-   <span data-ttu-id="8ebb5-124">Приложению необходимо сортировать значения последовательности по другому полю.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-124">The application requires sequence values to be sorted by another field.</span></span> <span data-ttu-id="8ebb5-125">Функция NEXT VALUE FOR может применять предложение OVER к вызову функции.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-125">The NEXT VALUE FOR function can apply the OVER clause to the function call.</span></span> <span data-ttu-id="8ebb5-126">Предложение OVER гарантирует, что возвращаемые значения создаются в порядке, указанном предложением ORDER BY в предложении OVER.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-126">The OVER clause guarantees that the values returned are generated in the order of the OVER clause's ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="8ebb5-127">Приложению требуется одновременно назначать несколько номеров.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-127">An application requires multiple numbers to be assigned at the same time.</span></span> <span data-ttu-id="8ebb5-128">Например, приложению требуется зарезервировать пять порядковых номеров.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-128">For example, an application needs to reserve five sequential numbers.</span></span> <span data-ttu-id="8ebb5-129">Запрос значений идентификаторов может вызвать пропуски в последовательности, если другие процессы одновременно запросили номера.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-129">Requesting identity values could result in gaps in the series if other processes were simultaneously issued numbers.</span></span> <span data-ttu-id="8ebb5-130">Вызов процедуры sp_sequence_get_range может получить несколько номеров в последовательности сразу.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-130">Calling sp_sequence_get_range can retrieve several numbers in the sequence at once.</span></span>  
  
-   <span data-ttu-id="8ebb5-131">Необходимо изменить спецификацию последовательности, например значение приращения.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-131">You need to change the specification of the sequence, such as the increment value.</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="8ebb5-132">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8ebb5-132">Limitations</span></span>  
 <span data-ttu-id="8ebb5-133">В отличие от столбцов идентификаторов, значения которых нельзя изменять, значения последовательностей не защищаются автоматически после вставки в таблицу.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-133">Unlike identity columns, whose values cannot be changed, sequence values are not automatically protected after insertion into the table.</span></span> <span data-ttu-id="8ebb5-134">Чтобы запретить изменение значений последовательности, используйте в таблице триггер Update для отката изменений.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-134">To prevent sequence values from being changed, use an update trigger on the table to roll back changes.</span></span>  
  
 <span data-ttu-id="8ebb5-135">Уникальность значений последовательности не соблюдается автоматически.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-135">Uniqueness is not automatically enforced for sequence values.</span></span> <span data-ttu-id="8ebb5-136">Значения последовательностей изначально предусматривают многократное использование.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-136">The ability to reuse sequence values is by design.</span></span> <span data-ttu-id="8ebb5-137">Если значения последовательности в таблице должны быть уникальными, создайте для столбца уникальный индекс.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-137">If sequence values in a table are required to be unique, create a unique index on the column.</span></span> <span data-ttu-id="8ebb5-138">Если значения последовательности должны быть уникальными в пределах группы таблиц, создайте триггеры для исключения повторов, вызываемых инструкциями обновлений или циклической сменой порядковых номеров.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-138">If sequence values in a table are required to be unique throughout a group of tables, create triggers to prevent duplicates caused by update statements or sequence number cycling.</span></span>  
  
 <span data-ttu-id="8ebb5-139">Объект последовательности создает номера в соответствии с определением, однако он не контролирует использование этих номеров.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-139">The sequence object generates numbers according to its definition, but the sequence object does not control how the numbers are used.</span></span> <span data-ttu-id="8ebb5-140">В порядковых номерах, вставляемых в таблицу, могут возникать промежутки в случае отката транзакции, если объект последовательности совместно используется несколькими таблицами или если порядковые номера выделяются, но не используются в таблицах.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-140">Sequence numbers inserted into a table can have gaps when a transaction is rolled back, when a sequence object is shared by multiple tables, or when sequence numbers are allocated without using them in tables.</span></span> <span data-ttu-id="8ebb5-141">Если создание производилось с параметром CACHE, то непредвиденное завершение (например, сбой питания) может привести к потере последовательных номеров в кэше.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-141">When created with the CACHE option, an unexpected shutdown, such as a power failure, can lose the sequence numbers in the cache.</span></span>  
  
 <span data-ttu-id="8ebb5-142">Если несколько экземпляров функции `NEXT VALUE FOR` определяют один и тот же генератор последовательностей в одной инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)], то все такие экземпляры возвращают одно и то же значение для строки, обрабатываемой этой инструкцией [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ebb5-142">If there are multiple instances of the `NEXT VALUE FOR` function specifying the same sequence generator within a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, all those instances return the same value for a given row processed by that [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="8ebb5-143">Такое поведение согласуется со стандартом ANSI.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-143">This behavior is consistent with the ANSI standard.</span></span>  
  
## <a name="typical-use"></a><span data-ttu-id="8ebb5-144">Типичные случаи использования</span><span class="sxs-lookup"><span data-stu-id="8ebb5-144">Typical Use</span></span>  
 <span data-ttu-id="8ebb5-145">Чтобы создать целочисленный порядковый номер с приращением 1, меняющийся от -2 147 483 648 до 2 147 483 647, используйте следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-145">To create an integer sequence number that increments by 1 from -2,147,483,648 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    INCREMENT BY 1 ;  
```  
  
 <span data-ttu-id="8ebb5-146">Чтобы создать целочисленный порядковый номер, аналогичный столбцу идентификаторов с приращением 1, меняющемуся от 1 до 2 147 483 647, используйте следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-146">To create an integer sequence number similar to an identity column that increments by 1 from 1 to 2,147,483,647, use the following statement.</span></span>  
  
```  
CREATE SEQUENCE Schema.SequenceName  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
  
```  
  
## <a name="managing-sequences"></a><span data-ttu-id="8ebb5-147">Управление последовательностями</span><span class="sxs-lookup"><span data-stu-id="8ebb5-147">Managing Sequences</span></span>  
 <span data-ttu-id="8ebb5-148">Чтобы получить сведения о последовательностях, запросите представление [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ebb5-148">For information about sequences, query [sys.sequences](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8ebb5-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="8ebb5-149">Examples</span></span>  
 <span data-ttu-id="8ebb5-150">Дополнительные примеры см. в статьях [CREATE SEQUENCE (Transact-SQL)](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR (Transact-SQL)](/sql/t-sql/functions/next-value-for-transact-sql) и [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ebb5-150">There are additional examples in the topics [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql), [NEXT VALUE FOR &#40;Transact-SQL&#41;](/sql/t-sql/functions/next-value-for-transact-sql), and [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql).</span></span>  
  
### <a name="a-using-a-sequence-number-in-a-single-table"></a><span data-ttu-id="8ebb5-151">A.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-151">A.</span></span> <span data-ttu-id="8ebb5-152">Использование порядкового номера в одной таблице</span><span class="sxs-lookup"><span data-stu-id="8ebb5-152">Using a sequence number in a single table</span></span>  
 <span data-ttu-id="8ebb5-153">В следующем примере создается схема с именем Test, таблица с именем Orders и последовательность с именем CountBy1, а затем строки вставляются в таблицу с помощью функции NEXT VALUE FOR.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-153">The following example creates a schema named Test, a table named Orders, and a sequence named CountBy1, and then inserts rows into the table using the NEXT VALUE FOR function.</span></span>  
  
```  
--Create the Test schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Orders  
    (OrderID int PRIMARY KEY,  
    Name varchar(20) NOT NULL,  
    Qty int NOT NULL);  
GO  
  
-- Create a sequence  
CREATE SEQUENCE Test.CountBy1  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
-- Insert three records  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Tire', 2) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Seat', 1) ;  
INSERT test.Orders (OrderID, Name, Qty)  
    VALUES (NEXT VALUE FOR Test.CountBy1, 'Brake', 1) ;  
GO  
  
-- View the table  
SELECT * FROM Test.Orders ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `OrderID  Name    Qty`  
  
 `1        Tire    2`  
  
 `2        Seat    1`  
  
 `3        Brake   1`  
  
### <a name="b-calling-next-value-for-before-inserting-a-row"></a><span data-ttu-id="8ebb5-154">Б.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-154">B.</span></span> <span data-ttu-id="8ebb5-155">Вызов NEXT VALUE FOR до вставки строки</span><span class="sxs-lookup"><span data-stu-id="8ebb5-155">Calling NEXT VALUE FOR before inserting a row</span></span>  
 <span data-ttu-id="8ebb5-156">В следующем примере с помощью таблицы `Orders` , созданной в примере А, объявляется переменная с именем `@nextID`, а затем с помощью функции NEXT VALUE FOR этой переменной присваивается следующий доступный порядковый номер.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-156">Using the `Orders` table created in example A, the following example declares a variable named `@nextID`, and then uses the NEXT VALUE FOR function to set the variable to the next available sequence number.</span></span> <span data-ttu-id="8ebb5-157">Предполагается, что в приложении выполняется некоторая обработка заказа, например заказчику сообщается номер `OrderID` потенциального заказа, а затем проводится проверка заказа.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-157">The application is presumed to do some processing of the order, such as providing the customer with the `OrderID` number of their potential order, and then validates the order.</span></span> <span data-ttu-id="8ebb5-158">Независимо от времени, затрачиваемого на такую обработку, и от числа других заказов, добавляемых во время обработки, исходный номер сохраняется для использования в этом соединении.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-158">No matter how long this processing might take, or how many other orders are added during the process, the original number is preserved for use by this connection.</span></span> <span data-ttu-id="8ebb5-159">Наконец, инструкция `INSERT` добавляет заказ в таблицу `Orders` .</span><span class="sxs-lookup"><span data-stu-id="8ebb5-159">Finally, the `INSERT` statement adds the order to the `Orders` table.</span></span>  
  
```  
DECLARE @NextID int ;  
SET @NextID = NEXT VALUE FOR Test.CountBy1;  
-- Some work happens  
INSERT Test.Orders (OrderID, Name, Qty)  
    VALUES (@NextID, 'Rim', 2) ;  
GO  
  
```  
  
### <a name="c-using-a-sequence-number-in-multiple-tables"></a><span data-ttu-id="8ebb5-160">В.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-160">C.</span></span> <span data-ttu-id="8ebb5-161">Использование порядкового номера в нескольких таблицах</span><span class="sxs-lookup"><span data-stu-id="8ebb5-161">Using a sequence number in multiple tables</span></span>  
 <span data-ttu-id="8ebb5-162">В этом примере предполагается, что процесс мониторинга производственной линии получает уведомления о событиях, происходящих в цеху.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-162">This example assumes that a production-line monitoring process receives notification of events that occur throughout the workshop.</span></span> <span data-ttu-id="8ebb5-163">Каждое событие получает уникальный, монотонно возрастающий номер `EventID` .</span><span class="sxs-lookup"><span data-stu-id="8ebb5-163">Each event receives a unique and monotonically increasing `EventID` number.</span></span> <span data-ttu-id="8ebb5-164">Все события используют один порядковый номер `EventID` , и поэтому отчеты, где объединяются все события, могут однозначно определить каждое событие.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-164">All events use the same `EventID` sequence number so that reports that combine all events can uniquely identify each event.</span></span> <span data-ttu-id="8ebb5-165">Данные событий хранятся в трех различных таблицах в зависимости от типа события.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-165">However the event data is stored in three different tables, depending on the type of event.</span></span> <span data-ttu-id="8ebb5-166">В примере кода создается схема с именем `Audit`, последовательность с именем `EventCounter`и три таблицы, каждая из которых использует последовательность `EventCounter` в качестве значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-166">The code example creates a schema named `Audit`, a sequence named `EventCounter`, and three tables which each use the `EventCounter` sequence as a default value.</span></span> <span data-ttu-id="8ebb5-167">Затем в примере добавляются строки в три таблицы и запрашиваются результаты.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-167">Then the example adds rows to the three tables and queries the results.</span></span>  
  
```  
CREATE SCHEMA Audit ;  
GO  
CREATE SEQUENCE Audit.EventCounter  
    AS int  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
CREATE TABLE Audit.ProcessEvents  
(  
    EventID int PRIMARY KEY CLUSTERED   
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EventCode nvarchar(5) NOT NULL,  
    Description nvarchar(300) NULL  
) ;  
GO  
  
CREATE TABLE Audit.ErrorEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NULL,  
    ErrorNumber int NOT NULL,  
    EventDesc nvarchar(256) NULL  
) ;  
GO  
  
CREATE TABLE Audit.StartStopEvents  
(  
    EventID int PRIMARY KEY CLUSTERED  
        DEFAULT (NEXT VALUE FOR Audit.EventCounter),  
    EventTime datetime NOT NULL DEFAULT (getdate()),  
    EquipmentID int NOT NULL,  
    StartOrStop bit NOT NULL  
) ;  
GO  
  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 0) ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (72, 0) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (2735,   
    'Clean room temperature 18 degrees C.') ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (18, 'Spin rate threashold exceeded.') ;  
INSERT Audit.ErrorEvents (EquipmentID, ErrorNumber, EventDesc)   
    VALUES (248, 82, 'Feeder jam') ;  
INSERT Audit.StartStopEvents (EquipmentID, StartOrStop)   
    VALUES (248, 1) ;  
INSERT Audit.ProcessEvents (EventCode, Description)   
    VALUES (1841, 'Central feed in bypass mode.') ;  
-- The following statement combines all events, though not all fields.  
SELECT EventID, EventTime, Description FROM Audit.ProcessEvents   
UNION SELECT EventID, EventTime, EventDesc FROM Audit.ErrorEvents   
UNION SELECT EventID, EventTime,   
CASE StartOrStop   
    WHEN 0 THEN 'Start'   
    ELSE 'Stop'  
END   
FROM Audit.StartStopEvents  
ORDER BY EventID ;  
GO  
  
```  
  
 [!INCLUDE[ssResult](../../../includes/ssresult-md.md)]  
  
 `EventID  EventTime                Description`  
  
 `1        2009-11-02 15:00:51.157  Start`  
  
 `2        2009-11-02 15:00:51.160  Start`  
  
 `3        2009-11-02 15:00:51.167  Clean room temperature 18 degrees C.`  
  
 `4        2009-11-02 15:00:51.167  Spin rate threshold exceeded.`  
  
 `5        2009-11-02 15:00:51.173  Feeder jam`  
  
 `6        2009-11-02 15:00:51.177  Stop`  
  
 `7        2009-11-02 15:00:51.180  Central feed in bypass mode.`  
  
### <a name="d-generating-repeating-sequence-numbers-in-a-result-set"></a><span data-ttu-id="8ebb5-168">Г.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-168">D.</span></span> <span data-ttu-id="8ebb5-169">Создание повторяющихся порядковых номеров в результирующем наборе</span><span class="sxs-lookup"><span data-stu-id="8ebb5-169">Generating repeating sequence numbers in a result set</span></span>  
 <span data-ttu-id="8ebb5-170">В следующем примере показаны две возможности работы с порядковыми номерами: циклическое повторение и использование `NEXT VALUE FOR` в инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-170">The following example demonstrates two features of sequence numbers: cycling, and using `NEXT VALUE FOR` in a select statement.</span></span>  
  
```  
CREATE SEQUENCE CountBy5  
   AS tinyint  
    START WITH 1  
    INCREMENT BY 1  
    MINVALUE 1  
    MAXVALUE 5  
    CYCLE ;  
GO  
  
SELECT NEXT VALUE FOR CountBy5 AS SurveyGroup, Name FROM sys.objects ;  
GO  
```  
  
### <a name="e-generating-sequence-numbers-for-a-result-set-by-using-the-over-clause"></a><span data-ttu-id="8ebb5-171">Д.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-171">E.</span></span> <span data-ttu-id="8ebb5-172">Создание порядковых номеров для результирующего набора с помощью предложения OVER</span><span class="sxs-lookup"><span data-stu-id="8ebb5-172">Generating sequence numbers for a result set by using the OVER clause</span></span>  
 <span data-ttu-id="8ebb5-173">В следующем примере предложение `OVER` используется для сортировки результирующего набора по столбцу `Name` перед добавлением столбца с порядковым номером.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-173">The following example uses the `OVER` clause to sort the result set by `Name` before it adds the sequence number column.</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE SCHEMA Samples ;  
GO  
  
CREATE SEQUENCE Samples.IDLabel  
    AS tinyint  
    START WITH 1  
    INCREMENT BY 1 ;  
GO  
  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="f-resetting-the-sequence-number"></a><span data-ttu-id="8ebb5-174">Е.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-174">F.</span></span> <span data-ttu-id="8ebb5-175">Сброс порядкового номера</span><span class="sxs-lookup"><span data-stu-id="8ebb5-175">Resetting the sequence number</span></span>  
 <span data-ttu-id="8ebb5-176">В примере Д обработаны первые 79 порядковых номеров `Samples.IDLabel`.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-176">Example E consumed the first 79 of the `Samples.IDLabel` sequence numbers.</span></span> <span data-ttu-id="8ebb5-177">(В используемой версии `AdventureWorks2012` может возвращаться другое число результатов.) Чтобы обработать следующие 79 порядковых номеров (от 80 до 158), выполните следующий код.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-177">(Your version of `AdventureWorks2012` may return a different number of results.) Execute the following to consume the next 79 sequence numbers (80 though 158).</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
 <span data-ttu-id="8ebb5-178">Выполните следующую инструкцию, чтобы перезапустить последовательность `Samples.IDLabel`</span><span class="sxs-lookup"><span data-stu-id="8ebb5-178">Execute the following statement to restart the `Samples.IDLabel` sequence.</span></span>  
  
```  
ALTER SEQUENCE Samples.IDLabel  
RESTART WITH 1 ;  
```  
  
 <span data-ttu-id="8ebb5-179">Снова выполните инструкцию SELECT, чтобы убедиться, что последовательность `Samples.IDLabel` перезапущена с номера 1.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-179">Execute the select statement again to verify that the `Samples.IDLabel` sequence restarted with number 1.</span></span>  
  
```  
SELECT NEXT VALUE FOR Samples.IDLabel OVER (ORDER BY Name) AS NutID, ProductID, Name, ProductNumber FROM Production.Product  
WHERE Name LIKE '%nut%' ;  
```  
  
### <a name="g-changing-a-table-from-identity-to-sequence"></a><span data-ttu-id="8ebb5-180">Ж.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-180">G.</span></span> <span data-ttu-id="8ebb5-181">Перевод таблицы с идентификаторов на последовательность</span><span class="sxs-lookup"><span data-stu-id="8ebb5-181">Changing a table from identity to sequence</span></span>  
 <span data-ttu-id="8ebb5-182">В следующем примере создается схема и таблица, содержащая три строки.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-182">The following example creates a schema and table containing three rows for the example.</span></span> <span data-ttu-id="8ebb5-183">Затем в примере добавляется новый столбец и удаляется старый столбец.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-183">Then the example adds a new column and drops the old column.</span></span>  
  
```  
-- Create a schema  
CREATE SCHEMA Test ;  
GO  
  
-- Create a table  
CREATE TABLE Test.Department  
    (  
        DepartmentID smallint IDENTITY(1,1) NOT NULL,  
        Name nvarchar(100) NOT NULL,  
        GroupName nvarchar(100) NOT NULL  
    CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC)   
    ) ;  
GO  
  
-- Insert three rows into the table  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Engineering', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Tool Design', 'Research and Development');  
GO  
  
INSERT Test.Department(Name, GroupName)  
    VALUES ('Sales', 'Sales and Marketing');  
GO  
  
-- View the table that will be changed  
SELECT * FROM Test.Department ;  
GO  
  
-- End of portion creating a sample table  
--------------------------------------------------------  
-- Add the new column that does not have the IDENTITY property  
ALTER TABLE Test.Department   
    ADD DepartmentIDNew smallint NULL  
GO  
  
-- Copy values from the old column to the new column  
UPDATE Test.Department  
    SET DepartmentIDNew = DepartmentID ;  
GO  
  
-- Drop the primary key constraint on the old column  
ALTER TABLE Test.Department  
    DROP CONSTRAINT [PK_Department_DepartmentID];  
-- Drop the old column  
ALTER TABLE Test.Department  
    DROP COLUMN DepartmentID ;  
GO  
  
-- Rename the new column to the old columns name  
EXEC sp_rename 'Test.Department.DepartmentIDNew',   
    'DepartmentID', 'COLUMN';  
GO  
  
-- Change the new column to NOT NULL  
ALTER TABLE Test.Department  
    ALTER COLUMN DepartmentID smallint NOT NULL ;  
-- Add the unique primary key constraint  
ALTER TABLE Test.Department  
    ADD CONSTRAINT PK_Department_DepartmentID PRIMARY KEY CLUSTERED   
         (DepartmentID ASC) ;  
-- Get the highest current value from the DepartmentID column   
-- and create a sequence to use with the column. (Returns 3.)  
SELECT MAX(DepartmentID) FROM Test.Department ;  
-- Use the next desired value (4) as the START WITH VALUE;  
CREATE SEQUENCE Test.DeptSeq  
    AS smallint  
    START WITH 4  
    INCREMENT BY 1 ;  
GO  
  
-- Add a default value for the DepartmentID column  
ALTER TABLE Test.Department  
    ADD CONSTRAINT DefSequence DEFAULT (NEXT VALUE FOR Test.DeptSeq)   
        FOR DepartmentID;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;   
-- Test insert  
INSERT Test.Department (Name, GroupName)  
    VALUES ('Audit', 'Quality Assurance') ;  
GO  
  
-- View the result  
SELECT DepartmentID, Name, GroupName  
FROM Test.Department ;  
GO  
  
```  
  
 <span data-ttu-id="8ebb5-184">Инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)], использующие `SELECT *`, будут получать новый столбец последним, а не первым.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-184">[!INCLUDE[tsql](../../../includes/tsql-md.md)] statements that use `SELECT *` will receive the new column as the last column instead of the first column.</span></span> <span data-ttu-id="8ebb5-185">Если такая обработка нежелательна, необходимо создать новую таблицу, переместить в нее данные, а затем повторно создать разрешения для новой таблицы.</span><span class="sxs-lookup"><span data-stu-id="8ebb5-185">If this is not acceptable, then you must create an entirely new table, move the data to it, and then recreate the permissions on the new table.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="8ebb5-186">См. также</span><span class="sxs-lookup"><span data-stu-id="8ebb5-186">Related Content</span></span>  
 [<span data-ttu-id="8ebb5-187">CREATE SEQUENCE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ebb5-187">CREATE SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-sequence-transact-sql)  
  
 [<span data-ttu-id="8ebb5-188">ALTER SEQUENCE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ebb5-188">ALTER SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-sequence-transact-sql)  
  
 [<span data-ttu-id="8ebb5-189">DROP SEQUENCE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ebb5-189">DROP SEQUENCE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-sequence-transact-sql)  
  
 [<span data-ttu-id="8ebb5-190">Свойство IDENTITY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ebb5-190">IDENTITY &#40;Property&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql-identity-property)  
  
  
