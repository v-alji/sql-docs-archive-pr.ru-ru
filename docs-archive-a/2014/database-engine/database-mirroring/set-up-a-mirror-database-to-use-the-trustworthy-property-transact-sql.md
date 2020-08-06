---
title: Настройка зеркальной базы данных для использование свойства Trustworthy (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database option
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 6993b076-78ef-453e-b0ea-e341b8e5ee3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd46a08037bcb6eee178a96d84bdab358e5350d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733049"
---
# <a name="set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql"></a><span data-ttu-id="68f90-102">Настройка зеркальной базы данных на использование свойства TRUSTWORTHY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="68f90-102">Set Up a Mirror Database to Use the Trustworthy Property (Transact-SQL)</span></span>
  <span data-ttu-id="68f90-103">При резервном копировании базы данных ее свойство TRUSTWORTHY принимает значение OFF.</span><span class="sxs-lookup"><span data-stu-id="68f90-103">When a database is backed up, the TRUSTWORTHY database property is set to OFF.</span></span> <span data-ttu-id="68f90-104">Поэтому в новой зеркальной базе данных оно всегда будет иметь значение OFF.</span><span class="sxs-lookup"><span data-stu-id="68f90-104">Therefore, on a new mirror database TRUSTWORTHY is always OFF.</span></span> <span data-ttu-id="68f90-105">Если для базы данных после отработки отказа с переходом на другой ресурс требуется доверие, это потребует дополнительных действий по настройке после начала зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="68f90-105">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68f90-106">Дополнительные сведения об этом свойстве базы данных см. в разделе [Свойство базы данных TRUSTWORTHY](../../relational-databases/security/trustworthy-database-property.md).</span><span class="sxs-lookup"><span data-stu-id="68f90-106">For information about this database property, see [TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="68f90-107">Процедура</span><span class="sxs-lookup"><span data-stu-id="68f90-107">Procedure</span></span>  
  
#### <a name="to-setup-a-mirror-database-to-use-the-trustworthy-property"></a><span data-ttu-id="68f90-108">Настройка зеркальной базы данных на использование свойства TRUSTWORTHY</span><span class="sxs-lookup"><span data-stu-id="68f90-108">To setup a mirror database to use the Trustworthy Property</span></span>  
  
1.  <span data-ttu-id="68f90-109">На основном экземпляре сервера необходимо убедиться, что свойство TRUSTWORTHY основной базы данных включено.</span><span class="sxs-lookup"><span data-stu-id="68f90-109">On the principal server instance, verify that the principal database has the Trustworthy property turned on.</span></span>  
  
    ```  
    SELECT name, database_id, is_trustworthy_on FROM sys.databases   
    ```  
  
     <span data-ttu-id="68f90-110">Дополнительные сведения см. в разделе [sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68f90-110">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span>  
  
2.  <span data-ttu-id="68f90-111">После начала зеркального отображения базы данных необходимо убедиться, что в этот момент база данных является основной, в сеансе используется синхронный режим работы и что сеанс уже синхронизирован.</span><span class="sxs-lookup"><span data-stu-id="68f90-111">After starting mirroring, verify that the database is currently the principal database, the session is using a synchronous operating mode, and the session is already synchronized.</span></span>  
  
    ```  
    SELECT database_id, mirroring_role, mirroring_safety_level_desc, mirroring_state_desc FROM sys.database_mirroring  
    ```  
  
     <span data-ttu-id="68f90-112">Дополнительные сведения см. в разделе [sys.database_mirroring (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68f90-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
3.  <span data-ttu-id="68f90-113">Как только завершится синхронизация сеанса зеркального отображения, вручную переключитесь к зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="68f90-113">Once the mirroring session is synchronized, manually fail over to the mirror database.</span></span>  
  
     <span data-ttu-id="68f90-114">Сделать это можно в среде SQL Server Management Studio или при помощи Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="68f90-114">This can be done in either SQL Server Management Studio or using Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="68f90-115">Переключение сеанса зеркального отображения базы данных на другой ресурс вручную (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="68f90-115">Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;</span></span>](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md)  
  
    -   [<span data-ttu-id="68f90-116">Переключение сеанса зеркального отображения базы данных на другой ресурс вручную (язык Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="68f90-116">Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](manually-fail-over-a-database-mirroring-session-transact-sql.md)  
  
4.  <span data-ttu-id="68f90-117">Следующей командой ALTER DATABASE включите свойство TRUSTWORTHY для базы данных:</span><span class="sxs-lookup"><span data-stu-id="68f90-117">Turn on the trustworthy database property using the following ALTER DATABASE command:</span></span>  
  
    ```  
    ALTER DATABASE <database_name> SET TRUSTWORTHY ON  
    ```  
  
     <span data-ttu-id="68f90-118">Дополнительные сведения см. в разделе [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68f90-118">For more information, see[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
5.  <span data-ttu-id="68f90-119">При необходимости можно вручную выполнить отработку отказа, чтобы вернуться к исходному участнику.</span><span class="sxs-lookup"><span data-stu-id="68f90-119">Optionally, manually failover again to return to the original principal.</span></span>  
  
6.  <span data-ttu-id="68f90-120">Кроме того, можно переключиться в асинхронный режим высокой производительности, для чего свойство SAFETY следует установить в значение OFF и проверить, что свойство WITNESS также установлено в значение OFF.</span><span class="sxs-lookup"><span data-stu-id="68f90-120">Optionally, switch to asynchronous, high-performance mode by setting SAFETY to OFF and ensuring that WITNESS is also set to OFF.</span></span>  
  
     <span data-ttu-id="68f90-121">На языке Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="68f90-121">In Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="68f90-122">Изменение безопасности транзакций в сеансах зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="68f90-122">Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md)  
  
    -   [<span data-ttu-id="68f90-123">Удаление следящего сервера из сеанса зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="68f90-123">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
     <span data-ttu-id="68f90-124">В среде SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="68f90-124">In SQL Server Management Studio:</span></span>  
  
    -   [<span data-ttu-id="68f90-125">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="68f90-125">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="68f90-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="68f90-126">See Also</span></span>  
 <span data-ttu-id="68f90-127">[Свойство базы данных TRUSTWORTHY](../../relational-databases/security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="68f90-127">[TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="68f90-128">Настройка зашифрованной зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="68f90-128">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
