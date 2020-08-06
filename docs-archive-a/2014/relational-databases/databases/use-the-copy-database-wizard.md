---
title: Использование мастера копирования базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.cdw.transfermethod.f1
- sql12.swb.cdw.welcome.f1
- sql12.swb.cdw.packageconfiguration.f1
- sql12.swb.cdw.schedule.f1
- sql12.swb.cdw.destination.f1
- sql12.swb.cdw.complete.f1
- sql12.swb.cdw.destinationconfiguration.f1
- sql12.swb.cdw.selectdatabaseobjects.f1
- sql12.swb.cdw.databases.f1
- sql12.swb.cdw.source.f1
- sql12.swb.cdw.locationofsourcedbfiles.f1
helpviewer_keywords:
- Copy Database Wizard
- starting Copy Database Wizard
ms.assetid: 7a999fc7-0a26-4a0d-9eeb-db6fc794f3cb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0baaeef6cb196a67b2f615aa280b61b61fbc5119
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749980"
---
# <a name="use-the-copy-database-wizard"></a><span data-ttu-id="64408-102">Использование мастера копирования базы данных</span><span class="sxs-lookup"><span data-stu-id="64408-102">Use the Copy Database Wizard</span></span>
  <span data-ttu-id="64408-103">С помощью мастера копирования баз данных можно легко перемещать или копировать базы данных и их объекты с одного сервера на другой, без перерывов в работе сервера.</span><span class="sxs-lookup"><span data-stu-id="64408-103">The Copy Database Wizard lets you move or copy databases and their objects easily from one server to another, with no server downtime.</span></span> <span data-ttu-id="64408-104">Можно также обновить базы данных с прошлой версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] до версии [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64408-104">You can also upgrade databases from a previous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="64408-105">С помощью этого мастера можно сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="64408-105">By using this wizard, you can do the following:</span></span>  
  
-   <span data-ttu-id="64408-106">Выбрать исходный и целевой серверы.</span><span class="sxs-lookup"><span data-stu-id="64408-106">Pick a source and destination server.</span></span>  
  
-   <span data-ttu-id="64408-107">Выбрать базы данных для перемещения, копирования или обновления.</span><span class="sxs-lookup"><span data-stu-id="64408-107">Select databases to move, copy or upgrade.</span></span>  
  
-   <span data-ttu-id="64408-108">Указать расположение файлов для баз данных.</span><span class="sxs-lookup"><span data-stu-id="64408-108">Specify the file location for the databases.</span></span>  
  
-   <span data-ttu-id="64408-109">Создать имена входа для целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="64408-109">Create logins on the destination server.</span></span>  
  
-   <span data-ttu-id="64408-110">Копировать дополнительные вспомогательные объекты, задания, пользовательские хранимые процедуры и сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="64408-110">Copy additional supporting objects, jobs, user-defined stored procedures, and error messages.</span></span>  
  
-   <span data-ttu-id="64408-111">Задать расписание перемещения или копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="64408-111">Schedule when to move or copy the databases.</span></span>  
  
 <span data-ttu-id="64408-112">При копировании базы данных можно также выполнить копирование связанных метаданных, например имен входа и объектов из базы данных **master** , необходимых для ее работы.</span><span class="sxs-lookup"><span data-stu-id="64408-112">In addition to copying databases, you can copy associated metadata, for example, logins and objects from the **master** database that are required by a copied database.</span></span>  
  
 <span data-ttu-id="64408-113">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="64408-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="64408-114">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="64408-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="64408-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="64408-115">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="64408-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="64408-116">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="64408-117">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="64408-117">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="64408-118">Безопасность</span><span class="sxs-lookup"><span data-stu-id="64408-118">Security</span></span>](#Security)  
  
-   <span data-ttu-id="64408-119">**Использование мастера копирования баз данных для:**</span><span class="sxs-lookup"><span data-stu-id="64408-119">**Using the Copy Database Wizard to:**</span></span>  
  
     [<span data-ttu-id="64408-120">Копирование, перемещение или обновление баз данных</span><span class="sxs-lookup"><span data-stu-id="64408-120">Copy, Move, or Upgrade Databases</span></span>](#Copy_Move)  
  
-   <span data-ttu-id="64408-121">**Проверки после обновления.**</span><span class="sxs-lookup"><span data-stu-id="64408-121">**Follow up, after upgrade:**</span></span>  
  
     [<span data-ttu-id="64408-122">После обновления базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="64408-122">After Upgrading a SQL Server Database</span></span>](#FollowUp)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="64408-123">Перед началом</span><span class="sxs-lookup"><span data-stu-id="64408-123">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="64408-124">Ограничения</span><span class="sxs-lookup"><span data-stu-id="64408-124">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="64408-125">Мастер копирования баз данных недоступен в выпуске Express.</span><span class="sxs-lookup"><span data-stu-id="64408-125">The Copy Database Wizard is not available in the Express edition.</span></span>  
  
-   <span data-ttu-id="64408-126">Мастер копирования базы данных нельзя использовать для перемещения или копирования следующих типов баз данных.</span><span class="sxs-lookup"><span data-stu-id="64408-126">The Copy Database Wizard cannot be used to copy or move the following databases.</span></span>  
  
    -   <span data-ttu-id="64408-127">Системные базы данных</span><span class="sxs-lookup"><span data-stu-id="64408-127">System databases</span></span>  
  
    -   <span data-ttu-id="64408-128">Базы данных, отмеченные для репликации.</span><span class="sxs-lookup"><span data-stu-id="64408-128">Databases marked for replication.</span></span>  
  
    -   <span data-ttu-id="64408-129">Базы данных в следующих состояниях: недоступные, в процессе загрузки, в режиме вне сети, в процессе восстановления, подозрительные или в аварийном режиме.</span><span class="sxs-lookup"><span data-stu-id="64408-129">Databases marked Inaccessible, Loading, Offline, Recovering, Suspect, or in Emergency Mode.</span></span>  
  
-   <span data-ttu-id="64408-130">После обновления базы данных возврат к предыдущей версии невозможен.</span><span class="sxs-lookup"><span data-stu-id="64408-130">After a database has been upgraded, it cannot be downgraded to a previous version.</span></span>  
  
-   <span data-ttu-id="64408-131">Если выбран параметр **Переместить** , после перемещения базы данных мастер автоматически удаляет базу данных-источник.</span><span class="sxs-lookup"><span data-stu-id="64408-131">If you select the **Move** option, the wizard deletes the source database automatically after moving the database.</span></span> <span data-ttu-id="64408-132">При выборе параметра **Копирование** мастер копирования базы данных не выполняет удаление базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="64408-132">The Copy Database Wizard does not delete a source database if you select the **Copy** option.</span></span>  
  
-   <span data-ttu-id="64408-133">При использовании метода управляющих объектов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для перемещения полнотекстового каталога после перемещения необходимо заново заполнить индекс.</span><span class="sxs-lookup"><span data-stu-id="64408-133">If you use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object method to move the full-text catalog, you must repopulate the index after the move.</span></span>  
  
-   <span data-ttu-id="64408-134">Метод отсоединения и присоединения отсоединяет базу данных, перемещает или копирует ее файлы (MDF, NDF и LDF) и подсоединяет базу данных в новом расположении.</span><span class="sxs-lookup"><span data-stu-id="64408-134">The detach-and-attach method detaches the database, moves or copies the database .mdf, .ndf, .ldf files and reattaches the database in the new location.</span></span> <span data-ttu-id="64408-135">При использовании этого метода во избежание потери или рассогласования данных к копируемой или перемещаемой базе данных нельзя присоединять активные сеансы.</span><span class="sxs-lookup"><span data-stu-id="64408-135">For the detach-and-attach method, to avoid data loss or inconsistency, active sessions cannot be attached to the database being moved or copied.</span></span> <span data-ttu-id="64408-136">При наличии каких-либо активных сеансов мастер копирования баз данных не выполняет операцию перемещения или копирования.</span><span class="sxs-lookup"><span data-stu-id="64408-136">If any active sessions exist, the Copy Database Wizard does not execute the move or copy operation.</span></span> <span data-ttu-id="64408-137">Если используется метод управляющих объектов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , активные сеансы допустимы, так как база данных не переводится в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="64408-137">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object method, active sessions are allowed because the database is never taken offline.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="64408-138">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="64408-138">Prerequisites</span></span>  
 <span data-ttu-id="64408-139">На сервере назначения должен быть запущен агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="64408-139">Ensure that SQL Server Agent is started on the destination server.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="64408-140">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="64408-140">Recommendations</span></span>  
  
-   <span data-ttu-id="64408-141">Для обеспечения оптимальной производительности обновленной базы данных выполните процедуру sp_updatestats (обновление статистики) для обновленной базы данных.</span><span class="sxs-lookup"><span data-stu-id="64408-141">To ensure optimal performance of an upgraded database, run sp_updatestats (update statistics) against the upgraded database.</span></span>  
  
-   <span data-ttu-id="64408-142">При копировании базы данных на другой экземпляр сервера, чтобы обеспечить однородность среды, возможно, на другом экземпляре сервера придется повторно создать некоторые (или даже все) метаданные базы данных: имена входа, задания и т. д.</span><span class="sxs-lookup"><span data-stu-id="64408-142">When you copy a database to another server instance, to provide a consistent experience to users and applications, you might have to re-create some or all of the metadata for the database, such as logins and jobs, on the other server instance.</span></span> <span data-ttu-id="64408-143">Дополнительные сведения см. в статье [Управление метаданными при обеспечении доступности базы данных на другом экземпляре сервера (SQL Server)](manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="64408-143">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="64408-144">безопасность</span><span class="sxs-lookup"><span data-stu-id="64408-144">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="64408-145">Permissions</span><span class="sxs-lookup"><span data-stu-id="64408-145">Permissions</span></span>  
 <span data-ttu-id="64408-146">Вы должны быть членом предопределенной роли сервера **sysadmin** как на исходном, так и на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="64408-146">You must be a member of the **sysadmin** fixed server role on both the source and destination servers.</span></span>  
  
##  <a name="copy-move-or-upgrade-databases"></a><a name="Copy_Move"></a><span data-ttu-id="64408-147">Копирование, перемещение или обновление баз данных</span><span class="sxs-lookup"><span data-stu-id="64408-147">Copy, Move or Upgrade Databases</span></span>  
  
1.  <span data-ttu-id="64408-148">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] обозревателе объектов разверните узел **базы данных**, щелкните правой кнопкой мыши базу данных, укажите пункт **задачи**и выберите команду **Копировать базу данных**.</span><span class="sxs-lookup"><span data-stu-id="64408-148">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], in Object Explorer, expand **Databases**, right-click a database, point to **Tasks**, and then click **Copy Database**.</span></span>  
  
2.  <span data-ttu-id="64408-149">На странице **Выбор исходного сервера** укажите сервер с базой данных, которую следует переместить или скопировать, а также введите сведения для входа.</span><span class="sxs-lookup"><span data-stu-id="64408-149">From the **Select a Source Server** page, specify the server with the database to move or copy, and to enter login information.</span></span> <span data-ttu-id="64408-150">После выбора метода проверки подлинности и введения сведений для входа нажмите кнопку **Далее** , чтобы установить соединения с исходным сервером.</span><span class="sxs-lookup"><span data-stu-id="64408-150">After you select the authentication method and enter login information, click **Next** to establish the connection to the source server.</span></span> <span data-ttu-id="64408-151">Это соединение остается открытым в течение всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="64408-151">This connection remains open throughout the session.</span></span>  
  
     <span data-ttu-id="64408-152">**Исходный сервер**</span><span class="sxs-lookup"><span data-stu-id="64408-152">**Source server**</span></span>  
     <span data-ttu-id="64408-153">Выберите имя сервера, на котором находятся базы данных, которые необходимо переместить или скопировать, или нажмите кнопку обзора (**...**), чтобы найти нужный сервер.</span><span class="sxs-lookup"><span data-stu-id="64408-153">Select the name of the server on which the database or databases you want to move or copy are located, or click the browse (**...**) button to locate the server you want.</span></span> <span data-ttu-id="64408-154">Версия сервера должна быть не ниже [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64408-154">The server must be at least [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="64408-155">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="64408-155">**Use Windows Authentication**</span></span>  
     <span data-ttu-id="64408-156">Пользователь может подключаться через учетную запись [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="64408-156">Allow a user to connect through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
     <span data-ttu-id="64408-157">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="64408-157">**Use SQL Server Authentication**</span></span>  
     <span data-ttu-id="64408-158">Позволяет пользователю подключаться с помощью имени пользователя и пароля для проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64408-158">Allow a user to connect by providing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication user name and password.</span></span>  
  
     <span data-ttu-id="64408-159">**User name**</span><span class="sxs-lookup"><span data-stu-id="64408-159">**User name**</span></span>  
     <span data-ttu-id="64408-160">Введите имя пользователя для соединения.</span><span class="sxs-lookup"><span data-stu-id="64408-160">Enter the user name to connect with.</span></span> <span data-ttu-id="64408-161">Этот параметр доступен только в том случае, если выбрано соединение с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64408-161">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication .</span></span>  
  
     <span data-ttu-id="64408-162">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="64408-162">**Password**</span></span>  
     <span data-ttu-id="64408-163">Введите пароль для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="64408-163">Enter the password for the login.</span></span> <span data-ttu-id="64408-164">Этот параметр доступен только в том случае, если выбрано соединение с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64408-164">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
     <span data-ttu-id="64408-165">**Вперед**</span><span class="sxs-lookup"><span data-stu-id="64408-165">**Next**</span></span>  
     <span data-ttu-id="64408-166">Соединение с сервером и проверка пользователя.</span><span class="sxs-lookup"><span data-stu-id="64408-166">Connect to the server and validate the user.</span></span> <span data-ttu-id="64408-167">Этот процесс проверяет членство пользователя в фиксированной роли сервера **sysadmin** на выбранном компьютере.</span><span class="sxs-lookup"><span data-stu-id="64408-167">This process checks whether the user is a member of the **sysadmin** fixed server role on the selected computer.</span></span>  
  
3.  <span data-ttu-id="64408-168">На странице **Выбор сервера назначения** укажите сервер, на который будет выполнено копирование или перемещение базы данных.</span><span class="sxs-lookup"><span data-stu-id="64408-168">From the **Select a Destination Server** page, specify the server where the database will be moved or copied.</span></span> <span data-ttu-id="64408-169">Если в качестве исходного и целевого сервера выбрать один и тот же экземпляр сервера, будет создана копия базы данных.</span><span class="sxs-lookup"><span data-stu-id="64408-169">If you set the source and destination servers to the same server instance, you will make a copy of a database.</span></span> <span data-ttu-id="64408-170">В этом случае необходимо задать другое имя для целевой базы данных в мастере.</span><span class="sxs-lookup"><span data-stu-id="64408-170">In this case you must rename the database at a later point in the wizard.</span></span> <span data-ttu-id="64408-171">Имя базы данных-источника может быть использовано в качестве имени скопированной или перемещенной базы данных только в том случае, если на целевом сервере не возникает конфликтов имен.</span><span class="sxs-lookup"><span data-stu-id="64408-171">The source database name can be used for the copied or moved database only if name conflicts do not exist on the destination server.</span></span> <span data-ttu-id="64408-172">Если конфликты имен существуют, их необходимо разрешить вручную на целевом сервере, прежде чем там можно будет использовать имя базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="64408-172">If name conflicts exist, you must resolve them manually on the destination server before you can use the source database name there.</span></span>  
  
     <span data-ttu-id="64408-173">**Целевой сервер**</span><span class="sxs-lookup"><span data-stu-id="64408-173">**Destination server**</span></span>  
     <span data-ttu-id="64408-174">Выберите имя сервера, на который будут перемещены или скопированы база данных или базы. либо нажмите кнопку обзора (**...**), чтобы найти целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="64408-174">Select the name of the server to which the database or databases will be moved or copied, or click the browse (**...**) button to locate a destination server.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="64408-175">В качестве целевого можно использовать кластеризованный сервер, при этом мастер копирования базы данных должен убедиться, что на кластеризованном целевом сервере выбраны только совместно используемые диски.</span><span class="sxs-lookup"><span data-stu-id="64408-175">You can use a destination that is a clustered server; the Copy Database Wizard will make sure you select only shared drives on a clustered destination server.</span></span>  
  
     <span data-ttu-id="64408-176">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="64408-176">**Use Windows Authentication**</span></span>  
     <span data-ttu-id="64408-177">Пользователь может подключаться через учетную запись [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="64408-177">Allow a user to connect through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
     <span data-ttu-id="64408-178">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="64408-178">**Use SQL Server Authentication**</span></span>  
     <span data-ttu-id="64408-179">Позволяет пользователю подключаться с помощью имени пользователя и пароля для проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64408-179">Allow a user to connect by providing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication user name and password.</span></span>  
  
     <span data-ttu-id="64408-180">**User name**</span><span class="sxs-lookup"><span data-stu-id="64408-180">**User name**</span></span>  
     <span data-ttu-id="64408-181">Введите имя пользователя для соединения.</span><span class="sxs-lookup"><span data-stu-id="64408-181">Enter the user name to connect with.</span></span> <span data-ttu-id="64408-182">Данный параметр доступен только при выборе проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64408-182">This option is only available if you have selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
     <span data-ttu-id="64408-183">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="64408-183">**Password**</span></span>  
     <span data-ttu-id="64408-184">Введите пароль для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="64408-184">Enter the password for the login.</span></span> <span data-ttu-id="64408-185">Данный параметр доступен только при выборе проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64408-185">This option is only available if you have selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
     <span data-ttu-id="64408-186">**Вперед**</span><span class="sxs-lookup"><span data-stu-id="64408-186">**Next**</span></span>  
     <span data-ttu-id="64408-187">Соединение с сервером и проверка пользователя.</span><span class="sxs-lookup"><span data-stu-id="64408-187">Connect to the server and validate the user.</span></span> <span data-ttu-id="64408-188">Во время этого процесса выполняется проверка перечисленных выше разрешений пользователя на выбранном компьютере.</span><span class="sxs-lookup"><span data-stu-id="64408-188">This process checks whether the user has the permissions listed above on the selected computers.</span></span>  
  
4.  <span data-ttu-id="64408-189">На странице **Выбор метода переноса** выберите метод переноса.</span><span class="sxs-lookup"><span data-stu-id="64408-189">From the **Select a Transfer Method** page, select the transfer method.</span></span>  
  
     <span data-ttu-id="64408-190">**Использовать метод отсоединения и присоединения**</span><span class="sxs-lookup"><span data-stu-id="64408-190">**Use the detach and attach method**</span></span>  
     <span data-ttu-id="64408-191">Отключите базу данных от сервера-источника, скопируйте файлы базы данных (MDF-, NDF- и LDF-файлы) на целевой сервер и подключите базу данных на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="64408-191">Detach the database from the source server, copy the database files (.mdf, .ndf, and .ldf) to the destination server, and attach the database at the destination server.</span></span> <span data-ttu-id="64408-192">Обычно это самый быстрый метод, так как основной выполняемой работой является считывание данных с диска источника и запись на целевой диск.</span><span class="sxs-lookup"><span data-stu-id="64408-192">This method is usually the faster method because the principal work is reading the source disk and writing the destination disk.</span></span> <span data-ttu-id="64408-193">Для создания объектов в базе данных или структур хранилищ данных не требуется логика [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64408-193">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logic is required to create objects within the database, or create data storage structures.</span></span> <span data-ttu-id="64408-194">Однако этот метод может быть более медленным, если база данных содержит большой объем выделенного, но неиспользуемого пространства.</span><span class="sxs-lookup"><span data-stu-id="64408-194">This method can be slower, however, if the database contains a large amount of allocated but unused space.</span></span> <span data-ttu-id="64408-195">Если экземпляр содержит новую и практически пустую базу данных, под которую при создании было выделено 100 МБ, все эти 100 МБ будут скопированы, даже если заполнено всего 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="64408-195">For instance, a new and practically empty database that is created allocating 100 MB, copies the entire 100 MB, even if only 5 MB is full.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="64408-196">Во время передачи данных этим методом база данных недоступна пользователям.</span><span class="sxs-lookup"><span data-stu-id="64408-196">This method makes the database unavailable to users during the transfer.</span></span>  
  
     <span data-ttu-id="64408-197">**В случае ошибки восстановить подключение базы данных-источника**</span><span class="sxs-lookup"><span data-stu-id="64408-197">**If a failure occurs, reattach the source database**</span></span>  
     <span data-ttu-id="64408-198">При копировании базы данных файлы исходной базы данных всегда повторно присоединяются к исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="64408-198">When a database is copied, the original database files are always reattached to the source server.</span></span> <span data-ttu-id="64408-199">Установите этот флажок, чтобы заново присоединить исходные файлы к базе данных-источнику, если перемещение базы данных не может быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="64408-199">Use this box to reattach original files to the source database if a database move cannot be completed.</span></span>  
  
     <span data-ttu-id="64408-200">**Использовать метод объектов SMO**</span><span class="sxs-lookup"><span data-stu-id="64408-200">**Use the SQL Management Object method**</span></span>  
     <span data-ttu-id="64408-201">Этот метод выполняет чтение определения каждого объекта базы данных-источника и создание каждого из этих объектов в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="64408-201">This method reads the definition of each database object on the source database and creates each object in the destination database.</span></span> <span data-ttu-id="64408-202">После этого происходит перенос данных из исходных таблиц в целевые таблицы с воссозданием индексов и метаданных.</span><span class="sxs-lookup"><span data-stu-id="64408-202">Then it transfers the data from the source tables to the destination tables, recreating indexes and metadata.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="64408-203">Во время переноса пользователи базы данных могут продолжать обращаться к ней.</span><span class="sxs-lookup"><span data-stu-id="64408-203">Database users can continue to access the database during the transfer.</span></span>  
  
5.  <span data-ttu-id="64408-204">На странице **Выбор базы данных** выберите одну или несколько баз данных, которые требуется переместить или скопировать с исходного сервера на целевой.</span><span class="sxs-lookup"><span data-stu-id="64408-204">From the **Select Database** page, select the database or databases you want to move or copy from the source server to the destination server.</span></span> <span data-ttu-id="64408-205">Ознакомьтесь с [ограничениями](#Restrictions) в разделе "перед тем, как вы Begin в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="64408-205">See [Limitations and Restrictions](#Restrictions) in the 'Before You Begin' section of this topic.</span></span>  
  
     <span data-ttu-id="64408-206">**Перемещение**</span><span class="sxs-lookup"><span data-stu-id="64408-206">**Move**</span></span>  
     <span data-ttu-id="64408-207">Переместить базы данных на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="64408-207">Move the database to the destination server.</span></span>  
  
     <span data-ttu-id="64408-208">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="64408-208">**Copy**</span></span>  
     <span data-ttu-id="64408-209">Копировать базы данных на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="64408-209">Copy the database to the destination server.</span></span>  
  
     <span data-ttu-id="64408-210">**Source**</span><span class="sxs-lookup"><span data-stu-id="64408-210">**Source**</span></span>  
     <span data-ttu-id="64408-211">Показывает базы данных, присутствующие на исходном сервере.</span><span class="sxs-lookup"><span data-stu-id="64408-211">Displays the databases that exist on the source server.</span></span>  
  
     <span data-ttu-id="64408-212">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="64408-212">**Status**</span></span>  
     <span data-ttu-id="64408-213">Если база данных может быть перемещена, отображается значение **ОК** .</span><span class="sxs-lookup"><span data-stu-id="64408-213">Displays **OK** if the database can be moved.</span></span> <span data-ttu-id="64408-214">В противном случае отображается причина, по которой база данных не может быть перемещена.</span><span class="sxs-lookup"><span data-stu-id="64408-214">Otherwise displays the reason why the database cannot be moved.</span></span>  
  
     <span data-ttu-id="64408-215">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="64408-215">**Refresh**</span></span>  
     <span data-ttu-id="64408-216">Обновить список баз данных.</span><span class="sxs-lookup"><span data-stu-id="64408-216">Refresh the list of databases.</span></span>  
  
     <span data-ttu-id="64408-217">**Вперед**</span><span class="sxs-lookup"><span data-stu-id="64408-217">**Next**</span></span>  
     <span data-ttu-id="64408-218">Начать проверку и перейти на следующий экран.</span><span class="sxs-lookup"><span data-stu-id="64408-218">Start the validation process, and then move to the next screen.</span></span>  
  
6.  <span data-ttu-id="64408-219">На странице **Настройка целевой базы данных** измените, если нужно, имя базы данных и укажите местоположение и имена файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="64408-219">From the **Configure Destination Database** page, change the database name if appropriate and specify the location and names of the database files.</span></span> <span data-ttu-id="64408-220">Эта страница отображается один раз для каждой перемещаемой или копируемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="64408-220">This page appears once for each database being moved or copied.</span></span>  
  
7.  <span data-ttu-id="64408-221">На странице **Выбор объектов базы данных** выберите объекты, которые необходимо включить в операцию перемещения или копирования.</span><span class="sxs-lookup"><span data-stu-id="64408-221">From the **Select Database Objects** page, select the objects to include in the move or copy operation.</span></span> <span data-ttu-id="64408-222">Эта страница доступна только в том случае, когда в качестве исходного и целевого серверов используются разные сервера.</span><span class="sxs-lookup"><span data-stu-id="64408-222">This page is only available when the source and destination are different servers.</span></span> <span data-ttu-id="64408-223">Чтобы включить объект, выберите имя объекта в поле **Доступные связанные объекты** , затем нажмите кнопку **>>** для перемещения объекта в поле **Выбранные связанные объекты** .</span><span class="sxs-lookup"><span data-stu-id="64408-223">To include an object, click the object name in the **Available related objects** box, and then click the **>>** button to move the object to the **Selected related objects** box.</span></span> <span data-ttu-id="64408-224">Чтобы исключить объект, щелкните имя объекта в поле **Выбранные связанные объекты** , а затем нажмите кнопку, **<\<** чтобы переместить объект в поле **доступные связанные объекты** .</span><span class="sxs-lookup"><span data-stu-id="64408-224">To exclude an object, click the object name in the **Selected related objects** box, and then click the **<\<** button to move the object to the **Available related objects** box.</span></span> <span data-ttu-id="64408-225">По умолчанию переносятся все объекты всех выбранных типов.</span><span class="sxs-lookup"><span data-stu-id="64408-225">By default all objects of each selected type are transferred.</span></span> <span data-ttu-id="64408-226">Для выбора отдельных объектов любого типа нажмите кнопку с многоточием рядом с любым типом объекта в поле **Выбранные связанные объекты** .</span><span class="sxs-lookup"><span data-stu-id="64408-226">To choose individual objects of any type, click the ellipsis button next to any object type in the **Selected related objects** box.</span></span> <span data-ttu-id="64408-227">Откроется диалоговое окно, в котором можно будет выбрать отдельные объекты.</span><span class="sxs-lookup"><span data-stu-id="64408-227">This opens a dialog box where you can select individual objects.</span></span>  
  
     <span data-ttu-id="64408-228">**Имена входа (все имена входа во время выполнения)**</span><span class="sxs-lookup"><span data-stu-id="64408-228">**Logins (All logins at run time)**</span></span>  
     <span data-ttu-id="64408-229">Включает имена входа в операцию копирования или перемещения.</span><span class="sxs-lookup"><span data-stu-id="64408-229">Include logins in the move or copy operation.</span></span> <span data-ttu-id="64408-230">Выбрано по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="64408-230">Selected by default.</span></span>  
  
     <span data-ttu-id="64408-231">**Хранимые процедуры из главной базы данных**</span><span class="sxs-lookup"><span data-stu-id="64408-231">**Stored procedures from master database**</span></span>  
     <span data-ttu-id="64408-232">Включить хранимые процедуры из базы данных **master** в операцию перемещения или копирования.</span><span class="sxs-lookup"><span data-stu-id="64408-232">Include stored procedures from the **master** database in the move or copy operation.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="64408-233">Расширенные хранимые процедуры и связанные с ними DLL-файлы недоступны для автоматического копирования.</span><span class="sxs-lookup"><span data-stu-id="64408-233">Extended stored procedures and their associated DLLs are not eligible for automated copy.</span></span>  
  
     <span data-ttu-id="64408-234">**задания агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="64408-234">**SQL Server Agent jobs**</span></span>  
     <span data-ttu-id="64408-235">Включить задания из базы данных **msdb** в операцию перемещения или копирования.</span><span class="sxs-lookup"><span data-stu-id="64408-235">Include jobs from the **msdb** database in the move or copy operation.</span></span>  
  
     <span data-ttu-id="64408-236">**Определяемые пользователем сообщения об ошибках**</span><span class="sxs-lookup"><span data-stu-id="64408-236">**User-defined error messages**</span></span>  
     <span data-ttu-id="64408-237">Включает в операцию перемещения или копирования определяемые пользователем сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="64408-237">Include user-defined error messages in the move or copy operation.</span></span>  
  
     <span data-ttu-id="64408-238">**Конечные точки**</span><span class="sxs-lookup"><span data-stu-id="64408-238">**Endpoints**</span></span>  
     <span data-ttu-id="64408-239">Включить конечные точки, определенные в базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="64408-239">Include endpoints defined in the source database.</span></span>  
  
     <span data-ttu-id="64408-240">**Полнотекстовый каталог**</span><span class="sxs-lookup"><span data-stu-id="64408-240">**Full-text catalog**</span></span>  
     <span data-ttu-id="64408-241">Включает полнотекстовые каталоги из базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="64408-241">Include full-text catalogs from the source database.</span></span>  
  
     <span data-ttu-id="64408-242">**Пакет служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="64408-242">**SSIS Package**</span></span>  
     <span data-ttu-id="64408-243">Включить пакеты служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , определенные в базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="64408-243">Include [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages defined in the source database.</span></span>  
  
     <span data-ttu-id="64408-244">**Описание**</span><span class="sxs-lookup"><span data-stu-id="64408-244">**Description**</span></span>  
     <span data-ttu-id="64408-245">Описание объекта.</span><span class="sxs-lookup"><span data-stu-id="64408-245">A description of the object.</span></span>  
  
8.  <span data-ttu-id="64408-246">На странице **Местоположение файлов исходной базы данных** укажите общую папку в файловой системе, содержащую файлы базы данных на исходном сервере.</span><span class="sxs-lookup"><span data-stu-id="64408-246">From the **Location of Source Database Files** page, specify a file system share that contains the database files on the source server.</span></span> <span data-ttu-id="64408-247">Это необходимо в том случае, если экземпляры исходного и целевого серверов находятся на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="64408-247">This is required if the source and destination server instances are on different computers.</span></span>  
  
     <span data-ttu-id="64408-248">**База данных**</span><span class="sxs-lookup"><span data-stu-id="64408-248">**Database**</span></span>  
     <span data-ttu-id="64408-249">Отображает имя каждой перемещаемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="64408-249">Displays the name of each database being moved.</span></span>  
  
     <span data-ttu-id="64408-250">**Расположение папки**</span><span class="sxs-lookup"><span data-stu-id="64408-250">**Folder location**</span></span>  
     <span data-ttu-id="64408-251">Укажите местоположение файлов базы данных-источника в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="64408-251">Specify the location of the source database files on the file system.</span></span>  
  
     <span data-ttu-id="64408-252">Например: C:\Program Files\Microsoft SQL Server\MSSQL110.MSSQLSERVER\MSSQL\DATA</span><span class="sxs-lookup"><span data-stu-id="64408-252">For example: C:\Program Files\Microsoft SQL Server\MSSQL110.MSSQLSERVER\MSSQL\DATA</span></span>  
  
     <span data-ttu-id="64408-253">**Общая папка на исходном сервере**</span><span class="sxs-lookup"><span data-stu-id="64408-253">**File share on source server**</span></span>  
     <span data-ttu-id="64408-254">Укажите местоположение файлов базы данных-источника в виде пути к общей папке.</span><span class="sxs-lookup"><span data-stu-id="64408-254">Specify the location of the source database files as a path of a file share.</span></span>  
  
     <span data-ttu-id="64408-255">Например: " \\ \\ *server_name*\c $ \Program Files\Microsoft SQL Server\MSSQL110. мссклсервер\мсскл\дата</span><span class="sxs-lookup"><span data-stu-id="64408-255">For example: "\\\\*server_name*\C$\Program Files\Microsoft SQL Server\MSSQL110.MSSQLSERVER\MSSQL\Data</span></span>  
  
9. <span data-ttu-id="64408-256">Мастер копирования базы данных создает пакет служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] для передачи базы данных на странице **Настройка пакета** . Внесите изменения в пакет, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="64408-256">The Copy Database Wizard creates a [!INCLUDE[ssIS](../../includes/ssis-md.md)] package to transfer the database From the **Configure the Package** page, customize the package if appropriate.</span></span>  
  
     <span data-ttu-id="64408-257">**Размещение пакета**</span><span class="sxs-lookup"><span data-stu-id="64408-257">**Package location**</span></span>  
     <span data-ttu-id="64408-258">Указывает, куда будет записан пакет служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64408-258">Displays where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package will be written.</span></span>  
  
     <span data-ttu-id="64408-259">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="64408-259">**Package name**</span></span>  
     <span data-ttu-id="64408-260">Введите имя для пакета служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64408-260">Enter a name for the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span>  
  
     <span data-ttu-id="64408-261">**Параметры ведения журнала**</span><span class="sxs-lookup"><span data-stu-id="64408-261">**Logging options**</span></span>  
     <span data-ttu-id="64408-262">Выберите сохранение сведений либо в журнал событий Windows, либо в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="64408-262">Select whether to store the logging information in the Windows event log, or in a text file.</span></span>  
  
     <span data-ttu-id="64408-263">**Путь к журналу ошибок**</span><span class="sxs-lookup"><span data-stu-id="64408-263">**Error log file path**</span></span>  
     <span data-ttu-id="64408-264">Укажите путь размещения файла журнала.</span><span class="sxs-lookup"><span data-stu-id="64408-264">Provide a path for the location of the log file.</span></span> <span data-ttu-id="64408-265">Этот параметр доступен только в том случае, если выбрано сохранение журнала в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="64408-265">This option is only available if the text file logging option is selected.</span></span>  
  
10. <span data-ttu-id="64408-266">На странице **Расписание пакета** укажите, когда требуется начать операцию перемещения или копирования.</span><span class="sxs-lookup"><span data-stu-id="64408-266">From the **Schedule the Package** page, specify when you want the move or copy operation to start.</span></span> <span data-ttu-id="64408-267">Если вы не являетесь системным администратором, необходимо указать учетную запись-посредник агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , имеющую доступ к подсистеме выполнения пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] (SSIS).</span><span class="sxs-lookup"><span data-stu-id="64408-267">If you are not a system administrator, you must specify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Proxy account that has access to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] (SSIS) Package execution subsystem.</span></span>  
  
     <span data-ttu-id="64408-268">**Run immediately**</span><span class="sxs-lookup"><span data-stu-id="64408-268">**Run immediately**</span></span>  
     <span data-ttu-id="64408-269">Запустите операцию перемещения или копирования после нажатия кнопки **Далее**.</span><span class="sxs-lookup"><span data-stu-id="64408-269">Start the move or copy operation after you click **Next**.</span></span>  
  
     <span data-ttu-id="64408-270">**Расписание**</span><span class="sxs-lookup"><span data-stu-id="64408-270">**Schedule**</span></span>  
     <span data-ttu-id="64408-271">Начать операцию копирования или перемещения позже.</span><span class="sxs-lookup"><span data-stu-id="64408-271">Start the move or copy operation later.</span></span> <span data-ttu-id="64408-272">В окне описания появятся текущие параметры расписания.</span><span class="sxs-lookup"><span data-stu-id="64408-272">The current schedule settings appear in the description box.</span></span> <span data-ttu-id="64408-273">Чтобы изменить расписание, нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="64408-273">To change the schedule, click **Change**.</span></span>  
  
     <span data-ttu-id="64408-274">**Изменение**</span><span class="sxs-lookup"><span data-stu-id="64408-274">**Change**</span></span>  
     <span data-ttu-id="64408-275">Откройте диалоговое окно **Создание расписания задания** .</span><span class="sxs-lookup"><span data-stu-id="64408-275">Open the **New Job Schedule** dialog box.</span></span>  
  
     <span data-ttu-id="64408-276">**Учетная запись-посредник служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="64408-276">**Integration Services proxy account**</span></span>  
     <span data-ttu-id="64408-277">Выберите учетную запись-посредник.</span><span class="sxs-lookup"><span data-stu-id="64408-277">Select an available proxy account.</span></span> <span data-ttu-id="64408-278">Чтобы запланировать перемещение, пользователь должен иметь по крайней мере одну учетную запись-посредник, настроенную с разрешением доступа к подсистеме **Выполнение пакетов служб SQL Server Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="64408-278">To schedule the transfer, there must be at least one proxy account available to the user, configured with permission to the **SQL Server Integration Services package execution** subsystem.</span></span>  
  
     <span data-ttu-id="64408-279">Чтобы создать учетную запись-посредник для [!INCLUDE[ssIS](../../includes/ssis-md.md)] выполнения пакета, в обозревателе объектов разверните узел **Агент SQL Server**, затем — **прокси-серверы**, щелкните правой кнопкой мыши пункт **выполнение пакетов служб SSIS**и выберите команду **создать прокси-сервер**.</span><span class="sxs-lookup"><span data-stu-id="64408-279">To create a proxy account for [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution, in Object Explorer, expand **SQL Server Agent**, expand **Proxies**, right-click **SSIS Package Execution**, and then click **New Proxy**.</span></span>  
  
     <span data-ttu-id="64408-280">Члены предопределенной роли сервера **sysadmin** могут выбрать **учетную запись службы агента SQL Server**, которая имеет все нужные разрешения.</span><span class="sxs-lookup"><span data-stu-id="64408-280">Members of the **sysadmin** fixed server role can select the **SQL Server Agent Service Account**, which has the necessary permissions.</span></span>  
  
11. <span data-ttu-id="64408-281">На странице **Завершение работы мастера** просмотрите сводку выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="64408-281">From the **Complete the Wizard** page, review the summary of the selected options.</span></span> <span data-ttu-id="64408-282">Нажмите кнопку **Назад** для изменения параметров.</span><span class="sxs-lookup"><span data-stu-id="64408-282">Click **Back** to change an option.</span></span> <span data-ttu-id="64408-283">Чтобы создать базу данных, нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="64408-283">Click **Finish** to create the database.</span></span> <span data-ttu-id="64408-284">Во время передачи на странице **Выполнение операции** отображаются данные о состоянии выполнения операций, заданных в **мастере копирования баз данных**.</span><span class="sxs-lookup"><span data-stu-id="64408-284">During the transfer, the **Performing operation** page monitors status information about the execution of the **Copy Database Wizard**.</span></span>  
  
     <span data-ttu-id="64408-285">**Действие**</span><span class="sxs-lookup"><span data-stu-id="64408-285">**Action**</span></span>  
     <span data-ttu-id="64408-286">Отображает список всех выполняемых действий.</span><span class="sxs-lookup"><span data-stu-id="64408-286">Lists each action being performed.</span></span>  
  
     <span data-ttu-id="64408-287">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="64408-287">**Status**</span></span>  
     <span data-ttu-id="64408-288">Указывает, выполнено действие успешно или нет.</span><span class="sxs-lookup"><span data-stu-id="64408-288">Indicates whether the action as a whole succeeded or failed.</span></span>  
  
     <span data-ttu-id="64408-289">**Message**</span><span class="sxs-lookup"><span data-stu-id="64408-289">**Message**</span></span>  
     <span data-ttu-id="64408-290">Предоставляет все сообщения, возвращаемые в каждом шаге.</span><span class="sxs-lookup"><span data-stu-id="64408-290">Provides any messages returned from each step.</span></span>  
  
##  <a name="follow-up-after-upgrading-a-sql-server-database"></a><a name="FollowUp"></a> <span data-ttu-id="64408-291">Дальнейшие действия. После обновления базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="64408-291">Follow Up: After Upgrading a SQL Server Database</span></span>  
 <span data-ttu-id="64408-292">После обновления базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]с помощью мастера копирования баз данных эта база данных сразу же становится доступной и обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="64408-292">After you use the Copy Database Wizard to upgrade a database from an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the database becomes available immediately and is automatically upgraded.</span></span> <span data-ttu-id="64408-293">Если база данных содержит полнотекстовые индексы, то в процессе обновления будет произведен их импорт, сброс или перестроение в зависимости от установленного значения свойства сервера **Режим обновления полнотекстового каталога** .</span><span class="sxs-lookup"><span data-stu-id="64408-293">If the database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the **Full-Text Upgrade Option** server property.</span></span> <span data-ttu-id="64408-294">Если при обновлении выбран режим **Импортировать** или **Перестроить**, то полнотекстовые индексы во время обновления будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="64408-294">If the upgrade option is set to **Import** or **Rebuild**, the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="64408-295">В зависимости от объема индексируемых данных процесс импорта может занять несколько часов, а перестроение — в несколько (до десяти) раз больше.</span><span class="sxs-lookup"><span data-stu-id="64408-295">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="64408-296">Обратите внимание, что если при обновлении выбран режим **Импортировать**, а полнотекстовый каталог недоступен, то связанные с ним полнотекстовые индексы будут перестроены.</span><span class="sxs-lookup"><span data-stu-id="64408-296">Note also that when the upgrade option is set to **Import**, if a full-text catalog is not available, the associated full-text indexes are rebuilt.</span></span> <span data-ttu-id="64408-297">Сведения о просмотре и изменении параметра **Режим обновления полнотекстового поиска** см. в статье [Наблюдение за полнотекстовым поиском для экземпляра сервера и управление им](../search/manage-and-monitor-full-text-search-for-a-server-instance.md).</span><span class="sxs-lookup"><span data-stu-id="64408-297">For information about viewing or changing the setting of the **Full-Text Upgrade Option** property, see [Manage and Monitor Full-Text Search for a Server Instance](../search/manage-and-monitor-full-text-search-for-a-server-instance.md).</span></span>  
  
 <span data-ttu-id="64408-298">Если уровень совместимости пользовательской базы данных до обновления был 100 или выше, после обновления он останется таким же.</span><span class="sxs-lookup"><span data-stu-id="64408-298">If the compatibility level of a user database was 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="64408-299">Если уровень совместимости был 90, то в обновленной базе данных устанавливается уровень 100, что является минимально поддерживаемым уровнем совместимости в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64408-299">If the compatibility level was 90 in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="64408-300">Дополнительные сведения см. в разделе [Уровень совместимости инструкции ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="64408-300">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64408-301">См. также:</span><span class="sxs-lookup"><span data-stu-id="64408-301">See Also</span></span>  
 <span data-ttu-id="64408-302">[Обновление базы данных с помощью отсоединения и присоединения &#40;Transact-SQL&#41;](upgrade-a-database-using-detach-and-attach-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="64408-302">[Upgrade a Database Using Detach and Attach &#40;Transact-SQL&#41;](upgrade-a-database-using-detach-and-attach-transact-sql.md) </span></span>  
 [<span data-ttu-id="64408-303">Создание учетной записи-посредника агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="64408-303">Create a SQL Server Agent Proxy</span></span>](../../ssms/agent/create-a-sql-server-agent-proxy.md)  
  
  
