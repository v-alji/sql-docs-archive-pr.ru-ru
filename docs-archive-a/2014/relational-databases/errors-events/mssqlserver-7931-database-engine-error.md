---
title: MSSQLSERVER_7931 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7931 (Database Engine error)
ms.assetid: 18e7a3dc-7d8a-41b9-8724-d2a8587b6903
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a93cc56869448d1dbcf95c1d9e1ffe1fe023e7e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664925"
---
# <a name="mssqlserver_7931"></a><span data-ttu-id="5eba1-102">MSSQLSERVER_7931</span><span class="sxs-lookup"><span data-stu-id="5eba1-102">MSSQLSERVER_7931</span></span>
    
## <a name="details"></a><span data-ttu-id="5eba1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5eba1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5eba1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5eba1-104">Product Name</span></span>|<span data-ttu-id="5eba1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5eba1-105">SQL Server</span></span>|  
|<span data-ttu-id="5eba1-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5eba1-106">Event ID</span></span>|<span data-ttu-id="5eba1-107">7931</span><span class="sxs-lookup"><span data-stu-id="5eba1-107">7931</span></span>|  
|<span data-ttu-id="5eba1-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5eba1-108">Event Source</span></span>|<span data-ttu-id="5eba1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5eba1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5eba1-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5eba1-110">Component</span></span>|<span data-ttu-id="5eba1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5eba1-111">SQLEngine</span></span>|  
|<span data-ttu-id="5eba1-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5eba1-112">Symbolic Name</span></span>|<span data-ttu-id="5eba1-113">DBCC2_FS_DOUBLE_ROWSET_ACTUAL_FACT</span><span class="sxs-lookup"><span data-stu-id="5eba1-113">DBCC2_FS_DOUBLE_ROWSET_ACTUAL_FACT</span></span>|  
|<span data-ttu-id="5eba1-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5eba1-114">Message Text</span></span>|<span data-ttu-id="5eba1-115">Ошибка базы данных: каталог файловых потоков с идентификатором "идентификатор" для секции был обнаружен дважды.</span><span class="sxs-lookup"><span data-stu-id="5eba1-115">Database error: The FileStream directory ID F_ID for a partition was seen twice.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5eba1-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5eba1-116">Explanation</span></span>  
 <span data-ttu-id="5eba1-117">В метаданных обнаружен такой же идентификатор секции для каталога файловых потоков.</span><span class="sxs-lookup"><span data-stu-id="5eba1-117">The same partition ID for a Filestream directory was found in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5eba1-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5eba1-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="5eba1-119">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="5eba1-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="5eba1-120">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="5eba1-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="5eba1-121">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="5eba1-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="5eba1-122">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="5eba1-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="5eba1-123">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="5eba1-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="5eba1-124">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="5eba1-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="5eba1-125">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="5eba1-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="5eba1-126">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="5eba1-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="5eba1-127">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5eba1-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="5eba1-128">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="5eba1-128">Restore from Backup</span></span>  
 <span data-ttu-id="5eba1-129">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="5eba1-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="5eba1-130">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="5eba1-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="5eba1-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="5eba1-131">Not applicable.</span></span> <span data-ttu-id="5eba1-132">Эту ошибку невозможно исправить автоматически.</span><span class="sxs-lookup"><span data-stu-id="5eba1-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="5eba1-133">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5eba1-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
