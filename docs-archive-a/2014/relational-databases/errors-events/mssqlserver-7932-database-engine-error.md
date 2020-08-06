---
title: MSSQLSERVER_7932 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7932 (Database Engine error)
ms.assetid: e2ad218a-3249-4f18-8b32-09f0030765a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 237d9be3e0f22664adb061d3bba526c9878d3bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664924"
---
# <a name="mssqlserver_7932"></a><span data-ttu-id="dc442-102">MSSQLSERVER_7932</span><span class="sxs-lookup"><span data-stu-id="dc442-102">MSSQLSERVER_7932</span></span>
    
## <a name="details"></a><span data-ttu-id="dc442-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="dc442-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc442-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="dc442-104">Product Name</span></span>|<span data-ttu-id="dc442-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc442-105">SQL Server</span></span>|  
|<span data-ttu-id="dc442-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="dc442-106">Event ID</span></span>|<span data-ttu-id="dc442-107">7932</span><span class="sxs-lookup"><span data-stu-id="dc442-107">7932</span></span>|  
|<span data-ttu-id="dc442-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="dc442-108">Event Source</span></span>|<span data-ttu-id="dc442-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dc442-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dc442-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="dc442-110">Component</span></span>|<span data-ttu-id="dc442-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dc442-111">SQLEngine</span></span>|  
|<span data-ttu-id="dc442-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="dc442-112">Symbolic Name</span></span>|<span data-ttu-id="dc442-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span><span class="sxs-lookup"><span data-stu-id="dc442-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span></span>|  
|<span data-ttu-id="dc442-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="dc442-114">Message Text</span></span>|<span data-ttu-id="dc442-115">Ошибка таблицы: каталог файловых потоков с идентификатором F_ID для объекта с идентификатором O_ID, индекса с идентификатором I_ID и секции с идентификатором PN_ID находится в файловой группе FG_ID1, но должен находиться в файловой группе FG_ID2.</span><span class="sxs-lookup"><span data-stu-id="dc442-115">Table error: The FileStream directory ID F_ID for object ID O_ID, index ID I_ID, partition ID PN_ID is in filegroup FG_ID1, but should be in filegroup FG_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dc442-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="dc442-116">Explanation</span></span>  
 <span data-ttu-id="dc442-117">При выполнении команды DBCC CHECKDB хранилище FILESTREAM для указанного объекта было обнаружено в неверной файловой группе.</span><span class="sxs-lookup"><span data-stu-id="dc442-117">During DBCC CHECKDB, the FILESTREAM storage for the specified object was detected in the wrong filegroup.</span></span> <span data-ttu-id="dc442-118">Причиной может быть повреждение метаданных объекта.</span><span class="sxs-lookup"><span data-stu-id="dc442-118">This could be a corruption in the metadata of the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc442-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="dc442-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="dc442-120">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="dc442-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="dc442-121">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="dc442-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="dc442-122">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="dc442-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="dc442-123">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="dc442-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="dc442-124">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="dc442-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="dc442-125">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="dc442-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="dc442-126">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="dc442-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="dc442-127">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="dc442-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="dc442-128">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="dc442-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="dc442-129">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="dc442-129">Restore from Backup</span></span>  
 <span data-ttu-id="dc442-130">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="dc442-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="dc442-131">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="dc442-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="dc442-132">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="dc442-132">Not applicable.</span></span> <span data-ttu-id="dc442-133">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="dc442-133">This error cannot be repaired automatically.</span></span> <span data-ttu-id="dc442-134">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc442-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
