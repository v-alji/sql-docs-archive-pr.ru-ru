---
title: Перенос базы данных с помощью функций отсоединения и присоединения (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database attaching [SQL Server]
- moving databases [SQL Server]
- database detaching [SQL Server]
- relocating databases [SQL Server]
- detaching databases [SQL Server]
- attaching databases [SQL Server]
ms.assetid: 6732a431-cdef-4f1e-9262-4ac3b77c275e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 768a70dfe94af6f8d65f7c76fa08d3dff650fe7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668883"
---
# <a name="move-a-database-using-detach-and-attach-transact-sql"></a><span data-ttu-id="37a34-102">Перенос базы данных путем отсоединения и присоединения (язык Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="37a34-102">Move a Database Using Detach and Attach (Transact-SQL)</span></span>
  <span data-ttu-id="37a34-103">В этом разделе описывается перемещение отсоединенной базы данных в другое местоположение и ее повторное присоединение к тому же или другому экземпляру сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37a34-103">This topic describes how to move a detached database to another location and re-attach it to the same or a different server instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="37a34-104">Однако рекомендуется переносить базы данных с помощью процедуры запланированного переноса ALTER DATABASE, а не путем отсоединения и присоединения.</span><span class="sxs-lookup"><span data-stu-id="37a34-104">However, we recommend that you move databases by using the ALTER DATABASE planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="37a34-105">Дополнительные сведения см. в статье [Move User Databases](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="37a34-105">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="37a34-106">Не рекомендуется подключать или восстанавливать базы данных, полученные из неизвестных или ненадежных источников.</span><span class="sxs-lookup"><span data-stu-id="37a34-106">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="37a34-107">В этих базах данных может содержаться вредоносный код, вызывающий выполнение непредусмотренных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] или появление ошибок из-за изменения схемы или физической структуры базы данных.</span><span class="sxs-lookup"><span data-stu-id="37a34-107">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="37a34-108">Перед тем как использовать базу данных, полученную из неизвестного или ненадежного источника, выполните на тестовом сервере инструкцию [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) для этой базы данных, а также изучите исходный код в базе данных, например хранимые процедуры и другой пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="37a34-108">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="37a34-109">Процедура</span><span class="sxs-lookup"><span data-stu-id="37a34-109">Procedure</span></span>  
  
#### <a name="to-move-a-database-by-using-detach-and-attach"></a><span data-ttu-id="37a34-110">Перемещение базы данных при помощи операций отсоединения и присоединения</span><span class="sxs-lookup"><span data-stu-id="37a34-110">To move a database by using detach and attach</span></span>  
  
1.  <span data-ttu-id="37a34-111">Отсоединение базы данных.</span><span class="sxs-lookup"><span data-stu-id="37a34-111">Detach the database.</span></span> <span data-ttu-id="37a34-112">Дополнительные сведения см. в разделе [Отсоединение базы данных](detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="37a34-112">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
2.  <span data-ttu-id="37a34-113">Переместите в «Проводнике» или окне командной строки файлы отсоединенной базы данных и журналов в новое место.</span><span class="sxs-lookup"><span data-stu-id="37a34-113">In a Windows Explorer or Windows Command Prompt window, move the detached database file or files and log file or files to the new location.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37a34-114">Если база данных включает только один файл небольшого размера, для ее перемещения можно использовать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="37a34-114">To move a single-file database, you can use email if the file size is small enough for email to accommodate.</span></span>  
  
     <span data-ttu-id="37a34-115">Перенос файлов журналов обязателен, даже если нужно создать новые файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="37a34-115">You should move the log files even if you intend to create new log files.</span></span> <span data-ttu-id="37a34-116">В некоторых случаях для повторного присоединения базы данных требуются файлы ее существующих журналов.</span><span class="sxs-lookup"><span data-stu-id="37a34-116">In some cases, reattaching a database requires its existing log files.</span></span> <span data-ttu-id="37a34-117">Поэтому всегда храните все файлы отсоединенных журналов, пока база данных не будет успешно присоединена без них.</span><span class="sxs-lookup"><span data-stu-id="37a34-117">Therefore, always keep all the detached log files until the database has been successfully attached without them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37a34-118">При попытке присоединить базу данных, не указывая файл журнала, операцией присоединения будет произведен поиск файла журнала в его исходном месте.</span><span class="sxs-lookup"><span data-stu-id="37a34-118">If you try to attach the database without specifying the log file, the attach operation will look for the log file in its original location.</span></span> <span data-ttu-id="37a34-119">Если копия журнала все еще хранится в исходном месте, она будет присоединена.</span><span class="sxs-lookup"><span data-stu-id="37a34-119">If a copy of the log still exists in the original location, that copy is attached.</span></span> <span data-ttu-id="37a34-120">Чтобы избежать применения исходного файла журнала, либо укажите путь к новому файлу журнала, либо удалите исходную его копию (после его копирования в новое место).</span><span class="sxs-lookup"><span data-stu-id="37a34-120">To avoid using the original log file, either specify the path of the new log file or remove the original copy of the log file (after copying it to the new location).</span></span>  
  
3.  <span data-ttu-id="37a34-121">Присоединение скопированных файлов.</span><span class="sxs-lookup"><span data-stu-id="37a34-121">Attach the copied files.</span></span> <span data-ttu-id="37a34-122">Дополнительные сведения см. в статье [Attach a Database](attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="37a34-122">For more information, see [Attach a Database](attach-a-database.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37a34-123">Пример</span><span class="sxs-lookup"><span data-stu-id="37a34-123">Example</span></span>  
 <span data-ttu-id="37a34-124">В следующем примере создается копия [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] инструкций, которая выполняется в окне редактора запросов, подключенном к экземпляру сервера, к которому присоединен.</span><span class="sxs-lookup"><span data-stu-id="37a34-124">The following example creates a copy of the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements are executed in a Query Editor window that is connected to the server instance to which is attached.</span></span>  
  
1.  <span data-ttu-id="37a34-125">Отсоедините [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] инструкции:</span><span class="sxs-lookup"><span data-stu-id="37a34-125">Detach the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sp_detach_db @dbname = N'AdventureWorks2012';  
    GO  
    ```  
  
2.  <span data-ttu-id="37a34-126">Скопируйте любым образом файлы базы данных (AdventureWorks208R2_Data.mdf и AdventureWorks208R2_log) в папки C:\MySQLServer\AdventureWorks208R2_Data.mdf и C:\MySQLServer\AdventureWorks208R2_Log.ldf, соответственно.</span><span class="sxs-lookup"><span data-stu-id="37a34-126">Using the method of your choice, copy the database files (AdventureWorks208R2_Data.mdf and AdventureWorks208R2_log) to: C:\MySQLServer\AdventureWorks208R2_Data.mdf and C:\MySQLServer\AdventureWorks208R2_Log.ldf, respectively.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="37a34-127">При работе с производственными базами данных помещайте базу данных и журналы транзакций на отдельные диски.</span><span class="sxs-lookup"><span data-stu-id="37a34-127">For a production database, place the database and transaction log on separate disks.</span></span>  
  
     <span data-ttu-id="37a34-128">При копировании файлов по сети на диск удаленного компьютера укажите имя удаленного места в формате UNC.</span><span class="sxs-lookup"><span data-stu-id="37a34-128">To copy files over the network to a disk on a remote computer, use the universal naming convention (UNC) name of the remote location.</span></span> <span data-ttu-id="37a34-129">Имя UNC имеет следующий формат: **\\\\** _имя_сервера_ **\\** _имя_общего_хранилища_ **\\** _путь_ **\\** _имя_файла_.</span><span class="sxs-lookup"><span data-stu-id="37a34-129">A UNC name takes the form **\\\\**_Servername_**\\**_Sharename_**\\**_Path_**\\**_Filename_.</span></span> <span data-ttu-id="37a34-130">Как и при записи файлов на жесткий диск локального компьютера, для записи (или считывания) файла на диск удаленного компьютера учетной запись пользователя, которая используется экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], должны быть предоставлены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="37a34-130">As with writing files to the local hard disk, the appropriate permissions that are required to read or write to a file on the remote disk must be granted to the user account used by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="37a34-131">Присоедините перемещенную базу данных и, возможно, ее журнал, выполнив следующие инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="37a34-131">Attach the moved database and, optionally, its log by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Data.mdf'),  
        (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Log.ldf')  
        FOR ATTACH;  
    GO  
    ```  
  
     <span data-ttu-id="37a34-132">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]только что присоединенная база данных отображается в обозревателе объектов не сразу.</span><span class="sxs-lookup"><span data-stu-id="37a34-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], a newly attached database is not immediately visible in Object Explorer.</span></span> <span data-ttu-id="37a34-133">Чтобы отобразить базу данных, щелкните в обозревателе объектов пункт **Вид** , а затем **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="37a34-133">To view the database, in Object Explorer, click **View,** and then **Refresh**.</span></span> <span data-ttu-id="37a34-134">Теперь, раскрыв в обозревателе объектов узел **Базы данных** , можно увидеть в списке присоединенную базу данных.</span><span class="sxs-lookup"><span data-stu-id="37a34-134">When the **Databases** node is expanded in Object Explorer, the newly attached database now appears in the list of databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a34-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="37a34-135">See Also</span></span>  
 [<span data-ttu-id="37a34-136">Присоединение и отсоединение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="37a34-136">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
