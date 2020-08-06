---
title: MSSQLSERVER_7937 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7937 (Database Engine error)
ms.assetid: 7dcc61a3-975d-4662-8a4e-c153e26b36c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44f299f9c7773e38dad483d084f2b097166460ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666649"
---
# <a name="mssqlserver_7937"></a><span data-ttu-id="5e07d-102">MSSQLSERVER_7937</span><span class="sxs-lookup"><span data-stu-id="5e07d-102">MSSQLSERVER_7937</span></span>
    
## <a name="details"></a><span data-ttu-id="5e07d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5e07d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e07d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5e07d-104">Product Name</span></span>|<span data-ttu-id="5e07d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5e07d-105">SQL Server</span></span>|  
|<span data-ttu-id="5e07d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5e07d-106">Event ID</span></span>|<span data-ttu-id="5e07d-107">7937</span><span class="sxs-lookup"><span data-stu-id="5e07d-107">7937</span></span>|  
|<span data-ttu-id="5e07d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5e07d-108">Event Source</span></span>|<span data-ttu-id="5e07d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5e07d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5e07d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5e07d-110">Component</span></span>|<span data-ttu-id="5e07d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5e07d-111">SQLEngine</span></span>|  
|<span data-ttu-id="5e07d-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5e07d-112">Symbolic Name</span></span>|<span data-ttu-id="5e07d-113">DBCC2_FS_MISSING_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="5e07d-113">DBCC2_FS_MISSING_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="5e07d-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5e07d-114">Message Text</span></span>|<span data-ttu-id="5e07d-115">Ошибка таблицы: не найден каталог Filestream для идентификатора столбца C_ID идентификатора объекта O_ID с идентификатором индекса I_ID и идентификатором секции PN_ID.</span><span class="sxs-lookup"><span data-stu-id="5e07d-115">Table error: Filestream directory for column ID C_ID of object ID O_ID, index ID I_ID, partition ID PN_ID was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5e07d-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5e07d-116">Explanation</span></span>  
 <span data-ttu-id="5e07d-117">Указанный столбец имеется в секции, однако соответствующий каталог FILESTREAM не найден в пространстве данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="5e07d-117">The specified column exists in a partition; however, its corresponding FILESTREAM directory was not found in the FILESTREAM dataspace.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5e07d-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5e07d-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="5e07d-119">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="5e07d-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="5e07d-120">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="5e07d-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="5e07d-121">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="5e07d-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="5e07d-122">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="5e07d-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="5e07d-123">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="5e07d-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="5e07d-124">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="5e07d-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="5e07d-125">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="5e07d-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="5e07d-126">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="5e07d-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="5e07d-127">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5e07d-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="5e07d-128">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="5e07d-128">Restore from Backup</span></span>  
 <span data-ttu-id="5e07d-129">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="5e07d-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="5e07d-130">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="5e07d-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="5e07d-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="5e07d-131">Not applicable.</span></span> <span data-ttu-id="5e07d-132">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="5e07d-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="5e07d-133">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e07d-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
