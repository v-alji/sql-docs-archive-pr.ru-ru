---
title: MSSQLSERVER_7936 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7936 (Database Engine error)
ms.assetid: d78fc8a9-d173-4801-bb32-ed6a29257f08
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c478e998b6185b0a8e22cd99caf2be4fc2fdee33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666648"
---
# <a name="mssqlserver_7936"></a><span data-ttu-id="d1835-102">MSSQLSERVER_7936</span><span class="sxs-lookup"><span data-stu-id="d1835-102">MSSQLSERVER_7936</span></span>
    
## <a name="details"></a><span data-ttu-id="d1835-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d1835-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1835-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d1835-104">Product Name</span></span>|<span data-ttu-id="d1835-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1835-105">SQL Server</span></span>|  
|<span data-ttu-id="d1835-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d1835-106">Event ID</span></span>|<span data-ttu-id="d1835-107">7936</span><span class="sxs-lookup"><span data-stu-id="d1835-107">7936</span></span>|  
|<span data-ttu-id="d1835-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d1835-108">Event Source</span></span>|<span data-ttu-id="d1835-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d1835-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d1835-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d1835-110">Component</span></span>|<span data-ttu-id="d1835-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d1835-111">SQLEngine</span></span>|  
|<span data-ttu-id="d1835-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="d1835-112">Symbolic Name</span></span>|<span data-ttu-id="d1835-113">DBCC2_FS_ORPHANED_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="d1835-113">DBCC2_FS_ORPHANED_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="d1835-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d1835-114">Message Text</span></span>|<span data-ttu-id="d1835-115">Ошибка таблицы: каталог Filestream существует для идентификатора столбца C_ID, идентификатора объекта O_ID с идентификатором индекса I_ID и идентификатором секции PN_ID, однако данный столбец не является столбцом Filestream.</span><span class="sxs-lookup"><span data-stu-id="d1835-115">Table error: Filestream directory exists for column ID C_ID of object ID O_ID, index ID I_ID, partition ID PN_ID, but that column is not a Filestream column.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d1835-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d1835-116">Explanation</span></span>  
 <span data-ttu-id="d1835-117">Во время выполнения команды DBCC CHECKDB для указанного столбца был найден каталог файловых потоков, но этот столбец не является столбцом `FILESTREAM`.</span><span class="sxs-lookup"><span data-stu-id="d1835-117">During DBCC CHECKDB, a FILESTREAM directory was found for the specified column; however, the column is not a `FILESTREAM` column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1835-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d1835-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="d1835-119">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="d1835-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="d1835-120">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="d1835-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="d1835-121">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="d1835-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="d1835-122">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="d1835-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="d1835-123">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="d1835-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="d1835-124">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="d1835-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="d1835-125">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="d1835-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="d1835-126">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="d1835-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="d1835-127">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="d1835-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="d1835-128">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="d1835-128">Restore from Backup</span></span>  
 <span data-ttu-id="d1835-129">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="d1835-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="d1835-130">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="d1835-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="d1835-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="d1835-131">Not applicable.</span></span> <span data-ttu-id="d1835-132">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="d1835-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="d1835-133">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1835-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
