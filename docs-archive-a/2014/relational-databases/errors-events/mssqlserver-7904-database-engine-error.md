---
title: MSSQLSERVER_7904 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7904 (Database Engine error)
ms.assetid: d047920c-f864-4338-b15f-49820886fbc5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5e7be2e8413bc0267a642360da66a6a9ec0de8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664223"
---
# <a name="mssqlserver_7904"></a><span data-ttu-id="e604c-102">MSSQLSERVER_7904</span><span class="sxs-lookup"><span data-stu-id="e604c-102">MSSQLSERVER_7904</span></span>
    
## <a name="details"></a><span data-ttu-id="e604c-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="e604c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e604c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="e604c-104">Product Name</span></span>|<span data-ttu-id="e604c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e604c-105">SQL Server</span></span>|  
|<span data-ttu-id="e604c-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e604c-106">Event ID</span></span>|<span data-ttu-id="e604c-107">7904</span><span class="sxs-lookup"><span data-stu-id="e604c-107">7904</span></span>|  
|<span data-ttu-id="e604c-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="e604c-108">Event Source</span></span>|<span data-ttu-id="e604c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e604c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e604c-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="e604c-110">Component</span></span>|<span data-ttu-id="e604c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e604c-111">SQLEngine</span></span>|  
|<span data-ttu-id="e604c-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="e604c-112">Symbolic Name</span></span>|<span data-ttu-id="e604c-113">DBCC2_FS_MISSING_FILE</span><span class="sxs-lookup"><span data-stu-id="e604c-113">DBCC2_FS_MISSING_FILE</span></span>|  
|<span data-ttu-id="e604c-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="e604c-114">Message Text</span></span>|<span data-ttu-id="e604c-115">Ошибка таблицы: не найден файл FILESTREAM для столбца с идентификатором C_ID, ROWGUID RG_ID в объекте с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID.</span><span class="sxs-lookup"><span data-stu-id="e604c-115">Table error: The filestream file for column ID C_ID, ROWGUID RG_ID in object ID O_ID, index ID I_ID, partition ID PN_ID was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e604c-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="e604c-116">Explanation</span></span>  
 <span data-ttu-id="e604c-117">Значение столбца секции не содержит нужного файла FILESTREAM в соответствующем каталоге столбца FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e604c-117">A column value of a partition does not have a matching FILESTREAM file in the corresponding FILESTREAM column directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e604c-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="e604c-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="e604c-119">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="e604c-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="e604c-120">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="e604c-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="e604c-121">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="e604c-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="e604c-122">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="e604c-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="e604c-123">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="e604c-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="e604c-124">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="e604c-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="e604c-125">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="e604c-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="e604c-126">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="e604c-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="e604c-127">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e604c-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="e604c-128">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="e604c-128">Restore from Backup</span></span>  
 <span data-ttu-id="e604c-129">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="e604c-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="e604c-130">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="e604c-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="e604c-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="e604c-131">Not applicable.</span></span> <span data-ttu-id="e604c-132">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="e604c-132">This error cannot be repaired.</span></span> <span data-ttu-id="e604c-133">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e604c-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
