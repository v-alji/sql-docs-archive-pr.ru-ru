---
title: Удаление зеркального отображения базы данных (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- removing database mirroring [SQL Server]
ms.assetid: bbc4d7f7-3bc7-40d6-a822-af195fe7f8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19c1d0449fa1c7434aeaf9c51e3b2dc7bc6b68c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733074"
---
# <a name="remove-database-mirroring-sql-server"></a><span data-ttu-id="61f1f-102">Удаление зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="61f1f-102">Remove Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="61f1f-103">В этом разделе описано, как удалить зеркальное отображение базы данных [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61f1f-103">This topic describes how to remove database mirroring from a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  <span data-ttu-id="61f1f-104">Владелец базы данных может в любое время удалить зеркальное отображение базы данных. Для этого он должен вручную остановить сеанс.</span><span class="sxs-lookup"><span data-stu-id="61f1f-104">At any time, the database owner can manually stop a database mirroring session by removing mirroring from the database.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="61f1f-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="61f1f-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="61f1f-106">безопасность</span><span class="sxs-lookup"><span data-stu-id="61f1f-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="61f1f-107">Permissions</span><span class="sxs-lookup"><span data-stu-id="61f1f-107">Permissions</span></span>  
 <span data-ttu-id="61f1f-108">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="61f1f-108">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="61f1f-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61f1f-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="61f1f-110">Удаление зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="61f1f-110">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="61f1f-111">Во время сеанса зеркального отображения базы данных установите соединение с экземпляром главного сервера, в обозревателе объектов щелкните имя сервера и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="61f1f-111">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="61f1f-112">Разверните **Базы данных**и выберите нужную базу данных.</span><span class="sxs-lookup"><span data-stu-id="61f1f-112">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="61f1f-113">Щелкните базу данных правой кнопкой мыши, выберите **Задачи**, а затем **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="61f1f-113">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="61f1f-114">Откроется страница **Зеркальное отображение** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="61f1f-114">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="61f1f-115">На панели **Выбор страницы** щелкните **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="61f1f-115">In the **Select a Page** pane, click **Mirroring**.</span></span>  
  
5.  <span data-ttu-id="61f1f-116">Для удаления зеркального отображения нажмите **Отключить отображение**.</span><span class="sxs-lookup"><span data-stu-id="61f1f-116">To remove mirroring, click **Remove Mirroring**.</span></span> <span data-ttu-id="61f1f-117">Будет запрошено подтверждение.</span><span class="sxs-lookup"><span data-stu-id="61f1f-117">A prompt asks for confirmation.</span></span> <span data-ttu-id="61f1f-118">Если нажать кнопку **Да**, сеанс будет остановлен и зеркальное отображение будет удалено из этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="61f1f-118">If you click **Yes**, the session is stopped and mirroring is removed from the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="61f1f-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61f1f-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="61f1f-120">Удалить зеркальное отображение базы данных можно в диалоговом окне **Свойства базы данных**.</span><span class="sxs-lookup"><span data-stu-id="61f1f-120">To remove database mirroring, use the **Database Properties**.</span></span> <span data-ttu-id="61f1f-121">Откройте страницу **Зеркальное отображение** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="61f1f-121">use the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="61f1f-122">Удаление зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="61f1f-122">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="61f1f-123">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] любого из участников зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="61f1f-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] of either mirroring partner.</span></span>  
  
2.  <span data-ttu-id="61f1f-124">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="61f1f-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="61f1f-125">Выполните следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="61f1f-125">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    ALTER DATABASE database_name SET PARTNER OFF  
    ```  
  
     <span data-ttu-id="61f1f-126">где *database_name* — зеркально отображаемая база данных, сеанс которой необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="61f1f-126">where *database_name* is the mirrored database whose session you want to remove.</span></span>  
  
     <span data-ttu-id="61f1f-127">В следующем примере удаляется зеркальное отображение образца базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61f1f-127">The following example removes database mirroring from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER OFF;  
    ```  
  
##  <a name="follow-up-removing-database-mirroring"></a><a name="FollowUp"></a> <span data-ttu-id="61f1f-128">Дальнейшие действия. Удаление зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="61f1f-128">Follow Up: Removing Database Mirroring</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61f1f-129">Дополнительные сведения о последствиях удаления зеркального отображения базы данных см. в статье [Удаление зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="61f1f-129">For information about the impact of removing mirroring, see [Removing Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="61f1f-130">**Если планируется возобновление зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="61f1f-130">**If you intend to restart mirroring on the database**</span></span>  
  
     <span data-ttu-id="61f1f-131">Перед повторным запуском зеркального отображения к зеркальной базе данных необходимо применить все резервные копии журналов, созданные в основной базе данных перед удалением зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="61f1f-131">Any log backups taken on the principal database after mirroring was removed must all be applied to the mirror database before you can restart mirroring.</span></span>  
  
-   <span data-ttu-id="61f1f-132">**Если возобновление зеркального отображения не планируется**</span><span class="sxs-lookup"><span data-stu-id="61f1f-132">**If you do not intent to restart mirroring**</span></span>  
  
     <span data-ttu-id="61f1f-133">При необходимости можно восстановить прежнюю зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="61f1f-133">Optionally, you can recover the former mirror database.</span></span> <span data-ttu-id="61f1f-134">На экземпляре сервера, который был зеркальным сервером, можно выполнить следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61f1f-134">On the server instance that was the mirror server, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    RESTORE DATABASE database_name WITH RECOVERY;  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="61f1f-135">При восстановлении этой базы данных в режиме «в сети» будут доступны две разные базы данных с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="61f1f-135">If you recover this database, two divergent databases with the same name are online.</span></span> <span data-ttu-id="61f1f-136">Поэтому необходимо предусмотреть, чтобы у клиентов был доступ только к одной из них, обычно к новейшей основной базе данных.</span><span class="sxs-lookup"><span data-stu-id="61f1f-136">Therefore, you need to ensure that clients can access only one of them-typically the most recent principal database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="61f1f-137">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="61f1f-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="61f1f-138">Приостановка или возобновление сеанса зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="61f1f-138">Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;</span></span>](pause-or-resume-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="61f1f-139">Удаление следящего сервера из сеанса зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="61f1f-139">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="61f1f-140">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="61f1f-140">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="61f1f-141">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="61f1f-141">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="61f1f-142">Пример. Настройка зеркального отображения с помощью сертификатов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="61f1f-142">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="61f1f-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="61f1f-143">See Also</span></span>  
 <span data-ttu-id="61f1f-144">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="61f1f-144">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="61f1f-145">[Настройка зеркального отображения базы данных (SQL Server)](setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="61f1f-145">[Setting Up Database Mirroring &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="61f1f-146">Группы доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="61f1f-146">AlwaysOn Availability Groups (SQL Server)</span></span>](../availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
