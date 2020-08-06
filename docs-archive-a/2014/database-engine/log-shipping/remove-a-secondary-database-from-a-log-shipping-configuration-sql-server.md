---
title: Удаление базы данных-получателя из конфигурации доставки журналов (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- deleting secondary databases
- secondary databases [SQL Server], in log shipping
- removing secondary databases
- secondary data files [SQL Server], removing
- log shipping [SQL Server], secondary databases
ms.assetid: ebe368a4-ca1c-45d0-9a71-3ddbd5b26a8e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 119f2762d41d0787b6b3279507e9671e89fddfca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665535"
---
# <a name="remove-a-secondary-database-from-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="b4e25-102">Удаление базы данных-получателя из конфигурации доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4e25-102">Remove a Secondary Database from a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="b4e25-103">В этом разделе описывается удаление базы данных-получателя доставки журналов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или языка [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4e25-103">This topic describes how to remove a log shipping secondary database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b4e25-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b4e25-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b4e25-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b4e25-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b4e25-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b4e25-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b4e25-107">**Удаление базы данных-получателя доставки журналов с помощью:**</span><span class="sxs-lookup"><span data-stu-id="b4e25-107">**To remove a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="b4e25-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b4e25-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b4e25-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4e25-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="b4e25-110">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="b4e25-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b4e25-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b4e25-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b4e25-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="b4e25-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b4e25-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="b4e25-113">Permissions</span></span>  
 <span data-ttu-id="b4e25-114">Для вызова хранимых процедур доставки журналов необходимо членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="b4e25-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b4e25-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b4e25-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-a-log-shipping-secondary-database"></a><span data-ttu-id="b4e25-116">Удаление базы данных-получателя доставки журналов</span><span class="sxs-lookup"><span data-stu-id="b4e25-116">To remove a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="b4e25-117">Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который в данный момент является сервером-источником доставки журналов и разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b4e25-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="b4e25-118">Разверните узел **Базы данных**, щелкните правой кнопкой мыши базу данных-источник доставки журналов и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b4e25-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="b4e25-119">В области **Выбор страницы**щелкните **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="b4e25-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="b4e25-120">В меню **Экземпляры сервера-получателя и базы данных**щелкните базу данных, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="b4e25-120">Under **Secondary server instances and databases**, click the database you want to remove.</span></span>  
  
5.  <span data-ttu-id="b4e25-121">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b4e25-121">Click **Remove**.</span></span>  
  
6.  <span data-ttu-id="b4e25-122">Нажмите кнопку **ОК** , чтобы обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b4e25-122">Click **OK** to update the configuration.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b4e25-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4e25-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-secondary-database"></a><span data-ttu-id="b4e25-124">Удаление базы данных-получатель</span><span class="sxs-lookup"><span data-stu-id="b4e25-124">To Remove a Secondary Database</span></span>  
  
1.  <span data-ttu-id="b4e25-125">Чтобы удалить сведения о базе данных-получателе с сервера-источника, запустите на нем хранимую процедуру [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="b4e25-125">On the primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="b4e25-126">Чтобы удалить базу данных-получатель с сервера-получателя, запустите на нем хранимую процедуру [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="b4e25-126">On the secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4e25-127">Если других баз данных-получателей с таким же идентификатором получателя нет, процедура **sp_delete_log_shipping_secondary_primary** запускается из процедуры **sp_delete_log_shipping_secondary_database** и удаляет запись об идентификаторе получателя, а также задания копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="b4e25-127">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="b4e25-128">На сервере-получателе отключите задания копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="b4e25-128">On the secondary server, disable the copy and restore jobs.</span></span> <span data-ttu-id="b4e25-129">Дополнительные сведения см. в статье [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="b4e25-129">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b4e25-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="b4e25-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b4e25-131">Обновление доставки журналов до SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b4e25-131">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="b4e25-132">Настройка доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4e25-132">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="b4e25-133">Добавление базы данных-получателя в конфигурацию доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4e25-133">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="b4e25-134">Удаление доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4e25-134">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="b4e25-135">Просмотр отчета о доставке журналов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b4e25-135">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b4e25-136">Наблюдение за доставкой журналов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b4e25-136">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="b4e25-137">Переход на вторичный сервер доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4e25-137">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4e25-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4e25-138">See Also</span></span>  
 <span data-ttu-id="b4e25-139">[Сведения о доставке журналов (SQL Server)](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b4e25-139">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="b4e25-140">Таблицы доставки журналов и хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="b4e25-140">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
