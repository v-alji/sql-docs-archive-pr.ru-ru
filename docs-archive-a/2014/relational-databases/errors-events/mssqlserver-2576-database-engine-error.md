---
title: MSSQLSERVER_2576 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2576 (Database Engine error)
ms.assetid: b727cc2f-c76c-46f8-bbbe-5e7a05a6eabf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f378051c7844bf08d617db56666d69b22ecf732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657797"
---
# <a name="mssqlserver_2576"></a><span data-ttu-id="9ca2a-102">MSSQLSERVER_2576</span><span class="sxs-lookup"><span data-stu-id="9ca2a-102">MSSQLSERVER_2576</span></span>
    
## <a name="details"></a><span data-ttu-id="9ca2a-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="9ca2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ca2a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="9ca2a-104">Product Name</span></span>|<span data-ttu-id="9ca2a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ca2a-105">SQL Server</span></span>|  
|<span data-ttu-id="9ca2a-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="9ca2a-106">Event ID</span></span>|<span data-ttu-id="9ca2a-107">2576</span><span class="sxs-lookup"><span data-stu-id="9ca2a-107">2576</span></span>|  
|<span data-ttu-id="9ca2a-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="9ca2a-108">Event Source</span></span>|<span data-ttu-id="9ca2a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9ca2a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9ca2a-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="9ca2a-110">Component</span></span>|<span data-ttu-id="9ca2a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9ca2a-111">SQLEngine</span></span>|  
|<span data-ttu-id="9ca2a-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="9ca2a-112">Symbolic Name</span></span>|<span data-ttu-id="9ca2a-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="9ca2a-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="9ca2a-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="9ca2a-114">Message Text</span></span>|<span data-ttu-id="9ca2a-115">На страницу карты распределения индекса (IAM) P_ID1 указывает предыдущий указатель IAM-страницы P_ID2 в объекте с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE), но это не было обнаружено в ходе просмотра.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-115">The Index Allocation Map (IAM) page P_ID1 is pointed to by the previous pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9ca2a-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="9ca2a-116">Explanation</span></span>  
 <span data-ttu-id="9ca2a-117">Несмотря на то, что существует ссылка на данную страницу в виде находящейся на другой IAM-странице в IAM-цепочке ссылки на предыдущую страницу, страница карты распределения индекса (IAM) или запись метаданных обнаружены не были.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-117">An Index Allocation Map (IAM) page or metadata entry was not located, even though a reference to the page exists as the previous page link on another IAM page in an IAM chain.</span></span> <span data-ttu-id="9ca2a-118">Если страница *P_ID1* имеет значение (0:0), то IAM-страница *P_ID2* является началом IAM-цепочки, при этом запись метаданных для IAM-цепочки отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-118">If the *P_ID1* page is (0:0), the IAM page, *P_ID2*, is the start of an IAM chain, and the metadata entry for the IAM chain is missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9ca2a-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="9ca2a-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="9ca2a-120">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="9ca2a-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="9ca2a-121">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="9ca2a-122">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="9ca2a-123">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="9ca2a-124">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="9ca2a-125">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="9ca2a-126">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="9ca2a-127">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="9ca2a-128">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="9ca2a-129">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="9ca2a-129">Restore from Backup</span></span>  
 <span data-ttu-id="9ca2a-130">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="9ca2a-131">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="9ca2a-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="9ca2a-132">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="9ca2a-133">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="9ca2a-134">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9ca2a-135">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="9ca2a-136">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="9ca2a-137">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="9ca2a-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="9ca2a-138">Инструкция REPAIR попытается перестроить IAM-цепочку, содержащую страницу *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-138">REPAIR will try to rebuild the IAM chain involving the *P_ID2* page.</span></span> <span data-ttu-id="9ca2a-139">Во время перестроения цепочки возможно удаление страниц из цепочки, либо удаление всей цепочки в случае повреждения метаданных.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-139">Rebuilding the chain may involve removing pages from the chain, or removing the whole chain if the metadata is corrupted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9ca2a-140">Эта операция может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="9ca2a-140">This repair may cause data loss.</span></span>  
  
  
