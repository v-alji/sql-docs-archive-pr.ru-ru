---
title: MSSQLSERVER_17066 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17066 (Database Engine error)
ms.assetid: 7d650bbf-c583-4af8-9e22-993ee2880d95
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c2bc421fb969e4f24e49871ff97047be9040ae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667160"
---
# <a name="mssqlserver_17066"></a><span data-ttu-id="a9fe6-102">MSSQLSERVER_17066</span><span class="sxs-lookup"><span data-stu-id="a9fe6-102">MSSQLSERVER_17066</span></span>
    
## <a name="details"></a><span data-ttu-id="a9fe6-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a9fe6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9fe6-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a9fe6-104">Product Name</span></span>|<span data-ttu-id="a9fe6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9fe6-105">SQL Server</span></span>|  
|<span data-ttu-id="a9fe6-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a9fe6-106">Event ID</span></span>|<span data-ttu-id="a9fe6-107">17066</span><span class="sxs-lookup"><span data-stu-id="a9fe6-107">17066</span></span>|  
|<span data-ttu-id="a9fe6-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a9fe6-108">Event Source</span></span>|<span data-ttu-id="a9fe6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a9fe6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a9fe6-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a9fe6-110">Component</span></span>|<span data-ttu-id="a9fe6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a9fe6-111">SQLEngine</span></span>|  
|<span data-ttu-id="a9fe6-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a9fe6-112">Symbolic Name</span></span>|<span data-ttu-id="a9fe6-113">SQLASSERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="a9fe6-113">SQLASSERT_ONLY</span></span>|  
|<span data-ttu-id="a9fe6-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a9fe6-114">Message Text</span></span>|<span data-ttu-id="a9fe6-115">Утверждение SQL Server: Файл: \<%s>, строка=%d Ошибочное утверждение = "%s".</span><span class="sxs-lookup"><span data-stu-id="a9fe6-115">SQL Server Assertion: File: \<%s>, line=%d Failed Assertion = '%s'.</span></span> <span data-ttu-id="a9fe6-116">Возможно, эта ошибка связана со временем.</span><span class="sxs-lookup"><span data-stu-id="a9fe6-116">This error may be timing-related.</span></span> <span data-ttu-id="a9fe6-117">Если ошибка не исчезнет после повторного выполнения инструкции, проверьте целостность структуры базы данных при помощи инструкции DBCC CHECKDB или перезапустите сервер, чтобы убедиться, что структуры данных в памяти не повреждены.</span><span class="sxs-lookup"><span data-stu-id="a9fe6-117">If the error persists after rerunning the statement, use DBCC CHECKDB to check the database for structural integrity, or restart the server to ensure in-memory data structures are not corrupted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a9fe6-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a9fe6-118">Explanation</span></span>  
 <span data-ttu-id="a9fe6-119">Эта ошибка может быть вызвана нерегулярными проблемами, связанными со временем, или повреждением данных в памяти или на диске.</span><span class="sxs-lookup"><span data-stu-id="a9fe6-119">This error can be caused by transient, timing-related errors, or by in-memory or on-disk data corruption.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9fe6-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a9fe6-120">User Action</span></span>  
 <span data-ttu-id="a9fe6-121">Выполните повторно инструкцию, которая вызвала появление исключения.</span><span class="sxs-lookup"><span data-stu-id="a9fe6-121">Rerun the statement that caused the exception to fire.</span></span> <span data-ttu-id="a9fe6-122">Если ошибка вызвана событием, связанным со временем, она, возможно, не повторится.</span><span class="sxs-lookup"><span data-stu-id="a9fe6-122">If the error was caused by a timing-related event, the error may not recur.</span></span> <span data-ttu-id="a9fe6-123">Если ошибка не исчезла, проверьте диск на наличие повреждений при помощи инструкции DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="a9fe6-123">If the problem persists, run DBCC CHECKDB to  check for on-disk corruption.</span></span> <span data-ttu-id="a9fe6-124">Перезапустите сервер, чтобы убедиться, что структуры данных в памяти не повреждены.</span><span class="sxs-lookup"><span data-stu-id="a9fe6-124">Restart the server to ensure that the in-memory data structures are not corrupted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fe6-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a9fe6-125">See Also</span></span>  
 [<span data-ttu-id="a9fe6-126">DBCC CHECKDB (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a9fe6-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
