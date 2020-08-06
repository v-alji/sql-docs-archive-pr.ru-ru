---
title: Указание форматов данных для совместимости с помощью программы bcp (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], compatibility
- bulk importing [SQL Server], compatibility
- compatibility [SQL Server], data formats
- data formats [SQL Server], compatibility
- bcp utility [SQL Server], compatibility
ms.assetid: cd5fc8c8-eab1-4165-9468-384f31e53f0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d12456760f32ddbd8cc434d474aebb0e0ecf141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738423"
---
# <a name="specify-data-formats-for-compatibility-when-using-bcp-sql-server"></a><span data-ttu-id="611ab-102">Указание форматов данных для совместимости с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="611ab-102">Specify Data Formats for Compatibility when Using bcp (SQL Server)</span></span>
  <span data-ttu-id="611ab-103">В этом разделе описываются атрибуты формата данных, запросы к конкретным полям и хранение данных по полям в файле форматирования, отличном от XML, в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `bcp` команде.</span><span class="sxs-lookup"><span data-stu-id="611ab-103">This topic describes the data-format attributes, field-specific prompts, and storing field-by-field data in a non-xml format file of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`bcp` command.</span></span> <span data-ttu-id="611ab-104">Понимать эти возможности может быть полезно, если производится массовый экспорт данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для массового импорта например, в другую программу базы данных.</span><span class="sxs-lookup"><span data-stu-id="611ab-104">Understanding these can be helpful when you bulk export [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data for bulk import into another program, such as another database program.</span></span> <span data-ttu-id="611ab-105">Стандартные форматы данных в исходной таблице (native, character или Unicode) могут быть несовместимы с форматом данных, ожидаемым другой программой. Если несовместимость существует, когда вы экспортируете данные, необходимо описать формат данных.</span><span class="sxs-lookup"><span data-stu-id="611ab-105">The default data formats (native, character, or Unicode) in the source table might be incompatible with the data layout expected by the other program If an incompatibility exists, when you export the data, you must describe the data layout.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="611ab-106">Описание форматов данных для импорта или экспорта см. в разделе [Форматы данных для массового экспорта или импорта (SQL Server)](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="611ab-106">If you are unfamiliar with data formats for importing or exporting data, see [Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span></span>  
  
 <span data-ttu-id="611ab-107">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="611ab-107">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="611ab-108">Атрибуты формата данных bcp</span><span class="sxs-lookup"><span data-stu-id="611ab-108">bcp Data-Format Attributes</span></span>](#bcpDataFormatAttr)  
  
-   [<span data-ttu-id="611ab-109">Общие сведения о запросах, относящихся к полям</span><span class="sxs-lookup"><span data-stu-id="611ab-109">Overview of the Field-Specific Prompts</span></span>](#FieldSpecificPrompts)  
  
-   [<span data-ttu-id="611ab-110">Хранение данных по полям в файле форматирования в формате, отличном от XML</span><span class="sxs-lookup"><span data-stu-id="611ab-110">Storing Field-by-Field Data in a Non-XML Format File</span></span>](#FieldByFieldNonXmlFF)  
  
-   [<span data-ttu-id="611ab-111">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="611ab-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="bcp-data-format-attributes"></a><a name="bcpDataFormatAttr"></a> <span data-ttu-id="611ab-112">Атрибуты формата данных в инструкции bcp</span><span class="sxs-lookup"><span data-stu-id="611ab-112">bcp Data-Format Attributes</span></span>  
 <span data-ttu-id="611ab-113">Команда `bcp` позволяет указывать структуру каждого поля в файле данных в виде следующих атрибутов формата данных:</span><span class="sxs-lookup"><span data-stu-id="611ab-113">The `bcp` command allows you to specify the structure of each field in a data file in terms of the following data-format attributes:</span></span>  
  
-   <span data-ttu-id="611ab-114">Тип файла хранилища</span><span class="sxs-lookup"><span data-stu-id="611ab-114">File storage type</span></span>  
  
     <span data-ttu-id="611ab-115">*Тип файла хранилища* описывает, каким образом данные хранятся в файле данных.</span><span class="sxs-lookup"><span data-stu-id="611ab-115">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="611ab-116">Экспорт данных может быть выполнен в файл данных в формате таблиц баз данных (собственный формат), в символьном представлении (символьный формат) или в любом формате данных, поддерживающем неявное преобразование, например копирование данных типа `smallint` как `int`.</span><span class="sxs-lookup"><span data-stu-id="611ab-116">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="611ab-117">Пользовательские типы данных экспортируются так же, как их базовые типы.</span><span class="sxs-lookup"><span data-stu-id="611ab-117">User-defined data types are exported as their base types.</span></span> <span data-ttu-id="611ab-118">Дополнительные сведения см. в разделе [Указание типа файлового хранилища с помощью программы bcp (SQL Server)](specify-file-storage-type-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="611ab-118">For more information, see [Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="611ab-119">Длина префикса</span><span class="sxs-lookup"><span data-stu-id="611ab-119">Prefix length</span></span>  
  
     <span data-ttu-id="611ab-120">Для наиболее компактного хранения файлов при массовом экспорте данных собственного формата в файл данных команда `bcp` ставит перед каждым полем один или несколько символов, которые указывают длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="611ab-120">To provide the most compact file storage for the bulk export of data in native format to a data file, the `bcp` command precedes each field with one or more characters that indicates the length of the field.</span></span> <span data-ttu-id="611ab-121">Эти символы называются *символами префикса длины*.</span><span class="sxs-lookup"><span data-stu-id="611ab-121">These characters are called *length prefix characters*.</span></span> <span data-ttu-id="611ab-122">Дополнительные сведения см. в разделе [Определение длины префикса в файлах данных с помощью программы bcp (SQL Server)](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="611ab-122">For more information, see [Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="611ab-123">Длина поля</span><span class="sxs-lookup"><span data-stu-id="611ab-123">Field length</span></span>  
  
     <span data-ttu-id="611ab-124">Длина поля указывает максимальное количество символов, необходимых для представления данных в символьном формате.</span><span class="sxs-lookup"><span data-stu-id="611ab-124">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="611ab-125">Если данные хранятся в собственном формате, то длина поля уже известна.</span><span class="sxs-lookup"><span data-stu-id="611ab-125">The field length is already known if the data is stored in the native format.</span></span> <span data-ttu-id="611ab-126">Дополнительные сведения см. в разделе [Указание длины поля с помощью программы bcp (SQL Server)](specify-field-length-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="611ab-126">For more information, see [Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="611ab-127">Признак конца поля</span><span class="sxs-lookup"><span data-stu-id="611ab-127">Field terminator</span></span>  
  
     <span data-ttu-id="611ab-128">Для символьных полей данных можно определить символы, которые являются разделителями полей и строк в файле данных, указав *признак конца поля*и *признак конца строки*.</span><span class="sxs-lookup"><span data-stu-id="611ab-128">For character data fields, optional terminating characters allow you to mark the end of each field in a data file (using a *field terminator*) and the end of each row (using a *row terminator*).</span></span> <span data-ttu-id="611ab-129">Символы признака конца представляют собой один из способов сообщения программе, считывающей файл данных, где заканчивается одно поле или строка и начинается другое.</span><span class="sxs-lookup"><span data-stu-id="611ab-129">Terminating characters are one way to indicate to programs reading the data file where one field or row ends and another begins.</span></span> <span data-ttu-id="611ab-130">Дополнительные сведения см. в разделе [Определение признаков конца поля и строки (SQL Server)](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="611ab-130">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
##  <a name="overview-of-the-field-specific-prompts"></a><a name="FieldSpecificPrompts"></a> <span data-ttu-id="611ab-131">Обзор приглашений, относящихся к полям</span><span class="sxs-lookup"><span data-stu-id="611ab-131">Overview of the Field-Specific Prompts</span></span>  
 <span data-ttu-id="611ab-132">Если интерактивная `bcp` команда содержит параметр **in** или **out** , но не содержит ни параметр файла форматирования (**-f**), ни параметр формата данных (**-n**, **-c**, **-w**или **-n**), каждый столбец в исходной или целевой таблице, в свою очередь, команда запрашивает каждый из описанных выше атрибутов.</span><span class="sxs-lookup"><span data-stu-id="611ab-132">If an interactive `bcp` command contains the **in** or **out** option but does not also contain either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**),  each column in the source or target table, the command prompts for each of the preceding attributes, in turn.</span></span> <span data-ttu-id="611ab-133">В каждом приглашении команда `bcp` предлагает значение по умолчанию, основанное на типе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="611ab-133">In each prompt, the `bcp` command provides a default value based on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the table column.</span></span> <span data-ttu-id="611ab-134">Принятие значений по умолчанию для всех приглашений эквивалентно указанию собственного формата ( **-n**) в командной строке.</span><span class="sxs-lookup"><span data-stu-id="611ab-134">Accepting the default value for all of the prompts produces the same result as specifying native format (**-n**) on the command line.</span></span> <span data-ttu-id="611ab-135">В каждом приглашении значение по умолчанию выводится в квадратных скобках: [*значение по умолчанию*].</span><span class="sxs-lookup"><span data-stu-id="611ab-135">Each prompt displays a default value in brackets: [*default*].</span></span> <span data-ttu-id="611ab-136">Чтобы согласиться с указанным значением по умолчанию, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="611ab-136">Pressing ENTER accepts the displayed default.</span></span> <span data-ttu-id="611ab-137">Чтобы указать другое значение, введите его в приглашении.</span><span class="sxs-lookup"><span data-stu-id="611ab-137">To specify a value other than the default, enter the new value at the prompt.</span></span>  
  
### <a name="example"></a><span data-ttu-id="611ab-138">Пример</span><span class="sxs-lookup"><span data-stu-id="611ab-138">Example</span></span>  
 <span data-ttu-id="611ab-139">В следующем примере команда `bcp` используется для массового интерактивного экспорта данных из таблицы `HumanResources.myTeam` в файл `myTeam.txt`.</span><span class="sxs-lookup"><span data-stu-id="611ab-139">The following example uses the `bcp` command to bulk export data from the `HumanResources.myTeam` table interactively to the `myTeam.txt` file.</span></span> <span data-ttu-id="611ab-140">Перед выполнением примера следует создать эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="611ab-140">Before you can run the example, you must create this table.</span></span> <span data-ttu-id="611ab-141">Дополнительные сведения о таблице и способе ее создания см. в разделе [Образец таблицы HumanResources.myTeam (SQL Server)](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="611ab-141">For information about the table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
 <span data-ttu-id="611ab-142">Команда не указывает ни файл форматирования, ни тип данных, поэтому программа `bcp` запрашивает сведения о формате данных.</span><span class="sxs-lookup"><span data-stu-id="611ab-142">The command specifies neither a format file nor a data type, causing `bcp` to prompt for data-format information.</span></span> <span data-ttu-id="611ab-143">В командной строке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows введите:</span><span class="sxs-lookup"><span data-stu-id="611ab-143">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam out myTeam.txt -T  
```  
  
 <span data-ttu-id="611ab-144">Для каждого столбца программа bcp запрашивает значения, относящиеся к полю.</span><span class="sxs-lookup"><span data-stu-id="611ab-144">For each column, bcp prompts for field-specific values.</span></span> <span data-ttu-id="611ab-145">В следующем примере показаны относящиеся к полям приглашения для столбцов таблицы `EmployeeID` и `Name` , и для каждого столбца предлагается тип хранения файла по умолчанию (собственный формат).</span><span class="sxs-lookup"><span data-stu-id="611ab-145">The following example shows the field-specific prompts for the `EmployeeID` and `Name` columns of the table, and suggests the default file storage type (the native format) for each column.</span></span> <span data-ttu-id="611ab-146">Длины префиксов столбцов `EmployeeID` и `Name` равны 0 и 2 соответственно.</span><span class="sxs-lookup"><span data-stu-id="611ab-146">The prefix lengths of the `EmployeeID` and `Name` column are 0 and 2, respectively.</span></span> <span data-ttu-id="611ab-147">Пользователь указывает запятую (`,`) в качестве признака конца поля.</span><span class="sxs-lookup"><span data-stu-id="611ab-147">The user specifies a comma (`,`) as the terminator of each field.</span></span>  
  
 `Enter the file storage type of field EmployeeID [smallint]:`  
  
 `Enter prefix-length of field EmployeeID [0]:`  
  
 `Enter field terminator [none]:,`  
  
 `Enter the file storage type of field Name [nvarchar]:`  
  
 `Enter prefix length of field Name [2]:`  
  
 `Enter field terminator [none]:,`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 <span data-ttu-id="611ab-148">Аналогичные приглашения (при необходимости) последовательно выводятся для каждого столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="611ab-148">Equivalent prompts (as needed) are displayed for each of the table columns in order.</span></span>  
  
##  <a name="storing-field-by-field-data-in-a-non-xml-format-file"></a><a name="FieldByFieldNonXmlFF"></a> <span data-ttu-id="611ab-149">Хранение данных полей в файле форматирования в формате, отличном от XML</span><span class="sxs-lookup"><span data-stu-id="611ab-149">Storing Field-by-Field Data in a Non-XML Format File</span></span>  
 <span data-ttu-id="611ab-150">После указания всех столбцов таблицы команда `bcp` предлагает сформировать файл форматирования в формате, отличном от XML, в который будут записаны предоставленные сведения о полях данных (см. предыдущий пример).</span><span class="sxs-lookup"><span data-stu-id="611ab-150">After all of the table columns are specified, the `bcp` command prompts you to optionally generate a non-XML format file that stores the field-by-field information just supplied (see the preceding example).</span></span> <span data-ttu-id="611ab-151">Создать файл форматирования можно как при экспорте данных из этой таблицы, так и при импорте данных схожей структуры в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="611ab-151">If you choose to generate a format file, you can whenever you export data out of that table or import like-structured data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="611ab-152">Файл форматирования можно использовать для массового импорта данных из файла данных в экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или для массового экспорта данных из таблицы, чтобы не указывать формат повторно.</span><span class="sxs-lookup"><span data-stu-id="611ab-152">You can use the format file to bulk import data from the data file into an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to bulk export data from the table, without needing to respecify the format.</span></span> <span data-ttu-id="611ab-153">Дополнительные сведения см в разделе [Файлы форматирования для импорта или экспорта данных (SQL Server)](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="611ab-153">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="611ab-154">В следующем примере создается файл форматирования в формате, `myFormatFile.fmt`отличном от XML:</span><span class="sxs-lookup"><span data-stu-id="611ab-154">The following example creates a non-XML format file named `myFormatFile.fmt`:</span></span>  
  
 `Do you want to save this format information in a file? [Y/n] y`  
  
 `Host filename: [bcp.fmt]myFormatFile.fmt`  
  
 <span data-ttu-id="611ab-155">Имя по умолчанию для файла форматирования — bcp.fmt, но можно указать и другое имя файла.</span><span class="sxs-lookup"><span data-stu-id="611ab-155">The default name for the format file is bcp.fmt, but you can specify a different file name if you choose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="611ab-156">Для файла данных, использующего только один формат данных для типа файлового хранилища, например символьный или собственный, можно быстро создать файл форматирования без экспорта и импорта данных, воспользовавшись параметром **format** .</span><span class="sxs-lookup"><span data-stu-id="611ab-156">For a data file that uses a single data format for its file-storage type, such as character or native format, you can quickly create a format file without exporting or importing data by using the **format** option.</span></span> <span data-ttu-id="611ab-157">Этот подход гораздо проще и позволяет создавать как XML-файлы форматирования, так и файлы форматирования в формате, отличном от XML.</span><span class="sxs-lookup"><span data-stu-id="611ab-157">This approach has the advantages of being easy and of allowing you to create either an XML format file or a non-XML format file.</span></span> <span data-ttu-id="611ab-158">Дополнительные сведения см. в разделе [Создание файла форматирования (SQL Server)](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="611ab-158">For more information, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="611ab-159">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="611ab-159">Related Tasks</span></span>  
  
-   [<span data-ttu-id="611ab-160">Указание типа файлового хранилища с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="611ab-160">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="611ab-161">Определение длины префикса в файлах данных с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="611ab-161">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="611ab-162">Указание длины поля с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="611ab-162">Specify Field Length by Using bcp &#40;SQL Server&#41;</span></span>](specify-field-length-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="611ab-163">Определение признаков конца поля и строки (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="611ab-163">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="611ab-164">См. также</span><span class="sxs-lookup"><span data-stu-id="611ab-164">Related Content</span></span>  
 <span data-ttu-id="611ab-165">Нет.</span><span class="sxs-lookup"><span data-stu-id="611ab-165">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="611ab-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="611ab-166">See Also</span></span>  
 <span data-ttu-id="611ab-167">[Массовый импорт и экспорт данных (SQL Server)](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="611ab-167">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="611ab-168">[Форматы данных для массового экспорта или импорта (SQL Server)](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="611ab-168">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 <span data-ttu-id="611ab-169">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="611ab-169">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="611ab-170">Типы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="611ab-170">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
