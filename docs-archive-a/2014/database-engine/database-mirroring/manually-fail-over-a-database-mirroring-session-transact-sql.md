---
title: Переключение сеанса зеркального отображения базы данных на другой ресурс вручную (язык Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 36218d61-b5f5-4194-905a-608e0e903db4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c04ea4908ccbc4cfe4f6bb3606347dd444ef416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655908"
---
# <a name="manually-fail-over-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="83517-102">Переключение сеанса зеркального отображения базы данных на другой ресурс вручную (язык Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="83517-102">Manually Fail Over a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="83517-103">Когда зеркальная база данных синхронизирована (то есть база данных находится в состоянии SYNCHRONIZED), владелец базы данных может инициировать отработку отказа на зеркальном сервере вручную.</span><span class="sxs-lookup"><span data-stu-id="83517-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span> <span data-ttu-id="83517-104">Переход на другой ресурс вручную может быть инициирован только с основного сервера.</span><span class="sxs-lookup"><span data-stu-id="83517-104">Manual failover can be initiated only from the principal server.</span></span>  
  
### <a name="to-manually-fail-over-a-database-mirroring-session"></a><span data-ttu-id="83517-105">Отработка отказа в сеансе зеркального отображения базы данных вручную</span><span class="sxs-lookup"><span data-stu-id="83517-105">To manually fail over a database mirroring session</span></span>  
  
1.  <span data-ttu-id="83517-106">Подключитесь к основному серверу.</span><span class="sxs-lookup"><span data-stu-id="83517-106">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="83517-107">Задайте базу данных **master** в качестве контекста базы данных:</span><span class="sxs-lookup"><span data-stu-id="83517-107">Set the database context to the **master** database:</span></span>  
  
     `USE master;`  
  
3.  <span data-ttu-id="83517-108">Введите следующую инструкцию на основном сервере:</span><span class="sxs-lookup"><span data-stu-id="83517-108">Issue the following statement on the principal server:</span></span>  
  
     <span data-ttu-id="83517-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *имя_базы_данных* SET PARTNER FAILOVER, где *имя_базы_данных* — это зеркально отображаемая база данных.</span><span class="sxs-lookup"><span data-stu-id="83517-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, where *database_name* is the mirrored database.</span></span>  
  
     <span data-ttu-id="83517-110">В результате роль основного сервера немедленно перейдет к зеркальному серверу.</span><span class="sxs-lookup"><span data-stu-id="83517-110">This initiates an immediate transition of the mirror server to the principal role.</span></span>  
  
 <span data-ttu-id="83517-111">На бывшем основном сервере произойдет отключение клиентов базы данных с откатом незавершенных транзакций.</span><span class="sxs-lookup"><span data-stu-id="83517-111">On the former principal, clients are disconnected from the database and in-flight transactions are rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83517-112">Транзакции, подготовленные с помощью координатора распределенных транзакций [!INCLUDE[msCoName](../../includes/msconame-md.md)] , но еще не зафиксированные на момент отработки отказа, после отработки отказа базы данных будут считаться отмененными.</span><span class="sxs-lookup"><span data-stu-id="83517-112">Transactions that have been prepared by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator but are still not committed when a failover occurs are considered aborted after the database has failed over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83517-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="83517-113">See Also</span></span>  
 <span data-ttu-id="83517-114">[Зеркальное отображение базы данных ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="83517-114">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="83517-115">[Вручную отработка отказа сеанса зеркального отображения базы данных &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="83517-115">[Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="83517-116">Переключение ролей во время сеанса зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="83517-116">Role Switching During a Database Mirroring Session &#40;SQL Server&#41;</span></span>](role-switching-during-a-database-mirroring-session-sql-server.md)  
  
  
