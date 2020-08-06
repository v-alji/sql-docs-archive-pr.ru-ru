---
title: MSSQLSERVER_7905 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7905 (Database Engine error)
ms.assetid: cf19fbbb-7158-45f2-8778-8f3cad7f574a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 253bf03c1bfacccfd809cd417163eb9d54644f28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664224"
---
# <a name="mssqlserver_7905"></a><span data-ttu-id="67487-102">MSSQLSERVER_7905</span><span class="sxs-lookup"><span data-stu-id="67487-102">MSSQLSERVER_7905</span></span>
    
## <a name="details"></a><span data-ttu-id="67487-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="67487-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67487-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="67487-104">Product Name</span></span>|<span data-ttu-id="67487-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="67487-105">SQL Server</span></span>|  
|<span data-ttu-id="67487-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="67487-106">Event ID</span></span>|<span data-ttu-id="67487-107">7905</span><span class="sxs-lookup"><span data-stu-id="67487-107">7905</span></span>|  
|<span data-ttu-id="67487-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="67487-108">Event Source</span></span>|<span data-ttu-id="67487-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="67487-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="67487-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="67487-110">Component</span></span>|<span data-ttu-id="67487-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="67487-111">SQLEngine</span></span>|  
|<span data-ttu-id="67487-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="67487-112">Symbolic Name</span></span>|<span data-ttu-id="67487-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="67487-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span></span>|  
|<span data-ttu-id="67487-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="67487-114">Message Text</span></span>|<span data-ttu-id="67487-115">Ошибка базы данных: каталог "имя-каталога" не является допустимым каталогом Filestream.</span><span class="sxs-lookup"><span data-stu-id="67487-115">Database error: The directory 'DIRECTORY' is not a valid Filestream directory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67487-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="67487-116">Explanation</span></span>  
 <span data-ttu-id="67487-117">Имя каталога набора строк является идентификатором секции, за исключением особых каталогов набора строк (например, «ghost»).</span><span class="sxs-lookup"><span data-stu-id="67487-117">The name of a rowset directory is the partition ID of the partition, except for the special rowset directory names such as 'ghost'.</span></span> <span data-ttu-id="67487-118">Если имя каталога набора строк не может быть преобразовано в идентификатор секции, данный каталог не является допустимым каталогом набора строк.</span><span class="sxs-lookup"><span data-stu-id="67487-118">If a rowset directory name cannot be converted to a partition ID, the directory is not a valid rowset directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67487-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="67487-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="67487-120">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="67487-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="67487-121">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="67487-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="67487-122">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="67487-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="67487-123">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="67487-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="67487-124">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="67487-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="67487-125">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="67487-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="67487-126">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="67487-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="67487-127">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="67487-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="67487-128">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="67487-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="67487-129">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="67487-129">Restore from Backup</span></span>  
 <span data-ttu-id="67487-130">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="67487-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="67487-131">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="67487-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="67487-132">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="67487-132">Not applicable.</span></span> <span data-ttu-id="67487-133">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="67487-133">This error cannot be repaired.</span></span> <span data-ttu-id="67487-134">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67487-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
