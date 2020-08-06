---
title: Перенос триггеров | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: ad5385c5-5a50-40ca-a319-97d5606b8511
author: rothja
ms.author: jroth
ms.openlocfilehash: 25965e7cce84b0dcfcd3b6ce6176e8ad3ddabc6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750984"
---
# <a name="migrating-triggers"></a><span data-ttu-id="7f8b9-102">Перенос триггеров</span><span class="sxs-lookup"><span data-stu-id="7f8b9-102">Migrating Triggers</span></span>
  <span data-ttu-id="7f8b9-103">В этом разделе описаны триггеры DDL и DML, а также оптимизированные для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-103">This topic discusses DDL and DML triggers and memory-optimized tables.</span></span>  
  
 <span data-ttu-id="7f8b9-104">Триггеры LOGON и триггеры, определенные для вызова событий LOGON.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-104">LOGON triggers are triggers defined to fire on LOGON events.</span></span> <span data-ttu-id="7f8b9-105">Триггеры LOGON не оказывают влияния на оптимизированные для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-105">LOGON triggers do not affect memory-optimized tables.</span></span>  
  
## <a name="ddl-triggers"></a><span data-ttu-id="7f8b9-106">Триггеры DDL</span><span class="sxs-lookup"><span data-stu-id="7f8b9-106">DDL Triggers</span></span>  
 <span data-ttu-id="7f8b9-107">Триггеры DDL — это триггеры, которые срабатывают при выполнении на сервере, на котором они определены, инструкции CREATE, ALTER, DROP, GRANT, DENY, REVOKE или UPDATE STATISTICS для базы данных.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-107">DDL triggers are triggers defined to fire when a CREATE, ALTER, DROP, GRANT, DENY, REVOKE, or UPDATE STATISTICS statement is executed on the database or server on which it is defined.</span></span>  
  
 <span data-ttu-id="7f8b9-108">Нельзя создать оптимизированные для памяти таблицы, если в базе данных или на сервере определен один или несколько триггеров DDL для события CREATE_TABLE или любой группы событий, которая содержит это событие.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-108">You cannot create memory-optimized tables if the database or server has one or more DDL trigger defined on CREATE_TABLE or any event group that includes it.</span></span> <span data-ttu-id="7f8b9-109">Нельзя удалить оптимизированную для памяти таблицу, если в базе данных или на сервере определен один или несколько триггеров DDL для события DROP_TABLE или любой группы событий, которая содержит это событие.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-109">You cannot drop a memory-optimized table if the database or server has one or more DDL trigger defined on DROP_TABLE or any event group that includes it.</span></span>  
  
 <span data-ttu-id="7f8b9-110">При наличии одного или нескольких триггеров DDL для событий CREATE_PROCEDURE и DROP_PROCEDURE или любой группы событий, в которую входят эти события, нельзя создавать скомпилированные в собственном коде хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-110">You cannot create natively compiled stored procedures if there are one or more DDL triggers on CREATE_PROCEDURE, DROP_PROCEDURE, or any event group that includes those events.</span></span>  
  
## <a name="dml-triggers"></a><span data-ttu-id="7f8b9-111">Триггеры DML</span><span class="sxs-lookup"><span data-stu-id="7f8b9-111">DML Triggers</span></span>  
 <span data-ttu-id="7f8b9-112">Триггеры DML нельзя задавать для оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-112">DML triggers cannot be defined on memory-optimized tables.</span></span> <span data-ttu-id="7f8b9-113">Однако OLTP в памяти позволяет достичь эффекта, подобного действию триггеров DML, если явно использовать хранимые процедуры для вставки, обновления или удаления данных.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-113">However, In-Memory OLTP allows you to achieve an effect similar to DML triggers if you explicitly use stored procedures to insert, update, or delete data.</span></span> <span data-ttu-id="7f8b9-114">Если в системе содержатся нерегламентированные запросы, то вместо имитации действия триггеров DML преобразуйте такие запросы, чтобы использовать эти хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-114">If your system contains ad-hoc queries, convert them to use these stored procedures instead to simulate the effect of DML triggers.</span></span>  
  
 <span data-ttu-id="7f8b9-115">В зависимости от события триггера (FOR/AFTER или INSTEAD OF) можно включить содержимое триггера в соответствующую хранимую процедуру, которая выполняет инструкции INSERT, UPDATE или DELETE в таблице.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-115">Depending on the trigger event (FOR/AFTER or INSTEAD OF), you may include the content of the trigger in the appropriate stored procedure that performs INSERT, UPDATE, or DELETE on that table.</span></span> <span data-ttu-id="7f8b9-116">Например, при переносе триггера AFTER INSERT можно изменить хранимую процедуру, которая выполняет операцию вставки, включив содержимое этого триггера после соответствующей инструкции INSERT.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-116">For example, when migrating an AFTER INSERT trigger, you could alter the stored procedure that performs the insert operation by including the content of the trigger after the appropriate INSERT statement.</span></span>  
  
 <span data-ttu-id="7f8b9-117">Можно использовать интерпретированную хранимую процедуру или скомпилированную в собственном коде хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-117">You can use an interpreted stored procedure or a natively compiled stored procedure.</span></span> <span data-ttu-id="7f8b9-118">Большинство конструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] в интерпретированных хранимых процедурах можно выполнить применительно к оптимизированной для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-118">Most [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs in an interpreted stored procedure can execute on a memory-optimized table.</span></span> <span data-ttu-id="7f8b9-119">Однако в скомпилированных в собственном коде хранимых процедурах поддерживается только подмножество конструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f8b9-119">However, only a subset of [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs are supported in natively compiled stored procedures.</span></span> <span data-ttu-id="7f8b9-120">Дополнительные сведения о поддержке [!INCLUDE[tsql](../../includes/tsql-md.md)] в отношении оптимизированных для памяти таблиц см. в разделе [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7f8b9-120">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support on memory-optimized tables, see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span> <span data-ttu-id="7f8b9-121">Дополнительные сведения о поддержке [!INCLUDE[tsql](../../includes/tsql-md.md)] в скомпилированных в собственном коде хранимых процедурах см. в разделе [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="7f8b9-121">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support in natively compiled stored procedures, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="7f8b9-122">Далее приведен простой пример имитации поведения триггера DML в отношении оптимизированной для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="7f8b9-122">The following is a simple example of simulating DML trigger behavior on a memory-optimized table.</span></span>  
  
 <span data-ttu-id="7f8b9-123">База данных содержит следующие объекты, написанные в виде инструкций CREATE TABLE, CREATE TRIGGER и CREATE PROCEDURE:</span><span class="sxs-lookup"><span data-stu-id="7f8b9-123">The database contains the following objects, scripted as CREATE TABLE, CREATE TRIGGER, and CREATE PROCEDURE statements:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null primary key,  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
)  
GO  
  
CREATE TRIGGER tr_order_details_insteadof_insert  
ON OrderDetails  
INSTEAD OF INSERT AS  
BEGIN  
   DECLARE @pid int, @qty_buy int, @qty_remain int  
   SELECT @pid = ProductId, @qty_buy = Quantity FROM inserted  
   SELECT @qty_remain = Quantity FROM Inventory WHERE ProductId = @pid  
   IF (@qty_remain <= @qty_buy)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      SELECT OrderId, ProductId, SalePrice, Quantity, Total FROM inserted  
      UPDATE Inventory SET Quantity = Quantity - @qty_buy WHERE ProductId = @pid  
   END  
END  
GO  
  
CREATE TRIGGER tr_order_details_after_update  
ON OrderDetails  
AFTER UPDATE AS  
BEGIN  
   INSERT INTO UpdateNotifications (OrderId, UpdateTime) SELECT OrderId, GETDATE() FROM inserted     
END  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
AS BEGIN  
   INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
   VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
AS BEGIN  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
END  
GO  
```  
  
 <span data-ttu-id="7f8b9-124">Следующие объекты функционально эквивалентны состоянию до переноса:</span><span class="sxs-lookup"><span data-stu-id="7f8b9-124">The following objects are functionally equivalent to the pre-migration state:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 1048576),  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE Inventory  
(  
   ProductId int not null PRIMARY KEY NONCLUSTERED,  
   Quantity int not null  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE UpdateNotifications  
(  
   OrderId int not null,  
   UpdateTime datetime2 not null  
   CONSTRAINT pk_updateNotifications PRIMARY KEY NONCLUSTERED (OrderId, UpdateTime)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   DECLARE @qty_remain int  
   SELECT @qty_remain = Quantity FROM dbo.Inventory WHERE ProductId = @ProductId  
   IF (@qty_remain <= @Quantity)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
      UPDATE dbo.Inventory SET Quantity = Quantity - @Quantity WHERE ProductId = @ProductId  
   END  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
   INSERT INTO dbo.UpdateNotifications (OrderId, UpdateTime) VALUES (@OrderId, GETDATE())  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f8b9-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f8b9-125">See Also</span></span>  
 [<span data-ttu-id="7f8b9-126">Миграция в In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="7f8b9-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
