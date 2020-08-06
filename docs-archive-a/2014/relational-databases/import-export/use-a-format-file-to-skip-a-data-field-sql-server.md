---
title: Использование файла форматирования для пропуска поля данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], skipping data fields
- skipping data fields when importing
ms.assetid: 6a76517e-983b-47a1-8f02-661b99859a8b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d3f78c3c97c5bbe862867d5f51ff35f57d147df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669415"
---
# <a name="use-a-format-file-to-skip-a-data-field-sql-server"></a><span data-ttu-id="b14cd-102">Использование файла форматирования для пропуска поля данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b14cd-102">Use a Format File to Skip a Data Field (SQL Server)</span></span>
  <span data-ttu-id="b14cd-103">Количество полей в файле данных может превышать количество столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="b14cd-103">A data file can contain more fields than the number of columns in the table.</span></span> <span data-ttu-id="b14cd-104">В этом подразделе описан процесс изменения файлов форматирования в форматах XML и не XML с целью сопоставления столбцов таблицы с полями файла данных и пропуска остальных полей.</span><span class="sxs-lookup"><span data-stu-id="b14cd-104">This topic describes modifying both non-XML and XML format files to accommodate a data file with more fields by mapping the table columns to the corresponding data fields and ignoring the extra fields.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b14cd-105">Файл форматирования в формате, отличном от XML или XML, можно использовать для выполнения операций импорта файла данных в таблицу с помощью команды **bcp** , BULK INSERT или инструкции INSERT... SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="b14cd-105">Either a non-XML or XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="b14cd-106">Дополнительные сведения см. в разделе [Использование файла форматирования для массового импорта данных (SQL Server)](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b14cd-106">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-data-file-and-table"></a><span data-ttu-id="b14cd-107">Образец таблицы и файла данных</span><span class="sxs-lookup"><span data-stu-id="b14cd-107">Sample Data File and Table</span></span>  
 <span data-ttu-id="b14cd-108">В примерах этого подраздела используются следующие таблица и файл данных.</span><span class="sxs-lookup"><span data-stu-id="b14cd-108">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="b14cd-109">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="b14cd-109">Sample Table</span></span>  
 <span data-ttu-id="b14cd-110">Для работы примеров необходимо, чтобы в образце базы данных `myTestSkipField` в схеме [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] была создана таблица `dbo` .</span><span class="sxs-lookup"><span data-stu-id="b14cd-110">The examples require that a table named `myTestSkipField` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="b14cd-111">Чтобы создать эту таблицу, в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] редакторе запросов выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="b14cd-111">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestSkipField   
   (  
   PersonID smallint,  
   FirstName nvarchar(50) ,  
   LastName nvarchar(50)   
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="b14cd-112">Образец файла данных</span><span class="sxs-lookup"><span data-stu-id="b14cd-112">Sample Data File</span></span>  
 <span data-ttu-id="b14cd-113">Файл данных `myTestSkipField-c.dat`содержит следующие записи:</span><span class="sxs-lookup"><span data-stu-id="b14cd-113">The data file, `myTestSkipField-c.dat`, contains the following records:</span></span>  
  
```  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
```  
  
 <span data-ttu-id="b14cd-114">Для массового импорта из файла `myTestSkipField-c.dat` в таблицу `myTestSkipField` файл форматирования должен сделать следующий код:</span><span class="sxs-lookup"><span data-stu-id="b14cd-114">To bulk import data from `myTestSkipField-c.dat` into the `myTestSkipField` table, the format file must do the following:</span></span>  
  
-   <span data-ttu-id="b14cd-115">сопоставить первое поле данных с первым столбцом, `PersonID`;</span><span class="sxs-lookup"><span data-stu-id="b14cd-115">Map the first data field to the first column, `PersonID`.</span></span>  
  
-   <span data-ttu-id="b14cd-116">пропустить второе поле данных;</span><span class="sxs-lookup"><span data-stu-id="b14cd-116">Skip the second data field.</span></span>  
  
-   <span data-ttu-id="b14cd-117">сопоставить третье поле данных со вторым столбцом, `FirstName`;</span><span class="sxs-lookup"><span data-stu-id="b14cd-117">Map the third data field to the second column, `FirstName`.</span></span>  
  
-   <span data-ttu-id="b14cd-118">сопоставить четвертое поле данных с третьим столбцом, `LastName`.</span><span class="sxs-lookup"><span data-stu-id="b14cd-118">Map the fourth data field to the third column, `LastName`.</span></span>  
  
## <a name="non-xml-format-file-for-more-data-fields"></a><span data-ttu-id="b14cd-119">Не XML-файлы форматирования для дополнительных полей данных</span><span class="sxs-lookup"><span data-stu-id="b14cd-119">Non-XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="b14cd-120">Файл форматирования `myTestSkipField.fmt` сопоставляет поля в файле `myTestSkipField-c.dat` со столбцами таблицы `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="b14cd-120">The following format file, `myTestSkipField.fmt`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="b14cd-121">Файл форматирования имеет символьный формат данных.</span><span class="sxs-lookup"><span data-stu-id="b14cd-121">The format file uses character data format.</span></span> <span data-ttu-id="b14cd-122">Чтобы пропустить столбец, необходимо изменить его порядковый номер на «0», как показано для столбца `ExtraField` в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="b14cd-122">Skipping a column mapping requires changing its column order value to 0, as shown for the `ExtraField` column in the format file.</span></span>  
  
 <span data-ttu-id="b14cd-123">В файле форматирования `myTestSkipField.fmt` содержатся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b14cd-123">The `myTestSkipField.fmt` format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     PersonID               ""  
2       SQLCHAR       0       100       ","    0     ExtraField             SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      2     FirstName              SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   3     LastName               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b14cd-124">Сведения о синтаксисе файлов форматирования в формате, отличном от XML, см. в разделе [Файлы формата, отличные от XML (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b14cd-124">For information about the syntax of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b14cd-125">Примеры</span><span class="sxs-lookup"><span data-stu-id="b14cd-125">Examples</span></span>  
 <span data-ttu-id="b14cd-126">В следующем примере используется инструкция `INSERT ... SELECT * FROM OPENROWSET(BULK...)` с файлом форматирования `myTestSkipField.fmt` .</span><span class="sxs-lookup"><span data-stu-id="b14cd-126">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.fmt` format file.</span></span> <span data-ttu-id="b14cd-127">В примере выполняется массовый импорт файла данных `myTestSkipField-c.dat` в таблицу `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="b14cd-127">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="b14cd-128">Создание образца таблицы и файла данных см. выше в разделе «Образец таблицы и файла данных».</span><span class="sxs-lookup"><span data-stu-id="b14cd-128">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="b14cd-129">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="b14cd-129">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
   SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.fmt'    
       ) AS t1;  
GO   
```  
  
## <a name="xml-format-file-for-more-data-fields"></a><span data-ttu-id="b14cd-130">XML-файл форматирования для дополнительных полей данных</span><span class="sxs-lookup"><span data-stu-id="b14cd-130">XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="b14cd-131">Файл форматирования в этом примере создан на основе другого файла форматирования `myTestSkipField.xml`, в котором количество полей совпадает с количеством столбцов таблицы `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="b14cd-131">The format file presented in this example is based on another format file, `myTestSkipField.xml`, which uses character data format throughout and whose fields correspond exactly in number and order to the columns in the `myTestSkipField` table.</span></span> <span data-ttu-id="b14cd-132">Содержимое этого файла форматирования см. в разделе [Создание файла форматирования (SQL Server)](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b14cd-132">To view the contents of that format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
 <span data-ttu-id="b14cd-133">Файл форматирования `myTestSkipField.xml` сопоставляет поля в файле `myTestSkipField-c.dat` со столбцами таблицы `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="b14cd-133">The following format file, `myTestSkipField.xml`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="b14cd-134">Файл форматирования имеет символьный формат данных.</span><span class="sxs-lookup"><span data-stu-id="b14cd-134">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="b14cd-135">В файле форматирования `myTestSkipField.xml` содержатся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b14cd-135">The `myTestSkipField.xml` format file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="PersonID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="3" NAME="FirstName" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="LastName" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
### <a name="examples"></a><span data-ttu-id="b14cd-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="b14cd-136">Examples</span></span>  
 <span data-ttu-id="b14cd-137">В следующем примере используется инструкция `INSERT ... SELECT * FROM OPENROWSET(BULK...)` с файлом форматирования `myTestSkipField.Xml` .</span><span class="sxs-lookup"><span data-stu-id="b14cd-137">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.Xml` format file.</span></span> <span data-ttu-id="b14cd-138">В примере выполняется массовый импорт файла данных `myTestSkipField-c.dat` в таблицу `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="b14cd-138">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="b14cd-139">Создание образца таблицы и файла данных см. выше в разделе «Образец таблицы и файла данных».</span><span class="sxs-lookup"><span data-stu-id="b14cd-139">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="b14cd-140">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="b14cd-140">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
  SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.xml'    
       ) AS t1;  
GO  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b14cd-141">Дополнительные сведения о синтаксисе XML-схемы и дополнительные образцы XML-файлов форматирования см. в статье [XML-файлы форматирования (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b14cd-141">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14cd-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="b14cd-142">See Also</span></span>  
 <span data-ttu-id="b14cd-143">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b14cd-143">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="b14cd-144">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b14cd-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="b14cd-145">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b14cd-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="b14cd-146">[Пропуск столбца таблицы с помощью файла форматирования (SQL Server)](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b14cd-146">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="b14cd-147">Использование файла форматирования для сопоставления столбцов таблицы с полями файла данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b14cd-147">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
  
