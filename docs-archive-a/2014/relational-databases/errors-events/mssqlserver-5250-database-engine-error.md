---
title: MSSQLSERVER_5250 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5250 (Database Engine error)
ms.assetid: f4a1d0e8-f27f-4cb8-a25d-040b40555dcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace26b88aca5b00c23aff3fe48f7c1d04ef35245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734089"
---
# <a name="mssqlserver_5250"></a><span data-ttu-id="f182e-102">MSSQLSERVER_5250</span><span class="sxs-lookup"><span data-stu-id="f182e-102">MSSQLSERVER_5250</span></span>
    
## <a name="details"></a><span data-ttu-id="f182e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="f182e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f182e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="f182e-104">Product Name</span></span>|<span data-ttu-id="f182e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f182e-105">SQL Server</span></span>|  
|<span data-ttu-id="f182e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f182e-106">Event ID</span></span>|<span data-ttu-id="f182e-107">5250</span><span class="sxs-lookup"><span data-stu-id="f182e-107">5250</span></span>|  
|<span data-ttu-id="f182e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="f182e-108">Event Source</span></span>|<span data-ttu-id="f182e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f182e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f182e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="f182e-110">Component</span></span>|<span data-ttu-id="f182e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f182e-111">SQLEngine</span></span>|  
|<span data-ttu-id="f182e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="f182e-112">Symbolic Name</span></span>|<span data-ttu-id="f182e-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="f182e-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span></span>|  
|<span data-ttu-id="f182e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="f182e-114">Message Text</span></span>|<span data-ttu-id="f182e-115">Ошибка базы данных: PAGE_TYPE страница P_ID для базы данных "NAME" (идентификатор базы данных DB_ID) неверна.</span><span class="sxs-lookup"><span data-stu-id="f182e-115">Database error: PAGE_TYPE page P_ID for database 'NAME' (database ID DB_ID) is invalid.</span></span> <span data-ttu-id="f182e-116">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="f182e-116">This error cannot be repaired.</span></span> <span data-ttu-id="f182e-117">Необходимо восстановить из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f182e-117">You must restore from backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f182e-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="f182e-118">Explanation</span></span>  
 <span data-ttu-id="f182e-119">Повреждена страница заголовка файла или загрузочная страница указанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="f182e-119">A file header page or boot page in the specified database is corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f182e-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="f182e-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="f182e-121">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="f182e-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="f182e-122">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="f182e-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="f182e-123">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="f182e-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="f182e-124">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="f182e-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="f182e-125">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="f182e-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="f182e-126">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="f182e-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="f182e-127">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="f182e-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="f182e-128">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="f182e-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="f182e-129">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f182e-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="f182e-130">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="f182e-130">Restore from Backup</span></span>  
 <span data-ttu-id="f182e-131">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="f182e-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="f182e-132">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="f182e-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="f182e-133">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="f182e-133">Not applicable.</span></span> <span data-ttu-id="f182e-134">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="f182e-134">This error cannot be repaired.</span></span> <span data-ttu-id="f182e-135">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f182e-135">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
