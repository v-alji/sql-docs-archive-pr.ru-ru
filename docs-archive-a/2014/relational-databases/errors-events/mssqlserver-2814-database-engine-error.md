---
title: MSSQLSERVER_2814 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2814 (Database Engine error)
ms.assetid: 22800748-9be9-4511-9428-6b8b40e5bef9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26b1fae5b683ed72cb93c3f81981bd41e2f4ad4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664258"
---
# <a name="mssqlserver_2814"></a><span data-ttu-id="eb4b5-102">MSSQLSERVER_2814</span><span class="sxs-lookup"><span data-stu-id="eb4b5-102">MSSQLSERVER_2814</span></span>
    
## <a name="details"></a><span data-ttu-id="eb4b5-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="eb4b5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb4b5-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="eb4b5-104">Product Name</span></span>|<span data-ttu-id="eb4b5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb4b5-105">SQL Server</span></span>|  
|<span data-ttu-id="eb4b5-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="eb4b5-106">Event ID</span></span>|<span data-ttu-id="eb4b5-107">2814</span><span class="sxs-lookup"><span data-stu-id="eb4b5-107">2814</span></span>|  
|<span data-ttu-id="eb4b5-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="eb4b5-108">Event Source</span></span>|<span data-ttu-id="eb4b5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="eb4b5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="eb4b5-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="eb4b5-110">Component</span></span>|<span data-ttu-id="eb4b5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="eb4b5-111">SQLEngine</span></span>|  
|<span data-ttu-id="eb4b5-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="eb4b5-112">Symbolic Name</span></span>|<span data-ttu-id="eb4b5-113">PR_POSSIBLE_INFINITE_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="eb4b5-113">PR_POSSIBLE_INFINITE_RECOMPILE</span></span>|  
|<span data-ttu-id="eb4b5-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="eb4b5-114">Message Text</span></span>|<span data-ttu-id="eb4b5-115">Обнаружена возможная бесконечная перекомпиляция для SQLHANDLE %hs, PlanHandle %hs, от смещения %d до смещения %d.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-115">A possible infinite recompile was detected for SQLHANDLE %hs, PlanHandle %hs, starting offset %d, ending offset %d.</span></span> <span data-ttu-id="eb4b5-116">Причиной последней перекомпиляции было %d.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-116">The last recompile reason was %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eb4b5-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="eb4b5-117">Explanation</span></span>  
 <span data-ttu-id="eb4b5-118">Одна или несколько инструкций вызвали перекомпиляцию пакета запросов по крайней мере 50 раз.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-118">One or more statements caused the query batch to recompile at least 50 times.</span></span> <span data-ttu-id="eb4b5-119">Необходимо исправить указанную инструкцию, чтобы избежать дальнейшей перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-119">The specified statement should be corrected to avoid further recompilations.</span></span>  
  
 <span data-ttu-id="eb4b5-120">В следующей таблице приводятся причины перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-120">The following table lists the reasons for recompilation.</span></span>  
  
|<span data-ttu-id="eb4b5-121">Код причины</span><span class="sxs-lookup"><span data-stu-id="eb4b5-121">Reason code</span></span>|<span data-ttu-id="eb4b5-122">Описание</span><span class="sxs-lookup"><span data-stu-id="eb4b5-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="eb4b5-123">1</span><span class="sxs-lookup"><span data-stu-id="eb4b5-123">1</span></span>|<span data-ttu-id="eb4b5-124">Изменение схемы</span><span class="sxs-lookup"><span data-stu-id="eb4b5-124">Schema changed</span></span>|  
|<span data-ttu-id="eb4b5-125">2</span><span class="sxs-lookup"><span data-stu-id="eb4b5-125">2</span></span>|<span data-ttu-id="eb4b5-126">Изменение статистики</span><span class="sxs-lookup"><span data-stu-id="eb4b5-126">Statistics changed</span></span>|  
|<span data-ttu-id="eb4b5-127">3</span><span class="sxs-lookup"><span data-stu-id="eb4b5-127">3</span></span>|<span data-ttu-id="eb4b5-128">Отложенная компиляция</span><span class="sxs-lookup"><span data-stu-id="eb4b5-128">Deferred compile</span></span>|  
|<span data-ttu-id="eb4b5-129">4</span><span class="sxs-lookup"><span data-stu-id="eb4b5-129">4</span></span>|<span data-ttu-id="eb4b5-130">Изменение параметра SET</span><span class="sxs-lookup"><span data-stu-id="eb4b5-130">Set option changed</span></span>|  
|<span data-ttu-id="eb4b5-131">5</span><span class="sxs-lookup"><span data-stu-id="eb4b5-131">5</span></span>|<span data-ttu-id="eb4b5-132">Изменение временной таблицы</span><span class="sxs-lookup"><span data-stu-id="eb4b5-132">Temp table changed</span></span>|  
|<span data-ttu-id="eb4b5-133">6</span><span class="sxs-lookup"><span data-stu-id="eb4b5-133">6</span></span>|<span data-ttu-id="eb4b5-134">Изменение удаленного набора строк</span><span class="sxs-lookup"><span data-stu-id="eb4b5-134">Remote rowset changed</span></span>|  
|<span data-ttu-id="eb4b5-135">7</span><span class="sxs-lookup"><span data-stu-id="eb4b5-135">7</span></span>|<span data-ttu-id="eb4b5-136">Изменение разрешений FOR BROWSE</span><span class="sxs-lookup"><span data-stu-id="eb4b5-136">For Browse permissions changed</span></span>|  
|<span data-ttu-id="eb4b5-137">8</span><span class="sxs-lookup"><span data-stu-id="eb4b5-137">8</span></span>|<span data-ttu-id="eb4b5-138">Изменение среды уведомлений о запросах</span><span class="sxs-lookup"><span data-stu-id="eb4b5-138">Query notification environment changed</span></span>|  
|<span data-ttu-id="eb4b5-139">9</span><span class="sxs-lookup"><span data-stu-id="eb4b5-139">9</span></span>|<span data-ttu-id="eb4b5-140">Изменение секционированного представления</span><span class="sxs-lookup"><span data-stu-id="eb4b5-140">Partition view changed</span></span>|  
|<span data-ttu-id="eb4b5-141">10</span><span class="sxs-lookup"><span data-stu-id="eb4b5-141">10</span></span>|<span data-ttu-id="eb4b5-142">Изменение параметров курсора</span><span class="sxs-lookup"><span data-stu-id="eb4b5-142">Cursor options changed</span></span>|  
|<span data-ttu-id="eb4b5-143">11</span><span class="sxs-lookup"><span data-stu-id="eb4b5-143">11</span></span>|<span data-ttu-id="eb4b5-144">Запрошено OPTION (RECOMPILE)</span><span class="sxs-lookup"><span data-stu-id="eb4b5-144">Option (recompile) requested</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="eb4b5-145">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="eb4b5-145">User Action</span></span>  
  
1.  <span data-ttu-id="eb4b5-146">Просмотрите инструкцию, вызывающую перекомпиляцию, запустив следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-146">View the statement causing the recompilation by running the following query.</span></span> <span data-ttu-id="eb4b5-147">Замените заполнители *sql_handle*, *starting_offset*, *ending_offset* и *plan_handle* соответствующими значениями, указанными в сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-147">Replace the *sql_handle*, *starting_offset*, *ending_offset*, and *plan_handle* placeholders with the values specified in the error message.</span></span> <span data-ttu-id="eb4b5-148">Обратите внимание, что столбцы **database_name** и **object_name** будут пустыми для динамических и подготовленных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb4b5-148">Note that the **database_name** and **object_name** columns will be NULL for ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="eb4b5-149">SELECT DB_NAME(st.dbid) AS database_name</span><span class="sxs-lookup"><span data-stu-id="eb4b5-149">SELECT DB_NAME(st.dbid) AS database_name</span></span>  
  
     <span data-ttu-id="eb4b5-150">, OBJECT_NAME(st.objectid) AS object_name</span><span class="sxs-lookup"><span data-stu-id="eb4b5-150">, OBJECT_NAME(st.objectid) AS object_name</span></span>  
  
     <span data-ttu-id="eb4b5-151">, st.text</span><span class="sxs-lookup"><span data-stu-id="eb4b5-151">, st.text</span></span>  
  
     <span data-ttu-id="eb4b5-152">FROM sys.dm_exec_query_stats AS qs</span><span class="sxs-lookup"><span data-stu-id="eb4b5-152">FROM sys.dm_exec_query_stats AS qs</span></span>  
  
     <span data-ttu-id="eb4b5-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span><span class="sxs-lookup"><span data-stu-id="eb4b5-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span></span>  
  
     <span data-ttu-id="eb4b5-154">WHERE qs.statement_start_offset = *starting_offset*</span><span class="sxs-lookup"><span data-stu-id="eb4b5-154">WHERE qs.statement_start_offset = *starting_offset*</span></span>  
  
     <span data-ttu-id="eb4b5-155">AND qs.statement_end_offset = *ending_offset*</span><span class="sxs-lookup"><span data-stu-id="eb4b5-155">AND qs.statement_end_offset = *ending_offset*</span></span>  
  
     <span data-ttu-id="eb4b5-156">AND qs.plan_handle = *plan_handle*;</span><span class="sxs-lookup"><span data-stu-id="eb4b5-156">AND qs.plan_handle = *plan_handle*;</span></span>  
  
2.  <span data-ttu-id="eb4b5-157">В зависимости от описания кода причины измените инструкцию, пакет или процедуру, чтобы избежать перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-157">Based on the reason code description, modify the statement, batch, or procedure to avoid recompilations.</span></span> <span data-ttu-id="eb4b5-158">Например, хранимая процедура может содержать одну или несколько инструкций SET.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-158">For example, a stored procedure may contain one or more SET statements.</span></span> <span data-ttu-id="eb4b5-159">Эти инструкции должны быть удалены из процедуры.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-159">These statements should be removed from the procedure.</span></span> <span data-ttu-id="eb4b5-160">Дополнительные примеры причин повторной компиляции и способов их устранения можно найти в статье [Компиляция пакета, повторная компиляция и проблемы кэширования плана в SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="eb4b5-160">For additional examples of recompilation causes and resolutions, see [Batch Compilation, Recompilation, and Plan Caching Issues in SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span></span>  
  
3.  <span data-ttu-id="eb4b5-161">Если ошибка повторится, обратитесь в службу поддержки пользователей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eb4b5-161">If the problem persists, contact Microsoft Customer Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4b5-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb4b5-162">See Also</span></span>  
 [<span data-ttu-id="eb4b5-163">Класс событий SQL:StmtRecompile</span><span class="sxs-lookup"><span data-stu-id="eb4b5-163">SQL:StmtRecompile Event Class</span></span>](../event-classes/sql-stmtrecompile-event-class.md)  
  
  
