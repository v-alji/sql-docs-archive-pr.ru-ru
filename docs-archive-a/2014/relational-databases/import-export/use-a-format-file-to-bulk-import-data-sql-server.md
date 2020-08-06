---
title: Использование файла форматирования для массового импорта данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], format files
- format files [SQL Server], importing data using
ms.assetid: 2956df78-833f-45fa-8a10-41d6522562b9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6d9779209b3ffb317658243c168d74740f6731b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669416"
---
# <a name="use-a-format-file-to-bulk-import-data-sql-server"></a><span data-ttu-id="918c5-102">Использование файла форматирования для массового импорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="918c5-102">Use a Format File to Bulk Import Data (SQL Server)</span></span>
  <span data-ttu-id="918c5-103">Эта тема посвящена использованию файла форматирования в операциях массового импорта.</span><span class="sxs-lookup"><span data-stu-id="918c5-103">This topic illustrates the use of a format file in bulk-import operations.</span></span> <span data-ttu-id="918c5-104">Файл форматирования сопоставляет поля файла данных столбцам таблицы.</span><span class="sxs-lookup"><span data-stu-id="918c5-104">The format file maps the fields of the data file to the columns of the table.</span></span>  <span data-ttu-id="918c5-105">Можно использовать файл форматирования в формате, отличном от XML или XML, для выполнения операций импорта данных при использовании команды **bcp** или BULK INSERT или INSERT... SELECT \* FROM OPENROWSET (BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] кнопки.</span><span class="sxs-lookup"><span data-stu-id="918c5-105">You can use a non-XML or XML format file to bulk import data when using a **bcp** command or a BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="918c5-106">Чтобы файл форматирования мог работать с файлом данных в Юникоде, все поля входных данных должны быть представлены в виде текстовых строк в Юникоде (то есть в Юникоде в виде строк фиксированной длины или заканчивающимися символом конца строки).</span><span class="sxs-lookup"><span data-stu-id="918c5-106">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="918c5-107">Если вы не знакомы с файлами форматирования, см. раздел [файлы форматирования в формате, отличном от XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) и [XML-файлы форматирования &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="918c5-107">If you are unfamiliar with format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) and [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="format-file-options-for-bulk-import-commands"></a><span data-ttu-id="918c5-108">Параметры файла форматирования для команд массового импортирования</span><span class="sxs-lookup"><span data-stu-id="918c5-108">Format File Options for Bulk-Import Commands</span></span>  
 <span data-ttu-id="918c5-109">В следующей таблице перечислены параметры файла форматирования для каждой команды массового импортирования.</span><span class="sxs-lookup"><span data-stu-id="918c5-109">The following table summarizes the format-file option of for each of the bulk-import commands.</span></span>  
  
|<span data-ttu-id="918c5-110">Команда массовой загрузки</span><span class="sxs-lookup"><span data-stu-id="918c5-110">Bulk-load Command</span></span>|<span data-ttu-id="918c5-111">Параметр файла форматирования</span><span class="sxs-lookup"><span data-stu-id="918c5-111">Using the Format-File Option</span></span>|  
|------------------------|-----------------------------------|  
|<span data-ttu-id="918c5-112">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="918c5-112">BULK INSERT</span></span>|<span data-ttu-id="918c5-113">FORMATFILE = '*путь_к_файлу_форматирования*'</span><span class="sxs-lookup"><span data-stu-id="918c5-113">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="918c5-114">Инструкции INSERT ... SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="918c5-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="918c5-115">FORMATFILE = '*путь_к_файлу_форматирования*'</span><span class="sxs-lookup"><span data-stu-id="918c5-115">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="918c5-116">**bcp** ... **в**</span><span class="sxs-lookup"><span data-stu-id="918c5-116">**bcp** ... **in**</span></span>|<span data-ttu-id="918c5-117">**-f** *format_file*</span><span class="sxs-lookup"><span data-stu-id="918c5-117">**-f** *format_file*</span></span>|  
  
 <span data-ttu-id="918c5-118">Дополнительные сведения см. в статьях [Программа bcp](../../tools/bcp-utility.md), [BULK INSERT (SQL Server)](/sql/t-sql/statements/bulk-insert-transact-sql) и [OPENROWSET (SQL Server)](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="918c5-118">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="918c5-119">Для массового экспорта или импорта данных SQLXML используется один из следующих типов данных в файле форматирования. SQLCHAR или SQLVARYCHAR (данные посылаются в кодовой странице клиента или в кодовой странице, предполагаемой параметрами сортировки), SQLNCHAR или SQLNVARCHAR (данные посылаются в формате Юникод) и SQLBINARY или SQLVARYBIN (данные посылаются без преобразования).</span><span class="sxs-lookup"><span data-stu-id="918c5-119">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="918c5-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="918c5-120">Examples</span></span>  
 <span data-ttu-id="918c5-121">В примерах этого раздела показано, как использовать файлы форматирования для выполнения операций с массовым импортом с помощью команды **bcp** , BULK INSERT и вставки... SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="918c5-121">The examples in this section illustrate how to use format files to bulk-import data by using the **bcp** command and the BULK INSERT, and INSERT ... SELECT \* FROM OPENROWSET(BULK...) statements.</span></span> <span data-ttu-id="918c5-122">Перед выполнением примеров массового импортирования необходимо создать учебную таблицу, файл данных и файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="918c5-122">Before you can run one of the bulk-import examples, you need to create a sample table, data file, and a format file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="918c5-123">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="918c5-123">Sample Table</span></span>  
 <span data-ttu-id="918c5-124">Для выполнения этих примеров необходимо создать таблицу **myTestFormatFiles** в схеме **dbo** образца базы данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="918c5-124">The examples require that a table named **myTestFormatFiles** table be created in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="918c5-125">Для создания этой таблицы в редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="918c5-125">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestFormatFiles (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50),  
   Col4 nvarchar(50)  
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="918c5-126">Образец файла данных</span><span class="sxs-lookup"><span data-stu-id="918c5-126">Sample Data File</span></span>  
 <span data-ttu-id="918c5-127">В примере используется образец файла данных `myTestFormatFiles-c.Dat`, который содержит следующие записи.</span><span class="sxs-lookup"><span data-stu-id="918c5-127">The examples use a sample data file, `myTestFormatFiles-c.Dat`, which contains the following records.</span></span> <span data-ttu-id="918c5-128">Для создания файла данных введите в командной строке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows:</span><span class="sxs-lookup"><span data-stu-id="918c5-128">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
10,Field2,Field3,Field4  
15,Field2,Field3,Field4  
46,Field2,Field3,Field4  
58,Field2,Field3,Field4  
```  
  
### <a name="sample-format-files"></a><span data-ttu-id="918c5-129">Образцы файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="918c5-129">Sample Format Files</span></span>  
 <span data-ttu-id="918c5-130">В некоторых примерах в этом разделе используется файл форматирования XML `myTestFormatFiles-f-x-c.Xml`, в других примерах используются файлы других форматов (не XML).</span><span class="sxs-lookup"><span data-stu-id="918c5-130">Some of the examples in this section use an XML format file, `myTestFormatFiles-f-x-c.Xml`, and other examples use a non-XML format file.</span></span> <span data-ttu-id="918c5-131">Во всех файлах форматирования содержатся символьные данные и используется нестандартный признак конца поля (,).</span><span class="sxs-lookup"><span data-stu-id="918c5-131">Both format files use character data formats and a non-default field terminator (,).</span></span>  
  
#### <a name="the-sample-non-xml-format-file"></a><span data-ttu-id="918c5-132">Образец файла форматирования в формате, отличном от XML</span><span class="sxs-lookup"><span data-stu-id="918c5-132">The Sample Non-XML Format File</span></span>  
 <span data-ttu-id="918c5-133">В приведенном ниже примере используется команда **bcp** для создания XML-файла форматирования из таблицы `myTestFormatFiles`.</span><span class="sxs-lookup"><span data-stu-id="918c5-133">The following example uses **bcp** to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="918c5-134">Файл `myTestFormatFiles.Fmt` содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="918c5-134">The `myTestFormatFiles.Fmt` file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     Col1         ""  
2       SQLCHAR       0       100     ","      2     Col2         SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      3     Col3         SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   4     Col4         SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="918c5-135">Чтобы воспользоваться командой **bcp** с параметром **format** для создания этого файла форматирования, введите в командной строке Windows следующее:</span><span class="sxs-lookup"><span data-stu-id="918c5-135">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -f myTestFormatFiles.Fmt -T  
  
```  
  
 <span data-ttu-id="918c5-136">Дополнительные сведения о создании файла форматирования см. в разделе [Создание файла форматирования (SQL Server)](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="918c5-136">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
#### <a name="the-sample-xml-format-file"></a><span data-ttu-id="918c5-137">Образец XML-файла форматирования</span><span class="sxs-lookup"><span data-stu-id="918c5-137">The Sample XML Format File</span></span>  
 <span data-ttu-id="918c5-138">В приведенном ниже примере используется команда **bcp** для создания XML-файла форматирования из таблицы `myTestFormatFiles`.</span><span class="sxs-lookup"><span data-stu-id="918c5-138">The following example uses **bcp** to create to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="918c5-139">Файл `myTestFormatFiles.Xml` содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="918c5-139">The `myTestFormatFiles.Xml` file contains the following information:</span></span>  
  
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
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="918c5-140">Чтобы воспользоваться командой **bcp** с параметром **format** для создания этого файла форматирования, введите в командной строке Windows следующее:</span><span class="sxs-lookup"><span data-stu-id="918c5-140">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -x -f myTestFormatFiles.Xml -T  
```  
  
### <a name="using-bcp"></a><span data-ttu-id="918c5-141">Использование команды bcp</span><span class="sxs-lookup"><span data-stu-id="918c5-141">Using bcp</span></span>  
 <span data-ttu-id="918c5-142">В приведенном ниже примере используется команда **bcp** для массового импорта данных из файла данных `myTestFormatFiles-c.Dat` в таблицу `HumanResources.myTestFormatFiles` в образце базы данных.</span><span class="sxs-lookup"><span data-stu-id="918c5-142">The following example uses **bcp** to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the  sample database.</span></span> <span data-ttu-id="918c5-143">В примере используется файл форматирования XML `MyTestFormatFiles.Xml`.</span><span class="sxs-lookup"><span data-stu-id="918c5-143">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="918c5-144">Перед импортированием файла данных все существующие строки таблицы удаляются.</span><span class="sxs-lookup"><span data-stu-id="918c5-144">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="918c5-145">В командной строке Windows введите:</span><span class="sxs-lookup"><span data-stu-id="918c5-145">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestFormatFiles in C:\myTestFormatFiles-c.Dat -f C:\myTestFormatFiles.Xml -T  
```  
  
> [!NOTE]  
>  <span data-ttu-id="918c5-146">Дополнительные сведения об этой команде см. в разделе [Программа bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="918c5-146">For more information about this command, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
### <a name="using-bulk-insert"></a><span data-ttu-id="918c5-147">Использование предложения BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="918c5-147">Using BULK INSERT</span></span>  
 <span data-ttu-id="918c5-148">В следующем примере для массового импортирования данных из файла данных `myTestFormatFiles-c.Dat` в таблицу `HumanResources.myTestFormatFiles` образца базы данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] используется инструкция BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="918c5-148">The following example uses BULK INSERT to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="918c5-149">В примере используется файл форматирования, отличный от XML, `MyTestFormatFiles.Fmt`.</span><span class="sxs-lookup"><span data-stu-id="918c5-149">This example uses a non-XML format file, `MyTestFormatFiles.Fmt`.</span></span> <span data-ttu-id="918c5-150">Перед импортированием файла данных все существующие строки таблицы удаляются.</span><span class="sxs-lookup"><span data-stu-id="918c5-150">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="918c5-151">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="918c5-151">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DELETE myTestFormatFiles;  
GO  
BULK INSERT myTestFormatFiles   
   FROM 'C:\myTestFormatFiles-c.Dat'   
   WITH (FORMATFILE = 'C:\myTestFormatFiles.Fmt');  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="918c5-152">Дополнительные сведения об этой инструкции см. в разделе [BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="918c5-152">For more information about this statement, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="using-the-openrowset-bulk-rowset-provider"></a><span data-ttu-id="918c5-153">Использование поставщика массовых наборов строк OPENROWSET</span><span class="sxs-lookup"><span data-stu-id="918c5-153">Using the OPENROWSET Bulk Rowset Provider</span></span>  
 <span data-ttu-id="918c5-154">В следующем примере для массового импорта данных из файла данных `INSERT ... SELECT * FROM OPENROWSET(BULK...)` в таблицу `myTestFormatFiles-c.Dat` образца базы данных `HumanResources.myTestFormatFiles` используется команда `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="918c5-154">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the `AdventureWorks` sample database.</span></span> <span data-ttu-id="918c5-155">В примере используется файл форматирования XML `MyTestFormatFiles.Xml`.</span><span class="sxs-lookup"><span data-stu-id="918c5-155">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="918c5-156">Перед импортированием файла данных все существующие строки таблицы удаляются.</span><span class="sxs-lookup"><span data-stu-id="918c5-156">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="918c5-157">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="918c5-157">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
DELETE myTestFormatFiles;  
GO  
INSERT INTO myTestFormatFiles  
    SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestFormatFiles-c.Dat',  
      FORMATFILE='C:\myTestFormatFiles.Xml'       
      ) as t1 ;  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
 <span data-ttu-id="918c5-158">Закончив эксперименты с образцом таблицы, удалите ее при помощи следующей инструкции:</span><span class="sxs-lookup"><span data-stu-id="918c5-158">When you finish using the sample table, you can drop it using the following statement:</span></span>  
  
```  
DROP TABLE myTestFormatFiles  
```  
  
> [!NOTE]  
>  <span data-ttu-id="918c5-159">Дополнительные сведения о предложении OPENROWSET BULK см. в разделе [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="918c5-159">For more information about the OPENROWSET BULK clause, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="918c5-160">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="918c5-160">Additional Examples</span></span>  
 [<span data-ttu-id="918c5-161">Создание файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="918c5-161">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
 [<span data-ttu-id="918c5-162">Пропуск столбца таблицы с помощью файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="918c5-162">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 [<span data-ttu-id="918c5-163">Использование файла форматирования для пропуска поля данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="918c5-163">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
 [<span data-ttu-id="918c5-164">Использование файла форматирования для сопоставления столбцов таблицы с полями файла данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="918c5-164">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="918c5-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="918c5-165">See Also</span></span>  
 <span data-ttu-id="918c5-166">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="918c5-166">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="918c5-167">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="918c5-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="918c5-168">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="918c5-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="918c5-169">[Файлы формата, отличные от XML (SQL Server)](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="918c5-169">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="918c5-170">XML-файлы форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="918c5-170">XML Format Files &#40;SQL Server&#41;</span></span>](xml-format-files-sql-server.md)  
  
  
