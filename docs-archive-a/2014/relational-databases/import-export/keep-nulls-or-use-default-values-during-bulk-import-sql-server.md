---
title: Сохранение значений NULL или использование значений по умолчанию при массовом импорте данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], null values
- bulk importing [SQL Server], default values
- data formats [SQL Server], null values
- bulk rowset providers [SQL Server]
- bcp utility [SQL Server], null values
- BULK INSERT statement
- default values
- OPENROWSET function, bulk importing
- data formats [SQL Server], default values
ms.assetid: 6b91d762-337b-4345-a159-88abb3e64a81
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 856aa12f6ad5e5094324e0df65941bc63d611451
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749951"
---
# <a name="keep-nulls-or-use-default-values-during-bulk-import-sql-server"></a><span data-ttu-id="fc05e-102">Сохранение значений NULL или использование значений по умолчанию при массовом импорте данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-102">Keep Nulls or Use Default Values During Bulk Import (SQL Server)</span></span>
  <span data-ttu-id="fc05e-103">При импорте данных в таблицу команда **bcp** и инструкция BULK INSERT используют значения по умолчанию, которые определены для столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="fc05e-103">By default, when data is imported into a table, the **bcp** command and BULK INSERT statement observe any defaults that are defined for the columns in the table.</span></span> <span data-ttu-id="fc05e-104">Например, если поле в файле данных имеет значение NULL, вместо него загружается значение по умолчанию соответствующего столбца.</span><span class="sxs-lookup"><span data-stu-id="fc05e-104">For example, if there is a null field in a data file, the default value for the column is loaded instead.</span></span> <span data-ttu-id="fc05e-105">И команда **bcp** , и инструкция BULK INSERT позволяют пользователю указать, следует ли оставлять значения NULL.</span><span class="sxs-lookup"><span data-stu-id="fc05e-105">The **bcp** command and BULK INSERT statement both allow you to specify that nulls values be retained.</span></span>  
  
 <span data-ttu-id="fc05e-106">Обычная инструкция INSERT, напротив, оставляет значение NULL и не использует значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc05e-106">In contrast, a regular INSERT statement retains the null value instead of inserting a default value.</span></span> <span data-ttu-id="fc05e-107">Инструкция INSERT ... Инструкция SELECT \* FROM OPENROWSET(BULK...) ведет себя так же, как обычная инструкция INSERT, но поддерживает табличное указание для загрузки значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc05e-107">The INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement provides the same basic behavior as regular INSERT but additionally supports a table hint for inserting the default values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc05e-108">Пример файла форматирования, пропускающего столбец таблицы, см. в статье [Пропуск столбца таблицы с помощью файла форматирования (SQL Server)](use-a-format-file-to-skip-a-table-column-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fc05e-108">For sample format files that skip a table column, see [Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="fc05e-109">Образец таблицы и файла данных</span><span class="sxs-lookup"><span data-stu-id="fc05e-109">Sample Table and Data File</span></span>  
 <span data-ttu-id="fc05e-110">Для выполнения примеров этого подраздела необходимо создать образец таблицы и файла данных.</span><span class="sxs-lookup"><span data-stu-id="fc05e-110">To run the examples in this topic, you need to create a sample table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="fc05e-111">Образец таблицы</span><span class="sxs-lookup"><span data-stu-id="fc05e-111">Sample Table</span></span>  
 <span data-ttu-id="fc05e-112">Для выполнения примеров этого раздела требуется создать таблицу **MyTestDefaultCol2** в образце базы данных **AdventureWorks** в схеме **dbo**.</span><span class="sxs-lookup"><span data-stu-id="fc05e-112">The examples require that a table named **MyTestDefaultCol2** be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="fc05e-113">Чтобы создать эту таблицу, в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] редакторе запросов выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fc05e-113">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE MyTestDefaultCol2   
(Col1 smallint,  
Col2 nvarchar(50) DEFAULT 'Default value of Col2',  
Col3 nvarchar(50)   
);  
GO  
  
```  
  
 <span data-ttu-id="fc05e-114">Заметьте, что во втором столбце таблицы (`Col2`) хранится значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc05e-114">Notice that the second table column, `Col2`, has a default value.</span></span>  
  
### <a name="sample-format-file"></a><span data-ttu-id="fc05e-115">Образец файла форматирования</span><span class="sxs-lookup"><span data-stu-id="fc05e-115">Sample Format File</span></span>  
 <span data-ttu-id="fc05e-116">Некоторые примеры массового импорта используют не XML-файл форматирования `MyTestDefaultCol2-f-c.Fmt`, в точности соответствующий таблице `MyTestDefaultCol2`.</span><span class="sxs-lookup"><span data-stu-id="fc05e-116">Some of the bulk-import examples use a non-XML format file, `MyTestDefaultCol2-f-c.Fmt` that corresponds exactly to the `MyTestDefaultCol2` table.</span></span> <span data-ttu-id="fc05e-117">Для создания этого файла форматирования в командной строке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="fc05e-117">To create this format file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 format nul -c -f C:\MyTestDefaultCol2-f-c.Fmt -t, -r\n -T  
  
```  
  
 <span data-ttu-id="fc05e-118">Дополнительные сведения о создании файла форматирования см. в статье [Создание файла форматирования (SQL Server)](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fc05e-118">For more information about creating format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="fc05e-119">Образец файла данных</span><span class="sxs-lookup"><span data-stu-id="fc05e-119">Sample Data File</span></span>  
 <span data-ttu-id="fc05e-120">Следующий пример использует образец файла данных `MyTestEmptyField2-c.Dat`, второе поле которого не содержит значений.</span><span class="sxs-lookup"><span data-stu-id="fc05e-120">The example uses a sample data file, `MyTestEmptyField2-c.Dat`, that contains no values in the second field.</span></span> <span data-ttu-id="fc05e-121">Файл данных `MyTestEmptyField2-c.Dat` содержит следующие записи.</span><span class="sxs-lookup"><span data-stu-id="fc05e-121">The `MyTestEmptyField2-c.Dat` data file contains the following records.</span></span>  
  
```  
1,,DataField3  
2,,DataField3  
  
```  
  
## <a name="keeping-null-values-with-bcp-or-bulk-insert"></a><span data-ttu-id="fc05e-122">Сохранение значение NULL при работе с командой bcp или инструкцией BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="fc05e-122">Keeping Null Values with bcp or BULK INSERT</span></span>  
 <span data-ttu-id="fc05e-123">Следующие квалификаторы указывают, что вместо пустого поля в файле данных необходимо вставить не значение по умолчанию, а значение NULL.</span><span class="sxs-lookup"><span data-stu-id="fc05e-123">The following qualifiers specify that an empty field in the data file retains its null value during the bulk-import operation, rather than inheriting a default value (if any) for the table columns.</span></span>  
  
|<span data-ttu-id="fc05e-124">Get-Help</span><span class="sxs-lookup"><span data-stu-id="fc05e-124">Command</span></span>|<span data-ttu-id="fc05e-125">Квалификатор</span><span class="sxs-lookup"><span data-stu-id="fc05e-125">Qualifier</span></span>|<span data-ttu-id="fc05e-126">Тип квалификатора</span><span class="sxs-lookup"><span data-stu-id="fc05e-126">Qualifier type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="fc05e-127">**bcp**</span><span class="sxs-lookup"><span data-stu-id="fc05e-127">**bcp**</span></span>|`-k`|<span data-ttu-id="fc05e-128">Параметр</span><span class="sxs-lookup"><span data-stu-id="fc05e-128">Switch</span></span>|  
|<span data-ttu-id="fc05e-129">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="fc05e-129">BULK INSERT</span></span>|<span data-ttu-id="fc05e-130">KEEPNULLS<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fc05e-130">KEEPNULLS<sup>1</sup></span></span>|<span data-ttu-id="fc05e-131">Аргумент</span><span class="sxs-lookup"><span data-stu-id="fc05e-131">Argument</span></span>|  
  
 <span data-ttu-id="fc05e-132"><sup>1</sup> для BULK INSERT, если значения по умолчанию недоступны, столбец таблицы должен быть определен для разрешения значений NULL.</span><span class="sxs-lookup"><span data-stu-id="fc05e-132"><sup>1</sup> For BULK INSERT, if default values are not available, the table column must be defined to allow null values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc05e-133">Эти квалификаторы отключают проверку определений DEFAULT для таблицы командами массового импорта.</span><span class="sxs-lookup"><span data-stu-id="fc05e-133">These qualifiers disable checking of DEFAULT definitions on a table by these bulk-import commands.</span></span> <span data-ttu-id="fc05e-134">Однако для одновременно выполняемых инструкций INSERT определения DEFAULT требуются.</span><span class="sxs-lookup"><span data-stu-id="fc05e-134">However, for any concurrent INSERT statements, DEFAULT definitions are expected.</span></span>  
  
 <span data-ttu-id="fc05e-135">Дополнительные сведения см. в статьях [Программа bcp](../../tools/bcp-utility.md) и [BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fc05e-135">For more information, see [bcp Utility](../../tools/bcp-utility.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="fc05e-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="fc05e-136">Examples</span></span>  
 <span data-ttu-id="fc05e-137">Примеры в этом разделе показывают, как выполнить массовый импорт данных с помощью команды **bcp** или инструкции BULK INSERT и сохранить значения NULL.</span><span class="sxs-lookup"><span data-stu-id="fc05e-137">The examples in this section bulk import using **bcp** or BULK INSERT and keep null values.</span></span>  
  
 <span data-ttu-id="fc05e-138">Для второго столбца таблицы (**Col2**) задано значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc05e-138">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="fc05e-139">Соответствующее поле файла данных содержит пустые строки.</span><span class="sxs-lookup"><span data-stu-id="fc05e-139">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="fc05e-140">По умолчанию при импорте данных из этого файла в таблицу **MyTestDefaultCol2** с помощью команды **bcp** или инструкции BULK INSERT вставляется значение по умолчанию столбца **Col2**, что приводит к получению следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="fc05e-140">By default, when **bcp** or BULK INSERT is used to import data from this data file into the **MyTestDefaultCol2** table, the default value of **Col2** is inserted, producing the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`Default value of Col2`|`DataField3`|  
|`2`|`Default value of Col2`|`DataField3`|  
  
 <span data-ttu-id="fc05e-141">Чтобы вставить " `NULL` " вместо " `Default value of Col2` ", необходимо использовать `-k` параметр Switch или keepnull (см, как показано в следующих примерах **bcp** и BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="fc05e-141">To insert "`NULL`" instead of "`Default value of Col2`", you need to use the `-k` switch or KEEPNULL option, as demonstrated in the following **bcp** and BULK INSERT examples.</span></span>  
  
#### <a name="using-bcp-and-keeping-null-values"></a><span data-ttu-id="fc05e-142">Сохранение значений NULL при работе с командой bcp</span><span class="sxs-lookup"><span data-stu-id="fc05e-142">Using bcp and Keeping Null Values</span></span>  
 <span data-ttu-id="fc05e-143">Следующий пример демонстрирует, как сохранить значения NULL при использовании команды **bcp**.</span><span class="sxs-lookup"><span data-stu-id="fc05e-143">The following example demonstrates how to keep null values in a **bcp** command.</span></span> <span data-ttu-id="fc05e-144">Команда **bcp** содержит следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fc05e-144">The **bcp** command contains the following switches:</span></span>  
  
|<span data-ttu-id="fc05e-145">Параметр</span><span class="sxs-lookup"><span data-stu-id="fc05e-145">Switch</span></span>|<span data-ttu-id="fc05e-146">Описание</span><span class="sxs-lookup"><span data-stu-id="fc05e-146">Description</span></span>|  
|------------|-----------------|  
|`-f`|<span data-ttu-id="fc05e-147">Позволяет указать файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="fc05e-147">Specifies that the command is using a format file..</span></span>|  
|`-k`|<span data-ttu-id="fc05e-148">Указывает, что пустые столбцы во время данной операции должны сохранить значение NULL вместо любых вставляемых значений столбцов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc05e-148">Specifies that empty columns should retain a null value during the operation, rather than have any default values for the columns inserted.</span></span>|  
|`-T`|<span data-ttu-id="fc05e-149">Указывает, что программа bcp подключается к серверу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], используя доверительное соединение.</span><span class="sxs-lookup"><span data-stu-id="fc05e-149">Specifies that the bcp utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="fc05e-150">В командной строке Windows введите:</span><span class="sxs-lookup"><span data-stu-id="fc05e-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 in C:\MyTestEmptyField2-c.Dat -f C:\MyTestDefaultCol2-f-c.Fmt -k -T  
  
```  
  
#### <a name="using-bulk-insert-and-keeping-null-values"></a><span data-ttu-id="fc05e-151">Сохранение значений NULL при работе с инструкцией BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="fc05e-151">Using BULK INSERT and Keeping Null Values</span></span>  
 <span data-ttu-id="fc05e-152">Следующий пример демонстрирует применение параметра KEEPNULLS в операторе BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="fc05e-152">The following example demonstrates how to use the KEEPNULLS option in a BULK INSERT statement.</span></span> <span data-ttu-id="fc05e-153">В средстве выполнения запросов, например в редакторе запросов [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], выполните:</span><span class="sxs-lookup"><span data-stu-id="fc05e-153">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT MyTestDefaultCol2  
   FROM 'C:\MyTestEmptyField2-c.Dat'  
   WITH (  
      DATAFILETYPE = 'char',  
      FIELDTERMINATOR = ',',  
      KEEPNULLS  
   );  
GO  
  
```  
  
## <a name="keeping-default-values-with-insert--select--from-openrowsetbulk"></a><span data-ttu-id="fc05e-154">Хранение значений по умолчанию с помощью инструкции INSERT... SELECT \* FROM OPENROWSET (BULK...)</span><span class="sxs-lookup"><span data-stu-id="fc05e-154">Keeping Default Values with INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
 <span data-ttu-id="fc05e-155">По умолчанию все столбцы, не указанные в операции групповой загрузки, устанавливаются в значение NULL путем вставки... SELECT \* FROM OPENROWSET (BULK...). Однако можно указать, что для пустого поля в файле данных соответствующий столбец таблицы использует значение по умолчанию (если таковое имеется).</span><span class="sxs-lookup"><span data-stu-id="fc05e-155">By default, any columns that are not specified in the bulk-load operation are set to NULL by INSERT ... SELECT \* FROM OPENROWSET(BULK...). However, you can specify that for an empty field in the data file, the corresponding table column uses its default value (if any).</span></span> <span data-ttu-id="fc05e-156">Чтобы вставить значения по умолчанию, укажите следующее табличное указание.</span><span class="sxs-lookup"><span data-stu-id="fc05e-156">To use default values, specify the following table hint:</span></span>  
  
|<span data-ttu-id="fc05e-157">Get-Help</span><span class="sxs-lookup"><span data-stu-id="fc05e-157">Command</span></span>|<span data-ttu-id="fc05e-158">Квалификатор</span><span class="sxs-lookup"><span data-stu-id="fc05e-158">Qualifier</span></span>|<span data-ttu-id="fc05e-159">Тип квалификатора</span><span class="sxs-lookup"><span data-stu-id="fc05e-159">Qualifier Type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="fc05e-160">Инструкции INSERT ... SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="fc05e-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="fc05e-161">WITH(KEEPDEFAULTS)</span><span class="sxs-lookup"><span data-stu-id="fc05e-161">WITH(KEEPDEFAULTS)</span></span>|<span data-ttu-id="fc05e-162">Табличное указание</span><span class="sxs-lookup"><span data-stu-id="fc05e-162">Table hint</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="fc05e-163">Дополнительные сведения см. в статьях [вставка &#40;Transact-sql&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)и [табличные указания &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span><span class="sxs-lookup"><span data-stu-id="fc05e-163">for more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span></span>  
  
### <a name="examples"></a><span data-ttu-id="fc05e-164">Примеры</span><span class="sxs-lookup"><span data-stu-id="fc05e-164">Examples</span></span>  
 <span data-ttu-id="fc05e-165">Следующая инструкция INSERT... SELECT \* FROM OPENROWSET (BULK...) пример выполняет операции по импорту данных и сохраняет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc05e-165">The following INSERT ... SELECT \* FROM OPENROWSET(BULK...) example bulk imports data and keeps the default values.</span></span>  
  
 <span data-ttu-id="fc05e-166">Чтобы выполнить эти примеры, необходимо создать образец таблицы **MyTestDefaultCol2**, файл данных `MyTestEmptyField2-c.Dat` и использовать файл форматирования `MyTestDefaultCol2-f-c.Fmt`.</span><span class="sxs-lookup"><span data-stu-id="fc05e-166">To run the examples, you need to create the **MyTestDefaultCol2** sample table, the `MyTestEmptyField2-c.Dat` data file, and use a format file, `MyTestDefaultCol2-f-c.Fmt`.</span></span> <span data-ttu-id="fc05e-167">Дополнительные сведения о создании этих образцов см. в подразделе «Образец таблицы и файла данных» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="fc05e-167">For information on creating these samples, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="fc05e-168">Для второго столбца таблицы (**Col2**) задано значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc05e-168">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="fc05e-169">Соответствующее поле файла данных содержит пустые строки.</span><span class="sxs-lookup"><span data-stu-id="fc05e-169">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="fc05e-170">При ВСТАВКе... Выбор \* из OPENROWSET (BULK...). Импорт полей этого файла данных в таблицу **MyTestDefaultCol2** по умолчанию значение NULL вставляется в **Col2** вместо значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fc05e-170">When INSERT ... SELECT \* FROM OPENROWSET(BULK...) import the fields of this data file into the **MyTestDefaultCol2** table, by default, NULL is inserted into **Col2** instead of the default value.</span></span> <span data-ttu-id="fc05e-171">В этом случае результат будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fc05e-171">This default behavior produces the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`NULL`|`DataField3`|  
|`2`|`NULL`|`DataField3`|  
  
 <span data-ttu-id="fc05e-172">Чтобы вставить значение по умолчанию `Default value of Col2` вместо значения `NULL`, необходимо использовать табличное указание KEEPDEFAULTS (см. следующий пример).</span><span class="sxs-lookup"><span data-stu-id="fc05e-172">To insert the default value, "`Default value of Col2`", instead of "`NULL`", you need to use KEEPDEFAULTS table hint, as demonstrated in the following example.</span></span> <span data-ttu-id="fc05e-173">В средстве выполнения запросов, например в редакторе запросов [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], выполните:</span><span class="sxs-lookup"><span data-stu-id="fc05e-173">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
INSERT INTO MyTestDefaultCol2  
    WITH (KEEPDEFAULTS)  
    SELECT *  
      FROM OPENROWSET(BULK  'C:\MyTestEmptyField2-c.Dat',  
      FORMATFILE='C:\MyTestDefaultCol2-f-c.Fmt'       
      ) as t1 ;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fc05e-174">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="fc05e-174">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fc05e-175">Сохранение значений идентификаторов при массовом импорте данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-175">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-176">Подготовка данных к массовому экспорту или импорту (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-176">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="fc05e-177">**Использование файла форматирования**</span><span class="sxs-lookup"><span data-stu-id="fc05e-177">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="fc05e-178">Создание файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-178">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-179">Использование файла форматирования для массового импорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-179">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-180">Использование файла форматирования для сопоставления столбцов таблицы с полями файла данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-180">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-181">Использование файла форматирования для пропуска поля данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-181">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-182">Пропуск столбца таблицы с помощью файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-182">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="fc05e-183">**Использование форматов данных для массового импорта или экспорта**</span><span class="sxs-lookup"><span data-stu-id="fc05e-183">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="fc05e-184">Импорт данных в собственном и символьном формате из предыдущих версий SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc05e-184">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-185">Использование символьного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-185">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-186">Использование собственного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-186">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-187">Использование символьного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-188">Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="fc05e-189">**Задание форматов данных для совместимости с помощью программы bcp**</span><span class="sxs-lookup"><span data-stu-id="fc05e-189">**To specify data formats for compatibility when using bcp**</span></span>  
  
-   [<span data-ttu-id="fc05e-190">Определение признаков конца поля и строки (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-190">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-191">Определение длины префикса в файлах данных с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-191">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="fc05e-192">Указание типа файлового хранилища с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc05e-192">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc05e-193">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc05e-193">See Also</span></span>  
 <span data-ttu-id="fc05e-194">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fc05e-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="fc05e-195">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fc05e-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="fc05e-196">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="fc05e-196">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="fc05e-197">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fc05e-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="fc05e-198">Табличные указания (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fc05e-198">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
