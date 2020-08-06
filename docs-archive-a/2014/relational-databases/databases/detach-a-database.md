---
title: Отсоединение базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.detachdatabase.f1
helpviewer_keywords:
- database detaching [SQL Server]
- detaching databases [SQL Server]
ms.assetid: f63d4107-13e4-4bfe-922d-5e4f712e472d
author: stevestein
ms.author: sstein
ms.openlocfilehash: b8acc809b881012d18f78995bb8e521337fb02ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668887"
---
# <a name="detach-a-database"></a><span data-ttu-id="337c0-102">Отсоединение базы данных</span><span class="sxs-lookup"><span data-stu-id="337c0-102">Detach a Database</span></span>
  <span data-ttu-id="337c0-103">В этом разделе описывается отсоединение базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="337c0-103">This topic describes how to detach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="337c0-104">Отсоединенные файлы останутся на диске и могут быть повторно подсоединены с помощью инструкции CREATE DATABASE с параметрами FOR ATTACH или FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="337c0-104">The detached files remain and can be reattached by using CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="337c0-105">Файлы можно также переместить на другой сервер и подсоединить там.</span><span class="sxs-lookup"><span data-stu-id="337c0-105">The files can be moved to another server and attached there.</span></span>  
  
 <span data-ttu-id="337c0-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="337c0-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="337c0-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="337c0-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="337c0-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="337c0-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="337c0-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="337c0-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="337c0-110">**Отсоединение базы данных с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="337c0-110">**To detach a database, using:**</span></span>  
  
     [<span data-ttu-id="337c0-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="337c0-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="337c0-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="337c0-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="337c0-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="337c0-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="337c0-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="337c0-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="337c0-115">Список ограничений см. в статье [Присоединение и отсоединение базы данных (SQL Server)](database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="337c0-115">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="337c0-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="337c0-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="337c0-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="337c0-117">Permissions</span></span>  
 <span data-ttu-id="337c0-118">Необходимо членство в предопределенной роли базы данных db_owner.</span><span class="sxs-lookup"><span data-stu-id="337c0-118">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="337c0-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="337c0-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="337c0-120">Отсоединение базы данных</span><span class="sxs-lookup"><span data-stu-id="337c0-120">To detach a database</span></span>  
  
1.  <span data-ttu-id="337c0-121">В обозревателе объектов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем раскройте его.</span><span class="sxs-lookup"><span data-stu-id="337c0-121">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand the instance.</span></span>  
  
2.  <span data-ttu-id="337c0-122">Раскройте список **Базы данных**и выберите имя пользовательской базы данных, которую необходимо отсоединить.</span><span class="sxs-lookup"><span data-stu-id="337c0-122">Expand **Databases**, and select the name of the user database you want to detach.</span></span>  
  
3.  <span data-ttu-id="337c0-123">Щелкните правой кнопкой мыши имя базы данных, укажите пункт **Задачи**, а затем выберите команду **Отсоединить**.</span><span class="sxs-lookup"><span data-stu-id="337c0-123">Right-click the database name, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="337c0-124">Появится диалоговое окно **Отсоединение базы данных** .</span><span class="sxs-lookup"><span data-stu-id="337c0-124">The **Detach Database** dialog box appears.</span></span>  
  
     <span data-ttu-id="337c0-125">**Базы данных для отсоединения**</span><span class="sxs-lookup"><span data-stu-id="337c0-125">**Databases to detach**</span></span>  
     <span data-ttu-id="337c0-126">Перечисляет базы данных для отсоединения.</span><span class="sxs-lookup"><span data-stu-id="337c0-126">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="337c0-127">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="337c0-127">**Database Name**</span></span>  
     <span data-ttu-id="337c0-128">Отображает имя базы данных для отсоединения.</span><span class="sxs-lookup"><span data-stu-id="337c0-128">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="337c0-129">**Удалить соединения**</span><span class="sxs-lookup"><span data-stu-id="337c0-129">**Drop Connections**</span></span>  
     <span data-ttu-id="337c0-130">Завершить соединения с указанной базой данных.</span><span class="sxs-lookup"><span data-stu-id="337c0-130">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="337c0-131">Невозможно отсоединить базу данных с активными соединениями.</span><span class="sxs-lookup"><span data-stu-id="337c0-131">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="337c0-132">**Обновить статистику**</span><span class="sxs-lookup"><span data-stu-id="337c0-132">**Update Statistics**</span></span>  
     <span data-ttu-id="337c0-133">По умолчанию операция отсоединения сохраняет устаревшую статистику оптимизации. Для ее обновления установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="337c0-133">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="337c0-134">**Сохранять полнотекстовые каталоги**</span><span class="sxs-lookup"><span data-stu-id="337c0-134">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="337c0-135">По умолчанию операция отсоединения сохраняет связанные с базой данных полнотекстовые каталоги.</span><span class="sxs-lookup"><span data-stu-id="337c0-135">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="337c0-136">Для удаления этих каталогов сбросьте флажок **Сохранять полнотекстовые каталоги** .</span><span class="sxs-lookup"><span data-stu-id="337c0-136">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="337c0-137">Этот параметр доступен только при обновлении базы данных с версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="337c0-137">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="337c0-138">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="337c0-138">**Status**</span></span>  
     <span data-ttu-id="337c0-139">Отображает одно из следующих состояний: **Готово** или **Не готово**.</span><span class="sxs-lookup"><span data-stu-id="337c0-139">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="337c0-140">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="337c0-140">**Message**</span></span>  
     <span data-ttu-id="337c0-141">Столбец **Сообщение** может отображать сведения о базе данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="337c0-141">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="337c0-142">Если база данных участвует в репликации, то ее **Состояние** имеет значение **Не готово** , а в столбце **Сообщение** отображается строка **База данных реплицирована**.</span><span class="sxs-lookup"><span data-stu-id="337c0-142">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="337c0-143">Если имеется одно или несколько активных соединений с базой данных, то ее **состояние** имеет значение **Не готово**, а в столбце **Сообщение** отображается **Активных соединений**: _<число_активных_соединений>_ , например: **Активных подключений: 1**.</span><span class="sxs-lookup"><span data-stu-id="337c0-143">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="337c0-144">Прежде чем можно будет отсоединить базу данных, необходимо отключить активные соединений, выбрав команду **Удалить соединения**.</span><span class="sxs-lookup"><span data-stu-id="337c0-144">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="337c0-145">Чтобы получить сведения о сообщении, откройте монитор активности, щелкнув текст с гиперссылкой.</span><span class="sxs-lookup"><span data-stu-id="337c0-145">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
4.  <span data-ttu-id="337c0-146">Если для отсоединения базы данных все готово, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="337c0-146">When you are ready to detach the database, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="337c0-147">Отсоединенная база данных отображается в узле **Базы данных** обозревателя объектов до тех пор, пока не будет обновлено представление.</span><span class="sxs-lookup"><span data-stu-id="337c0-147">The newly detached database will remain visible in the **Databases** node of Object Explorer until the view is refreshed.</span></span> <span data-ttu-id="337c0-148">Обновить его можно в любой момент. Щелкните область обозревателя объектов и в меню выберите пункт **Представление**, а затем пункт **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="337c0-148">You can refresh the view at any time: Click in the Object Explorer pane, and from the menu bar select **View** and then **Refresh**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="337c0-149">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="337c0-149">Using Transact-SQL</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="337c0-150">Отсоединение базы данных</span><span class="sxs-lookup"><span data-stu-id="337c0-150">To detach a database</span></span>  
  
1.  <span data-ttu-id="337c0-151">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="337c0-151">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="337c0-152">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="337c0-152">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="337c0-153">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="337c0-153">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="337c0-154">В этом примере отсоединяется база данных AdventureWorks2012 с параметром SKIPCHECKS, установленным в значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="337c0-154">This example detaches the AdventureWorks2012 database with skipchecks set to true.</span></span>  
  
```  
EXEC sp_detach_db 'AdventureWorks2012', 'true';  
```  
  
## <a name="see-also"></a><span data-ttu-id="337c0-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="337c0-155">See Also</span></span>  
 <span data-ttu-id="337c0-156">[Присоединение и отсоединение базы данных (SQL Server)](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="337c0-156">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 [<span data-ttu-id="337c0-157">sp_detach_db (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="337c0-157">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
