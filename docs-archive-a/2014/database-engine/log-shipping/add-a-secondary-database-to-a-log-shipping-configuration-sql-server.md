---
title: Добавление базы данных-получателя в конфигурацию доставки журналов (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- adding secondary databases
- secondary databases [SQL Server], in log shipping
- secondary data files [SQL Server], adding
- log shipping [SQL Server], secondary databases
ms.assetid: b02eba13-f8e6-4684-b7e4-75ea038ea473
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 062df1b53ed74321ba0c75c9df763de79a4802bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664467"
---
# <a name="add-a-secondary-database-to-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="7fbf4-102">Добавление базы данных-получателя в конфигурацию доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7fbf4-102">Add a Secondary Database to a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="7fbf4-103">В этом разделе объясняется, как добавить базу данных-получатель в имеющуюся конфигурацию доставки журналов [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или языка [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fbf4-103">This topic describes how to add a secondary database to an existing log shipping configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7fbf4-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7fbf4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7fbf4-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7fbf4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7fbf4-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7fbf4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7fbf4-107">**Добавление базы данных-получателя доставки журналов с помощью:**</span><span class="sxs-lookup"><span data-stu-id="7fbf4-107">**To add a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="7fbf4-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7fbf4-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7fbf4-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7fbf4-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="7fbf4-110">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7fbf4-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7fbf4-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7fbf4-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7fbf4-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="7fbf4-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7fbf4-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="7fbf4-113">Permissions</span></span>  
 <span data-ttu-id="7fbf4-114">Для вызова хранимых процедур доставки журналов необходимо членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="7fbf4-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7fbf4-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7fbf4-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="7fbf4-116">Добавление базы данных-получателя доставки журналов</span><span class="sxs-lookup"><span data-stu-id="7fbf4-116">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="7fbf4-117">Щелкните правой кнопкой мыши имя базы данных, которая станет базой данных-источником в конфигурации доставки журналов, затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-117">Right-click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7fbf4-118">В области **Выбор страницы**щелкните **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-118">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="7fbf4-119">В разделе **Экземпляры сервера-получателя и базы данных**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-119">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="7fbf4-120">Нажмите **Соединить** и соединитесь с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который нужно использовать в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-120">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
5.  <span data-ttu-id="7fbf4-121">В окне **База данных-получатель** выберите базу данных из списка или введите имя базы данных, которую нужно создать.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-121">In the **Secondary database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
6.  <span data-ttu-id="7fbf4-122">На вкладке **Инициализация базы данных-получателя** выберите параметр, который нужно использовать для инициализации базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-122">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
7.  <span data-ttu-id="7fbf4-123">На вкладке **Копирование файлов**введите в поле **Папка назначения для копирования файлов** путь к папке, в которую следует скопировать резервные копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-123">On the **Copy Files tab**, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="7fbf4-124">Эта папка часто находится на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-124">This folder is often located on the secondary server.</span></span>  
  
8.  <span data-ttu-id="7fbf4-125">Обратите внимание на расписание копирования в поле **Расписание** в разделе **Задание копирования**.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="7fbf4-126">Если необходимо изменить расписание, нажмите кнопку **Расписание** и задайте расписание для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-126">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="7fbf4-127">Это расписание должно быть максимально приближено к расписанию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-127">This schedule should approximate the backup schedule.</span></span>  
  
9. <span data-ttu-id="7fbf4-128">На вкладке **Восстановление журнала транзакций** в разделе **Состояние базы данных во время восстановления резервных копий**выберите пункт **Без режима восстановления** или **Режим ожидания** .</span><span class="sxs-lookup"><span data-stu-id="7fbf4-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
10. <span data-ttu-id="7fbf4-129">Если выбран параметр **Режим ожидания** , то нужно указать, следует ли отключать пользователей от базы данных-получателя, пока идет процесс восстановления.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-129">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
11. <span data-ttu-id="7fbf4-130">Если нужно отложить процесс восстановления на сервере-получателе, укажите время задержки в поле **Отложить восстановление резервных копий по крайней мере на**.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-130">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
12. <span data-ttu-id="7fbf4-131">Выберите пороговое значение для предупреждения в поле **Предупреждение, если восстановление не выполнено в течение**.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
13. <span data-ttu-id="7fbf4-132">Обратите внимание на расписание восстановления в поле **Расписание** раздела **Задание восстановления**.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-132">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="7fbf4-133">Если необходимо изменить расписание, нажмите кнопку **Расписание** и задайте расписание для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-133">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="7fbf4-134">Это расписание должно быть максимально приближено к расписанию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-134">This schedule should approximate the backup schedule.</span></span>  
  
14. <span data-ttu-id="7fbf4-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-135">Click **OK**.</span></span>  
  
15. <span data-ttu-id="7fbf4-136">Чтобы начать процесс настройки, нажмите в диалоговом окне «Свойства базы данных» кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="7fbf4-136">Click **OK** on the Database Properties dialog box to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7fbf4-137">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7fbf4-137">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="7fbf4-138">Добавление базы данных-получателя доставки журналов</span><span class="sxs-lookup"><span data-stu-id="7fbf4-138">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="7fbf4-139">На сервере-получателе выполните процедуру [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) для обеспечения подробных характеристик сервера-источника и базы данных.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-139">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="7fbf4-140">Данная хранимая процедура возвращает идентификатор получателя, а также идентификаторы заданий копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-140">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
2.  <span data-ttu-id="7fbf4-141">На сервере-получателе выполните процедуру [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) для настройки расписания заданий копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-141">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="7fbf4-142">На сервере-получателе выполните процедуру [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) для добавления базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-142">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
4.  <span data-ttu-id="7fbf4-143">На сервере-источнике выполните процедуру [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) для добавления на сервер-источник необходимых сведений о новой базе данных-получателе.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-143">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
5.  <span data-ttu-id="7fbf4-144">На сервере-получателе включите задания копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="7fbf4-144">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="7fbf4-145">Дополнительные сведения см. в статье [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="7fbf4-145">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7fbf4-146">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7fbf4-146">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7fbf4-147">Обновление доставки журналов до SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7fbf4-147">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="7fbf4-148">Настройка доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7fbf4-148">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="7fbf4-149">Удаление базы данных-получателя из конфигурации доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7fbf4-149">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="7fbf4-150">Удаление доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7fbf4-150">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="7fbf4-151">Просмотр отчета о доставке журналов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7fbf4-151">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="7fbf4-152">Наблюдение за доставкой журналов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7fbf4-152">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="7fbf4-153">Переход на вторичный сервер доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7fbf4-153">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="7fbf4-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="7fbf4-154">See Also</span></span>  
 <span data-ttu-id="7fbf4-155">[Сведения о доставке журналов (SQL Server)](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7fbf4-155">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="7fbf4-156">Таблицы доставки журналов и хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="7fbf4-156">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
