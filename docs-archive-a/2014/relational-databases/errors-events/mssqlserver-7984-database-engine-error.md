---
title: MSSQLSERVER_7984 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7984 (Database Engine error)
ms.assetid: e3192f56-e4e2-41da-b132-65f1e7540b1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7f92fe4f3751621e0cc636ffcd2d4de73b348d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666643"
---
# <a name="mssqlserver_7984"></a><span data-ttu-id="b94cb-102">MSSQLSERVER_7984</span><span class="sxs-lookup"><span data-stu-id="b94cb-102">MSSQLSERVER_7984</span></span>
    
## <a name="details"></a><span data-ttu-id="b94cb-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b94cb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b94cb-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b94cb-104">Product Name</span></span>|<span data-ttu-id="b94cb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b94cb-105">SQL Server</span></span>|  
|<span data-ttu-id="b94cb-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b94cb-106">Event ID</span></span>|<span data-ttu-id="b94cb-107">7984</span><span class="sxs-lookup"><span data-stu-id="b94cb-107">7984</span></span>|  
|<span data-ttu-id="b94cb-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b94cb-108">Event Source</span></span>|<span data-ttu-id="b94cb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b94cb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b94cb-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b94cb-110">Component</span></span>|<span data-ttu-id="b94cb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b94cb-111">SQLEngine</span></span>|  
|<span data-ttu-id="b94cb-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b94cb-112">Symbolic Name</span></span>|<span data-ttu-id="b94cb-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b94cb-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span></span>|  
|<span data-ttu-id="b94cb-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b94cb-114">Message Text</span></span>|<span data-ttu-id="b94cb-115">Предварительная проверка системных таблиц: идентификатор объекта O_ID.</span><span class="sxs-lookup"><span data-stu-id="b94cb-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="b94cb-116">Страница P_ID имеет непредвиденный тип PAGETYPE.</span><span class="sxs-lookup"><span data-stu-id="b94cb-116">Page P_ID has unexpected page type PAGETYPE.</span></span> <span data-ttu-id="b94cb-117">Инструкция проверки прервана из-за непоправимой ошибки.</span><span class="sxs-lookup"><span data-stu-id="b94cb-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b94cb-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b94cb-118">Explanation</span></span>  
 <span data-ttu-id="b94cb-119">Обнаружена страница типа, отличного от DATA_PAGE, на уровне данных заданного объекта.</span><span class="sxs-lookup"><span data-stu-id="b94cb-119">A page with a type other than DATA_PAGE was found in the data level of the specified object.</span></span> <span data-ttu-id="b94cb-120">Эта ошибка возникает на первой стадии проверки команды DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="b94cb-120">This error is raised during the first phase of the DBCC CHECKDB command checks.</span></span> <span data-ttu-id="b94cb-121">На этой стадии команда DBCC CHECKDB выполняет простые проверки страниц данных важных системных базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="b94cb-121">During this phase, DBCC CHECKDB performs primitive checks on the data pages of critical system base tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b94cb-122">Если найдены ошибки в системных таблицах, то ошибки не могут быть устранены; следовательно, выполнение команды DBCC CHECKDB немедленно завершается.</span><span class="sxs-lookup"><span data-stu-id="b94cb-122">If any errors are found in the system tables, the errors cannot be repaired; therefore, the DBCC CHECKDB command ends immediately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b94cb-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b94cb-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b94cb-124">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="b94cb-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b94cb-125">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="b94cb-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b94cb-126">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="b94cb-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b94cb-127">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="b94cb-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b94cb-128">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="b94cb-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b94cb-129">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="b94cb-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b94cb-130">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="b94cb-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b94cb-131">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="b94cb-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b94cb-132">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b94cb-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b94cb-133">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="b94cb-133">Restore from Backup</span></span>  
 <span data-ttu-id="b94cb-134">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="b94cb-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b94cb-135">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b94cb-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b94cb-136">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b94cb-136">Not applicable.</span></span> <span data-ttu-id="b94cb-137">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="b94cb-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="b94cb-138">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b94cb-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
