---
title: MSSQLSERVER_7907 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7907 (Database Engine error)
ms.assetid: a1c94e4a-7e91-46e0-9fac-07bbbf6dd018
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e09e95d9a2416ae54c40f5c8e57d9444497c579f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664221"
---
# <a name="mssqlserver_7907"></a><span data-ttu-id="2491d-102">MSSQLSERVER_7907</span><span class="sxs-lookup"><span data-stu-id="2491d-102">MSSQLSERVER_7907</span></span>
    
## <a name="details"></a><span data-ttu-id="2491d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="2491d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2491d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="2491d-104">Product Name</span></span>|<span data-ttu-id="2491d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2491d-105">SQL Server</span></span>|  
|<span data-ttu-id="2491d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="2491d-106">Event ID</span></span>|<span data-ttu-id="2491d-107">7907</span><span class="sxs-lookup"><span data-stu-id="2491d-107">7907</span></span>|  
|<span data-ttu-id="2491d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="2491d-108">Event Source</span></span>|<span data-ttu-id="2491d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2491d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2491d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="2491d-110">Component</span></span>|<span data-ttu-id="2491d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2491d-111">SQLEngine</span></span>|  
|<span data-ttu-id="2491d-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="2491d-112">Symbolic Name</span></span>|<span data-ttu-id="2491d-113">DBCC2_FS_INVALID_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="2491d-113">DBCC2_FS_INVALID_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="2491d-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="2491d-114">Message Text</span></span>|<span data-ttu-id="2491d-115">Ошибка таблицы: каталог "DIRECTORY" в секции с идентификатором PN_ID не является допустимым каталогом Filestream.</span><span class="sxs-lookup"><span data-stu-id="2491d-115">Table error: The directory 'DIRECTORY' in partition ID PN_ID is not a valid Filestream directory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2491d-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="2491d-116">Explanation</span></span>  
 <span data-ttu-id="2491d-117">Имя каталога столбцов является идентификатором столбцов реляционного механизма секции.</span><span class="sxs-lookup"><span data-stu-id="2491d-117">The name of a column directory is the relational engine column ID of the partition.</span></span> <span data-ttu-id="2491d-118">Если имя каталога столбцов не может быть преобразовано в идентификатор столбца, то данный каталог не является допустимым каталогом столбцов.</span><span class="sxs-lookup"><span data-stu-id="2491d-118">If a column directory name cannot be converted to a column ID, the directory is not a valid column directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2491d-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="2491d-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="2491d-120">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="2491d-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="2491d-121">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="2491d-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="2491d-122">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="2491d-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="2491d-123">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="2491d-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="2491d-124">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="2491d-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="2491d-125">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="2491d-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="2491d-126">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="2491d-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="2491d-127">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="2491d-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="2491d-128">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2491d-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="2491d-129">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="2491d-129">Restore from Backup</span></span>  
 <span data-ttu-id="2491d-130">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="2491d-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="2491d-131">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="2491d-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="2491d-132">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="2491d-132">Not applicable.</span></span> <span data-ttu-id="2491d-133">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="2491d-133">This error cannot be repaired.</span></span> <span data-ttu-id="2491d-134">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2491d-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
