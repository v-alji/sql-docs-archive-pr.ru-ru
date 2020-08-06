---
title: MSSQLSERVER_2537 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2537 (Database Engine error)
ms.assetid: 0af6ff69-d75a-4c39-8da2-9bd0695277c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c227867bac5a0ea5789ba653414444d011e5910d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667135"
---
# <a name="mssqlserver_2537"></a><span data-ttu-id="1e601-102">MSSQLSERVER_2537</span><span class="sxs-lookup"><span data-stu-id="1e601-102">MSSQLSERVER_2537</span></span>
    
## <a name="details"></a><span data-ttu-id="1e601-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1e601-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e601-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1e601-104">Product Name</span></span>|<span data-ttu-id="1e601-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1e601-105">SQL Server</span></span>|  
|<span data-ttu-id="1e601-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1e601-106">Event ID</span></span>|<span data-ttu-id="1e601-107">2537</span><span class="sxs-lookup"><span data-stu-id="1e601-107">2537</span></span>|  
|<span data-ttu-id="1e601-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1e601-108">Event Source</span></span>|<span data-ttu-id="1e601-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1e601-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1e601-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1e601-110">Component</span></span>|<span data-ttu-id="1e601-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1e601-111">SQLEngine</span></span>|  
|<span data-ttu-id="1e601-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1e601-112">Symbolic Name</span></span>|<span data-ttu-id="1e601-113">DBCC_RECORD_CHECK_FAILED</span><span class="sxs-lookup"><span data-stu-id="1e601-113">DBCC_RECORD_CHECK_FAILED</span></span>|  
|<span data-ttu-id="1e601-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1e601-114">Message Text</span></span>|<span data-ttu-id="1e601-115">Ошибка таблицы: идентификатор объекта O_ID, идентификатор индекса I_ID, идентификатор секции PN_ID, идентификатор единицы распределения A_ID (тип TYPE), страница P_ID, строка ROW_ID.</span><span class="sxs-lookup"><span data-stu-id="1e601-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page P_ID, row ROW_ID.</span></span> <span data-ttu-id="1e601-116">Проверка записи (CHECK_TEXT) завершилась неудачно.</span><span class="sxs-lookup"><span data-stu-id="1e601-116">Record check (CHECK_TEXT) failed.</span></span> <span data-ttu-id="1e601-117">Значениями являются VALUE1 и VALUE2.</span><span class="sxs-lookup"><span data-stu-id="1e601-117">Values are VALUE1 and VALUE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1e601-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1e601-118">Explanation</span></span>  
 <span data-ttu-id="1e601-119">В строке ROW_ID (или в одном из столбцов в строке) окончилась неудачей проверка или нарушено условие, описанное значением CHECK_TEXT.</span><span class="sxs-lookup"><span data-stu-id="1e601-119">The row ROW_ID (or a column in the row) failed the test or condition described by CHECK_TEXT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e601-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1e601-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="1e601-121">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="1e601-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="1e601-122">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="1e601-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="1e601-123">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="1e601-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="1e601-124">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="1e601-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="1e601-125">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="1e601-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="1e601-126">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="1e601-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="1e601-127">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="1e601-127">If you suspect that write-caching is the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="1e601-128">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="1e601-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="1e601-129">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1e601-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="1e601-130">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="1e601-130">Restore from Backup</span></span>  
 <span data-ttu-id="1e601-131">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="1e601-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="1e601-132">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="1e601-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="1e601-133">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="1e601-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="1e601-134">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="1e601-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="1e601-135">Затем вызовите на выполнение команду DBCC CHECKDB с рекомендуемым предложением REPAIR.</span><span class="sxs-lookup"><span data-stu-id="1e601-135">Then, run DBCC CHECKDB with the recommended REPAIR clause.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1e601-136">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="1e601-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="1e601-137">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="1e601-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="1e601-138">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="1e601-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="1e601-139">REPAIR будет перестраивать индекс, если индекс существует.</span><span class="sxs-lookup"><span data-stu-id="1e601-139">REPAIR will rebuild the index if an index exists.</span></span>  
  
 <span data-ttu-id="1e601-140">**Внимание!**  Эта операция восстановления может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="1e601-140">**Caution** This repair may cause data loss.</span></span>  
  
  
