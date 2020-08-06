---
title: Удаление доставки журналов (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], removing
- removing log shipping
- deleting log shipping
ms.assetid: 859373db-c744-4a4b-8479-45163f61e8cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 14fdc36c66073e89dcc2014aed4319a2ce78a98f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664466"
---
# <a name="remove-log-shipping-sql-server"></a><span data-ttu-id="2b242-102">Удаление доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2b242-102">Remove Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="2b242-103">В данном разделе описывается удаление доставки журналов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b242-103">This topic describes how to remove log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2b242-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2b242-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2b242-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2b242-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2b242-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2b242-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2b242-107">**Удаление доставки журналов с помощью:**</span><span class="sxs-lookup"><span data-stu-id="2b242-107">**To remove log shipping, using:**</span></span>  
  
     [<span data-ttu-id="2b242-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b242-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2b242-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b242-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="2b242-110">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2b242-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2b242-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2b242-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2b242-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="2b242-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2b242-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="2b242-113">Permissions</span></span>  
 <span data-ttu-id="2b242-114">Для вызова хранимых процедур доставки журналов необходимо членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="2b242-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2b242-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b242-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="2b242-116">Удаление доставки журналов</span><span class="sxs-lookup"><span data-stu-id="2b242-116">To remove log shipping</span></span>  
  
1.  <span data-ttu-id="2b242-117">Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который в данный момент является сервером-источником доставки журналов и разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="2b242-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="2b242-118">Разверните узел **Базы данных**, щелкните правой кнопкой мыши базу данных-источник доставки журналов и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2b242-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2b242-119">В области **Выбор страницы**щелкните **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="2b242-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="2b242-120">Снимите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов** .</span><span class="sxs-lookup"><span data-stu-id="2b242-120">Clear the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
5.  <span data-ttu-id="2b242-121">Нажмите кнопку **ОК** , чтобы удалить доставку журналов из этой базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="2b242-121">Click **OK** to remove log shipping from this primary database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2b242-122">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b242-122">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="2b242-123">Удаление доставки журналов</span><span class="sxs-lookup"><span data-stu-id="2b242-123">To Remove Log Shipping</span></span>  
  
1.  <span data-ttu-id="2b242-124">Чтобы удалить сведения о базе данных-получателе с сервера-источника доставки журналов, запустите на нем хранимую процедуру [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2b242-124">On the log shipping primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="2b242-125">Чтобы удалить базу данных-получатель с сервера-получателя доставки журналов, запустите на нем хранимую процедуру [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2b242-125">On the log shipping secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2b242-126">Если других баз данных-получателей с таким же идентификатором получателя нет, процедура **sp_delete_log_shipping_secondary_primary** запускается из процедуры **sp_delete_log_shipping_secondary_database** и удаляет запись об идентификаторе получателя, а также задания копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="2b242-126">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="2b242-127">Чтобы удалить данные о конфигурации доставки журналов с сервера-источника доставки журналов, запустите на нем хранимую процедуру **sp_delete_log_shipping_primary_database** .</span><span class="sxs-lookup"><span data-stu-id="2b242-127">On the log shipping primary server, execute **sp_delete_log_shipping_primary_database** to delete information about the log shipping configuration from the primary server.</span></span> <span data-ttu-id="2b242-128">При этом задание резервного копирования также будет удалено.</span><span class="sxs-lookup"><span data-stu-id="2b242-128">This also deletes the backup job.</span></span>  
  
4.  <span data-ttu-id="2b242-129">Отключите задание резервного копирования на сервере-источнике доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="2b242-129">On the log shipping primary server, disable the backup job.</span></span> <span data-ttu-id="2b242-130">Дополнительные сведения см. в статье [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="2b242-130">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
5.  <span data-ttu-id="2b242-131">На сервере-получателе доставки журналов отключите задания копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="2b242-131">On the log shipping secondary server, disable the copy and restore jobs.</span></span>  
  
6.  <span data-ttu-id="2b242-132">Кроме того, если база данных-получатель доставки журналов больше не используется, ее можно удалить с сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="2b242-132">Optionally, if you are no longer using the log shipping secondary database, you can delete it from the secondary server.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2b242-133">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2b242-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2b242-134">Обновление доставки журналов до SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b242-134">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="2b242-135">Настройка доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2b242-135">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="2b242-136">Добавление базы данных-получателя в конфигурацию доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2b242-136">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="2b242-137">Удаление базы данных-получателя из конфигурации доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2b242-137">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="2b242-138">Наблюдение за доставкой журналов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2b242-138">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="2b242-139">Переход на вторичный сервер доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2b242-139">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="2b242-140">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="2b242-140">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b242-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="2b242-141">See Also</span></span>  
 <span data-ttu-id="2b242-142">[Сведения о доставке журналов (SQL Server)](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2b242-142">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="2b242-143">Таблицы доставки журналов и хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="2b242-143">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
