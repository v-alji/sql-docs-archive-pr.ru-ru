---
title: выполнить загрузку файлов в таблицу FileTables | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], migrating files
- FileTables [SQL Server], bulk loading
- FileTables [SQL Server], loading files
ms.assetid: dc842a10-0586-4b0f-9775-5ca0ecc761d9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 43ea31523da2dfa8b387f68ce4f7c7f07868dd6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740058"
---
# <a name="load-files-into-filetables"></a><span data-ttu-id="eee0a-102">выполнить загрузку файлов в таблицу FileTables</span><span class="sxs-lookup"><span data-stu-id="eee0a-102">Load Files into FileTables</span></span>
  <span data-ttu-id="eee0a-103">Описывает процедуру загрузки или переноса файлов в таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="eee0a-103">Describes how to load or migrate files into FileTables.</span></span>  
  
##  <a name="loading-or-migrating-files-into-a-filetable"></a><a name="BasicsLoadNew"></a> <span data-ttu-id="eee0a-104">загрузить или перенести файлы в таблицу FileTable</span><span class="sxs-lookup"><span data-stu-id="eee0a-104">Loading or Migrating Files into a FileTable</span></span>  
 <span data-ttu-id="eee0a-105">Выбор метода загрузки или переноса файлов в таблицу FileTable зависит от того, где хранятся файлы в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="eee0a-105">The method that you choose for loading or migrating files into a FileTable depends on where the files are currently stored.</span></span>  
  
|<span data-ttu-id="eee0a-106">Текущее местоположение файлов</span><span class="sxs-lookup"><span data-stu-id="eee0a-106">Current location of files</span></span>|<span data-ttu-id="eee0a-107">Параметры для переноса</span><span class="sxs-lookup"><span data-stu-id="eee0a-107">Options for migration</span></span>|  
|-------------------------------|---------------------------|  
|<span data-ttu-id="eee0a-108">Файлы в настоящее время хранятся в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="eee0a-108">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="eee0a-109">не имеет сведений о файлах.</span><span class="sxs-lookup"><span data-stu-id="eee0a-109">has no knowledge of the files.</span></span>|<span data-ttu-id="eee0a-110">Поскольку таблица FileTable в файловой системе Windows отображается в виде папки, можно легко загрузить файлы в новую таблицу FileTable любым из доступных способов перемещения или копирования файлов.</span><span class="sxs-lookup"><span data-stu-id="eee0a-110">Since a FileTable appears as a folder in the Windows file system, you can easily load files into a new FileTable by using any of the available methods for moving or copying files.</span></span> <span data-ttu-id="eee0a-111">Это может быть проводник Windows, программы командной строки, включая xcopy и robocopy, и пользовательские скрипты или приложения.</span><span class="sxs-lookup"><span data-stu-id="eee0a-111">These methods include Windows Explorer, command line options including xcopy and robocopy, and custom scripts or applications.</span></span><br /><br /> <span data-ttu-id="eee0a-112">Существующую папку невозможно преобразовать в таблицу FileTable.</span><span class="sxs-lookup"><span data-stu-id="eee0a-112">You cannot convert an existing folder to a FileTable.</span></span>|  
|<span data-ttu-id="eee0a-113">Файлы в настоящее время хранятся в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="eee0a-113">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="eee0a-114">содержит таблицу метаданных, в которой находятся указатели на файлы.</span><span class="sxs-lookup"><span data-stu-id="eee0a-114">contains a table of metadata that contains pointers to the files.</span></span>|<span data-ttu-id="eee0a-115">Сначала нужно переместить или скопировать файлы одним из способов, описанных выше.</span><span class="sxs-lookup"><span data-stu-id="eee0a-115">The first step is to move or copy the files by using one of the methods mentioned above.</span></span><br /><br /> <span data-ttu-id="eee0a-116">Затем нужно обновить существующую таблицу метаданных, чтобы они указывали на новое расположение файлов.</span><span class="sxs-lookup"><span data-stu-id="eee0a-116">The second step is to update the existing table of metadata to point to the new location of the files.</span></span><br /><br /> <span data-ttu-id="eee0a-117">Дополнительные сведения см. в подразделе [Пример. Перенос файлов из файловой системы в таблицу FileTable](#HowToMigrateFiles) этого раздела.</span><span class="sxs-lookup"><span data-stu-id="eee0a-117">For more information, see [Example: Migrating Files from the File System into a FileTable](#HowToMigrateFiles) in this topic.</span></span>|  
  
###  <a name="how-to-load-files-into-a-filetable"></a><a name="HowToLoadNew"></a> <span data-ttu-id="eee0a-118">Как выполнить загрузку файлов в таблицу FileTable</span><span class="sxs-lookup"><span data-stu-id="eee0a-118">How To: Load Files into a FileTable</span></span>  
 <span data-ttu-id="eee0a-119">Ниже перечислены методы, которые можно использовать для загрузки файлов в таблицу FileTable.</span><span class="sxs-lookup"><span data-stu-id="eee0a-119">The methods that you can use to load files into a FileTable include the following:</span></span>  
  
-   <span data-ttu-id="eee0a-120">Перетаскивание файлов из исходной папки в новую папку FileTable в проводнике Windows.</span><span class="sxs-lookup"><span data-stu-id="eee0a-120">Drag and drop files from the source folders to the new FileTable folder in Windows Explorer.</span></span>  
  
-   <span data-ttu-id="eee0a-121">Применение программ командной строки, таких как MOVE, COPY, XCOPY или ROBOCOPY из командной строки или пакетного файла или скрипта.</span><span class="sxs-lookup"><span data-stu-id="eee0a-121">Use command line options such as MOVE, COPY, XCOPY, or ROBOCOPY from the command prompt or in a batch file or script.</span></span>  
  
-   <span data-ttu-id="eee0a-122">Написание на C# или Visual Basic.NET пользовательского приложения для перемещения или копирования файлов с применением методов из пространства имен **System.IO** .</span><span class="sxs-lookup"><span data-stu-id="eee0a-122">Write a custom application in C# or Visual Basic.NET that uses methods from the **System.IO** namespace to move or copy the files.</span></span>  
  
###  <a name="example-migrating-files-from-the-file-system-into-a-filetable"></a><a name="HowToMigrateFiles"></a> <span data-ttu-id="eee0a-123">Пример. Перенос файлов из файловой системы в таблицу FileTable</span><span class="sxs-lookup"><span data-stu-id="eee0a-123">Example: Migrating Files from the File System into a FileTable</span></span>  
 <span data-ttu-id="eee0a-124">В этом сценарии файлы хранятся в файловой системе, а в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеется таблица метаданных, содержащая указатели на эти файлы.</span><span class="sxs-lookup"><span data-stu-id="eee0a-124">In this scenario, your files are stored in the file system, and you have a table of metadata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains pointers to the files.</span></span> <span data-ttu-id="eee0a-125">Необходимо переместить файлы в таблицу FileTable, затем заменить исходный путь UNC для каждого файла в метаданных на путь UNC таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="eee0a-125">You want to move the files into a FileTable, and then replace the original UNC path for each file in the metadata with the FileTable UNC path.</span></span> <span data-ttu-id="eee0a-126">Функция [GetPathLocator (Transact-SQL)](/sql/relational-databases/system-functions/getpathlocator-transact-sql) помогает добиться этой цели.</span><span class="sxs-lookup"><span data-stu-id="eee0a-126">The [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function helps you to achieve this goal.</span></span>  
  
 <span data-ttu-id="eee0a-127">В этом примере предположим, что существует таблица базы данных, `PhotoMetadata` содержащая данные о фотографиях.</span><span class="sxs-lookup"><span data-stu-id="eee0a-127">For this example, assume that there is an existing database table, `PhotoMetadata`, which contains data about photographs.</span></span> <span data-ttu-id="eee0a-128">В этой таблице также имеется столбец `UNCPath` типа `varchar`(512), содержащий фактический путь UNC к JPG-файлу.</span><span class="sxs-lookup"><span data-stu-id="eee0a-128">This table has a column `UNCPath` of type `varchar`(512) which contains the actual UNC path to a .jpg file.</span></span>  
  
 <span data-ttu-id="eee0a-129">Чтобы перенести файлы изображений из файловой системы в таблицу FileTable, нужно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="eee0a-129">To migrate the image files from the file system into a FileTable, you have to do the following:</span></span>  
  
1.  <span data-ttu-id="eee0a-130">Создайте новую таблицу FileTable для хранения файлов.</span><span class="sxs-lookup"><span data-stu-id="eee0a-130">Create a new FileTable to hold the files.</span></span> <span data-ttu-id="eee0a-131">В этом примере используется имя таблицы `dbo.PhotoTable`, но не показан код для создания самой таблицы.</span><span class="sxs-lookup"><span data-stu-id="eee0a-131">This example uses the table name, `dbo.PhotoTable`, but does not show the code to create the table.</span></span>  
  
2.  <span data-ttu-id="eee0a-132">Для копирования JPG-файлов с их структурой каталогов в корневой каталог таблицы FileTable можно использовать программу xcopy или аналогичное средство.</span><span class="sxs-lookup"><span data-stu-id="eee0a-132">Use xcopy or a similar tool to copy the .jpg files, with their directory structure, into the root directory of the FileTable.</span></span>  
  
3.  <span data-ttu-id="eee0a-133">Исправьте метаданные в таблице `PhotoMetadata` с помощью кода, похожего на следующий:</span><span class="sxs-lookup"><span data-stu-id="eee0a-133">Fix the metadata in the `PhotoMetadata` table, by using code similar to the following:</span></span>  
  
```sql  
--  Add a path locator column to the PhotoMetadata table.  
ALTER TABLE PhotoMetadata ADD pathlocator hierarchyid;  
  
-- Get the root path of the Photo directory on the File Server.  
DECLARE @UNCPathRoot varchar(100) = '\\RemoteShare\Photographs';  
  
-- Get the root path of the FileTable.  
DECLARE @FileTableRoot varchar(1000);  
SELECT @FileTableRoot = FileTableRootPath('dbo.PhotoTable');  
  
-- Update the PhotoMetadata table.  
  
-- Replace the File Server UNC path with the FileTable path.  
UPDATE PhotoMetadata  
    SET UNCPath = REPLACE(UNCPath, @UNCPathRoot, @FileTableRoot);  
  
-- Update the pathlocator column to contain the pathlocator IDs from the FileTable.  
UPDATE PhotoMetadata  
    SET pathlocator = GetPathLocator(UNCPath);  
```  
  
##  <a name="bulk-loading-files-into-a-filetable"></a><a name="BasicsBulkLoad"></a> <span data-ttu-id="eee0a-134">массовая загрузка файлов в таблицу FileTable</span><span class="sxs-lookup"><span data-stu-id="eee0a-134">Bulk Loading Files into a FileTable</span></span>  
 <span data-ttu-id="eee0a-135">FileTable ведет себя как обычный стол для массовых операций, со следующей квалификацией.</span><span class="sxs-lookup"><span data-stu-id="eee0a-135">A FileTable behaves like a normal table for bulk operations, with the following qualifications.</span></span>  
  
 <span data-ttu-id="eee0a-136">Таблица FileTable имеет системные ограничения, гарантирующие целостность пространства имен файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="eee0a-136">A FileTable has system-defined constraints which ensure that the integrity of the file and directory namespace is maintained.</span></span> <span data-ttu-id="eee0a-137">Эти ограничения должны быть проверены на массовых данных, загружаемых в FileTable.</span><span class="sxs-lookup"><span data-stu-id="eee0a-137">These constraints have to be verified on the data bulk loaded into the FileTable.</span></span> <span data-ttu-id="eee0a-138">Так как часть операций массовой вставки разрешает игнорировать табличные ограничения, следующие меры применяются принудительно.</span><span class="sxs-lookup"><span data-stu-id="eee0a-138">Since some bulk insert operations allow table constraints to be ignored, the following requirements are enforced.</span></span>  
  
-   <span data-ttu-id="eee0a-139">В настоящее время операции массовой загрузки в таблицу FileTable, принудительно применяющие ограничения, можно выполнять, как с любой другой таблицей.</span><span class="sxs-lookup"><span data-stu-id="eee0a-139">Bulk loading operations that enforce constraints can be run against a FileTable as against any other table.</span></span> <span data-ttu-id="eee0a-140">В эту категорию входят следующие операции:</span><span class="sxs-lookup"><span data-stu-id="eee0a-140">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="eee0a-141">bcp с предложением CHECK_CONSTRAINTS;</span><span class="sxs-lookup"><span data-stu-id="eee0a-141">bcp with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="eee0a-142">BULK INSERT с предложением CHECK_CONSTRAINTS;</span><span class="sxs-lookup"><span data-stu-id="eee0a-142">BULK INSERT with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="eee0a-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) без предложения IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="eee0a-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) without IGNORE_CONSTRAINTS clause.</span></span>  
  
-   <span data-ttu-id="eee0a-144">Операции массовой загрузки, не применяющие принудительно ограничения, завершаются неуспешно, если системные ограничения для таблицы FileTable не были отключены.</span><span class="sxs-lookup"><span data-stu-id="eee0a-144">Bulk loading operations that do not enforce constraints fail unless the FileTable system-defined constraints have been disabled.</span></span> <span data-ttu-id="eee0a-145">В эту категорию входят следующие операции:</span><span class="sxs-lookup"><span data-stu-id="eee0a-145">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="eee0a-146">bcp без предложения CHECK_CONSTRAINTS;</span><span class="sxs-lookup"><span data-stu-id="eee0a-146">bcp without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="eee0a-147">BULK INSERT без предложения CHECK_CONSTRAINTS;</span><span class="sxs-lookup"><span data-stu-id="eee0a-147">BULK INSERT without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="eee0a-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) с предложением IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="eee0a-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) with IGNORE_CONSTRAINTS clause.</span></span>  
  
###  <a name="how-to-bulk-load-files-into-a-filetable"></a><a name="HowToBulkLoad"></a> <span data-ttu-id="eee0a-149">Как выполнить массовую загрузку файлов в таблицу FileTable</span><span class="sxs-lookup"><span data-stu-id="eee0a-149">How To: Bulk Load Files into a FileTable</span></span>  
 <span data-ttu-id="eee0a-150">Для массовой загрузки файлов в таблицу FileTable можно использовать различные способы.</span><span class="sxs-lookup"><span data-stu-id="eee0a-150">You can use various methods to bulk load files into a FileTable:</span></span>  
  
-   <span data-ttu-id="eee0a-151">**bcp**</span><span class="sxs-lookup"><span data-stu-id="eee0a-151">**bcp**</span></span>  
  
    -   <span data-ttu-id="eee0a-152">Вызвать с предложением **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="eee0a-152">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="eee0a-153">Отключить пространство имен FileTable и вызвать без предложения **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="eee0a-153">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="eee0a-154">Затем снова включить пространство имен FileTable.</span><span class="sxs-lookup"><span data-stu-id="eee0a-154">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="eee0a-155">**BULK INSERT**</span><span class="sxs-lookup"><span data-stu-id="eee0a-155">**BULK INSERT**</span></span>  
  
    -   <span data-ttu-id="eee0a-156">Вызвать с предложением **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="eee0a-156">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="eee0a-157">Отключить пространство имен FileTable и вызвать без предложения **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="eee0a-157">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="eee0a-158">Затем снова включить пространство имен FileTable.</span><span class="sxs-lookup"><span data-stu-id="eee0a-158">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="eee0a-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span><span class="sxs-lookup"><span data-stu-id="eee0a-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span></span>  
  
    -   <span data-ttu-id="eee0a-160">Вызвать с предложением **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="eee0a-160">Call with the **IGNORE_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="eee0a-161">Отключить пространство имен FileTable и выполнить вызов без предложения **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="eee0a-161">Disable the FileTable namespace and call without the **IGNORE_CONSTRAINTS** clause.</span></span> <span data-ttu-id="eee0a-162">Затем снова включить пространство имен FileTable.</span><span class="sxs-lookup"><span data-stu-id="eee0a-162">Then re-enable the FileTable namespace.</span></span>  
  
 <span data-ttu-id="eee0a-163">Сведения об отключении ограничений FileTable см. в разделе [Управление таблицами FileTable](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="eee0a-163">For information about disabling the FileTable constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-disable-filetable-constraints-for-bulk-loading"></a><a name="disabling"></a> <span data-ttu-id="eee0a-164">Как отключить ограничения FileTable для массовой загрузки</span><span class="sxs-lookup"><span data-stu-id="eee0a-164">How To: Disable FileTable Constraints for Bulk Loading</span></span>  
 <span data-ttu-id="eee0a-165">Для массовой загрузки файлов в таблицу FileTable без издержек по применению определенных в системе ограничений, можно временно отключить ограничения.</span><span class="sxs-lookup"><span data-stu-id="eee0a-165">To bulk load files into a FileTable without the overhead of enforcing the system-defined constraints, you can temporarily disable the constraints.</span></span> <span data-ttu-id="eee0a-166">Дополнительные сведения см. в статье [Управление таблицами FileTable](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="eee0a-166">For more information, see [Manage FileTables](manage-filetables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee0a-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="eee0a-167">See Also</span></span>  
 <span data-ttu-id="eee0a-168">[Доступ к таблицам FileTable с помощью Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="eee0a-168">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="eee0a-169">Доступ к таблицам FileTable с помощью API-интерфейсов ввода-вывода файлов</span><span class="sxs-lookup"><span data-stu-id="eee0a-169">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
