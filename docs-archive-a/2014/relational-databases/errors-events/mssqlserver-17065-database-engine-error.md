---
title: MSSQLSERVER_17065 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17065 (Database Engine error)
ms.assetid: 63c2ba5a-be34-461e-bee1-03c25b396cd2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47aebfa29b60a1c2ae50c6699946312996d26e6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667161"
---
# <a name="mssqlserver_17065"></a><span data-ttu-id="4a2bc-102">MSSQLSERVER_17065</span><span class="sxs-lookup"><span data-stu-id="4a2bc-102">MSSQLSERVER_17065</span></span>
    
## <a name="details"></a><span data-ttu-id="4a2bc-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="4a2bc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a2bc-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="4a2bc-104">Product Name</span></span>|<span data-ttu-id="4a2bc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a2bc-105">SQL Server</span></span>|  
|<span data-ttu-id="4a2bc-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4a2bc-106">Event ID</span></span>|<span data-ttu-id="4a2bc-107">17065</span><span class="sxs-lookup"><span data-stu-id="4a2bc-107">17065</span></span>|  
|<span data-ttu-id="4a2bc-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="4a2bc-108">Event Source</span></span>|<span data-ttu-id="4a2bc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4a2bc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4a2bc-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="4a2bc-110">Component</span></span>|<span data-ttu-id="4a2bc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4a2bc-111">SQLEngine</span></span>|  
|<span data-ttu-id="4a2bc-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="4a2bc-112">Symbolic Name</span></span>|<span data-ttu-id="4a2bc-113">SQLASSERT_BOTH</span><span class="sxs-lookup"><span data-stu-id="4a2bc-113">SQLASSERT_BOTH</span></span>|  
|<span data-ttu-id="4a2bc-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="4a2bc-114">Message Text</span></span>|<span data-ttu-id="4a2bc-115">Утверждение SQL Server: Файл: \<%s>, строка=%d Предположение об ошибке '%s' %s.</span><span class="sxs-lookup"><span data-stu-id="4a2bc-115">SQL Server Assertion: File: \<%s>, line = %d Failed Assertion = '%s' %s.</span></span> <span data-ttu-id="4a2bc-116">Возможно, эта ошибка связана со временем.</span><span class="sxs-lookup"><span data-stu-id="4a2bc-116">This error may be timing-related.</span></span> <span data-ttu-id="4a2bc-117">Если ошибка не исчезнет после повторного выполнения инструкции, проверьте целостность структуры базы данных при помощи инструкции DBCC CHECKDB или перезапустите сервер, чтобы убедиться, что структуры данных в памяти не повреждены.</span><span class="sxs-lookup"><span data-stu-id="4a2bc-117">If the error persists after rerunning the statement, use DBCC CHECKDB to check the database for structural integrity, or restart the server to ensure in-memory data structures are not corrupted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4a2bc-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="4a2bc-118">Explanation</span></span>  
 <span data-ttu-id="4a2bc-119">Эта ошибка может быть вызвана нерегулярными проблемами, связанными со временем, или повреждением данных в памяти или на диске.</span><span class="sxs-lookup"><span data-stu-id="4a2bc-119">This error can be caused by transient, timing-related errors, or by in-memory or on-disk data corruption.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4a2bc-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="4a2bc-120">User Action</span></span>  
 <span data-ttu-id="4a2bc-121">Выполните повторно инструкцию, которая вызвала появление исключения.</span><span class="sxs-lookup"><span data-stu-id="4a2bc-121">Rerun the statement that caused the exception to fire.</span></span> <span data-ttu-id="4a2bc-122">Если ошибка вызвана событием, связанным со временем, она, возможно, не повторится.</span><span class="sxs-lookup"><span data-stu-id="4a2bc-122">If the error was caused by a timing-related event, the error may not recur.</span></span> <span data-ttu-id="4a2bc-123">Если ошибка не исчезла, проверьте диск на наличие повреждений при помощи инструкции DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="4a2bc-123">If the problem persists, run DBCC CHECKDB to check for on-disk corruption.</span></span> <span data-ttu-id="4a2bc-124">Перезапустите сервер, чтобы убедиться, что структуры данных в памяти не повреждены.</span><span class="sxs-lookup"><span data-stu-id="4a2bc-124">Restart the server to ensure the in-memory data structures are not corrupted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a2bc-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a2bc-125">See Also</span></span>  
 [<span data-ttu-id="4a2bc-126">DBCC CHECKDB (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4a2bc-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
