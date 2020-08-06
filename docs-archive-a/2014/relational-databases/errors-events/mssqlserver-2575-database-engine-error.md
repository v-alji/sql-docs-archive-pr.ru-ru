---
title: MSSQLSERVER_2575 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2575 (Database Engine error)
ms.assetid: 92dfe449-a122-4730-942b-e1d319862d20
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 461d2b57b5ace98ca624f8dc3717c98f3e9e4d67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655238"
---
# <a name="mssqlserver_2575"></a><span data-ttu-id="cfdd6-102">MSSQLSERVER_2575</span><span class="sxs-lookup"><span data-stu-id="cfdd6-102">MSSQLSERVER_2575</span></span>
    
## <a name="details"></a><span data-ttu-id="cfdd6-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="cfdd6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfdd6-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="cfdd6-104">Product Name</span></span>|<span data-ttu-id="cfdd6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfdd6-105">SQL Server</span></span>|  
|<span data-ttu-id="cfdd6-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="cfdd6-106">Event ID</span></span>|<span data-ttu-id="cfdd6-107">2575</span><span class="sxs-lookup"><span data-stu-id="cfdd6-107">2575</span></span>|  
|<span data-ttu-id="cfdd6-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="cfdd6-108">Event Source</span></span>|<span data-ttu-id="cfdd6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cfdd6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cfdd6-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="cfdd6-110">Component</span></span>|<span data-ttu-id="cfdd6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cfdd6-111">SQLEngine</span></span>|  
|<span data-ttu-id="cfdd6-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="cfdd6-112">Symbolic Name</span></span>|<span data-ttu-id="cfdd6-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="cfdd6-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="cfdd6-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="cfdd6-114">Message Text</span></span>|<span data-ttu-id="cfdd6-115">На IAM-страницу P_ID1 указывает следующий указатель IAM-страницы P_ID2 в идентификаторе объекта O_ID с идентификатором индекса I_ID, идентификатором секции PN_ID и идентификатором единицы распределения A_ID (тип TYPE), однако эта страница не была обнаружена в ходе просмотра.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-115">IAM page P_ID1 is pointed to by the next pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cfdd6-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="cfdd6-116">Explanation</span></span>  
 <span data-ttu-id="cfdd6-117">Страница карты распределения индекса (IAM) для указанного индекса найдена, однако не найдена IAM-страница для указателя следующей страницы.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-117">An Index Allocation Map (IAM) page was found for the specified index; however, the IAM page for its next-page pointer was not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cfdd6-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="cfdd6-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="cfdd6-119">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="cfdd6-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="cfdd6-120">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="cfdd6-121">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="cfdd6-122">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="cfdd6-123">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="cfdd6-124">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="cfdd6-125">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="cfdd6-126">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="cfdd6-127">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="cfdd6-128">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="cfdd6-128">Restore from Backup</span></span>  
 <span data-ttu-id="cfdd6-129">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="cfdd6-130">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="cfdd6-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="cfdd6-131">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-131">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="cfdd6-132">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-132">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="cfdd6-133">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-133">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="cfdd6-134">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-134">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="cfdd6-135">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-135">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="cfdd6-136">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="cfdd6-136">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="cfdd6-137">Инструкция DBCC перестроит индекс.</span><span class="sxs-lookup"><span data-stu-id="cfdd6-137">DBCC will rebuild the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfdd6-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfdd6-138">See Also</span></span>  
 [<span data-ttu-id="cfdd6-139">DBCC CHECKDB (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cfdd6-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
