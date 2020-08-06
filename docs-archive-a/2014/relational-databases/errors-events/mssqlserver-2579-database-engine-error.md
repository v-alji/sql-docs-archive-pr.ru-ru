---
title: MSSQLSERVER_2579 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2579 (Database Engine error)
ms.assetid: 8f929d69-8eb4-4fe9-be52-b9680a7820db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e68cd090ff9d20b14b3456dcda66496fc2bc02d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667123"
---
# <a name="mssqlserver_2579"></a><span data-ttu-id="66868-102">MSSQLSERVER_2579</span><span class="sxs-lookup"><span data-stu-id="66868-102">MSSQLSERVER_2579</span></span>
    
## <a name="details"></a><span data-ttu-id="66868-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="66868-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66868-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="66868-104">Product Name</span></span>|<span data-ttu-id="66868-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="66868-105">SQL Server</span></span>|  
|<span data-ttu-id="66868-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="66868-106">Event ID</span></span>|<span data-ttu-id="66868-107">2579</span><span class="sxs-lookup"><span data-stu-id="66868-107">2579</span></span>|  
|<span data-ttu-id="66868-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="66868-108">Event Source</span></span>|<span data-ttu-id="66868-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="66868-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="66868-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="66868-110">Component</span></span>|<span data-ttu-id="66868-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="66868-111">SQLEngine</span></span>|  
|<span data-ttu-id="66868-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="66868-112">Symbolic Name</span></span>|<span data-ttu-id="66868-113">DBCC_EXTENT_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="66868-113">DBCC_EXTENT_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="66868-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="66868-114">Message Text</span></span>|<span data-ttu-id="66868-115">Ошибка таблицы: экстент P_ID в объекте с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE) выходит за пределы диапазона для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="66868-115">Table error: Extent P_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) is beyond the range of this database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="66868-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="66868-116">Explanation</span></span>  
 <span data-ttu-id="66868-117">*P_ID* является идентификатором страницы в формате *(номер_файла:страница_в_файле)* .</span><span class="sxs-lookup"><span data-stu-id="66868-117">*P_ID* is a PageID of the form *(filenum:pageinfile)*.</span></span> <span data-ttu-id="66868-118">Значение параметра *страница_в_файле* для этой области памяти превышает физический размер файла базы данных (*номер_файла*).</span><span class="sxs-lookup"><span data-stu-id="66868-118">The *pageinfile* of this extent is greater than the physical size of the file (*filenum)* of the database.</span></span> <span data-ttu-id="66868-119">Экстент отмечен как выделенный на IAM-странице для указанного идентификатора единицы распределения.</span><span class="sxs-lookup"><span data-stu-id="66868-119">The extent is marked as being allocated in an IAM page for the indicated allocation unit ID.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66868-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="66868-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="66868-121">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="66868-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="66868-122">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="66868-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="66868-123">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="66868-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="66868-124">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="66868-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="66868-125">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="66868-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="66868-126">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="66868-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="66868-127">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="66868-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="66868-128">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="66868-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="66868-129">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="66868-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="66868-130">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="66868-130">Restore from Backup</span></span>  
 <span data-ttu-id="66868-131">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="66868-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="66868-132">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="66868-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="66868-133">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="66868-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="66868-134">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="66868-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="66868-135">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="66868-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="66868-136">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="66868-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="66868-137">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="66868-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="66868-138">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="66868-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="66868-139">Запуск REPAIR приведет к отмене выделения экстента для IAM-страницы.</span><span class="sxs-lookup"><span data-stu-id="66868-139">Running REPAIR will cause the extent to be deallocated from the IAM page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="66868-140">Эта операция может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="66868-140">This repair may cause data loss.</span></span>  
  
  
