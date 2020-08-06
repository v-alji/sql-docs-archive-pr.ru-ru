---
title: Создание базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], creating
- database creation [SQL Server], SQL Server Management Studio
- creating databases
ms.assetid: 4c4beea2-6cbc-4352-9db6-49ea8130bb64
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe42e394482e3abf4d87c00c6e79ee84db6ba278
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658831"
---
# <a name="create-a-database"></a><span data-ttu-id="b58cc-102">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="b58cc-102">Create a Database</span></span>
  <span data-ttu-id="b58cc-103">В этом разделе описывается создание базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b58cc-103">This topic describes how to create a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b58cc-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b58cc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b58cc-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b58cc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b58cc-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b58cc-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b58cc-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b58cc-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="b58cc-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="b58cc-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b58cc-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b58cc-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b58cc-110">**Создание базы данных с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="b58cc-110">**To create a database, using:**</span></span>  
  
     [<span data-ttu-id="b58cc-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b58cc-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b58cc-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b58cc-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b58cc-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b58cc-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b58cc-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b58cc-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b58cc-115">В экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]может быть задано не более 32 767 баз данных.</span><span class="sxs-lookup"><span data-stu-id="b58cc-115">A maximum of 32,767 databases can be specified on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b58cc-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b58cc-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="b58cc-117">Инструкция CREATE DATABASE должна выполняться в режиме автоматической фиксации (режим управления транзакциями по умолчанию) и не может применяться в явной или неявной транзакции.</span><span class="sxs-lookup"><span data-stu-id="b58cc-117">The CREATE DATABASE statement must run in autocommit mode (the default transaction management mode) and is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b58cc-118">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="b58cc-118">Recommendations</span></span>  
  
-   <span data-ttu-id="b58cc-119">Резервную копию базы данных [master](master-database.md) необходимо создавать каждый раз при создании, изменении или удалении пользовательской базы данных.</span><span class="sxs-lookup"><span data-stu-id="b58cc-119">The [master](master-database.md) database should be backed up whenever a user database is created, modified, or dropped.</span></span>  
  
-   <span data-ttu-id="b58cc-120">При создании базы данных файлы данных следует делать как можно большего размера, в соответствии с максимальным предполагаемым объемом данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="b58cc-120">When you create a database, make the data files as large as possible based on the maximum amount of data you expect in the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b58cc-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="b58cc-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b58cc-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="b58cc-122">Permissions</span></span>  
 <span data-ttu-id="b58cc-123">Требуется разрешение CREATE DATABASE в базе данных master или разрешение CREATE ANY DATABASE или ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="b58cc-123">Requires CREATE DATABASE permission in the master database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="b58cc-124">В целях сохранения управления над использованием диска в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]разрешение на создание баз данных обычно предоставляется небольшому числу учетных записей входа.</span><span class="sxs-lookup"><span data-stu-id="b58cc-124">To maintain control over disk use on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], permission to create databases is typically limited to a few login accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b58cc-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b58cc-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="b58cc-126">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="b58cc-126">To create a database</span></span>  
  
1.  <span data-ttu-id="b58cc-127">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="b58cc-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="b58cc-128">Щелкните правой кнопкой мыши элемент **Базы данных**, а затем выберите пункт **Создать базу данных**.</span><span class="sxs-lookup"><span data-stu-id="b58cc-128">Right-click **Databases**, and then click **New Database**.</span></span>  
  
3.  <span data-ttu-id="b58cc-129">В поле **Новая база данных**введите имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="b58cc-129">In **New Database**, enter a database name.</span></span>  
  
4.  <span data-ttu-id="b58cc-130">Чтобы создать базу данных, приняв все значения по умолчанию, нажмите кнопку **ОК**; иначе продолжайте выполнение следующих дополнительных шагов.</span><span class="sxs-lookup"><span data-stu-id="b58cc-130">To create the database by accepting all default values, click **OK**; otherwise, continue with the following optional steps.</span></span>  
  
5.  <span data-ttu-id="b58cc-131">Чтобы изменить имя владельца, нажмите ( **…** ) и выберите другого владельца.</span><span class="sxs-lookup"><span data-stu-id="b58cc-131">To change the owner name, click (**...**) to select another owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b58cc-132">Параметр **Использовать полнотекстовое индексирование** всегда установлен и недоступен (т. к. начиная с [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]все пользовательские базы данных поддерживают полнотекстовый поиск).</span><span class="sxs-lookup"><span data-stu-id="b58cc-132">The **Use full-text indexing** option is always checked and dimmed because, beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], all user databases are full-text enabled.</span></span>  
  
6.  <span data-ttu-id="b58cc-133">Чтобы изменить значения первичных данных по умолчанию и файлов журнала транзакций, щелкните соответствующую ячейку в сетке **Файлы базы данных** и введите новое значение.</span><span class="sxs-lookup"><span data-stu-id="b58cc-133">To change the default values of the primary data and transaction log files, in the **Database files** grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="b58cc-134">Дополнительные сведения см. в статье [AДобавление файлов данных или журналов в базу данных](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="b58cc-134">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
7.  <span data-ttu-id="b58cc-135">Чтобы изменить параметры сортировки базы данных, выберите страницу **Параметры** и выберите из списка желаемые параметры сортировки.</span><span class="sxs-lookup"><span data-stu-id="b58cc-135">To change the collation of the database, select the **Options** page, and then select a collation from the list.</span></span>  
  
8.  <span data-ttu-id="b58cc-136">Чтобы изменить модель восстановления, выберите страницу **Параметры** и модель восстановления из списка.</span><span class="sxs-lookup"><span data-stu-id="b58cc-136">To change the recovery model, select the **Options** page and select a recovery model from the list.</span></span>  
  
9. <span data-ttu-id="b58cc-137">Чтобы изменить параметры базы данных, выберите страницу **Параметры** и измените параметры базы данных.</span><span class="sxs-lookup"><span data-stu-id="b58cc-137">To change database options, select the **Options** page, and then modify the database options.</span></span> <span data-ttu-id="b58cc-138">Описание каждого параметра см. в статье [Параметры ALTER DATABASE SET (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="b58cc-138">For a description of each option, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
10. <span data-ttu-id="b58cc-139">Чтобы добавить новую файловую группу, перейдите на страницу **Группы файлов** .</span><span class="sxs-lookup"><span data-stu-id="b58cc-139">To add a new filegroup, click the **Filegroups** page.</span></span> <span data-ttu-id="b58cc-140">Нажмите **Добавить** и введите значения для файловой группы.</span><span class="sxs-lookup"><span data-stu-id="b58cc-140">Click **Add** and then enter the values for the filegroup.</span></span>  
  
11. <span data-ttu-id="b58cc-141">Чтобы добавить расширенное свойство в базу данных, выберите страницу **Расширенные свойства** .</span><span class="sxs-lookup"><span data-stu-id="b58cc-141">To add an extended property to the database, select the **Extended Properties** page.</span></span>  
  
    1.  <span data-ttu-id="b58cc-142">В столбце **Имя** введите имя расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="b58cc-142">In the **Name** column, enter a name for the extended property.</span></span>  
  
    2.  <span data-ttu-id="b58cc-143">В столбце **Значение** введите текст расширенного свойства.</span><span class="sxs-lookup"><span data-stu-id="b58cc-143">In the **Value** column, enter the extended property text.</span></span> <span data-ttu-id="b58cc-144">Например, введите одно или несколько предложений, которые описывают базу данных.</span><span class="sxs-lookup"><span data-stu-id="b58cc-144">For example, enter one or more statements that describe the database.</span></span>  
  
12. <span data-ttu-id="b58cc-145">Чтобы создать базу данных, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b58cc-145">To create the database, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b58cc-146">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b58cc-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="b58cc-147">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="b58cc-147">To create a database</span></span>  
  
1.  <span data-ttu-id="b58cc-148">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b58cc-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b58cc-149">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b58cc-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b58cc-150">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b58cc-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b58cc-151">В этом примере создается база данных `Sales`.</span><span class="sxs-lookup"><span data-stu-id="b58cc-151">This example creates the database `Sales`.</span></span> <span data-ttu-id="b58cc-152">Ключевое слово PRIMARY не использовано, поэтому первый файл (`Sales`_`dat`) становится первичным файлом.</span><span class="sxs-lookup"><span data-stu-id="b58cc-152">Because the keyword PRIMARY is not used, the first file (`Sales`_`dat`) becomes the primary file.</span></span> <span data-ttu-id="b58cc-153">Поскольку в параметре SIZE для файла `Sales`\_`dat` не заданы суффиксы MB и KB, используется значение MB и пространство выделяется в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="b58cc-153">Because neither MB nor KB is specified in the SIZE parameter for the `Sales`\_`dat` file, it uses MB and is allocated in megabytes.</span></span> <span data-ttu-id="b58cc-154">Резервную копию базы данных `Sales`\_`log` выделено в мегабайтах, потому что суффикс `MB` явно указан в параметре `SIZE` .</span><span class="sxs-lookup"><span data-stu-id="b58cc-154">The `Sales`\_`log` file is allocated in megabytes because the `MB` suffix is explicitly stated in the `SIZE` parameter.</span></span>  
  
```sql  
USE master ;  
GO  
CREATE DATABASE Sales  
ON   
( NAME = Sales_dat,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\saledat.mdf',  
    SIZE = 10,  
    MAXSIZE = 50,  
    FILEGROWTH = 5 )  
LOG ON  
( NAME = Sales_log,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\salelog.ldf',  
    SIZE = 5MB,  
    MAXSIZE = 25MB,  
    FILEGROWTH = 5MB ) ;  
GO  
```  
  
 <span data-ttu-id="b58cc-155">Дополнительные примеры см. в статье [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b58cc-155">For more examples, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58cc-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="b58cc-156">See Also</span></span>  
 <span data-ttu-id="b58cc-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="b58cc-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="b58cc-158">[Присоединение и отсоединение базы данных (SQL Server)](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b58cc-158">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="b58cc-159">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b58cc-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="b58cc-160">Добавление файлов данных или журналов в базу данных</span><span class="sxs-lookup"><span data-stu-id="b58cc-160">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
