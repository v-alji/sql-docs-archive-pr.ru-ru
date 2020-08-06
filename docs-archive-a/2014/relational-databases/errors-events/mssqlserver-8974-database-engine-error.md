---
title: MSSQLSERVER_8974 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8974 (Database Engine error)
ms.assetid: 52098678-0858-4a14-ad07-37ebbafca5fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3107f5b62caf04e232532c2d2b93d5da19fb53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669417"
---
# <a name="mssqlserver_8974"></a><span data-ttu-id="4160b-102">MSSQLSERVER_8974</span><span class="sxs-lookup"><span data-stu-id="4160b-102">MSSQLSERVER_8974</span></span>
    
## <a name="details"></a><span data-ttu-id="4160b-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="4160b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4160b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="4160b-104">Product Name</span></span>|<span data-ttu-id="4160b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4160b-105">SQL Server</span></span>|  
|<span data-ttu-id="4160b-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4160b-106">Event ID</span></span>|<span data-ttu-id="4160b-107">8974</span><span class="sxs-lookup"><span data-stu-id="4160b-107">8974</span></span>|  
|<span data-ttu-id="4160b-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="4160b-108">Event Source</span></span>|<span data-ttu-id="4160b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4160b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4160b-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="4160b-110">Component</span></span>|<span data-ttu-id="4160b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4160b-111">SQLEngine</span></span>|  
|<span data-ttu-id="4160b-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="4160b-112">Symbolic Name</span></span>|<span data-ttu-id="4160b-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span><span class="sxs-lookup"><span data-stu-id="4160b-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span></span>|  
|<span data-ttu-id="4160b-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="4160b-114">Message Text</span></span>|<span data-ttu-id="4160b-115">Ошибка таблицы: идентификатор объекта O_ID, идентификатор индекса I_ID, идентификатор секции PN_ID, идентификатор единицы распределения A_ID (тип TYPE).</span><span class="sxs-lookup"><span data-stu-id="4160b-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="4160b-116">На данный внестрочный узел данных на странице P_ID1, область памяти S_ID1, идентификатор текста TEXT_ID, ссылается страница P_ID2, область памяти S_ID2 и страница P_ID3, область памяти P_ID3.</span><span class="sxs-lookup"><span data-stu-id="4160b-116">The off-row data node at page P_ID1, slot S_ID1, text ID TEXT_ID is pointed to by page P_ID2, slot S_ID2 and by page P_ID3, slot P_ID3.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4160b-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="4160b-117">Explanation</span></span>  
 <span data-ttu-id="4160b-118">Во внестрочном узле данных есть две записи данных или индекса, которые фиксируют его как дочерний узел.</span><span class="sxs-lookup"><span data-stu-id="4160b-118">An off-row data node has two data or index records that list it as a child node.</span></span> <span data-ttu-id="4160b-119">У узла может быть только один родительский узел.</span><span class="sxs-lookup"><span data-stu-id="4160b-119">A node can have only one parent node.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4160b-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="4160b-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4160b-121">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="4160b-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4160b-122">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="4160b-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4160b-123">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="4160b-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4160b-124">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="4160b-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4160b-125">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="4160b-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4160b-126">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="4160b-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4160b-127">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="4160b-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4160b-128">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="4160b-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4160b-129">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4160b-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4160b-130">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="4160b-130">Restore from Backup</span></span>  
 <span data-ttu-id="4160b-131">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="4160b-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4160b-132">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4160b-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4160b-133">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="4160b-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="4160b-134">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="4160b-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="4160b-135">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="4160b-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4160b-136">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="4160b-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="4160b-137">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="4160b-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="4160b-138">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="4160b-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="4160b-139">Внестрочный узел данных на странице *P_ID1* будет удален, как и обе ссылки на страницах *P_ID2* и *P_ID3*.</span><span class="sxs-lookup"><span data-stu-id="4160b-139">The off-row data node on page *P_ID1* will be deleted and both references on pages *P_ID2* and *P_ID3* will be deleted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4160b-140">Эта операция может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="4160b-140">This repair might cause data loss.</span></span>  
  
  
