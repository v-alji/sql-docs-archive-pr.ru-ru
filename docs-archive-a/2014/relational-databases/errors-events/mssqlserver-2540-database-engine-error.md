---
title: MSSQLSERVER_2540 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2540 (Database Engine error)
ms.assetid: eb5ee2be-acbb-4fb7-9b45-dc6200bde06e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4a49abeadcd49263ea7d0701ee468a36882179cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729514"
---
# <a name="mssqlserver_2540"></a><span data-ttu-id="8ec68-102">MSSQLSERVER_2540</span><span class="sxs-lookup"><span data-stu-id="8ec68-102">MSSQLSERVER_2540</span></span>
    
## <a name="details"></a><span data-ttu-id="8ec68-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="8ec68-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ec68-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="8ec68-104">Product Name</span></span>|<span data-ttu-id="8ec68-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8ec68-105">SQL Server</span></span>|  
|<span data-ttu-id="8ec68-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="8ec68-106">Event ID</span></span>|<span data-ttu-id="8ec68-107">2540</span><span class="sxs-lookup"><span data-stu-id="8ec68-107">2540</span></span>|  
|<span data-ttu-id="8ec68-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="8ec68-108">Event Source</span></span>|<span data-ttu-id="8ec68-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8ec68-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8ec68-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="8ec68-110">Component</span></span>|<span data-ttu-id="8ec68-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8ec68-111">SQLEngine</span></span>|  
|<span data-ttu-id="8ec68-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="8ec68-112">Symbolic Name</span></span>|<span data-ttu-id="8ec68-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span><span class="sxs-lookup"><span data-stu-id="8ec68-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span></span>|  
|<span data-ttu-id="8ec68-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="8ec68-114">Message Text</span></span>|<span data-ttu-id="8ec68-115">Система не может самостоятельно исправить эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="8ec68-115">The system cannot self repair this error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8ec68-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="8ec68-116">Explanation</span></span>  
 <span data-ttu-id="8ec68-117">Данное сообщение указывает на ошибки, которые нельзя исправить автоматически, например повреждение метаданных, повреждение PFS-страницы или повреждения в важных системных базовых таблицах.</span><span class="sxs-lookup"><span data-stu-id="8ec68-117">This error message indicates problems that cannot be repaired automatically, such as corrupt metadata, Page Free Space (PFS) page corruptions, or corruptions in certain critical system base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8ec68-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="8ec68-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="8ec68-119">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="8ec68-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="8ec68-120">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="8ec68-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="8ec68-121">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="8ec68-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="8ec68-122">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="8ec68-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="8ec68-123">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="8ec68-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="8ec68-124">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="8ec68-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="8ec68-125">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="8ec68-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="8ec68-126">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="8ec68-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="8ec68-127">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8ec68-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="8ec68-128">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="8ec68-128">Restore from Backup</span></span>  
 <span data-ttu-id="8ec68-129">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="8ec68-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="8ec68-130">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="8ec68-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="8ec68-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8ec68-131">Not applicable.</span></span> <span data-ttu-id="8ec68-132">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="8ec68-132">This error cannot be repaired automatically.</span></span>  
  
  
