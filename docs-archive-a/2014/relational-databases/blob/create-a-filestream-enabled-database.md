---
title: Создание базы данных с поддержкой FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FILESTREAM-enabled databases
ms.assetid: 0fc16356-76f7-44b8-a58b-f0b7c43694ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0fe6e5bc6e4f60bc0703482f3bf4d761104b3c5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732698"
---
# <a name="create-a-filestream-enabled-database"></a><span data-ttu-id="48259-102">Создание базы данных с поддержкой FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="48259-102">Create a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="48259-103">В этом разделе показано, как создать базу данных с поддержкой FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="48259-103">This topic shows how to create a database that supports FILESTREAM.</span></span> <span data-ttu-id="48259-104">Поскольку хранилище FILESTREAM использует особый тип файловой группы, при создании базы данных необходимо указать предложение CONTAINS FILESTREAM хотя бы для одной файловой группы.</span><span class="sxs-lookup"><span data-stu-id="48259-104">Because FILESTREAM uses a special type of filegroup, when you create the database, you must specify the CONTAINS FILESTREAM clause for at least one filegroup.</span></span>  
  
 <span data-ttu-id="48259-105">Файловая группа FILESTREAM может содержать более одного файла.</span><span class="sxs-lookup"><span data-stu-id="48259-105">A FILESTREAM filegroup can contain more than one file.</span></span> <span data-ttu-id="48259-106">Пример кода, демонстрирующий создание файловой группы FILESTREAM из нескольких файлов, см. в разделе [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="48259-106">For a code example that demonstrates how to create a FILESTREAM filegroup that contains multiple files, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
### <a name="to-create-a-filestream-enabled-database"></a><span data-ttu-id="48259-107">Создание базы данных с поддержкой FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="48259-107">To create a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="48259-108">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]нажмите кнопку **Создать запрос** , чтобы открыть редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="48259-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="48259-109">Скопируйте [!INCLUDE[tsql](../../includes/tsql-md.md)] код создает базу данных с поддержкой FILESTREAM с именем Archive.</span><span class="sxs-lookup"><span data-stu-id="48259-109">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled database called Archive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48259-110">Для этого скрипта должен существовать каталог C:\Data.</span><span class="sxs-lookup"><span data-stu-id="48259-110">For this script, the directory C:\Data must exist.</span></span>  
  
3.  <span data-ttu-id="48259-111">Чтобы построить базу данных, нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="48259-111">To build the database, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48259-112">Пример</span><span class="sxs-lookup"><span data-stu-id="48259-112">Example</span></span>  
 <span data-ttu-id="48259-113">В следующем примере кода создается база данных с именем `Archive`.</span><span class="sxs-lookup"><span data-stu-id="48259-113">The following code example creates a database that is named `Archive`.</span></span> <span data-ttu-id="48259-114">В этой базе данных содержатся три файловые группы: `PRIMARY`, `Arch1`и `FileStreamGroup1`.</span><span class="sxs-lookup"><span data-stu-id="48259-114">The database contains three filegroups: `PRIMARY`, `Arch1`, and `FileStreamGroup1`.</span></span> <span data-ttu-id="48259-115">`PRIMARY` и `Arch1` — это обычные файловые группы, которые не могут содержать данные FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="48259-115">`PRIMARY` and `Arch1` are regular filegroups that cannot contain FILESTREAM data.</span></span> <span data-ttu-id="48259-116">`FileStreamGroup1` — это файловая группа `FILESTREAM` .</span><span class="sxs-lookup"><span data-stu-id="48259-116">`FileStreamGroup1` is the `FILESTREAM` filegroup.</span></span>  
  
```sql  
CREATE DATABASE Archive   
ON  
PRIMARY ( NAME = Arch1,  
    FILENAME = 'c:\data\archdat1.mdf'),  
FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
    FILENAME = 'c:\data\filestream1')  
LOG ON  ( NAME = Archlog1,  
    FILENAME = 'c:\data\archlog1.ldf')  
GO  
```  
  
 <span data-ttu-id="48259-117">Для файловой группы `FILESTREAM` параметр `FILENAME` содержит путь.</span><span class="sxs-lookup"><span data-stu-id="48259-117">For a `FILESTREAM` filegroup, `FILENAME` refers to a path.</span></span> <span data-ttu-id="48259-118">Должен существовать путь вплоть до последнего каталога, но последний каталог существовать не должен.</span><span class="sxs-lookup"><span data-stu-id="48259-118">The path up to the last folder must exist, and the last folder must not exist.</span></span> <span data-ttu-id="48259-119">В этом примере `c:\data` должен существовать.</span><span class="sxs-lookup"><span data-stu-id="48259-119">In this example, `c:\data` must exist.</span></span> <span data-ttu-id="48259-120">Но вложенная папка `filestream1` не может существовать, если выполняется инструкция `CREATE DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="48259-120">However, the `filestream1` subfolder cannot exist when you execute the `CREATE DATABASE` statement.</span></span> <span data-ttu-id="48259-121">Дополнительные сведения о синтаксисе см. в разделе [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="48259-121">For more information about the syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
 <span data-ttu-id="48259-122">После запуска предыдущего примера в папке «c:\Data\filestream1» появится файл filestream.hdr и папка $FSLOG.</span><span class="sxs-lookup"><span data-stu-id="48259-122">After you run the previous example, a filestream.hdr file and an $FSLOG folder appears in the c:\Data\filestream1 folder.</span></span> <span data-ttu-id="48259-123">Файл filestream.hdr является файлом заголовка контейнера FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="48259-123">The filestream.hdr file is a header file for the FILESTREAM container.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48259-124">Файл filestream.hdr является важным системным файлом.</span><span class="sxs-lookup"><span data-stu-id="48259-124">The filestream.hdr file is an important system file.</span></span> <span data-ttu-id="48259-125">Он содержит данные заголовка FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="48259-125">It contains FILESTREAM header information.</span></span> <span data-ttu-id="48259-126">Не перемещайте и не изменяйте этот файл.</span><span class="sxs-lookup"><span data-stu-id="48259-126">Do not remove or modify this file.</span></span>  
  
 <span data-ttu-id="48259-127">Для существующих баз данных файловую группу FILESTREAM можно добавить с помощью инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="48259-127">For existing databases, you can use the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to add a FILESTREAM filegroup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48259-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="48259-128">See Also</span></span>  
 <span data-ttu-id="48259-129">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48259-129">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="48259-130">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="48259-130">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
