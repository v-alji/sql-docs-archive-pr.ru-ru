---
title: Работа с каталогами и путями в таблицах FileTable | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], directories
ms.assetid: f1e45900-bea0-4f6f-924e-c11e1f98ab62
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4641159e894b764cbee4d7f02085f3ceb8e6d87d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728350"
---
# <a name="work-with-directories-and-paths-in-filetables"></a><span data-ttu-id="fb05f-102">Работа с каталогами и путями в таблицах FileTable</span><span class="sxs-lookup"><span data-stu-id="fb05f-102">Work with Directories and Paths in FileTables</span></span>
  <span data-ttu-id="fb05f-103">Описывает структуру каталогов, в которой файлы хранятся в таблицах FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb05f-103">Describes the directory structure in which the files are stored in FileTables.</span></span>  
  
##  <a name="how-to-work-with-directories-and-paths-in-filetables"></a><a name="HowToDirectories"></a> <span data-ttu-id="fb05f-104">Как Работа с каталогами и путями в таблицах FileTable</span><span class="sxs-lookup"><span data-stu-id="fb05f-104">How To: Work with Directories and Paths in FileTables</span></span>  
 <span data-ttu-id="fb05f-105">Следующие 3 функции можно использовать для работы с каталогами FileTable в [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fb05f-105">You can use the following 3 functions to work with FileTable directories in [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
|<span data-ttu-id="fb05f-106">Чтобы получить этот результат, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="fb05f-106">To get this result</span></span>|<span data-ttu-id="fb05f-107">Воспользуйтесь этой функцией</span><span class="sxs-lookup"><span data-stu-id="fb05f-107">Use this function</span></span>|  
|------------------------|-----------------------|  
|<span data-ttu-id="fb05f-108">Получите корневой путь UNC для конкретной таблицы FileTable или для текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="fb05f-108">Get the root-level UNC path for a specific FileTable or for the current database.</span></span>|[<span data-ttu-id="fb05f-109">FileTableRootPath (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb05f-109">FileTableRootPath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/filetablerootpath-transact-sql)|  
|<span data-ttu-id="fb05f-110">Получите абсолютный или относительный путь UNC к файлу или каталогу в таблице FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb05f-110">Get an absolute or relative UNC path for a file or directory in a FileTable.</span></span>|[<span data-ttu-id="fb05f-111">GetFileNamespacePath (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb05f-111">GetFileNamespacePath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)|  
|<span data-ttu-id="fb05f-112">Получите значение идентификатора path_locator для заданного файла или каталога в таблице FileTable, указав путь к нему.</span><span class="sxs-lookup"><span data-stu-id="fb05f-112">Get the path locator ID value for the specified file or directory in a FileTable, by providing the path.</span></span>|[<span data-ttu-id="fb05f-113">GetPathLocator (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb05f-113">GetPathLocator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getpathlocator-transact-sql)|  
  
##  <a name="how-to-use-relative-paths-for-portable-code"></a><a name="BestPracticeRelativePaths"></a> <span data-ttu-id="fb05f-114">Как Как использовать относительные пути для переносимого кода</span><span class="sxs-lookup"><span data-stu-id="fb05f-114">How to: Use Relative Paths for Portable Code</span></span>  
 <span data-ttu-id="fb05f-115">Чтобы код и приложения были независимы от текущего компьютера и базы данных, следует избегать создания кода с использованием абсолютных путей.</span><span class="sxs-lookup"><span data-stu-id="fb05f-115">To keep code and applications independent of the current computer and database, avoid writing code that relies on absolute file paths.</span></span> <span data-ttu-id="fb05f-116">Вместо этого рекомендуется получать полный путь к файлу во время выполнения с помощью функций [FileTableRootPath (Transact-SQL)](/sql/relational-databases/system-functions/filetablerootpath-transact-sql) и [GetFileNamespacePath (Transact-SQL)](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql), как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="fb05f-116">Instead, get the complete path for a file at run time by using the [FileTableRootPath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filetablerootpath-transact-sql) and [GetFileNamespacePath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)) functions together, as shown in the following example.</span></span> <span data-ttu-id="fb05f-117">По умолчанию функция `GetFileNamespacePath` возвращает относительный путь к файлу, находящемуся внутри корневого пути к базе данных.</span><span class="sxs-lookup"><span data-stu-id="fb05f-117">By default, the `GetFileNamespacePath` function returns the relative path of the file under the root path for the database.</span></span>  
  
```sql  
USE database_name;  
DECLARE @root nvarchar(100);  
DECLARE @fullpath nvarchar(1000);  
  
SELECT @root = FileTableRootPath();  
SELECT @fullpath = @root + file_stream.GetFileNamespacePath()  
    FROM filetable_name  
    WHERE name = N'document_name';  
  
PRINT @fullpath;  
GO  
```  
  
##  <a name="important-restrictions"></a><a name="restrictions"></a> <span data-ttu-id="fb05f-118">Важные ограничения</span><span class="sxs-lookup"><span data-stu-id="fb05f-118">Important restrictions</span></span>  
  
###  <a name="nesting-level"></a><a name="nesting"></a> <span data-ttu-id="fb05f-119">Уровень вложенности</span><span class="sxs-lookup"><span data-stu-id="fb05f-119">Nesting level</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb05f-120">Нельзя хранить более 15 уровней вложенных каталогов в каталоге FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb05f-120">You cannot store more than 15 levels of subdirectories in the FileTable directory.</span></span> <span data-ttu-id="fb05f-121">Если сохранено 15 уровней вложенных каталогов, каталог самого нижнего уровня не сможет содержать файлы, так как эти файлы представляют собой дополнительный уровень.</span><span class="sxs-lookup"><span data-stu-id="fb05f-121">When you store 15 levels of subdirectories, then the lowest level cannot contain files, since these files would represent an additional level.</span></span>  
  
###  <a name="length-of-full-path-name"></a><a name="fqnlength"></a> <span data-ttu-id="fb05f-122">Длина полного имени</span><span class="sxs-lookup"><span data-stu-id="fb05f-122">Length of full path name</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fb05f-123">Файловая система NTFS поддерживает пути, намного превышающие ограничение в 260 символов, установленное в оболочке Windows и большинстве других функций Windows API.</span><span class="sxs-lookup"><span data-stu-id="fb05f-123">The NTFS file system supports path names that are much longer than the 260-character limit of the Windows shell and most Windows APIs.</span></span> <span data-ttu-id="fb05f-124">Поэтому можно создавать файлы в файловой иерархии FileTable с помощью Transact-SQL, которые нельзя будет просмотреть или открыть в Проводнике Windows и многих других приложениях Windows, поскольку полный путь превышает 260 символов.</span><span class="sxs-lookup"><span data-stu-id="fb05f-124">Therefore it is possible to create files in the file hierarchy of a FileTable by using Transact-SQL that you cannot view or open with Windows Explorer or many other Windows applications, because the full path name exceeds 260 characters.</span></span> <span data-ttu-id="fb05f-125">Однако с этими файлами вы можете продолжать работать с помощью инструкций Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="fb05f-125">However you can continue to access these files by using Transact-SQL.</span></span>  
  
##  <a name="the-full-path-to-an-item-stored-in-a-filetable"></a><a name="fullpath"></a> <span data-ttu-id="fb05f-126">Полный путь к элементу, хранящемуся в таблице FileTable</span><span class="sxs-lookup"><span data-stu-id="fb05f-126">The full path to an item stored in a FileTable</span></span>  
 <span data-ttu-id="fb05f-127">Полный путь к файлу или каталогу, сохраненный в таблице FileTable, начинается со следующих элементов.</span><span class="sxs-lookup"><span data-stu-id="fb05f-127">The full path to a file or directory stored in a FileTable begins with the following elements:</span></span>  
  
1.  <span data-ttu-id="fb05f-128">Общий ресурс с поддержкой доступа файлового ввода-вывода к данным FILESTREAM на уровне экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb05f-128">The share enabled for FILESTREAM file I/O access at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level.</span></span>  
  
2.  <span data-ttu-id="fb05f-129">Имя **DIRECTORY_NAME** на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="fb05f-129">The **DIRECTORY_NAME** specified at the database level.</span></span>  
  
3.  <span data-ttu-id="fb05f-130">**FILETABLE_DIRECTORY** на уровне таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb05f-130">The **FILETABLE_DIRECTORY** specified at the FileTable level.</span></span>  
  
 <span data-ttu-id="fb05f-131">В итоге иерархия выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fb05f-131">The resulting hierarchy looks like this:</span></span>  
  
 `\\<machine>\<instance-level FILESTREAM share>\<database-level directory>\<FileTable directory>\`  
  
 <span data-ttu-id="fb05f-132">Данная иерархия каталогов образует корень пространства имен файлов FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb05f-132">This directory hierarchy forms the root of the FileTable's file namespace.</span></span> <span data-ttu-id="fb05f-133">В этой иерархии каталогов данные FILESTREAM для FileTable хранятся в виде файлов и в виде вложенных каталогов, которые также могут содержать файлы и вложенные каталоги.</span><span class="sxs-lookup"><span data-stu-id="fb05f-133">Under this directory hierarchy, the FILESTREAM data for the FileTable is stored as files, and as subdirectories which can also contain files and subdirectories.</span></span>  
  
 <span data-ttu-id="fb05f-134">Важно иметь в виду, что иерархия каталогов, созданная в общем ресурсе FILESTREAM на уровне экземпляра, является виртуальной иерархией каталогов.</span><span class="sxs-lookup"><span data-stu-id="fb05f-134">It is important to keep in mind that the directory hierarchy created under the instance-level FILESTREAM share is a virtual directory hierarchy.</span></span> <span data-ttu-id="fb05f-135">Иерархия хранится в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и не представлена физически в файловой системе NTFS.</span><span class="sxs-lookup"><span data-stu-id="fb05f-135">This hierarchy is stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and is not represented physically in the NTFS file system.</span></span> <span data-ttu-id="fb05f-136">Все операции, осуществляющие доступ к файлам и каталогам в общем ресурсе FILESTREAM в таблицах FileTable, перехватываются и обрабатываются компонентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , внедренным в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="fb05f-136">All operations that access files and directories under the FILESTREAM share and in the FileTables that it contains are intercepted and handled by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component embedded in the file system.</span></span>  
  
##  <a name="the-semantics-of-the-root-directories-at-the-instance-database-and-filetable-levels"></a><a name="roots"></a> <span data-ttu-id="fb05f-137">Семантика корневых каталогов на уровне экземпляра, базы данных и таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="fb05f-137">The semantics of the root directories at the instance, database, and FileTable levels</span></span>  
 <span data-ttu-id="fb05f-138">Эта иерархия каталогов имеет следующую семантику.</span><span class="sxs-lookup"><span data-stu-id="fb05f-138">This directory hierarchy observes the following semantics:</span></span>  
  
-   <span data-ttu-id="fb05f-139">Общий ресурс FILESTREAM на уровне экземпляра настраивается администратором и хранится в виде свойства сервера.</span><span class="sxs-lookup"><span data-stu-id="fb05f-139">The instance-level FILESTREAM share is configured by an administrator and stored as a property of the server.</span></span> <span data-ttu-id="fb05f-140">Этот общий ресурс можно переименовать с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb05f-140">You can rename this share by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="fb05f-141">Операция переименования вступает в силу только после перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="fb05f-141">A renaming operation does not take effect until the server is restarted.</span></span>  
  
-   <span data-ttu-id="fb05f-142">Параметр **DIRECTORY_NAME** уровня базы данных при создании базы данных по умолчанию имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="fb05f-142">The database-level **DIRECTORY_NAME** is null by default when you create a new database.</span></span> <span data-ttu-id="fb05f-143">Администратор может задать или изменить это имя с помощью инструкции **ALTER DATABASE** .</span><span class="sxs-lookup"><span data-stu-id="fb05f-143">An administrator can set or change this name by using the **ALTER DATABASE** statement.</span></span> <span data-ttu-id="fb05f-144">Это имя должно быть уникальным (при сравнении без учета регистра) в этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="fb05f-144">The name must be unique (in a case-insensitive comparison) in that instance.</span></span>  
  
-   <span data-ttu-id="fb05f-145">Обычно имя **FILETABLE_DIRECTORY** указывается в составе инструкции **CREATE TABLE** при создании таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb05f-145">You typically provide the **FILETABLE_DIRECTORY** name as part of the **CREATE TABLE** statement when you create a FileTable.</span></span> <span data-ttu-id="fb05f-146">Это имя можно изменить с помощью команды **ALTER TABLE** .</span><span class="sxs-lookup"><span data-stu-id="fb05f-146">You can change this name by using the **ALTER TABLE** command.</span></span>  
  
-   <span data-ttu-id="fb05f-147">Эти корневые каталоги нельзя переименовать с помощью операций файлового ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="fb05f-147">You cannot rename these root directories through file I/O operations.</span></span>  
  
-   <span data-ttu-id="fb05f-148">Эти корневые каталоги нельзя открыть с использованием дескрипторов файлов для монопольного доступа.</span><span class="sxs-lookup"><span data-stu-id="fb05f-148">You cannot open these root directories with exclusive file handles.</span></span>  
  
##  <a name="the-is_directory-column-in-the-filetable-schema"></a><a name="is_directory"></a> <span data-ttu-id="fb05f-149">Столбец is_directory в схеме FileTable</span><span class="sxs-lookup"><span data-stu-id="fb05f-149">The is_directory column in the FileTable schema</span></span>  
 <span data-ttu-id="fb05f-150">В приведенной ниже таблице описывается взаимодействие между столбцом **is_directory** и столбцом **file_stream** , в котором находятся данные FILESTREAM в таблице FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb05f-150">The following table describes the interaction between the **is_directory** column and the **file_stream** column that contains the FILESTREAM data in a FileTable.</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="fb05f-151">*is_directory* **значение**</span><span class="sxs-lookup"><span data-stu-id="fb05f-151">*is_directory* **value**</span></span>|<span data-ttu-id="fb05f-152">*file_stream* **значение**</span><span class="sxs-lookup"><span data-stu-id="fb05f-152">*file_stream* **value**</span></span>|<span data-ttu-id="fb05f-153">**Поведение**</span><span class="sxs-lookup"><span data-stu-id="fb05f-153">**Behavior**</span></span>|  
|<span data-ttu-id="fb05f-154">FALSE</span><span class="sxs-lookup"><span data-stu-id="fb05f-154">FALSE</span></span>|<span data-ttu-id="fb05f-155">NULL</span><span class="sxs-lookup"><span data-stu-id="fb05f-155">NULL</span></span>|<span data-ttu-id="fb05f-156">Это недопустимое сочетание, которое будет перехвачено системным ограничением.</span><span class="sxs-lookup"><span data-stu-id="fb05f-156">This is an invalid combination that will be caught by a system-defined constraint.</span></span>|  
|<span data-ttu-id="fb05f-157">FALSE</span><span class="sxs-lookup"><span data-stu-id="fb05f-157">FALSE</span></span>|\<value>|<span data-ttu-id="fb05f-158">Этот элемент представляет файл.</span><span class="sxs-lookup"><span data-stu-id="fb05f-158">The item represents a file.</span></span>|  
|<span data-ttu-id="fb05f-159">TRUE</span><span class="sxs-lookup"><span data-stu-id="fb05f-159">TRUE</span></span>|<span data-ttu-id="fb05f-160">NULL</span><span class="sxs-lookup"><span data-stu-id="fb05f-160">NULL</span></span>|<span data-ttu-id="fb05f-161">Этот элемент представляет каталог.</span><span class="sxs-lookup"><span data-stu-id="fb05f-161">The item represents a directory.</span></span>|  
|<span data-ttu-id="fb05f-162">TRUE</span><span class="sxs-lookup"><span data-stu-id="fb05f-162">TRUE</span></span>|\<value>|<span data-ttu-id="fb05f-163">Это недопустимое сочетание, которое будет перехвачено системным ограничением.</span><span class="sxs-lookup"><span data-stu-id="fb05f-163">This is an invalid combination that will be caught by a system-defined constraint.</span></span>|  
  
##  <a name="using-virtual-network-names-vnns-with-alwayson-availability-groups"></a><a name="alwayson"></a> <span data-ttu-id="fb05f-164">Использование имен виртуальной сети для групп доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="fb05f-164">Using Virtual Network Names (VNNs) with AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="fb05f-165">Если база данных, содержащая данные FILESTREAM или FileTable, принадлежит группе доступности:</span><span class="sxs-lookup"><span data-stu-id="fb05f-165">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="fb05f-166">Функции FILESTREAM и FileTable принимают или возвращают имена виртуальной сети, а не имена компьютеров.</span><span class="sxs-lookup"><span data-stu-id="fb05f-166">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="fb05f-167">Дополнительные сведения об этих функциях см. в разделе [Функции Filestream и FileTable (Transact-SQL)](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fb05f-167">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="fb05f-168">При осуществлении любого доступа к данным FILESTREAM или FileTable посредством API-интерфейса файловой системы будут использоваться имена виртуальной сети, а не имена компьютеров.</span><span class="sxs-lookup"><span data-stu-id="fb05f-168">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span> <span data-ttu-id="fb05f-169">Дополнительные сведения см. в разделе [FILESTREAM и FileTable с группами доступности AlwaysOn (SQL Server)](../../database-engine/availability-groups/windows/filestream-and-filetable-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fb05f-169">For more information, see [FILESTREAM and FileTable with AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/filestream-and-filetable-with-always-on-availability-groups-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb05f-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb05f-170">See Also</span></span>  
 <span data-ttu-id="fb05f-171">[Включение необходимых компонентов для таблицы FileTable](enable-the-prerequisites-for-filetable.md) </span><span class="sxs-lookup"><span data-stu-id="fb05f-171">[Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md) </span></span>  
 <span data-ttu-id="fb05f-172">[Создание, изменение и удаление таблиц FileTables](create-alter-and-drop-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="fb05f-172">[Create, Alter, and Drop FileTables](create-alter-and-drop-filetables.md) </span></span>  
 <span data-ttu-id="fb05f-173">[Доступ к таблицам FileTable с помощью Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="fb05f-173">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="fb05f-174">Доступ к таблицам FileTable с помощью API-интерфейсов ввода-вывода файлов</span><span class="sxs-lookup"><span data-stu-id="fb05f-174">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
