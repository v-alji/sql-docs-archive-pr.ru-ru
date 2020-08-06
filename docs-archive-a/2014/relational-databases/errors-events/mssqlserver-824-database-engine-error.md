---
title: MSSQLSERVER_824 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
ms.assetid: 2aa22246-2712-4fdb-9744-36e7e6f3175e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d57b19bc8c837b92b65728fbb0046039b862d31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664210"
---
# <a name="mssqlserver_824"></a><span data-ttu-id="a5f25-102">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="a5f25-102">MSSQLSERVER_824</span></span>
    
## <a name="details"></a><span data-ttu-id="a5f25-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a5f25-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5f25-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a5f25-104">Product Name</span></span>|<span data-ttu-id="a5f25-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5f25-105">SQL Server</span></span>|  
|<span data-ttu-id="a5f25-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a5f25-106">Event ID</span></span>|<span data-ttu-id="a5f25-107">824</span><span class="sxs-lookup"><span data-stu-id="a5f25-107">824</span></span>|  
|<span data-ttu-id="a5f25-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a5f25-108">Event Source</span></span>|<span data-ttu-id="a5f25-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a5f25-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a5f25-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a5f25-110">Component</span></span>|<span data-ttu-id="a5f25-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a5f25-111">SQLEngine</span></span>|  
|<span data-ttu-id="a5f25-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a5f25-112">Symbolic Name</span></span>|<span data-ttu-id="a5f25-113">B_HARDSSERR</span><span class="sxs-lookup"><span data-stu-id="a5f25-113">B_HARDSSERR</span></span>|  
|<span data-ttu-id="a5f25-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a5f25-114">Message Text</span></span>|<span data-ttu-id="a5f25-115">SQL Server обнаружил логическую ошибку ввода-вывода, связанную с согласованностью: %ls.</span><span class="sxs-lookup"><span data-stu-id="a5f25-115">SQL Server detected a logical consistency-based I/O error: %ls.</span></span> <span data-ttu-id="a5f25-116">Она произошла при %S_MSG страницы %S_PGID в базе данных с идентификатором %d по смещению %#016I64x файла «%ls».</span><span class="sxs-lookup"><span data-stu-id="a5f25-116">It occurred during a %S_MSG of page %S_PGID in database ID %d at offset %#016I64x in file '%ls'.</span></span>  <span data-ttu-id="a5f25-117">Дополнительные сведения см. в журнале ошибок SQL Server и журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="a5f25-117">Additional messages in the SQL Server error log or system event log may provide more detail.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a5f25-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a5f25-118">Explanation</span></span>  
 <span data-ttu-id="a5f25-119">Эта ошибка говорит о следующем: Windows сообщает об успешном считывании страницы с диска, но [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обнаружил некоторые повреждения страницы.</span><span class="sxs-lookup"><span data-stu-id="a5f25-119">This error indicates that Windows reports that the page is successfully read from disk, but [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has discovered something wrong with the page.</span></span> <span data-ttu-id="a5f25-120">Данная ошибка схожа с ошибкой 823, за исключением того, что в Windows никакие ошибки обнаружены не были.</span><span class="sxs-lookup"><span data-stu-id="a5f25-120">This error is similar to error 823 except that Windows did not detect the error.</span></span> <span data-ttu-id="a5f25-121">Чаще всего это говорит о проблеме с подсистемой ввода-вывода, например сбое жесткого диска, проблемах с дисковым встроенным ПО, драйверами устройств и т.д.</span><span class="sxs-lookup"><span data-stu-id="a5f25-121">This usually indicates a problem in the I/O subsystem, such as a failing disk drive, disk firmware problems, faulty device driver, and so on.</span></span> <span data-ttu-id="a5f25-122">Дополнительные сведения об ошибках ввода-вывода см. в [главе 2 документации Майкрософт об основных операциях ввода-вывода в SQL Server](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="a5f25-122">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a5f25-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a5f25-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a5f25-124">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="a5f25-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a5f25-125">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="a5f25-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a5f25-126">Также просмотрите журнал системы и журналы приложений [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="a5f25-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred because of hardware failure.</span></span> <span data-ttu-id="a5f25-127">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="a5f25-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a5f25-128">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="a5f25-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a5f25-129">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="a5f25-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a5f25-130">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="a5f25-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a5f25-131">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="a5f25-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a5f25-132">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="a5f25-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a5f25-133">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="a5f25-133">Restore from Backup</span></span>  
 <span data-ttu-id="a5f25-134">Если проблема не связана с оборудованием и имеется безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="a5f25-134">If the problem is not hardware-related and a known clean backup is available, restore the database from the backup.</span></span>  
  
 <span data-ttu-id="a5f25-135">Рассмотрите вариант изменения настроек баз данных и включения параметра PAGE_VERIFY CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="a5f25-135">Consider changing the databases to use the PAGE_VERIFY CHECKSUM option.</span></span> <span data-ttu-id="a5f25-136">Дополнительные сведения о PAGE_VERIFY см. в статье [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5f25-136">For information about PAGE_VERIFY, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f25-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="a5f25-137">See Also</span></span>  
 [<span data-ttu-id="a5f25-138">Управление таблицей suspect_pages (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a5f25-138">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
