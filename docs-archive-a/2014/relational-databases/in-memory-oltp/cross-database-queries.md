---
title: Межбазовые запросы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a0305f5b-91bd-4d18-a2fc-ec235b062fd3
author: rothja
ms.author: jroth
ms.openlocfilehash: 4afbb580a55273ec241005493fd37f99e98ec0e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657101"
---
# <a name="cross-database-queries"></a><span data-ttu-id="7e8d2-102">Межбазовые запросы</span><span class="sxs-lookup"><span data-stu-id="7e8d2-102">Cross-Database Queries</span></span>
  <span data-ttu-id="7e8d2-103">В [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]транзакции между базами данных не поддерживаются с таблицами, оптимизированными для памяти.</span><span class="sxs-lookup"><span data-stu-id="7e8d2-103">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], memory-optimized tables do not support cross-database transactions.</span></span> <span data-ttu-id="7e8d2-104">Нельзя получить доступ к другой базе данных из той же транзакции или того же запроса, которые также получают доступ к оптимизированной для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="7e8d2-104">You cannot access another database from the same transaction or the same query that also accesses a memory-optimized table.</span></span> <span data-ttu-id="7e8d2-105">Нельзя скопировать данные из одной таблицы в базе данных в оптимизированную для памяти таблицу в другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="7e8d2-105">You cannot easily copy data from a table in one database, to a memory-optimized table in another database.</span></span>  
  
 <span data-ttu-id="7e8d2-106">Табличные переменные не является транзакционными.</span><span class="sxs-lookup"><span data-stu-id="7e8d2-106">Table variables are not transactional.</span></span> <span data-ttu-id="7e8d2-107">Поэтому табличные переменные, оптимизированные для памяти, можно использовать в запросах между базами данных. Такие переменные упрощают перемещение данных из таблицы в одной базе данных в оптимизированные для памяти таблицы в другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="7e8d2-107">Therefore, memory-optimized table variables can be used in cross-database queries, and can thus facilitate moving data from one database into memory-optimized tables in another.</span></span> <span data-ttu-id="7e8d2-108">Можно использовать две транзакции.</span><span class="sxs-lookup"><span data-stu-id="7e8d2-108">You can use two transactions.</span></span> <span data-ttu-id="7e8d2-109">В первой транзакции вставьте данные из удаленной таблицы в переменную.</span><span class="sxs-lookup"><span data-stu-id="7e8d2-109">In the first transaction, insert the data from the remote table into the variable.</span></span> <span data-ttu-id="7e8d2-110">Во второй транзакции вставьте данные в локальную оптимизированную для памяти таблицу из переменной.</span><span class="sxs-lookup"><span data-stu-id="7e8d2-110">In the second transaction, insert the data into the local memory-optimized table from the variable.</span></span>  
  
 <span data-ttu-id="7e8d2-111">Например, чтобы скопировать строку из таблицы T1 в базе данных DB1 в таблицу T2 в DB2, используя переменную @v1 типа dbo. TT1, можно использовать нечто вроде:</span><span class="sxs-lookup"><span data-stu-id="7e8d2-111">For example, to copy the row from table t1 in database db1 to table t2 in db2, using variable @v1 of type dbo.tt1, you can use something like:</span></span>  
  
```sql  
USE db2   
GO   
DECLARE @v1 dbo.tt1   
INSERT @v1 SELECT * FROM db1.dbo.t1   
INSERT dbo.t2 SELECT * FROM @v1   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e8d2-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e8d2-112">See Also</span></span>  
 [<span data-ttu-id="7e8d2-113">Миграция в In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="7e8d2-113">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
