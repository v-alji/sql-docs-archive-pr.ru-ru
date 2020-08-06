---
title: MSSQLSERVER_5235 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5235 (Database Engine error)
ms.assetid: 1aa7e6a5-7ccb-43c8-a1fd-d50e92e0a798
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 42c807944d7506a6a118de97ccd8c2c488942c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740025"
---
# <a name="mssqlserver_5235"></a><span data-ttu-id="f3b05-102">MSSQLSERVER_5235</span><span class="sxs-lookup"><span data-stu-id="f3b05-102">MSSQLSERVER_5235</span></span>
    
## <a name="details"></a><span data-ttu-id="f3b05-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="f3b05-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3b05-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="f3b05-104">Product Name</span></span>|<span data-ttu-id="f3b05-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3b05-105">SQL Server</span></span>|  
|<span data-ttu-id="f3b05-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f3b05-106">Event ID</span></span>|<span data-ttu-id="f3b05-107">5235</span><span class="sxs-lookup"><span data-stu-id="f3b05-107">5235</span></span>|  
|<span data-ttu-id="f3b05-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="f3b05-108">Event Source</span></span>|<span data-ttu-id="f3b05-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f3b05-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f3b05-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="f3b05-110">Component</span></span>|<span data-ttu-id="f3b05-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f3b05-111">SQLEngine</span></span>|  
|<span data-ttu-id="f3b05-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="f3b05-112">Symbolic Name</span></span>|<span data-ttu-id="f3b05-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span><span class="sxs-lookup"><span data-stu-id="f3b05-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span></span>|  
|<span data-ttu-id="f3b05-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="f3b05-114">Message Text</span></span>|<span data-ttu-id="f3b05-115">Аварийное завершение инструкции [EMERGENCY] DBCC DBCC_COMMAND_DETAILS, выполненной пользователем USER_NAME, в результате ошибки с состоянием ERROR_STATE.</span><span class="sxs-lookup"><span data-stu-id="f3b05-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS executed by USER_NAME terminated abnormally due to error state ERROR_STATE.</span></span> <span data-ttu-id="f3b05-116">Затраченное время: HOURS часы MINUTES минуты SECONDS секунды.</span><span class="sxs-lookup"><span data-stu-id="f3b05-116">Elapsed time: HOURS hours MINUTES minutes SECONDS seconds.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f3b05-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="f3b05-117">Explanation</span></span>  
 <span data-ttu-id="f3b05-118">Это сообщение сводки, которое DBCC распечатывает в журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при аварийном завершении во время выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="f3b05-118">This is the summary message that DBCC prints to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log when an unexpected termination occurs while the command is running.</span></span> <span data-ttu-id="f3b05-119">Состояние ошибки в сообщении определяет тип аварийного завершения.</span><span class="sxs-lookup"><span data-stu-id="f3b05-119">The error state reported in the message defines the type of unexpected termination.</span></span>  
  
 <span data-ttu-id="f3b05-120">В следующей ниже таблице приведены состояния ошибок и их определения.</span><span class="sxs-lookup"><span data-stu-id="f3b05-120">The following table lists and defines the error states.</span></span>  
  
|<span data-ttu-id="f3b05-121">Состояние ошибки</span><span class="sxs-lookup"><span data-stu-id="f3b05-121">Error state</span></span>|<span data-ttu-id="f3b05-122">Определение</span><span class="sxs-lookup"><span data-stu-id="f3b05-122">Definition</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="f3b05-123">Состояние 0</span><span class="sxs-lookup"><span data-stu-id="f3b05-123">State 0</span></span>|<span data-ttu-id="f3b05-124">Инструкция завершена из-за неустранимого повреждения метаданных.</span><span class="sxs-lookup"><span data-stu-id="f3b05-124">The statement was terminated because of a fatal metadata corruption.</span></span> <span data-ttu-id="f3b05-125">Это сообщение будет сопровождаться одним или несколькими экземплярами ошибки 8930.</span><span class="sxs-lookup"><span data-stu-id="f3b05-125">This message will be accompanied by one or more instances of error 8930.</span></span>|  
|<span data-ttu-id="f3b05-126">Состояние 1</span><span class="sxs-lookup"><span data-stu-id="f3b05-126">State 1</span></span>|<span data-ttu-id="f3b05-127">Инструкция завершена из-за сбоя выполнения внутренней проверки.</span><span class="sxs-lookup"><span data-stu-id="f3b05-127">The statement was terminated because of an internal check failure.</span></span> <span data-ttu-id="f3b05-128">Это сообщение будет сопровождаться одним или несколькими экземплярами ошибки 8967.</span><span class="sxs-lookup"><span data-stu-id="f3b05-128">This message will be accompanied by one or more instances of error 8967.</span></span>|  
|<span data-ttu-id="f3b05-129">Состояние 2</span><span class="sxs-lookup"><span data-stu-id="f3b05-129">State 2</span></span>|<span data-ttu-id="f3b05-130">Основной системной таблице не удалось выполнить проверку базовых системных таблиц подсистемы хранилища.</span><span class="sxs-lookup"><span data-stu-id="f3b05-130">Basic system table checks of the core storage engine system tables failed.</span></span> <span data-ttu-id="f3b05-131">Это сообщение будет сопровождаться одним или несколькими экземплярами ошибок [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md) или [7988](mssqlserver-7988-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="f3b05-131">This message will be accompanied by one or more instances of error [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md), or [7988](mssqlserver-7988-database-engine-error.md).</span></span>|  
|<span data-ttu-id="f3b05-132">Состояние 3</span><span class="sxs-lookup"><span data-stu-id="f3b05-132">State 3</span></span>|<span data-ttu-id="f3b05-133">Произошел сбой при аварийном восстановлении DBCC, поскольку базу данных не удалось запустить после перестроения журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="f3b05-133">DBCC emergency-mode repair failed because the database could not be started after rebuilding the transaction log.</span></span> <span data-ttu-id="f3b05-134">Это сообщение будет сопровождаться ошибкой 7909.</span><span class="sxs-lookup"><span data-stu-id="f3b05-134">This message will be accompanied by error 7909.</span></span>|  
|<span data-ttu-id="f3b05-135">Состояние 4</span><span class="sxs-lookup"><span data-stu-id="f3b05-135">State 4</span></span>|<span data-ttu-id="f3b05-136">Во время выполнения команды произошло нарушение предположения или нарушение доступа.</span><span class="sxs-lookup"><span data-stu-id="f3b05-136">A failed assertion or access violation occurred during the execution of the command.</span></span>|  
|<span data-ttu-id="f3b05-137">Состояние 5</span><span class="sxs-lookup"><span data-stu-id="f3b05-137">State 5</span></span>|<span data-ttu-id="f3b05-138">Возникла неизвестная ошибка, которая привела к непредвиденному завершению команды DBCC.</span><span class="sxs-lookup"><span data-stu-id="f3b05-138">An unknown failure occurred that unexpectedly terminated the DBCC command.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="f3b05-139">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="f3b05-139">User Action</span></span>  
 <span data-ttu-id="f3b05-140">В следующей таблице приведены действия пользователя, соответствующие указанному состоянию ошибки.</span><span class="sxs-lookup"><span data-stu-id="f3b05-140">The following table provides the user action that is appropriate for the specified error state.</span></span>  
  
|<span data-ttu-id="f3b05-141">Состояние ошибки</span><span class="sxs-lookup"><span data-stu-id="f3b05-141">Error state</span></span>|<span data-ttu-id="f3b05-142">Рекомендуемые действия</span><span class="sxs-lookup"><span data-stu-id="f3b05-142">User action</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f3b05-143">Состояние 0</span><span class="sxs-lookup"><span data-stu-id="f3b05-143">State 0</span></span>|<span data-ttu-id="f3b05-144">Выполните восстановление из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f3b05-144">Restore from backup.</span></span>|  
|<span data-ttu-id="f3b05-145">Состояние 1</span><span class="sxs-lookup"><span data-stu-id="f3b05-145">State 1</span></span>|<span data-ttu-id="f3b05-146">Обратитесь в службу поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)] (CSS).</span><span class="sxs-lookup"><span data-stu-id="f3b05-146">Contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>|  
|<span data-ttu-id="f3b05-147">Состояние 2</span><span class="sxs-lookup"><span data-stu-id="f3b05-147">State 2</span></span>|<span data-ttu-id="f3b05-148">Выполните восстановление из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f3b05-148">Restore from backup.</span></span>|  
|<span data-ttu-id="f3b05-149">Состояние 3</span><span class="sxs-lookup"><span data-stu-id="f3b05-149">State 3</span></span>|<span data-ttu-id="f3b05-150">Выполните восстановление из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f3b05-150">Restore from backup.</span></span>|  
|<span data-ttu-id="f3b05-151">Состояние 4</span><span class="sxs-lookup"><span data-stu-id="f3b05-151">State 4</span></span>|<span data-ttu-id="f3b05-152">Обратитесь в службу поддержки пользователей.</span><span class="sxs-lookup"><span data-stu-id="f3b05-152">Contact CSS.</span></span>|  
|<span data-ttu-id="f3b05-153">Состояние 5</span><span class="sxs-lookup"><span data-stu-id="f3b05-153">State 5</span></span>|<span data-ttu-id="f3b05-154">Запустите команду еще раз:</span><span class="sxs-lookup"><span data-stu-id="f3b05-154">Run the command again.</span></span> <span data-ttu-id="f3b05-155">если устранить неполадку не удается, обратитесь в службу поддержки пользователей.</span><span class="sxs-lookup"><span data-stu-id="f3b05-155">If the problem persists, contact CSS.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3b05-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3b05-156">See Also</span></span>  
 [<span data-ttu-id="f3b05-157">DBCC (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f3b05-157">DBCC &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-transact-sql)  
  
  
