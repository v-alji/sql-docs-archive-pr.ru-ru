---
title: Указание типа хранилища файлов с помощью программы bcp (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], file storage types
- importing data, file storage types
- native data format [SQL Server]
- file storage types [SQL Server]
- data formats [SQL Server], file storage types
ms.assetid: 85e12df8-1be7-4bdc-aea9-05aade085c06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1f3ad2a94ffe3e0f1db19a8e66f85497e7143dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655725"
---
# <a name="specify-file-storage-type-by-using-bcp-sql-server"></a><span data-ttu-id="7101b-102">Указание типа файлового хранилища с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7101b-102">Specify File Storage Type by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="7101b-103">*Тип файла хранилища* описывает, каким образом данные хранятся в файле данных.</span><span class="sxs-lookup"><span data-stu-id="7101b-103">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="7101b-104">Экспорт данных может быть выполнен в файл данных в формате таблиц баз данных (собственный формат), в символьном представлении (символьный формат) или в любом формате данных, поддерживающем неявное преобразование, например копирование данных типа `smallint` как `int`.</span><span class="sxs-lookup"><span data-stu-id="7101b-104">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="7101b-105">Пользовательские типы данных экспортируются так же, как их базовые типы.</span><span class="sxs-lookup"><span data-stu-id="7101b-105">User-defined data types are exported as their base types.</span></span>  
  
## <a name="the-bcp-prompt-for-file-storage-type"></a><span data-ttu-id="7101b-106">Приглашение bcp указать тип файлового хранилища</span><span class="sxs-lookup"><span data-stu-id="7101b-106">The bcp Prompt for File Storage Type</span></span>  
 <span data-ttu-id="7101b-107">Если интерактивная команда **bcp** содержит параметр **in** или **out** без параметра файла форматирования ( **-f**) или параметра формата данных ( **-n**, **-c**, **-w**или **-N**), команда запрашивает тип файлового хранилища для каждого поля данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7101b-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the file storage type of each data field, as follows:</span></span>  
  
 `Enter the file storage type of field <field_name> [<default>]:`  
  
 <span data-ttu-id="7101b-108">Ответ на такое приглашение зависит от выполняемой задачи.</span><span class="sxs-lookup"><span data-stu-id="7101b-108">Your response to this prompt depends on the task you perform, as follows:</span></span>  
  
-   <span data-ttu-id="7101b-109">Для массового экспорта данных из экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в файл данных в наиболее компактном хранилище (собственный формат данных) примите типы файловых хранилищ по умолчанию, которые предлагает программа **bcp**.</span><span class="sxs-lookup"><span data-stu-id="7101b-109">To bulk export data from an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in the most compact storage possible (native data format), accept the default file storage types that are provided by **bcp**.</span></span> <span data-ttu-id="7101b-110">Список собственных типов файловых хранилищ см. в разделе «Собственные типы файловых хранилищ» далее в этом подразделе.</span><span class="sxs-lookup"><span data-stu-id="7101b-110">For a list of the native file storage types, see "Native File Storage Types," later in this topic.</span></span>  
  
-   <span data-ttu-id="7101b-111">Для массового экспорта данных из экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в файл данных в символьном формате укажите в качестве типа файлового хранилища `char` для всех столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="7101b-111">To bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in character format, specify `char` as the file storage type for all columns in the table.</span></span>  
  
-   <span data-ttu-id="7101b-112">Для массового импорта данных в экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из файла данных, укажите тип файлового хранилища `char` для типов, для которых данные хранятся в символьном формате, а для данных, хранящихся в формате собственного типа данных, укажите один из типов файлового хранилища.</span><span class="sxs-lookup"><span data-stu-id="7101b-112">To bulk import data to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file, specify the file storage type as `char` for types stored in character format and, for data stored in native data type format, specify one of the file storage types, as appropriate:</span></span>  
  
    |<span data-ttu-id="7101b-113">Тип файла хранилища</span><span class="sxs-lookup"><span data-stu-id="7101b-113">File storage type</span></span>|<span data-ttu-id="7101b-114">Введите в командной строке</span><span class="sxs-lookup"><span data-stu-id="7101b-114">Enter at command prompt</span></span>|  
    |-----------------------|-----------------------------|  
    |<span data-ttu-id="7101b-115">`char` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7101b-115">`char` <sup>1</sup></span></span>|<span data-ttu-id="7101b-116">`c`[`har`]</span><span class="sxs-lookup"><span data-stu-id="7101b-116">`c`[`har`]</span></span>|  
    |`varchar`|`c[har]`|  
    |`nchar`|`w`|  
    |`nvarchar`|`w`|  
    |<span data-ttu-id="7101b-117">`text` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7101b-117">`text` <sup>2</sup></span></span>|<span data-ttu-id="7101b-118">`T`[`ext`]</span><span class="sxs-lookup"><span data-stu-id="7101b-118">`T`[`ext`]</span></span>|  
    |`ntext2`|`W`|  
    |`binary`|`x`|  
    |`varbinary`|`x`|  
    |<span data-ttu-id="7101b-119">`image` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7101b-119">`image` <sup>2</sup></span></span>|<span data-ttu-id="7101b-120">`I`[`mage`]</span><span class="sxs-lookup"><span data-stu-id="7101b-120">`I`[`mage`]</span></span>|  
    |`datetime`|<span data-ttu-id="7101b-121">**d[ate]**</span><span class="sxs-lookup"><span data-stu-id="7101b-121">**d[ate]**</span></span>|  
    |`smalldatetime`|`D`|  
    |`time`|`te`|  
    |`date`|`de`|  
    |`datetime2`|`d2`|  
    |`datetimeoffset`|`do`|  
    |`decimal`|`n`|  
    |`numeric`|`n`|  
    |`float`|<span data-ttu-id="7101b-122">**f[loat]**</span><span class="sxs-lookup"><span data-stu-id="7101b-122">**f[loat]**</span></span>|  
    |`real`|`r`|  
    |`Int`|<span data-ttu-id="7101b-123">**i[nt]**</span><span class="sxs-lookup"><span data-stu-id="7101b-123">**i[nt]**</span></span>|  
    |`bigint`|`B[igint]`|  
    |`smallint`|<span data-ttu-id="7101b-124">**s[mallint]**</span><span class="sxs-lookup"><span data-stu-id="7101b-124">**s[mallint]**</span></span>|  
    |`tinyint`|<span data-ttu-id="7101b-125">**t[inyint]**</span><span class="sxs-lookup"><span data-stu-id="7101b-125">**t[inyint]**</span></span>|  
    |`money`|<span data-ttu-id="7101b-126">**m[oney]**</span><span class="sxs-lookup"><span data-stu-id="7101b-126">**m[oney]**</span></span>|  
    |`smallmoney`|`M`|  
    |`bit`|`b[it]`|  
    |`uniqueidentifier`|`u`|  
    |`sql_variant`|`V[ariant]`|  
    |`timestamp`|`x`|  
    |<span data-ttu-id="7101b-127">`UDT` (пользовательский тип данных)</span><span class="sxs-lookup"><span data-stu-id="7101b-127">`UDT` (a user-defined data type)</span></span>|`U`|  
    |`XML`|`X`|  
  
     <span data-ttu-id="7101b-128"><sup>1</sup> взаимодействие длины поля, длины префикса и признаков конца определяет объем дискового пространства, выделенного в файле данных для несимвольных данных, экспортируемых в качестве `char` типа хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="7101b-128"><sup>1</sup> The interaction of field length, prefix length, and terminators determines the amount of storage space that is allocated in a data file for noncharacter data that is exported as the `char` file storage type.</span></span>  
  
     <span data-ttu-id="7101b-129"><sup>2</sup> `ntext` `text` типы данных, и `image` будут удалены в следующей версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7101b-129"><sup>2</sup> The `ntext`, `text`, and `image` data types will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7101b-130">Следует избегать использования этих типов данных при новой разработке и запланировать изменение приложений, использующих их в настоящий момент.</span><span class="sxs-lookup"><span data-stu-id="7101b-130">In new development work, avoid using these data types, and plan to modify applications that currently use them.</span></span> <span data-ttu-id="7101b-131">Используйте вместо них типы данных `nvarchar(max)`, `varchar(max)` и `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="7101b-131">Use `nvarchar(max)`, `varchar(max)`, and `varbinary(max)` instead.</span></span>  
  
## <a name="native-file-storage-types"></a><span data-ttu-id="7101b-132">Собственные типы файловых хранилищ</span><span class="sxs-lookup"><span data-stu-id="7101b-132">Native File Storage Types</span></span>  
 <span data-ttu-id="7101b-133">Все собственные типы файловых хранилищ записаны в файле форматирования как соответствующие типы данных основных файлов.</span><span class="sxs-lookup"><span data-stu-id="7101b-133">Each native file storage type is recorded in the format file as a corresponding host file data type.</span></span>  
  
|<span data-ttu-id="7101b-134">Тип файла хранилища</span><span class="sxs-lookup"><span data-stu-id="7101b-134">File storage type</span></span>|<span data-ttu-id="7101b-135">Тип данных файла</span><span class="sxs-lookup"><span data-stu-id="7101b-135">Host file data type</span></span>|  
|-----------------------|-------------------------|  
|<span data-ttu-id="7101b-136">`char` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7101b-136">`char` <sup>1</sup></span></span>|<span data-ttu-id="7101b-137">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="7101b-137">SQLCHAR</span></span>|  
|`varchar`|<span data-ttu-id="7101b-138">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="7101b-138">SQLCHAR</span></span>|  
|`nchar`|<span data-ttu-id="7101b-139">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="7101b-139">SQLNCHAR</span></span>|  
|`nvarchar`|<span data-ttu-id="7101b-140">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="7101b-140">SQLNCHAR</span></span>|  
|<span data-ttu-id="7101b-141">`text` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7101b-141">`text` <sup>2</sup></span></span>|<span data-ttu-id="7101b-142">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="7101b-142">SQLCHAR</span></span>|  
|<span data-ttu-id="7101b-143">`ntext` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7101b-143">`ntext` <sup>2</sup></span></span>|<span data-ttu-id="7101b-144">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="7101b-144">SQLNCHAR</span></span>|  
|`binary`|<span data-ttu-id="7101b-145">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="7101b-145">SQLBINARY</span></span>|  
|`varbinary`|<span data-ttu-id="7101b-146">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="7101b-146">SQLBINARY</span></span>|  
|<span data-ttu-id="7101b-147">`image` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7101b-147">`image` <sup>2</sup></span></span>|<span data-ttu-id="7101b-148">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="7101b-148">SQLBINARY</span></span>|  
|`datetime`|<span data-ttu-id="7101b-149">SQLDATETIME</span><span class="sxs-lookup"><span data-stu-id="7101b-149">SQLDATETIME</span></span>|  
|`smalldatetime`|<span data-ttu-id="7101b-150">SQLDATETIM4</span><span class="sxs-lookup"><span data-stu-id="7101b-150">SQLDATETIM4</span></span>|  
|`decimal`|<span data-ttu-id="7101b-151">SQLDECIMAL</span><span class="sxs-lookup"><span data-stu-id="7101b-151">SQLDECIMAL</span></span>|  
|`numeric`|<span data-ttu-id="7101b-152">SQLNUMERIC</span><span class="sxs-lookup"><span data-stu-id="7101b-152">SQLNUMERIC</span></span>|  
|`float`|<span data-ttu-id="7101b-153">SQLFLT8</span><span class="sxs-lookup"><span data-stu-id="7101b-153">SQLFLT8</span></span>|  
|`real`|<span data-ttu-id="7101b-154">SQLFLT4</span><span class="sxs-lookup"><span data-stu-id="7101b-154">SQLFLT4</span></span>|  
|`int`|<span data-ttu-id="7101b-155">SQLINT</span><span class="sxs-lookup"><span data-stu-id="7101b-155">SQLINT</span></span>|  
|`bigint`|<span data-ttu-id="7101b-156">SQLBIGINT</span><span class="sxs-lookup"><span data-stu-id="7101b-156">SQLBIGINT</span></span>|  
|`smallint`|<span data-ttu-id="7101b-157">SQLSMALLINT</span><span class="sxs-lookup"><span data-stu-id="7101b-157">SQLSMALLINT</span></span>|  
|`tinyint`|<span data-ttu-id="7101b-158">SQLTINYINT</span><span class="sxs-lookup"><span data-stu-id="7101b-158">SQLTINYINT</span></span>|  
|`money`|<span data-ttu-id="7101b-159">SQLMONEY</span><span class="sxs-lookup"><span data-stu-id="7101b-159">SQLMONEY</span></span>|  
|`smallmoney`|<span data-ttu-id="7101b-160">SQLMONEY4</span><span class="sxs-lookup"><span data-stu-id="7101b-160">SQLMONEY4</span></span>|  
|`bit`|<span data-ttu-id="7101b-161">SQLBIT</span><span class="sxs-lookup"><span data-stu-id="7101b-161">SQLBIT</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="7101b-162">SQLUNIQUEID</span><span class="sxs-lookup"><span data-stu-id="7101b-162">SQLUNIQUEID</span></span>|  
|`sql_variant`|<span data-ttu-id="7101b-163">SQLVARIANT</span><span class="sxs-lookup"><span data-stu-id="7101b-163">SQLVARIANT</span></span>|  
|`timestamp`|<span data-ttu-id="7101b-164">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="7101b-164">SQLBINARY</span></span>|  
|<span data-ttu-id="7101b-165">UDT (определяемый пользователем тип данных)</span><span class="sxs-lookup"><span data-stu-id="7101b-165">UDT (a user-defined data type)</span></span>|<span data-ttu-id="7101b-166">SQLUDT</span><span class="sxs-lookup"><span data-stu-id="7101b-166">SQLUDT</span></span>|  
  
 <span data-ttu-id="7101b-167"><sup>1</sup> файлы данных, хранящиеся в символьном формате, используют `char` в качестве типа хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="7101b-167"><sup>1</sup> Data files that are stored in character format use `char` as the file storage type.</span></span> <span data-ttu-id="7101b-168">Таким образом, для символьных файлов данных SQLCHAR — это единственный тип данных, допустимый в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="7101b-168">Therefore, for character data files, SQLCHAR is the only data type that appears in a format file.</span></span>  
  
 <span data-ttu-id="7101b-169"><sup>2</sup> вы не можете выполнить операции с массовым импортом данных в `text` `ntext` столбцы, и `image` , имеющие значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7101b-169"><sup>2</sup> You cannot bulk import data into `text`, `ntext`, and `image` columns that have DEFAULT values.</span></span>  
  
## <a name="additional-considerations-for-file-storage-types"></a><span data-ttu-id="7101b-170">Дополнительные замечания относительно типов файловых хранилищ</span><span class="sxs-lookup"><span data-stu-id="7101b-170">Additional Considerations for File Storage Types</span></span>  
 <span data-ttu-id="7101b-171">При массовом экспорте данных из экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в файл данных:</span><span class="sxs-lookup"><span data-stu-id="7101b-171">When you bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file:</span></span>  
  
-   <span data-ttu-id="7101b-172">можно указать в качестве типа файлового хранилища `char`;</span><span class="sxs-lookup"><span data-stu-id="7101b-172">You can always specify `char` as the file storage type.</span></span>  
  
-   <span data-ttu-id="7101b-173">При вводе типа файлового хранилища, представляющего Недопустимое неявное преобразование, программа **bcp** завершается с ошибкой. Например, можно указать `int` для `smallint` данных, если указать `smallint` для `int` данных, результат ошибки переполнения.</span><span class="sxs-lookup"><span data-stu-id="7101b-173">If you enter a file storage type that represents an invalid implicit conversion, **bcp** fails; for example, though you can specify `int` for `smallint` data, if you specify `smallint` for `int` data, overflow errors result.</span></span>  
  
-   <span data-ttu-id="7101b-174">когда несимвольные типы данных, такие как `float`, `money`, `datetime` или `int`, хранятся с использованием соответствующих типов баз данных, то данные записываются в файл данных в собственном формате [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7101b-174">When noncharacter data types such as `float`, `money`, `datetime`, or `int` are stored as their database types, the data is written to the data file in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7101b-175">После интерактивного заполнения всех полей в команде **bcp** появится запрос на сохранение введенных ответов для каждого поля в файле форматирования в формате, отличном от XML.</span><span class="sxs-lookup"><span data-stu-id="7101b-175">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="7101b-176">Дополнительные сведения о файлах форматирования в формате, отличном от XML, см. в разделе [Файлы формата, отличные от XML (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7101b-176">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7101b-177">См. также:</span><span class="sxs-lookup"><span data-stu-id="7101b-177">See Also</span></span>  
 <span data-ttu-id="7101b-178">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="7101b-178">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="7101b-179">[Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7101b-179">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="7101b-180">[Указание длины поля с помощью программы bcp (SQL Server)](specify-field-length-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7101b-180">[Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="7101b-181">[Определение признаков конца поля и строки (SQL Server)](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7101b-181">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 [<span data-ttu-id="7101b-182">Определение длины префикса в файлах данных с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7101b-182">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
  
