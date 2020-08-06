---
title: Использование файла форматирования для пропуска столбца таблицы (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- skipping columns when importing
- format files [SQL Server], skipping columns
ms.assetid: 30e0e7b9-d131-46c7-90a4-6ccf77e3d4f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 153ef21209ff4261020e26aca3bc52d28dc852a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669407"
---
# <a name="use-a-format-file-to-skip-a-table-column-sql-server"></a><span data-ttu-id="eeb2d-102">Пропуск столбца таблицы с помощью файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="eeb2d-102">Use a Format File to Skip a Table Column (SQL Server)</span></span>
  <span data-ttu-id="eeb2d-103">В этом подразделе описываются файлы форматирования.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-103">This topic describes format files.</span></span> <span data-ttu-id="eeb2d-104">Если поле не существует в файле данных, то импорт столбца таблицы можно пропустить с помощью файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-104">You can use a format file to skip importing a table column when the field does not exist in the data file.</span></span> <span data-ttu-id="eeb2d-105">Файл данных может содержать меньше полей, чем таблица столбцов, только если пропущенные столбцы необязательно определяемы и (или) имеют значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-105">A data file can contain fewer fields than the number of columns in the table only if the skipped columns are nullable and/or have default value.</span></span>

## <a name="sample-table-and-data-file"></a><span data-ttu-id="eeb2d-106">Образец таблицы и файла данных</span><span class="sxs-lookup"><span data-stu-id="eeb2d-106">Sample Table and Data File</span></span>
 <span data-ttu-id="eeb2d-107">Для следующих примеров требуется таблица с именем `myTestSkipCol` в образце базы данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] схемы **dbo** .</span><span class="sxs-lookup"><span data-stu-id="eeb2d-107">The following examples require a table named `myTestSkipCol` in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="eeb2d-108">Создайте таблицу следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eeb2d-108">Create this table as follows:</span></span>

```
USE AdventureWorks2012;
GO
CREATE TABLE myTestSkipCol 
   (
   Col1 smallint,
   Col2 nvarchar(50) NULL,
   Col3 nvarchar(50) not NULL
   );
GO
```

 <span data-ttu-id="eeb2d-109">В примерах, приведенных ниже, используется образец файла данных `myTestSkipCol2.dat`, который содержит только два поля, в то время как в соответствующей таблице три столбца:</span><span class="sxs-lookup"><span data-stu-id="eeb2d-109">The following examples use a sample data file, `myTestSkipCol2.dat`, which contains only two fields, although the corresponding table contains three columns:</span></span>

```
1,DataForColumn3
1,DataForColumn3
1,DataForColumn3

```

 <span data-ttu-id="eeb2d-110">Чтобы выполнить массовый импорт данных из таблицы `myTestSkipCol2.dat` в таблицу `myTestSkipCol` , файл форматирования должен сопоставлять первое поле данных с `Col1`, а второе поле данных с `Col3`, пропуская поле `Col2`.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-110">To bulk import data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col1`, the second field to `Col3`, skipping `Col2`.</span></span>

## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="eeb2d-111">Использование файла форматирования в формате, отличном от XML</span><span class="sxs-lookup"><span data-stu-id="eeb2d-111">Using a Non-XML Format File</span></span>
 <span data-ttu-id="eeb2d-112">Чтобы пропустить столбец таблицы, можно изменить файл форматирования в формате, отличном от XML.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-112">You can modify a non-XML format file to skip a table column.</span></span> <span data-ttu-id="eeb2d-113">Обычно при этом используется служебная программа **bcp** (для создания файла форматирования по умолчанию в формате, отличном от XML) и в текстовом редакторе изменяется файл по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-113">Typically, this involves using the **bcp** utility to create a default non-XML format file and the modifying the default file in a text editor.</span></span> <span data-ttu-id="eeb2d-114">Измененный файл форматирования должен сопоставлять все существующие поля соответствующим столбцам таблицы и указывать, какие столбцы или столбец таблицы пропускать.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-114">The modified format file must map each existing fields to its corresponding table column and indicate which table column or columns to skip.</span></span> <span data-ttu-id="eeb2d-115">Есть два варианта изменения файлов форматирования в формате, отличном от XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-115">Two alternatives exist for modifying a default non-XML data file.</span></span> <span data-ttu-id="eeb2d-116">В одном случае поле данных не существует в файле данных, и в соответствующий столбец таблицы не будут записаны никакие данные.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-116">Either alternative indicates that the data field does not exist in the data file and that no data will be inserted into the corresponding table column.</span></span>

### <a name="creating-a-default-non-xml-format-file"></a><span data-ttu-id="eeb2d-117">Создание файла форматирования в формате, отличном от XML, по умолчанию</span><span class="sxs-lookup"><span data-stu-id="eeb2d-117">Creating a Default Non-XML Format File</span></span>
 <span data-ttu-id="eeb2d-118">В этой статье используется файл форматирования по умолчанию в формате, отличном от XML, созданный для образца таблицы `myTestSkipCol` с помощью следующей команды **bcp** :</span><span class="sxs-lookup"><span data-stu-id="eeb2d-118">This topic uses the default non-XML format file that was created for the `myTestSkipCol` sample table by using the following **bcp** command:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.fmt -c -T
```

 <span data-ttu-id="eeb2d-119">Предыдущая команда создает файл форматирования в формате, отличном от XML, `myTestSkipCol_Default.fmt`.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-119">The previous command creates a non-XML format file, `myTestSkipCol_Default.fmt`.</span></span> <span data-ttu-id="eeb2d-120">Этот файл называется *файлом форматирования по умолчанию* , так как представляет собой форму, созданную командой **bcp**.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-120">This format file is called a *default format file* because it is the form generated by **bcp**.</span></span> <span data-ttu-id="eeb2d-121">Обычно файл форматирования по умолчанию описывает сопоставления один к одному между полями файла данных и столбцами таблицы.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-121">Typically, a default format file describes a one-to-one correspondence between data-file fields and table columns.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="eeb2d-122">Необходимо указать имя экземпляра сервера, с которым осуществляется соединение.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-122">You might have to specify the name of the server instance to which you are connecting.</span></span> <span data-ttu-id="eeb2d-123">Возможно также потребуется указать имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-123">Also, you might have to specify the user name and password.</span></span> <span data-ttu-id="eeb2d-124">Дополнительные сведения см. в разделе [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="eeb2d-124">For more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>

 <span data-ttu-id="eeb2d-125">Следующая иллюстрация показывает значения в образцах файлов форматирования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-125">The following illustration shows the values in this sample default format files.</span></span> <span data-ttu-id="eeb2d-126">Иллюстрация также показывает имя каждого поля файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-126">The illustration also shows the name of each format-file field.</span></span>

 <span data-ttu-id="eeb2d-127">![файл форматирования по умолчанию в формате, отличном от XML, для myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "файл форматирования по умолчанию в формате, отличном от XML, для myTestSkipCol")</span><span class="sxs-lookup"><span data-stu-id="eeb2d-127">![default non-XML format file for myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "default non-XML format file for myTestSkipCol")</span></span>

> [!NOTE]
>  <span data-ttu-id="eeb2d-128">Дополнительные сведения о файлах форматирования в формате, отличном от XML, см. в разделе [Файлы формата, отличные от XML (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eeb2d-128">For more information about the format-file fields, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="methods-for-modifying-a-non-xml-format-file"></a><span data-ttu-id="eeb2d-129">Методы изменения файла форматирования в формате, отличном от XML</span><span class="sxs-lookup"><span data-stu-id="eeb2d-129">Methods for Modifying a Non-XML Format File</span></span>
 <span data-ttu-id="eeb2d-130">Чтобы пропустить столбец таблицы, отредактируйте файл форматирования в формате, отличном от XML, и измените файл с помощью одного из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-130">To skip a table column, edit the default non-XML format file and modify the file by using one of the following alternative methods:</span></span>

-   <span data-ttu-id="eeb2d-131">Рекомендуемый метод состоит из трех основных шагов.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-131">The preferred method involves three basic steps.</span></span> <span data-ttu-id="eeb2d-132">Сначала удалите все строки файла форматирования, описывающие пропущенные в файле данных поля.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-132">First, delete any format-file row that describes a field that is missing from the data file.</span></span> <span data-ttu-id="eeb2d-133">Затем уменьшите значение «порядкового номера поля в файле данных» каждой строки файла форматирования, которая следует за удаленной строкой.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-133">Then, reduce the "Host file field order" value of each format-file row that follows a deleted row.</span></span> <span data-ttu-id="eeb2d-134">Целью являются последовательные значения "порядкового номера поля в файле данных", от 1 до *n*, которые отражают действительную позицию каждого поля данных в файле данных.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-134">The goal is sequential "Host file field order" values, 1 through *n*, that reflect the actual position of each data field in the data file.</span></span> <span data-ttu-id="eeb2d-135">Наконец, уменьшите значение в поле «Число столбцов» до действительного числа полей в файле данных.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-135">Finally, reduce the value in the "Number of columns" field to reflect the actual number of fields in the data file.</span></span>

     <span data-ttu-id="eeb2d-136">Следующий пример основан на файле форматирования по умолчанию для таблицы `myTestSkipCol` , создаваемой в подразделе «Создание файла форматирования в формате, отличном от XML» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-136">The following example is based on the default format file for the `myTestSkipCol` table, which is created in "Creating a Default Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="eeb2d-137">Этот измененный файл форматирования сопоставляет первое поле данных полю `Col1`, пропускает поле `Col2`и сопоставляет второе поле данных `Col3`.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-137">This modified format file maps the first data field to `Col1`, skips `Col2`, and maps the second data field to `Col3`.</span></span> <span data-ttu-id="eeb2d-138">Строка для поля `Col2` была удалена.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-138">The row for `Col2` has been deleted.</span></span> <span data-ttu-id="eeb2d-139">Другие изменения выделены полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-139">Other modifications are indicated in bold:</span></span>

    ```
    9.0
    2
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

-   <span data-ttu-id="eeb2d-140">В качестве альтернативы, чтобы пропустить столбец таблицы, можно изменить определение строки файла форматирования, которая соответствует этому столбцу таблицы.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-140">Alternatively, to skip a table column, you can modify the definition of the format-file row that corresponds to the table column.</span></span> <span data-ttu-id="eeb2d-141">В этой строке файла форматирования значения «длина префикса», «длина данных файла узла» и «порядковый номер столбца на сервере» должны быть равны 0.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-141">In this format-file row, the "prefix length," "host file data length," and "server column order" values must be set to 0.</span></span> <span data-ttu-id="eeb2d-142">Также должны быть установлены в значение « » (NULL) поля «признак конца» и «параметры сортировки столбца».</span><span class="sxs-lookup"><span data-stu-id="eeb2d-142">Also, the "terminator" and "column collation" fields must be set to "" (NULL).</span></span>

     <span data-ttu-id="eeb2d-143">Для значения поля «порядковый номер столбца на сервере» необходима непустая строка, хотя действительное имя столбца не требуется.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-143">The "server column name" value requires a nonblank string, though the actual column name is not necessary.</span></span> <span data-ttu-id="eeb2d-144">Для оставшихся полей форматирования требуются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-144">The remaining format fields require their default values.</span></span>

     <span data-ttu-id="eeb2d-145">Следующий пример основан на файле форматирования по умолчанию для таблицы `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="eeb2d-145">The following example is also derived from the default format file for the `myTestSkipCol` table.</span></span> <span data-ttu-id="eeb2d-146">Значения, которые должны быть равны 0 или NULL, выделены полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-146">Values that must be 0 or NULL are indicated in bold.</span></span>

    ```
    9.0
    3
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       00""0     Col2         ""
    3       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

### <a name="examples"></a><span data-ttu-id="eeb2d-147">Примеры</span><span class="sxs-lookup"><span data-stu-id="eeb2d-147">Examples</span></span>
 <span data-ttu-id="eeb2d-148">Следующие примеры также базируются на образце таблицы `myTestSkipCol` и образце файла данных `myTestSkipCol2.dat` , созданных в подразделе «Образец таблицы и файла данных» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-148">The following examples are also based on the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span>

#### <a name="using-bulk-insert"></a><span data-ttu-id="eeb2d-149">Использование предложения BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="eeb2d-149">Using BULK INSERT</span></span>
 <span data-ttu-id="eeb2d-150">Следующий пример работает с использованием любого из файлов форматирования, отличных от XML и создаваемых в подразделе «Методы изменения не XML-файла форматирования» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-150">This example works by using either of the modified non-XML format files created in "Methods for Modifying a Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="eeb2d-151">В этом примере измененный файл форматирования называется `C:\myTestSkipCol2.fmt`.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-151">In this example, the modified format file is named `C:\myTestSkipCol2.fmt`.</span></span> <span data-ttu-id="eeb2d-152">Чтобы использовать `BULK INSERT` для массового импорта файла данных `myTestSkipCol2.dat` , в редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="eeb2d-152">To use `BULK INSERT` to bulk import the `myTestSkipCol2.dat` data file, in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
BULK INSERT myTestSkipCol 
   FROM 'C:\myTestSkipCol2.dat' 
   WITH (FORMATFILE = 'C:\myTestSkipCol2.fmt');
GO
SELECT * FROM myTestSkipCol;
GO
```

## <a name="using-an-xml-format-file"></a><span data-ttu-id="eeb2d-153">Использование XML-файла форматирования</span><span class="sxs-lookup"><span data-stu-id="eeb2d-153">Using an XML Format File</span></span>
 <span data-ttu-id="eeb2d-154">Если для импорта непосредственно в таблицу используется XML-файл форматирования, с помощью команды **bcp** или инструкции BULK INSERT столбец пропустить нельзя.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-154">With an XML format file, you cannot skip a column when you are importing directly into a table by using a **bcp** command or a BULK INSERT statement.</span></span> <span data-ttu-id="eeb2d-155">Однако можно выполнить импорт всех столбцов таблицы, кроме последнего.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-155">However, you can import into all but the last column of a table.</span></span> <span data-ttu-id="eeb2d-156">Если нужно пропустить все столбцы, кроме последнего, необходимо создать представление целевой таблицы, содержащее только столбцы из файла данных.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-156">If you have to skip any but the last column, you must create a view of the target table that contains only the columns contained in the data file.</span></span> <span data-ttu-id="eeb2d-157">После этого можно выполнить массовый импорт данных из этого файла в представление.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-157">Then, you can bulk import data from that file into the view.</span></span>

 <span data-ttu-id="eeb2d-158">Чтобы пропустить столбец таблицы с помощью XML-файла форматирования с помощью инструкции OPENROWSET(BULK...), необходимо следующим образом подставить явный список столбцов в список выбора и в целевую таблицу:</span><span class="sxs-lookup"><span data-stu-id="eeb2d-158">To use an XML format file to skip a table column by using OPENROWSET(BULK...), you have to provide explicit list of columns in the select list and also in the target table, as follows:</span></span>

 <span data-ttu-id="eeb2d-159">INSERT ...<список_столбцов> SELECT <список_столбцов> FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="eeb2d-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span></span>

### <a name="creating-a-default-xml-format-file"></a><span data-ttu-id="eeb2d-160">Создание XML-файла форматирования по умолчанию</span><span class="sxs-lookup"><span data-stu-id="eeb2d-160">Creating a Default XML Format File</span></span>
 <span data-ttu-id="eeb2d-161">Следующие примеры измененных файлов форматирования базируются на образце таблицы `myTestSkipCol` и файла данных, созданных в подразделе «Образец таблицы и файла данных» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-161">The examples of modified format files are based on the `myTestSkipCol` sample table and data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="eeb2d-162">Следующая команда \*\*bcp`myTestSkipCol` создает XML-файл форматирования по умолчанию для таблицы \*\*.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-162">The following **bcp** command creates a default XML format file for the `myTestSkipCol` table:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.xml -c -x -T
```

 <span data-ttu-id="eeb2d-163">Результирующий файл форматирования в формате, отличном от XML, описывает сопоставления один к одному между полями файла данных и столбцами таблицы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eeb2d-163">The resulting default non-XML format file describes a one-to-one correspondence between data-file fields and table columns, as follows:</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

> [!NOTE]
>  <span data-ttu-id="eeb2d-164">Сведения о структуре файлов форматирования XML см. в разделе [Файлы формата XML (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eeb2d-164">For information about the structure of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="examples"></a><span data-ttu-id="eeb2d-165">Примеры</span><span class="sxs-lookup"><span data-stu-id="eeb2d-165">Examples</span></span>
 <span data-ttu-id="eeb2d-166">В примерах этого раздела используется образец таблицы `myTestSkipCol` и образец файла данных `myTestSkipCol2.dat` , создаваемых в подразделе «Образец таблицы и файла данных» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-166">The examples in this section use the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="eeb2d-167">Для импортирования данных из файла `myTestSkipCol2.dat` в таблицу `myTestSkipCol` в примерах используется следующий измененный XML-файл форматирования `myTestSkipCol2-x.xml`.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-167">To import the data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the examples use the following modified XML format file, `myTestSkipCol2-x.xml`.</span></span> <span data-ttu-id="eeb2d-168">Следующий пример основан на файле форматирования, создаваемом в подразделе «Создание не XML-файла форматирования по умолчанию» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-168">This is based on the format file that is created in "Creating a Default XML Format File," earlier in this topic.</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

#### <a name="using-openrowsetbulk"></a><span data-ttu-id="eeb2d-169">Применение инструкции OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="eeb2d-169">Using OPENROWSET(BULK...)</span></span>
 <span data-ttu-id="eeb2d-170">В следующем примере используется поставщик массового набора строк `OPENROWSET` и файл форматирования `myTestSkipCol2.xml` .</span><span class="sxs-lookup"><span data-stu-id="eeb2d-170">The following example uses the `OPENROWSET` bulk rowset provider and the `myTestSkipCol2.xml` format file.</span></span> <span data-ttu-id="eeb2d-171">В примере выполняется массовый импорт файла данных `myTestSkipCol2.dat` в таблицу `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="eeb2d-171">The example bulk imports the `myTestSkipCol2.dat` data file into the `myTestSkipCol` table.</span></span> <span data-ttu-id="eeb2d-172">Инструкция, в соответствии с требованиями, содержит явный список столбцов в списке выбора, а также в целевой таблице.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-172">The statement contains an explicit list of columns in the select list and also in the target table, as required.</span></span>

 <span data-ttu-id="eeb2d-173">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="eeb2d-173">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
INSERT INTO myTestSkipCol
  (Col1,Col3)
    SELECT Col1,Col3
      FROM  OPENROWSET(BULK  'C:\myTestSkipCol2.Dat',
      FORMATFILE='C:\myTestSkipCol2.Xml'  
       ) as t1 ;
GO
```

#### <a name="using-bulk-import-on-a-view"></a><span data-ttu-id="eeb2d-174">Использование инструкции BULK IMPORT на представлениях</span><span class="sxs-lookup"><span data-stu-id="eeb2d-174">Using BULK IMPORT on a View</span></span>
 <span data-ttu-id="eeb2d-175">В следующем примере создается представление `v_myTestSkipCol` для таблицы `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="eeb2d-175">The following example creates the `v_myTestSkipCol` on the `myTestSkipCol` table.</span></span> <span data-ttu-id="eeb2d-176">В этом представлении пропущен второй столбец таблицы `Col2`.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-176">This view skips the second table column, `Col2`.</span></span> <span data-ttu-id="eeb2d-177">Затем применяется инструкция `BULK INSERT` для импорта файла данных `myTestSkipCol2.dat` в это представление.</span><span class="sxs-lookup"><span data-stu-id="eeb2d-177">The example then uses `BULK INSERT` to import the `myTestSkipCol2.dat` data file into this view.</span></span>

 <span data-ttu-id="eeb2d-178">В редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните:</span><span class="sxs-lookup"><span data-stu-id="eeb2d-178">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
CREATE VIEW v_myTestSkipCol AS
    SELECT Col1,Col3
    FROM myTestSkipCol;
GO

USE AdventureWorks2012;
GO
BULK INSERT v_myTestSkipCol
FROM 'C:\myTestSkipCol2.dat'
WITH (FORMATFILE='C:\myTestSkipCol2.xml');
GO
```

## <a name="see-also"></a><span data-ttu-id="eeb2d-179">См. также:</span><span class="sxs-lookup"><span data-stu-id="eeb2d-179">See Also</span></span>
 <span data-ttu-id="eeb2d-180">[программа bcp](../../tools/bcp-utility.md) [BULK INSERT &#40;transact-sql&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [использовать файл форматирования для пропуска поля данных &#40;](use-a-format-file-to-skip-a-data-field-sql-server.md) SQL Server&#41;[использовать файл форматирования для преобразования столбцов таблицы в поля файла данных &#40;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) SQL Server&#41;[использовать файл форматирования для выполнения операций импорта](use-a-format-file-to-bulk-import-data-sql-server.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eeb2d-180">[bcp Utility](../../tools/bcp-utility.md) [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md) [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md)</span></span>


