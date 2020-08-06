---
title: Создание, изменение и удаление таблиц FileTable | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], altering
- FileTables [SQL Server], dropping
- FileTables [SQL Server], creating
ms.assetid: 47d69e37-8778-4630-809b-2261b5c41c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a10e6333f6dd38a850a832b82a7cb7a0e0bf698
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655782"
---
# <a name="create-alter-and-drop-filetables"></a><span data-ttu-id="6a35a-102">Создание, изменение и удаление таблиц FileTables</span><span class="sxs-lookup"><span data-stu-id="6a35a-102">Create, Alter, and Drop FileTables</span></span>
  <span data-ttu-id="6a35a-103">Описывает способы создания новых таблиц FileTable и изменения или удаления существующих таблиц FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-103">Describes how to create a new FileTable, or alter or drop an existing FileTable.</span></span>  
  
##  <a name="creating-a-filetable"></a><a name="BasicsCreate"></a> <span data-ttu-id="6a35a-104">Создание таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="6a35a-104">Creating a FileTable</span></span>  
 <span data-ttu-id="6a35a-105">Таблица FileTable является специализированной пользовательской таблицей с заранее заданной и фиксированной схемой.</span><span class="sxs-lookup"><span data-stu-id="6a35a-105">A FileTable is a specialized user table that has a pre-defined and fixed schema.</span></span> <span data-ttu-id="6a35a-106">Эта схема содержит данные FILESTREAM, сведения о файлах и каталогах и атрибуты файлов.</span><span class="sxs-lookup"><span data-stu-id="6a35a-106">This schema stores FILESTREAM data, file and directory information, and file attributes.</span></span> <span data-ttu-id="6a35a-107">Сведения о данном образце схемы см. в разделе [FileTable Schema](filetable-schema.md).</span><span class="sxs-lookup"><span data-stu-id="6a35a-107">For information about the FileTable schema, see [FileTable Schema](filetable-schema.md).</span></span>  
  
 <span data-ttu-id="6a35a-108">Новую таблицу FileTable можно создать с помощью языка Transact-SQL или среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a35a-108">You can create a new FileTable by using Transact-SQL or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6a35a-109">Поскольку таблица FileTable имеет фиксированную схему, нет необходимости указывать список столбцов.</span><span class="sxs-lookup"><span data-stu-id="6a35a-109">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="6a35a-110">Простой синтаксис для создания таблицы FileTable позволяет указать следующее:</span><span class="sxs-lookup"><span data-stu-id="6a35a-110">The simple syntax for creating a FileTable lets you specify:</span></span>  
  
-   <span data-ttu-id="6a35a-111">Имя каталога.</span><span class="sxs-lookup"><span data-stu-id="6a35a-111">A directory name.</span></span> <span data-ttu-id="6a35a-112">В иерархии папок FileTable этот каталог уровня таблицы становится дочерним для каталога базы данных, указанного на уровне базы данных, и родительским для файлов или каталогов, хранящихся в таблице.</span><span class="sxs-lookup"><span data-stu-id="6a35a-112">In the FileTable folder hierarchy, this table-level directory becomes the child of the database directory specified at the database level, and the parent of the files or directories stored in the table.</span></span>  
  
-   <span data-ttu-id="6a35a-113">Имя параметров сортировки, используемое для имен файлов в столбце **Name** таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-113">The name of the collation to be used for file names in the **Name** column of the FileTable.</span></span>  
  
-   <span data-ttu-id="6a35a-114">Можно также указать имена, предназначенные для использования в трех первичных ключах и ограничениях уникальности, создаваемых автоматически.</span><span class="sxs-lookup"><span data-stu-id="6a35a-114">The names to be used for the 3 primary key and unique constraints that are automatically created.</span></span>  
  
###  <a name="how-to-create-a-filetable"></a><a name="HowToCreate"></a> <span data-ttu-id="6a35a-115">Как создать FileTable</span><span class="sxs-lookup"><span data-stu-id="6a35a-115">How To: Create a FileTable</span></span>  
 <span data-ttu-id="6a35a-116">**Создание таблицы FileTable с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="6a35a-116">**Create a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="6a35a-117">Создайте объект FileTable, вызвав инструкцию [CREATE TABLE (Transact-SQL)](/sql/t-sql/statements/create-table-transact-sql) с параметром **AS FileTable**.</span><span class="sxs-lookup"><span data-stu-id="6a35a-117">Create a FileTable by calling the [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) statement with the **AS FileTable** option.</span></span> <span data-ttu-id="6a35a-118">Поскольку таблица FileTable имеет фиксированную схему, нет необходимости указывать список столбцов.</span><span class="sxs-lookup"><span data-stu-id="6a35a-118">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="6a35a-119">Можно указать следующие параметры для новой FileTable:</span><span class="sxs-lookup"><span data-stu-id="6a35a-119">You can specify the following settings for the new FileTable:</span></span>  
  
1.  <span data-ttu-id="6a35a-120">**FILETABLE_DIRECTORY**.</span><span class="sxs-lookup"><span data-stu-id="6a35a-120">**FILETABLE_DIRECTORY**.</span></span> <span data-ttu-id="6a35a-121">Указывает каталог, выполняющий функции корневого каталога для всех файлов и каталогов, хранящихся в FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-121">Specifies the directory that serves as the root directory for all the files and directories stored in the FileTable.</span></span> <span data-ttu-id="6a35a-122">Это имя должно быть уникальным среди всех имен каталогов FileTable в базе данных.</span><span class="sxs-lookup"><span data-stu-id="6a35a-122">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="6a35a-123">Проверка уникальности выполняется без учета регистра, независимо от текущих параметров сортировки.</span><span class="sxs-lookup"><span data-stu-id="6a35a-123">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="6a35a-124">Это значение имеет тип данных **nvarchar(255)** и использует фиксированные параметры сортировки **Latin1_General_CI_AS_KS_WS**.</span><span class="sxs-lookup"><span data-stu-id="6a35a-124">This value has a data type of **nvarchar(255)** and uses a fixed collation of **Latin1_General_CI_AS_KS_WS**.</span></span>  
  
    -   <span data-ttu-id="6a35a-125">Указываемое имя каталога должно соответствовать требованиям файловой системы для допустимых имен каталогов.</span><span class="sxs-lookup"><span data-stu-id="6a35a-125">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
    -   <span data-ttu-id="6a35a-126">Это имя должно быть уникальным среди всех имен каталогов FileTable в базе данных.</span><span class="sxs-lookup"><span data-stu-id="6a35a-126">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="6a35a-127">Проверка уникальности выполняется без учета регистра, независимо от текущих параметров сортировки.</span><span class="sxs-lookup"><span data-stu-id="6a35a-127">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="6a35a-128">Если при создании таблицы FileTable не указано имя каталога, то в качестве имени каталога используется имя самой таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-128">If you do not provide a directory name when you create the FileTable, then the name of the FileTable itself is used as the directory name.</span></span>  
  
2.  <span data-ttu-id="6a35a-129">**FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="6a35a-129">**FILETABLE_COLLATE_FILENAME**.</span></span> <span data-ttu-id="6a35a-130">Указывает имя параметров сортировки, применяемых к столбцу **Name** в таблице FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-130">Specifies the name of the collation to be applied to the **Name** column in the FileTable.</span></span>  
  
    1.  <span data-ttu-id="6a35a-131">Указанные параметры сортировки должны быть **нечувствительны к регистру** , чтобы соответствовать семантике имен файлов Windows.</span><span class="sxs-lookup"><span data-stu-id="6a35a-131">The specified collation must be **case-insensitive** to comply with Windows file naming semantics.</span></span>  
  
    2.  <span data-ttu-id="6a35a-132">Если для параметра **FILETABLE_COLLATE_FILENAME**не указано значение или было задано значение **database_default**, столбец унаследует параметры сортировки текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="6a35a-132">If you do not provide a value for **FILETABLE_COLLATE_FILENAME**, or you specify **database_default**, the column inherits the collation of the current database.</span></span> <span data-ttu-id="6a35a-133">Если в текущей базе данных используются параметры сортировки с учетом регистра, то операция **CREATE TABLE** завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="6a35a-133">If the current database collation is case-sensitive, an error is raised and the **CREATE TABLE** operation fails.</span></span>  
  
3.  <span data-ttu-id="6a35a-134">Можно также указать имена, предназначенные для использования в трех первичных ключах и ограничениях уникальности, создаваемых автоматически.</span><span class="sxs-lookup"><span data-stu-id="6a35a-134">You can also specify the names to be used for the 3 primary key and unique constraints that are automatically created.</span></span> <span data-ttu-id="6a35a-135">Если имена не будут предоставлены, то система сформирует имена, как описано ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6a35a-135">If you do not provide names, then the system generates names as described later in this topic.</span></span>  
  
    -   <span data-ttu-id="6a35a-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="6a35a-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="6a35a-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="6a35a-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="6a35a-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="6a35a-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
 <span data-ttu-id="6a35a-139">**Примеры**</span><span class="sxs-lookup"><span data-stu-id="6a35a-139">**Examples**</span></span>  
  
 <span data-ttu-id="6a35a-140">В следующем примере рассмотрено создание новой таблицы FileTable с указанием значений, определяемых пользователем, для **FILETABLE_DIRECTORY** и **FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="6a35a-140">The following example creates a new FileTable and specifies user-defined values for both **FILETABLE_DIRECTORY** and **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable  
    WITH (   
          FileTable_Directory = 'DocumentTable',  
          FileTable_Collate_Filename = database_default  
         );  
GO  
```  
  
 <span data-ttu-id="6a35a-141">В следующем примере также создается новый FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-141">The following example also creates a new FileTable.</span></span> <span data-ttu-id="6a35a-142">Определяемые пользователем значения не заданы, поэтому значение **FILETABLE_DIRECTORY** становится именем таблицы FileTable, значение **FILETABLE_COLLATE_FILENAME** становится равным database_default, а первичный ключ и ограничения уникальности принимают значения, сформированные системой.</span><span class="sxs-lookup"><span data-stu-id="6a35a-142">Since user-defined values are not specified, the value of **FILETABLE_DIRECTORY** becomes the name of the FileTable, the value of **FILETABLE_COLLATE_FILENAME** becomes database_default, and the primary key and unique contraints receive system-generated names.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable;  
GO  
```  
  
 <span data-ttu-id="6a35a-143">**Создание таблицы FileTable в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="6a35a-143">**Create a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="6a35a-144">В обозревателе объектов разверните объекты в выбранной базе данных, затем щелкните правой кнопкой мыши папку **Таблицы** и выберите **Создать FileTable**.</span><span class="sxs-lookup"><span data-stu-id="6a35a-144">In Object Explorer, expand the objects under the selected database, then right-click on the **Tables** folder, and then select **New FileTable**.</span></span>  
  
 <span data-ttu-id="6a35a-145">Этот параметр открывает новое окно скрипта, в котором содержится шаблон скрипта Transact-SQL, который можно настроить и выполнить с целью создания таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-145">This option opens a new script window which contains a Transact-SQL script template that you can customize and run to create a FileTable.</span></span> <span data-ttu-id="6a35a-146">Для простой настройки скрипта используйте параметр **Указать значения для параметров шаблона** в меню **Запрос** .</span><span class="sxs-lookup"><span data-stu-id="6a35a-146">Use the **Specify Values for Template Parameters** option on the **Query** menu to customize the script easily.</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-filetable"></a><a name="ReqCreate"></a> <span data-ttu-id="6a35a-147">Требования и ограничения для создания FileTable</span><span class="sxs-lookup"><span data-stu-id="6a35a-147">Requirements and Restrictions for Creating a FileTable</span></span>  
  
-   <span data-ttu-id="6a35a-148">Существующую таблицу невозможно изменить, преобразовав ее в таблицу FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-148">You cannot alter an existing table to convert it into a FileTable.</span></span>  
  
-   <span data-ttu-id="6a35a-149">Родительский каталог, предварительно указанный на уровне базы данных, должен иметь значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="6a35a-149">The parent directory previously specified at the database level must have a non-null value.</span></span> <span data-ttu-id="6a35a-150">Сведения об указании каталогов на уровне базы данных см. в разделе [Включение необходимых компонентов для таблицы FileTable](enable-the-prerequisites-for-filetable.md).</span><span class="sxs-lookup"><span data-stu-id="6a35a-150">For information about specifying the database-level directory, see [Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md).</span></span>  
  
-   <span data-ttu-id="6a35a-151">Поскольку таблица FileTable содержит столбец FILESTREAM, требуется действующая файловая группа FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="6a35a-151">A FileTable requires a valid FILESTREAM filegroup, since a FileTable contains a FILESTREAM column.</span></span> <span data-ttu-id="6a35a-152">При необходимости можно указать действующую файловую группу FILESTREAM в команде **CREATE TABLE** для создания таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-152">You can optionally specify a valid FILESTREAM filegroup as part of the **CREATE TABLE** command for creating a FileTable.</span></span> <span data-ttu-id="6a35a-153">Если файловая группа не указана, то таблица FileTable использует файловую группу FILESTREAM по умолчанию для базы данных.</span><span class="sxs-lookup"><span data-stu-id="6a35a-153">If you do not specify a filegroup, then the FileTable uses the default FILESTREAM filegroup for the database.</span></span> <span data-ttu-id="6a35a-154">Если база данных не содержит файловую группу FILESTREAM, то возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="6a35a-154">If the database does not have a FILESTREAM filegroup, then an error is raised.</span></span>  
  
-   <span data-ttu-id="6a35a-155">Невозможно создать ограничение таблицы в составе инструкции **CREATE TABLE…AS FILETABLE**.</span><span class="sxs-lookup"><span data-stu-id="6a35a-155">You cannot create a table constraint as part of a **CREATE TABLE...AS FILETABLE** statement.</span></span> <span data-ttu-id="6a35a-156">Однако можно добавить ограничение позже с помощью инструкции **ALTER TABLE** .</span><span class="sxs-lookup"><span data-stu-id="6a35a-156">However you can add the constraint later by using an **ALTER TABLE** statement.</span></span>  
  
-   <span data-ttu-id="6a35a-157">Невозможно создать FileTable в базе данных **tempdb** или любой другой системной базе данных.</span><span class="sxs-lookup"><span data-stu-id="6a35a-157">You cannot create a FileTable in the **tempdb** database or in any of the other system databases.</span></span>  
  
-   <span data-ttu-id="6a35a-158">Невозможно создать таблицу FileTable как временную таблицу.</span><span class="sxs-lookup"><span data-stu-id="6a35a-158">You cannot create a FileTable as a temporary table.</span></span>  
  
##  <a name="altering-a-filetable"></a><a name="BasicsAlter"></a> <span data-ttu-id="6a35a-159">изменение таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="6a35a-159">Altering a FileTable</span></span>  
 <span data-ttu-id="6a35a-160">Поскольку FileTable имеет предопределенную и фиксированную схему, добавлять и изменять столбцы в ней нельзя.</span><span class="sxs-lookup"><span data-stu-id="6a35a-160">Since a FileTable has a pre-defined and fixed schema, you cannot add or change its columns.</span></span> <span data-ttu-id="6a35a-161">Тем не менее в таблицу FileTable можно добавлять пользовательские индексы, триггеры, ограничения и другие параметры.</span><span class="sxs-lookup"><span data-stu-id="6a35a-161">However, you can add custom indexes, triggers, constraints, and other options to a FileTable.</span></span>  
  
 <span data-ttu-id="6a35a-162">Сведения об использовании инструкции ALTER TABLE для включения или отключения пространства имен FileTable, включая системные ограничения, см. в разделе [Управление объектами FileTable](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="6a35a-162">For information about using the ALTER TABLE statement to enable or disable the FileTable namespace, including the system-defined constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-change-the-directory-for-a-filetable"></a><a name="HowToChange"></a> <span data-ttu-id="6a35a-163">Как изменить каталог для таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="6a35a-163">How To: Change the Directory for a FileTable</span></span>  
 <span data-ttu-id="6a35a-164">**Изменение каталога для таблицы FileTable с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="6a35a-164">**Change the Directory for a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="6a35a-165">Вызовите инструкцию ALTER TABLE и задайте новое допустимое значение параметра **FILETABLE_DIRECTORY** SET.</span><span class="sxs-lookup"><span data-stu-id="6a35a-165">Call the ALTER TABLE statement and provide a valid new value for the **FILETABLE_DIRECTORY** SET option.</span></span>  
  
 <span data-ttu-id="6a35a-166">**Пример**</span><span class="sxs-lookup"><span data-stu-id="6a35a-166">**Example**</span></span>  
  
```sql  
ALTER TABLE filetable_name  
    SET ( FILETABLE_DIRECTORY = N'directory_name' );  
GO  
```  
  
 <span data-ttu-id="6a35a-167">**Изменение каталога для таблицы FileTable с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="6a35a-167">**Change the Directory for a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="6a35a-168">Щелкните правой кнопкой мыши таблицу FileTable в обозревателе объектов и выберите пункт **Свойства** , чтобы открыть диалоговое окно **Свойства таблицы** .</span><span class="sxs-lookup"><span data-stu-id="6a35a-168">In Object Explorer, right-click on the FileTable and select **Properties** to open the **Table Properties** dialog box.</span></span> <span data-ttu-id="6a35a-169">На странице **FileTable** введите новое значение для свойства **Имя каталога FileTable**.</span><span class="sxs-lookup"><span data-stu-id="6a35a-169">On the **FileTable** page, enter a new value for **FileTable directory name**.</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-a-filetable"></a><a name="ReqAlter"></a> <span data-ttu-id="6a35a-170">Требования и ограничения для изменения FileTable</span><span class="sxs-lookup"><span data-stu-id="6a35a-170">Requirements and Restrictions for Altering a FileTable</span></span>  
  
-   <span data-ttu-id="6a35a-171">Изменить значение **FILETABLE_COLLATE_FILENAME**невозможно.</span><span class="sxs-lookup"><span data-stu-id="6a35a-171">You cannot alter the value of **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
-   <span data-ttu-id="6a35a-172">Нельзя изменить, удалить или отключить системные столбцы в таблице FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-172">You cannot change, drop, or disable the system-defined columns of a FileTable.</span></span>  
  
-   <span data-ttu-id="6a35a-173">Нельзя добавлять новые пользовательские столбцы, вычисляемые или материализованные вычисляемые столбцы в таблицу FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-173">You cannot add new user columns, computed columns, or persisted computed columns to a FileTable.</span></span>  
  
##  <a name="dropping-a-filetable"></a><a name="BasicsDrop"></a> <span data-ttu-id="6a35a-174">удаление таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="6a35a-174">Dropping a FileTable</span></span>  
 <span data-ttu-id="6a35a-175">Таблицу FileTable можно удалить с помощью обычного синтаксиса инструкции [DROP TABLE (Transact-SQL)](/sql/t-sql/statements/drop-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6a35a-175">You can drop a FileTable by using the ordinary syntax for the [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="6a35a-176">При удалении таблицы FileTable также удаляются следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="6a35a-176">When you drop a FileTable, the following objects are also dropped:</span></span>  
  
-   <span data-ttu-id="6a35a-177">Все столбцы и объекты, связанные с таблицей, например индексы, ограничения и триггеры также удаляются.</span><span class="sxs-lookup"><span data-stu-id="6a35a-177">All the columns of the FileTable and all the objects associated with the table, such as indexes, constraints, and triggers, are also dropped.</span></span>  
  
-   <span data-ttu-id="6a35a-178">Каталог таблицы FileTable и вложенные каталоги удаляются из файла FILESTREAM и иерархии каталогов базы данных.</span><span class="sxs-lookup"><span data-stu-id="6a35a-178">The FileTable directory and the sub-directories that it contained disappear from the FILESTREAM file and directory hierarchy of the database.</span></span>  
  
 <span data-ttu-id="6a35a-179">Команда DROP TABLE завершается ошибкой, если в пространстве имен файлов FileTable имеются открытые дескрипторы файлов.</span><span class="sxs-lookup"><span data-stu-id="6a35a-179">The DROP TABLE command fails if there are open file handles in the FileTable's file namespace.</span></span> <span data-ttu-id="6a35a-180">Сведения о закрытии открытых дескрипторов см. в разделе [Управление объектами FileTable](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="6a35a-180">For information about closing open handles, see [Manage FileTables](manage-filetables.md).</span></span>  
  
##  <a name="other-database-objects-are-created-when-you-create-a-filetable"></a><a name="BasicsOtherObjects"></a> <span data-ttu-id="6a35a-181">другие объекты базы данных, создаваемые при создании таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="6a35a-181">Other Database Objects Are Created When You Create a FileTable</span></span>  
 <span data-ttu-id="6a35a-182">При создании новой таблицы FileTable также создаются некоторые системные индексы и ограничения.</span><span class="sxs-lookup"><span data-stu-id="6a35a-182">When you create a new FileTable, some system-defined indexes and constraints are also created.</span></span> <span data-ttu-id="6a35a-183">Эти объекты нельзя изменять или удалять, они исчезают только после удаления самой таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="6a35a-183">You cannot alter or drop these objects; they disappear only when the FileTable itself is dropped.</span></span> <span data-ttu-id="6a35a-184">Чтобы просмотреть список этих объектов, отправьте запрос представлению каталога [sys.filetable_system_defined_objects (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6a35a-184">To see the list of these objects, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
--View all objects for all filetables, unsorted  
SELECT * FROM sys.filetable_system_defined_objects;  
GO  
  
--View sorted list with friendly names  
SELECT OBJECT_NAME(parent_object_id) AS 'FileTable', OBJECT_NAME(object_id) AS 'System-defined Object'  
    FROM sys.filetable_system_defined_objects  
    ORDER BY FileTable, 'System-defined Object';  
GO  
```  
  
 <span data-ttu-id="6a35a-185">**Индексы, которые создаются при создании новой таблицы FileTable**</span><span class="sxs-lookup"><span data-stu-id="6a35a-185">**Indexes that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="6a35a-186">При создании новой таблицы FileTable также создаются следующие системные индексы.</span><span class="sxs-lookup"><span data-stu-id="6a35a-186">When you create a new FileTable, the following system-defined indexes are also created:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a35a-187">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="6a35a-187">**Columns**</span></span>|<span data-ttu-id="6a35a-188">**Тип индекса**</span><span class="sxs-lookup"><span data-stu-id="6a35a-188">**Index type**</span></span>|  
|<span data-ttu-id="6a35a-189">[path_locator] ASC</span><span class="sxs-lookup"><span data-stu-id="6a35a-189">[path_locator] ASC</span></span>|<span data-ttu-id="6a35a-190">Первичный ключ, некластеризованный</span><span class="sxs-lookup"><span data-stu-id="6a35a-190">Primary Key, nonclustered</span></span>|  
|<span data-ttu-id="6a35a-191">[parent_path_locator] ASC,</span><span class="sxs-lookup"><span data-stu-id="6a35a-191">[parent_path_locator] ASC,</span></span><br /><br /> <span data-ttu-id="6a35a-192">[name] ASC</span><span class="sxs-lookup"><span data-stu-id="6a35a-192">[name] ASC</span></span>|<span data-ttu-id="6a35a-193">Уникальный, некластеризованный</span><span class="sxs-lookup"><span data-stu-id="6a35a-193">Unique, nonclustered</span></span>|  
|<span data-ttu-id="6a35a-194">[stream_id] ASC</span><span class="sxs-lookup"><span data-stu-id="6a35a-194">[stream_id] ASC</span></span>|<span data-ttu-id="6a35a-195">Уникальный, некластеризованный</span><span class="sxs-lookup"><span data-stu-id="6a35a-195">Unique, nonclustered</span></span>|  
  
 <span data-ttu-id="6a35a-196">**Ограничения, которые создаются при создании новой таблицы FileTable**</span><span class="sxs-lookup"><span data-stu-id="6a35a-196">**Constraints that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="6a35a-197">При создании новой таблицы FileTable также создаются следующие системные ограничения.</span><span class="sxs-lookup"><span data-stu-id="6a35a-197">When you create a new FileTable, the following system-defined constraints are also created:</span></span>  
  
|<span data-ttu-id="6a35a-198">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6a35a-198">Constraints</span></span>|<span data-ttu-id="6a35a-199">Принудительно применяет</span><span class="sxs-lookup"><span data-stu-id="6a35a-199">Enforces</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="6a35a-200">Ограничения по умолчанию для следующих столбцов:</span><span class="sxs-lookup"><span data-stu-id="6a35a-200">Default constraints on the following columns:</span></span><br /><br /> <span data-ttu-id="6a35a-201">**creation_time**</span><span class="sxs-lookup"><span data-stu-id="6a35a-201">**creation_time**</span></span> <br /> <span data-ttu-id="6a35a-202">**is_archive**</span><span class="sxs-lookup"><span data-stu-id="6a35a-202">**is_archive**</span></span> <br /> <span data-ttu-id="6a35a-203">**is_directory**</span><span class="sxs-lookup"><span data-stu-id="6a35a-203">**is_directory**</span></span> <br /> <span data-ttu-id="6a35a-204">**is_hidden**</span><span class="sxs-lookup"><span data-stu-id="6a35a-204">**is_hidden**</span></span> <br /> <span data-ttu-id="6a35a-205">**is_offline**</span><span class="sxs-lookup"><span data-stu-id="6a35a-205">**is_offline**</span></span> <br /> <span data-ttu-id="6a35a-206">**is_readonly**</span><span class="sxs-lookup"><span data-stu-id="6a35a-206">**is_readonly**</span></span> <br /> <span data-ttu-id="6a35a-207">**is_system**</span><span class="sxs-lookup"><span data-stu-id="6a35a-207">**is_system**</span></span> <br /> <span data-ttu-id="6a35a-208">**is_temporary**</span><span class="sxs-lookup"><span data-stu-id="6a35a-208">**is_temporary**</span></span> <br /> <span data-ttu-id="6a35a-209">**last_access_time**</span><span class="sxs-lookup"><span data-stu-id="6a35a-209">**last_access_time**</span></span> <br /> <span data-ttu-id="6a35a-210">**last_write_time**</span><span class="sxs-lookup"><span data-stu-id="6a35a-210">**last_write_time**</span></span> <br /> <span data-ttu-id="6a35a-211">**path_locator**</span><span class="sxs-lookup"><span data-stu-id="6a35a-211">**path_locator**</span></span> <br /> <span data-ttu-id="6a35a-212">**stream_id**</span><span class="sxs-lookup"><span data-stu-id="6a35a-212">**stream_id**</span></span>|<span data-ttu-id="6a35a-213">Системные ограничения по умолчанию используют значения по умолчанию для указанных столбцов.</span><span class="sxs-lookup"><span data-stu-id="6a35a-213">The system-defined default constraints enforce default values for the specified columns.</span></span>|  
|<span data-ttu-id="6a35a-214">Проверочные ограничения</span><span class="sxs-lookup"><span data-stu-id="6a35a-214">Check constraints</span></span>|<span data-ttu-id="6a35a-215">Системные проверочные ограничения обеспечивают следующие требования.</span><span class="sxs-lookup"><span data-stu-id="6a35a-215">The system-defined check constraints enforce the following requirements:</span></span><br /><br /> <span data-ttu-id="6a35a-216">Допустимые имена файлов.</span><span class="sxs-lookup"><span data-stu-id="6a35a-216">Valid filenames.</span></span><br /><br /> <span data-ttu-id="6a35a-217">Допустимые атрибуты файлов.</span><span class="sxs-lookup"><span data-stu-id="6a35a-217">Valid file attributes.</span></span><br /><br /> <span data-ttu-id="6a35a-218">Родительский объект должен быть каталогом.</span><span class="sxs-lookup"><span data-stu-id="6a35a-218">Parent object must be a directory.</span></span><br /><br /> <span data-ttu-id="6a35a-219">При обработке файла иерархия пространств имен заблокирована.</span><span class="sxs-lookup"><span data-stu-id="6a35a-219">Namespace hierarchy is locked during file manipulation.</span></span>|  
  
 <span data-ttu-id="6a35a-220">**Соглашение об именах для системных ограничений**</span><span class="sxs-lookup"><span data-stu-id="6a35a-220">**Naming convention for the system-defined constraints**</span></span>  
 <span data-ttu-id="6a35a-221">Системные ограничения, описанные выше, должны именоваться в формате **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** , где:</span><span class="sxs-lookup"><span data-stu-id="6a35a-221">The system-defined constraints described above are named in the format **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** where:</span></span>  
  
-   <span data-ttu-id="6a35a-222">*<тип_ограничения>* может быть равен CK (проверочное ограничение), DF (ограничение по умолчанию), FK (внешний ключ), PK (первичный ключ) или UQ (ограничение уникальности).</span><span class="sxs-lookup"><span data-stu-id="6a35a-222">*<constraint_type>* is CK (check constraint), DF (default constraint), FK (foreign key), PK (primary key), or UQ (unique constraint).</span></span>  
  
-   <span data-ttu-id="6a35a-223">*\<uniquifier>*  — это формируемая системой строка, уникальным образом идентифицирующая ограничение.</span><span class="sxs-lookup"><span data-stu-id="6a35a-223">*\<uniquifier>* is a system-generated string to make the name unique.</span></span> <span data-ttu-id="6a35a-224">Эта строка может содержать имя таблицы FileTable и уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="6a35a-224">This string may contain the FileTable name and a unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a35a-225">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a35a-225">See Also</span></span>  
 [<span data-ttu-id="6a35a-226">Управление таблицами FileTable</span><span class="sxs-lookup"><span data-stu-id="6a35a-226">Manage FileTables</span></span>](manage-filetables.md)  
  
  
