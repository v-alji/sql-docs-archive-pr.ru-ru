---
title: MSSQLSERVER_7988 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7988 (Database Engine error)
ms.assetid: 29b967b8-de30-4618-99a8-8b1155e69026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 984cb03aeb5feaa230762e200304f16cd8c5df08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731618"
---
# <a name="mssqlserver_7988"></a><span data-ttu-id="4295b-102">MSSQLSERVER_7988</span><span class="sxs-lookup"><span data-stu-id="4295b-102">MSSQLSERVER_7988</span></span>
    
## <a name="details"></a><span data-ttu-id="4295b-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="4295b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4295b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="4295b-104">Product Name</span></span>|<span data-ttu-id="4295b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4295b-105">SQL Server</span></span>|  
|<span data-ttu-id="4295b-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4295b-106">Event ID</span></span>|<span data-ttu-id="4295b-107">7988</span><span class="sxs-lookup"><span data-stu-id="4295b-107">7988</span></span>|  
|<span data-ttu-id="4295b-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="4295b-108">Event Source</span></span>|<span data-ttu-id="4295b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4295b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4295b-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="4295b-110">Component</span></span>|<span data-ttu-id="4295b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4295b-111">SQLEngine</span></span>|  
|<span data-ttu-id="4295b-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="4295b-112">Symbolic Name</span></span>|<span data-ttu-id="4295b-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span><span class="sxs-lookup"><span data-stu-id="4295b-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span></span>|  
|<span data-ttu-id="4295b-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="4295b-114">Message Text</span></span>|<span data-ttu-id="4295b-115">Предварительная проверка системных таблиц: идентификатор объекта O_ID.</span><span class="sxs-lookup"><span data-stu-id="4295b-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="4295b-116">Обнаружена циклическая цепочка данных в P_ID.</span><span class="sxs-lookup"><span data-stu-id="4295b-116">Loop in data chain detected at P_ID.</span></span> <span data-ttu-id="4295b-117">Инструкция проверки прервана из-за непоправимой ошибки.</span><span class="sxs-lookup"><span data-stu-id="4295b-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4295b-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="4295b-118">Explanation</span></span>  
 <span data-ttu-id="4295b-119">Первый этап работы DBCC CHECKDB заключается в осуществлении примитивных проверок страниц данных важных системных таблиц.</span><span class="sxs-lookup"><span data-stu-id="4295b-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="4295b-120">Если найдены ошибки, они считаются неисправимыми, поэтому инструкция DBCC CHECKDB немедленно прерывается.</span><span class="sxs-lookup"><span data-stu-id="4295b-120">If any errors are found, they cannot be repaired; therefore, DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="4295b-121">На странице *P_ID* обнаружена циклическая связь страниц.</span><span class="sxs-lookup"><span data-stu-id="4295b-121">A page linkage loop has been detected on page *P_ID*.</span></span> <span data-ttu-id="4295b-122">Циклическая связь страниц происходит, если указатели следующих страниц с одной из страниц, в конце концов, возвращаются к этой же странице.</span><span class="sxs-lookup"><span data-stu-id="4295b-122">A page linkage loop occurs when the next page pointers from a page eventually return to the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4295b-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="4295b-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4295b-124">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="4295b-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4295b-125">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="4295b-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4295b-126">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="4295b-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4295b-127">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="4295b-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4295b-128">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="4295b-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4295b-129">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="4295b-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4295b-130">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="4295b-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4295b-131">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="4295b-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4295b-132">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4295b-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4295b-133">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="4295b-133">Restore from Backup</span></span>  
 <span data-ttu-id="4295b-134">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="4295b-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4295b-135">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4295b-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4295b-136">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="4295b-136">Not applicable.</span></span> <span data-ttu-id="4295b-137">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="4295b-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="4295b-138">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4295b-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
