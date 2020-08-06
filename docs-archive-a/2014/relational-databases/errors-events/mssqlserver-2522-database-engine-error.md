---
title: MSSQLSERVER_2522 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2522 (Database Engine error)
ms.assetid: 19b9b00c-330f-4dd3-9052-9d88bce83849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60446c21599c02ee9c4bc96789b106b49b71582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655241"
---
# <a name="mssqlserver_2522"></a><span data-ttu-id="10813-102">MSSQLSERVER_2522</span><span class="sxs-lookup"><span data-stu-id="10813-102">MSSQLSERVER_2522</span></span>
    
## <a name="details"></a><span data-ttu-id="10813-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="10813-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10813-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="10813-104">Product Name</span></span>|<span data-ttu-id="10813-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="10813-105">SQL Server</span></span>|  
|<span data-ttu-id="10813-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="10813-106">Event ID</span></span>|<span data-ttu-id="10813-107">2522</span><span class="sxs-lookup"><span data-stu-id="10813-107">2522</span></span>|  
|<span data-ttu-id="10813-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="10813-108">Event Source</span></span>|<span data-ttu-id="10813-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="10813-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="10813-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="10813-110">Component</span></span>|<span data-ttu-id="10813-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="10813-111">SQLEngine</span></span>|  
|<span data-ttu-id="10813-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="10813-112">Symbolic Name</span></span>|<span data-ttu-id="10813-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="10813-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span></span>|  
|<span data-ttu-id="10813-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="10813-114">Message Text</span></span>|<span data-ttu-id="10813-115">Невозможно обработать индекс I_NAME таблицы O_NAME из-за недопустимой файловой группы F_NAME.</span><span class="sxs-lookup"><span data-stu-id="10813-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is invalid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="10813-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="10813-116">Explanation</span></span>  
 <span data-ttu-id="10813-117">Это информационное сообщение указывает, что индекс невозможно проверить, поскольку одна из файловых групп с идентификатором, хранящимся в метаданных индекса, не существует.</span><span class="sxs-lookup"><span data-stu-id="10813-117">This informational message indicates that the index cannot be checked because one of the filegroup IDs that is stored in the metadata of the index does not exist.</span></span> <span data-ttu-id="10813-118">Недопустимый идентификатор файловой группы может принадлежать самим данным, данным больших объектов (LOB) или превышающим размер страницы данным строки.</span><span class="sxs-lookup"><span data-stu-id="10813-118">The filegroup ID that is not valid might pertain to the data itself, or to the large object (LOB) data, or to the row-overflow data.</span></span>  
  
 <span data-ttu-id="10813-119">Если других проблем нет, то будут проверяться все остальные индексы того же объекта.</span><span class="sxs-lookup"><span data-stu-id="10813-119">If there are no problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10813-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="10813-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="10813-121">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="10813-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="10813-122">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="10813-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="10813-123">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="10813-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="10813-124">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="10813-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="10813-125">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="10813-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="10813-126">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="10813-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="10813-127">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="10813-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="10813-128">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="10813-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="10813-129">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="10813-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="10813-130">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="10813-130">Restore from Backup</span></span>  
 <span data-ttu-id="10813-131">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="10813-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="10813-132">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="10813-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="10813-133">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="10813-133">Not applicable.</span></span> <span data-ttu-id="10813-134">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="10813-134">This error cannot be repaired automatically.</span></span>  
  
  
