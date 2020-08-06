---
title: MSSQLSERVER_17300 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17300 (Database Engine error)
ms.assetid: c1d6bfb6-28af-4df6-8087-25807602d282
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f77e39c71901166085d011d6d00f9a4a379bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729545"
---
# <a name="mssqlserver_17300"></a><span data-ttu-id="60264-102">MSSQLSERVER_17300</span><span class="sxs-lookup"><span data-stu-id="60264-102">MSSQLSERVER_17300</span></span>
    
## <a name="details"></a><span data-ttu-id="60264-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="60264-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60264-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="60264-104">Product Name</span></span>|<span data-ttu-id="60264-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="60264-105">SQL Server</span></span>|  
|<span data-ttu-id="60264-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="60264-106">Event ID</span></span>|<span data-ttu-id="60264-107">17300</span><span class="sxs-lookup"><span data-stu-id="60264-107">17300</span></span>|  
|<span data-ttu-id="60264-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="60264-108">Event Source</span></span>|<span data-ttu-id="60264-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="60264-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="60264-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="60264-110">Component</span></span>|<span data-ttu-id="60264-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="60264-111">SQLEngine</span></span>|  
|<span data-ttu-id="60264-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="60264-112">Symbolic Name</span></span>|<span data-ttu-id="60264-113">PROC_OUT_OF_SYSTASK_SESSIONS</span><span class="sxs-lookup"><span data-stu-id="60264-113">PROC_OUT_OF_SYSTASK_SESSIONS</span></span>|  
|<span data-ttu-id="60264-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="60264-114">Message Text</span></span>|<span data-ttu-id="60264-115">SQL Server не удалось запустить новую системную задачу либо из-за недостатка памяти, либо из-за превышения заданного в конфигурации максимального числа сеансов, допустимого для сервера.</span><span class="sxs-lookup"><span data-stu-id="60264-115">SQL Server was unable to run a new system task, either because there is insufficient memory or the number of configured sessions exceeds the maximum allowed in the server.</span></span> <span data-ttu-id="60264-116">Проверьте, что на сервере достаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="60264-116">Verify that the server has adequate memory.</span></span> <span data-ttu-id="60264-117">Используйте хранимую процедуру sp_configure с параметром «user connections», чтобы выяснить максимально допустимое число соединений пользователя.</span><span class="sxs-lookup"><span data-stu-id="60264-117">Use sp_configure with option 'user connections' to check the maximum number of user connections allowed.</span></span> <span data-ttu-id="60264-118">Текущее число сеансов, включая пользовательские процессы, можно получить из представления sys.dm_exec_sessions.</span><span class="sxs-lookup"><span data-stu-id="60264-118">Use sys.dm_exec_sessions to check the current number of sessions, including user processes.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60264-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="60264-119">Explanation</span></span>  
 <span data-ttu-id="60264-120">Не удалось запустить новую системную задачу либо из-за недостатка памяти, либо из-за превышения заданного в конфигурации числа сеансов для сервера.</span><span class="sxs-lookup"><span data-stu-id="60264-120">An attempt to run a new system task failed because of insufficient memory or because the number of configured sessions in the server was exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60264-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="60264-121">User Action</span></span>  
 <span data-ttu-id="60264-122">Проверьте, что на сервере достаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="60264-122">Verify that the server has enough memory.</span></span> <span data-ttu-id="60264-123">Проверьте текущее число системных задач с помощью представления sys.dm_exec_sessions и проверьте заданное значение максимального числа соединений пользователя с помощью хранимой процедуры sp_configure.</span><span class="sxs-lookup"><span data-stu-id="60264-123">Verify the current number of system tasks by using sys.dm_exec_sessions, and verify the configured value of maximum user connections by using sp_configure.</span></span>  
  
 <span data-ttu-id="60264-124">При необходимости выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="60264-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="60264-125">Добавьте память на сервер.</span><span class="sxs-lookup"><span data-stu-id="60264-125">Add more memory to the server.</span></span>  
  
-   <span data-ttu-id="60264-126">Завершите один или несколько сеансов.</span><span class="sxs-lookup"><span data-stu-id="60264-126">Terminate one or more sessions.</span></span>  
  
-   <span data-ttu-id="60264-127">Увеличьте максимально допустимое число одновременно подключенных пользователей на сервере.</span><span class="sxs-lookup"><span data-stu-id="60264-127">Increase the maximum number of user connections allowed on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60264-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="60264-128">See Also</span></span>  
 <span data-ttu-id="60264-129">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="60264-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="60264-130">[Параметры конфигурации сервера (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60264-130">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="60264-131">[sys.dm_exec_sessions (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="60264-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span></span>  
 <span data-ttu-id="60264-132">[Настройка параметра конфигурации сервера «User Connections»](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="60264-132">[Configure the user connections Server Configuration Option](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="60264-133">KILL (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="60264-133">KILL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/kill-transact-sql)  
  
  
