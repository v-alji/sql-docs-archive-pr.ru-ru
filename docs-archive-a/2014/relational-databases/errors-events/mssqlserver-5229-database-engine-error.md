---
title: MSSQLSERVER_5229 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5229 (Database Engine error)
ms.assetid: 0d9e50da-4f42-4b3a-bc84-daf05cf0e0e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 12cc4631dec430b9c4ad63f06fa20819ba3d82ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729505"
---
# <a name="mssqlserver_5229"></a><span data-ttu-id="89f69-102">MSSQLSERVER_5229</span><span class="sxs-lookup"><span data-stu-id="89f69-102">MSSQLSERVER_5229</span></span>
    
## <a name="details"></a><span data-ttu-id="89f69-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="89f69-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="89f69-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="89f69-104">Product Name</span></span>|<span data-ttu-id="89f69-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="89f69-105">SQL Server</span></span>|  
|<span data-ttu-id="89f69-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="89f69-106">Event ID</span></span>|<span data-ttu-id="89f69-107">5229</span><span class="sxs-lookup"><span data-stu-id="89f69-107">5229</span></span>|  
|<span data-ttu-id="89f69-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="89f69-108">Event Source</span></span>|<span data-ttu-id="89f69-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="89f69-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="89f69-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="89f69-110">Component</span></span>|<span data-ttu-id="89f69-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="89f69-111">SQLEngine</span></span>|  
|<span data-ttu-id="89f69-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="89f69-112">Symbolic Name</span></span>|<span data-ttu-id="89f69-113">DBCC4_ANTIMATTER_IN_HEAP_OR_CLUSTERED_INDEX</span><span class="sxs-lookup"><span data-stu-id="89f69-113">DBCC4_ANTIMATTER_IN_HEAP_OR_CLUSTERED_INDEX</span></span>|  
|<span data-ttu-id="89f69-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="89f69-114">Message Text</span></span>|<span data-ttu-id="89f69-115">Ошибка таблицы: идентификатор объекта O_ID, идентификатор индекса I_ID, идентификатор секции PN_ID, идентификатор единицы распределения A_ID (тип TYPE) содержит виртуальный столбец, однако не является некластеризованным индексом.</span><span class="sxs-lookup"><span data-stu-id="89f69-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) contains an anti-matter column, but is not a nonclustered index.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="89f69-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="89f69-116">Explanation</span></span>  
 <span data-ttu-id="89f69-117">Куча или кластеризованный индекс содержит виртуальный столбец, хотя этого быть не должно.</span><span class="sxs-lookup"><span data-stu-id="89f69-117">A heap or clustered index contains an antimatter column, but should not.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="89f69-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="89f69-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="89f69-119">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="89f69-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="89f69-120">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="89f69-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="89f69-121">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="89f69-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="89f69-122">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="89f69-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="89f69-123">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="89f69-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="89f69-124">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="89f69-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="89f69-125">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="89f69-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="89f69-126">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="89f69-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="89f69-127">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="89f69-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="89f69-128">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="89f69-128">Restore from Backup</span></span>  
 <span data-ttu-id="89f69-129">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="89f69-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="89f69-130">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="89f69-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="89f69-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="89f69-131">Not applicable.</span></span> <span data-ttu-id="89f69-132">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="89f69-132">This error cannot be repaired.</span></span> <span data-ttu-id="89f69-133">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89f69-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
