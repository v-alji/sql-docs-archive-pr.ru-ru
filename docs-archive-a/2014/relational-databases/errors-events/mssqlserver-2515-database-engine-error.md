---
title: MSSQLSERVER_2515 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2515 (Database Engine error)
ms.assetid: af93aa29-70c9-4923-90af-aafadb20c1c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73b2d8b8ff01b97428ba6149f537d96044c6ae3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729518"
---
# <a name="mssqlserver_2515"></a><span data-ttu-id="f5c9d-102">MSSQLSERVER_2515</span><span class="sxs-lookup"><span data-stu-id="f5c9d-102">MSSQLSERVER_2515</span></span>
    
## <a name="details"></a><span data-ttu-id="f5c9d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="f5c9d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5c9d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="f5c9d-104">Product Name</span></span>|<span data-ttu-id="f5c9d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5c9d-105">SQL Server</span></span>|  
|<span data-ttu-id="f5c9d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f5c9d-106">Event ID</span></span>|<span data-ttu-id="f5c9d-107">2515</span><span class="sxs-lookup"><span data-stu-id="f5c9d-107">2515</span></span>|  
|<span data-ttu-id="f5c9d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="f5c9d-108">Event Source</span></span>|<span data-ttu-id="f5c9d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f5c9d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f5c9d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="f5c9d-110">Component</span></span>|<span data-ttu-id="f5c9d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f5c9d-111">SQLEngine</span></span>|  
|<span data-ttu-id="f5c9d-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="f5c9d-112">Symbolic Name</span></span>|<span data-ttu-id="f5c9d-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span><span class="sxs-lookup"><span data-stu-id="f5c9d-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span></span>|  
|<span data-ttu-id="f5c9d-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="f5c9d-114">Message Text</span></span>|<span data-ttu-id="f5c9d-115">Страница P_ID с идентификатором объекта O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID и (тип TYPE) была модифицирована, но не помечена как измененная в битовой карте разностного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-115">Page P_ID, object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID type TYPE has been modified but is not marked modified in the differential backup bitmap.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f5c9d-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="f5c9d-116">Explanation</span></span>  
 <span data-ttu-id="f5c9d-117">Регистрационный номер транзакции в журнале (LSN) заданной страницы больше разностного ссылочного номера LSN в BackupManager базы данных или базовой копии для разностного копирования LSN в блоке управления файла, что встречается более часто.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-117">The page specified has a log sequence number (LSN) that is higher than the differential reference LSN in the BackupManager of the database, or the differential base LSN in the file control block of the file, whichever is more recent.</span></span> <span data-ttu-id="f5c9d-118">Однако страница не помечена как измененная в битовой карте разностной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-118">However, the page is not marked as changed in the differential backup bitmap.</span></span>  
  
 <span data-ttu-id="f5c9d-119">Будет обработана только одна страница из каждой базы данных, так как эта проверка проводится только в случаях, когда известно, что в разностной битовой карте отсутствуют ошибки.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-119">Only one page per database will be reported, because this check is only performed when the differential bitmap is known to be error free.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f5c9d-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="f5c9d-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="f5c9d-121">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="f5c9d-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="f5c9d-122">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="f5c9d-123">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="f5c9d-124">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="f5c9d-125">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="f5c9d-126">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="f5c9d-127">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="f5c9d-128">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="f5c9d-129">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="f5c9d-130">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="f5c9d-130">Restore from Backup</span></span>  
 <span data-ttu-id="f5c9d-131">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="f5c9d-132">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="f5c9d-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="f5c9d-133">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="f5c9d-134">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="f5c9d-135">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f5c9d-136">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="f5c9d-137">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="f5c9d-138">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="f5c9d-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="f5c9d-139">Выполнение инструкции REPAIR сделает недействительными разностные битовые карты.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-139">Running REPAIR will invalidate the differential bitmap.</span></span> <span data-ttu-id="f5c9d-140">Нельзя выполнить разностное резервное копирование до создания полной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-140">You cannot perform a differential backup until a full database backup is taken.</span></span> <span data-ttu-id="f5c9d-141">Полная резервная копия базы данных обеспечит основу для повторного создания разностной битовой карты.</span><span class="sxs-lookup"><span data-stu-id="f5c9d-141">The full database backup provides a baseline for the differential bitmap to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c9d-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5c9d-142">See Also</span></span>  
 <span data-ttu-id="f5c9d-143">[Создание полной резервной копии базы данных (SQL Server)](../backup-restore/create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5c9d-143">[Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="f5c9d-144">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="f5c9d-144">MSSQLSERVER_2516</span></span>](mssqlserver-2516-database-engine-error.md)  
  
  
