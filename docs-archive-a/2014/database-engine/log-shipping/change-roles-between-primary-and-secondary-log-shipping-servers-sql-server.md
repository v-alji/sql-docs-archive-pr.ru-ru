---
title: Обмен ролями между сервером-источником и сервером-получателем доставки журналов (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], role changes
- secondary data files [SQL Server], roles changed between
- primary databases [SQL Server]
- initial role changes [SQL Server]
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: 2d7cc40a-47e8-4419-9b2b-7c69f700e806
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 52ddb89bfd18eef4cd2140bc67cf93d1800138f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734422"
---
# <a name="change-roles-between-primary-and-secondary-log-shipping-servers-sql-server"></a><span data-ttu-id="397fe-102">Обмен ролями между сервером-источником и сервером-получателем доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="397fe-102">Change Roles Between Primary and Secondary Log Shipping Servers (SQL Server)</span></span>
  <span data-ttu-id="397fe-103">После перехода конфигурации доставки журналов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на ресурс сервера-получателя можно настроить базу данных-получатель для работы в качестве базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="397fe-103">After you have failed over a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log shipping configuration to a secondary server, you can configure your secondary database to act as the primary database.</span></span> <span data-ttu-id="397fe-104">Затем базу данных-источник и базу данных-получатель можно менять местами по необходимости.</span><span class="sxs-lookup"><span data-stu-id="397fe-104">Then, you will be able to swap primary and secondary databases as needed.</span></span>  
  
## <a name="performing-the-initial-role-change"></a><span data-ttu-id="397fe-105">Выполнение исходного изменения роли</span><span class="sxs-lookup"><span data-stu-id="397fe-105">Performing the Initial Role Change</span></span>  
 <span data-ttu-id="397fe-106">В первый раз при переключении на базу данных-получатель и назначении ее новой базой данных-источником необходимо выполнить ряд шагов.</span><span class="sxs-lookup"><span data-stu-id="397fe-106">The first time you want to fail over to the secondary database and make it your new primary database, there is a series of steps you must take.</span></span> <span data-ttu-id="397fe-107">После выполнения этих первоначальных шагов появится возможность легко менять местами базу данных-источник и базу данных-получатель.</span><span class="sxs-lookup"><span data-stu-id="397fe-107">After you have followed these initial steps, you will be able to swap roles between the primary database and the secondary database easily.</span></span>  
  
1.  <span data-ttu-id="397fe-108">Переход с базы данных-источника на базу данных-получатель вручную.</span><span class="sxs-lookup"><span data-stu-id="397fe-108">Manually fail over from the primary database to a secondary database.</span></span> <span data-ttu-id="397fe-109">Обязательно создайте резервную копию активного журнала транзакций сервера-источника с параметром NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="397fe-109">Be sure to back up the active transaction log on your primary server with NORECOVERY.</span></span> <span data-ttu-id="397fe-110">Дополнительные сведения см. в разделе [Переход на вторичный сервер доставки журналов (SQL Server)](fail-over-to-a-log-shipping-secondary-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-110">For more information, see [Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="397fe-111">Отключите задание резервного копирования в доставке журналов на исходном сервере-источнике и задания копирования и восстановления на исходном сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="397fe-111">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="397fe-112">С помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] настройте доставку журналов для базы данных-получателя (базы данных, которую хотите сделать источником).</span><span class="sxs-lookup"><span data-stu-id="397fe-112">On your secondary database (the database you want to be the new primary), configure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="397fe-113">Дополнительные сведения см. в разделе [Настройка доставки журналов (SQL Server)](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-113">For more information, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span> <span data-ttu-id="397fe-114">Выполните следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="397fe-114">Include the following steps:</span></span>  
  
    1.  <span data-ttu-id="397fe-115">Для создания резервных копий используйте ту же общую папку, которая была создана для первоначального сервера-источника.</span><span class="sxs-lookup"><span data-stu-id="397fe-115">Use the same share for creating backups that you created for the original primary server.</span></span>  
  
    2.  <span data-ttu-id="397fe-116">При добавлении базы данных-получателя в диалоговом окне **Настройки базы данных-получателя** введите имя исходной базы данных-источника в поле **База данных-получатель**</span><span class="sxs-lookup"><span data-stu-id="397fe-116">When adding the secondary database, in the **Secondary Database Settings** dialog box, enter the name of the original primary database in the **Secondary database** box.</span></span>  
  
    3.  <span data-ttu-id="397fe-117">В диалоговом окне **Настройки базы данных-получателя** выберите параметр **Нет, база данных-получатель инициализирована**.</span><span class="sxs-lookup"><span data-stu-id="397fe-117">In the **Secondary Database Settings** dialog box, select **No, the secondary database is initialized**.</span></span>  
  
4.  <span data-ttu-id="397fe-118">Если в предыдущей конфигурации доставки журналов был включен мониторинг доставки журнала, внесите изменения в настройки мониторинга доставки журнала для отслеживания новой конфигурации доставки журнала.</span><span class="sxs-lookup"><span data-stu-id="397fe-118">If log shipping monitoring was enabled on your former log shipping configuration, reconfigure log shipping monitoring to monitor the new log shipping configuration.</span></span>  <span data-ttu-id="397fe-119">Выполните следующие команды, заменив *database_name* именем вашей базы данных:</span><span class="sxs-lookup"><span data-stu-id="397fe-119">Execute the following commands, replacing *database_name* with the name of your database:</span></span>  
  
    1.  <span data-ttu-id="397fe-120">**На новом сервере-источнике**</span><span class="sxs-lookup"><span data-stu-id="397fe-120">**On the new primary server**</span></span>  
  
         <span data-ttu-id="397fe-121">Выполните следующие инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="397fe-121">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new primary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_secondary_database @secondary_database = N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
    2.  <span data-ttu-id="397fe-122">**На новом сервере-получателе**</span><span class="sxs-lookup"><span data-stu-id="397fe-122">**On the new secondary server**</span></span>  
  
         <span data-ttu-id="397fe-123">Выполните следующие инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="397fe-123">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new secondary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_primary_database @database=N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
## <a name="swapping-roles"></a><span data-ttu-id="397fe-124">Смена ролей</span><span class="sxs-lookup"><span data-stu-id="397fe-124">Swapping Roles</span></span>  
 <span data-ttu-id="397fe-125">После завершения перечисленных выше шагов для первоначальной смены ролей можно выполнить обмен ролями между базой данных-источником и базой данных-получателем, выполняя действия, приведенные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="397fe-125">After you have completed the steps above for the initial role change, you can change roles between the primary database and the secondary database by following the steps in this section.</span></span> <span data-ttu-id="397fe-126">Выполните следующие шаги для обмена ролями:</span><span class="sxs-lookup"><span data-stu-id="397fe-126">To perform a role change, follow these general steps:</span></span>  
  
1.  <span data-ttu-id="397fe-127">Переведите базу данных-получатель в режим «в сети», выполните резервное копирование журнала транзакций на сервере-источнике с параметром NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="397fe-127">Bring the secondary database online, backing up the transaction log on the primary server with NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="397fe-128">Отключите задание резервного копирования в доставке журналов на исходном сервере-источнике и задания копирования и восстановления на исходном сервере-получателе.</span><span class="sxs-lookup"><span data-stu-id="397fe-128">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="397fe-129">Включите задание резервного копирования в доставке журналов на исходном сервере-получателе (новом сервере-источнике) и задания копирования и восстановления на исходном сервере-источнике (новом сервере-получателе).</span><span class="sxs-lookup"><span data-stu-id="397fe-129">Enable the log shipping backup job on the secondary server (the new primary server), and the copy and restore jobs on the primary server (the new secondary server).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="397fe-130">Чтобы обеспечить согласованную работу пользователей и приложений при изменении базы данных-получателя на базу данных-источник, необходимо повторно создать часть или все метаданные базы данных, такие как имена входа и задания, в новом экземпляре сервера-источника.</span><span class="sxs-lookup"><span data-stu-id="397fe-130">When you change a secondary database to the primary database, to provide a consistent experience to users and applications, you might have to re-create some or all of the metadata for the database, such as logins and jobs, on the new primary server instance.</span></span> <span data-ttu-id="397fe-131">Дополнительные сведения см. в статье [Управление метаданными при обеспечении доступности базы данных на другом экземпляре сервера (SQL Server)](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-131">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="397fe-132">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="397fe-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="397fe-133">Переход на вторичный сервер доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="397fe-133">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="397fe-134">Управление именами входа и заданиями после переключения ролей (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="397fe-134">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="397fe-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="397fe-135">See Also</span></span>  
 [<span data-ttu-id="397fe-136">Таблицы доставки журналов и хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="397fe-136">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
