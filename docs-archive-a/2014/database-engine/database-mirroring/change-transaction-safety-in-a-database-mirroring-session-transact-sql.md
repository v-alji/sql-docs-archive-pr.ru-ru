---
title: Изменение безопасности транзакций в сеансах зеркального отображения базы данных (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- transaction safety [SQL Server database mirroring]
ms.assetid: 8b03bb82-8589-4558-8545-9942fe008391
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d8bc9d0fb639770d33507c29a6ec67f60bd0434a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657296"
---
# <a name="change-transaction-safety-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="26136-102">Изменение безопасности транзакций в сеансах зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="26136-102">Change Transaction Safety in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="26136-103">Безопасность транзакций является атрибутом, который контролирует режим работы сеанса.</span><span class="sxs-lookup"><span data-stu-id="26136-103">Transaction safety is the attribute that controls the operating mode of the session.</span></span> <span data-ttu-id="26136-104">Однако в любой момент времени владелец базы данных может изменить безопасность транзакций.</span><span class="sxs-lookup"><span data-stu-id="26136-104">At any time, however, the database owner can change the transaction safety.</span></span> <span data-ttu-id="26136-105">По умолчанию уровень безопасности транзакций установлен в FULL (синхронный режим работы).</span><span class="sxs-lookup"><span data-stu-id="26136-105">By default, the level of transaction safety is set to FULL (synchronous operating mode).</span></span>  
  
 <span data-ttu-id="26136-106">Выключение безопасности транзакций переключает сеанс в асинхронный режим работы, что максимизирует производительность.</span><span class="sxs-lookup"><span data-stu-id="26136-106">Turning off transaction safety shifts the session into asynchronous operating mode, which maximizes performance.</span></span> <span data-ttu-id="26136-107">Если участник становится недоступен, зеркало останавливается, но остается доступным в качестве «горячего» резервирования (переход на ресурс отработки отказа требует принудительного запуска службы с возможностью потери данных).</span><span class="sxs-lookup"><span data-stu-id="26136-107">If the principal becomes unavailable, the mirror stops but is available as a warm standby (failover requires forcing service with possible data loss).</span></span>  
  
### <a name="to-turn-on-transaction-safety"></a><span data-ttu-id="26136-108">Включение безопасности транзакций</span><span class="sxs-lookup"><span data-stu-id="26136-108">To turn on transaction safety</span></span>  
  
1.  <span data-ttu-id="26136-109">Подключитесь к основному серверу.</span><span class="sxs-lookup"><span data-stu-id="26136-109">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="26136-110">Выполните следующую инструкцию Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="26136-110">Issue the following Transact-SQL statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY FULL  
    ```  
  
     <span data-ttu-id="26136-111">где *\<database>*  — имя зеркально отображаемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="26136-111">where *\<database>* is the name of the mirrored database.</span></span>  
  
### <a name="to-turn-off-transaction-safety"></a><span data-ttu-id="26136-112">Выключение безопасности транзакций</span><span class="sxs-lookup"><span data-stu-id="26136-112">To turn off transaction safety</span></span>  
  
1.  <span data-ttu-id="26136-113">Подключитесь к основному серверу.</span><span class="sxs-lookup"><span data-stu-id="26136-113">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="26136-114">Выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="26136-114">Issue the following statement:</span></span>  
  
    ```  
    ALTER DATABASE <database> SET PARTNER SAFETY OFF  
    ```  
  
     <span data-ttu-id="26136-115">где *\<database>*  — зеркально отображаемая база данных.</span><span class="sxs-lookup"><span data-stu-id="26136-115">where *\<database>* is the mirrored database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26136-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="26136-116">See Also</span></span>  
 <span data-ttu-id="26136-117">[Зеркальное отображение базы данных ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="26136-117">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 [<span data-ttu-id="26136-118">Режимы работы зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="26136-118">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
