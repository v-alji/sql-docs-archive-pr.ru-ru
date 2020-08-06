---
title: MSSQLSERVER_8994 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8994 (Database Engine error)
ms.assetid: 8f4b0e2f-04c0-46e4-9208-20a7085d7a1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0bcc0b1db100b70390c09e9c825dbfd068d968af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655229"
---
# <a name="mssqlserver_8994"></a><span data-ttu-id="a4a4a-102">MSSQLSERVER_8994</span><span class="sxs-lookup"><span data-stu-id="a4a4a-102">MSSQLSERVER_8994</span></span>
    
## <a name="details"></a><span data-ttu-id="a4a4a-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a4a4a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a4a4a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a4a4a-104">Product Name</span></span>|<span data-ttu-id="a4a4a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a4a4a-105">SQL Server</span></span>|  
|<span data-ttu-id="a4a4a-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a4a4a-106">Event ID</span></span>|<span data-ttu-id="a4a4a-107">8994</span><span class="sxs-lookup"><span data-stu-id="a4a4a-107">8994</span></span>|  
|<span data-ttu-id="a4a4a-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a4a4a-108">Event Source</span></span>|<span data-ttu-id="a4a4a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a4a4a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a4a4a-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a4a4a-110">Component</span></span>|<span data-ttu-id="a4a4a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a4a4a-111">SQLEngine</span></span>|  
|<span data-ttu-id="a4a4a-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a4a4a-112">Symbolic Name</span></span>|<span data-ttu-id="a4a4a-113">DBCC3_MISSING_FORWARDING_ROW</span><span class="sxs-lookup"><span data-stu-id="a4a4a-113">DBCC3_MISSING_FORWARDING_ROW</span></span>|  
|<span data-ttu-id="a4a4a-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a4a4a-114">Message Text</span></span>|<span data-ttu-id="a4a4a-115">На идентификатор объекта O_ID, страницу переадресованной строки P_ID1, область памяти S_ID1 должна указывать страница переадресующей строки P_ID2, область памяти S_ID2.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-115">Object ID O_ID, forwarded row page P_ID1, slot S_ID1 should be pointed to by forwarding row page P_ID2, slot S_ID2.</span></span> <span data-ttu-id="a4a4a-116">Переадресующая строка не обнаружена.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-116">Did not encounter forwarding row.</span></span> <span data-ttu-id="a4a4a-117">Возможно, произошла ошибка размещения.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-117">Possible allocation error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a4a4a-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a4a4a-118">Explanation</span></span>  
 <span data-ttu-id="a4a4a-119">В переадресованной строке в куче отсутствует переадресующая строка, которая должна на нее указывать.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-119">A forwarded row in a heap is missing the forwarding row that should point to it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a4a4a-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a4a4a-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a4a4a-121">Поиск сбоев оборудования</span><span class="sxs-lookup"><span data-stu-id="a4a4a-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a4a4a-122">Выполните диагностику оборудования и исправьте все найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a4a4a-123">Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a4a4a-124">Исправьте все неполадки оборудования, обнаруженные в журналах.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a4a4a-125">Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a4a4a-126">Убедитесь, что в системе не включено кэширование записи для контроллера дисков.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a4a4a-127">Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a4a4a-128">В конце концов можно попробовать сменить оборудование.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a4a4a-129">Это может включать форматирование дисков и переустановку операционной системы.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a4a4a-130">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="a4a4a-130">Restore from Backup</span></span>  
 <span data-ttu-id="a4a4a-131">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a4a4a-132">Запуск DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a4a4a-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a4a4a-133">Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="a4a4a-134">Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="a4a4a-135">После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a4a4a-136">Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="a4a4a-137">Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="a4a4a-138">Результаты выполнения инструкции REPAIR</span><span class="sxs-lookup"><span data-stu-id="a4a4a-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="a4a4a-139">Переадресованная строка будет преобразована в обычную строку данных.</span><span class="sxs-lookup"><span data-stu-id="a4a4a-139">The forwarded row will be converted to a regular data row.</span></span>  
  
  
