---
title: Настройка доставки журналов (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], enabling
- log shipping [SQL Server], configuring
ms.assetid: c42aa04a-4945-4417-b4c7-50589d727e9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269b0ae2980435e507128cc87606f7eb702c2b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729746"
---
# <a name="configure-log-shipping-sql-server"></a><span data-ttu-id="23c17-102">Настройка доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23c17-102">Configure Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="23c17-103">В данном разделе описывается настройка доставки журналов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23c17-103">This topic describes how to configure log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="23c17-104">и более поздние версии поддерживают сжатие резервных копий.</span><span class="sxs-lookup"><span data-stu-id="23c17-104">and later versions support backup compression.</span></span> <span data-ttu-id="23c17-105">При создании конфигурации доставки журналов можно управлять поведением сжатия резервных копий журналов.</span><span class="sxs-lookup"><span data-stu-id="23c17-105">When creating a log shipping configuration, you can control the backup compression behavior of log backups.</span></span> <span data-ttu-id="23c17-106">Дополнительные сведения см. в разделе [Сжатие резервных копий (SQL Server)](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="23c17-106">For more information, see [Backup Compression &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="23c17-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="23c17-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="23c17-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="23c17-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="23c17-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="23c17-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="23c17-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="23c17-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="23c17-111">**Настройка доставки журналов с помощью:**</span><span class="sxs-lookup"><span data-stu-id="23c17-111">**To configure log shipping, using:**</span></span>  
  
     [<span data-ttu-id="23c17-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23c17-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="23c17-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="23c17-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="23c17-114">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="23c17-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="23c17-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="23c17-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="23c17-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="23c17-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="23c17-117">База данных-источник должна использовать модель полного восстановления или восстановления с неполным протоколированием; переключение базы данных на использование модели простого восстановления приведет к прекращению доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="23c17-117">The primary database must use the full or bulk-logged recovery model; switching the database to simple recovery will cause log shipping to stop functioning.</span></span>  
  
-   <span data-ttu-id="23c17-118">Перед настройкой доставки журналов необходимо создать общую папку, чтобы сделать резервные копии журнала транзакций доступными серверу-получателю.</span><span class="sxs-lookup"><span data-stu-id="23c17-118">Before you configure log shipping, you must create a share to make the transaction log backups available to the secondary server.</span></span> <span data-ttu-id="23c17-119">Именно в каталоге с открытым доступом будут формироваться резервные копии журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="23c17-119">This is a share of the directory where the transaction log backups will be generated.</span></span> <span data-ttu-id="23c17-120">Например, если создание резервных копий журналов транзакций производится в каталог "c:\data\tlogs\\", то для открытого доступа к этому каталогу можно создать каталог " \\\\*primaryserver*\tlogs".</span><span class="sxs-lookup"><span data-stu-id="23c17-120">For example, if you back up your transaction logs to the directory c:\data\tlogs\\, you could create the \\\\*primaryserver*\tlogs share of that directory.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="23c17-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="23c17-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="23c17-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="23c17-122">Permissions</span></span>  
 <span data-ttu-id="23c17-123">Для вызова хранимых процедур доставки журналов необходимо членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="23c17-123">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="23c17-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23c17-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="23c17-125">Настройка доставки журналов</span><span class="sxs-lookup"><span data-stu-id="23c17-125">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="23c17-126">Щелкните правой кнопкой мыши имя базы данных, которая станет базой данных-источником в конфигурации доставки журналов, затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="23c17-126">Right click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="23c17-127">В области **Выбор страницы**щелкните **Доставка журналов транзакций**.</span><span class="sxs-lookup"><span data-stu-id="23c17-127">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="23c17-128">Установите флажок **Включить эту базу данных в качестве источника в конфигурацию доставки журналов** .</span><span class="sxs-lookup"><span data-stu-id="23c17-128">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
4.  <span data-ttu-id="23c17-129">В разделе **Резервные копии журналов транзакций**нажмите кнопку **Параметры копирования**.</span><span class="sxs-lookup"><span data-stu-id="23c17-129">Under **Transaction log backups**, click **Backup Settings**.</span></span>  
  
5.  <span data-ttu-id="23c17-130">В поле **Сетевой путь к папке резервного копирования** введите сетевой путь к общему ресурсу, который создан для папки резервного копирования журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="23c17-130">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>  
  
6.  <span data-ttu-id="23c17-131">Если папка резервного копирования расположена на сервере-источнике, введите локальный путь к папке резервного копирования в поле **Если папка резервного копирования находится на сервере-источнике, укажите локальный путь к папке** .</span><span class="sxs-lookup"><span data-stu-id="23c17-131">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="23c17-132">(Если папка резервного копирования находится не на сервере-источнике, можно оставить это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="23c17-132">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="23c17-133">Если учетная запись служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на сервере-источнике выполняется с правами учетной записи «Локальная система», надо создать папку резервного копирования на сервере-источнике и указать локальный путь к ней.</span><span class="sxs-lookup"><span data-stu-id="23c17-133">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>  
  
7.  <span data-ttu-id="23c17-134">Настройте параметры **Удалить файлы, созданные ранее** и **Предупредить, если резервное копирование не произошло в течение** .</span><span class="sxs-lookup"><span data-stu-id="23c17-134">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>  
  
8.  <span data-ttu-id="23c17-135">Обратите внимание на расписание в поле **Расписание** в разделе **Задание резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="23c17-135">Note the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="23c17-136">Если нужно изменить расписание, нажмите кнопку **Расписание** и задайте расписание для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="23c17-136">If you want to customize the schedule for your installation, then click **Schedule** and adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span>  
  
9. [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="23c17-137">поддерживает [сжатие резервных копий](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="23c17-137">supports [backup compression](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span> <span data-ttu-id="23c17-138">При создании конфигурации доставки журналов можно управлять поведением сжатия резервных копий журналов, выбрав один из следующих параметров. **Использовать параметр сервера по умолчанию**, **Сжимать резервные копии** и **Не сжимать резервные копии**.</span><span class="sxs-lookup"><span data-stu-id="23c17-138">When creating a log shipping configuration, you can control the backup compression behavior of log backups by choosing one of the following options: **Use the default server setting**, **Compress backup**, or **Do not compress backup**.</span></span> <span data-ttu-id="23c17-139">Дополнительные сведения см. в статье [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span><span class="sxs-lookup"><span data-stu-id="23c17-139">For more information, see [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span></span>  
  
10. <span data-ttu-id="23c17-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23c17-140">Click **OK**.</span></span>  
  
11. <span data-ttu-id="23c17-141">В разделе **Экземпляры сервера-получателя и базы данных**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="23c17-141">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
12. <span data-ttu-id="23c17-142">Нажмите **Соединить** и соединитесь с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который нужно использовать в качестве сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="23c17-142">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
13. <span data-ttu-id="23c17-143">В поле **База данных-получатель** выберите базу данных из списка или введите имя базы данных, которую нужно создать.</span><span class="sxs-lookup"><span data-stu-id="23c17-143">In the **Secondary Database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
14. <span data-ttu-id="23c17-144">На вкладке **Инициализация базы данных-получателя** выберите параметр, который нужно использовать для инициализации базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="23c17-144">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23c17-145">Если выбрана инициализация базы данных-получателя из резервной копии базы данных с помощью среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , то данные и файлы журналов базы данных-получателя будут находиться в том же расположении, что данные и файлы журналов базы данных **master** .</span><span class="sxs-lookup"><span data-stu-id="23c17-145">If you choose to have [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] initialize the secondary database from a database backup, the data and log files of the secondary database are placed in the same location as the data and log files of the **master** database.</span></span> <span data-ttu-id="23c17-146">Это расположение, вероятно, будет отличаться от расположения файлов данных и файлов журнала базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="23c17-146">This location is likely to be different than the location of the data and log files of the primary database.</span></span>  
  
15. <span data-ttu-id="23c17-147">На вкладке **Копирование файлов** в поле **Папка назначения для копирования файлов** введите путь папки, в которую должны копироваться резервные копии журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="23c17-147">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="23c17-148">Эта папка часто находится на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="23c17-148">This folder is often located on the secondary server.</span></span>  
  
16. <span data-ttu-id="23c17-149">Обратите внимание на расписание копирования в поле **Расписание** в разделе **Задание копирования**.</span><span class="sxs-lookup"><span data-stu-id="23c17-149">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="23c17-150">Если необходимо изменить расписание, нажмите кнопку **Расписание** и задайте расписание для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="23c17-150">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="23c17-151">Это расписание должно быть максимально приближено к расписанию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="23c17-151">This schedule should approximate the backup schedule.</span></span>  
  
17. <span data-ttu-id="23c17-152">На вкладке **Восстановление журнала транзакций** в разделе **Состояние базы данных во время восстановления резервных копий**выберите пункт **Без режима восстановления** или **Режим ожидания** .</span><span class="sxs-lookup"><span data-stu-id="23c17-152">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
18. <span data-ttu-id="23c17-153">Если выбран параметр **Режим ожидания** , то нужно указать, следует ли отключать пользователей от базы данных-получателя, пока идет процесс восстановления.</span><span class="sxs-lookup"><span data-stu-id="23c17-153">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
19. <span data-ttu-id="23c17-154">Если нужно отложить процесс восстановления на сервере-получателе, укажите время задержки в поле **Отложить восстановление резервных копий по крайней мере на**.</span><span class="sxs-lookup"><span data-stu-id="23c17-154">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
20. <span data-ttu-id="23c17-155">Выберите пороговое значение для предупреждения в поле **Предупреждение, если восстановление не выполнено в течение**.</span><span class="sxs-lookup"><span data-stu-id="23c17-155">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
21. <span data-ttu-id="23c17-156">Обратите внимание на расписание восстановления в поле **Расписание** раздела **Задание восстановления**.</span><span class="sxs-lookup"><span data-stu-id="23c17-156">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="23c17-157">Если необходимо изменить расписание, нажмите кнопку **Расписание** и задайте расписание для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="23c17-157">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="23c17-158">Это расписание должно быть максимально приближено к расписанию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="23c17-158">This schedule should approximate the backup schedule.</span></span>  
  
22. <span data-ttu-id="23c17-159">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23c17-159">Click **OK**.</span></span>  
  
23. <span data-ttu-id="23c17-160">В разделе **Экземпляр сервера мониторинга**выберите флажок **Использовать экземпляр сервера мониторинга** и затем нажмите кнопку **Настройки**.</span><span class="sxs-lookup"><span data-stu-id="23c17-160">Under **Monitor server instance**, select the **Use a monitor server instance** check box, and then click **Settings**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="23c17-161">Для отслеживания данной конфигурации доставки журналов необходимо добавить сервер мониторинга сейчас.</span><span class="sxs-lookup"><span data-stu-id="23c17-161">To monitor this log shipping configuration, you must add the monitor server now.</span></span> <span data-ttu-id="23c17-162">Чтобы добавить сервер мониторинга позже, потребуется удалить данную конфигурацию доставки журналов, а затем заменить ее новой конфигурацией, включающей сервер мониторинга.</span><span class="sxs-lookup"><span data-stu-id="23c17-162">To add the monitor server later, you would need to remove this log shipping configuration and then replace it with a new configuration that includes a monitor server.</span></span>  
  
24. <span data-ttu-id="23c17-163">Нажмите кнопку **Соединить** и соединитесь с экземпляром компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который нужно использовать в качестве сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="23c17-163">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your monitor server.</span></span>  
  
25. <span data-ttu-id="23c17-164">В разделе **Соединения с сервером мониторинга**выберите метод подключения, который используется заданиями резервного копирования, обычного копирования и восстановления для соединения с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="23c17-164">Under **Monitor connections**, choose the connection method to be used by the backup, copy, and restore jobs to connect to the monitor server.</span></span>  
  
26. <span data-ttu-id="23c17-165">В разделе **Хранение журнала**выберите отрезок времени, в течение которого нужно хранить записи об отправке журналов.</span><span class="sxs-lookup"><span data-stu-id="23c17-165">Under **History retention**, choose the length of time you want to retain a record of your log shipping history.</span></span>  
  
27. <span data-ttu-id="23c17-166">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23c17-166">Click **OK**.</span></span>  
  
28. <span data-ttu-id="23c17-167">В диалоговом окне **Свойства базы данных** нажмите кнопку **ОК** , чтобы начать процесс настройки.</span><span class="sxs-lookup"><span data-stu-id="23c17-167">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="23c17-168">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="23c17-168">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="23c17-169">Настройка доставки журналов</span><span class="sxs-lookup"><span data-stu-id="23c17-169">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="23c17-170">Инициализируйте базу данных-получатель путем восстановления полной резервной копии базы данных-источника на сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="23c17-170">Initialize the secondary database by restoring a full backup of the primary database on the secondary server.</span></span>  
  
2.  <span data-ttu-id="23c17-171">Для добавления базы данных-источника на сервер-источник выполните процедуру [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="23c17-171">On the primary server, execute [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) to add a primary database.</span></span> <span data-ttu-id="23c17-172">Хранимая процедура возвращает идентификатор задания резервирования и первичный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="23c17-172">The stored procedure returns the backup job ID and primary ID.</span></span>  
  
3.  <span data-ttu-id="23c17-173">Для установки расписания заданий копирования и восстановления выполните процедуру [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) на сервере-источнике.</span><span class="sxs-lookup"><span data-stu-id="23c17-173">On the primary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to add a schedule for the backup job.</span></span>  
  
4.  <span data-ttu-id="23c17-174">Для добавления задания предупреждения выполните процедуру [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) на сервере мониторинга.</span><span class="sxs-lookup"><span data-stu-id="23c17-174">On the monitor server, execute [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) to add the alert job.</span></span>  
  
5.  <span data-ttu-id="23c17-175">Включите задание копирования на сервере-источнике.</span><span class="sxs-lookup"><span data-stu-id="23c17-175">On the primary server, enable the backup job.</span></span>  
  
6.  <span data-ttu-id="23c17-176">На сервере-получателе выполните процедуру [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) для обеспечения подробных характеристик сервера-источника и базы данных.</span><span class="sxs-lookup"><span data-stu-id="23c17-176">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="23c17-177">Данная хранимая процедура возвращает идентификатор получателя, а также идентификаторы заданий копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="23c17-177">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
7.  <span data-ttu-id="23c17-178">На сервере-получателе выполните процедуру [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) для настройки расписания заданий копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="23c17-178">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
8.  <span data-ttu-id="23c17-179">На сервере-получателе выполните процедуру [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) для добавления базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="23c17-179">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
9. <span data-ttu-id="23c17-180">На сервере-источнике выполните процедуру [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) для добавления на сервер-источник необходимых сведений о новой базе данных-получателе.</span><span class="sxs-lookup"><span data-stu-id="23c17-180">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
10. <span data-ttu-id="23c17-181">На сервере-получателе включите задания копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="23c17-181">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="23c17-182">Дополнительные сведения см. в статье [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="23c17-182">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="23c17-183">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="23c17-183">Related Tasks</span></span>  
  
-   [<span data-ttu-id="23c17-184">Обновление доставки журналов до SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="23c17-184">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="23c17-185">Добавление базы данных-получателя в конфигурацию доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23c17-185">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="23c17-186">Удаление базы данных-получателя из конфигурации доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23c17-186">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="23c17-187">Удаление доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23c17-187">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="23c17-188">Просмотр отчета о доставке журналов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="23c17-188">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="23c17-189">Наблюдение за доставкой журналов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="23c17-189">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="23c17-190">Переход на вторичный сервер доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23c17-190">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="23c17-191">См. также:</span><span class="sxs-lookup"><span data-stu-id="23c17-191">See Also</span></span>  
 <span data-ttu-id="23c17-192">[Сведения о доставке журналов (SQL Server)](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="23c17-192">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="23c17-193">Таблицы доставки журналов и хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="23c17-193">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
