---
title: MSSQLSERVER_ 2577 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2577 (Database Engine error)
ms.assetid: f53256a2-2fb0-47fd-9ed9-c45389104145
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9e4b7b85f59ba721eae6b4a0ac8db1b2d288422d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667127"
---
# <a name="mssqlserver_2577"></a><span data-ttu-id="1e6b3-102">MSSQLSERVER_2577</span><span class="sxs-lookup"><span data-stu-id="1e6b3-102">MSSQLSERVER_2577</span></span>
    
## <a name="details"></a><span data-ttu-id="1e6b3-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1e6b3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e6b3-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1e6b3-104">Product Name</span></span>|<span data-ttu-id="1e6b3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1e6b3-105">SQL Server</span></span>|  
|<span data-ttu-id="1e6b3-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1e6b3-106">Event ID</span></span>|<span data-ttu-id="1e6b3-107">2577</span><span class="sxs-lookup"><span data-stu-id="1e6b3-107">2577</span></span>|  
|<span data-ttu-id="1e6b3-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1e6b3-108">Event Source</span></span>|<span data-ttu-id="1e6b3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1e6b3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1e6b3-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1e6b3-110">Component</span></span>|<span data-ttu-id="1e6b3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1e6b3-111">SQLEngine</span></span>|  
|<span data-ttu-id="1e6b3-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1e6b3-112">Symbolic Name</span></span>|<span data-ttu-id="1e6b3-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="1e6b3-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="1e6b3-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1e6b3-114">Message Text</span></span>|<span data-ttu-id="1e6b3-115">Перепутаны порядковые номера в цепочке карты распределения индекса (IAM) для объекта с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE).</span><span class="sxs-lookup"><span data-stu-id="1e6b3-115">Chain sequence numbers out of order in the Index Allocation Map (IAM) chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="1e6b3-116">Страница P_ID1 с порядковым номером SEQUENCE1 указывает на страницу P_ID2 с порядковым номером SEQUENCE2.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-116">Page P_ID1 with sequence number SEQUENCE1 points to page P_ID2 with sequence number SEQUENCE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1e6b3-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1e6b3-117">Explanation</span></span>  
 <span data-ttu-id="1e6b3-118">Каждая страница карты распределения индекса (IAM) имеет свой порядковый номер.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-118">Every Index Allocation Map (IAM) page has a sequence number.</span></span> <span data-ttu-id="1e6b3-119">Порядковый номер является положением IAM-страницы в цепочке IAM.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-119">The sequence number is the position of the IAM page within the IAM chain.</span></span> <span data-ttu-id="1e6b3-120">Порядковые номера IAM-страниц отличаются на единицу.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-120">The rule is that sequence numbers increase by one for each IAM page.</span></span> <span data-ttu-id="1e6b3-121">IAM-страница с индексом *P_ID2* имеет порядковый номер, который является исключением из этого правила.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-121">IAM page, *P_ID2*, has a sequence number that does not follow this rule.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e6b3-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1e6b3-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="1e6b3-123">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="1e6b3-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="1e6b3-124">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="1e6b3-125">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="1e6b3-126">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="1e6b3-127">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="1e6b3-128">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="1e6b3-129">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="1e6b3-130">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="1e6b3-131">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="1e6b3-132">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="1e6b3-132">Restore from Backup</span></span>  
 <span data-ttu-id="1e6b3-133">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="1e6b3-134">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="1e6b3-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="1e6b3-135">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-135">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="1e6b3-136">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-136">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="1e6b3-137">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-137">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1e6b3-138">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-138">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="1e6b3-139">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-139">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="1e6b3-140">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="1e6b3-140">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="1e6b3-141">При выполнении инструкции REPAIR перестраивается цепочка IAM.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-141">Running REPAIR will rebuild the IAM chain.</span></span> <span data-ttu-id="1e6b3-142">Вначале инструкция REPAIR делит существующую цепочку IAM на две половины.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-142">REPAIR first splits the existing IAM chain in two halves.</span></span> <span data-ttu-id="1e6b3-143">Первая половина цепочки заканчивается IAM-страницей с индексом *P_ID1*.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-143">The first half of the chain will end with IAM page, *P_ID1*.</span></span> <span data-ttu-id="1e6b3-144">Указатель на следующую страницу страницы с индексом *P_ID1* устанавливается в значение (0:0).</span><span class="sxs-lookup"><span data-stu-id="1e6b3-144">The next page pointer of the *P_ID1* page will be set to (0:0).</span></span> <span data-ttu-id="1e6b3-145">Вторая половина цепочки начинается IAM-страницей с индексом *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-145">The second half of the chain will start with IAM page, *P_ID2*.</span></span> <span data-ttu-id="1e6b3-146">Указатель на предыдущую страницу устанавливается для страницы с индексом *P_ID2* в значение (0:0).</span><span class="sxs-lookup"><span data-stu-id="1e6b3-146">The previous page pointer of the *P_ID2* page will be set to (0:0).</span></span>  
  
 <span data-ttu-id="1e6b3-147">После этого инструкция REPAIR соединяет две половины цепи и повторно формирует порядковые номера цепочки IAM.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-147">REPAIR will then connect the two haves of the chain together and regenerate the sequence numbers for the IAM chain.</span></span> <span data-ttu-id="1e6b3-148">Любые IAM-страницы, которые невозможно исправить, будут освобождены.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-148">Any IAM pages that cannot be repaired will be deallocated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1e6b3-149">Эта операция может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="1e6b3-149">This repair may cause data loss.</span></span>  
  
  
