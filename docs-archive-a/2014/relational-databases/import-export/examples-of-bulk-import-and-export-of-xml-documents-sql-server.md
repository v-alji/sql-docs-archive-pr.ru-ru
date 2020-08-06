---
title: Примеры массового импорта и экспорта XML-документов (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- field terminators [SQL Server]
- bulk importing [SQL Server], data formats
- row terminators [SQL Server]
- OPENROWSET function, XML bulk load
- terminators [SQL Server]
- bulk exporting [SQL Server], data formats
- XML bulk load [SQL Server]
ms.assetid: dff99404-a002-48ee-910e-f37f013d946d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d72c84a7ed84503e0c88d2a46c808196903900b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666609"
---
# <a name="examples-of-bulk-import-and-export-of-xml-documents-sql-server"></a><span data-ttu-id="b7468-102">Примеры массового импорта и экспорта XML-документов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b7468-102">Examples of Bulk Import and Export of XML Documents (SQL Server)</span></span>
    
##  <a name="you-can-bulk-import-xml-documents-into-a-ssnoversion-database-or-bulk-export-them-from-a-ssnoversion-database-this-topic-provides-examples-of-both"></a><a name="top"></a><span data-ttu-id="b7468-103">Можно выполнять массовый импорт XML-документов в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базу данных или выполнить их экспорт из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базы данных.</span><span class="sxs-lookup"><span data-stu-id="b7468-103">You can bulk import XML documents into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or bulk export them from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="b7468-104">В этом разделе приведены примеры и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="b7468-104">This topic provides examples of both.</span></span>  
  
 <span data-ttu-id="b7468-105">Для выполнения массового импорта данных из файла в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или несекционированное представление могут использоваться следующие средства.</span><span class="sxs-lookup"><span data-stu-id="b7468-105">To bulk import data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or non-partitioned view, you can use the following:</span></span>  
  
-   <span data-ttu-id="b7468-106">Программа**bcp**</span><span class="sxs-lookup"><span data-stu-id="b7468-106">**bcp** utility</span></span>  
  
     <span data-ttu-id="b7468-107">Программа **bcp** может выполнять экспорт везде в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , где работает инструкция SELECT, включая секционированные представления.</span><span class="sxs-lookup"><span data-stu-id="b7468-107">You can also use the **bcp** utility to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that a SELECT statement works, including partitioned views.</span></span>  
  
-   <span data-ttu-id="b7468-108">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="b7468-108">BULK INSERT</span></span>  
  
-   <span data-ttu-id="b7468-109">Инструкции INSERT ... SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="b7468-109">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
  
 <span data-ttu-id="b7468-110">Дополнительные сведения см. в статьях [Импорт и экспорт данных с помощью программы bcp &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) и [Импорт данных с помощью BULK INSERT или OPENROWSET&#40;BULK... &#41; &#40;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md)SQL Server&#41;.</span><span class="sxs-lookup"><span data-stu-id="b7468-110">For more information, see [Import and Export Bulk Data by Using the bcp Utility &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) and [Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b7468-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="b7468-111">Examples</span></span>  
 <span data-ttu-id="b7468-112">Далее следуют примеры.</span><span class="sxs-lookup"><span data-stu-id="b7468-112">The examples are the following:</span></span>  
  
-   <span data-ttu-id="b7468-113">A.</span><span class="sxs-lookup"><span data-stu-id="b7468-113">A.</span></span> [<span data-ttu-id="b7468-114">МАССОВЫй импорт XML-данных в виде двоичного байтового потока</span><span class="sxs-lookup"><span data-stu-id="b7468-114">BULK importing XML data as a binary byte stream</span></span>](#binary_byte_stream)  
  
-   <span data-ttu-id="b7468-115">Б.</span><span class="sxs-lookup"><span data-stu-id="b7468-115">B.</span></span> [<span data-ttu-id="b7468-116">Массовый импорт XML-данных в существующую строку</span><span class="sxs-lookup"><span data-stu-id="b7468-116">Bulk importing XML data in an existing row</span></span>](#existing_row)  
  
-   <span data-ttu-id="b7468-117">В.</span><span class="sxs-lookup"><span data-stu-id="b7468-117">C.</span></span> [<span data-ttu-id="b7468-118">Массовый импорт XML-данных из файла, содержащего DTD</span><span class="sxs-lookup"><span data-stu-id="b7468-118">Bulk importing XML data from a file that contains a DTD</span></span>](#file_contains_dtd)  
  
-   <span data-ttu-id="b7468-119">Г.</span><span class="sxs-lookup"><span data-stu-id="b7468-119">D.</span></span> [<span data-ttu-id="b7468-120">Указание признаков конца поля явным образом с помощью файла форматирования</span><span class="sxs-lookup"><span data-stu-id="b7468-120">Specifying the field terminator explicitly using a format file</span></span>](#field_terminator_in_format_file)  
  
-   <span data-ttu-id="b7468-121">Д.</span><span class="sxs-lookup"><span data-stu-id="b7468-121">E.</span></span> [<span data-ttu-id="b7468-122">Групповое Экспортирование XML-данных</span><span class="sxs-lookup"><span data-stu-id="b7468-122">Bulk exporting XML data</span></span>](#bulk_export_xml_data)  
  
###  <a name="a-bulk-importing-xml-data-as-a-binary-byte-stream"></a><a name="binary_byte_stream"></a> <span data-ttu-id="b7468-123">A.</span><span class="sxs-lookup"><span data-stu-id="b7468-123">A.</span></span> <span data-ttu-id="b7468-124">Массовый импорт XML-данных в виде двоичного байтового потока</span><span class="sxs-lookup"><span data-stu-id="b7468-124">Bulk importing XML data as a binary byte stream</span></span>  
 <span data-ttu-id="b7468-125">При массовом импорте XML-данных из файла, содержащего объявление кодировки, которое необходимо применить, нужно указать параметр SINGLE_BLOB в предложении OPENROWSET(BULK…).</span><span class="sxs-lookup"><span data-stu-id="b7468-125">When you bulk import XML data from a file that contains an encoding declaration that you want to apply, specify the SINGLE_BLOB option in the OPENROWSET(BULK...) clause.</span></span> <span data-ttu-id="b7468-126">Параметр SINGLE_BLOB гарантирует, что средство синтаксического анализа XML в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] произведет импорт данных в соответствии со схемой кодирования, указанной в XML-объявлении.</span><span class="sxs-lookup"><span data-stu-id="b7468-126">The SINGLE_BLOB option makes sure that the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] imports the data according to the encoding scheme specified in the XML declaration.</span></span>  
  
#### <a name="sample-table"></a><span data-ttu-id="b7468-127">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="b7468-127">Sample Table</span></span>  
 <span data-ttu-id="b7468-128">Для проверки примера A необходимо создать образец таблицы `T`.</span><span class="sxs-lookup"><span data-stu-id="b7468-128">To test example A, you must create sample table `T`.</span></span>  
  
```  
USE tempdb  
CREATE TABLE T (IntCol int, XmlCol xml);  
GO  
```  
  
#### <a name="sample-data-file"></a><span data-ttu-id="b7468-129">Образец файла данных</span><span class="sxs-lookup"><span data-stu-id="b7468-129">Sample Data File</span></span>  
 <span data-ttu-id="b7468-130">Перед запуском примера А необходимо создать файл в кодировке UTF-8 (`C:\SampleFolder\SampleData3.txt`), содержащий следующий образец, который определяет схему в кодировке `UTF-8` .</span><span class="sxs-lookup"><span data-stu-id="b7468-130">Before you can run example A, you must create a UTF-8 encoded file (`C:\SampleFolder\SampleData3.txt`) that contains the following sample instance that specifies the `UTF-8` encoding scheme.</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<Root>  
          <ProductDescription ProductModelID="5">  
             <Summary>Some Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-a"></a><span data-ttu-id="b7468-131">Пример A</span><span class="sxs-lookup"><span data-stu-id="b7468-131">Example A</span></span>  
 <span data-ttu-id="b7468-132">В этом примере используется параметр `SINGLE_BLOB` в инструкции `INSERT ... SELECT * FROM OPENROWSET(BULK...)` для импорта данных из файла с именем `SampleData3.txt` и вставки экземпляра данных XML в таблицу с одним столбцом, образец таблицы `T`.</span><span class="sxs-lookup"><span data-stu-id="b7468-132">This example uses the `SINGLE_BLOB` option in an `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement to import data from a file named `SampleData3.txt` and insert an XML instance in the single-column table, sample table `T`.</span></span>  
  
```  
INSERT INTO T(XmlCol)  
SELECT * FROM OPENROWSET(  
   BULK 'c:\SampleFolder\SampleData3.txt',  
   SINGLE_BLOB) AS x;  
```  
  
#### <a name="remarks"></a><span data-ttu-id="b7468-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7468-133">Remarks</span></span>  
 <span data-ttu-id="b7468-134">С помощью параметра SINGLE_BLOB можно избежать несоответствия между кодировкой XML-документа (указанной в объявлении кодировки XML) и кодовой страницей строки, используемой сервером.</span><span class="sxs-lookup"><span data-stu-id="b7468-134">By using SINGLE_BLOB in this case, you can avoid a mismatch between the encoding of the XML document (as specified by the XML encoding declaration) and the string codepage implied by the server.</span></span>  
  
 <span data-ttu-id="b7468-135">Если при использовании типов данных NCLOB или CLOB возникает конфликт кодовой страницы или кодировки, необходимо выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b7468-135">If you use NCLOB or CLOB data types and run into a codepage or encoding conflict, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="b7468-136">Удалить XML-декларацию, чтобы успешно импортировать содержимое XML-файла данных.</span><span class="sxs-lookup"><span data-stu-id="b7468-136">Remove the XML declaration to successfully import the contents of the XML data file.</span></span>  
  
-   <span data-ttu-id="b7468-137">Указать кодовую страницу в параметре CODEPAGE запроса, который соответствует схеме кодирования, используемой в XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="b7468-137">Specify a code page in the CODEPAGE option of the query that matches the encoding scheme that is used in the XML declaration.</span></span>  
  
-   <span data-ttu-id="b7468-138">Подобрать настройки параметров сортировки баз данных для схемы кодирования XML-данных, отличной от кодировки Юникод.</span><span class="sxs-lookup"><span data-stu-id="b7468-138">Match, or resolve, the database collation settings with a non-Unicode XML encoding scheme.</span></span>  
  
 [<span data-ttu-id="b7468-139">&#91;В начало&#93;</span><span class="sxs-lookup"><span data-stu-id="b7468-139">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="b-bulk-importing-xml-data-in-an-existing-row"></a><a name="existing_row"></a> <span data-ttu-id="b7468-140">Б.</span><span class="sxs-lookup"><span data-stu-id="b7468-140">B.</span></span> <span data-ttu-id="b7468-141">Массовый импорт XML-данных в существующую строку</span><span class="sxs-lookup"><span data-stu-id="b7468-141">Bulk importing XML data in an existing row</span></span>  
 <span data-ttu-id="b7468-142">В этом примере при помощи поставщика массового набора строк `OPENROWSET` в существующую строку или строки образца таблицы `T`добавляются инструкции XML.</span><span class="sxs-lookup"><span data-stu-id="b7468-142">This example uses the `OPENROWSET` bulk rowset provider to add an XML instance to an existing row or rows in sample table `T`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7468-143">Чтобы выполнить этот пример, вначале необходимо выполнить скрипт проверки в примере А. В этом примере сначала создается таблица `tempdb.dbo.T` ; затем в нее проводится массовый импорт данных из файла `SampleData3.txt`.</span><span class="sxs-lookup"><span data-stu-id="b7468-143">To run this example, you must first complete the test script provided in example A. That example creates the `tempdb.dbo.T` table and bulk imports data from `SampleData3.txt`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="b7468-144">Образец файла данных</span><span class="sxs-lookup"><span data-stu-id="b7468-144">Sample Data File</span></span>  
 <span data-ttu-id="b7468-145">В примере Б используется измененная версия образца файла данных `SampleData3.txt` из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="b7468-145">Example B uses a modified version of the `SampleData3.txt` sample data file from the preceding example.</span></span> <span data-ttu-id="b7468-146">Для запуска этого примера нужно изменить содержимое этого файла следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b7468-146">To run this example, modify the content of this file as follows:</span></span>  
  
```  
<Root>  
          <ProductDescription ProductModelID="10">  
             <Summary>Some New Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-b"></a><span data-ttu-id="b7468-147">Пример Б</span><span class="sxs-lookup"><span data-stu-id="b7468-147">Example B</span></span>  
  
```  
-- Query before update shows initial state of XmlCol values.  
SELECT * FROM T  
UPDATE T  
SET XmlCol =(  
SELECT * FROM OPENROWSET(  
   BULK 'C:\SampleFolder\SampleData3.txt',  
           SINGLE_BLOB  
) AS x  
)  
WHERE IntCol = 1;  
GO  
```  
  
 [<span data-ttu-id="b7468-148">&#91;В начало&#93;</span><span class="sxs-lookup"><span data-stu-id="b7468-148">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="c-bulk-importing-xml-data-from-a-file-that-contains-a-dtd"></a><a name="file_contains_dtd"></a> <span data-ttu-id="b7468-149">В.</span><span class="sxs-lookup"><span data-stu-id="b7468-149">C.</span></span> <span data-ttu-id="b7468-150">Массовый импорт XML-данных из файла, содержащего DTD</span><span class="sxs-lookup"><span data-stu-id="b7468-150">Bulk importing XML data from a file that contains a DTD</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b7468-151">Включать поддержку для определений типов документов (DTD) не рекомендуется, если только это не является неотъемлемой частью среды XML.</span><span class="sxs-lookup"><span data-stu-id="b7468-151">We recommended that you not enable support for Document Type Definitions (DTDs) if it is not required in your XML environment.</span></span> <span data-ttu-id="b7468-152">Включение поддержки DTD увеличивает уязвимую контактную зону сервера и может привести к атаке типа «отказ в обслуживании».</span><span class="sxs-lookup"><span data-stu-id="b7468-152">Turning on DTD support increases the attackable surface area of your server, and may expose it to a denial-of-service attack.</span></span> <span data-ttu-id="b7468-153">При необходимости включения поддержки DTD снизить риск для этой опасности можно с помощью обработки только доверенных XML-документов.</span><span class="sxs-lookup"><span data-stu-id="b7468-153">If you must enable DTD support, you can reduce this security risk by processing only trusted XML documents.</span></span>  
  
 <span data-ttu-id="b7468-154">При попытке использования команды [bcp](../../tools/bcp-utility.md) для импорта XML-данных из файла, содержащего DTD, может возникнуть одна из следующих ошибок:</span><span class="sxs-lookup"><span data-stu-id="b7468-154">During an attempt to use a [bcp](../../tools/bcp-utility.md) command to import XML data from a file that contains a DTD, an error similar to the following can occur:</span></span>  
  
 <span data-ttu-id="b7468-155">SQLState = 42000, NativeError = 6359</span><span class="sxs-lookup"><span data-stu-id="b7468-155">"SQLState = 42000, NativeError = 6359"</span></span>  
  
 <span data-ttu-id="b7468-156">«Error = [Microsoft][SQL Server Native Client][ SQL Server]Разбор XML при помощи встроенного DTD не допускается.</span><span class="sxs-lookup"><span data-stu-id="b7468-156">"Error = [Microsoft][SQL Server Native Client][ SQL Server]Parsing XML with internal subset DTDs not allowed.</span></span> <span data-ttu-id="b7468-157">Используйте CONVERT с параметром стиля 2 для включения ограниченной поддержки встроенного DTD.»</span><span class="sxs-lookup"><span data-stu-id="b7468-157">Use CONVERT with style option 2 to enable limited internal subset DTD support."</span></span>  
  
 <span data-ttu-id="b7468-158">«Не удалось выполнить BCP-копирование %s»</span><span class="sxs-lookup"><span data-stu-id="b7468-158">"BCP copy %s failed"</span></span>  
  
 <span data-ttu-id="b7468-159">Чтобы избежать этой проблемы, можно импортировать XML-данные из файла, содержащего DTD, при помощи функции `OPENROWSET(BULK...)` , а затем указать параметр `CONVERT` в предложении `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="b7468-159">To work around this problem, you can import XML data from a data file that contains a DTD by using the `OPENROWSET(BULK...)` function and then specifying the `CONVERT` option in the `SELECT` clause of the command.</span></span> <span data-ttu-id="b7468-160">Базовым синтаксисом команды является:</span><span class="sxs-lookup"><span data-stu-id="b7468-160">The basic syntax for the command is:</span></span>  
  
 `INSERT ... SELECT CONVERT(...) FROM OPENROWSET(BULK...)`  
  
#### <a name="sample-data-file"></a><span data-ttu-id="b7468-161">Образец файла данных</span><span class="sxs-lookup"><span data-stu-id="b7468-161">Sample Data File</span></span>  
 <span data-ttu-id="b7468-162">Перед проверкой этого примера массового импорта создайте файл (`C:\temp\Dtdfile.xml`), содержащий следующий образец данных:</span><span class="sxs-lookup"><span data-stu-id="b7468-162">Before you can test this bulk import example, create a file (`C:\temp\Dtdfile.xml`) that contains the following sample instance:</span></span>  
  
```  
<!DOCTYPE DOC [<!ATTLIST elem1 attr1 CDATA "defVal1">]><elem1>January</elem1>  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="b7468-163">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="b7468-163">Sample Table</span></span>  
 <span data-ttu-id="b7468-164">В примере В используется образец таблицы `T1` , созданный следующей инструкцией `CREATE TABLE` :</span><span class="sxs-lookup"><span data-stu-id="b7468-164">Example C uses the `T1` sample table that is created by the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE T1(XmlCol xml);  
GO  
```  
  
#### <a name="example-c"></a><span data-ttu-id="b7468-165">Пример В</span><span class="sxs-lookup"><span data-stu-id="b7468-165">Example C</span></span>  
 <span data-ttu-id="b7468-166">В этом примере используется `OPENROWSET(BULK...)` и в предложении `CONVERT` указывается параметр `SELECT` для импорта XML-данных из `Dtdfile.xml` в образец таблицы `T1`.</span><span class="sxs-lookup"><span data-stu-id="b7468-166">This example uses `OPENROWSET(BULK...)` and specifies the `CONVERT` option in the `SELECT` clause to import the XML data from `Dtdfile.xml` into sample table `T1`.</span></span>  
  
```  
INSERT T1  
  SELECT CONVERT(xml, BulkColumn, 2) FROM   
    OPENROWSET(Bulk 'c:\temp\Dtdfile.xml', SINGLE_BLOB) [rowsetresults];  
```  
  
 <span data-ttu-id="b7468-167">После выполнения инструкции `INSERT` определение DTD исключается из XML и хранится в таблице `T1` .</span><span class="sxs-lookup"><span data-stu-id="b7468-167">After the `INSERT` statement executes, the DTD is stripped from the XML and stored in the `T1` table.</span></span>  
  
 [<span data-ttu-id="b7468-168">&#91;В начало&#93;</span><span class="sxs-lookup"><span data-stu-id="b7468-168">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="d-specifying-the-field-terminator-explicitly-using-a-format-file"></a><a name="field_terminator_in_format_file"></a> <span data-ttu-id="b7468-169">Г.</span><span class="sxs-lookup"><span data-stu-id="b7468-169">D.</span></span> <span data-ttu-id="b7468-170">Указание признаков конца поля явным образом при помощи файла форматирования</span><span class="sxs-lookup"><span data-stu-id="b7468-170">Specifying the field terminator explicitly using a format file</span></span>  
 <span data-ttu-id="b7468-171">В следующем примере демонстрируется, как выполнить массовый импорт XML-документа `Xmltable.dat`.</span><span class="sxs-lookup"><span data-stu-id="b7468-171">The following example shows how to bulk import the following XML document, `Xmltable.dat`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="b7468-172">Образец файла данных</span><span class="sxs-lookup"><span data-stu-id="b7468-172">Sample Data File</span></span>  
 <span data-ttu-id="b7468-173">Документ из `Xmltable.dat` содержит два значения XML, по одному в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="b7468-173">The document in `Xmltable.dat` contains two XML values, one for each row.</span></span> <span data-ttu-id="b7468-174">Первое значение XML имеет кодировку UTF-16, второе — UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b7468-174">The first XML value is encoded with UTF-16, and the second value is encoded with UTF-8.</span></span>  
  
 <span data-ttu-id="b7468-175">Содержимое этого файла данных показано в следующем шестнадцатеричном дампе:</span><span class="sxs-lookup"><span data-stu-id="b7468-175">The contents of this data file are shown in the following Hex dump:</span></span>  
  
```  
FF FE 3C 00 3F 00 78 00-6D 00 6C 00 20 00 76 00  *..<.?.x.m.l. .v.*  
65 00 72 00 73 00 69 00-6F 00 6E 00 3D 00 22 00  *e.r.s.i.o.n.=.".*  
31 00 2E 00 30 00 22 00-20 00 65 00 6E 00 63 00  *1...0.". .e.n.c.*  
6F 00 64 00 69 00 6E 00-67 00 3D 00 22 00 75 00  *o.d.i.n.g.=.".u.*  
74 00 66 00 2D 00 31 00-36 00 22 00 3F 00 3E 00  *t.f.-.1.6.".?.>.*  
3C 00 72 00 6F 00 6F 00-74 00 3E 00 A2 4F 9C 76  *<.r.o.o.t.>..O.v*  
0C FA 77 E4 80 00 89 00-00 06 90 06 91 2E 9B 2E  *..w.............*  
99 34 A2 34 86 00 83 02-92 20 7F 02 4E C5 E4 A3  *.4.4..... ..N...*  
34 B2 B7 B3 B7 FE F8 FF-F8 00 3C 00 2F 00 72 00  *4.........<./.r.*  
6F 00 6F 00 74 00 3E 00-00 00 00 00 7A EF BB BF  *o.o.t.>.....z...*  
3C 3F 78 6D 6C 20 76 65-72 73 69 6F 6E 3D 22 31  *<?xml version="1*  
2E 30 22 20 65 6E 63 6F-64 69 6E 67 3D 22 75 74  *.0" encoding="ut*  
66 2D 38 22 3F 3E 3C 72-6F 6F 74 3E E4 BE A2 E7  *f-8"?><root>....*  
9A 9C EF A8 8C EE 91 B7-C2 80 C2 89 D8 80 DA 90  *................*  
E2 BA 91 E2 BA 9B E3 92-99 E3 92 A2 C2 86 CA 83  *................*  
E2 82 92 C9 BF EC 95 8E-EA 8F A4 EB 88 B4 EB 8E  *................*  
B7 EF BA B7 EF BF B8 C3-B8 3C 2F 72 6F 6F 74 3E  *.........</root>*  
00 00 00 00 7A                                   *....z*  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="b7468-176">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="b7468-176">Sample Table</span></span>  
 <span data-ttu-id="b7468-177">При выполнении массового импорта или экспорта XML-документа следует использовать [признаки конца поля](specify-field-and-row-terminators-sql-server.md) , которые не могут присутствовать в каком-либо документе, например последовательность из четырех значений NULL (`\0`), заканчивающаяся буквой `z`: `\0\0\0\0z`.</span><span class="sxs-lookup"><span data-stu-id="b7468-177">When you bulk import or export an XML document, you should use a [field terminator](specify-field-and-row-terminators-sql-server.md) that cannot possibly appear in any of the documents; for example, a series of four nulls (`\0`) followed by the letter `z`: `\0\0\0\0z`.</span></span>  
  
 <span data-ttu-id="b7468-178">В этом примере показано, как использовать эти признаки конца поля в образце таблицы `xTable` .</span><span class="sxs-lookup"><span data-stu-id="b7468-178">This example shows how to use this field terminator for the `xTable` sample table.</span></span> <span data-ttu-id="b7468-179">Чтобы создать этот образец таблицы, используйте следующую инструкцию `CREATE TABLE` :</span><span class="sxs-lookup"><span data-stu-id="b7468-179">To create this sample table, use the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE xTable (xCol xml);  
GO  
```  
  
#### <a name="sample-format-file"></a><span data-ttu-id="b7468-180">Образец файла форматирования</span><span class="sxs-lookup"><span data-stu-id="b7468-180">Sample Format File</span></span>  
 <span data-ttu-id="b7468-181">Признак конца поля должен быть указан в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="b7468-181">The field terminator must be specified in the format file.</span></span> <span data-ttu-id="b7468-182">В примере Г создается файл форматирования `Xmltable.fmt` в формате, отличном от XML, который содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="b7468-182">Example D uses a non-XML format file named `Xmltable.fmt` that contains the following:</span></span>  
  
```  
9.0  
1  
1       SQLBINARY     0       0       "\0\0\0\0z"    1     xCol         ""  
```  
  
 <span data-ttu-id="b7468-183">Этот файл форматирования можно использовать для массового импорта XML-документов в таблицу `xTable` при помощи команды `bcp` или инструкции `BULK INSERT` или `INSERT ... SELECT * FROM OPENROWSET(BULK...)` .</span><span class="sxs-lookup"><span data-stu-id="b7468-183">You can use this format file to bulk import XML documents into the `xTable` table by using a `bcp` command or a `BULK INSERT` or `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="b7468-184">Пример Г</span><span class="sxs-lookup"><span data-stu-id="b7468-184">Example D</span></span>  
 <span data-ttu-id="b7468-185">В этом примере используется файл форматирования `Xmltable.fmt` в инструкции `BULK INSERT` для импорта содержимого файла XML-данных с именем `Xmltable.dat`.</span><span class="sxs-lookup"><span data-stu-id="b7468-185">This example uses the `Xmltable.fmt` format file in a `BULK INSERT` statement to import the contents of an XML data file named `Xmltable.dat`.</span></span>  
  
```  
BULK INSERT xTable   
FROM 'C:\Xmltable.dat'  
WITH (FORMATFILE = 'C:\Xmltable.fmt');  
GO  
```  
  
 [<span data-ttu-id="b7468-186">&#91;В начало&#93;</span><span class="sxs-lookup"><span data-stu-id="b7468-186">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="e-bulk-exporting-xml-data"></a><a name="bulk_export_xml_data"></a> <span data-ttu-id="b7468-187">Д.</span><span class="sxs-lookup"><span data-stu-id="b7468-187">E.</span></span> <span data-ttu-id="b7468-188">Массовый экспорт XML-данных</span><span class="sxs-lookup"><span data-stu-id="b7468-188">Bulk exporting XML data</span></span>  
 <span data-ttu-id="b7468-189">В следующем примере для выполнения массового экспорта XML-данных из таблицы, созданной в предыдущем примере при помощи того же XML-файла форматирования, используется программа `bcp` .</span><span class="sxs-lookup"><span data-stu-id="b7468-189">The following example uses `bcp` to bulk export XML data from the table that is created in the preceding example by using the same XML format file.</span></span> <span data-ttu-id="b7468-190">В следующей команде `bcp``<server_name>` и `<instance_name>` являются заполнителями, которые должны быть заменены соответствующими значениями:</span><span class="sxs-lookup"><span data-stu-id="b7468-190">In the following `bcp` command, `<server_name>` and `<instance_name>` represent placeholders that must be replaced with appropriate values:</span></span>  
  
```  
bcp bulktest..xTable out a-wn.out -N -T -S<server_name>\<instance_name>  
```  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b7468-191">не сохраняет кодировку XML, если XML-данные постоянно хранятся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="b7468-191">does not save the XML encoding when XML data is persisted in the database.</span></span> <span data-ttu-id="b7468-192">Поэтому оригинальная кодировка полей XML недоступна при экспорте XML-данных.</span><span class="sxs-lookup"><span data-stu-id="b7468-192">Therefore, the original encoding of XML fields is not available when XML data is exported.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b7468-193">использует для экспорта XML-данных кодировку UTF-16.</span><span class="sxs-lookup"><span data-stu-id="b7468-193">uses UTF-16 encoding when exporting XML data.</span></span>  
  
 [<span data-ttu-id="b7468-194">&#91;В начало&#93;</span><span class="sxs-lookup"><span data-stu-id="b7468-194">&#91;Top&#93;</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="b7468-195">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7468-195">See Also</span></span>  
 <span data-ttu-id="b7468-196">[INSERT (Transact-SQL)](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b7468-196">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="b7468-197">[Предложение SELECT (Transact-SQL)](/sql/t-sql/queries/select-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b7468-197">[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span></span>  
 <span data-ttu-id="b7468-198">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b7468-198">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="b7468-199">[Массовый импорт и экспорт данных (SQL Server)](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b7468-199">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="b7468-200">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b7468-200">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="b7468-201">OPENROWSET (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b7468-201">OPENROWSET &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openrowset-transact-sql)  
  
  
