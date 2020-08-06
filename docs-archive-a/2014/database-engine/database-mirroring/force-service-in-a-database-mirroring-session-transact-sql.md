---
title: Принудительный запуск службы в сеансе зеркального отображения базы данных (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- forced service [SQL Server]
- database mirroring [SQL Server], forcing service
ms.assetid: 8b6ffe77-35f3-4e2a-a658-8a38a8e1c794
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b909f3602a78f3244ab3cf4479b8745956a7bd62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751467"
---
# <a name="force-service-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="6a989-102">Принудительный запуск службы в сеансе зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6a989-102">Force Service in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="6a989-103">Если в режимах с высокой производительностью и высокой безопасностью без автоматической отработки отказа на основном сервере происходит сбой, в то время как доступен зеркальный сервер, владелец базы данных может сделать базу данных доступной, принудительно переведя ее на другой ресурс (с возможной потерей данных).</span><span class="sxs-lookup"><span data-stu-id="6a989-103">In high-performance mode and high-safety mode without automatic failover, if the principal server fails while the mirror server is available, the database owner can make the database available by forcing service to fail over (with possible data loss) to the mirror database.</span></span> <span data-ttu-id="6a989-104">Этот параметр доступен только при выполнении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="6a989-104">This option is available only under all the following conditions:</span></span>  
  
-   <span data-ttu-id="6a989-105">основной сервер недоступен;</span><span class="sxs-lookup"><span data-stu-id="6a989-105">The principal server is down.</span></span>  
  
-   <span data-ttu-id="6a989-106">параметр WITNESS установлен в OFF или подключен к зеркальному серверу.</span><span class="sxs-lookup"><span data-stu-id="6a989-106">WITNESS is set to OFF or is connected to the mirror server.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6a989-107">Метод принудительного обслуживания применяется исключительно при аварийном восстановлении.</span><span class="sxs-lookup"><span data-stu-id="6a989-107">Forced service is strictly a disaster recovery method.</span></span> <span data-ttu-id="6a989-108">Принудительный запуск службы может привести к потере некоторых данных.</span><span class="sxs-lookup"><span data-stu-id="6a989-108">Forcing service may involve some data loss.</span></span> <span data-ttu-id="6a989-109">Поэтому используйте принудительный запуск службы только в случае, когда потеря некоторых данных допустима, чтобы восстановить службу базы данных немедленно.</span><span class="sxs-lookup"><span data-stu-id="6a989-109">Therefore, force service only if you are willing to risk losing some data in order to restore service to the database immediately.</span></span> <span data-ttu-id="6a989-110">Если это вызовет риск потери значительного объема данных, рекомендуется остановить зеркальное отображение и вручную повторно синхронизировать базы данных.</span><span class="sxs-lookup"><span data-stu-id="6a989-110">If forcing service risks losing significant data, we recommend that you stop mirroring and manually resynchronize the databases.</span></span> <span data-ttu-id="6a989-111">Дополнительные сведения о рисках принудительного обслуживания см. в разделе [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="6a989-111">For more information about the risks of forcing service, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
 <span data-ttu-id="6a989-112">Принудительное обслуживание приостанавливает сеанс и создает новую вилку восстановления.</span><span class="sxs-lookup"><span data-stu-id="6a989-112">Forcing service suspends the session and starts a new recovery fork.</span></span> <span data-ttu-id="6a989-113">Оно вызывает такой же эффект, как и удаление зеркального отображения с восстановлением бывшей основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="6a989-113">The effect of forcing service is similar to removing mirroring and recovering the former principal database.</span></span> <span data-ttu-id="6a989-114">Тем не менее, принудительное обслуживание облегчает повторную синхронизацию базы данных (с возможной потерей данных) при возобновлении зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="6a989-114">However, forcing service facilitates resynchronizing the databases (with possible data loss) when mirroring resumes.</span></span>  
  
### <a name="to-force-service-in-a-database-mirroring-session"></a><span data-ttu-id="6a989-115">Принудительный запуск службы в сеансе зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="6a989-115">To force service in a database mirroring session</span></span>  
  
1.  <span data-ttu-id="6a989-116">Установите соединение с зеркальным сервером.</span><span class="sxs-lookup"><span data-stu-id="6a989-116">Connect to the mirror server.</span></span>  
  
2.  <span data-ttu-id="6a989-117">Выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="6a989-117">Issue the following statement:</span></span>  
  
     <span data-ttu-id="6a989-118">ALTER DATABASE *<имя_базы_данных>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span><span class="sxs-lookup"><span data-stu-id="6a989-118">ALTER DATABASE *<database_name>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span></span>  
  
     <span data-ttu-id="6a989-119">где *<имя_базы_данных>*  — зеркально отображаемая база данных.</span><span class="sxs-lookup"><span data-stu-id="6a989-119">where *<database_name>* is the mirrored database.</span></span>  
  
     <span data-ttu-id="6a989-120">Зеркальный сервер немедленно переходит на основной сервер, а зеркальное отображение приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="6a989-120">The mirror server immediately transitions to principal server, and mirroring is suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a989-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a989-121">See Also</span></span>  
 <span data-ttu-id="6a989-122">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a989-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="6a989-123">Режимы работы зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="6a989-123">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
