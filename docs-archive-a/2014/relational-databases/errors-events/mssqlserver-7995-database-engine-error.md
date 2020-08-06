---
title: MSSQLSERVER_7995 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7995 (Database Engine error)
ms.assetid: af6d6322-3cba-43d8-be97-e6ef15f8c933
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c65cf2b16c4d7a0dcf40272f8280205a111d08e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664911"
---
# <a name="mssqlserver_7995"></a><span data-ttu-id="224a0-102">MSSQLSERVER_7995</span><span class="sxs-lookup"><span data-stu-id="224a0-102">MSSQLSERVER_7995</span></span>
    
## <a name="details"></a><span data-ttu-id="224a0-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="224a0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="224a0-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="224a0-104">Product Name</span></span>|<span data-ttu-id="224a0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="224a0-105">SQL Server</span></span>|  
|<span data-ttu-id="224a0-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="224a0-106">Event ID</span></span>|<span data-ttu-id="224a0-107">7995</span><span class="sxs-lookup"><span data-stu-id="224a0-107">7995</span></span>|  
|<span data-ttu-id="224a0-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="224a0-108">Event Source</span></span>|<span data-ttu-id="224a0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="224a0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="224a0-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="224a0-110">Component</span></span>|<span data-ttu-id="224a0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="224a0-111">SQLEngine</span></span>|  
|<span data-ttu-id="224a0-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="224a0-112">Symbolic Name</span></span>|<span data-ttu-id="224a0-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="224a0-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span></span>|  
|<span data-ttu-id="224a0-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="224a0-114">Message Text</span></span>|<span data-ttu-id="224a0-115">База данных «DBNAME»: ошибки согласованности в системных каталогах препятствуют дальнейшей обработке DBCC CHECKNAME.</span><span class="sxs-lookup"><span data-stu-id="224a0-115">Database 'DBNAME': consistency errors in system catalogs prevent further DBCC CHECKNAME processing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="224a0-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="224a0-116">Explanation</span></span>  
 <span data-ttu-id="224a0-117">Обработка команды DBCC CHECKDB состоит из следующих трех этапов.</span><span class="sxs-lookup"><span data-stu-id="224a0-117">The DBCC CHECKDB process consists of the following three stages:</span></span>  
  
1.  <span data-ttu-id="224a0-118">Проверка выделенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="224a0-118">Allocation checks.</span></span> <span data-ttu-id="224a0-119">Это равносильно запуску команды DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="224a0-119">This is equivalent to running DBCC CHECKALLOC.</span></span>  
  
2.  <span data-ttu-id="224a0-120">Проверка согласованности системных базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="224a0-120">System tables consistency checks.</span></span> <span data-ttu-id="224a0-121">Это равносильно запуску команды DBCC CHECKTABLE для небольшого количества необходимых системных базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="224a0-121">This is equivalent to running DBCC CHECKTABLE on a small list of necessary system base tables.</span></span>  
  
3.  <span data-ttu-id="224a0-122">Полная проверка согласованности базы данных.</span><span class="sxs-lookup"><span data-stu-id="224a0-122">Complete database consistency checks.</span></span>  
  
 <span data-ttu-id="224a0-123">Ошибка MSSQLEngine_7995 возникает на втором этапе, когда команда DBCC CHECKDB находит ошибки, которые она не может исправить, или команда, для которой параметр REPAIR не определен.</span><span class="sxs-lookup"><span data-stu-id="224a0-123">MSSQLEngine_7995 is raised in stage 2 to indicate that DBCC CHECKDB has found errors that the command cannot repair or that REPAIR has not been specified.</span></span> <span data-ttu-id="224a0-124">Команда DBCC CHECKDB не может перейти к этапу 3, так как соответствующие базовые системные таблицы хранят метаданные всех объектов базы данных, либо повреждены.</span><span class="sxs-lookup"><span data-stu-id="224a0-124">DBCC CHECKDB cannot continue with stage 3 because either the system base tables in question store the metadata for all objects in the database or the system base tables are corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="224a0-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="224a0-125">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="224a0-126">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="224a0-126">Look for Hardware Failure</span></span>  
 <span data-ttu-id="224a0-127">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="224a0-127">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="224a0-128">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="224a0-128">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="224a0-129">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="224a0-129">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="224a0-130">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="224a0-130">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="224a0-131">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="224a0-131">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="224a0-132">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="224a0-132">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="224a0-133">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="224a0-133">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="224a0-134">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="224a0-134">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="224a0-135">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="224a0-135">Restore from Backup</span></span>  
 <span data-ttu-id="224a0-136">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="224a0-136">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="224a0-137">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="224a0-137">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="224a0-138">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="224a0-138">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="224a0-139">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="224a0-139">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="224a0-140">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="224a0-140">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="224a0-141">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="224a0-141">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="224a0-142">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="224a0-142">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="224a0-143">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="224a0-143">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="224a0-144">Изучите список ошибок и действия, производимые инструкцией REPAIR для их исправления.</span><span class="sxs-lookup"><span data-stu-id="224a0-144">Examine the list of errors to see what REPAIR will do for each.</span></span>  
  
  
