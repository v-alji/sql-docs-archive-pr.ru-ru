---
title: Доступ к таблицам FileTable с помощью Transact-SQL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], accessing files with T-SQL
ms.assetid: 3c4a5ffb-c521-4696-99cb-2b03cffc9c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c47751ef34747e1b3742accf5040846ecde074f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736407"
---
# <a name="access-filetables-with-transact-sql"></a><span data-ttu-id="50fe0-102">Доступ к таблицам FileTable с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50fe0-102">Access FileTables with Transact-SQL</span></span>
  <span data-ttu-id="50fe0-103">Описывает, как команды языка обработки данных DML [!INCLUDE[tsql](../../includes/tsql-md.md)] работают c таблицами FileTable.</span><span class="sxs-lookup"><span data-stu-id="50fe0-103">Describes how [!INCLUDE[tsql](../../includes/tsql-md.md)] data manipulation language (DML) commands work with FileTables.</span></span>  
  
##  <a name="insert-operations-on-filetables"></a><a name="BasicsInsert"></a> <span data-ttu-id="50fe0-104">Операции INSERT в таблицах FileTable</span><span class="sxs-lookup"><span data-stu-id="50fe0-104">INSERT Operations on FileTables</span></span>  
 <span data-ttu-id="50fe0-105">С операциями **INSERT** в таблицах FileTable связаны следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="50fe0-105">The following considerations apply to **INSERT** Operations on FileTables:</span></span>  
  
-   <span data-ttu-id="50fe0-106">Все столбцы атрибутов файла имеют ограничения NO NULL.</span><span class="sxs-lookup"><span data-stu-id="50fe0-106">All the file attribute columns have NOT NULL constraints.</span></span> <span data-ttu-id="50fe0-107">Если значения не заданы явным образом, предоставляются соответствующие значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="50fe0-107">If values are not explicitly set, then appropriate default values are supplied.</span></span>  
  
-   <span data-ttu-id="50fe0-108">Если инструкция INSERT задает значения для параметров **name**, **path_locator**, **parent_path_locator**или атрибуты файлов, то применяются системные ограничения.</span><span class="sxs-lookup"><span data-stu-id="50fe0-108">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="50fe0-109">Приложение может получить **path_locator** для файла или каталога, указав путь файловой системы для функции [GetPathLocator (Transact-SQL)](/sql/relational-databases/system-functions/getpathlocator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50fe0-109">The application can obtain the **path_locator** for a file or directory by providing the file system path to the [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function.</span></span>  
  
##  <a name="update-operations-on-filetables"></a><a name="BasicsUpdate"></a> <span data-ttu-id="50fe0-110">Операции UPDATE в таблицах FileTable</span><span class="sxs-lookup"><span data-stu-id="50fe0-110">UPDATE Operations on FileTables</span></span>  
 <span data-ttu-id="50fe0-111">С операциями UPDATE в таблицах **FileTable** связаны следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="50fe0-111">The following considerations apply to **UPDATE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="50fe0-112">Разрешается обновлять любые данные, определяемые пользователем.</span><span class="sxs-lookup"><span data-stu-id="50fe0-112">Updates to any user-defined data are allowed.</span></span>  
  
-   <span data-ttu-id="50fe0-113">Если инструкция INSERT задает значения для параметров **name**, **path_locator**, **parent_path_locator**или атрибуты файлов, то применяются системные ограничения.</span><span class="sxs-lookup"><span data-stu-id="50fe0-113">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="50fe0-114">Обновления данных FILESTREAM в столбце **file_stream** не влияют ни на какие другие столбцы, включая отметки времени.</span><span class="sxs-lookup"><span data-stu-id="50fe0-114">Updates can be made to the FILESTREAM data in the **file_stream** column without affecting any of the other columns, including the timestamps.</span></span>  
  
##  <a name="delete-operations-on-filetables"></a><a name="BasicsDelete"></a> <span data-ttu-id="50fe0-115">Операции DELETE в таблицах FileTable</span><span class="sxs-lookup"><span data-stu-id="50fe0-115">DELETE Operations on FileTables</span></span>  
 <span data-ttu-id="50fe0-116">С операциями **DELETE** в таблицах FileTable связаны следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="50fe0-116">The following considerations apply to **DELETE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="50fe0-117">При удалении строки удаляется соответствующий файл или каталог из файловой системы.</span><span class="sxs-lookup"><span data-stu-id="50fe0-117">Deleting a row also removes the corresponding file or directory from the file system.</span></span>  
  
-   <span data-ttu-id="50fe0-118">Невозможно удалить строку, если она относится к каталогу, который содержит другие файлы или каталоги.</span><span class="sxs-lookup"><span data-stu-id="50fe0-118">Deleting a row fails if the row corresponds to a directory that contains other files or directories.</span></span>  
  
##  <a name="constraints-that-are-enforced-for-dml-operations-on-filetables"></a><a name="BasicsConstraints"></a> <span data-ttu-id="50fe0-119">Ограничения, необходимые для операций DML в таблицах FileTable</span><span class="sxs-lookup"><span data-stu-id="50fe0-119">Constraints That Are Enforced for DML Operations on FileTables</span></span>  
 <span data-ttu-id="50fe0-120">Определяемые системой ограничения обеспечивают сохранение целостности иерархии пространства имен файлов во время операций DML.</span><span class="sxs-lookup"><span data-stu-id="50fe0-120">System-defined constraints ensure that DML actions do not compromise the integrity of the file namespace hierarchy.</span></span> <span data-ttu-id="50fe0-121">Принудительно применяются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="50fe0-121">The constraints that are enforced include the following:</span></span>  
  
-   <span data-ttu-id="50fe0-122">При установке или изменении **name** файла или каталога:</span><span class="sxs-lookup"><span data-stu-id="50fe0-122">When you set or change the **name** of the file or directory:</span></span>  
  
    -   <span data-ttu-id="50fe0-123">Поддерживаются обозначения имен файлов и каталогов Windows.</span><span class="sxs-lookup"><span data-stu-id="50fe0-123">Windows file and directory naming conventions are enforced.</span></span>  
  
    -   <span data-ttu-id="50fe0-124">Обеспечивается уникальность имени в родительском каталоге.</span><span class="sxs-lookup"><span data-stu-id="50fe0-124">The uniqueness of the name in the parent directory is enforced.</span></span>  
  
-   <span data-ttu-id="50fe0-125">При установке или изменении расположения файла или каталога путем назначения или редактирования **path_locator** или **parent_path_locator**:</span><span class="sxs-lookup"><span data-stu-id="50fe0-125">When you set or change the location of a file or directory by setting or changing the **path_locator** or **parent_path_locator**:</span></span>  
  
    -   <span data-ttu-id="50fe0-126">Обеспечивается уникальность.</span><span class="sxs-lookup"><span data-stu-id="50fe0-126">Uniqueness is enforced.</span></span>  
  
    -   <span data-ttu-id="50fe0-127">Обеспечивается согласованность иерархического дерева каталогов и файлов, включая согласованность значений **path_locator** и **parent_path_locator** .</span><span class="sxs-lookup"><span data-stu-id="50fe0-127">The consistency of the hierarchical tree of directories and files is enforced, including the consistency of **path_locator** and **parent_path_locator** values.</span></span>  
  
-   <span data-ttu-id="50fe0-128">Значение **is_directory** не может быть задано как true для ненулевого столбца **file_stream** .</span><span class="sxs-lookup"><span data-stu-id="50fe0-128">The value of **is_directory** cannot be set to true when the **file_stream** column is not null.</span></span> <span data-ttu-id="50fe0-129">Данные в столбце **file_stream** показывают, что строка соответствует файлу, а не каталогу.</span><span class="sxs-lookup"><span data-stu-id="50fe0-129">Data in the **file_stream** column indicates that the row represents a file and not a directory.</span></span>  
  
-   <span data-ttu-id="50fe0-130">Столбцы атрибутов файлов не могут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="50fe0-130">File attribute columns cannot be null.</span></span> <span data-ttu-id="50fe0-131">Ограничения NOT NULL применяются со значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="50fe0-131">NOT NULL constraints are enforced with default values.</span></span>  
  
-   <span data-ttu-id="50fe0-132">Значение **last_access_time** не может быть меньше (раньше), чем **last_write_time** и **creation_time**.</span><span class="sxs-lookup"><span data-stu-id="50fe0-132">The value of **last_access_time** cannot be earlier than **last_write_time** and **creation_time**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50fe0-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="50fe0-133">See Also</span></span>  
 <span data-ttu-id="50fe0-134">[выполнить загрузку файлов в таблицу FileTables](load-files-into-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="50fe0-134">[Load Files into FileTables](load-files-into-filetables.md) </span></span>  
 <span data-ttu-id="50fe0-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="50fe0-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span></span>  
 <span data-ttu-id="50fe0-136">[Доступ к таблицам FileTable с помощью API-интерфейсов ввода-вывода файлов](access-filetables-with-file-input-output-apis.md) </span><span class="sxs-lookup"><span data-stu-id="50fe0-136">[Access FileTables with File Input-Output APIs](access-filetables-with-file-input-output-apis.md) </span></span>  
 [<span data-ttu-id="50fe0-137">Инструкции FileTable языка DDL, функции, хранимые процедуры и представления</span><span class="sxs-lookup"><span data-stu-id="50fe0-137">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
