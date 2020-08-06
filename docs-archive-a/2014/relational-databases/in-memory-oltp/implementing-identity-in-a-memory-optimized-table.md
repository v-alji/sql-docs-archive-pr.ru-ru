---
title: Реализация IDENTITY в оптимизированной для памяти таблице | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c0a704a3-3a31-4c2c-b967-addacda62ef8
author: rothja
ms.author: jroth
ms.openlocfilehash: 955f9f1a905a9d0c71304320f60abe300e430e4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658274"
---
# <a name="implementing-identity-in-a-memory-optimized-table"></a><span data-ttu-id="3b42e-102">Реализация IDENTITY в таблице, оптимизированной для памяти</span><span class="sxs-lookup"><span data-stu-id="3b42e-102">Implementing IDENTITY in a Memory-Optimized Table</span></span>
  <span data-ttu-id="3b42e-103">IDENTITY(1, 1) поддерживается для таблицы, оптимизированной для памяти.</span><span class="sxs-lookup"><span data-stu-id="3b42e-103">IDENTITY(1, 1) is supported on a memory-optimized table.</span></span> <span data-ttu-id="3b42e-104">Однако столбцы идентификаторов с определением IDENTITY(x, y), где x != 1 или y != 1 для таблиц, оптимизированных для памяти, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="3b42e-104">However, identity columns with definition of IDENTITY(x, y) where x != 1 or y != 1 are not supported on memory-optimized tables.</span></span> <span data-ttu-id="3b42e-105">Для обхода этой проблемы значения IDENTITY используют объект SEQUENCE ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span><span class="sxs-lookup"><span data-stu-id="3b42e-105">The workaround for IDENTITY values uses the SEQUENCE object ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span></span>  
  
 <span data-ttu-id="3b42e-106">Вначале удалите свойство IDENTITY из таблицы, которая преобразуется в OLTP в памяти.</span><span class="sxs-lookup"><span data-stu-id="3b42e-106">First remove the IDENTITY property from the table you are converting to In-Memory OLTP.</span></span> <span data-ttu-id="3b42e-107">Затем определите новый объект SEQUENCE для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="3b42e-107">Then, define a new SEQUENCE object for the column in the table.</span></span> <span data-ttu-id="3b42e-108">Объекты SEQUENCE как столбцы идентификаторов зависят от возможности создания для столбцов значений DEFAULT, которые используют синтаксис NEXT VALUE FOR для получения нового значения идентификатора.</span><span class="sxs-lookup"><span data-stu-id="3b42e-108">SEQUENCE objects as identity columns rely on the ability to create DEFAULT values for columns that use the NEXT VALUE FOR syntax to get a new identity value.</span></span> <span data-ttu-id="3b42e-109">Поскольку значения DEFAULT не поддерживаются в OLTP в памяти, необходимо передать вновь созданное значение SEQUENCE в инструкцию INSERT или в скомпилированную хранимую процедуру, которая выполняет вставку.</span><span class="sxs-lookup"><span data-stu-id="3b42e-109">Since DEFAULTs are not supported in In-Memory OLTP, you need to pass the newly-generated SEQUENCE value either to the INSERT statement or to a natively compiled stored procedure that does the insert.</span></span> <span data-ttu-id="3b42e-110">Следующий пример демонстрирует этот подход.</span><span class="sxs-lookup"><span data-stu-id="3b42e-110">The following example demonstrates this pattern.</span></span>  
  
```sql  
-- Create a new In-Memory OLTP table to simulate IDENTITY insert  
-- Here the column C1 was the identity column in the original table  
--  
create table T1  
(  
  
[c1] integer not null primary key T1_c1 nonclustered,  
[c2] varchar(32) not null,  
[c3] datetime not null  
  
) with (memory_optimized = on)  
go  
  
-- This is a sequence provider that will give us values for column [c1]  
--  
create sequence usq_SequenceForT1 as integer start with 2 increment by 1  
go  
  
--   insert a sample row using the sequence  
--   note that a new value needs to be retrieved form   
--   the sequence object for every insert  
--  
declare @c1 integer = next value for [dbo].[usq_SequenceForT1]  
insert into T1 values (@c1, 'test', getdate())  
```  
  
 <span data-ttu-id="3b42e-111">После выполнения нескольких вставок можно увидеть монотонно возрастающие значения в столбце [c1].</span><span class="sxs-lookup"><span data-stu-id="3b42e-111">After performing the insert several times, you see valid monotonically increasing values in column [c1].</span></span> <span data-ttu-id="3b42e-112">Этот результирующий набор создан с помощью просмотра таблицы и хэш-индекса без `ORDER BY`, поэтому строки не упорядочены.</span><span class="sxs-lookup"><span data-stu-id="3b42e-112">This result set is generated using table scan and hash index without `ORDER BY` so the rows are not ordered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b42e-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b42e-113">See Also</span></span>  
 [<span data-ttu-id="3b42e-114">Миграция в In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="3b42e-114">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
