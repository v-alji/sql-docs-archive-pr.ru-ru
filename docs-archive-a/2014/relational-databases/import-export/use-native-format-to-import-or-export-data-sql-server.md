---
title: Использование собственного формата для импорта или экспорта данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- data formats [SQL Server], native
ms.assetid: eb279b2f-0f1f-428f-9b8f-2a7fc495b79f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab42ba3eb6468aac3da2fa780d371818c8776690
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749935"
---
# <a name="use-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="0a73b-102">Использование собственного формата для импорта или экспорта данных</span><span class="sxs-lookup"><span data-stu-id="0a73b-102">Use Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="0a73b-103">Собственный формат данных рекомендуется использовать при массовой передаче данных между несколькими экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] через файл данных, который не содержит символов в расширенной кодировке или символов в двухбайтовой кодировке (DBCS).</span><span class="sxs-lookup"><span data-stu-id="0a73b-103">Native format is recommended when you bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using a data file that does not contain any extended/double-byte character set (DBCS) characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a73b-104">При массовой передаче данных между несколькими экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи файла данных, содержащего символы в расширенной кодировке или символы DBCS, необходимо использовать собственный формат в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="0a73b-104">To bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters, you should use the Unicode native format.</span></span> <span data-ttu-id="0a73b-105">Дополнительные сведения см. в разделе [Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0a73b-105">For more information, see [Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="0a73b-106">В собственном формате используются собственные типы данных базы данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-106">Native format maintains the native data types of a database.</span></span> <span data-ttu-id="0a73b-107">Собственный формат предназначен для высокоскоростной передачи данных между таблицами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a73b-107">Native format is intended for high-speed data transfer of data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="0a73b-108">Если используется файл форматирования, то исходная и целевая таблицы не обязаны быть идентичными.</span><span class="sxs-lookup"><span data-stu-id="0a73b-108">If you use a format file, the source and target tables do not need to be identical.</span></span> <span data-ttu-id="0a73b-109">Передача данных происходит в два этапа:</span><span class="sxs-lookup"><span data-stu-id="0a73b-109">The data transfer involves two steps:</span></span>  
  
1.  <span data-ttu-id="0a73b-110">Массовый экспорт данных из исходной таблицы в файл данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-110">Bulk exporting the data from a source table into a data file</span></span>  
  
2.  <span data-ttu-id="0a73b-111">Массовый импорт данных из файла данных в целевую таблицу.</span><span class="sxs-lookup"><span data-stu-id="0a73b-111">Bulk importing the data from the data file into the target table</span></span>  
  
 <span data-ttu-id="0a73b-112">Использование собственного формата между идентичными таблицами позволяет избежать бесполезного преобразования типов данных из символьного формата и обратно, экономя тем самым время и пространство хранения.</span><span class="sxs-lookup"><span data-stu-id="0a73b-112">The use of native format between identical tables avoids unnecessary conversion of data types to and from character format, saving time and space.</span></span> <span data-ttu-id="0a73b-113">Для достижения оптимальной скорости передачи, однако, уменьшается количество проверок форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-113">To achieve the optimum transfer rate, however, few checks are performed regarding data formatting.</span></span> <span data-ttu-id="0a73b-114">Чтобы избежать проблемы с загруженными данными, изучите следующий список ограничений.</span><span class="sxs-lookup"><span data-stu-id="0a73b-114">To prevent problems with the loaded data, see the following restrictions list.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="0a73b-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0a73b-115">Restrictions</span></span>  
 <span data-ttu-id="0a73b-116">Чтобы успешно импортировать данные в собственный формат, убедитесь, что:</span><span class="sxs-lookup"><span data-stu-id="0a73b-116">To import data in native format successfully, ensure that:</span></span>  
  
-   <span data-ttu-id="0a73b-117">Файл данных создан в собственном формате.</span><span class="sxs-lookup"><span data-stu-id="0a73b-117">The data file is in native format.</span></span>  
  
-   <span data-ttu-id="0a73b-118">Либо целевая таблица должна быть совместима с файлом данных (иметь верное число столбцов, типы данных, длину, допустимость значений NULL и так далее), либо необходимо использовать файл форматирования для сопоставления каждого поля с соответствующим столбцом.</span><span class="sxs-lookup"><span data-stu-id="0a73b-118">Either the target table must be compatible with the data file (having the correct number of columns, data type, length, NULL status, and so forth), or you must use a format file to map each field to its corresponding columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a73b-119">Если импортируются данные из файла, не совпадающего по структуре с целевой таблицей, то, хотя операция импорта может завершиться успешно, вставляемые в целевую таблицу данные, скорее всего, будут неправильными.</span><span class="sxs-lookup"><span data-stu-id="0a73b-119">If you import data from a file that is mismatched with the target table, the import operation might succeed but the data values inserted into the target table are likely to be incorrect.</span></span> <span data-ttu-id="0a73b-120">Это происходит из-за того, что данные из файла интерпретируются при помощи формата целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="0a73b-120">This is because the data from the file is interpreted by using the format of the target table.</span></span> <span data-ttu-id="0a73b-121">Таким образом, любые различия приведут к вставке неправильных данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-121">Therefore, any mismatch results in the insertion of incorrect values.</span></span> <span data-ttu-id="0a73b-122">Однако ни при каких обстоятельствах подобные различия не могут привести к логическому или физическому несоответствию в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-122">However, under no circumstances can such a mismatch cause logical or physical inconsistencies in the database.</span></span>  
  
     <span data-ttu-id="0a73b-123">Дополнительные сведения см. в разделе [Файлы форматирования для импорта или экспорта данных (SQL Server)](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0a73b-123">For information on using format files, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="0a73b-124">Успешный импорт не приводит к повреждению целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="0a73b-124">A successful import will not corrupt the target table.</span></span>  
  
## <a name="how-bcp-handles-data-in-native-format"></a><span data-ttu-id="0a73b-125">Как bcp обрабатывает данные в собственном формате</span><span class="sxs-lookup"><span data-stu-id="0a73b-125">How bcp Handles Data in Native Format</span></span>  
 <span data-ttu-id="0a73b-126">В этом разделе обсуждаются особые аспекты выполнения программой **bcp** операций экспорта и импорта данных в собственном формате.</span><span class="sxs-lookup"><span data-stu-id="0a73b-126">This section discusses special considerations for how the **bcp** utility exports and imports data in native format.</span></span>  
  
-   <span data-ttu-id="0a73b-127">Несимвольные данные.</span><span class="sxs-lookup"><span data-stu-id="0a73b-127">Noncharacter data</span></span>  
  
     <span data-ttu-id="0a73b-128">Программа bcp использует для записи несимвольных данных из таблицы в файл данных внутренний двоичный формат данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a73b-128">The bcp utility uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internal binary data format to write noncharacter data from a table to a data file.</span></span>  
  
-   <span data-ttu-id="0a73b-129">Данные типа `char` или `varchar`.</span><span class="sxs-lookup"><span data-stu-id="0a73b-129">`char` or `varchar` data</span></span>  
  
     <span data-ttu-id="0a73b-130">В начале каждого `char` `varchar` поля или программа **bcp** добавляет длину префикса.</span><span class="sxs-lookup"><span data-stu-id="0a73b-130">At the beginning of each `char` or `varchar` field, **bcp** adds the prefix length.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0a73b-131">Когда используется собственный режим, программа **bcp** по умолчанию преобразует символы из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в символы OEM перед их копированием в файл данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-131">When native mode is used, by default, the **bcp** utility converts characters from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to OEM characters before it copies them to a data file.</span></span> <span data-ttu-id="0a73b-132">Программа **bcp** преобразует символы из файла данных в символы ANSI перед их массовым импортом в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицу.</span><span class="sxs-lookup"><span data-stu-id="0a73b-132">The **bcp** utility converts characters from a data file to ANSI characters before it bulk imports them into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="0a73b-133">Во время подобных преобразований расширенные символьные данные могут быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="0a73b-133">During these conversions, extended character data can be lost.</span></span> <span data-ttu-id="0a73b-134">Для расширенных наборов символов необходимо либо использовать собственный формат в Юникоде, либо задать кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="0a73b-134">For extended characters, either use Unicode native format or specify a code page.</span></span>  
  
-   <span data-ttu-id="0a73b-135">Данные `sql_variant`.</span><span class="sxs-lookup"><span data-stu-id="0a73b-135">`sql_variant` data</span></span>  
  
     <span data-ttu-id="0a73b-136">Если данные типа `sql_variant` сохраняются как SQLVARIANT в файле данных в собственном формате, то все характеристики данных сохраняются.</span><span class="sxs-lookup"><span data-stu-id="0a73b-136">If `sql_variant` data is stored as a SQLVARIANT in a native-format data file, the data maintains all of its characteristics.</span></span> <span data-ttu-id="0a73b-137">Метаданные, в которых записан тип данных каждой величины, записываются вместе со значениями данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-137">The metadata that records the data type of each data value is stored along with the data value.</span></span> <span data-ttu-id="0a73b-138">Эти метаданные используются для повторного создания значений данных с тем же типом данных, как и в столбце назначения `sql_variant`.</span><span class="sxs-lookup"><span data-stu-id="0a73b-138">This metadata is used to re-create the data value with the same data type in a destination `sql_variant` column.</span></span>  
  
     <span data-ttu-id="0a73b-139">Если в столбце назначения тип данных отличается от `sql_variant`, то каждое значение данных преобразуется в тип данных столбца назначений согласно стандартным правилам неявного преобразования данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-139">If the data type of the destination column is not `sql_variant`, each data value is converted to the data type of the destination column, following the normal rules of implicit data conversion.</span></span> <span data-ttu-id="0a73b-140">При возникновении ошибки во время преобразования данных происходит откат текущего пакета.</span><span class="sxs-lookup"><span data-stu-id="0a73b-140">If an error occurs during data conversion, the current batch is rolled back.</span></span> <span data-ttu-id="0a73b-141">С любыми значениями `char` и `varchar`, которые передаются между столбцами `sql_variant`, могут возникнуть проблемы преобразования кодовых страниц.</span><span class="sxs-lookup"><span data-stu-id="0a73b-141">Any `char` and `varchar` values that are transferred between `sql_variant` columns may have code page conversion issues.</span></span>  
  
     <span data-ttu-id="0a73b-142">Дополнительные сведения о преобразовании данных см. в статье [Преобразование типов данных (ядро СУБД)](/sql/t-sql/data-types/data-type-conversion-database-engine).</span><span class="sxs-lookup"><span data-stu-id="0a73b-142">For more information about data conversion, see [Data Type Conversion &#40;Database Engine&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span></span>  
  
## <a name="command-options-for-native-format"></a><span data-ttu-id="0a73b-143">Параметры командной строки для собственного формата</span><span class="sxs-lookup"><span data-stu-id="0a73b-143">Command Options for Native Format</span></span>  
 <span data-ttu-id="0a73b-144">Данные собственного формата можно импортировать в таблицу с помощью программы **bcp**, BULK INSERT или INSERT... Выбор \* из OPENROWSET (BULK...). Для команды **bcp** или инструкции BULK INSERT можно указать формат данных в командной строке.</span><span class="sxs-lookup"><span data-stu-id="0a73b-144">You can import native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="0a73b-145">Для инструкции INSERT ... SELECT \* FROM OPENROWSET(BULK...) нужно указать формат данных в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="0a73b-145">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="0a73b-146">Собственный формат поддерживается следующими параметрами командной строки:</span><span class="sxs-lookup"><span data-stu-id="0a73b-146">Native format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="0a73b-147">Get-Help</span><span class="sxs-lookup"><span data-stu-id="0a73b-147">Command</span></span>|<span data-ttu-id="0a73b-148">Параметр</span><span class="sxs-lookup"><span data-stu-id="0a73b-148">Option</span></span>|<span data-ttu-id="0a73b-149">Описание</span><span class="sxs-lookup"><span data-stu-id="0a73b-149">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="0a73b-150">**bcp**</span><span class="sxs-lookup"><span data-stu-id="0a73b-150">**bcp**</span></span>|<span data-ttu-id="0a73b-151">**-n**</span><span class="sxs-lookup"><span data-stu-id="0a73b-151">**-n**</span></span>|<span data-ttu-id="0a73b-152">Заставляет служебную программу **bcp** использовать собственные типы данных. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0a73b-152">Causes the **bcp** utility to use the native data types of the data.<sup>1</sup></span></span>|  
|<span data-ttu-id="0a73b-153">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="0a73b-153">BULK INSERT</span></span>|<span data-ttu-id="0a73b-154">DATAFILETYPE **= "** Native **"**</span><span class="sxs-lookup"><span data-stu-id="0a73b-154">DATAFILETYPE **='** native **'**</span></span>|<span data-ttu-id="0a73b-155">Использует собственный тип данных или расширенный собственный тип данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-155">Uses the native or wide native data types of the data.</span></span> <span data-ttu-id="0a73b-156">Учтите, что параметр DATAFILETYPE не нужен, если типы данных указываются в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="0a73b-156">Note that DATAFILETYPE is not needed if a format file specifies the data types.</span></span>|  
  
 <span data-ttu-id="0a73b-157"><sup>1</sup> чтобы загрузить собственные (**-n**) данные в формате, совместимом с предыдущими версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] клиентов, используйте параметр **-V** .</span><span class="sxs-lookup"><span data-stu-id="0a73b-157"><sup>1</sup> To load native (**-n**) data to a format compatible with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients, use the **-V** switch.</span></span> <span data-ttu-id="0a73b-158">Дополнительные сведения см. в разделе [Импорт данных в собственном и символьном формате из предыдущих версий SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0a73b-158">For more information, see [Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span></span>  
  
 <span data-ttu-id="0a73b-159">Дополнительные сведения см. в статьях [Программа bcp](../../tools/bcp-utility.md), [BULK INSERT (SQL Server)](/sql/t-sql/statements/bulk-insert-transact-sql) и [OPENROWSET (SQL Server)](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0a73b-159">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a73b-160">Также в файле форматирования можно указать форматирование для каждого поля.</span><span class="sxs-lookup"><span data-stu-id="0a73b-160">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="0a73b-161">Дополнительные сведения см в разделе [Файлы форматирования для импорта или экспорта данных (SQL Server)](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0a73b-161">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0a73b-162">Примеры</span><span class="sxs-lookup"><span data-stu-id="0a73b-162">Examples</span></span>  
 <span data-ttu-id="0a73b-163">В следующих примерах показан массовый экспорт данных в собственном формате с помощью программы **bcp** , а также массовый импорт тех же данных с помощью инструкции BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="0a73b-163">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="0a73b-164">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="0a73b-164">Sample Table</span></span>  
 <span data-ttu-id="0a73b-165">Для данного примера необходимо, чтобы таблица **myTestNativeData** существовала в образце базы данных **AdventureWorks** в схеме **dbo** .</span><span class="sxs-lookup"><span data-stu-id="0a73b-165">The examples require that a table named **myTestNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="0a73b-166">Перед выполнением примеров следует создать эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="0a73b-166">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="0a73b-167">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="0a73b-167">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="0a73b-168">Чтобы заполнить эту таблицу и просмотреть результирующее содержимое, выполните следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="0a73b-168">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="0a73b-169">Массовый экспорт собственных данных с помощью программы bcp</span><span class="sxs-lookup"><span data-stu-id="0a73b-169">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="0a73b-170">Чтобы экспортировать данные из таблицы в файл данных, используйте команду **bcp** с параметром **out** и следующими квалификаторами:</span><span class="sxs-lookup"><span data-stu-id="0a73b-170">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="0a73b-171">Квалификаторы</span><span class="sxs-lookup"><span data-stu-id="0a73b-171">Qualifiers</span></span>|<span data-ttu-id="0a73b-172">Описание</span><span class="sxs-lookup"><span data-stu-id="0a73b-172">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="0a73b-173">**-n**</span><span class="sxs-lookup"><span data-stu-id="0a73b-173">**-n**</span></span>|<span data-ttu-id="0a73b-174">Указывает собственные типы данных.</span><span class="sxs-lookup"><span data-stu-id="0a73b-174">Specifies native data types.</span></span>|  
|<span data-ttu-id="0a73b-175">**-T**</span><span class="sxs-lookup"><span data-stu-id="0a73b-175">**-T**</span></span>|<span data-ttu-id="0a73b-176">Указывает, что программа **bcp** устанавливает доверительное соединение с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием встроенной безопасности.</span><span class="sxs-lookup"><span data-stu-id="0a73b-176">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="0a73b-177">Если параметр **-T** не указан, для входа необходимо указать **-U** и **-P** .</span><span class="sxs-lookup"><span data-stu-id="0a73b-177">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="0a73b-178">В следующем примере показан массовый экспорт данных в собственном формате из таблицы `myTestNativeData` в новый файл данных с именем `myTestNativeData-n.Dat`.</span><span class="sxs-lookup"><span data-stu-id="0a73b-178">The following example bulk exports data in native format from the `myTestNativeData` table into a new data file named `myTestNativeData-n.Dat` data file.</span></span> <span data-ttu-id="0a73b-179">В командной строке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows введите:</span><span class="sxs-lookup"><span data-stu-id="0a73b-179">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestNativeData out C:\myTestNativeData-n.Dat -n -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="0a73b-180">Массовый импорт собственных данных с помощью инструкции BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="0a73b-180">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="0a73b-181">В следующем примере с помощью инструкции BULK INSERT выполняется импорт данных из файла данных `myTestNativeData-n.Dat` в таблицу `myTestNativeData` .</span><span class="sxs-lookup"><span data-stu-id="0a73b-181">The following example uses BULK INSERT to import the data in the `myTestNativeData-n.Dat` data file into the `myTestNativeData` table.</span></span> <span data-ttu-id="0a73b-182">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="0a73b-182">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestNativeData   
    FROM 'C:\myTestNativeData-n.Dat'   
   WITH (DATAFILETYPE='native');   
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0a73b-183">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="0a73b-183">Related Tasks</span></span>  
 <span data-ttu-id="0a73b-184">**Использование форматов данных для массового импорта или экспорта**</span><span class="sxs-lookup"><span data-stu-id="0a73b-184">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="0a73b-185">Импорт данных в собственном и символьном формате из предыдущих версий SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a73b-185">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="0a73b-186">Использование символьного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0a73b-186">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="0a73b-187">Использование символьного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0a73b-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="0a73b-188">Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0a73b-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a73b-189">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a73b-189">See Also</span></span>  
 <span data-ttu-id="0a73b-190">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0a73b-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="0a73b-191">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0a73b-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="0a73b-192">[Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0a73b-192">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="0a73b-193">[sql_variant (Transact-SQL)](/sql/t-sql/data-types/sql-variant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0a73b-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span></span>  
 <span data-ttu-id="0a73b-194">[Импорт данных в собственном и символьном формате из предыдущих версий SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a73b-194">[Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span></span>  
 <span data-ttu-id="0a73b-195">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0a73b-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="0a73b-196">Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0a73b-196">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
  
