---
title: MSSQLSERVER_7933 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7933 (Database Engine error)
ms.assetid: 722bd2c6-0fb9-4838-954a-439744c6ac4b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ff25201d56b1bf55a0ecafbba7fbc787dc2fb64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664918"
---
# <a name="mssqlserver_7933"></a><span data-ttu-id="b2155-102">MSSQLSERVER_7933</span><span class="sxs-lookup"><span data-stu-id="b2155-102">MSSQLSERVER_7933</span></span>
    
## <a name="details"></a><span data-ttu-id="b2155-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b2155-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2155-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b2155-104">Product Name</span></span>|<span data-ttu-id="b2155-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2155-105">SQL Server</span></span>|  
|<span data-ttu-id="b2155-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b2155-106">Event ID</span></span>|<span data-ttu-id="b2155-107">7933</span><span class="sxs-lookup"><span data-stu-id="b2155-107">7933</span></span>|  
|<span data-ttu-id="b2155-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b2155-108">Event Source</span></span>|<span data-ttu-id="b2155-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b2155-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b2155-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b2155-110">Component</span></span>|<span data-ttu-id="b2155-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b2155-111">SQLEngine</span></span>|  
|<span data-ttu-id="b2155-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b2155-112">Symbolic Name</span></span>|<span data-ttu-id="b2155-113">DBCC2_FS_ORPHANED_ROWSET_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="b2155-113">DBCC2_FS_ORPHANED_ROWSET_DIRECTORY</span></span>|  
|<span data-ttu-id="b2155-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b2155-114">Message Text</span></span>|<span data-ttu-id="b2155-115">Ошибка таблицы: для секции существует каталог файловых потоков с идентификатором F_ID, но в базе данных отсутствует соответствующая секция.</span><span class="sxs-lookup"><span data-stu-id="b2155-115">Table error: A Filestream directory ID F_ID exists for a partition, but the corresponding partition does not exist in the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b2155-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b2155-116">Explanation</span></span>  
 <span data-ttu-id="b2155-117">При выполнении команды DBCC CHECKDB в пространстве данных FILESTREAM был обнаружен каталог наборов строк, но в базе данных отсутствует соответствующая ему секция.</span><span class="sxs-lookup"><span data-stu-id="b2155-117">During DBCC CHECKDB, a rowset directory was found in the FILESTREAM dataspace; however, its corresponding partition is missing in the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2155-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b2155-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b2155-119">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="b2155-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b2155-120">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="b2155-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b2155-121">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="b2155-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b2155-122">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="b2155-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b2155-123">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="b2155-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b2155-124">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="b2155-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b2155-125">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="b2155-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b2155-126">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="b2155-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b2155-127">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b2155-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b2155-128">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="b2155-128">Restore from Backup</span></span>  
 <span data-ttu-id="b2155-129">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="b2155-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b2155-130">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b2155-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b2155-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b2155-131">Not applicable.</span></span> <span data-ttu-id="b2155-132">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="b2155-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="b2155-133">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2155-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
