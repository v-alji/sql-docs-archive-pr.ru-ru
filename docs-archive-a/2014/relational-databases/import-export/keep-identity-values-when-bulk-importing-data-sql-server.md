---
title: Сохранение значений идентификаторов при массовом импорте данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- identity values [SQL Server], bulk imports
- data formats [SQL Server], identity values
- bulk importing [SQL Server], identity values
ms.assetid: 45894a3f-2d8a-4edd-9568-afa7d0d3061f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07f6714f27f60afda91134034509ff439d92f071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666594"
---
# <a name="keep-identity-values-when-bulk-importing-data-sql-server"></a><span data-ttu-id="9d506-102">Сохранение значений идентификаторов при массовом импорте данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-102">Keep Identity Values When Bulk Importing Data (SQL Server)</span></span>
  <span data-ttu-id="9d506-103">Файлы данных, содержащие значения идентификаторов, можно импортировать в экземпляр [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d506-103">Data files that contain identity values can be bulk imported into an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9d506-104">По умолчанию значения столбца идентификаторов в импортируемом файле данных не учитываются, и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] автоматически присваивает им уникальные значения</span><span class="sxs-lookup"><span data-stu-id="9d506-104">By default, the values for the identity column in the data file that is imported are ignored and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns unique values automatically.</span></span> <span data-ttu-id="9d506-105">на основе начального значения и значения приращения, указанных при создании таблицы.</span><span class="sxs-lookup"><span data-stu-id="9d506-105">The unique values are based on the seed and increment values that are specified during table creation.</span></span>  
  
 <span data-ttu-id="9d506-106">Если файл данных не содержит значений для столбцов идентификаторов в таблице, то для указания того, что при импорте столбец идентификаторов в таблице нужно пропустить, применяется файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="9d506-106">If the data file does not contain values for the identifier column in the table, use a format file to specify that the identifier column in the table should be skipped when importing data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9d506-107">автоматически присваивает столбцу уникальные значения.</span><span class="sxs-lookup"><span data-stu-id="9d506-107">assigns unique values for the column automatically.</span></span>  
  
 <span data-ttu-id="9d506-108">Чтобы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не присваивал значения идентификаторов при массовом импорте строк в таблицу, используется соответствующий квалификатор команды для сохранения значений идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="9d506-108">To prevent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from assigning identity values while bulk importing data rows into a table, use the appropriate keep-identity command qualifier.</span></span> <span data-ttu-id="9d506-109">При указании квалификатора сохранения значений идентификаторов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пользуется значениями идентификаторов, имеющимися в файле данных.</span><span class="sxs-lookup"><span data-stu-id="9d506-109">When you specify a keep-identity qualifier, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the identity values in the data file.</span></span> <span data-ttu-id="9d506-110">Ниже приведены эти квалификаторы.</span><span class="sxs-lookup"><span data-stu-id="9d506-110">These qualifiers are as follows:</span></span>  
  
|<span data-ttu-id="9d506-111">Get-Help</span><span class="sxs-lookup"><span data-stu-id="9d506-111">Command</span></span>|<span data-ttu-id="9d506-112">Квалификатор сохранения значений идентификаторов</span><span class="sxs-lookup"><span data-stu-id="9d506-112">Keep-identity qualifier</span></span>|<span data-ttu-id="9d506-113">Тип квалификатора</span><span class="sxs-lookup"><span data-stu-id="9d506-113">Qualifier type</span></span>|  
|-------------|------------------------------|--------------------|  
|`bcp`|<span data-ttu-id="9d506-114">**-E**</span><span class="sxs-lookup"><span data-stu-id="9d506-114">**-E**</span></span>|<span data-ttu-id="9d506-115">Параметр</span><span class="sxs-lookup"><span data-stu-id="9d506-115">Switch</span></span>|  
|<span data-ttu-id="9d506-116">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="9d506-116">BULK INSERT</span></span>|<span data-ttu-id="9d506-117">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="9d506-117">KEEPIDENTITY</span></span>|<span data-ttu-id="9d506-118">Аргумент</span><span class="sxs-lookup"><span data-stu-id="9d506-118">Argument</span></span>|  
|<span data-ttu-id="9d506-119">Инструкции INSERT ... SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="9d506-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="9d506-120">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="9d506-120">KEEPIDENTITY</span></span>|<span data-ttu-id="9d506-121">Табличное указание</span><span class="sxs-lookup"><span data-stu-id="9d506-121">Table hint</span></span>|  
  
 <span data-ttu-id="9d506-122">Дополнительные сведения см. в статьях [Программа bcp](../../tools/bcp-utility.md), [BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql), [INSERT (Transact-SQL)](/sql/t-sql/statements/insert-transact-sql), [SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) и [Табличные указания (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-table).</span><span class="sxs-lookup"><span data-stu-id="9d506-122">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d506-123">Сведения о том, как создать автоматически увеличивающееся числовое значение, которое может использоваться в нескольких таблицах или вызываться из приложений без ссылки на какие-либо таблицы, см. в разделе [Порядковые номера](../sequence-numbers/sequence-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="9d506-123">To create an automatically incrementing number that can be used in multiple tables or that can be called from applications without referencing any table, see [Sequence Numbers](../sequence-numbers/sequence-numbers.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9d506-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="9d506-124">Examples</span></span>  
 <span data-ttu-id="9d506-125">Примеры в этом разделе используются для импорта данных с помощью инструкции INSERT... Выберите \* из OPENROWSET (BULK...) и сохранив значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d506-125">The examples in this topic bulk import data using INSERT ... SELECT \* FROM OPENROWSET(BULK...) and keeping default values.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="9d506-126">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="9d506-126">Sample Table</span></span>  
 <span data-ttu-id="9d506-127">Примеры массового импорта требуют, чтобы в образце базы данных **AdventureWorks** в схеме **dbo** была создана таблица с именем **myTestKeepNulls**.</span><span class="sxs-lookup"><span data-stu-id="9d506-127">The bulk-import examples require that a table named **myTestKeepNulls** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="9d506-128">Для создания такой таблицы:</span><span class="sxs-lookup"><span data-stu-id="9d506-128">To create this table.</span></span> <span data-ttu-id="9d506-129">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="9d506-129">in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT * INTO HumanResources.myDepartment   
   FROM HumanResources.Department  
      WHERE 1=0;  
GO  
SELECT * FROM HumanResources.myDepartment;  
```  
  
 <span data-ttu-id="9d506-130">В таблице **Department**, на которой основана таблица `myDepartment`, IDENTITY_INSERT имеет значение OFF.</span><span class="sxs-lookup"><span data-stu-id="9d506-130">The **Department** table on which `myDepartment` is based has IDENTITY_INSERT is set to OFF.</span></span> <span data-ttu-id="9d506-131">Поэтому для импорта данных в столбец идентификаторов необходимо указать KEEPIDENTITY или **-E**.</span><span class="sxs-lookup"><span data-stu-id="9d506-131">Therefore, to import data into an identity column you must specify KEEPIDENTITY or **-E**.</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="9d506-132">Образец файла данных</span><span class="sxs-lookup"><span data-stu-id="9d506-132">Sample Data File</span></span>  
 <span data-ttu-id="9d506-133">Файл данных, который используется в примерах массового импорта, содержит данные, экспортированные из таблицы `HumanResources.Department` в собственном формате.</span><span class="sxs-lookup"><span data-stu-id="9d506-133">The data file used in the bulk-import examples contains data bulk exported from the `HumanResources.Department` table in native format.</span></span> <span data-ttu-id="9d506-134">Для создания файла данных введите в командной строке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows:</span><span class="sxs-lookup"><span data-stu-id="9d506-134">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department out myDepartment-n.Dat -n -T  
```  
  
### <a name="sample-format-file"></a><span data-ttu-id="9d506-135">Образец файла форматирования</span><span class="sxs-lookup"><span data-stu-id="9d506-135">Sample Format File</span></span>  
 <span data-ttu-id="9d506-136">В этих примерах массового импорта применяется XML-файл форматирования `myDepartment-f-x-n.Xml`, использующий собственные форматы данных.</span><span class="sxs-lookup"><span data-stu-id="9d506-136">This bulk-import examples use an XML format file, `myDepartment-f-x-n.Xml`, which uses native data formats.</span></span> <span data-ttu-id="9d506-137">В этом примере `bcp` используется для создания данного файла форматирования из таблицы `HumanResources.Department` базы данных `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="9d506-137">This example uses `bcp` to create to generate this format file from the `HumanResources.Department` table of the `AdventureWorks` database.</span></span> <span data-ttu-id="9d506-138">В командной строке Windows введите:</span><span class="sxs-lookup"><span data-stu-id="9d506-138">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department format nul -n -x -f myDepartment-f-n-x.Xml -T  
```  
  
 <span data-ttu-id="9d506-139">Дополнительные сведения о создании файла форматирования см. в разделе [Создание файла форматирования (SQL Server)](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d506-139">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="a-using-bcp-and-keeping-identity-values"></a><span data-ttu-id="9d506-140">A.</span><span class="sxs-lookup"><span data-stu-id="9d506-140">A.</span></span> <span data-ttu-id="9d506-141">Использование команды bcp с сохранением значений идентификаторов</span><span class="sxs-lookup"><span data-stu-id="9d506-141">Using bcp and Keeping Identity Values</span></span>  
 <span data-ttu-id="9d506-142">В следующем примере показан способ сохранения значений идентификаторов при использовании команды `bcp` для массового импорта данных.</span><span class="sxs-lookup"><span data-stu-id="9d506-142">The following example demonstrates how to keep identity values when using `bcp` to bulk import data.</span></span> <span data-ttu-id="9d506-143">Команда `bcp` использует файл форматирования `myDepartment-f-n-x.Xml` и содержит следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9d506-143">The `bcp` command uses the format file, `myDepartment-f-n-x.Xml`, and contains the following switches:</span></span>  
  
|<span data-ttu-id="9d506-144">Квалификаторы</span><span class="sxs-lookup"><span data-stu-id="9d506-144">Qualifiers</span></span>|<span data-ttu-id="9d506-145">Описание</span><span class="sxs-lookup"><span data-stu-id="9d506-145">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="9d506-146">**-E**</span><span class="sxs-lookup"><span data-stu-id="9d506-146">**-E**</span></span>|<span data-ttu-id="9d506-147">Указывает, что в столбец идентификаторов загружаются значения идентификаторов, находящиеся в файле данных.</span><span class="sxs-lookup"><span data-stu-id="9d506-147">Specifies that identity value or values in the data file are to be used for the identity column.</span></span>|  
|<span data-ttu-id="9d506-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="9d506-148">**-T**</span></span>|<span data-ttu-id="9d506-149">Указывает, что `bcp` программа подключается к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с доверенным соединением.</span><span class="sxs-lookup"><span data-stu-id="9d506-149">Specifies that the `bcp` utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="9d506-150">В командной строке Windows введите:</span><span class="sxs-lookup"><span data-stu-id="9d506-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myDepartment in C:\myDepartment-n.Dat -f C:\myDepartment-f-n-x.Xml -E -T  
  
```  
  
### <a name="b-using-bulk-insert-and-keeping-identity-values"></a><span data-ttu-id="9d506-151">Б.</span><span class="sxs-lookup"><span data-stu-id="9d506-151">B.</span></span> <span data-ttu-id="9d506-152">Использование BULK INSERT с сохранением значений идентификаторов</span><span class="sxs-lookup"><span data-stu-id="9d506-152">Using BULK INSERT and Keeping Identity Values</span></span>  
 <span data-ttu-id="9d506-153">В следующем примере BULK INSERT используется для массового импорта данных из файла `myDepartment-c.Dat` в таблицу `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="9d506-153">The following example uses BULK INSERT to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="9d506-154">Инструкция использует файл форматирования `myDepartment-f-n-x.Xml` и включает параметр KEEPIDENTITY для сохранения значений идентификаторов, находящихся в файле данных.</span><span class="sxs-lookup"><span data-stu-id="9d506-154">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY option to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="9d506-155">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="9d506-155">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
BULK INSERT HumanResources.myDepartment  
   FROM 'C:\myDepartment-n.Dat'  
   WITH (  
      KEEPIDENTITY,  
      FORMATFILE='C:\myDepartment-f-n-x.Xml'  
   );  
GO  
SELECT * FROM HumanResources.myDepartment;  
  
```  
  
### <a name="c-using-openrowset-and-keeping-identity-values"></a><span data-ttu-id="9d506-156">В.</span><span class="sxs-lookup"><span data-stu-id="9d506-156">C.</span></span> <span data-ttu-id="9d506-157">Использование OPENROWSET с сохранением значений идентификаторов</span><span class="sxs-lookup"><span data-stu-id="9d506-157">Using OPENROWSET and Keeping Identity Values</span></span>  
 <span data-ttu-id="9d506-158">В следующем примере поставщик наборов строк OPENROWSET используется для массового импорта данных из файла `myDepartment-c.Dat` в таблицу `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="9d506-158">The following example uses the OPENROWSET bulk rowset provider to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="9d506-159">Инструкция использует файл форматирования `myDepartment-f-n-x.Xml` и включает указание KEEPIDENTITY для сохранения всех значений идентификаторов, содержащихся в файле данных.</span><span class="sxs-lookup"><span data-stu-id="9d506-159">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY hint to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="9d506-160">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="9d506-160">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
  
INSERT INTO HumanResources.myDepartment  
   with (KEEPIDENTITY)  
   (DepartmentID, Name, GroupName, ModifiedDate)  
   SELECT *  
      FROM  OPENROWSET(BULK 'C:\myDepartment-n.Dat',  
      FORMATFILE='C:\myDepartment-f-n-x.Xml') as t1;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9d506-161">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9d506-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9d506-162">Сохранение значений NULL или использование значений по умолчанию при массовом импорте данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-162">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="9d506-163">Подготовка данных к массовому экспорту или импорту (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-163">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="9d506-164">**Использование файла форматирования**</span><span class="sxs-lookup"><span data-stu-id="9d506-164">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="9d506-165">Создание файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-165">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="9d506-166">Использование файла форматирования для массового импорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-166">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="9d506-167">Использование файла форматирования для сопоставления столбцов таблицы с полями файла данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-167">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="9d506-168">Использование файла форматирования для пропуска поля данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-168">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="9d506-169">Пропуск столбца таблицы с помощью файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-169">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="9d506-170">**Использование форматов данных для массового импорта или экспорта**</span><span class="sxs-lookup"><span data-stu-id="9d506-170">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="9d506-171">Импорт данных в собственном и символьном формате из предыдущих версий SQL Server</span><span class="sxs-lookup"><span data-stu-id="9d506-171">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="9d506-172">Использование символьного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-172">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="9d506-173">Использование собственного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-173">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="9d506-174">Использование символьного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-174">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="9d506-175">Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-175">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="9d506-176">**Задание форматов данных для совместимости с помощью программы bcp**</span><span class="sxs-lookup"><span data-stu-id="9d506-176">**To specify data formats for compatibility when using bcp**</span></span>  
  
1.  [<span data-ttu-id="9d506-177">Определение признаков конца поля и строки (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-177">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
2.  [<span data-ttu-id="9d506-178">Определение длины префикса в файлах данных с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-178">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
3.  [<span data-ttu-id="9d506-179">Указание типа файлового хранилища с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d506-179">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="9d506-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d506-180">See Also</span></span>  
 <span data-ttu-id="9d506-181">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d506-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="9d506-182">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="9d506-182">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="9d506-183">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d506-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="9d506-184">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d506-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="9d506-185">Табличные указания (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9d506-185">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
