---
title: MSSQLSERVER_5233 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5233 (Database Engine error)
ms.assetid: 7a855afa-2d3b-49b7-adef-197b99fc98b1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0a5e2c603652534a6d3093a01da0a926a7195954
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667107"
---
# <a name="mssqlserver_5233"></a><span data-ttu-id="8c2ea-102">MSSQLSERVER_5233</span><span class="sxs-lookup"><span data-stu-id="8c2ea-102">MSSQLSERVER_5233</span></span>
    
## <a name="details"></a><span data-ttu-id="8c2ea-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="8c2ea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c2ea-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="8c2ea-104">Product Name</span></span>|<span data-ttu-id="8c2ea-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c2ea-105">SQL Server</span></span>|  
|<span data-ttu-id="8c2ea-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="8c2ea-106">Event ID</span></span>|<span data-ttu-id="8c2ea-107">5233</span><span class="sxs-lookup"><span data-stu-id="8c2ea-107">5233</span></span>|  
|<span data-ttu-id="8c2ea-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="8c2ea-108">Event Source</span></span>|<span data-ttu-id="8c2ea-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8c2ea-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8c2ea-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="8c2ea-110">Component</span></span>|<span data-ttu-id="8c2ea-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8c2ea-111">SQLEngine</span></span>|  
|<span data-ttu-id="8c2ea-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="8c2ea-112">Symbolic Name</span></span>|<span data-ttu-id="8c2ea-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="8c2ea-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="8c2ea-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="8c2ea-114">Message Text</span></span>|<span data-ttu-id="8c2ea-115">Ошибка в таблице: идентификатор единицы распределения A_ID, идентификатор страницы P_ID.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-115">Table error: alloc unit ID A_ID, page P_ID.</span></span> <span data-ttu-id="8c2ea-116">Проверка (TEST) завершилась с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-116">The test (TEST) failed.</span></span> <span data-ttu-id="8c2ea-117">Значениями являются VAL1 и VAL2.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-117">The values are VAL1 and VAL2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8c2ea-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="8c2ea-118">Explanation</span></span>  
 <span data-ttu-id="8c2ea-119">Аудит страницы *P_ID* окончился неудачей из-за повреждения в заголовке страницы.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-119">Page *P_ID* has failed auditing due to a corruption in its page header.</span></span> <span data-ttu-id="8c2ea-120">Строка в объекте TEST указывает, какая именно проверка окончилась неудачей.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-120">The string in TEST gives the actual test that failed.</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="8c2ea-121">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="8c2ea-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="8c2ea-122">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="8c2ea-123">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="8c2ea-124">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="8c2ea-125">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="8c2ea-126">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="8c2ea-127">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="8c2ea-128">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="8c2ea-129">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="8c2ea-130">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="8c2ea-130">Restore from Backup</span></span>  
 <span data-ttu-id="8c2ea-131">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="8c2ea-132">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="8c2ea-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="8c2ea-133">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-133">Not applicable.</span></span> <span data-ttu-id="8c2ea-134">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="8c2ea-134">This error cannot be repaired.</span></span> <span data-ttu-id="8c2ea-135">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей Майкрософт (CSS).</span><span class="sxs-lookup"><span data-stu-id="8c2ea-135">If you cannot restore the database from a backup, contact Microsoft Customer Service and Support (CSS).</span></span>  
  
  
