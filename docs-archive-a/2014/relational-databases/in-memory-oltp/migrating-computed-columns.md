---
title: Перенос вычисляемых столбцов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 64a9eade-22c3-4a9d-ab50-956219e08df1
author: rothja
ms.author: jroth
ms.openlocfilehash: feb50ef64f42d95913ad4e13f9a79e6e0e4ecad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750995"
---
# <a name="migrating-computed-columns"></a><span data-ttu-id="f7130-102">Перенос вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="f7130-102">Migrating Computed Columns</span></span>
  <span data-ttu-id="f7130-103">Вычисляемые столбцы не поддерживаются в оптимизированных для памяти таблицах.</span><span class="sxs-lookup"><span data-stu-id="f7130-103">Computed columns are not supported in memory-optimized tables.</span></span> <span data-ttu-id="f7130-104">Однако вычисляемый столбец можно смоделировать.</span><span class="sxs-lookup"><span data-stu-id="f7130-104">However, you can simulate a computed column.</span></span>  
  
 <span data-ttu-id="f7130-105">Должна быть определена необходимость сохранять вычисляемые столбцы при переносе таблиц на диске в таблицы, оптимизированные для памяти.</span><span class="sxs-lookup"><span data-stu-id="f7130-105">You should consider the need to persist your computed columns when you migrate your disk-based tables to memory-optimized tables.</span></span> <span data-ttu-id="f7130-106">Различные характеристики производительности таблиц, оптимизированных для памяти, и скомпилированных в собственной коде хранимых процедур могут поставить под сомнение необходимость сохранения.</span><span class="sxs-lookup"><span data-stu-id="f7130-106">The different performance characteristics of memory-optimized tables and natively compiled stored procedures may negate the need for persistence.</span></span>  
  
## <a name="non-persisted-computed-columns"></a><span data-ttu-id="f7130-107">Несохраняемые вычисляемые столбцы</span><span class="sxs-lookup"><span data-stu-id="f7130-107">Non-Persisted Computed Columns</span></span>  
 <span data-ttu-id="f7130-108">Для моделирования эффектов несохраняемого вычисляемого столбца можно создать представление на таблице, оптимизированной для памяти.</span><span class="sxs-lookup"><span data-stu-id="f7130-108">To simulate the effects of a non-persisted computed column, create a view on the memory-optimized table.</span></span> <span data-ttu-id="f7130-109">В инструкции SELECT, определяющей представление, добавьте определение вычисляемого столбца в представление.</span><span class="sxs-lookup"><span data-stu-id="f7130-109">In the SELECT statement that defines the view, add the computed column definition into the view.</span></span> <span data-ttu-id="f7130-110">За исключением скомпилированных в собственном коде хранимых процедур, запросы, в которых используются значения из вычисляемого столбца, должны читать данные из представления.</span><span class="sxs-lookup"><span data-stu-id="f7130-110">Except in a natively compiled stored procedure, queries that use values from the computed column should read from the view.</span></span> <span data-ttu-id="f7130-111">Внутри скомпилированных в собственном коде хранимых процедур необходимо обновить все инструкции выборки, обновления и удаления в соответствии с определением вычисляемого столбца.</span><span class="sxs-lookup"><span data-stu-id="f7130-111">Inside natively compiled stored procedures, you should update any select, update, or delete statement according to your computed column definition.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is not persisted.  
CREATE VIEW dbo.v_order_details AS  
   SELECT  
      OrderId,  
      ProductId,  
      SalePrice,  
      Quantity,  
      Quantity * SalePrice AS Total  
   FROM dbo.order_details  
```  
  
## <a name="persisted-computed-columns"></a><span data-ttu-id="f7130-112">Материализованные вычисляемые столбцы</span><span class="sxs-lookup"><span data-stu-id="f7130-112">Persisted Computed Columns</span></span>  
 <span data-ttu-id="f7130-113">Для моделирования эффектов материализованного вычисляемого столбца создайте хранимую процедуру для вставки в таблицу и еще одну хранимую процедуру для обновления таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7130-113">To simulate the effects of a persisted computed column, create a stored procedure for inserting into the table and another stored procedure for updating the table.</span></span> <span data-ttu-id="f7130-114">При вставке или обновлении таблицы вызывайте для выполнения данных задач эти хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="f7130-114">When inserting or updating the table, invoke these stored procedures to perform these tasks.</span></span> <span data-ttu-id="f7130-115">Внутри хранимых процедур вычисляйте значения для вычисляемых полей в соответствии с входными данными аналогично определению вычисляемого столбца в исходной таблице на диске.</span><span class="sxs-lookup"><span data-stu-id="f7130-115">Inside the stored procedures, calculate the value for the computed field according to the inputs, much like how the computed column is defined on the original disk-based table.</span></span> <span data-ttu-id="f7130-116">Затем вставляйте данные или обновляйте таблицу по мере необходимости внутри хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f7130-116">Then, insert or update the table as needed inside the stored procedure.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is persisted.  
-- we need to create insert and update procedures to calculate Total.  
CREATE PROCEDURE sp_insert_order_details   
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
-- for bulk inserts, accept a table-valued parameter into the stored procedure  
-- and use an INSERT INTO SELECT statement.  
DECLARE @total money = @SalePrice * @Quantity  
INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
DECLARE @total money = @SalePrice * @Quantity  
UPDATE dbo.OrderDetails   
SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
WHERE OrderId = @OrderId  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7130-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7130-117">See Also</span></span>  
 [<span data-ttu-id="f7130-118">Миграция в In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="f7130-118">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
