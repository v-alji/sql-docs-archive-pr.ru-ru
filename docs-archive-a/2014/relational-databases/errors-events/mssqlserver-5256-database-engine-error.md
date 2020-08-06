---
title: MSSQLSERVER_5256 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5256 (Database Engine error)
ms.assetid: 6fe254b4-2926-446f-8b20-0f1d921a4615
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9146b7744e78550463cbec4c05df5fd75a049898
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734085"
---
# <a name="mssqlserver_5256"></a><span data-ttu-id="856ce-102">MSSQLSERVER_5256</span><span class="sxs-lookup"><span data-stu-id="856ce-102">MSSQLSERVER_5256</span></span>
    
## <a name="details"></a><span data-ttu-id="856ce-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="856ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="856ce-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="856ce-104">Product Name</span></span>|<span data-ttu-id="856ce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="856ce-105">SQL Server</span></span>|  
|<span data-ttu-id="856ce-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="856ce-106">Event ID</span></span>|<span data-ttu-id="856ce-107">5256</span><span class="sxs-lookup"><span data-stu-id="856ce-107">5256</span></span>|  
|<span data-ttu-id="856ce-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="856ce-108">Event Source</span></span>|<span data-ttu-id="856ce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="856ce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="856ce-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="856ce-110">Component</span></span>|<span data-ttu-id="856ce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="856ce-111">SQLEngine</span></span>|  
|<span data-ttu-id="856ce-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="856ce-112">Symbolic Name</span></span>|<span data-ttu-id="856ce-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="856ce-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="856ce-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="856ce-114">Message Text</span></span>|<span data-ttu-id="856ce-115">Ошибка в таблице: идентификатор единицы распределения A_ID, страница с идентификатором P_ID1 содержит неверный идентификатор страницы в заголовке.</span><span class="sxs-lookup"><span data-stu-id="856ce-115">Table error: alloc unit ID A_ID, page P_ID1 contains an incorrect page ID in its page header.</span></span> <span data-ttu-id="856ce-116">PageId в заголовке страницы равен P_ID2.</span><span class="sxs-lookup"><span data-stu-id="856ce-116">The PageId in the page header = P_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="856ce-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="856ce-117">Explanation</span></span>  
 <span data-ttu-id="856ce-118">Заголовок страницы *P_ID1* содержит неправильный идентификатор страницы *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="856ce-118">The page header of page *P_ID1* contains an incorrect page ID, *P_ID2*.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="856ce-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="856ce-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="856ce-120">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="856ce-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="856ce-121">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="856ce-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="856ce-122">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="856ce-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="856ce-123">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="856ce-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="856ce-124">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="856ce-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="856ce-125">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="856ce-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="856ce-126">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="856ce-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="856ce-127">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="856ce-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="856ce-128">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="856ce-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="856ce-129">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="856ce-129">Restore from Backup</span></span>  
 <span data-ttu-id="856ce-130">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="856ce-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="856ce-131">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="856ce-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="856ce-132">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="856ce-132">Not applicable.</span></span> <span data-ttu-id="856ce-133">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="856ce-133">This error cannot be repaired.</span></span> <span data-ttu-id="856ce-134">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="856ce-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
