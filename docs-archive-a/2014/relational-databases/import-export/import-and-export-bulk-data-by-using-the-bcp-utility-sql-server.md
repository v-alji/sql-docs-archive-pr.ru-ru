---
title: Массовый импорт и экспорт данных с использованием программы bcp (SQL Server) | Документация Майкрософт
ms.prod: sql-server-2014
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], bcp utility
- bulk importing [SQL Server], bcp utility
- bcp utility [SQL Server], about bcp utility
ms.assetid: 73e949de-67a3-4c84-9735-7da1ad4ba34a
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: ''
ms.date: 06/14/2017
ms.openlocfilehash: 7d1892b26f3c638a696d8ed15e739f56ac2e682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666597"
---
# <a name="import-and-export-bulk-data-by-using-the-bcp-utility-sql-server"></a><span data-ttu-id="880fa-102">Массовый импорт и экспорт данных с использованием программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-102">Import and Export Bulk Data by Using the bcp Utility (SQL Server)</span></span>

<span data-ttu-id="880fa-103">В этом разделе представлен обзор использования [программы bcp](../../tools/bcp-utility.md) для экспорта данных из любого местоположения в базу данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , в которой может применяться инструкция SELECT, включая секционированные представления.</span><span class="sxs-lookup"><span data-stu-id="880fa-103">This topic provides an overview for using the [bcp utility](../../tools/bcp-utility.md) to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database where a SELECT statement works, including partitioned views.</span></span>  
  
 <span data-ttu-id="880fa-104">Программа bcp (bcp.exe) представляет собой инструмент командной строки, использующий API-интерфейс программы массового копирования (BCP).</span><span class="sxs-lookup"><span data-stu-id="880fa-104">The bcp utility (Bcp.exe) is a command-line tool that uses the Bulk Copy Program (BCP) API.</span></span> <span data-ttu-id="880fa-105">Программа bcp выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="880fa-105">The bcp utility performs the following tasks:</span></span>  
  
-   <span data-ttu-id="880fa-106">массовый экспорт данных из таблицы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в файл данных;</span><span class="sxs-lookup"><span data-stu-id="880fa-106">Bulk exports data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into a data file.</span></span>  
  
-   <span data-ttu-id="880fa-107">массовый экспорт данных из запроса;</span><span class="sxs-lookup"><span data-stu-id="880fa-107">Bulk exports data from a query.</span></span>  
  
-   <span data-ttu-id="880fa-108">массовый импорт данных из файла данных в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="880fa-108">Bulk imports data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
-   <span data-ttu-id="880fa-109">создание файлов форматирования.</span><span class="sxs-lookup"><span data-stu-id="880fa-109">Generates format files.</span></span>  
  
 <span data-ttu-id="880fa-110">Служебная программа bcp вызывается командой **bcp** .</span><span class="sxs-lookup"><span data-stu-id="880fa-110">The bcp utility is accessed by the **bcp** command.</span></span> <span data-ttu-id="880fa-111">Применение команды **bcp** для массового импорта требует понимания схемы таблицы и типов данных ее столбцов (если не используется заранее созданный файл форматирования).</span><span class="sxs-lookup"><span data-stu-id="880fa-111">To use the **bcp** command to bulk import data, you must understand the schema of the table and the data types of its columns, unless you are using a pre-existing format file.</span></span>  
  
 <span data-ttu-id="880fa-112">Программа bcp может экспортировать данные из таблицы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в файл данных для использования другими программами.</span><span class="sxs-lookup"><span data-stu-id="880fa-112">The bcp utility can export data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table to a data file for use in other programs.</span></span> <span data-ttu-id="880fa-113">Программа также может импортировать данные в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из другой программы, обычно другой системы управления базой данных (СУБД).</span><span class="sxs-lookup"><span data-stu-id="880fa-113">The utility can also import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from another program, usually another database management system (DBMS).</span></span> <span data-ttu-id="880fa-114">Вначале выполняется экспорт данных из исходной программы в файл данных, а затем отдельной операцией данные копируются из файла данных в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="880fa-114">The data is first exported from the source program to a data file and then, in a separate operation, copied from the data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="880fa-115">Команда **bcp** предоставляет параметры для указания типа данных файла данных и других сведений.</span><span class="sxs-lookup"><span data-stu-id="880fa-115">The **bcp** command provides switches that you use to specify the data type of the data file and other information.</span></span> <span data-ttu-id="880fa-116">Если такие ключи не заданы, программа выводит приглашение для ввода этих сведений, например для типа полей данных в файле данных.</span><span class="sxs-lookup"><span data-stu-id="880fa-116">If these switches are not specified, the command prompts for formatting information, such as the type of data fields in a data file.</span></span> <span data-ttu-id="880fa-117">Затем команда запрашивает, нужно ли создать файл форматирования, содержащий данные ответы.</span><span class="sxs-lookup"><span data-stu-id="880fa-117">The command then asks whether you want to create a format file that contains your interactive responses.</span></span> <span data-ttu-id="880fa-118">Чтобы обеспечить гибкость для будущих операций массового импорта и экспорта, часто используется файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="880fa-118">If you want flexibility for future bulk-import or bulk-export operations, a format file is often useful.</span></span> <span data-ttu-id="880fa-119">В последующих командах **bcp** вы можете указать файл форматирования для эквивалентных файлов данных.</span><span class="sxs-lookup"><span data-stu-id="880fa-119">You can specify the format file on later **bcp** commands for equivalent data files.</span></span> <span data-ttu-id="880fa-120">Дополнительные сведения см. в разделе [Указание форматов данных для совместимости с помощью программы bcp (SQL Server)](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="880fa-120">For more information, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="880fa-121">Служебная программа bcp написана при использовании массового копирования ODBC</span><span class="sxs-lookup"><span data-stu-id="880fa-121">The bcp utility is written by using the ODBC bulk-copy</span></span>  
  
 <span data-ttu-id="880fa-122">Описание синтаксиса команды **bcp** см. в разделе [Служебная программа bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="880fa-122">For a description of the **bcp** command syntax, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="880fa-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="880fa-123">Examples</span></span>

 <span data-ttu-id="880fa-124">Примеры **bcp** см. здесь:</span><span class="sxs-lookup"><span data-stu-id="880fa-124">For **bcp** examples, see:</span></span>  
  
-   [<span data-ttu-id="880fa-125">Программа bcp</span><span class="sxs-lookup"><span data-stu-id="880fa-125">bcp Utility</span></span>](../../tools/bcp-utility.md)  
  
-   [<span data-ttu-id="880fa-126">Создание файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-126">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="880fa-127">Примеры массового импорта и экспорта XML-документов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-127">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
  
-   [<span data-ttu-id="880fa-128">Сохранение значений идентификаторов при массовом импорте данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-128">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="880fa-129">Сохранение значений NULL или использование значений по умолчанию при массовом импорте данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-129">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="880fa-130">Определение признаков конца поля и строки (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-130">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="880fa-131">Использование файла форматирования для массового импорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-131">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="880fa-132">Использование символьного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="880fa-133">Использование собственного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-133">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="880fa-134">Использование символьного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="880fa-135">Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="880fa-135">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  

## <a name="see-also"></a><span data-ttu-id="880fa-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="880fa-136">See Also</span></span>

<span data-ttu-id="880fa-137">&#41;Transact- [SQL INSERT &#40;](/sql/t-sql/statements/insert-transact-sql) 
 [Предложение SELECT &#40;&#41;](/sql/t-sql/queries/select-clause-transact-sql) 
 Transact-SQL [программа bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="880fa-137">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql)
[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql)
[bcp Utility](../../tools/bcp-utility.md) </span></span>  
<span data-ttu-id="880fa-138">[Подготовка SQL Server &#40;данных к групповому импорту&#41;](prepare-to-bulk-import-data-sql-server.md) 
 [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) 
 [Групповой импорт и экспорт SQL Server &#40;данных&#41;](bulk-import-and-export-of-data-sql-server.md) 
 [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) 
 [Создайте файл форматирования &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="880fa-138">[Prepare to Bulk Import Data &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md)
[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql)
[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md)
[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)
[Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span></span>