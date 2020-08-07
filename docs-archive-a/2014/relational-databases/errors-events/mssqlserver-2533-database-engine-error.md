---
title: MSSQLSERVER_2533 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2533 (Database Engine error)
ms.assetid: 0418352c-0ab2-4dc7-b8b9-5c3bad94560c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1eb3e2780693a3a0ffed21ce7b9d7887615536c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731630"
---
# <a name="mssqlserver_2533"></a><span data-ttu-id="1ba77-102">MSSQLSERVER_2533</span><span class="sxs-lookup"><span data-stu-id="1ba77-102">MSSQLSERVER_2533</span></span>
    
## <a name="details"></a><span data-ttu-id="1ba77-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1ba77-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ba77-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1ba77-104">Product Name</span></span>|<span data-ttu-id="1ba77-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ba77-105">SQL Server</span></span>|  
|<span data-ttu-id="1ba77-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1ba77-106">Event ID</span></span>|<span data-ttu-id="1ba77-107">2533</span><span class="sxs-lookup"><span data-stu-id="1ba77-107">2533</span></span>|  
|<span data-ttu-id="1ba77-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1ba77-108">Event Source</span></span>|<span data-ttu-id="1ba77-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1ba77-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1ba77-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1ba77-110">Component</span></span>|<span data-ttu-id="1ba77-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1ba77-111">SQLEngine</span></span>|  
|<span data-ttu-id="1ba77-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1ba77-112">Symbolic Name</span></span>|<span data-ttu-id="1ba77-113">DBCC_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="1ba77-113">DBCC_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="1ba77-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1ba77-114">Message Text</span></span>|<span data-ttu-id="1ba77-115">Ошибка таблицы: страница P_ID, выделенная для идентификатора объекта O_ID, идентификатора индекса I_ID, идентификатора секции PN_ID, идентификатора единицы распределения A_ID (тип TYPE), не найдена.</span><span class="sxs-lookup"><span data-stu-id="1ba77-115">Table error: Page P_ID allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) was not seen.</span></span> <span data-ttu-id="1ba77-116">Возможно, указана недопустимая страница, либо идентификатор единицы распределения в ее заголовке неверен.</span><span class="sxs-lookup"><span data-stu-id="1ba77-116">Page may be invalid or have incorrect alloc unit ID in its header.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ba77-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1ba77-117">Explanation</span></span>  
 <span data-ttu-id="1ba77-118">Страница размещена в единице распределения с идентификатором *A_ID*, однако этот идентификатор отсутствует в заголовке страницы.</span><span class="sxs-lookup"><span data-stu-id="1ba77-118">A page is allocated to the allocation unit ID, *A_ID*, but this allocation unit ID is not in the header of the page.</span></span> <span data-ttu-id="1ba77-119">Заголовок содержит другой идентификатор единицы распределения.</span><span class="sxs-lookup"><span data-stu-id="1ba77-119">The header has a different allocation unit ID.</span></span> <span data-ttu-id="1ba77-120">Если идентификатор единицы распределения в заголовке страницы ссылается на правильный объект, страница может содержать ошибку MSSQLEngine_2534.</span><span class="sxs-lookup"><span data-stu-id="1ba77-120">If the allocation unit ID in the header of the page is for a valid object, the page may have a matching MSSQLEngine_2534 error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ba77-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1ba77-121">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="1ba77-122">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="1ba77-122">Look for Hardware Failure</span></span>  
 <span data-ttu-id="1ba77-123">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="1ba77-123">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="1ba77-124">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="1ba77-124">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="1ba77-125">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="1ba77-125">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="1ba77-126">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="1ba77-126">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="1ba77-127">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="1ba77-127">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="1ba77-128">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="1ba77-128">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="1ba77-129">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="1ba77-129">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="1ba77-130">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1ba77-130">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="1ba77-131">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="1ba77-131">Restore from Backup</span></span>  
 <span data-ttu-id="1ba77-132">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="1ba77-132">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="1ba77-133">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="1ba77-133">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="1ba77-134">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="1ba77-134">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="1ba77-135">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="1ba77-135">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="1ba77-136">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="1ba77-136">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1ba77-137">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="1ba77-137">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="1ba77-138">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="1ba77-138">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="1ba77-139">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="1ba77-139">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="1ba77-140">Инструкция REPAIR освободит страницу.</span><span class="sxs-lookup"><span data-stu-id="1ba77-140">REPAIR will deallocate the page.</span></span> <span data-ttu-id="1ba77-141">Если страница находилась в единице распределения памяти для данных, индекс, если он существует, будет перестроен.</span><span class="sxs-lookup"><span data-stu-id="1ba77-141">If the page was from an in-row data allocation unit, the index, if one exists, will be rebuilt.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1ba77-142">Эта операция может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="1ba77-142">This repair may cause data loss.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba77-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ba77-143">See Also</span></span>  
 [<span data-ttu-id="1ba77-144">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="1ba77-144">MSSQLSERVER_2534</span></span>](mssqlserver-2534-database-engine-error.md)  
  
  
