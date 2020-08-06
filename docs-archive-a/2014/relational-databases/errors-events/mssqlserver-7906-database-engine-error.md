---
title: MSSQLSERVER_7906 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7906 (Database Engine error)
ms.assetid: 9638a764-4ac1-40ae-a614-2726ebcc6ba4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57485a8f330f186a4abd83182c6035168ed38e0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664222"
---
# <a name="mssqlserver_7906"></a><span data-ttu-id="ff146-102">MSSQLSERVER_7906</span><span class="sxs-lookup"><span data-stu-id="ff146-102">MSSQLSERVER_7906</span></span>
    
## <a name="details"></a><span data-ttu-id="ff146-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="ff146-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff146-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ff146-104">Product Name</span></span>|<span data-ttu-id="ff146-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff146-105">SQL Server</span></span>|  
|<span data-ttu-id="ff146-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ff146-106">Event ID</span></span>|<span data-ttu-id="ff146-107">7906</span><span class="sxs-lookup"><span data-stu-id="ff146-107">7906</span></span>|  
|<span data-ttu-id="ff146-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ff146-108">Event Source</span></span>|<span data-ttu-id="ff146-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ff146-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ff146-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ff146-110">Component</span></span>|<span data-ttu-id="ff146-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ff146-111">SQLEngine</span></span>|  
|<span data-ttu-id="ff146-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ff146-112">Symbolic Name</span></span>|<span data-ttu-id="ff146-113">DBCC2_FS_INVALID_TOP_LEVEL_FILE</span><span class="sxs-lookup"><span data-stu-id="ff146-113">DBCC2_FS_INVALID_TOP_LEVEL_FILE</span></span>|  
|<span data-ttu-id="ff146-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ff146-114">Message Text</span></span>|<span data-ttu-id="ff146-115">Ошибка базы данных: файл "имя_файла" не является допустимым файлом Filestream.</span><span class="sxs-lookup"><span data-stu-id="ff146-115">Database error: The file 'FILE' is not a valid Filestream file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ff146-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ff146-116">Explanation</span></span>  
 <span data-ttu-id="ff146-117">Кроме ряда специальных файлов (например, «filestream.hdr»), никакие другие файлы входить непосредственно в пространство данных FILESTREAM не должны.</span><span class="sxs-lookup"><span data-stu-id="ff146-117">Except for some special files such as, 'filestream.hdr', no files should be found directly under the Filestream dataspace.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ff146-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ff146-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="ff146-119">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="ff146-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="ff146-120">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="ff146-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="ff146-121">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="ff146-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="ff146-122">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="ff146-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="ff146-123">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="ff146-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="ff146-124">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="ff146-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="ff146-125">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="ff146-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="ff146-126">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="ff146-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="ff146-127">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ff146-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="ff146-128">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="ff146-128">Restore from Backup</span></span>  
 <span data-ttu-id="ff146-129">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="ff146-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="ff146-130">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="ff146-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="ff146-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ff146-131">Not applicable.</span></span> <span data-ttu-id="ff146-132">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="ff146-132">This error cannot be repaired.</span></span> <span data-ttu-id="ff146-133">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff146-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
