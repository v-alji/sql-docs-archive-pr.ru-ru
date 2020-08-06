---
title: Использование собственного формата Юникода для импорта или экспорта данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- Unicode [SQL Server], bulk importing and exporting
- data formats [SQL Server], Unicode native
ms.assetid: a6213308-f3d5-406e-9029-19d8bb3367f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beae2f836de16dedf3be6d8c196910c53be02266
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749920"
---
# <a name="use-unicode-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="1ee60-102">Использование собственного формата Юникода для импорта или экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1ee60-102">Use Unicode Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="1ee60-103">Собственный формат Юникода может быть полезен при копировании данных из одной установки [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в другую.</span><span class="sxs-lookup"><span data-stu-id="1ee60-103">Unicode native format is helpful when information must be copied from one [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation to another.</span></span> <span data-ttu-id="1ee60-104">Использование собственного формата для несимвольных данных позволяет сэкономить время благодаря исключению ненужных преобразований типов данных в символьный формат и обратно.</span><span class="sxs-lookup"><span data-stu-id="1ee60-104">The use of native format for noncharacter data saves time, eliminating unnecessary conversion of data types to and from character format.</span></span> <span data-ttu-id="1ee60-105">Использование символьного формата Юникода для всех символьных данных предотвращает потерю дополнительных символов в ходе массовой передачи данных между серверами, использующими различные кодовые страницы.</span><span class="sxs-lookup"><span data-stu-id="1ee60-105">The use of Unicode character format for all character data prevents loss of any extended characters during bulk transfer of data between servers using different code pages.</span></span> <span data-ttu-id="1ee60-106">Файл данных в собственном формате Юникода может быть считан с помощью любого метода массового импорта.</span><span class="sxs-lookup"><span data-stu-id="1ee60-106">A data file in Unicode native format can be read by any bulk-import method.</span></span>  
  
 <span data-ttu-id="1ee60-107">Собственный формат Юникода рекомендуется использовать для массовой передачи данных между несколькими экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью файла данных, который содержит дополнительный набор символов или символы в кодировке DBCS.</span><span class="sxs-lookup"><span data-stu-id="1ee60-107">Unicode native format is recommended for the bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span> <span data-ttu-id="1ee60-108">В отношении несимвольных данных собственный формат Юникода использует собственные (для базы данных) типы данных.</span><span class="sxs-lookup"><span data-stu-id="1ee60-108">For noncharacter data, Unicode native format uses native (database) data types.</span></span> <span data-ttu-id="1ee60-109">В отношении символьных данных, таких как `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)` и `ntext`, собственный формат Юникода использует формат данных Юникода.</span><span class="sxs-lookup"><span data-stu-id="1ee60-109">For character data, such as `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)`, and `ntext`, the Unicode native format uses Unicode character data format.</span></span>  
  
 <span data-ttu-id="1ee60-110">Данные типа `sql_variant`, которые хранятся в виде инструкции SQLVARIANT в файле собственного формата Юникода, функционируют точно так, как в файле данных собственного формата, за исключением того, что значения типа `char` и `varchar` преобразуются в `nchar` и `nvarchar`, что требует вдвое больше места для хранения столбцов, подлежащих преобразованию.</span><span class="sxs-lookup"><span data-stu-id="1ee60-110">The `sql_variant` data that is stored as a SQLVARIANT in a Unicode native-format data file operates in the same manner as it does in a native-format data file, except that `char` and `varchar` values are converted to `nchar` and `nvarchar`, which doubles the amount of storage required for the affected columns.</span></span> <span data-ttu-id="1ee60-111">В процессе массового импорта в столбец таблицы исходные метаданные сохраняются, а значения преобразуются обратно в исходные типы данных `char` и `varchar`.</span><span class="sxs-lookup"><span data-stu-id="1ee60-111">The original metadata is preserved, and the values are converted back to their original `char` and `varchar` data type when bulk imported into a table column.</span></span>  
  
## <a name="command-options-for-unicode-native-format"></a><span data-ttu-id="1ee60-112">Командные параметры для собственного формата Юникода</span><span class="sxs-lookup"><span data-stu-id="1ee60-112">Command Options for Unicode Native Format</span></span>  
 <span data-ttu-id="1ee60-113">Вы можете импортировать данные в собственном формате Юникода в таблицу с помощью программы **bcp**, BULK INSERT или INSERT... Выбор \* из OPENROWSET (BULK...). Для команды **bcp** или инструкции BULK INSERT можно указать формат данных в командной строке.</span><span class="sxs-lookup"><span data-stu-id="1ee60-113">You can import Unicode native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="1ee60-114">Для инструкции INSERT ... SELECT \* FROM OPENROWSET(BULK...) нужно указать формат данных в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="1ee60-114">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="1ee60-115">Собственный формат Юникода поддерживается следующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="1ee60-115">Unicode native format is supported by the following options:</span></span>  
  
|<span data-ttu-id="1ee60-116">Get-Help</span><span class="sxs-lookup"><span data-stu-id="1ee60-116">Command</span></span>|<span data-ttu-id="1ee60-117">Параметр</span><span class="sxs-lookup"><span data-stu-id="1ee60-117">Option</span></span>|<span data-ttu-id="1ee60-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1ee60-118">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="1ee60-119">**bcp**</span><span class="sxs-lookup"><span data-stu-id="1ee60-119">**bcp**</span></span>|<span data-ttu-id="1ee60-120">**-N**</span><span class="sxs-lookup"><span data-stu-id="1ee60-120">**-N**</span></span>|<span data-ttu-id="1ee60-121">Заставляет служебную программу **bcp** использовать собственный формат Юникода, в котором используются собственные типы данных (базы данных) для всех несимвольных данных и формат символьных данных Юникода для всех символьных данных (,,,, `char` `nchar` `varchar` `nvarchar` `text` и `ntext` ).</span><span class="sxs-lookup"><span data-stu-id="1ee60-121">Causes the **bcp** utility to use the Unicode native format, which uses native (database) data types for all noncharacter data and Unicode character data format for all character (`char`, `nchar`, `varchar`, `nvarchar`, `text`, and `ntext`) data.</span></span>|  
|<span data-ttu-id="1ee60-122">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="1ee60-122">BULK INSERT</span></span>|<span data-ttu-id="1ee60-123">DATAFILETYPE **= '** widenative **'**</span><span class="sxs-lookup"><span data-stu-id="1ee60-123">DATAFILETYPE **='** widenative **'**</span></span>|<span data-ttu-id="1ee60-124">Собственный формат Юникода используется при массовом импорте данных.</span><span class="sxs-lookup"><span data-stu-id="1ee60-124">Use Unicode native format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="1ee60-125">Дополнительные сведения см. в статьях [Программа bcp](../../tools/bcp-utility.md), [BULK INSERT (SQL Server)](/sql/t-sql/statements/bulk-insert-transact-sql) и [OPENROWSET (SQL Server)](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1ee60-125">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ee60-126">Также в файле форматирования можно указать форматирование для каждого поля.</span><span class="sxs-lookup"><span data-stu-id="1ee60-126">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="1ee60-127">Дополнительные сведения см в разделе [Файлы форматирования для импорта или экспорта данных (SQL Server)](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1ee60-127">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1ee60-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="1ee60-128">Examples</span></span>  
 <span data-ttu-id="1ee60-129">В следующих примерах показан массовый экспорт данных в собственном формате с помощью программы **bcp** , а также массовый импорт тех же данных с помощью инструкции BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="1ee60-129">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="1ee60-130">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="1ee60-130">Sample Table</span></span>  
 <span data-ttu-id="1ee60-131">Для использования в примерах необходимо создать таблицу **myTestUniNativeData** в образце базы данных **AdventureWorks** под схемой **dbo** .</span><span class="sxs-lookup"><span data-stu-id="1ee60-131">The examples require that a table named **myTestUniNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="1ee60-132">Перед выполнением примеров следует создать эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="1ee60-132">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="1ee60-133">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="1ee60-133">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestUniNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="1ee60-134">Чтобы заполнить эту таблицу и просмотреть результирующее содержимое, выполните следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="1ee60-134">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="1ee60-135">Массовый экспорт собственных данных с помощью программы bcp</span><span class="sxs-lookup"><span data-stu-id="1ee60-135">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="1ee60-136">Чтобы экспортировать данные из таблицы в файл данных, используйте команду **bcp** с параметром **out** и следующими квалификаторами:</span><span class="sxs-lookup"><span data-stu-id="1ee60-136">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="1ee60-137">Квалификаторы</span><span class="sxs-lookup"><span data-stu-id="1ee60-137">Qualifiers</span></span>|<span data-ttu-id="1ee60-138">Описание</span><span class="sxs-lookup"><span data-stu-id="1ee60-138">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="1ee60-139">**-N**</span><span class="sxs-lookup"><span data-stu-id="1ee60-139">**-N**</span></span>|<span data-ttu-id="1ee60-140">Указывает собственные типы данных.</span><span class="sxs-lookup"><span data-stu-id="1ee60-140">Specifies native data types.</span></span>|  
|<span data-ttu-id="1ee60-141">**-T**</span><span class="sxs-lookup"><span data-stu-id="1ee60-141">**-T**</span></span>|<span data-ttu-id="1ee60-142">Указывает, что программа **bcp** устанавливает доверительное соединение с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием встроенной безопасности.</span><span class="sxs-lookup"><span data-stu-id="1ee60-142">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="1ee60-143">Если параметр **-T** не указан, для входа необходимо указать **-U** и **-P** .</span><span class="sxs-lookup"><span data-stu-id="1ee60-143">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="1ee60-144">В следующем примере показан массовый экспорт данных в собственном формате из таблицы `myTestUniNativeData` в новый файл данных с именем `myTestUniNativeData-N.Dat`.</span><span class="sxs-lookup"><span data-stu-id="1ee60-144">The following example bulk exports data in native format from the `myTestUniNativeData` table into a new data file named `myTestUniNativeData-N.Dat` data file.</span></span> <span data-ttu-id="1ee60-145">В командной строке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows введите:</span><span class="sxs-lookup"><span data-stu-id="1ee60-145">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestUniNativeData out C:\myTestUniNativeData-N.Dat -N -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="1ee60-146">Массовый импорт собственных данных с помощью инструкции BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="1ee60-146">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="1ee60-147">В следующем примере с помощью инструкции BULK INSERT выполняется импорт данных из файла данных `myTestUniNativeData-N.Dat` в таблицу `myTestUniNativeData` .</span><span class="sxs-lookup"><span data-stu-id="1ee60-147">The following example uses BULK INSERT to import the data in the `myTestUniNativeData-N.Dat` data file into the `myTestUniNativeData` table.</span></span> <span data-ttu-id="1ee60-148">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="1ee60-148">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestUniNativeData   
    FROM 'C:\myTestUniNativeData-N.Dat'   
   WITH (DATAFILETYPE='widenative');   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1ee60-149">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1ee60-149">Related Tasks</span></span>  
 <span data-ttu-id="1ee60-150">**Использование форматов данных для массового импорта или экспорта**</span><span class="sxs-lookup"><span data-stu-id="1ee60-150">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="1ee60-151">Импорт данных в собственном и символьном формате из предыдущих версий SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ee60-151">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="1ee60-152">Использование символьного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1ee60-152">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="1ee60-153">Использование собственного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1ee60-153">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="1ee60-154">Использование символьного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1ee60-154">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="1ee60-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ee60-155">See Also</span></span>  
 <span data-ttu-id="1ee60-156">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="1ee60-156">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="1ee60-157">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ee60-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="1ee60-158">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ee60-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="1ee60-159">Типы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1ee60-159">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
