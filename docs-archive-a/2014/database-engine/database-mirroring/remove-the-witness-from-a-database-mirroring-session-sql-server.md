---
title: Удаление следящего сервера из сеанса зеркального отображения базы данных (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], turning off
- witness [SQL Server], removing
- database mirroring [SQL Server], witness
ms.assetid: f3ce7afc-8936-4d35-80ce-d0f8fbc318d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5ede54aca3588a6fcd7cee8759112b606eac752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733073"
---
# <a name="remove-the-witness-from-a-database-mirroring-session-sql-server"></a><span data-ttu-id="a6b79-102">Удаление следящего сервера из сеанса зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a6b79-102">Remove the Witness from a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="a6b79-103">В этом разделе описано, как удалить следящий сервер из сеанса зеркального отображения базы данных [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6b79-103">This topic describes how to remove a witness from a database mirroring session in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a6b79-104">Во время сеанса зеркального отображения владелец базы данных в любой момент может отключить следящий сервер для сеанса зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="a6b79-104">At any time during a database mirroring session, the database owner can turn off the witness for a database mirroring session.</span></span>  
  
 <span data-ttu-id="a6b79-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a6b79-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a6b79-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a6b79-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a6b79-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a6b79-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a6b79-108">**Удаление следящего сервера с помощью:**</span><span class="sxs-lookup"><span data-stu-id="a6b79-108">**To Replace remove the witness, using:**</span></span>  
  
     [<span data-ttu-id="a6b79-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6b79-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a6b79-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6b79-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="a6b79-111">**Дальнейшие действия**  [После удаления следящего сервера](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a6b79-111">**Follow Up:**  [After Removing the Witness](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a6b79-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a6b79-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a6b79-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="a6b79-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a6b79-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="a6b79-114">Permissions</span></span>  
 <span data-ttu-id="a6b79-115">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="a6b79-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a6b79-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6b79-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="a6b79-117">Удаление следящего сервера</span><span class="sxs-lookup"><span data-stu-id="a6b79-117">To remove the witness</span></span>  
  
1.  <span data-ttu-id="a6b79-118">Установите соединение с экземпляром основного сервера и на панели **Обозреватель объектов** щелкните имя сервера, чтобы развернуть этот узел.</span><span class="sxs-lookup"><span data-stu-id="a6b79-118">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a6b79-119">Раскройте **Базы данных**и выберите базу данных, для которой нужно удалить следящий сервер.</span><span class="sxs-lookup"><span data-stu-id="a6b79-119">Expand **Databases**, and select the database whose witness you want to remove.</span></span>  
  
3.  <span data-ttu-id="a6b79-120">Щелкните базу данных правой кнопкой мыши, выберите **Задачи**, а затем **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="a6b79-120">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="a6b79-121">Откроется страница **Зеркальное отображение** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="a6b79-121">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="a6b79-122">Чтобы удалить следящий сервер, удалите его сетевой адрес из поля **Следящий** .</span><span class="sxs-lookup"><span data-stu-id="a6b79-122">To remove the witness, delete its server network address from the **Witness** field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a6b79-123">При переключении из режима высокого уровня безопасности с автоматической отработкой отказа в высокопроизводительный режим поле **Следящий** автоматически очищается.</span><span class="sxs-lookup"><span data-stu-id="a6b79-123">If you switch from high-safety mode with automatic failover to high-performance mode, the **Witness** field is automatically cleared.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a6b79-124">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6b79-124">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="a6b79-125">Удаление следящего сервера</span><span class="sxs-lookup"><span data-stu-id="a6b79-125">To remove the witness</span></span>  
  
1.  <span data-ttu-id="a6b79-126">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] на экземпляре любого из серверов-участников.</span><span class="sxs-lookup"><span data-stu-id="a6b79-126">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on either partner server instance.</span></span>  
  
2.  <span data-ttu-id="a6b79-127">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a6b79-127">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a6b79-128">Выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="a6b79-128">Issue the following statement:</span></span>  
  
     <span data-ttu-id="a6b79-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *имя_базы_данных* SET WITNESS OFF</span><span class="sxs-lookup"><span data-stu-id="a6b79-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET WITNESS OFF</span></span>  
  
     <span data-ttu-id="a6b79-130">где *имя_базы_данных* — имя зеркально отображаемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="a6b79-130">where *database_name* is the name of the mirrored database.</span></span>  
  
     <span data-ttu-id="a6b79-131">В следующем примере показано удаление следящего сервера для базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6b79-131">The following example removes the witness from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET WITNESS OFF ;  
    ```  
  
##  <a name="follow-up-after-removing-the-witness"></a><a name="FollowUp"></a><span data-ttu-id="a6b79-132">Дальнейшие действия. После удаления следящего сервера</span><span class="sxs-lookup"><span data-stu-id="a6b79-132">Follow Up: After Removing the Witness</span></span>  
 <span data-ttu-id="a6b79-133">При отключении следящего сервера [режим работы](database-mirroring-operating-modes.md)изменяется в соответствии с параметром безопасности транзакций.</span><span class="sxs-lookup"><span data-stu-id="a6b79-133">Turning off the witness changes the [operating mode](database-mirroring-operating-modes.md)in accordance with the transaction-safety setting:</span></span>  
  
-   <span data-ttu-id="a6b79-134">Если уровень безопасности транзакций установлен в FULL (значение по умолчанию), то сеанс использует синхронный режим с высоким уровнем защиты без автоматической отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="a6b79-134">If transaction safety is set to FULL (the default), the session uses high-safety, synchronous mode without automatic failover.</span></span>  
  
-   <span data-ttu-id="a6b79-135">Когда безопасность транзакций отключена, сеанс работает асинхронно (в режиме высокой производительности), не требуя кворума.</span><span class="sxs-lookup"><span data-stu-id="a6b79-135">If transaction safety is set to OFF, the session operates asynchronously (in high-performance mode) without requiring quorum.</span></span> <span data-ttu-id="a6b79-136">При отключенной безопасности транзакций настоятельно рекомендуется также отключить следящий сервер.</span><span class="sxs-lookup"><span data-stu-id="a6b79-136">Whenever transaction safety is turned off, we strongly recommend also turning the witness off.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a6b79-137">Параметры безопасности транзакций для каждого участника на экземпляре сервера доступны через представление каталога [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql), в столбцах **mirroring_safety_level** и **mirroring_safety_level_desc**.</span><span class="sxs-lookup"><span data-stu-id="a6b79-137">The transaction safety setting of the database is recorded on each partner in the [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql) catalog view in the **mirroring_safety_level** and **mirroring_safety_level_desc** columns.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a6b79-138">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="a6b79-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a6b79-139">Добавление следящего сервера для зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a6b79-139">Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="a6b79-140">Добавление или замена следящего сервера зеркального отображения базы данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a6b79-140">Add or Replace a Database Mirroring Witness &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/add-or-replace-a-database-mirroring-witness-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="a6b79-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6b79-141">See Also</span></span>  
 <span data-ttu-id="a6b79-142">[Зеркальное отображение базы данных ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="a6b79-142">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="a6b79-143">[Изменение безопасности транзакций в сеансе зеркального отображения базы данных &#40;&#41;Transact-SQL](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="a6b79-143">[Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="a6b79-144">[Добавление следящего сервера зеркального отображения базы данных с использованием проверки подлинности Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="a6b79-144">[Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="a6b79-145">Следящий сервер зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="a6b79-145">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
