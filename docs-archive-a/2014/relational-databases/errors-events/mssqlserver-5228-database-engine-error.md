---
title: MSSQLSERVER_5228 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5228 (Database Engine error)
ms.assetid: 5e83c617-4aa2-4755-bcc5-a798c46b97e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eef59e62f00a44aad7bfefb1719a6d8d2b3d0290
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655234"
---
# <a name="mssqlserver_5228"></a><span data-ttu-id="d8a19-102">MSSQLSERVER_5228</span><span class="sxs-lookup"><span data-stu-id="d8a19-102">MSSQLSERVER_5228</span></span>
    
## <a name="details"></a><span data-ttu-id="d8a19-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d8a19-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8a19-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d8a19-104">Product Name</span></span>|<span data-ttu-id="d8a19-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8a19-105">SQL Server</span></span>|  
|<span data-ttu-id="d8a19-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d8a19-106">Event ID</span></span>|<span data-ttu-id="d8a19-107">5228</span><span class="sxs-lookup"><span data-stu-id="d8a19-107">5228</span></span>|  
|<span data-ttu-id="d8a19-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d8a19-108">Event Source</span></span>|<span data-ttu-id="d8a19-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d8a19-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d8a19-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d8a19-110">Component</span></span>|<span data-ttu-id="d8a19-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d8a19-111">SQLEngine</span></span>|  
|<span data-ttu-id="d8a19-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="d8a19-112">Symbolic Name</span></span>|<span data-ttu-id="d8a19-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span><span class="sxs-lookup"><span data-stu-id="d8a19-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span></span>|  
|<span data-ttu-id="d8a19-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d8a19-114">Message Text</span></span>|<span data-ttu-id="d8a19-115">Ошибка таблицы: идентификатор объекта O_ID, идентификатор индекса I_ID, идентификатор секции PN_ID, идентификатор единицы распределения A_ID (тип TYPE), страница PG_ID, строка R_ID.</span><span class="sxs-lookup"><span data-stu-id="d8a19-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page PG_ID, row R_ID.</span></span> <span data-ttu-id="d8a19-116">При проверке DBCC обнаружен незавершенный процесс очистки после операции построения индекса в сети.</span><span class="sxs-lookup"><span data-stu-id="d8a19-116">DBCC detected incomplete cleanup from an online index build operation.</span></span> <span data-ttu-id="d8a19-117">(Значение виртуального столбца — VALUE.)</span><span class="sxs-lookup"><span data-stu-id="d8a19-117">(Antimatter column value is VALUE.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8a19-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d8a19-118">Explanation</span></span>  
 <span data-ttu-id="d8a19-119">Для объекта *O_ID*, индекса *I_ID* и секции *PN_ID* обнаружено незавершенное построение индекса в режиме "в сети".</span><span class="sxs-lookup"><span data-stu-id="d8a19-119">An unfinished online index build was detected for object *O_ID*, index *I_ID*, and partition *PN_ID*.</span></span> <span data-ttu-id="d8a19-120">Это подтверждается наличием виртуальных столбцов в строке *R_ID*.</span><span class="sxs-lookup"><span data-stu-id="d8a19-120">This is manifested by the presence of an antimatter column on the row *R_ID*.</span></span> <span data-ttu-id="d8a19-121">Виртуальный столбец используется для сверки записей из нескольких источников при построении индекса в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="d8a19-121">An antimatter column is used when reconciling records from multiple sources during an online index build.</span></span> <span data-ttu-id="d8a19-122">Сообщение об ошибке также указывает на значение такого столбца.</span><span class="sxs-lookup"><span data-stu-id="d8a19-122">The error message also indicates the value of the antimatter column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8a19-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d8a19-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="d8a19-124">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="d8a19-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="d8a19-125">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="d8a19-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="d8a19-126">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="d8a19-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="d8a19-127">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="d8a19-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="d8a19-128">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="d8a19-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="d8a19-129">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="d8a19-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="d8a19-130">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="d8a19-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="d8a19-131">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="d8a19-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="d8a19-132">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="d8a19-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="d8a19-133">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="d8a19-133">Restore from Backup</span></span>  
 <span data-ttu-id="d8a19-134">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="d8a19-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="d8a19-135">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="d8a19-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="d8a19-136">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="d8a19-136">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="d8a19-137">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="d8a19-137">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="d8a19-138">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="d8a19-138">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="d8a19-139">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="d8a19-139">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="d8a19-140">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="d8a19-140">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="d8a19-141">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="d8a19-141">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="d8a19-142">Запуск инструкции REPAIR приведет к перестроению указанного индекса и всех зависимых индексов.</span><span class="sxs-lookup"><span data-stu-id="d8a19-142">Running REPAIR will cause the specified index and all its dependent indexes to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a19-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8a19-143">See Also</span></span>  
 [<span data-ttu-id="d8a19-144">DBCC CHECKDB (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d8a19-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
