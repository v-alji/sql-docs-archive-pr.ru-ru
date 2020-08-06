---
title: MSSQLSERVER_17067 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17067 (Database Engine error)
ms.assetid: 32c1f0e8-db70-4836-95b2-8833be9e0ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4ff3de7ed2fbe54a32aaa501979a3acb6b452947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667155"
---
# <a name="mssqlserver_17067"></a><span data-ttu-id="bcb17-102">MSSQLSERVER_17067</span><span class="sxs-lookup"><span data-stu-id="bcb17-102">MSSQLSERVER_17067</span></span>
    
## <a name="details"></a><span data-ttu-id="bcb17-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="bcb17-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bcb17-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="bcb17-104">Product Name</span></span>|<span data-ttu-id="bcb17-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bcb17-105">SQL Server</span></span>|  
|<span data-ttu-id="bcb17-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="bcb17-106">Event ID</span></span>|<span data-ttu-id="bcb17-107">17067</span><span class="sxs-lookup"><span data-stu-id="bcb17-107">17067</span></span>|  
|<span data-ttu-id="bcb17-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="bcb17-108">Event Source</span></span>|<span data-ttu-id="bcb17-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bcb17-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bcb17-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="bcb17-110">Component</span></span>|<span data-ttu-id="bcb17-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bcb17-111">SQLEngine</span></span>|  
|<span data-ttu-id="bcb17-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="bcb17-112">Symbolic Name</span></span>|<span data-ttu-id="bcb17-113">SQLASSERT_MESG</span><span class="sxs-lookup"><span data-stu-id="bcb17-113">SQLASSERT_MESG</span></span>|  
|<span data-ttu-id="bcb17-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="bcb17-114">Message Text</span></span>|<span data-ttu-id="bcb17-115">Утверждение SQL Server: Файл: \<%s>, строка = %d %s.</span><span class="sxs-lookup"><span data-stu-id="bcb17-115">SQL Server Assertion: File: \<%s>, line = %d %s.</span></span> <span data-ttu-id="bcb17-116">Возможно, эта ошибка связана со временем.</span><span class="sxs-lookup"><span data-stu-id="bcb17-116">This error may be timing-related.</span></span> <span data-ttu-id="bcb17-117">Если ошибка не исчезнет после повторного выполнения инструкции, проверьте целостность структуры базы данных при помощи инструкции DBCC CHECKDB или перезапустите сервер, чтобы убедиться, что структуры данных в памяти не повреждены.</span><span class="sxs-lookup"><span data-stu-id="bcb17-117">If the error persists after rerunning the statement, use DBCC CHECKDB to check the database for structural integrity, or restart the server to ensure in-memory data structures are not corrupted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bcb17-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="bcb17-118">Explanation</span></span>  
 <span data-ttu-id="bcb17-119">Эта ошибка может быть вызвана нерегулярными проблемами, связанными со временем, или повреждением данных в памяти или на диске.</span><span class="sxs-lookup"><span data-stu-id="bcb17-119">This error can be caused by transient, timing-related errors, or by in-memory or on-disk data corruption.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bcb17-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="bcb17-120">User Action</span></span>  
 <span data-ttu-id="bcb17-121">Выполните повторно инструкцию, которая вызвала появление исключения.</span><span class="sxs-lookup"><span data-stu-id="bcb17-121">Rerun the statement that caused the exception to fire.</span></span> <span data-ttu-id="bcb17-122">Если ошибка вызвана событием, связанным со временем, она, возможно, не повторится.</span><span class="sxs-lookup"><span data-stu-id="bcb17-122">If the error was caused by a timing-related event, the error may not recur.</span></span> <span data-ttu-id="bcb17-123">Если ошибка не исчезла, проверьте диск на наличие повреждений при помощи инструкции DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="bcb17-123">If the problem persists, run DBCC CHECKDB to check for on-disk corruption.</span></span> <span data-ttu-id="bcb17-124">Перезапустите сервер, чтобы убедиться, что структуры данных в памяти не повреждены.</span><span class="sxs-lookup"><span data-stu-id="bcb17-124">Restart the server to ensure that the in-memory data structures are not corrupted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb17-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="bcb17-125">See Also</span></span>  
 [<span data-ttu-id="bcb17-126">DBCC CHECKDB (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bcb17-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
