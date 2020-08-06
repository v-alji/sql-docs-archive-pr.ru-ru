---
title: Включение необходимых компонентов для таблицы FileTable | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], prerequisites
ms.assetid: 6286468c-9dc9-4eda-9961-071d2a36ebd6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5d5d2c5dab7909ec5403911d482823f488cdd809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654359"
---
# <a name="enable-the-prerequisites-for-filetable"></a><span data-ttu-id="6bf2b-102">Включение необходимых компонентов для таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="6bf2b-102">Enable the Prerequisites for FileTable</span></span>
  <span data-ttu-id="6bf2b-103">Описывает способ включения компонентов, обязательных для создания и использования таблиц FileTable.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-103">Describes how to enable the prerequisites for creating and using FileTables.</span></span>  
  
##  <a name="enabling-the-prerequisites-for-filetable"></a><a name="EnablePrereq"></a> <span data-ttu-id="6bf2b-104">Включение необходимых компонентов для FileTable</span><span class="sxs-lookup"><span data-stu-id="6bf2b-104">Enabling the Prerequisites for FileTable</span></span>  
 <span data-ttu-id="6bf2b-105">Чтобы включить необходимые компоненты для создания и использования таблиц FileTable, включите следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="6bf2b-105">To enable the prerequisites for creating and using FileTables, enable the following items:</span></span>  
  
-   <span data-ttu-id="6bf2b-106">**На уровне экземпляра.**</span><span class="sxs-lookup"><span data-stu-id="6bf2b-106">**At the instance level:**</span></span>  
  
    -   [<span data-ttu-id="6bf2b-107">Включение FILESTREAM на уровне экземпляра</span><span class="sxs-lookup"><span data-stu-id="6bf2b-107">Enabling FILESTREAM at the Instance Level</span></span>](#BasicsFilestream)  
  
-   <span data-ttu-id="6bf2b-108">**На уровне базы данных.**</span><span class="sxs-lookup"><span data-stu-id="6bf2b-108">**At the database level:**</span></span>  
  
    -   [<span data-ttu-id="6bf2b-109">Предоставление файловой группы FILESTREAM на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="6bf2b-109">Providing a FILESTREAM Filegroup at the Database Level</span></span>](#filegroup)  
  
    -   [<span data-ttu-id="6bf2b-110">Включение нетранзакционного доступа на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="6bf2b-110">Enabling Non-Transactional Access at the Database Level</span></span>](#BasicsNTAccess)  
  
    -   [<span data-ttu-id="6bf2b-111">Указание каталога для таблиц FileTable на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="6bf2b-111">Specifying a Directory for FileTables at the Database Level</span></span>](#BasicsDirectory)  
  
##  <a name="enabling-filestream-at-the-instance-level"></a><a name="BasicsFilestream"></a> <span data-ttu-id="6bf2b-112">Включение FILESTREAM на уровне экземпляра</span><span class="sxs-lookup"><span data-stu-id="6bf2b-112">Enabling FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="6bf2b-113">Таблицы FileTable расширяют возможности функции FILESTREAM в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bf2b-113">FileTables extend the capabilities of the FILESTREAM feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6bf2b-114">Поэтому, прежде чем будет возможно создавать и использовать таблицы FileTable, необходимо включить функцию FILESTREAM для доступа к операциям файлового ввода-вывода на уровне Windows и в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6bf2b-114">Therefore you have to enable FILESTREAM for file I/O access at the Windows level and on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you can create and use FileTables.</span></span>  
  
###  <a name="how-to-enable-filestream-at-the-instance-level"></a><a name="HowToFilestream"></a> <span data-ttu-id="6bf2b-115">Как включить функцию FILESTREAM на уровне экземпляра</span><span class="sxs-lookup"><span data-stu-id="6bf2b-115">How To: Enable FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="6bf2b-116">Сведения о включении FILESTREAM см. в разделе [Включение и настройка FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="6bf2b-116">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
 <span data-ttu-id="6bf2b-117">При вызове `sp_configure` для включения FILESTREAM на уровне экземпляра необходимо установить параметр filestream_access_level в значение 2.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-117">When you call `sp_configure` to enable FILESTREAM at the instance level, you have to set the filestream_access_level option to 2.</span></span> <span data-ttu-id="6bf2b-118">Дополнительные сведения см. в статье [Параметр конфигурации сервера "уровень доступа файлового потока"](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="6bf2b-118">For more information, see [filestream access level Server Configuration Option](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span></span>  
  
###  <a name="how-to-allow-filestream-through-the-firewall"></a><a name="firewall"></a> <span data-ttu-id="6bf2b-119">Как разрешить FILESTREAM через брандмауэр</span><span class="sxs-lookup"><span data-stu-id="6bf2b-119">How To: Allow FILESTREAM through the Firewall</span></span>  
 <span data-ttu-id="6bf2b-120">Сведения о разрешении FILESTREAM через брандмауэр см. в разделе [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span><span class="sxs-lookup"><span data-stu-id="6bf2b-120">For information about how to allow FILESTREAM through the firewall, see [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span></span>  
  
##  <a name="providing-a-filestream-filegroup-at-the-database-level"></a><a name="filegroup"></a> <span data-ttu-id="6bf2b-121">Предоставление файловой группы FILESTREAM на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="6bf2b-121">Providing a FILESTREAM Filegroup at the Database Level</span></span>  
 <span data-ttu-id="6bf2b-122">Для создания в базе данных таблиц FileTables эта база должна иметь файловую группу FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-122">Before you can create FileTables in a database, the database must have a FILESTREAM filegroup.</span></span> <span data-ttu-id="6bf2b-123">Дополнительные сведения об этом предварительном требовании см. в статье [Создание базы данных FILESTREAM-Enabled](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="6bf2b-123">For more information about this prerequisite, see [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
##  <a name="enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsNTAccess"></a> <span data-ttu-id="6bf2b-124">Включение нетранзакционного доступа на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="6bf2b-124">Enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="6bf2b-125">Таблицы FileTable позволяют приложениям Windows получать дескрипторы файлов Windows для данных FILESTREAM без необходимости транзакции.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-125">FileTables let Windows applications obtain a Windows file handle to FILESTREAM data without requiring a transaction.</span></span> <span data-ttu-id="6bf2b-126">Чтобы разрешить такой нетранзакционный доступ к файлам, хранящимся в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], необходимо указать нужный уровень нетранзакционного доступа на уровне базы данных, в которой будут содержаться таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-126">To allow this non-transactional access to files stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you have to specify the desired level of non-transactional access at the database level for each database that will contain FileTables.</span></span>  
  
###  <a name="how-to-check-whether-non-transactional-access-is-enabled-on-databases"></a><a name="HowToCheckAccess"></a> <span data-ttu-id="6bf2b-127">Как проверить состояние нетранзакционного доступа (включен или выключен)</span><span class="sxs-lookup"><span data-stu-id="6bf2b-127">How To: Check Whether Non-Transactional Access Is Enabled on Databases</span></span>  
 <span data-ttu-id="6bf2b-128">Выполнить запрос к представлению каталога [sys.database_filestream_options (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) и проверить столбцы **non_transacted_access** и **non_transacted_access_desc**.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-128">Query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **non_transacted_access** and **non_transacted_access_desc** columns.</span></span>  
  
```sql  
SELECT DB_NAME(database_id), non_transacted_access, non_transacted_access_desc  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="how-to-enable-non-transactional-access-at-the-database-level"></a><a name="HowToNTAccess"></a> <span data-ttu-id="6bf2b-129">Как включить нетранзакционный доступ на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="6bf2b-129">How To: Enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="6bf2b-130">Доступными уровнями нетранзакционного доступа являются FULL, READ_ONLY и OFF.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-130">The available levels of non-transactional access are FULL, READ_ONLY, and OFF.</span></span>  
  
 <span data-ttu-id="6bf2b-131">**Указание уровня нетранзакционного доступа с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="6bf2b-131">**Specify the level of non-transactional access by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="6bf2b-132">При **create a new database** вызовите инструкцию [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) с параметром **NON_TRANSACTED_ACCESS** FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-132">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
-   <span data-ttu-id="6bf2b-133">При **изменении существующей базы данных** вызовите инструкцию [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) с параметром **NON_TRANSACTED_ACCESS** FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-133">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
 <span data-ttu-id="6bf2b-134">**Задание уровня нетранзакционного доступа в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="6bf2b-134">**Specify the level of non-transactional access by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="6bf2b-135">Можно задать уровень нетранзакционного доступа в поле **Нетранзакционный доступ к файловому потоку** на странице **Параметры** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="6bf2b-135">You can specify the level of non-transactional access in the **FILESTREAM Non-transacted Access** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="6bf2b-136">Дополнительные сведения об этом диалоговом окне см. в статье [Свойства базы данных (страница "Параметры")](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="6bf2b-136">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
##  <a name="specifying-a-directory-for-filetables-at-the-database-level"></a><a name="BasicsDirectory"></a> <span data-ttu-id="6bf2b-137">Указание каталога для таблиц FileTable на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="6bf2b-137">Specifying a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="6bf2b-138">При включении нетранзакционного доступа к файлам на уровне базы данных можно при необходимости в то же время указать имя каталога с помощью параметра **DIRECTORY_NAME** .</span><span class="sxs-lookup"><span data-stu-id="6bf2b-138">When you enable non-transactional access to files at the database level, you can optionally provide a directory name at the same time by using the **DIRECTORY_NAME** option.</span></span> <span data-ttu-id="6bf2b-139">Если при включении нетранзакционного доступа не указано имя каталога, то необходимо ввести его позже, прежде чем будет возможно создать таблицу FileTable в базе данных.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-139">If you do not provide a directory name when you enable non-transactional access, then you have to provide it later before you can create FileTables in the database.</span></span>  
  
 <span data-ttu-id="6bf2b-140">В иерархии папок FileTable этот каталог на уровне базы данных является дочерним по отношению к общему ресурсу для FILESTREAM на уровне экземпляра и родительским по отношению к таблицам FileTable, созданным в базе данных.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-140">In the FileTable folder hierarchy, this database-level directory becomes the child of the share name specified for FILESTREAM at the instance level, and the parent of the FileTables created in the database.</span></span> <span data-ttu-id="6bf2b-141">Дополнительные сведения см. в статье [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="6bf2b-141">For more information, see [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span></span>  
  
###  <a name="how-to-specify-a-directory-for-filetables-at-the-database-level"></a><a name="HowToDirectory"></a> <span data-ttu-id="6bf2b-142">Как указать каталог для таблиц FileTable на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="6bf2b-142">How To: Specify a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="6bf2b-143">Указанное имя должно быть уникальным в экземпляре для каталогов уровня базы данных.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-143">The name that you specify must be unique across the instance for database-level directories.</span></span>  
  
 <span data-ttu-id="6bf2b-144">**Указание каталога для таблиц FileTable с помощью языка Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="6bf2b-144">**Specify a directory for FileTables by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="6bf2b-145">При **create a new database** вызовите инструкцию [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) с параметром **DIRECTORY_NAME** FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-145">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="6bf2b-146">При **изменении существующей базы данных** вызовите инструкцию [ALTER DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) с параметром **DIRECTORY_NAME** FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-146">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span> <span data-ttu-id="6bf2b-147">Если эти параметры используются для изменения имени каталога, то база данных должна быть заблокирована в монопольном режиме при отсутствии открытых дескрипторов файлов.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-147">When you use these options to change the directory name, the database must be exclusively locked, with no open file handles.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="6bf2b-148">При **подключении базы данных** вызовите инструкцию [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) с параметром **FOR ATTACH** и **DIRECTORY_NAME** FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-148">When you **attach a database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **FOR ATTACH** option and with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        FOR ATTACH WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="6bf2b-149">При **восстановлении базы данных** вызовите инструкцию [RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) с параметром **DIRECTORY_NAME** FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-149">When you **restore a database**, call the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    RESTORE DATABASE database_name  
        WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
 <span data-ttu-id="6bf2b-150">**Задание каталога для таблиц FileTable в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="6bf2b-150">**Specify a directory for FileTables by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="6bf2b-151">Можно указать имя каталога в поле **Имя каталога FILESTREAM** на странице **Параметры** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="6bf2b-151">You can specify a directory name in the **FILESTREAM Directory Name** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="6bf2b-152">Дополнительные сведения об этом диалоговом окне см. в статье [Свойства базы данных (страница "Параметры")](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="6bf2b-152">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
###  <a name="how-to-view-existing-directory-names-for-the-instance"></a><a name="viewnames"></a> <span data-ttu-id="6bf2b-153">Как просмотреть существующие имена каталогов для экземпляра</span><span class="sxs-lookup"><span data-stu-id="6bf2b-153">How to: View Existing Directory Names for the Instance</span></span>  
 <span data-ttu-id="6bf2b-154">Чтобы просмотреть список существующих имен каталогов для экземпляра, выполните запрос к представлению каталога [sys.database_filestream_options (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) и проверьте столбец **filestream_database_directory_name**.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-154">To view the list of existing directory names for the instance, query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **filestream_database_directory_name** column.</span></span>  
  
```sql  
SELECT DB_NAME ( database_id ), directory_name  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="requirements-and-restrictions-for-the-database-level-directory"></a><a name="ReqDirectory"></a> <span data-ttu-id="6bf2b-155">Требования и ограничения для уровня базы данных каталога</span><span class="sxs-lookup"><span data-stu-id="6bf2b-155">Requirements and Restrictions for the Database-Level Directory</span></span>  
  
-   <span data-ttu-id="6bf2b-156">При вызове метода **CREATE DATABASE** или **ALTER DATABASE** параметр **DIRECTORY_NAME**является необязательным.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-156">Setting the **DIRECTORY_NAME** is optional when you call **CREATE DATABASE** or **ALTER DATABASE**.</span></span> <span data-ttu-id="6bf2b-157">Если значение **DIRECTORY_NAME**не указано, имя каталога имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-157">If you do not specify a value for **DIRECTORY_NAME**, then the directory name remains null.</span></span> <span data-ttu-id="6bf2b-158">Тем не менее невозможно создать таблицу FileTable в базе данных, пока не указано значение для параметра **DIRECTORY_NAME** на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-158">However you cannot create FileTables in the database until you specify a value for **DIRECTORY_NAME** at the database level.</span></span>  
  
-   <span data-ttu-id="6bf2b-159">Указываемое имя каталога должно соответствовать требованиям файловой системы для допустимых имен каталогов.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-159">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
-   <span data-ttu-id="6bf2b-160">Если база данных содержит таблицы FileTable, нельзя вернуть параметр **DIRECTORY_NAME** в значение NULL.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-160">When the database contains FileTables, you cannot set the **DIRECTORY_NAME** back to a null value.</span></span>  
  
-   <span data-ttu-id="6bf2b-161">Операция присоединения или восстановления базы данных завершится ошибкой, если новая база данных имеет такое же значение параметра **DIRECTORY_NAME** , так как уже существует в целевом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-161">When you attach or restore a database, the operation fails if the new database has a value for **DIRECTORY_NAME** that already exists in the target instance.</span></span> <span data-ttu-id="6bf2b-162">Укажите уникальное значение для параметра **DIRECTORY_NAME** при вызове инструкции **CREATE DATABASE FOR ATTACH** или **RESTORE DATABASE**.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-162">Specify a unique value for **DIRECTORY_NAME** when you call **CREATE DATABASE FOR ATTACH** or **RESTORE DATABASE**.</span></span>  
  
-   <span data-ttu-id="6bf2b-163">При обновлении существующей базы данных до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]значение **DIRECTORY_NAME** равно NULL.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-163">When you upgrade an existing database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the value of **DIRECTORY_NAME** is null.</span></span>  
  
-   <span data-ttu-id="6bf2b-164">При включении или отключении нетранзакционного доступа на уровне базы данных операция не проверяет, было ли указано имя каталога и является ли оно уникальным.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-164">When you enable or disable non-transactional access at the database level, the operation does not check whether the directory name has been specified or whether it is unique.</span></span>  
  
-   <span data-ttu-id="6bf2b-165">При удалении базы данных, в которой включены таблицы FileTable, каталог на уровне базы данных и все структуры каталогов всех находящихся в ней таблиц FileTable удаляются.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-165">When you drop a database that was enabled for FileTables, the database-level directory and all the directory stuctures of all the FileTables under it are removed.</span></span>  
  
  
