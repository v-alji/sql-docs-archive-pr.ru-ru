---
title: MSSQLSERVER_2512 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2512 (Database Engine error)
ms.assetid: 989b527f-5b02-403c-9b7f-51580f4e7688
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da121c8b49ab8290c494d33f0f2a0ba6fded9e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730713"
---
# <a name="mssqlserver_2512"></a><span data-ttu-id="48fad-102">MSSQLSERVER_2512</span><span class="sxs-lookup"><span data-stu-id="48fad-102">MSSQLSERVER_2512</span></span>
    
## <a name="details"></a><span data-ttu-id="48fad-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="48fad-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48fad-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="48fad-104">Product Name</span></span>|<span data-ttu-id="48fad-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="48fad-105">SQL Server</span></span>|  
|<span data-ttu-id="48fad-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="48fad-106">Event ID</span></span>|<span data-ttu-id="48fad-107">2512</span><span class="sxs-lookup"><span data-stu-id="48fad-107">2512</span></span>|  
|<span data-ttu-id="48fad-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="48fad-108">Event Source</span></span>|<span data-ttu-id="48fad-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="48fad-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="48fad-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="48fad-110">Component</span></span>|<span data-ttu-id="48fad-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="48fad-111">SQLEngine</span></span>|  
|<span data-ttu-id="48fad-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="48fad-112">Symbolic Name</span></span>|<span data-ttu-id="48fad-113">DBCC_DUPLICATE_KEYS</span><span class="sxs-lookup"><span data-stu-id="48fad-113">DBCC_DUPLICATE_KEYS</span></span>|  
|<span data-ttu-id="48fad-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="48fad-114">Message Text</span></span>|<span data-ttu-id="48fad-115">Ошибка таблицы: идентификатор объекта O_ID, идентификатор индекса I_ID, идентификатор секции PN_ID, идентификатор единицы распределения A_ID (тип TYPE).</span><span class="sxs-lookup"><span data-stu-id="48fad-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="48fad-116">Повторяющиеся ключи на странице P_ID1, область памяти SLOT1, и странице P_ID2, область памяти SLOT2.</span><span class="sxs-lookup"><span data-stu-id="48fad-116">Duplicate keys on page P_ID1 slot SLOT1 and page P_ID2 slot SLOT2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="48fad-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="48fad-117">Explanation</span></span>  
 <span data-ttu-id="48fad-118">Две указанные области памяти обладают одинаковыми ключами, возможно, типа `uniqueifiers`.</span><span class="sxs-lookup"><span data-stu-id="48fad-118">The two specified slots have identical keys, including any `uniqueifiers`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="48fad-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="48fad-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="48fad-120">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="48fad-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="48fad-121">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="48fad-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="48fad-122">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="48fad-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="48fad-123">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="48fad-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="48fad-124">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="48fad-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="48fad-125">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="48fad-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="48fad-126">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="48fad-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="48fad-127">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="48fad-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="48fad-128">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="48fad-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="48fad-129">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="48fad-129">Restore from Backup</span></span>  
 <span data-ttu-id="48fad-130">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="48fad-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="48fad-131">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="48fad-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="48fad-132">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="48fad-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="48fad-133">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="48fad-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="48fad-134">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="48fad-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="48fad-135">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="48fad-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="48fad-136">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="48fad-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="48fad-137">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="48fad-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="48fad-138">Если запись является фантомной или индекс не является уникальным, то DBCC может исправить эту проблему при помощи перестройки индекса.</span><span class="sxs-lookup"><span data-stu-id="48fad-138">If either record is a ghost or the index is nonunique, DBCC can repair this problem by rebuilding the index.</span></span> <span data-ttu-id="48fad-139">В противном случае, если это необходимо, REPAIR может удалить область памяти *SLOT2* на странице *P_ID2* или отметить эту область памяти как фантомную.</span><span class="sxs-lookup"><span data-stu-id="48fad-139">Otherwise, if necessary, REPAIR will delete slot *SLOT2* on page *P_ID2* or mark the slot as a ghost.</span></span>  
  
  
