---
title: Присоединение и отсоединение баз данных DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 830e33bc-dd15-4f8e-a4ac-d8634b78fe45
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bcac9d1f53b10cf6356b878ce4006f66c198d99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656576"
---
# <a name="detaching-and-attaching-dqs-databases"></a><span data-ttu-id="b2446-102">Присоединение и отсоединение баз данных DQS</span><span class="sxs-lookup"><span data-stu-id="b2446-102">Detaching and Attaching DQS Databases</span></span>
  <span data-ttu-id="b2446-103">В этом разделе описывается, как отсоединять и присоединять базы данных DQS.</span><span class="sxs-lookup"><span data-stu-id="b2446-103">This topic describes how to detach and attach the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b2446-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b2446-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="b2446-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b2446-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b2446-106">Список ограничений см. в статье [Присоединение и отсоединение базы данных (SQL Server)](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2446-106">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b2446-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b2446-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="b2446-108">Убедитесь, что не существует текущих операций или процессов в DQS.</span><span class="sxs-lookup"><span data-stu-id="b2446-108">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="b2446-109">Это можно проверить с помощью экрана **Мониторинг активности** .</span><span class="sxs-lookup"><span data-stu-id="b2446-109">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="b2446-110">Дополнительные сведения о работе с этим экраном см. в разделе [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="b2446-110">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="b2446-111">Убедитесь, что на сервере [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]нет подключенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b2446-111">Ensure that there are no users logged on the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b2446-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="b2446-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b2446-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="b2446-113">Permissions</span></span>  
  
-   <span data-ttu-id="b2446-114">Для отсоединения баз данных DQS учетная запись пользователя Windows должна входить в предопределенную роль сервера db_owner на экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b2446-114">Your Windows user account must be a member of the db_owner fixed server role in the SQL Server instance to detach DQS databases.</span></span>  
  
-   <span data-ttu-id="b2446-115">Для присоединения баз данных учетная запись пользователя Windows должна обладать разрешением CREATE DATABASE, CREATE ANY DATABASE или ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="b2446-115">Your Windows user account must have CREATE DATABASE, CREATE ANY DATABASE, or ALTER ANY DATABASE permission to attach a database.</span></span>  
  
-   <span data-ttu-id="b2446-116">Для завершения любых выполняемых операций или остановки каких-либо процессов в службах DQS необходимо быть членом роли dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="b2446-116">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="detach-dqs-databases"></a><a name="Detach"></a><span data-ttu-id="b2446-117">Отсоединение баз данных DQS</span><span class="sxs-lookup"><span data-stu-id="b2446-117">Detach DQS Databases</span></span>  
 <span data-ttu-id="b2446-118">При отсоединении базы данных DQS с помощью среды SQL Server Management Studio отсоединенные файлы остаются на компьютере, их можно повторно присоединить к этому же экземпляру SQL Server либо они могу быть перемещены на другой сервер и присоединены там.</span><span class="sxs-lookup"><span data-stu-id="b2446-118">When you detach a DQS database using SQL Server Management Studio, the detached files remain on your computer, and can be reattached to the same SQL Server instance or can be can be moved to another server and attached there.</span></span> <span data-ttu-id="b2446-119">Файлы базы данных DQS обычно доступны в следующем расположении на компьютере со службами Data Quality Services: C:\Program Files\Microsoft SQL Server\MSSQL12. *<Instance_Name>* \MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="b2446-119">The DQS database files are typically available at the following location on your Data Quality Services computer: C:\Program Files\Microsoft SQL Server\MSSQL12.*<Instance_Name>* \MSSQL\DATA.</span></span>  
  
1.  <span data-ttu-id="b2446-120">Запустите среду Microsoft SQL Server Management Studio и подключитесь к соответствующему экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b2446-120">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="b2446-121">В обозревателе объектов разверните узел **Базы данных** .</span><span class="sxs-lookup"><span data-stu-id="b2446-121">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="b2446-122">Щелкните правой кнопкой мыши базу данных **DQS_MAIN** , укажите пункт **Задачи**, а затем выберите команду **Отсоединить**.</span><span class="sxs-lookup"><span data-stu-id="b2446-122">Right-click the **DQS_MAIN** database, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="b2446-123">Появится диалоговое окно **Отсоединение базы данных** .</span><span class="sxs-lookup"><span data-stu-id="b2446-123">The **Detach Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b2446-124">Установите флажок в столбце **Удаление** и нажмите кнопку **ОК** , чтобы отсоединить базу данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="b2446-124">Select the check box under the **Drop** column, and click **OK** to detach the DQS_MAIN database.</span></span>  
  
5.  <span data-ttu-id="b2446-125">Повторите шаги 3 и 4 для баз данных DQS_PROJECTS и DQS_STAGING_DATA, чтобы отсоединить их.</span><span class="sxs-lookup"><span data-stu-id="b2446-125">Repeat steps 3 and 4 with the DQS_PROJECTS and DQS_STAGING_DATA databases to detach them.</span></span>  
  
 <span data-ttu-id="b2446-126">Базы данных DQS также можно отсоединять с использованием инструкций Transact-SQL с помощью хранимой процедуры sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="b2446-126">You can also detach DQS databases using the Transact-SQL statements by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="b2446-127">Дополнительные сведения об отсоединении баз данных с помощью инструкций Transact-SQL см. в подразделе [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) раздела [Detach a Database](../relational-databases/databases/detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="b2446-127">For more information about detaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) in [Detach a Database](../relational-databases/databases/detach-a-database.md).</span></span>  
  
##  <a name="attach-dqs-databases"></a><a name="Attach"></a><span data-ttu-id="b2446-128">Присоединение баз данных DQS</span><span class="sxs-lookup"><span data-stu-id="b2446-128">Attach DQS Databases</span></span>  
 <span data-ttu-id="b2446-129">Используйте следующие указания для присоединения базы данных DQS к тому же экземпляру SQL Server (от которого она была отсоединена) или другому экземпляру SQL Server, на котором установлен [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2446-129">Use the following instructions to attach a DQS database to the same SQL Server instance (from where you detached) or a different SQL Server instance where [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
1.  <span data-ttu-id="b2446-130">Запустите среду Microsoft SQL Server Management Studio и подключитесь к соответствующему экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b2446-130">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="b2446-131">В обозревателе объектов щелкните правой кнопкой мыши **Базы данных**и выберите пункт **Присоединить**.</span><span class="sxs-lookup"><span data-stu-id="b2446-131">In Object Explorer, right-click **Databases**, and then click **Attach**.</span></span> <span data-ttu-id="b2446-132">Появится диалоговое окно **Присоединение базы данных** .</span><span class="sxs-lookup"><span data-stu-id="b2446-132">The **Attach Databases** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="b2446-133">Чтобы указать базу данных для присоединения, щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b2446-133">To specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="b2446-134">Откроется диалоговое окно **Расположение файлов базы данных** .</span><span class="sxs-lookup"><span data-stu-id="b2446-134">The **Locate Database Files** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b2446-135">Выберите диск, на котором находится база данных, и разверните дерево каталогов, чтобы найти и выделить MDF-файл базы данных.</span><span class="sxs-lookup"><span data-stu-id="b2446-135">Select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database.</span></span> <span data-ttu-id="b2446-136">Например, для базы данных DQS_MAIN:</span><span class="sxs-lookup"><span data-stu-id="b2446-136">For example, for the DQS_MAIN database:</span></span>  
  
    ```  
    C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\DQS_MAIN.mdf  
    ```  
  
5.  <span data-ttu-id="b2446-137">Панель **Сведения базы данных** (внизу) отображает имя присоединяемых файлов.</span><span class="sxs-lookup"><span data-stu-id="b2446-137">The **database details** (lower) pane displays the names of the files to be attached.</span></span> <span data-ttu-id="b2446-138">Чтобы проверить или изменить путь к файлу, нажмите кнопку **Обзор** ( ... ).</span><span class="sxs-lookup"><span data-stu-id="b2446-138">To verify or change the pathname of a file, click the **Browse** button (...).</span></span>  
  
6.  <span data-ttu-id="b2446-139">Чтобы присоединить базу данных DQS_MAIN, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="b2446-139">Click **OK** to attach the DQS_MAIN database.</span></span>  
  
7.  <span data-ttu-id="b2446-140">Повторите шаги с 2 по 6 для баз данных DQS_PROJECTS и DQS_STAGING_DATA, чтобы присоединить их.</span><span class="sxs-lookup"><span data-stu-id="b2446-140">Repeat steps 2-6 for the DQS_PROJECTS and DQS_STAGING_DATA databases to attach them.</span></span>  
  
8.  <span data-ttu-id="b2446-141">Затем также необходимо выполнить инструкции Transact-SQL после восстановления базы данных DQS_MAIN из копии, в противном случае при попытке подключиться к серверу Data Quality Server с помощью приложения Data Quality Client на экране появится сообщение об ошибке и подключение установить не удастся.</span><span class="sxs-lookup"><span data-stu-id="b2446-141">You must also run the Transact-SQL statements in the next step after restoring the DQS_MAIN database otherwise an error message is displayed when you try to connect to Data Quality Server by using the Data Quality Client application, and you cannot connect.</span></span> <span data-ttu-id="b2446-142">Однако выполнять шаги 9 и 10 не требуется, если вы присоединили только базу данных DQS_PROJECTS или DQS_STAGING_DATA, а не базу данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="b2446-142">However, you do not need to perform steps 9 and 10 if you have just attached the DQS_PROJECTS or DQS_STAGING_DATA database, and not DQS_MAIN.</span></span>  
  
     <span data-ttu-id="b2446-143">Чтобы выполнить инструкции Transact-SQL, в обозревателе объектов щелкните сервер правой кнопкой мыши и выберите команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b2446-143">To run the Transact-SQL statements, in Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
9. <span data-ttu-id="b2446-144">В окно редактора запросов скопируйте следующие инструкции SQL:</span><span class="sxs-lookup"><span data-stu-id="b2446-144">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    ALTER DATABASE [DQS_MAIN] SET TRUSTWORTHY ON;  
    EXEC sp_configure 'clr enabled', 1;  
    RECONFIGURE WITH OVERRIDE  
    ALTER DATABASE [DQS_MAIN] SET ENABLE_BROKER  
    ALTER AUTHORIZATION ON DATABASE::[DQS_MAIN] TO [##MS_dqs_db_owner_login##]  
    ALTER AUTHORIZATION ON DATABASE::[DQS_PROJECTS] TO [##MS_dqs_db_owner_login##]  
    ```  
  
10. <span data-ttu-id="b2446-145">Нажмите клавишу F5, чтобы выполнить инструкции.</span><span class="sxs-lookup"><span data-stu-id="b2446-145">Press F5 to execute the statements.</span></span> <span data-ttu-id="b2446-146">Откройте область «Результаты», чтобы удостовериться в успешном выполнении инструкций.</span><span class="sxs-lookup"><span data-stu-id="b2446-146">Check the Results pane to verify that the statements have executed successfully.</span></span> <span data-ttu-id="b2446-147">На экране появится следующее сообщение: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span><span class="sxs-lookup"><span data-stu-id="b2446-147">You will see the following message: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span></span>  
  
11. <span data-ttu-id="b2446-148">Подключитесь к серверу Data Quality Server с помощью приложения Data Quality Client, чтобы проверить возможность установления подключения.</span><span class="sxs-lookup"><span data-stu-id="b2446-148">Connect to the Data Quality Server using the Data Quality Client to verify if you can connect successfully.</span></span>  
  
 <span data-ttu-id="b2446-149">Базы данных DQS также можно присоединять с помощью инструкций Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b2446-149">You can also attach DQS databases using the Transact-SQL statements.</span></span> <span data-ttu-id="b2446-150">Дополнительные сведения о присоединении баз данных с помощью инструкций Transact-SQL см. в подразделе [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) раздела [Attach a Database](../relational-databases/databases/attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="b2446-150">For more information about attaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) in [Attach a Database](../relational-databases/databases/attach-a-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2446-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2446-151">See Also</span></span>  
 [<span data-ttu-id="b2446-152">Manage DQS Databases</span><span class="sxs-lookup"><span data-stu-id="b2446-152">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
