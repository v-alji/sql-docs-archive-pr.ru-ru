---
title: MSSQLSERVER_2534 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2534 (Database Engine error)
ms.assetid: 121cf99d-0722-494c-be24-3369c1a0badc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 409c429f961cd8357bfa2e40663c33f3c1f2e36d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667140"
---
# <a name="mssqlserver_2534"></a><span data-ttu-id="831be-102">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="831be-102">MSSQLSERVER_2534</span></span>
    
## <a name="details"></a><span data-ttu-id="831be-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="831be-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="831be-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="831be-104">Product Name</span></span>|<span data-ttu-id="831be-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="831be-105">SQL Server</span></span>|  
|<span data-ttu-id="831be-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="831be-106">Event ID</span></span>|<span data-ttu-id="831be-107">2534</span><span class="sxs-lookup"><span data-stu-id="831be-107">2534</span></span>|  
|<span data-ttu-id="831be-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="831be-108">Event Source</span></span>|<span data-ttu-id="831be-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="831be-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="831be-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="831be-110">Component</span></span>|<span data-ttu-id="831be-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="831be-111">SQLEngine</span></span>|  
|<span data-ttu-id="831be-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="831be-112">Symbolic Name</span></span>|<span data-ttu-id="831be-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span><span class="sxs-lookup"><span data-stu-id="831be-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span></span>|  
|<span data-ttu-id="831be-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="831be-114">Message Text</span></span>|<span data-ttu-id="831be-115">Ошибка таблицы: страница P_ID, заголовок которой указывает, что она выделена для идентификатора объекта O_ID, идентификатора индекса I_ID, идентификатора секции PN_ID, идентификатора единицы распределения A_ID (тип TYPE), выделена другим объектом.</span><span class="sxs-lookup"><span data-stu-id="831be-115">Table error: Page P_ID, whose header indicates it as being allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), is allocated by another object.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="831be-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="831be-116">Explanation</span></span>  
 <span data-ttu-id="831be-117">Заголовок страницы содержит идентификатор единицы распределения *A_ID*, но ни одна из страниц карты распределения индексов для этой единицы распределения не выделяет эту страницу.</span><span class="sxs-lookup"><span data-stu-id="831be-117">The header of the page contains the allocation unit ID, *A_ID*, but none of the Index Allocation Map (IAM) pages of that allocation unit allocates the page.</span></span> <span data-ttu-id="831be-118">Следовательно, заголовок содержит неверный идентификатор единицы распределения, и на странице появится совпадающая ошибка MSSQLServer_2533, которая соответствует идентификатору единицы распределения, которая на самом деле распределяет данную страницу.</span><span class="sxs-lookup"><span data-stu-id="831be-118">Therefore, the header of the page contains the wrong allocation unit ID, and the page will have a matching MSSQLServer_2533 error that corresponds to the allocation unit ID to which the page is actually allocated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="831be-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="831be-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="831be-120">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="831be-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="831be-121">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="831be-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="831be-122">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="831be-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="831be-123">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="831be-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="831be-124">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="831be-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="831be-125">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="831be-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="831be-126">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="831be-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="831be-127">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="831be-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="831be-128">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="831be-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="831be-129">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="831be-129">Restore from Backup</span></span>  
 <span data-ttu-id="831be-130">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="831be-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="831be-131">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="831be-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="831be-132">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="831be-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="831be-133">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="831be-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="831be-134">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="831be-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="831be-135">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="831be-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="831be-136">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="831be-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="831be-137">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="831be-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="831be-138">REPAIR будет перестраивать индекс, если индекс существует.</span><span class="sxs-lookup"><span data-stu-id="831be-138">REPAIR will rebuild the index if an index exists.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="831be-139">Запуск REPAIR для соответствующей ошибки [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) освобождает страницу перед перестройкой.</span><span class="sxs-lookup"><span data-stu-id="831be-139">Running REPAIR for the matching [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) error deallocates the page before the rebuild.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="831be-140">Эта операция может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="831be-140">This repair may cause data loss.</span></span>  
  
  
