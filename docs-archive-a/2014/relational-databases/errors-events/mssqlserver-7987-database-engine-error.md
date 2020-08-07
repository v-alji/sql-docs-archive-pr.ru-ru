---
title: MSSQLSERVER_7987 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7987 (Database Engine error)
ms.assetid: 314aebf1-6cdf-488d-a274-ce967fadb57b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2fec3cf707e2e9923084f48096a88c60655513e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732686"
---
# <a name="mssqlserver_7987"></a><span data-ttu-id="2ad64-102">MSSQLSERVER_7987</span><span class="sxs-lookup"><span data-stu-id="2ad64-102">MSSQLSERVER_7987</span></span>
    
## <a name="details"></a><span data-ttu-id="2ad64-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="2ad64-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ad64-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="2ad64-104">Product Name</span></span>|<span data-ttu-id="2ad64-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ad64-105">SQL Server</span></span>|  
|<span data-ttu-id="2ad64-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="2ad64-106">Event ID</span></span>|<span data-ttu-id="2ad64-107">7987</span><span class="sxs-lookup"><span data-stu-id="2ad64-107">7987</span></span>|  
|<span data-ttu-id="2ad64-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="2ad64-108">Event Source</span></span>|<span data-ttu-id="2ad64-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2ad64-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2ad64-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="2ad64-110">Component</span></span>|<span data-ttu-id="2ad64-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2ad64-111">SQLEngine</span></span>|  
|<span data-ttu-id="2ad64-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="2ad64-112">Symbolic Name</span></span>|<span data-ttu-id="2ad64-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="2ad64-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span></span>|  
|<span data-ttu-id="2ad64-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="2ad64-114">Message Text</span></span>|<span data-ttu-id="2ad64-115">Предварительная проверка системных таблиц: идентификатор объекта O_ID содержит ошибку в цепочке ссылок.</span><span class="sxs-lookup"><span data-stu-id="2ad64-115">System table pre-checks: Object ID O_ID has chain linkage mismatch.</span></span> <span data-ttu-id="2ad64-116">P_ID1->next = P_ID2, но P_ID2->prev = P_ID3.</span><span class="sxs-lookup"><span data-stu-id="2ad64-116">P_ID1->next = P_ID2, but P_ID2->prev = P_ID3.</span></span> <span data-ttu-id="2ad64-117">Инструкция проверки прервана из-за непоправимой ошибки.</span><span class="sxs-lookup"><span data-stu-id="2ad64-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2ad64-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="2ad64-118">Explanation</span></span>  
 <span data-ttu-id="2ad64-119">Первый этап работы DBCC CHECKDB заключается в осуществлении примитивных проверок страниц данных важных системных таблиц.</span><span class="sxs-lookup"><span data-stu-id="2ad64-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="2ad64-120">Найденные на этом этапе ошибки не подлежат исправлению, поэтому при их обнаружении DBCC CHECKDB немедленно прекращает свою работу.</span><span class="sxs-lookup"><span data-stu-id="2ad64-120">If any errors are found, they cannot be repaired; therefore, the DBCC CHECKDB terminates immediately.</span></span>  
  
 <span data-ttu-id="2ad64-121">Указатель следующей страницы на странице *P_ID1* указывает на страницу *P_ID2*, однако указатель предыдущей страницы на странице *P_ID2* указывает на страницу *P_ID3*, а не обратно на страницу *P_ID1*, как должно быть.</span><span class="sxs-lookup"><span data-stu-id="2ad64-121">The next page pointer of page *P_ID1* points to page *P_ID2*; however, the previous page pointer of page *P_ID2* points to page *P_ID3* but not back to page *P_ID1*, as it should.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ad64-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="2ad64-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="2ad64-123">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="2ad64-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="2ad64-124">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="2ad64-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="2ad64-125">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="2ad64-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="2ad64-126">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="2ad64-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="2ad64-127">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="2ad64-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="2ad64-128">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="2ad64-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="2ad64-129">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="2ad64-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="2ad64-130">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="2ad64-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="2ad64-131">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2ad64-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="2ad64-132">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="2ad64-132">Restore from Backup</span></span>  
 <span data-ttu-id="2ad64-133">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="2ad64-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="2ad64-134">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="2ad64-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="2ad64-135">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="2ad64-135">Not applicable.</span></span> <span data-ttu-id="2ad64-136">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="2ad64-136">This error cannot be repaired automatically.</span></span> <span data-ttu-id="2ad64-137">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ad64-137">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
