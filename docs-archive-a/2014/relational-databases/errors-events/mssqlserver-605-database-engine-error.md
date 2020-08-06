---
title: MSSQLSERVER_605 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 605 (Database Engine error)
ms.assetid: d8d3a22e-1ff8-48a4-891f-4c8619437e24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e196fba84af492b25e798629d3e808b1bf22857e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667101"
---
# <a name="mssqlserver_605"></a><span data-ttu-id="44605-102">MSSQLSERVER_605</span><span class="sxs-lookup"><span data-stu-id="44605-102">MSSQLSERVER_605</span></span>
    
## <a name="details"></a><span data-ttu-id="44605-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="44605-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44605-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="44605-104">Product Name</span></span>|<span data-ttu-id="44605-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="44605-105">SQL Server</span></span>|  
|<span data-ttu-id="44605-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="44605-106">Event ID</span></span>|<span data-ttu-id="44605-107">605</span><span class="sxs-lookup"><span data-stu-id="44605-107">605</span></span>|  
|<span data-ttu-id="44605-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="44605-108">Event Source</span></span>|<span data-ttu-id="44605-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="44605-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="44605-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="44605-110">Component</span></span>|<span data-ttu-id="44605-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="44605-111">SQLEngine</span></span>|  
|<span data-ttu-id="44605-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="44605-112">Symbolic Name</span></span>|<span data-ttu-id="44605-113">WRONGPAGE</span><span class="sxs-lookup"><span data-stu-id="44605-113">WRONGPAGE</span></span>|  
|<span data-ttu-id="44605-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="44605-114">Message Text</span></span>|<span data-ttu-id="44605-115">Не удалось выбрать логическую страницу с идентификатором %S_PGID в базе данных %d.</span><span class="sxs-lookup"><span data-stu-id="44605-115">Attempt to fetch logical page %S_PGID in database %d failed.</span></span> <span data-ttu-id="44605-116">Она принадлежит единице распределения %I64d, а не %I64d.</span><span class="sxs-lookup"><span data-stu-id="44605-116">It belongs to allocation unit %I64d not to %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44605-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="44605-117">Explanation</span></span>  
 <span data-ttu-id="44605-118">Обычно эта ошибка свидетельствует о повреждении страниц или об ошибке при их выделении в указанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="44605-118">This error generally signifies page or allocation corruption in the specified database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="44605-119">выявляет это при чтении страниц таблицы либо по указателям, либо через карту распределения индекса (IAM).</span><span class="sxs-lookup"><span data-stu-id="44605-119">detects corruption when reading pages belonging to a table either by following the page linkages or by using the Index Allocation Map (IAM).</span></span> <span data-ttu-id="44605-120">Все относящиеся к таблице страницы должны принадлежать одной из единиц распределения, связанных с данной таблицей.</span><span class="sxs-lookup"><span data-stu-id="44605-120">All pages allocated to a table must belong to one of the allocation units associated with the table.</span></span> <span data-ttu-id="44605-121">Если идентификатор единицы распределения, содержащийся в заголовке страницы, не соответствует идентификатору единицы распределения, связанной с таблицей, возникает это исключение.</span><span class="sxs-lookup"><span data-stu-id="44605-121">If the allocation unit ID contained in the page header does not match an allocation unit ID associated with the table, this exception is raised.</span></span> <span data-ttu-id="44605-122">Первый идентификатор единицы распределения, приведенный в сообщении об ошибке, содержится в заголовке страницы, а второй является идентификатором, связанным с таблицей.</span><span class="sxs-lookup"><span data-stu-id="44605-122">The first allocation unit ID listed in the error message is the ID present in the page header, and the second allocation unit value is the ID associated with the table.</span></span>  
  
 <span data-ttu-id="44605-123">**Ошибки повреждения данных**</span><span class="sxs-lookup"><span data-stu-id="44605-123">**Data Corruption Errors**</span></span>  
  
 <span data-ttu-id="44605-124">Уровень серьезности 21 указывает на потенциальное повреждение данных.</span><span class="sxs-lookup"><span data-stu-id="44605-124">A severity level of 21 indicates potential data corruption.</span></span> <span data-ttu-id="44605-125">Его причиной может стать повреждение цепочки страниц, карты распределения индекса или неверная запись в представлении каталога [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="44605-125">Possible causes are a damaged page chain, a corrupt IAM, or an invalid entry in the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view for that object.</span></span> <span data-ttu-id="44605-126">Зачастую такие ошибки вызваны сбоем оборудования или драйвера дискового устройства.</span><span class="sxs-lookup"><span data-stu-id="44605-126">These errors are often caused by hardware or disk device driver failure.</span></span>  
  
 <span data-ttu-id="44605-127">**Нерегулярные ошибки**</span><span class="sxs-lookup"><span data-stu-id="44605-127">**Transient Errors**</span></span>  
  
 <span data-ttu-id="44605-128">Уровень серьезности 12 означает потенциальную нерегулярную ошибку. Такие ошибки возникают в кэше и не указывают на повреждение данных на диске.</span><span class="sxs-lookup"><span data-stu-id="44605-128">A severity level of 12 indicates a potential transient error; that is, it occurs in the cache and does not indicate damage to data on disk.</span></span> <span data-ttu-id="44605-129">Нерегулярные ошибки 605 могут быть вызваны следующими причинами.</span><span class="sxs-lookup"><span data-stu-id="44605-129">Transient 605 errors can be caused by the following conditions:</span></span>  
  
-   <span data-ttu-id="44605-130">Операционная система преждевременно извещает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] о завершении операции ввода-вывода. В таком случае будет выдано сообщение об ошибке, хотя реальное повреждение данных места не имело.</span><span class="sxs-lookup"><span data-stu-id="44605-130">The operating system prematurely notifies [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that an I/O operation has completed; the error message is displayed even though no actual data corruption exists.</span></span>  
  
 <span data-ttu-id="44605-131">Запуск запроса с указанием оптимизатору NOLOCK или задание уровня изоляции транзакций READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="44605-131">Running a query with the Optimizer hint NOLOCK or setting the transaction isolation level to READ UNCOMMITTED.</span></span> <span data-ttu-id="44605-132">Когда запрос с подсказкой NOLOCK или на уровне изоляции READ UNCOMMITTED пытается прочитать данные, которые перемещены или изменены другим пользователем, возникает ошибка 605.</span><span class="sxs-lookup"><span data-stu-id="44605-132">When a query that is using NOLOCK or READ UNCOMMITTED tries to read data that is being moved or changed by another user, a 605 error occurs.</span></span> <span data-ttu-id="44605-133">Чтобы убедиться, что имеет место нерегулярная ошибка 605, перезапустите запрос позже.</span><span class="sxs-lookup"><span data-stu-id="44605-133">To verify that it is a transient 605 error, rerun the query later.</span></span> <span data-ttu-id="44605-134">Дополнительные сведения см. в статье базы знаний [235880](https://support.microsoft.com/kb/235880/en-us): "При выполнении запроса с указанием оптимизатору NOLOCK или при установке уровня изоляции транзакции в значение READ UNCOMMITTED в SQL Server получено сообщение об ошибке «Ошибка 605»".</span><span class="sxs-lookup"><span data-stu-id="44605-134">For more information, see this KB article [235880](https://support.microsoft.com/kb/235880/en-us): "You receive an "Error 605" error message when you run a query with the optimizer hint NOLOCK or you set the transaction isolation level to READ UNCOMMITTED in SQL Server."</span></span>  
  
 <span data-ttu-id="44605-135">Как правило, если эта ошибка возникла при доступе к данным, но последующие операции DBCC CHECKDB завершились успешно, то скорее всего ошибка 605 была нерегулярной.</span><span class="sxs-lookup"><span data-stu-id="44605-135">In general, if the error occurs during data access but subsequent DBCC CHECKDB operations complete without error, the 605 error was probably transient.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44605-136">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="44605-136">User Action</span></span>  
 <span data-ttu-id="44605-137">Если ошибка 605 появляется регулярно, это означает, что возникла серьезная проблема, которая должна быть решена путем выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="44605-137">If the 605 error is not transient, the problem is severe and must be corrected by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="44605-138">Выясните, какие таблицы связаны с указанными в сообщении единицами распределения, запустив следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="44605-138">Identify the tables associated with the allocation units specified in the message by running the following query.</span></span> <span data-ttu-id="44605-139">Замените `allocation_unit_id` указанными в сообщении об ошибке единицами распределения.</span><span class="sxs-lookup"><span data-stu-id="44605-139">Replace `allocation_unit_id` with the allocation units specified in the error message.</span></span>  
  
     <span data-ttu-id="44605-140">USE`database_name`;</span><span class="sxs-lookup"><span data-stu-id="44605-140">USE`database_name`;</span></span>  
  
     <span data-ttu-id="44605-141">GO</span><span class="sxs-lookup"><span data-stu-id="44605-141">GO</span></span>  
  
     <span data-ttu-id="44605-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span><span class="sxs-lookup"><span data-stu-id="44605-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span></span>  
  
     <span data-ttu-id="44605-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span><span class="sxs-lookup"><span data-stu-id="44605-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span></span>  
  
     <span data-ttu-id="44605-144">FROM sys.allocation_units AS au</span><span class="sxs-lookup"><span data-stu-id="44605-144">FROM sys.allocation_units AS au</span></span>  
  
     <span data-ttu-id="44605-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span><span class="sxs-lookup"><span data-stu-id="44605-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span></span>  
  
     <span data-ttu-id="44605-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span><span class="sxs-lookup"><span data-stu-id="44605-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span></span>  
  
     <span data-ttu-id="44605-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span><span class="sxs-lookup"><span data-stu-id="44605-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span></span>  
  
     <span data-ttu-id="44605-148">ORDER BY au.allocation_unit_id;</span><span class="sxs-lookup"><span data-stu-id="44605-148">ORDER BY au.allocation_unit_id;</span></span>  
  
     <span data-ttu-id="44605-149">GO</span><span class="sxs-lookup"><span data-stu-id="44605-149">GO</span></span>  
  
2.  <span data-ttu-id="44605-150">Выполните инструкцию DBCC CHECKTABLE без предложения REPAIR для таблицы, связанной со вторым идентификатором единицы распределения, указанным в сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="44605-150">Execute DBCC CHECKTABLE without a REPAIR clause on the table associated with the second allocation unit ID specified in the error message.</span></span>  
  
3.  <span data-ttu-id="44605-151">Выполните инструкцию DBCC CHECKDB без предложения REPAIR как можно скорее, чтобы выявить весь поврежденный экстент в базе данных.</span><span class="sxs-lookup"><span data-stu-id="44605-151">Execute DBCC CHECKDB without a REPAIR clause as soon as possible to determine the full extent of the corruption in the entire database.</span></span>  
  
4.  <span data-ttu-id="44605-152">Проверьте в журнале ошибок наличие других ошибок, которые обычно сопровождают ошибку 605 и выясните, не указывают ли они на какие-либо проблемы, связанные с системой или оборудованием.</span><span class="sxs-lookup"><span data-stu-id="44605-152">Check the error log for other errors that often accompany a 605 error and examine the Windows Event Log for any system or hardware related issues.</span></span> <span data-ttu-id="44605-153">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="44605-153">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="44605-154">Если проблема не связана с оборудованием, выполните одну из следующих задач.</span><span class="sxs-lookup"><span data-stu-id="44605-154">If the problem is not hardware related, perform one of the following tasks:</span></span>  
  
1.  <span data-ttu-id="44605-155">Восстановите базу данных из безошибочной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="44605-155">Restore the database from a known clean backup.</span></span> <span data-ttu-id="44605-156">Восстановление страниц позволяет эффективно восстанавливать из резервных копий только поврежденные страницы.</span><span class="sxs-lookup"><span data-stu-id="44605-156">You can leverage the page restore backup feature to restore just the damaged pages.</span></span>  
  
2.  <span data-ttu-id="44605-157">Для исправления повреждения запустите инструкцию DBCC CHECKDB с предложением REPAIR согласно рекомендации операции DBCC CHECKDB, выполненной на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="44605-157">Run DBCC CHECKDB with the REPAIR clause recommended by the DBCC CHECKDB operation performed in step 3 to repair the corruption.</span></span> <span data-ttu-id="44605-158">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="44605-158">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span> <span data-ttu-id="44605-159">Подготовьте к просмотру выходные данные инструкции DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="44605-159">Have the output from DBCC CHECKDB available for review.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="44605-160">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="44605-160">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44605-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="44605-161">See Also</span></span>  
 [<span data-ttu-id="44605-162">DBCC CHECKTABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="44605-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql)  
  
  
