---
title: Файлы форматирования для импорта или экспорта данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], format files
- bulk importing [SQL Server], format files
- format files [SQL Server]
ms.assetid: b7b97d68-4336-4091-aee4-1941fab568e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1143690f0322fef2612fde51eebcb7427ee237ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666603"
---
# <a name="format-files-for-importing-or-exporting-data-sql-server"></a><span data-ttu-id="91704-102">Файлы форматирования для импорта или экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91704-102">Format Files for Importing or Exporting Data (SQL Server)</span></span>
  <span data-ttu-id="91704-103">Если выполняется массовый импорт данных в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или массовый экспорт данных из таблицы, можно использовать *файл форматирования* для сохранения всех сведений о формате, необходимых для массового экспорта или массового импорта данных.</span><span class="sxs-lookup"><span data-stu-id="91704-103">When you bulk import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or bulk export data from a table, you can use a *format file* to store all the format information that is required to bulk export or bulk import data.</span></span> <span data-ttu-id="91704-104">Это включает сведения о формате каждого поля в файле данных для этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="91704-104">This includes format information for each field in a data file relative to that table.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="91704-105">поддерживает два типа файлов форматирования: XML-файлы и файлы форматирования в формате, отличном от XML.</span><span class="sxs-lookup"><span data-stu-id="91704-105">supports two types of format files: XML formats and non-XML format files.</span></span> <span data-ttu-id="91704-106">Файлы форматирования как в XML, так и в другом формате, содержат описания каждого поля в файле данных, а XML-файлы форматирования содержат еще описания соответствующих столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="91704-106">Both non-XML format files and XML format files contain descriptions of every field in a data file, and XML format files also contain descriptions of the corresponding table columns.</span></span> <span data-ttu-id="91704-107">Как правило, XML-файлы и файлы форматирования в формате, отличном от XML взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="91704-107">Generally, XML and non-XML format files are interchangeable.</span></span> <span data-ttu-id="91704-108">Однако рекомендуется пользоваться XML-синтаксисом новых файлов форматирования, так как он обеспечивает ряд преимуществ перед файлами форматирования в формате, отличном от XML.</span><span class="sxs-lookup"><span data-stu-id="91704-108">However, we recommend that you use the XML syntax for new format files because they provide several advantages over non-XML format files.</span></span> <span data-ttu-id="91704-109">Дополнительные сведения см. в разделе [XML-файлы форматирования (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="91704-109">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 
  
##  <a name="benefits-of-format-files"></a><a name="Benefits"></a> <span data-ttu-id="91704-110">Преимущества файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="91704-110">Benefits of Format Files</span></span>  
  
-   <span data-ttu-id="91704-111">Предоставляет гибкую систему записи файлов данных, которая вообще не требует или требует лишь небольших правок для совместимости с другими форматами данных или для чтения файлов данных, созданных в другом программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="91704-111">Provides a flexible system for writing data files that requires little or no editing to comply with other data formats or to read data files from other software.</span></span>  
  
-   <span data-ttu-id="91704-112">Позволяет выполнять массовый импорт данных без необходимости добавлять или удалять ненужные данные, а также изменять порядок существующих данных в файле данных.</span><span class="sxs-lookup"><span data-stu-id="91704-112">Enables you to bulk import data without having to add or delete unnecessary data or to reorder existing data in the data file.</span></span> <span data-ttu-id="91704-113">Файлы форматирования особенно полезны в том случае, если существует несоответствие между полями в файле данных и столбцами в таблице.</span><span class="sxs-lookup"><span data-stu-id="91704-113">Format files are particularly useful when a mismatch exists between fields in the data file and columns in the table.</span></span>  
  
##  <a name="examples-of-format-files"></a><a name="ExamplesOfFFs"></a> <span data-ttu-id="91704-114">Примеры файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="91704-114">Examples of Format Files</span></span>  
 <span data-ttu-id="91704-115">В следующих примерах показана структура файлов форматирования в формате, отличном от XML, и XML-файлов форматирования.</span><span class="sxs-lookup"><span data-stu-id="91704-115">The following examples show the layout of a non-XML format file and of an XML format file.</span></span> <span data-ttu-id="91704-116">Эти файлы форматирования соответствуют таблице `HumanResources.myTeam` в образце базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91704-116">These format files correspond to the `HumanResources.myTeam` table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="91704-117">Эта таблица содержит четыре столбца: `EmployeeID`, `Name`, `Title`и `ModifiedDate`.</span><span class="sxs-lookup"><span data-stu-id="91704-117">This table contains four columns: `EmployeeID`, `Name`, `Title`, and `ModifiedDate`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91704-118">Дополнительные сведения о таблице и способе ее создания см. в разделе [Образец таблицы HumanResources.myTeam (SQL Server)](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="91704-118">For information about this table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
### <a name="a-using-a-non-xml-format-file"></a><span data-ttu-id="91704-119">A.</span><span class="sxs-lookup"><span data-stu-id="91704-119">A.</span></span> <span data-ttu-id="91704-120">Использование файла форматирования в формате, отличном от XML</span><span class="sxs-lookup"><span data-stu-id="91704-120">Using a non-XML format file</span></span>  
 <span data-ttu-id="91704-121">Следующий файл форматирования в формате, отличном от XML использует собственный формат данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для таблицы `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="91704-121">The following non-XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="91704-122">Этот файл форматирования был создан с помощью следующей команды `bcp` :</span><span class="sxs-lookup"><span data-stu-id="91704-122">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Fmt -n -T   
The contents of this format file are as follows: 9.0  
4  
1       SQLSMALLINT   0       2       ""   1     EmployeeID               ""  
2       SQLNCHAR      2       100     ""   2     Name                     SQL_Latin1_General_CP1_CI_AS  
3       SQLNCHAR      2       100     ""   3     Title                    SQL_Latin1_General_CP1_CI_AS  
4       SQLNCHAR      2       100     ""   4     Background               SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="91704-123">Дополнительные сведения см в разделе [Файлы формата, отличные от XML (SQL Server)](non-xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="91704-123">For more information, see [Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span></span>  
  
 
  
### <a name="b-using-an-xml-format-file"></a><span data-ttu-id="91704-124">Б.</span><span class="sxs-lookup"><span data-stu-id="91704-124">B.</span></span> <span data-ttu-id="91704-125">Использование XML-файла форматирования</span><span class="sxs-lookup"><span data-stu-id="91704-125">Using an XML format file</span></span>  
 <span data-ttu-id="91704-126">Следующий XML-файл форматирования использует собственный формат данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для таблицы `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="91704-126">The following XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="91704-127">Этот файл форматирования был создан с помощью следующей команды `bcp` :</span><span class="sxs-lookup"><span data-stu-id="91704-127">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Xml -x -n -T   
```  
  
 <span data-ttu-id="91704-128">Файл форматирования содержит:</span><span class="sxs-lookup"><span data-stu-id="91704-128">The format file contains:</span></span>  
  
```  
 <?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="EmployeeID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Name" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Title" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Background" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="91704-129">Дополнительные сведения см. в разделе [XML-файлы форматирования (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="91704-129">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="when-is-a-format-file-required"></a><a name="WhenFFrequired"></a> <span data-ttu-id="91704-130">Когда необходим файл форматирования?</span><span class="sxs-lookup"><span data-stu-id="91704-130">When Is a Format File Required?</span></span>  
 <span data-ttu-id="91704-131">Инструкция INSERT... SELECT \* FROM OPENROWSET(BULK...) всегда требует наличия файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="91704-131">An INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement always requires a format file.</span></span>  
  
-   <span data-ttu-id="91704-132">Для **bcp** или BULK INSERT использование файла форматирования в простых ситуациях необязательно, и в этом редко возникает необходимость.</span><span class="sxs-lookup"><span data-stu-id="91704-132">For **bcp** or BULK INSERT, in simple situations, using a format file is optional and rarely necessary.</span></span> <span data-ttu-id="91704-133">Однако при выполнении сложных операций массового импорта файл форматирования очень часто необходим.</span><span class="sxs-lookup"><span data-stu-id="91704-133">However, for complex bulk-import situations, a format file is frequently required.</span></span>  
  
 <span data-ttu-id="91704-134">Файлы форматирования необходимы, если:</span><span class="sxs-lookup"><span data-stu-id="91704-134">Format files are required if:</span></span>  
  
-   <span data-ttu-id="91704-135">один и тот же файл данных используется в качестве источника для нескольких таблиц с разными схемами;</span><span class="sxs-lookup"><span data-stu-id="91704-135">The same data file is used as a source for multiple tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="91704-136">число полей в файле данных отличается от числа столбцов в целевой таблице, например:</span><span class="sxs-lookup"><span data-stu-id="91704-136">The data file has a different number of fields that the target table has columns; for example:</span></span>  
  
    -   <span data-ttu-id="91704-137">целевая таблица содержит по крайней мере один столбец, для которого либо задано значение по умолчанию, либо разрешено значение NULL;</span><span class="sxs-lookup"><span data-stu-id="91704-137">The target table contains at least one column for which either a default value is defined or NULL is allowed.</span></span>  
  
    -   <span data-ttu-id="91704-138">пользователи не имеют разрешений на выполнение инструкций SELECT/INSERT в одном или нескольких столбцах таблицы;</span><span class="sxs-lookup"><span data-stu-id="91704-138">The users do not have SELECT/INSERT permissions on one or more columns in the table.</span></span>  
  
    -   <span data-ttu-id="91704-139">один и тот же файл данных используется для двух или более таблиц с разными схемами.</span><span class="sxs-lookup"><span data-stu-id="91704-139">A single data file is used with two or more tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="91704-140">порядок столбцов в файле данных отличается от порядка столбцов в таблице;</span><span class="sxs-lookup"><span data-stu-id="91704-140">The column order is different for the data file and table.</span></span>  
  
-   <span data-ttu-id="91704-141">завершающие символы или длины префиксов отличаются в столбцах файла данных.</span><span class="sxs-lookup"><span data-stu-id="91704-141">The terminating characters or prefix lengths differ among the columns of the data file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91704-142">Если файл форматирования отсутствует и в команде **bcp** задан параметр формата данных ( **-n**, **-c**, **-w**или **-N**) либо в операции BULK INSERT задан параметр DATAFILETYPE, указанный формат данных используется как метод интерпретации полей в файле данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="91704-142">In the absence of a format file, if a **bcp** command specifies a data-format switch (**-n**, **-c**, **-w**, or **-N**) or a BULK INSERT operation specifies the DATAFILETYPE option, the specified data format is used as the default method of interpreting the fields of the data file.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="91704-143">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="91704-143">Related Tasks</span></span>  
  
-   [<span data-ttu-id="91704-144">Создание файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91704-144">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="91704-145">Использование файла форматирования для массового импорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91704-145">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="91704-146">Пропуск столбца таблицы с помощью файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91704-146">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="91704-147">Использование файла форматирования для пропуска поля данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91704-147">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="91704-148">Использование файла форматирования для сопоставления столбцов таблицы с полями файла данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91704-148">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="91704-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="91704-149">See Also</span></span>  
 <span data-ttu-id="91704-150">[Файлы формата, отличные от XML (SQL Server)](non-xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91704-150">[Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span></span>  
 <span data-ttu-id="91704-151">[XML-файлы форматирования (SQL Server)](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91704-151">[XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="91704-152">Форматы данных для массового экспорта или импорта (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91704-152">Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;</span></span>](data-formats-for-bulk-import-or-bulk-export-sql-server.md)  
  
  
