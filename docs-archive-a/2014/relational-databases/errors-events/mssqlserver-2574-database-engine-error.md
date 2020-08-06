---
title: MSSQLSERVER_2574 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2574 (Database Engine error)
ms.assetid: efba507a-b5ad-4f1d-b0c8-f73b663a0562
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fd103f8c651ca968ae997ae9c3d544b41cbf3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729510"
---
# <a name="mssqlserver_2574"></a><span data-ttu-id="a5cc8-102">MSSQLSERVER_2574</span><span class="sxs-lookup"><span data-stu-id="a5cc8-102">MSSQLSERVER_2574</span></span>
    
## <a name="details"></a><span data-ttu-id="a5cc8-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a5cc8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5cc8-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a5cc8-104">Product Name</span></span>|<span data-ttu-id="a5cc8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5cc8-105">SQL Server</span></span>|  
|<span data-ttu-id="a5cc8-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a5cc8-106">Event ID</span></span>|<span data-ttu-id="a5cc8-107">2574</span><span class="sxs-lookup"><span data-stu-id="a5cc8-107">2574</span></span>|  
|<span data-ttu-id="a5cc8-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a5cc8-108">Event Source</span></span>|<span data-ttu-id="a5cc8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a5cc8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a5cc8-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a5cc8-110">Component</span></span>|<span data-ttu-id="a5cc8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a5cc8-111">SQLEngine</span></span>|  
|<span data-ttu-id="a5cc8-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a5cc8-112">Symbolic Name</span></span>|<span data-ttu-id="a5cc8-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span><span class="sxs-lookup"><span data-stu-id="a5cc8-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span></span>|  
|<span data-ttu-id="a5cc8-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a5cc8-114">Message Text</span></span>|<span data-ttu-id="a5cc8-115">Ошибка таблицы: страница P_ID пуста в объекте с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE).</span><span class="sxs-lookup"><span data-stu-id="a5cc8-115">Table error: Page P_ID is empty in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="a5cc8-116">Это недопустимо на LEVEL уровне сбалансированного дерева.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-116">This is not permitted at level LEVEL of the B-tree.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a5cc8-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a5cc8-117">Explanation</span></span>  
 <span data-ttu-id="a5cc8-118">Страница сбалансированного дерева над конечным уровнем указанного индекса пуста, следовательно, не содержит строк.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-118">A B-tree page above the leaf level of the specified index is empty, that is it has no rows.</span></span> <span data-ttu-id="a5cc8-119">В [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] такое поведение возможно для страниц конечного уровня, но невозможно на уровнях дерева.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-119">This behavior is possible for leaf-level pages in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but has never been possible in tree levels.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a5cc8-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a5cc8-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a5cc8-121">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="a5cc8-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a5cc8-122">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a5cc8-123">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a5cc8-124">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a5cc8-125">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a5cc8-126">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a5cc8-127">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a5cc8-128">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a5cc8-129">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a5cc8-130">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="a5cc8-130">Restore from Backup</span></span>  
 <span data-ttu-id="a5cc8-131">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a5cc8-132">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a5cc8-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a5cc8-133">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="a5cc8-134">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="a5cc8-135">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a5cc8-136">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="a5cc8-137">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="a5cc8-138">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="a5cc8-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="a5cc8-139">Инструкция DBCC перестроит индекс.</span><span class="sxs-lookup"><span data-stu-id="a5cc8-139">DBCC will rebuild the index.</span></span>  
  
  
