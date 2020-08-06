---
title: Использование символьного формата Юникода для импорта или экспорта данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], Unicode character
- Unicode [SQL Server], bulk importing and exporting
ms.assetid: 74342a11-c1c0-4746-b482-7f3537744a70
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 520ce1b4eed8dc11d6d3fe038969257aea1e90fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749931"
---
# <a name="use-unicode-character-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="d5425-102">Использование символьного формата Юникода для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d5425-102">Use Unicode Character Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="d5425-103">Символьный формат Юникода рекомендуется для массового переноса данных между несколькими экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] через файл данных, содержащий символы расширенной или двухбайтовой кодировки (DBCS).</span><span class="sxs-lookup"><span data-stu-id="d5425-103">Unicode character format is recommended for bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended/DBCS characters.</span></span> <span data-ttu-id="d5425-104">Формат символьных данных Юникода позволяет экспортировать данные из сервера в кодовой странице, отличающейся от кодовой страницы, используемой выполняющим операцию клиентом.</span><span class="sxs-lookup"><span data-stu-id="d5425-104">The Unicode character data format allows data to be exported from a server by using a code page that differs from the code page used by the client that is performing the operation.</span></span> <span data-ttu-id="d5425-105">В этих случаях использование символьного формата Юникода имеет следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="d5425-105">In such cases, use of Unicode character format has the following advantages:</span></span>  
  
-   <span data-ttu-id="d5425-106">Если данные источника и назначения имеют тип данных Юникода, при использовании символьного формата Юникода все символьные данные сохраняются.</span><span class="sxs-lookup"><span data-stu-id="d5425-106">If the source and destination data are Unicode data types, use of Unicode character format preserves all of the character data.</span></span>  
  
-   <span data-ttu-id="d5425-107">Если данные источника и назначения имеют тип данных, отличный от Юникода, использование символьного формата Юникода позволяет уменьшить потери дополнительных символов данных источника, которые не могут быть представимы в назначении.</span><span class="sxs-lookup"><span data-stu-id="d5425-107">if the source and destination data are not Unicode data types, use of Unicode character format minimizes the loss of extended characters in the source data that cannot be represented at the destination.</span></span>  
  
 <span data-ttu-id="d5425-108">Файлы данных символьного формата Юникода следуют соглашениям для файлов Юникода.</span><span class="sxs-lookup"><span data-stu-id="d5425-108">Unicode character format data files follow the conventions for Unicode files.</span></span> <span data-ttu-id="d5425-109">Первые два байта файла являются шестнадцатеричными числами 0xFFFE.</span><span class="sxs-lookup"><span data-stu-id="d5425-109">The first two bytes of the file are hexadecimal numbers, 0xFFFE.</span></span> <span data-ttu-id="d5425-110">Эти байты служат в качестве меток порядка байтов, определяющих, хранится старший байт в файле первым или последним.</span><span class="sxs-lookup"><span data-stu-id="d5425-110">These bytes serve as byte-order marks, specifying whether the high-order byte is stored first or last in the file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d5425-111">Чтобы файл форматирования мог работать с файлом данных в Юникоде, все поля входных данных должны быть представлены в виде текстовых строк в Юникоде (то есть в Юникоде в виде строк фиксированной длины или заканчивающимися символом конца строки).</span><span class="sxs-lookup"><span data-stu-id="d5425-111">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
 <span data-ttu-id="d5425-112">Данные типа `sql_variant`, хранящиеся в файле данных символьного формата Юникода, обрабатываются таким же образом, что и данные файла данных символьного формата, за исключением того, что они хранятся как данные типа данных `nchar`, а не как данные типа данных `char`.</span><span class="sxs-lookup"><span data-stu-id="d5425-112">The `sql_variant` data that is stored in a Unicode character-format data file operates in the same way it operates in a character-format data file, except that the data is stored as `nchar` instead of `char` data.</span></span> <span data-ttu-id="d5425-113">Дополнительные сведения о формате символов см. в разделе [Поддержка параметров сортировки и Юникода](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="d5425-113">For more information about character format, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="d5425-114">Сведения об использовании признака конца поля или строки, отличного от признака по умолчанию, предоставляемого в символьном формате Юникод, см. в разделе [Определение признаков конца поля и строки (SQL Server)](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5425-114">To use a field or row terminator other than the default that is provided with Unicode character format, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
## <a name="command-options-for-unicode-character-format"></a><span data-ttu-id="d5425-115">Параметры команд для символьного формата Юникода</span><span class="sxs-lookup"><span data-stu-id="d5425-115">Command Options for Unicode Character Format</span></span>  
 <span data-ttu-id="d5425-116">Данные символьного формата Юникода можно импортировать в таблицу с помощью программы **bcp**, BULK INSERT или INSERT... Выбор \* из OPENROWSET (BULK...). Для команды **bcp** или инструкции BULK INSERT можно указать формат данных в командной строке.</span><span class="sxs-lookup"><span data-stu-id="d5425-116">You can import Unicode character format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="d5425-117">Для инструкции INSERT ... SELECT \* FROM OPENROWSET(BULK...) нужно указать формат данных в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="d5425-117">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="d5425-118">Символьный формат Юникода поддерживается следующими параметрами командной строки.</span><span class="sxs-lookup"><span data-stu-id="d5425-118">Unicode character format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="d5425-119">Get-Help</span><span class="sxs-lookup"><span data-stu-id="d5425-119">Command</span></span>|<span data-ttu-id="d5425-120">Параметр</span><span class="sxs-lookup"><span data-stu-id="d5425-120">Option</span></span>|<span data-ttu-id="d5425-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d5425-121">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="d5425-122">**bcp**</span><span class="sxs-lookup"><span data-stu-id="d5425-122">**bcp**</span></span>|<span data-ttu-id="d5425-123">**-w**</span><span class="sxs-lookup"><span data-stu-id="d5425-123">**-w**</span></span>|<span data-ttu-id="d5425-124">Использует символьный формат Юникода.</span><span class="sxs-lookup"><span data-stu-id="d5425-124">Uses the Unicode character format.</span></span>|  
|<span data-ttu-id="d5425-125">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="d5425-125">BULK INSERT</span></span>|<span data-ttu-id="d5425-126">DATAFILETYPE **= '** widechar **'**</span><span class="sxs-lookup"><span data-stu-id="d5425-126">DATAFILETYPE **='** widechar **'**</span></span>|<span data-ttu-id="d5425-127">Использует символьный формат Юникода при массовом импорте данных.</span><span class="sxs-lookup"><span data-stu-id="d5425-127">Uses Unicode character format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="d5425-128">Дополнительные сведения см. в статьях [Программа bcp](../../tools/bcp-utility.md), [BULK INSERT (SQL Server)](/sql/t-sql/statements/bulk-insert-transact-sql) и [OPENROWSET (SQL Server)](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d5425-128">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5425-129">Также в файле форматирования можно указать форматирование для каждого поля.</span><span class="sxs-lookup"><span data-stu-id="d5425-129">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="d5425-130">Дополнительные сведения см в разделе [Файлы форматирования для импорта или экспорта данных (SQL Server)](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5425-130">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d5425-131">Примеры</span><span class="sxs-lookup"><span data-stu-id="d5425-131">Examples</span></span>  
 <span data-ttu-id="d5425-132">В следующих примерах демонстрируется массовый экспорт символьных данных в Юникоде при помощи команды **bcp** и массовый импорт тех же данных при помощи инструкции BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="d5425-132">The following examples demonstrate how to bulk export Unicode character data using **bcp** and to bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="d5425-133">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="d5425-133">Sample Table</span></span>  
 <span data-ttu-id="d5425-134">Для работы примеров необходимо, чтобы в образце базы данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] в схеме `myTestUniCharData` была создана таблица `dbo`.</span><span class="sxs-lookup"><span data-stu-id="d5425-134">The examples require that a table named `myTestUniCharData` table be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="d5425-135">Перед выполнением примеров следует создать эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="d5425-135">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="d5425-136">Для создания этой таблицы в редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="d5425-136">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestUniCharData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="d5425-137">Чтобы заполнить эту таблицу и просмотреть результирующее содержимое, выполните следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="d5425-137">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniCharData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3')   
        ,(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
  
```  
  
### <a name="using-bcp-to-bulk-export-unicode-character-data"></a><span data-ttu-id="d5425-138">Использование программы bcp для массового экспорта символьных данных формата Юникода</span><span class="sxs-lookup"><span data-stu-id="d5425-138">Using bcp to Bulk Export Unicode Character Data</span></span>  
 <span data-ttu-id="d5425-139">Чтобы экспортировать данные из таблицы в файл данных, используйте команду **bcp** с параметром **out** и следующими квалификаторами:</span><span class="sxs-lookup"><span data-stu-id="d5425-139">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="d5425-140">Квалификаторы</span><span class="sxs-lookup"><span data-stu-id="d5425-140">Qualifiers</span></span>|<span data-ttu-id="d5425-141">Описание</span><span class="sxs-lookup"><span data-stu-id="d5425-141">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="d5425-142">**-w**</span><span class="sxs-lookup"><span data-stu-id="d5425-142">**-w**</span></span>|<span data-ttu-id="d5425-143">Задает символьный формат Юникода.</span><span class="sxs-lookup"><span data-stu-id="d5425-143">Specifies Unicode character format.</span></span>|  
|<span data-ttu-id="d5425-144">**-t** `,`</span><span class="sxs-lookup"><span data-stu-id="d5425-144">**-t** `,`</span></span>|<span data-ttu-id="d5425-145">Задает запятую (`,`) в качестве признака конца поля.</span><span class="sxs-lookup"><span data-stu-id="d5425-145">Specifies a comma (`,`) as the field terminator.</span></span><br /><br /> <span data-ttu-id="d5425-146">Примечание. признак конца поля по умолчанию — символ табуляции в Юникоде (\t).</span><span class="sxs-lookup"><span data-stu-id="d5425-146">Note: The default field terminator is the tab Unicode character (\t).</span></span> <span data-ttu-id="d5425-147">Дополнительные сведения см. в разделе [Определение признаков конца поля и строки (SQL Server)](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5425-147">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>|  
|<span data-ttu-id="d5425-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="d5425-148">**-T**</span></span>|<span data-ttu-id="d5425-149">Указывает, что программа **bcp** устанавливает доверительное соединение с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием встроенной безопасности.</span><span class="sxs-lookup"><span data-stu-id="d5425-149">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="d5425-150">Если параметр **-T** не указан, для входа необходимо указать **-U** и **-P** .</span><span class="sxs-lookup"><span data-stu-id="d5425-150">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="d5425-151">Далее приводится пример массового экспорта символьных данных в Юникоде из таблицы `myTestUniCharData` в новый файл данных `myTestUniCharData-w.Dat`, в котором признаком конца поля служит запятая (`,`).</span><span class="sxs-lookup"><span data-stu-id="d5425-151">The following example bulk exports data in Unicode character format from the `myTestUniCharData` table into a new data file named `myTestUniCharData-w.Dat` data file that uses the comma (`,`) as the field terminator.</span></span> <span data-ttu-id="d5425-152">В командной строке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows введите:</span><span class="sxs-lookup"><span data-stu-id="d5425-152">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestUniCharData out C:\myTestUniCharData-w.Dat -w -t, -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-unicode-character-data"></a><span data-ttu-id="d5425-153">Использование инструкции BULK INSERT для массового импорта символьных данных формата Юникода</span><span class="sxs-lookup"><span data-stu-id="d5425-153">Using BULK INSERT to Bulk Import Unicode Character Data</span></span>  
 <span data-ttu-id="d5425-154">В следующем примере инструкция `BULK INSERT` используется для импорта данных из файла `myTestUniCharData-w.Dat` в таблицу `myTestUniCharData`.</span><span class="sxs-lookup"><span data-stu-id="d5425-154">The following example uses `BULK INSERT` to import the data in the `myTestUniCharData-w.Dat` data file into the `myTestUniCharData` table.</span></span> <span data-ttu-id="d5425-155">В инструкции должен быть объявлен признак конца поля (`,`), отличающийся от установленного по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5425-155">The nondefault field terminator (`,`) must be declared in the statement.</span></span> <span data-ttu-id="d5425-156">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="d5425-156">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestUniCharData   
   FROM 'C:\myTestUniCharData-w.Dat'   
   WITH (  
      DATAFILETYPE='widechar',  
      FIELDTERMINATOR=','  
   );   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d5425-157">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d5425-157">Related Tasks</span></span>  
 <span data-ttu-id="d5425-158">**Использование форматов данных для массового импорта или экспорта**</span><span class="sxs-lookup"><span data-stu-id="d5425-158">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="d5425-159">Импорт данных в собственном и символьном формате из предыдущих версий SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5425-159">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="d5425-160">Использование символьного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d5425-160">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="d5425-161">Использование собственного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d5425-161">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="d5425-162">Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d5425-162">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d5425-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5425-163">See Also</span></span>  
 <span data-ttu-id="d5425-164">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="d5425-164">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="d5425-165">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5425-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="d5425-166">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5425-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="d5425-167">[Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5425-167">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="d5425-168">Поддержка параметров сортировки и Юникода</span><span class="sxs-lookup"><span data-stu-id="d5425-168">Collation and Unicode Support</span></span>](../collations/collation-and-unicode-support.md)  
  
  
