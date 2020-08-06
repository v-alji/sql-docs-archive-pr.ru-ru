---
title: XML-файлы форматирования (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], XML format files
- bulk importing [SQL Server], format files
- XML format files [SQL Server]
ms.assetid: 69024aad-eeea-4187-8fea-b49bc2359849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cc1e8de30fa582898ef8516b9767dec14c4fa81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667095"
---
# <a name="xml-format-files-sql-server"></a><span data-ttu-id="9103a-102">XML-файлы форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-102">XML Format Files (SQL Server)</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="9103a-103">предоставляет схему XML, которая определяет синтаксис для написания *XML-файлов форматирования* в целях использования при массовом импорте данных в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9103a-103">provides an XML schema that defines syntax for writing *XML format files* to use for bulk importing data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="9103a-104">XML-файлы форматирования должны придерживаться этой схемы, которая определена при помощи языка XML Schema Definition Language (XSDL).</span><span class="sxs-lookup"><span data-stu-id="9103a-104">XML format files must adhere to this schema, which is defined in the XML Schema Definition Language (XSDL).</span></span> <span data-ttu-id="9103a-105">XML-файлы форматирования поддерживаются только при установке средств [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] вместе с собственным клиентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9103a-105">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tools are installed together with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="9103a-106">Можно использовать XML-файл форматирования с командой **bcp**, инструкциями BULK INSERT или INSERT... Инструкция SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="9103a-106">You can use an XML format file with a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="9103a-107">Команда **bcp** позволяет автоматически создать XML-файл форматирования для таблицы. Дополнительные сведения см. в разделе [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="9103a-107">The **bcp** command allows you to automatically generate an XML format file for a table; for more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9103a-108">Для массового экспорта и импорта поддерживаются два типа файлов форматирования: *файлы форматирования, отличные от XML* , и *XML-файлы форматирования*.</span><span class="sxs-lookup"><span data-stu-id="9103a-108">Two types of format files are supported for bulk exporting and importing: *non-XML format files* and *XML format files*.</span></span> <span data-ttu-id="9103a-109">Они более гибкие и мощные по сравнению с файлом форматирования в формате, отличном от XML.</span><span class="sxs-lookup"><span data-stu-id="9103a-109">XML format files provide a flexible and powerful alternative to non-XML format files.</span></span> <span data-ttu-id="9103a-110">Сведения о файлах форматирования в формате, отличном от XML, см. в разделе [Файлы формата, отличные от XML (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9103a-110">For information about non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="benefits-of-xml-format-files"></a><a name="BenefitsOfXmlFFs"></a> <span data-ttu-id="9103a-111">Преимущества использования XML-файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="9103a-111">Benefits of XML Format Files</span></span>  
  
-   <span data-ttu-id="9103a-112">XML-файлы форматирования описывают сами себя, благодаря чему упрощается их чтение, создание и расширение.</span><span class="sxs-lookup"><span data-stu-id="9103a-112">XML format files are self-describing, making them easy to read, create, and extend.</span></span> <span data-ttu-id="9103a-113">Они доступны для чтения человеком, что позволяет легко понять, как интерпретируются данные во время массовых операций.</span><span class="sxs-lookup"><span data-stu-id="9103a-113">They are human readable, making it easy to understand how data is interpreted during bulk operations.</span></span>  
  
-   <span data-ttu-id="9103a-114">XML-файлы форматирования содержат типы данных целевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="9103a-114">XML format files contain the data types of target columns.</span></span>  <span data-ttu-id="9103a-115">Запись XML четко описывает типы данных и элементы файла данных, а также соответствие элементов данных столбцам таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-115">The XML encoding clearly describes the data types and data elements of the data file and also the mapping between data elements and table columns.</span></span>  
  
     <span data-ttu-id="9103a-116">Это позволяет отделить представление данных в файле от типов данных полей.</span><span class="sxs-lookup"><span data-stu-id="9103a-116">This enables separation between how data is represented in the data file and what data type is associated with each field in the file.</span></span> <span data-ttu-id="9103a-117">Например, если файл данных содержит данные в символьном представлении, то тип данных SQL соответствующего столбца будет утрачен.</span><span class="sxs-lookup"><span data-stu-id="9103a-117">For example, if a data file contains a character representation of the data, the corresponding SQL column type is lost.</span></span>  
  
-   <span data-ttu-id="9103a-118">XML-файл форматирования позволяет загружать из файлов данных поля, содержащие единственный тип данных LOB.</span><span class="sxs-lookup"><span data-stu-id="9103a-118">An XML format file allows for loading of a field that contains a single large object (LOB) data type from a data file.</span></span>  
  
-   <span data-ttu-id="9103a-119">XML-файл форматирования можно улучшить, сохранив совместимость с предыдущими версиями.</span><span class="sxs-lookup"><span data-stu-id="9103a-119">An XML format file can be enhanced yet remain compatible with its earlier versions.</span></span> <span data-ttu-id="9103a-120">Кроме того, понятность записи XML облегчает создание нескольких файлов форматирования для некоторого файла данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-120">Furthermore, the clarity of XML encoding facilitates the creation of multiple format files for a given data file.</span></span> <span data-ttu-id="9103a-121">Это удобно при сопоставлении всех или некоторых полей данных со столбцами в различных таблицах и представлениях.</span><span class="sxs-lookup"><span data-stu-id="9103a-121">This is useful if you have to map all or some of the data fields to columns in different tables or views.</span></span>  
  
-   <span data-ttu-id="9103a-122">Синтаксис XML-файла форматирования не зависит от направления операции; для операций массового импорта и массового экспорта синтаксис одинаков.</span><span class="sxs-lookup"><span data-stu-id="9103a-122">The XML syntax is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span>  
  
-   <span data-ttu-id="9103a-123">XML-файлы форматирования можно использовать для массового импорта данных в таблицы или несекционированные представления и массового экспорта данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-123">You can use XML format files to bulk import data into tables or non-partitioned views and to bulk export data.</span></span>  
  
-   <span data-ttu-id="9103a-124">Для функции OPENROWSET(BULK...) указание целевой таблицы является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9103a-124">For the OPENROWSET(BULK...) function specifying a target table is optional.</span></span> <span data-ttu-id="9103a-125">Это обусловлено тем, что эта функция для чтения данных из файла данных использует XML-файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="9103a-125">This is because the function relies on the XML format file to read data from a data file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9103a-126">Целевая таблица необходима при работе с командой **bcp** и инструкцией BULK INSERT, которая использует столбцы целевой таблицы при преобразовании типов.</span><span class="sxs-lookup"><span data-stu-id="9103a-126">A target table is necessary with the **bcp** command and the BULK INSERT statement, which uses the target table columns to do the type conversion.</span></span>  
  
##  <a name="structure-of-xml-format-files"></a><a name="StructureOfXmlFFs"></a> <span data-ttu-id="9103a-127">Структура XML-файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="9103a-127">Structure of XML Format Files</span></span>  
 <span data-ttu-id="9103a-128">XML-файлы форматирования, как и файл форматирования в формате, отличном от XML, определяют формат и структуру полей данных в файле данных и сопоставляют их со столбцами целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-128">Like a non-XML format file, an XML format file defines the format and structure of the data fields in a data file and maps those data fields to columns in a single target table.</span></span>  
  
 <span data-ttu-id="9103a-129">XML-файл форматирования содержит два основных элемента, \<RECORD> и \<ROW>.</span><span class="sxs-lookup"><span data-stu-id="9103a-129">An XML format file possesses two main components, \<RECORD> and \<ROW>:</span></span>  
  
-   <span data-ttu-id="9103a-130">\<RECORD> описывает способ хранения данных в файле данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-130">\<RECORD> describes the data as it is stored in the data file.</span></span>  
  
     <span data-ttu-id="9103a-131">Каждый элемент \<RECORD> содержит набор из одного элемента \<FIELD> или нескольких.</span><span class="sxs-lookup"><span data-stu-id="9103a-131">Each \<RECORD> element contains a set of one or more \<FIELD> elements.</span></span> <span data-ttu-id="9103a-132">Эти элементы соответствуют полям в файле данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-132">These elements correspond to fields in the data file.</span></span> <span data-ttu-id="9103a-133">Базовый синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9103a-133">The basic syntax is as follows:</span></span>  
  
     \<RECORD>  
  
     <span data-ttu-id="9103a-134">\<FIELD .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="9103a-134">\<FIELD .../> [ ...*n* ]</span></span>  
  
     \</RECORD>  
  
     <span data-ttu-id="9103a-135">Каждый элемент \<FIELD> описывает содержимое определенного поля данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-135">Each \<FIELD> element describes the contents of a specific data field.</span></span> <span data-ttu-id="9103a-136">Поле может быть сопоставлено только с одним столбцом таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-136">A field can only be mapped to one column in the table.</span></span> <span data-ttu-id="9103a-137">Столбцам не обязательно сопоставлять все поля.</span><span class="sxs-lookup"><span data-stu-id="9103a-137">Not all fields need to be mapped to columns.</span></span>  
  
     <span data-ttu-id="9103a-138">Поле в файле данных может иметь фиксированную или переменную длину или завершаться определенным символом.</span><span class="sxs-lookup"><span data-stu-id="9103a-138">A field in a data file can be either of fixed/variable length or character terminated.</span></span> <span data-ttu-id="9103a-139">*Значение поля* может быть представлено в следующем виде: символ (однобайтовое представление), широкий символ (двухбайтовое представление Юникода), собственный формат базы данных или имя файла.</span><span class="sxs-lookup"><span data-stu-id="9103a-139">A *field value* can be represented as: a character (using single-byte representation), a wide character (using Unicode two-byte representation), native database format, or a file name.</span></span> <span data-ttu-id="9103a-140">Если значение поля представляется в виде имени файла, оно указывает на файл, который содержит значение столбца BLOB в целевой таблице.</span><span class="sxs-lookup"><span data-stu-id="9103a-140">If a field value is represented as a file name, the file name points to the file that contains the value of a BLOB column in the target table.</span></span>  
  
-   <span data-ttu-id="9103a-141">\<ROW> описывает, как создавать строки данных из файла данных, который импортируется в таблицу сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9103a-141">\<ROW> describes how to construct data rows from a data file when the data from the file is imported into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
     <span data-ttu-id="9103a-142">Элемент \<ROW> содержит набор элементов \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="9103a-142">A \<ROW> element contains a set of \<COLUMN> elements.</span></span> <span data-ttu-id="9103a-143">Эти элементы соответствуют столбцам таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-143">These elements correspond to table columns.</span></span> <span data-ttu-id="9103a-144">Базовый синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9103a-144">The basic syntax is as follows:</span></span>  
  
     \<ROW>  
  
     <span data-ttu-id="9103a-145">\<COLUMN .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="9103a-145">\<COLUMN .../> [ ...*n* ]</span></span>  
  
     \</ROW>  
  
     <span data-ttu-id="9103a-146">Каждый элемент \<COLUMN> можно сопоставить только с одним полем в файле данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-146">Each \<COLUMN> element can be mapped to only one field in the data file.</span></span> <span data-ttu-id="9103a-147">Порядок элементов \<COLUMN> в элементе \<ROW> задает порядок, в котором они будут возвращены массовой операцией.</span><span class="sxs-lookup"><span data-stu-id="9103a-147">The order of the \<COLUMN> elements in the \<ROW> element defines the order in which they are returned by the bulk operation.</span></span> <span data-ttu-id="9103a-148">XML-файл форматирования назначает каждому элементу \<COLUMN> локальное имя, не имеющее отношения к столбцу целевой таблицы операции массового импорта.</span><span class="sxs-lookup"><span data-stu-id="9103a-148">The XML format file assigns each \<COLUMN> element a local name that has no relationship to the column in the target table of a bulk import operation.</span></span>  
  
##  <a name="schema-syntax-for-xml-format-files"></a><a name="SchemaSyntax"></a> <span data-ttu-id="9103a-149">Синтаксис схемы для XML-файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="9103a-149">Schema Syntax for XML Format Files</span></span>  
 <span data-ttu-id="9103a-150">Этот раздел содержит список элементов и атрибутов схемы XML для XML-файлов форматирования.</span><span class="sxs-lookup"><span data-stu-id="9103a-150">This section contains a summary of the elements and attributes of the XML schema for XML format files.</span></span> <span data-ttu-id="9103a-151">Синтаксис файла форматирования не зависит от направления операции; для операций массового импорта и массового экспорта синтаксис одинаков.</span><span class="sxs-lookup"><span data-stu-id="9103a-151">The syntax of a format file is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span> <span data-ttu-id="9103a-152">В разделе также рассматривается использование элементов \<ROW> и \<COLUMN> массовым импортом и помещение значения xsi:type элемента в набор данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-152">This section also considers how bulk import uses the \<ROW> and \<COLUMN> elements and how to put the xsi:type value of an element into a data set.</span></span>  
  
 <span data-ttu-id="9103a-153">Чтобы узнать, как этот синтаксис соответствует реальным XML-файлам форматирования, см. далее раздел [Образец XML-файлов форматирования](#SampleXmlFFs).</span><span class="sxs-lookup"><span data-stu-id="9103a-153">To see how the syntax corresponds to actual XML format files, see [Sample XML Format Files](#SampleXmlFFs), later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9103a-154">Можно изменить файл форматирования, чтобы обеспечить возможность массового импорта данных из файла данных, в котором количество или порядок полей отличаются от количества или порядка столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-154">You can modify a format file to let you bulk import from a data file in which the number and/or order of the fields differ from the number and/or order of table columns.</span></span> <span data-ttu-id="9103a-155">Дополнительные сведения см в разделе [Файлы форматирования для импорта или экспорта данных (SQL Server)](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9103a-155">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
  
  
###  <a name="basic-syntax-of-the-xml-schema"></a><a name="BasicSyntax"></a> <span data-ttu-id="9103a-156">Основной синтаксис схемы XML</span><span class="sxs-lookup"><span data-stu-id="9103a-156">Basic Syntax of the XML Schema</span></span>  
 <span data-ttu-id="9103a-157">Данные инструкции синтаксиса показывают только элементы (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW> и \<COLUMN>) и их основные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="9103a-157">This syntax statements show only the elements (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW>, and \<COLUMN>) and their basic attributes.</span></span>  
  
 \<BCPFORMAT ...>  
  
 \<RECORD>  
  
 <span data-ttu-id="9103a-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span><span class="sxs-lookup"><span data-stu-id="9103a-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span></span>  
  
 />  
  
 \</RECORD>  
  
 \<ROW>  
  
 <span data-ttu-id="9103a-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span><span class="sxs-lookup"><span data-stu-id="9103a-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span></span>  
  
 />  
  
 \</ROW>  
  
 \</BCPFORMAT>  
  
> [!NOTE]  
>  <span data-ttu-id="9103a-160">Дополнительные атрибуты, связанные со значением типа xsi:type в элементах \<FIELD> или \<COLUMN>, описаны ниже в этом подразделе.</span><span class="sxs-lookup"><span data-stu-id="9103a-160">Additional attributes that are associated with the value of the xsi:type in a \<FIELD> or \<COLUMN> element are described later in this topic.</span></span>  
  

  
####  <a name="schema-elements"></a><a name="SchemaElements"></a> <span data-ttu-id="9103a-161">Элементы схемы</span><span class="sxs-lookup"><span data-stu-id="9103a-161">Schema Elements</span></span>  
 <span data-ttu-id="9103a-162">В этом разделе кратко описаны назначения каждого элемента, определяемого схемой XML для XML-файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="9103a-162">This section summarizes the purpose of each element that the XML schema defines for XML format files.</span></span> <span data-ttu-id="9103a-163">Атрибуты описаны в отдельных подразделах ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9103a-163">The attributes are described in separate sections later in this topic.</span></span>  
  
 \<BCPFORMAT>  
 <span data-ttu-id="9103a-164">Элемент файла форматирования, который определяет структуру записей данного файла данных и его соответствие столбцам строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-164">Is the format-file element that defines the record structure of a given data file and its correspondence to the columns of a table row in the table.</span></span>  
  
 \<RECORD .../>  
 <span data-ttu-id="9103a-165">Определяет составной элемент, содержащий один элемент \<FIELD> или несколько.</span><span class="sxs-lookup"><span data-stu-id="9103a-165">Defines a complex element containing one or more \<FIELD> elements.</span></span> <span data-ttu-id="9103a-166">Порядок, в котором поля объявлены в файле форматирования, является порядком, в котором эти поля будут расположены в файле данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-166">The order in which the fields are declared in the format file is the order in which those fields appear in the data file.</span></span>  
  
 \<FIELD .../>  
 <span data-ttu-id="9103a-167">Определяет поле в файле данных, которое содержит данные.</span><span class="sxs-lookup"><span data-stu-id="9103a-167">Defines a field in data file, which contains data.</span></span>  
  
 <span data-ttu-id="9103a-168">Атрибуты этого элемента описаны в разделе [Атрибуты элемента \<FIELD>](#AttrOfFieldElement) ниже в данной статье.</span><span class="sxs-lookup"><span data-stu-id="9103a-168">The attributes of this element are discussed in [Attributes of the \<FIELD> Element](#AttrOfFieldElement), later in this topic.</span></span>  
  
 \<ROW .../>  
 <span data-ttu-id="9103a-169">Определяет составной элемент, содержащий один элемент \<COLUMN> или несколько.</span><span class="sxs-lookup"><span data-stu-id="9103a-169">Defines a complex element containing one or more \<COLUMN> elements.</span></span> <span data-ttu-id="9103a-170">Порядок элементов \<COLUMN> не зависит от порядка элементов \<FIELD> в определении RECORD.</span><span class="sxs-lookup"><span data-stu-id="9103a-170">The order of the \<COLUMN> elements is independent of the order of \<FIELD> elements in a RECORD definition.</span></span> <span data-ttu-id="9103a-171">Скорее, порядок элементов \<COLUMN> в файле форматирования определяет порядок столбцов результирующего набора строк.</span><span class="sxs-lookup"><span data-stu-id="9103a-171">Rather, the order of the \<COLUMN> elements in a format file determines the column order of the resultant rowset.</span></span> <span data-ttu-id="9103a-172">Поля данных загружаются в порядке, в котором соответствующие элементы \<COLUMN> объявлены в элементе \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="9103a-172">Data fields are loaded in the order in which the corresponding \<COLUMN> elements are declared in the \<COLUMN> element.</span></span>  
  
 <span data-ttu-id="9103a-173">Дополнительные сведения см. в разделе [Как массовый импорт использует элемент \<ROW>](#HowUsesROW) ниже в данной статье.</span><span class="sxs-lookup"><span data-stu-id="9103a-173">For more information, see [How Bulk Import Uses the \<ROW> Element](#HowUsesROW), later in this topic.</span></span>  
  
 \<COLUMN>  
 <span data-ttu-id="9103a-174">Определяет столбец как элемент (\<COLUMN>).</span><span class="sxs-lookup"><span data-stu-id="9103a-174">Defines a column as an element (\<COLUMN>).</span></span> <span data-ttu-id="9103a-175">Каждый элемент \<COLUMN> соответствует элементу \<FIELD> (чей идентификатор задан в атрибуте SOURCE элемента \<COLUMN>).</span><span class="sxs-lookup"><span data-stu-id="9103a-175">Each \<COLUMN> element corresponds to a \<FIELD> element (whose ID is specified in the SOURCE attribute of the \<COLUMN> element).</span></span>  
  
 <span data-ttu-id="9103a-176">Атрибуты этого элемента описаны в разделе [Атрибуты элемента \<COLUMN>](#AttrOfColumnElement) ниже в данной статье.</span><span class="sxs-lookup"><span data-stu-id="9103a-176">The attributes of this element are discussed in [Attributes of the \<COLUMN> Element](#AttrOfColumnElement), later in this topic.</span></span> <span data-ttu-id="9103a-177">См. также раздел [Как массовый импорт использует элемент \<COLUMN>](#HowUsesColumn) ниже в данной статье.</span><span class="sxs-lookup"><span data-stu-id="9103a-177">Also see, [How Bulk Import Uses the \<COLUMN> Element](#HowUsesColumn), later in this topic.</span></span>  
  
 \</BCPFORMAT>  
 <span data-ttu-id="9103a-178">Требуется в конце файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="9103a-178">Required to end the format file.</span></span>  
  
####  <a name="attributes-of-the-field-element"></a><a name="AttrOfFieldElement"></a> <span data-ttu-id="9103a-179">Атрибуты элемента \<FIELD></span><span class="sxs-lookup"><span data-stu-id="9103a-179">Attributes of the \<FIELD> Element</span></span>  
 <span data-ttu-id="9103a-180">В этом разделе описываются атрибуты элемента \<FIELD>, которые обобщены в следующем синтаксисе схемы.</span><span class="sxs-lookup"><span data-stu-id="9103a-180">This section describes the attributes of the \<FIELD> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="9103a-181">Значения xsi:type элемента <FIELD</span><span class="sxs-lookup"><span data-stu-id="9103a-181"><FIELD</span></span>  
  
 <span data-ttu-id="9103a-182">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-182">ID **="*`fieldID`*"**</span></span>  
  
 <span data-ttu-id="9103a-183">xsi **:** Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-183">xsi **:** type **="*`fieldType`*"**</span></span>  
  
 <span data-ttu-id="9103a-184">[ LENGTH **="*`n`*"** ]</span><span class="sxs-lookup"><span data-stu-id="9103a-184">[ LENGTH **="*`n`*"** ]</span></span>  
  
 <span data-ttu-id="9103a-185">[PREFIX_LENGTH **= " *`p`* "** ]</span><span class="sxs-lookup"><span data-stu-id="9103a-185">[ PREFIX_LENGTH **="*`p`*"** ]</span></span>  
  
 <span data-ttu-id="9103a-186">[MAX_LENGTH **= " *`m`* "** ]</span><span class="sxs-lookup"><span data-stu-id="9103a-186">[ MAX_LENGTH **="*`m`*"** ]</span></span>  
  
 <span data-ttu-id="9103a-187">[Collation **= " *`collationName`* "** ]</span><span class="sxs-lookup"><span data-stu-id="9103a-187">[ COLLATION **="*`collationName`*"** ]</span></span>  
  
 <span data-ttu-id="9103a-188">[ПРИЗНАК конца **= " *`terminator`* "** ]</span><span class="sxs-lookup"><span data-stu-id="9103a-188">[ TERMINATOR **="*`terminator`*"** ]</span></span>  
  
 />  
  
 <span data-ttu-id="9103a-189">Каждый элемент \<FIELD> независим от других.</span><span class="sxs-lookup"><span data-stu-id="9103a-189">Each \<FIELD> element is independent of the others.</span></span> <span data-ttu-id="9103a-190">Поле описывается на основе следующих атрибутов:</span><span class="sxs-lookup"><span data-stu-id="9103a-190">A field is described in terms of the following attributes:</span></span>  
  
|<span data-ttu-id="9103a-191">Атрибут FIELD</span><span class="sxs-lookup"><span data-stu-id="9103a-191">FIELD Attribute</span></span>|<span data-ttu-id="9103a-192">Описание</span><span class="sxs-lookup"><span data-stu-id="9103a-192">Description</span></span>|<span data-ttu-id="9103a-193">Необязательный или</span><span class="sxs-lookup"><span data-stu-id="9103a-193">Optional /</span></span><br /><br /> <span data-ttu-id="9103a-194">Обязательно</span><span class="sxs-lookup"><span data-stu-id="9103a-194">Required</span></span>|  
|---------------------|-----------------|------------------------------|  
|<span data-ttu-id="9103a-195">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-195">ID **="*`fieldID`*"**</span></span>|<span data-ttu-id="9103a-196">Задает логическое имя поля в файле данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-196">Specifies the logical name of the field in the data file.</span></span> <span data-ttu-id="9103a-197">Идентификатор поля является ключом, используемым для обращения к полю.</span><span class="sxs-lookup"><span data-stu-id="9103a-197">The ID of a field is the key used to refer to the field.</span></span><br /><br /> <span data-ttu-id="9103a-198"><поле ID **= " *`fieldID`* "**/> сопоставляется с <столбца source **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="9103a-198"><FIELD ID **="*`fieldID`*"**/> maps to <COLUMN SOURCE **="*`fieldID`*"**/></span></span>|<span data-ttu-id="9103a-199">Обязательный</span><span class="sxs-lookup"><span data-stu-id="9103a-199">Required</span></span>|  
|<span data-ttu-id="9103a-200">xsi: Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-200">xsi:type **="*`fieldType`*"**</span></span>|<span data-ttu-id="9103a-201">Это конструкция XML (используется как атрибут), которая указывает тип экземпляра элемента.</span><span class="sxs-lookup"><span data-stu-id="9103a-201">This is an XML construct (used like an attribute) that identifies the type of the instance of the element.</span></span> <span data-ttu-id="9103a-202">Значение атрибута *fieldType* определяет, какой из необязательных атрибутов (см. ниже) необходим в данном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="9103a-202">The value of *fieldType* determines which of the optional attributes (below) you need in a given instance.</span></span>|<span data-ttu-id="9103a-203">Обязательный (в зависимости от типа данных)</span><span class="sxs-lookup"><span data-stu-id="9103a-203">Required (depending on the data type)</span></span>|  
|<span data-ttu-id="9103a-204">LENGTH **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-204">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="9103a-205">Этот атрибут определяет длину для экземпляра типа данных фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="9103a-205">This attribute defines the length for an instance of a fixed-length data type.</span></span><br /><br /> <span data-ttu-id="9103a-206">Значение *n* должно быть положительным целым числом.</span><span class="sxs-lookup"><span data-stu-id="9103a-206">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="9103a-207">Необязательный, когда не требуется значением xsi:type</span><span class="sxs-lookup"><span data-stu-id="9103a-207">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="9103a-208">PREFIX_LENGTH **= " *`p`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-208">PREFIX_LENGTH **="*`p`*"**</span></span>|<span data-ttu-id="9103a-209">Этот атрибут определяет длину префикса для двоичного представления данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-209">This attribute defines the prefix length for a binary data representation.</span></span> <span data-ttu-id="9103a-210">Значение PREFIX_LENGTH, *p*, должно быть равно 1, 2, 4 или 8.</span><span class="sxs-lookup"><span data-stu-id="9103a-210">The PREFIX_LENGTH value, *p*, must be one of the following: 1, 2, 4, or 8.</span></span>|<span data-ttu-id="9103a-211">Необязательный, когда не требуется значением xsi:type</span><span class="sxs-lookup"><span data-stu-id="9103a-211">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="9103a-212">MAX_LENGTH **= " *`m`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-212">MAX_LENGTH **="*`m`*"**</span></span>|<span data-ttu-id="9103a-213">Этот атрибут является максимальным числом байтов, которые могут храниться в данном поле.</span><span class="sxs-lookup"><span data-stu-id="9103a-213">This attribute is the maximum number of bytes that can be stored in a given field.</span></span> <span data-ttu-id="9103a-214">Без целевой таблицы максимальная длина столбца неизвестна.</span><span class="sxs-lookup"><span data-stu-id="9103a-214">Without a target table, the column max-length is not known.</span></span> <span data-ttu-id="9103a-215">Атрибут MAX_LENGTH ограничивает максимальную длину выходного столбца символов, ограничивая хранилище, выделенное для значения столбца.</span><span class="sxs-lookup"><span data-stu-id="9103a-215">The MAX_LENGTH attribute restricts the maximum length of an output character column, limiting the storage allocated for the column value.</span></span> <span data-ttu-id="9103a-216">Это особенно удобно при использовании параметра BULK функции OPENROWSET в предложении SELECT FROM.</span><span class="sxs-lookup"><span data-stu-id="9103a-216">This is especially convenient when using the OPENROWSET function's BULK option in a SELECT FROM clause.</span></span><br /><br /> <span data-ttu-id="9103a-217">Значение *m* должно быть положительным целым числом.</span><span class="sxs-lookup"><span data-stu-id="9103a-217">The value of *m* must be a positive integer.</span></span> <span data-ttu-id="9103a-218">По умолчанию максимальная длина 8000 символов для столбца типа **char** и 4000 символов для столбца типа **nchar** .</span><span class="sxs-lookup"><span data-stu-id="9103a-218">By default, the maximum length is 8000 characters for a **char** column and 4000 characters for an **nchar** column.</span></span>|<span data-ttu-id="9103a-219">Необязательно</span><span class="sxs-lookup"><span data-stu-id="9103a-219">Optional</span></span>|  
|<span data-ttu-id="9103a-220">Параметры сортировки **= " *`collationName`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-220">COLLATION **="*`collationName`*"**</span></span>|<span data-ttu-id="9103a-221">Аргумент COLLATION допустим только для символьных полей.</span><span class="sxs-lookup"><span data-stu-id="9103a-221">COLLATION is only allowed for character fields.</span></span> <span data-ttu-id="9103a-222">Список имен параметров сортировки SQL см. в разделе [Имя параметров сортировки SQL Server (Transact-SQL)](/sql/t-sql/statements/sql-server-collation-name-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="9103a-222">For a list of the SQL collation names, see [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span></span>|<span data-ttu-id="9103a-223">Необязательно</span><span class="sxs-lookup"><span data-stu-id="9103a-223">Optional</span></span>|  
|<span data-ttu-id="9103a-224">ПРИЗНАК конца **= " *`terminator`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-224">TERMINATOR **= "*`terminator`*"**</span></span>|<span data-ttu-id="9103a-225">Этот атрибут задает признак конца поля данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-225">This attribute specifies the terminator of a data field.</span></span> <span data-ttu-id="9103a-226">Признаком конца может быть любой символ.</span><span class="sxs-lookup"><span data-stu-id="9103a-226">The terminator can be any character.</span></span> <span data-ttu-id="9103a-227">Признак конца должен быть уникальным символом, который не является частью данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-227">The terminator must be a unique character that is not part of the data.</span></span><br /><br /> <span data-ttu-id="9103a-228">По умолчанию признаком конца поля является символ табуляции (представленный как «\t»).</span><span class="sxs-lookup"><span data-stu-id="9103a-228">By default, the field terminator is the tab character (represented as \t).</span></span> <span data-ttu-id="9103a-229">Чтобы указать знак абзаца, используйте сочетание символов «\r\n».</span><span class="sxs-lookup"><span data-stu-id="9103a-229">To represent a paragraph mark, use \r\n.</span></span>|<span data-ttu-id="9103a-230">Используется только со значением xsi:type символьных данных, которые требуют наличия этого атрибута</span><span class="sxs-lookup"><span data-stu-id="9103a-230">Used only with an xsi:type of character data, which requires this attribute</span></span>|  
  
#####  <a name="xsitype-values-of-the-field-element"></a><a name="XsiTypeValuesOfFIELD"></a> <span data-ttu-id="9103a-231">Значения Xsi:type элемента \<FIELD></span><span class="sxs-lookup"><span data-stu-id="9103a-231">Xsi:type values of the \<FIELD> Element</span></span>  
 <span data-ttu-id="9103a-232">Значение xsi:type — это конструкция XML, используемая как атрибут и определяющая тип данных экземпляра элемента.</span><span class="sxs-lookup"><span data-stu-id="9103a-232">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="9103a-233">Сведения по применению этой конструкции см. в пункте «Размещение значения xsi:type в наборе данных» ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9103a-233">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="9103a-234">Значение xsi:type элемента \<FIELD> поддерживает следующие типы данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-234">The xsi:type value of the \<FIELD> element supports the following data types.</span></span>  
  
|<span data-ttu-id="9103a-235">Значения \<FIELD> xsi:type</span><span class="sxs-lookup"><span data-stu-id="9103a-235">\<FIELD> xsi:type values</span></span>|<span data-ttu-id="9103a-236">Обязательные XML-атрибуты</span><span class="sxs-lookup"><span data-stu-id="9103a-236">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="9103a-237">для типа данных</span><span class="sxs-lookup"><span data-stu-id="9103a-237">for Data Type</span></span>|<span data-ttu-id="9103a-238">Необязательные XML-атрибуты</span><span class="sxs-lookup"><span data-stu-id="9103a-238">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="9103a-239">для типа данных</span><span class="sxs-lookup"><span data-stu-id="9103a-239">for Data Type</span></span>|  
|-------------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="9103a-240">**NativeFixed**</span><span class="sxs-lookup"><span data-stu-id="9103a-240">**NativeFixed**</span></span>|`LENGTH`|<span data-ttu-id="9103a-241">Нет.</span><span class="sxs-lookup"><span data-stu-id="9103a-241">None.</span></span>|  
|<span data-ttu-id="9103a-242">**NativePrefix**</span><span class="sxs-lookup"><span data-stu-id="9103a-242">**NativePrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="9103a-243">MAX_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9103a-243">MAX_LENGTH</span></span>|  
|<span data-ttu-id="9103a-244">**CharFixed**</span><span class="sxs-lookup"><span data-stu-id="9103a-244">**CharFixed**</span></span>|`LENGTH`|<span data-ttu-id="9103a-245">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9103a-245">COLLATION</span></span>|  
|<span data-ttu-id="9103a-246">**NCharFixed**</span><span class="sxs-lookup"><span data-stu-id="9103a-246">**NCharFixed**</span></span>|`LENGTH`|<span data-ttu-id="9103a-247">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9103a-247">COLLATION</span></span>|  
|<span data-ttu-id="9103a-248">**CharPrefix**</span><span class="sxs-lookup"><span data-stu-id="9103a-248">**CharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="9103a-249">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="9103a-249">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="9103a-250">**NCharPrefix**</span><span class="sxs-lookup"><span data-stu-id="9103a-250">**NCharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="9103a-251">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="9103a-251">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="9103a-252">**CharTerm**</span><span class="sxs-lookup"><span data-stu-id="9103a-252">**CharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="9103a-253">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="9103a-253">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="9103a-254">**NCharTerm**</span><span class="sxs-lookup"><span data-stu-id="9103a-254">**NCharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="9103a-255">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="9103a-255">MAX_LENGTH, COLLATION</span></span>|  
  
 <span data-ttu-id="9103a-256">Дополнительные сведения о типах данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9103a-256">For more information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
####  <a name="attributes-of-the-column-element"></a><a name="AttrOfColumnElement"></a> <span data-ttu-id="9103a-257">Атрибуты элемента \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="9103a-257">Attributes of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="9103a-258">В этом разделе описываются атрибуты элемента \<COLUMN>, которые обобщены в следующем синтаксисе схемы.</span><span class="sxs-lookup"><span data-stu-id="9103a-258">This section describes the attributes of the \<COLUMN> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="9103a-259">\<COLUMN</span><span class="sxs-lookup"><span data-stu-id="9103a-259">\<COLUMN</span></span>  
  
 <span data-ttu-id="9103a-260">SOURCE = "*fieldID*"</span><span class="sxs-lookup"><span data-stu-id="9103a-260">SOURCE = "*fieldID*"</span></span>  
  
 <span data-ttu-id="9103a-261">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="9103a-261">NAME = "*columnName*"</span></span>  
  
 <span data-ttu-id="9103a-262">xsi:type = "*columnType*"</span><span class="sxs-lookup"><span data-stu-id="9103a-262">xsi:type = "*columnType*"</span></span>  
  
 <span data-ttu-id="9103a-263">[ LENGTH = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="9103a-263">[ LENGTH = "*n*" ]</span></span>  
  
 <span data-ttu-id="9103a-264">[ PRECISION = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="9103a-264">[ PRECISION = "*n*" ]</span></span>  
  
 <span data-ttu-id="9103a-265">[ SCALE = "*value*" ]</span><span class="sxs-lookup"><span data-stu-id="9103a-265">[ SCALE = "*value*" ]</span></span>  
  
 <span data-ttu-id="9103a-266">[ NULLABLE = { "YES"</span><span class="sxs-lookup"><span data-stu-id="9103a-266">[ NULLABLE = { "YES"</span></span>  
  
 <span data-ttu-id="9103a-267">"NO" } ]</span><span class="sxs-lookup"><span data-stu-id="9103a-267">"NO" } ]</span></span>  
  
 />  
  
 <span data-ttu-id="9103a-268">Поле сопоставлено со столбцом целевой таблицы с использованием следующих атрибутов:</span><span class="sxs-lookup"><span data-stu-id="9103a-268">A field is mapped to a column in the target table using the following attributes:</span></span>  
  
|<span data-ttu-id="9103a-269">Атрибут COLUMN</span><span class="sxs-lookup"><span data-stu-id="9103a-269">COLUMN Attribute</span></span>|<span data-ttu-id="9103a-270">Описание</span><span class="sxs-lookup"><span data-stu-id="9103a-270">Description</span></span>|<span data-ttu-id="9103a-271">Необязательный или</span><span class="sxs-lookup"><span data-stu-id="9103a-271">Optional /</span></span><br /><br /> <span data-ttu-id="9103a-272">Обязательно</span><span class="sxs-lookup"><span data-stu-id="9103a-272">Required</span></span>|  
|----------------------|-----------------|------------------------------|  
|<span data-ttu-id="9103a-273">SOURCE **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-273">SOURCE **="*`fieldID`*"**</span></span>|<span data-ttu-id="9103a-274">Задает идентификатор поля, сопоставляемого со столбцом.</span><span class="sxs-lookup"><span data-stu-id="9103a-274">Specifies the ID of the field being mapped to the column.</span></span><br /><br /> <span data-ttu-id="9103a-275"><Column source **= " *`fieldID`* "**/> сопоставляется с <поля с идентификатором **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="9103a-275"><COLUMN SOURCE **="*`fieldID`*"**/> maps to <FIELD ID **="*`fieldID`*"**/></span></span>|<span data-ttu-id="9103a-276">Обязательно</span><span class="sxs-lookup"><span data-stu-id="9103a-276">Required</span></span>|  
|<span data-ttu-id="9103a-277">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="9103a-277">NAME = "*columnName*"</span></span>|<span data-ttu-id="9103a-278">Задает имя столбца в наборе строк, представленном файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="9103a-278">Specifies the name of the column in the row set represented by the format file.</span></span> <span data-ttu-id="9103a-279">Это имя столбца используется для идентификации столбца в результирующем наборе, и оно не обязательно должно соответствовать имени столбца целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-279">This column name is used to identify the column in the result set, and it need not correspond to the column name used in the target table.</span></span>|<span data-ttu-id="9103a-280">Обязательно</span><span class="sxs-lookup"><span data-stu-id="9103a-280">Required</span></span>|  
|<span data-ttu-id="9103a-281">xsi **:** Type **= " *`ColumnType`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-281">xsi **:** type **="*`ColumnType`*"**</span></span>|<span data-ttu-id="9103a-282">Это конструкция XML (используется как атрибут), которая указывает тип данных экземпляра элемента.</span><span class="sxs-lookup"><span data-stu-id="9103a-282">This is an XML construct (used like an attribute) that identifies the data type of the instance of the element.</span></span> <span data-ttu-id="9103a-283">Значение атрибута *ColumnType* определяет, какой из необязательных атрибутов (см. ниже) необходим в данном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="9103a-283">The value of *ColumnType* determines which of the optional attributes (below) you need in a given instance.</span></span><br /><br /> <span data-ttu-id="9103a-284">Примечание. Возможные значения *ColumnType* и связанные с ними атрибуты перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9103a-284">Note: The possible values of *ColumnType* and their associated attributes are listed in the next table.</span></span>|<span data-ttu-id="9103a-285">Необязательно</span><span class="sxs-lookup"><span data-stu-id="9103a-285">Optional</span></span>|  
|<span data-ttu-id="9103a-286">LENGTH **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-286">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="9103a-287">Определяет длину для экземпляра типа данных фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="9103a-287">Defines the length for an instance of a fixed-length data type.</span></span> <span data-ttu-id="9103a-288">Атрибут LENGTH используется только в том случае, если значение xsi:type является строковым типом данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-288">LENGTH is used only when the xsi:type is a string data type.</span></span><br /><br /> <span data-ttu-id="9103a-289">Значение *n* должно быть положительным целым числом.</span><span class="sxs-lookup"><span data-stu-id="9103a-289">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="9103a-290">Необязательный (доступен только в том случае, если значение xsi:type является строковым типом данных)</span><span class="sxs-lookup"><span data-stu-id="9103a-290">Optional (available only if the xsi:type is a string data type)</span></span>|  
|<span data-ttu-id="9103a-291">PRECISION **="*`n`*"**</span><span class="sxs-lookup"><span data-stu-id="9103a-291">PRECISION **="*`n`*"**</span></span>|<span data-ttu-id="9103a-292">Указывает количество цифр в числе.</span><span class="sxs-lookup"><span data-stu-id="9103a-292">Indicates the number of digits in a number.</span></span> <span data-ttu-id="9103a-293">Например, число 123,45 имеет точность 5.</span><span class="sxs-lookup"><span data-stu-id="9103a-293">For example, the number 123.45 has a precision of 5.</span></span><br /><br /> <span data-ttu-id="9103a-294">Значение должно быть положительным целым числом.</span><span class="sxs-lookup"><span data-stu-id="9103a-294">The value must be a positive integer.</span></span>|<span data-ttu-id="9103a-295">Необязательный (доступен только в том случае, если значение xsi:type является переменным числовым типом данных)</span><span class="sxs-lookup"><span data-stu-id="9103a-295">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="9103a-296">SCALE **= " *`int`* "**</span><span class="sxs-lookup"><span data-stu-id="9103a-296">SCALE **="*`int`*"**</span></span>|<span data-ttu-id="9103a-297">Указывает количество цифр справа от десятичной запятой в числе.</span><span class="sxs-lookup"><span data-stu-id="9103a-297">Indicates the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="9103a-298">Например, число 123,45 имеет масштаб 2.</span><span class="sxs-lookup"><span data-stu-id="9103a-298">For example, the number 123.45 has a scale of 2.</span></span><br /><br /> <span data-ttu-id="9103a-299">Значением должно быть целое число.</span><span class="sxs-lookup"><span data-stu-id="9103a-299">The value must be an integer.</span></span>|<span data-ttu-id="9103a-300">Необязательный (доступен только в том случае, если значение xsi:type является переменным числовым типом данных)</span><span class="sxs-lookup"><span data-stu-id="9103a-300">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="9103a-301">NULLABLE **=** { **"** YES **"**</span><span class="sxs-lookup"><span data-stu-id="9103a-301">NULLABLE **=** { **"** YES **"**</span></span><br /><br /> <span data-ttu-id="9103a-302">**"** NO **"** }</span><span class="sxs-lookup"><span data-stu-id="9103a-302">**"** NO **"** }</span></span>|<span data-ttu-id="9103a-303">Указывает, может ли столбец принимать значение NULL.</span><span class="sxs-lookup"><span data-stu-id="9103a-303">Indicates whether a column can assume NULL values.</span></span> <span data-ttu-id="9103a-304">Этот атрибут полностью независим от FIELDS.</span><span class="sxs-lookup"><span data-stu-id="9103a-304">This attribute is completely independent of FIELDS.</span></span> <span data-ttu-id="9103a-305">Однако если столбец не NULLABLE и в поле указано значение NULL (значение не указано), результатом будет ошибка выполнения.</span><span class="sxs-lookup"><span data-stu-id="9103a-305">However, if a column is not NULLABLE and field specifies NULL (by not specifying any value), a run-time error results.</span></span><br /><br /> <span data-ttu-id="9103a-306">Атрибут NULLABLE используется только при выполнении простых инструкций SELECT FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="9103a-306">The NULLABLE attribute is used only if you do a plain SELECT FROM OPENROWSET(BULK...) statement.</span></span>|<span data-ttu-id="9103a-307">Необязательный (доступен для любого типа данных)</span><span class="sxs-lookup"><span data-stu-id="9103a-307">Optional (available for any data type)</span></span>|  
  
#####  <a name="xsitype-values-of-the-column-element"></a><a name="XsiTypeValuesOfCOLUMN"></a> <span data-ttu-id="9103a-308">Значения Xsi:type элемента \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="9103a-308">Xsi:type values of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="9103a-309">Значение xsi:type — это конструкция XML, используемая как атрибут и определяющая тип данных экземпляра элемента.</span><span class="sxs-lookup"><span data-stu-id="9103a-309">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="9103a-310">Сведения по применению этой конструкции см. в пункте «Размещение значения xsi:type в наборе данных» ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9103a-310">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="9103a-311">Элемент \<COLUMN> поддерживает следующие собственные типы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="9103a-311">The \<COLUMN> element supports native SQL data types, as follows:</span></span>  
  
|<span data-ttu-id="9103a-312">Категория типа</span><span class="sxs-lookup"><span data-stu-id="9103a-312">Type Category</span></span>|<span data-ttu-id="9103a-313">\<COLUMN> Типы данных</span><span class="sxs-lookup"><span data-stu-id="9103a-313">\<COLUMN> Data Types</span></span>|<span data-ttu-id="9103a-314">Обязательные XML-атрибуты</span><span class="sxs-lookup"><span data-stu-id="9103a-314">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="9103a-315">для типа данных</span><span class="sxs-lookup"><span data-stu-id="9103a-315">for Data Type</span></span>|<span data-ttu-id="9103a-316">Необязательные XML-атрибуты</span><span class="sxs-lookup"><span data-stu-id="9103a-316">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="9103a-317">для типа данных</span><span class="sxs-lookup"><span data-stu-id="9103a-317">for Data Type</span></span>|  
|-------------------|---------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="9103a-318">исправление</span><span class="sxs-lookup"><span data-stu-id="9103a-318">Fixed</span></span>|<span data-ttu-id="9103a-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT` и `SQLUNIQUEID`</span><span class="sxs-lookup"><span data-stu-id="9103a-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT`, and `SQLUNIQUEID`</span></span>|<span data-ttu-id="9103a-320">Нет.</span><span class="sxs-lookup"><span data-stu-id="9103a-320">None.</span></span>|<span data-ttu-id="9103a-321">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9103a-321">NULLABLE</span></span>|  
|<span data-ttu-id="9103a-322">Переменное число</span><span class="sxs-lookup"><span data-stu-id="9103a-322">Variable Number</span></span>|<span data-ttu-id="9103a-323">`SQLDECIMAL` и `SQLNUMERIC`</span><span class="sxs-lookup"><span data-stu-id="9103a-323">`SQLDECIMAL` and `SQLNUMERIC`</span></span>|<span data-ttu-id="9103a-324">Нет.</span><span class="sxs-lookup"><span data-stu-id="9103a-324">None.</span></span>|<span data-ttu-id="9103a-325">NULLABLE, PRECISION, SCALE</span><span class="sxs-lookup"><span data-stu-id="9103a-325">NULLABLE, PRECISION, SCALE</span></span>|  
|<span data-ttu-id="9103a-326">Большой объект (LOB)</span><span class="sxs-lookup"><span data-stu-id="9103a-326">LOB</span></span>|<span data-ttu-id="9103a-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT` и `SQLUDT`</span><span class="sxs-lookup"><span data-stu-id="9103a-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT`, and `SQLUDT`</span></span>|<span data-ttu-id="9103a-328">Нет.</span><span class="sxs-lookup"><span data-stu-id="9103a-328">None.</span></span>|<span data-ttu-id="9103a-329">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9103a-329">NULLABLE</span></span>|  
|<span data-ttu-id="9103a-330">Большой символьный объект (CLOB)</span><span class="sxs-lookup"><span data-stu-id="9103a-330">Character LOB</span></span>|`SQLNTEXT`|<span data-ttu-id="9103a-331">Нет.</span><span class="sxs-lookup"><span data-stu-id="9103a-331">None.</span></span>|<span data-ttu-id="9103a-332">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9103a-332">NULLABLE</span></span>|  
|<span data-ttu-id="9103a-333">Двоичная строка</span><span class="sxs-lookup"><span data-stu-id="9103a-333">Binary string</span></span>|<span data-ttu-id="9103a-334">`SQLBINARY` и `SQLVARYBIN`</span><span class="sxs-lookup"><span data-stu-id="9103a-334">`SQLBINARY` and `SQLVARYBIN`</span></span>|<span data-ttu-id="9103a-335">Нет.</span><span class="sxs-lookup"><span data-stu-id="9103a-335">None.</span></span>|<span data-ttu-id="9103a-336">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="9103a-336">NULLABLE, LENGTH</span></span>|  
|<span data-ttu-id="9103a-337">Строка символов</span><span class="sxs-lookup"><span data-stu-id="9103a-337">Character string</span></span>|<span data-ttu-id="9103a-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR` и `SQLNVARCHAR`</span><span class="sxs-lookup"><span data-stu-id="9103a-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR`, and `SQLNVARCHAR`</span></span>|<span data-ttu-id="9103a-339">Нет.</span><span class="sxs-lookup"><span data-stu-id="9103a-339">None.</span></span>|<span data-ttu-id="9103a-340">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="9103a-340">NULLABLE, LENGTH</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9103a-341">Для массового экспорта или импорта данных SQLXML используется один из следующих типов данных в файле форматирования. SQLCHAR или SQLVARYCHAR (данные посылаются в кодовой странице клиента или в кодовой странице, предполагаемой параметрами сортировки), SQLNCHAR или SQLNVARCHAR (данные посылаются в формате Юникод) и SQLBINARY или SQLVARYBIN (данные посылаются без преобразования).</span><span class="sxs-lookup"><span data-stu-id="9103a-341">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
 <span data-ttu-id="9103a-342">Дополнительные сведения о типах значений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9103a-342">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
###  <a name="how-bulk-import-uses-the-row-element"></a><a name="HowUsesROW"></a> <span data-ttu-id="9103a-343">Как массовый импорт использует элемент \<ROW></span><span class="sxs-lookup"><span data-stu-id="9103a-343">How Bulk Import Uses the \<ROW> Element</span></span>  
 <span data-ttu-id="9103a-344">Элемент \<ROW> не учитывается в некоторых контекстах.</span><span class="sxs-lookup"><span data-stu-id="9103a-344">The \<ROW> element is ignored in some contexts.</span></span> <span data-ttu-id="9103a-345">Влияние элемента \<ROW> на операцию массового импорта зависит от того, как выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="9103a-345">Whether the \<ROW> element affects a bulk-import operation depends on how the operation is performed:</span></span>  
  
-   <span data-ttu-id="9103a-346">команда **bcp**</span><span class="sxs-lookup"><span data-stu-id="9103a-346">the **bcp** command</span></span>  
  
     <span data-ttu-id="9103a-347">При загрузке данных в целевую таблицу команда **bcp** не учитывает компонент \<ROW>.</span><span class="sxs-lookup"><span data-stu-id="9103a-347">When data is loaded into a target table, **bcp** ignores the \<ROW> component.</span></span> <span data-ttu-id="9103a-348">Вместо этого команда **bcp** загружает данные с учетом типов столбцов целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-348">Instead, **bcp** loads the data based on the column types of the target table.</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)] <span data-ttu-id="9103a-349">инструкции (команда BULK INSERT и поставщик массового набора строк OPENROWSET)</span><span class="sxs-lookup"><span data-stu-id="9103a-349">statements (BULK INSERT and OPENROWSET's Bulk rowset provider)</span></span>  
  
     <span data-ttu-id="9103a-350">При мас=совом импорте данных в таблицу инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)] используют компонент \<ROW> для формирования входного набора строк.</span><span class="sxs-lookup"><span data-stu-id="9103a-350">When bulk importing data into a table, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements use the \<ROW> component to generate the input rowset.</span></span> <span data-ttu-id="9103a-351">Инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)] также выполняют соответствующие преобразования типов, основываясь на типах столбцов, указанных для элемента \<ROW> и соответствующего столбца в целевой таблице.</span><span class="sxs-lookup"><span data-stu-id="9103a-351">Also, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements perform appropriate type conversions based on the column types specified under \<ROW> and the corresponding column in the target table.</span></span> <span data-ttu-id="9103a-352">При несовпадении типов столбцов в файле форматирования и в целевой таблице производится дополнительное преобразование типов,</span><span class="sxs-lookup"><span data-stu-id="9103a-352">If a mismatch exists between column types as specified in the format file and in the target table, an extra type conversion occurs.</span></span> <span data-ttu-id="9103a-353">Это дополнительное преобразование типа может привести к некоторым различиям (т. е. к потере точности) в работе команды BULK INSERT или поставщика массового набора строк OPENROWSET по сравнению с командой **bcp**.</span><span class="sxs-lookup"><span data-stu-id="9103a-353">This extra type conversion may lead to some discrepancy (that is, a loss of precision) in behavior in BULK INSERT or OPENROWSET's Bulk rowset provider as compared to **bcp**.</span></span>  
  
     <span data-ttu-id="9103a-354">Сведения в элементе \<ROW> позволяют построить строку без дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="9103a-354">The information in the \<ROW> element allows a row to be constructed without requiring any additional information.</span></span> <span data-ttu-id="9103a-355">По этой причине набор строк можно сформировать при помощи инструкции SELECT (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span><span class="sxs-lookup"><span data-stu-id="9103a-355">For this reason, you can generate a rowset using a SELECT statement (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9103a-356">Чтобы использовать предложение OPENROWSET BULK, необходим файл форматирования (обратите внимание, что преобразование типа данных поля в тип данных столбца доступно только при наличии XML-файла форматирования).</span><span class="sxs-lookup"><span data-stu-id="9103a-356">The OPENROWSET BULK clause requires a format file (note that converting from the data type of the field to the data type of a column is available only with an XML format file).</span></span>  
  
###  <a name="how-bulk-import-uses-the-column-element"></a><a name="HowUsesColumn"></a> <span data-ttu-id="9103a-357">Как массовый импорт использует элемент \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="9103a-357">How Bulk Import Uses the \<COLUMN> Element</span></span>  
 <span data-ttu-id="9103a-358">Для массового импорта данных в таблицу элементы \<COLUMN> в файле форматирования сопоставляют поле файла данных со столбцами таблицы, указывая:</span><span class="sxs-lookup"><span data-stu-id="9103a-358">For bulk importing data into a table, the \<COLUMN> elements in a format file map a data-file field to table columns by specifying:</span></span>  
  
-   <span data-ttu-id="9103a-359">позицию каждого поля в строке файла данных;</span><span class="sxs-lookup"><span data-stu-id="9103a-359">The position of each field within a row in the data file.</span></span>  
  
-   <span data-ttu-id="9103a-360">тип столбца, используемый для преобразования типа данных поля в необходимый тип данных столбца.</span><span class="sxs-lookup"><span data-stu-id="9103a-360">The column type, which is used to convert the field data type to the desired column data type.</span></span>  
  
 <span data-ttu-id="9103a-361">Если с полем не сопоставлено ни одного столбца, поле не копируется в сформированные строки.</span><span class="sxs-lookup"><span data-stu-id="9103a-361">If no column is mapped to a field, the field is not copied into the generated row(s).</span></span> <span data-ttu-id="9103a-362">Такое поведение позволяет файлам данных формировать строки с различными столбцами (в разных таблицах).</span><span class="sxs-lookup"><span data-stu-id="9103a-362">This behavior allows a data file to generate rows with different columns (in different tables).</span></span>  
  
 <span data-ttu-id="9103a-363">Аналогично для массового экспорта данных из таблицы каждый элемент \<COLUMN> в файле форматирования сопоставляет столбец строки входной таблицы с соответствующим полем выходного файла данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-363">Similarly, for bulk exporting data from a table, each \<COLUMN> in the format file maps the column from the input table row to its corresponding field in the output data file.</span></span>  
  
###  <a name="putting-the-xsitype-value-into-a-data-set"></a><a name="PutXsiTypeValueIntoDataSet"></a> <span data-ttu-id="9103a-364">Помещение значения xsi:type в набор данных</span><span class="sxs-lookup"><span data-stu-id="9103a-364">Putting the xsi:type Value into a Data Set</span></span>  
 <span data-ttu-id="9103a-365">Если XML-документ проверяется при помощи языка определения схемы XML (XSD), значение xsi:type не помещается в набор данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-365">When an XML document is validated through the XML Schema Definition (XSD) language, the xsi:type value is not put into the data set.</span></span> <span data-ttu-id="9103a-366">Тем не менее, сведения xsi:type можно поместить в набор данных, загрузив XML-файл форматирования в XML-документ, например `myDoc`, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="9103a-366">However, you can put the xsi:type information into the data set by loading the XML format file into an XML document (for example, `myDoc`), as illustrated in the following code snippet:</span></span>  
  
```  
...;  
myDoc.LoadXml(xmlFormat);  
XmlNodeList ColumnList = myDoc.GetElementsByTagName("COLUMN");  
for(int i=0;i<ColumnList.Count;i++)  
{  
   Console.Write("COLUMN: xsi:type=" +ColumnList[i].Attributes["type",  
      "http://www.w3.org/2001/XMLSchema-instance"].Value+"\n");  
}  
```  
  
##  <a name="sample-xml-format-files"></a><a name="SampleXmlFFs"></a> <span data-ttu-id="9103a-367">Образцы XML-файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="9103a-367">Sample XML Format Files</span></span>  
 <span data-ttu-id="9103a-368">Этот раздел содержит сведения о различных способах использования XML-файлов форматирования, в том числе пример работы с базой данных [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9103a-368">This section contains information on using XML format files in a variety of cases, including an [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9103a-369">В файлах данных, приведенных в следующих примерах, `<tab>` обозначает символ табуляции в файле данных, а `<return>` означает символ возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="9103a-369">In the data files shown in the following examples, `<tab>` indicates a tab character in a data file, and `<return>` indicates a carriage return.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="9103a-370">Сведения о создании файлов форматирования см. в разделе [Создание файла форматирования (SQL Server)](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9103a-370">For information about how to create format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="a-ordering-character-data-fields-the-same-as-table-columns"></a><a name="OrderCharFieldsSameAsCols"></a> <span data-ttu-id="9103a-371">A.</span><span class="sxs-lookup"><span data-stu-id="9103a-371">A.</span></span> <span data-ttu-id="9103a-372">упорядочивание полей с символьными данными по столбцам таблицы;</span><span class="sxs-lookup"><span data-stu-id="9103a-372">Ordering character-data fields the same as table columns</span></span>  
 <span data-ttu-id="9103a-373">В следующем примере представлен XML-файл форматирования, описывающий файл данных, в котором содержатся три поля символьных данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-373">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="9103a-374">Файл форматирования сопоставляет файл данных с таблицей, содержащей три столбца.</span><span class="sxs-lookup"><span data-stu-id="9103a-374">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="9103a-375">Поля данных соответствуют «один к одному» столбцам таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-375">The data fields correspond one-to-one with the columns of the table.</span></span>  
  
 <span data-ttu-id="9103a-376">**Таблица (строка):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="9103a-376">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="9103a-377">**Файл данных (запись):** Age\<tab>FirstName\<tab>LastName\<return></span><span class="sxs-lookup"><span data-stu-id="9103a-377">**Data file (record):** Age\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="9103a-378">Следующий XML-файл форматирования считывает данные из файла данных в таблицу.</span><span class="sxs-lookup"><span data-stu-id="9103a-378">The following XML format file reads from the data file to the table.</span></span>  
  
 <span data-ttu-id="9103a-379">В элементе `<RECORD>` файл форматирования представляет значения во всех трех полях в символьном виде.</span><span class="sxs-lookup"><span data-stu-id="9103a-379">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span> <span data-ttu-id="9103a-380">Для каждого поля атрибут `TERMINATOR` указывает признак конца поля, следующий за значением.</span><span class="sxs-lookup"><span data-stu-id="9103a-380">For each field, the `TERMINATOR` attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="9103a-381">Поля данных соответствуют «один к одному» столбцам таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-381">The data fields correspond one-to-one with the columns of the table.</span></span> <span data-ttu-id="9103a-382">В элементе `<ROW>` файла форматирования столбец `Age` сопоставляется с первым полем, столбец `FirstName` — со вторым, а столбец `LastName` — с третьим.</span><span class="sxs-lookup"><span data-stu-id="9103a-382">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the second field, and the column `LastName` to the third field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>   
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="2" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="3" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="9103a-383">Эквивалентный пример [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] см. в разделе [Создание файла форматирования (SQL Server)](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9103a-383">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="b-ordering-data-fields-and-table-columns-differently"></a><a name="OrderFieldsAndColsDifferently"></a> <span data-ttu-id="9103a-384">Б.</span><span class="sxs-lookup"><span data-stu-id="9103a-384">B.</span></span> <span data-ttu-id="9103a-385">упорядочивание полей данных в порядке, отличающемся от порядка столбцов таблицы;</span><span class="sxs-lookup"><span data-stu-id="9103a-385">Ordering data fields and table columns differently</span></span>  
 <span data-ttu-id="9103a-386">В следующем примере представлен XML-файл форматирования, описывающий файл данных, в котором содержатся три поля символьных данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-386">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="9103a-387">Файл форматирования сопоставляет файл данных с таблицей, содержащей три столбца, порядок следования которых отличается от порядка следования полей файла данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-387">The format file maps the data file to a table that contains three columns that are ordered differently from the fields of the data file.</span></span>  
  
 <span data-ttu-id="9103a-388">**Таблица (строка):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="9103a-388">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="9103a-389">**Файл данных** (запись): Age\<tab>Lastname\<tab>Firstname\<return></span><span class="sxs-lookup"><span data-stu-id="9103a-389">**Data file** (record): Age\<tab>Lastname\<tab>Firstname\<return></span></span>  
  
 <span data-ttu-id="9103a-390">В элементе `<RECORD>` файл форматирования представляет значения во всех трех полях в символьном виде.</span><span class="sxs-lookup"><span data-stu-id="9103a-390">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span>  
  
 <span data-ttu-id="9103a-391">В элементе `<ROW>` файла форматирования столбец `Age` сопоставляется с первым полем, столбец `FirstName` — с третьим, а столбец `LastName` — со вторым.</span><span class="sxs-lookup"><span data-stu-id="9103a-391">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the second field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="2" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="9103a-392">Эквивалентный пример [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] см. в разделе [Использование файла форматирования для сопоставления столбцов таблицы с полями файла данных (SQL Server)](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9103a-392">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span></span>  
  
### <a name="c-omitting-a-data-field"></a><span data-ttu-id="9103a-393">В.</span><span class="sxs-lookup"><span data-stu-id="9103a-393">C.</span></span> <span data-ttu-id="9103a-394">пропуск поля данных;</span><span class="sxs-lookup"><span data-stu-id="9103a-394">Omitting a data field</span></span>  
 <span data-ttu-id="9103a-395">В следующем примере представлен XML-файл форматирования, описывающий файл данных, в котором содержатся четыре поля символьных данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-395">The following example shows an XML format file that describes a data file containing four fields of character data.</span></span> <span data-ttu-id="9103a-396">Файл форматирования сопоставляет файл данных с таблицей, содержащей три столбца.</span><span class="sxs-lookup"><span data-stu-id="9103a-396">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="9103a-397">Второе поле данных не связывается ни с одним столбцом таблицы.</span><span class="sxs-lookup"><span data-stu-id="9103a-397">The second data field does not correspond to any table column.</span></span>  
  
 <span data-ttu-id="9103a-398">**Таблица (строка):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span><span class="sxs-lookup"><span data-stu-id="9103a-398">**Table (row):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span></span>  
  
 <span data-ttu-id="9103a-399">**Файл данных (запись):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="9103a-399">**Data file (record):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="9103a-400">В элементе `<RECORD>` файла форматирования значения данных представлены во всех четырех полях как символьные данные.</span><span class="sxs-lookup"><span data-stu-id="9103a-400">In the `<RECORD>` element, the format file represents the data values in all four fields as character data.</span></span> <span data-ttu-id="9103a-401">Для каждого поля атрибут TERMINATOR указывает признак конца, следующий за значением данных.</span><span class="sxs-lookup"><span data-stu-id="9103a-401">For each field, the TERMINATOR attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="9103a-402">В элементе `<ROW>` файла форматирования столбец `Age` сопоставляется с первым полем, столбец `FirstName` — с третьим, а столбец `LastName` — с четвертым.</span><span class="sxs-lookup"><span data-stu-id="9103a-402">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the fourth field.</span></span>  
  
```  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="10"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="4" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="9103a-403">Эквивалентный пример [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] см. в разделе [Использование файла форматирования для пропуска поля данных (SQL Server)](use-a-format-file-to-skip-a-data-field-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9103a-403">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span></span>  
  
###  <a name="d-mapping-field-xsitype-to-column-xsitype"></a><a name="MapXSItype"></a> <span data-ttu-id="9103a-404">Г.</span><span class="sxs-lookup"><span data-stu-id="9103a-404">D.</span></span> <span data-ttu-id="9103a-405">Сопоставление \<FIELD> xsi: Type и \<COLUMN> xsi: Type</span><span class="sxs-lookup"><span data-stu-id="9103a-405">Mapping \<FIELD> xsi:type to \<COLUMN> xsi:type</span></span>  
 <span data-ttu-id="9103a-406">Следующий пример демонстрирует различные типы полей и их сопоставление со столбцами.</span><span class="sxs-lookup"><span data-stu-id="9103a-406">The following example shows different types of fields and their mappings to columns.</span></span>  
  
```  
<?xml version = "1.0"?>  
<BCPFORMAT  
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   <RECORD>  
      <FIELD xsi:type="CharTerm" ID="C1" TERMINATOR="\t"   
            MAX_LENGTH="4"/>  
      <FIELD xsi:type="CharFixed" ID="C2" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="CharPrefix" ID="C3" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharTerm" ID="C4" TERMINATOR="\t"   
         MAX_LENGTH="4"/>  
      <FIELD xsi:type="NCharFixed" ID="C5" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharPrefix" ID="C6" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NativeFixed" ID="C7" LENGTH="4"/>  
   </RECORD>  
   <ROW>  
      <COLUMN SOURCE="C1" NAME="Age" xsi:type="SQLTINYINT"/>  
      <COLUMN SOURCE="C2" NAME="FirstName" xsi:type="SQLVARYCHAR"   
      LENGTH="16" NULLABLE="NO"/>  
      <COLUMN SOURCE="C3" NAME="LastName" />  
      <COLUMN SOURCE="C4" NAME="Salary" xsi:type="SQLMONEY"/>  
      <COLUMN SOURCE="C5" NAME="Picture" xsi:type="SQLIMAGE"/>  
      <COLUMN SOURCE="C6" NAME="Bio" xsi:type="SQLTEXT"/>  
      <COLUMN SOURCE="C7" NAME="Interest"xsi:type="SQLDECIMAL"   
      PRECISION="5" SCALE="3"/>  
   </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="e-mapping-xml-data-to-a-table"></a><a name="MapXMLDataToTbl"></a> <span data-ttu-id="9103a-407">Д.</span><span class="sxs-lookup"><span data-stu-id="9103a-407">E.</span></span> <span data-ttu-id="9103a-408">сопоставление XML-данных с таблицей;</span><span class="sxs-lookup"><span data-stu-id="9103a-408">Mapping XML data to a table</span></span>  
 <span data-ttu-id="9103a-409">В следующем примере создается пустая таблица из двух столбцов (`t_xml`), первый столбец которой сопоставляется с типом данных `int` , а второй — с типом данных `xml` .</span><span class="sxs-lookup"><span data-stu-id="9103a-409">The following example creates an empty two-column table (`t_xml`), in which the first column maps to the `int` data type and the second column maps to the `xml` data type.</span></span>  
  
```  
CREATE TABLE t_xml (c1 int, c2 xml)  
```  
  
 <span data-ttu-id="9103a-410">Следующий XML-файл форматирования загружает файл данных в таблицу `t_xml`.</span><span class="sxs-lookup"><span data-stu-id="9103a-410">The following XML format file would load a data file into table `t_xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" PREFIX_LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="8"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="c1" xsi:type="SQLINT"/>  
  <COLUMN SOURCE="2" NAME="c2" xsi:type="SQLNCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="f-importing-fixed-length-or-fixed-width-fields"></a><a name="ImportFixedFields"></a> <span data-ttu-id="9103a-411">Е.</span><span class="sxs-lookup"><span data-stu-id="9103a-411">F.</span></span> <span data-ttu-id="9103a-412">импорт полей фиксированной длины и полей фиксированной ширины.</span><span class="sxs-lookup"><span data-stu-id="9103a-412">Importing fixed-length or fixed-width fields</span></span>  
 <span data-ttu-id="9103a-413">В следующем примере описываются поля фиксированной ширины в `10` или `6` символов каждое.</span><span class="sxs-lookup"><span data-stu-id="9103a-413">The following example describes fixed fields of `10` or `6` characters each.</span></span> <span data-ttu-id="9103a-414">Файл форматирования представляет длину и ширину этих полей в виде `LENGTH="10"` и `LENGTH="6"`соответственно.</span><span class="sxs-lookup"><span data-stu-id="9103a-414">The format file represents these field lengths/widths as `LENGTH="10"` and `LENGTH="6"`, respectively.</span></span> <span data-ttu-id="9103a-415">Каждая строка файлов данных заканчивается сочетанием символов возврата каретки и перевода строки, {CR}{LF}, которое в файле форматирования представлено в виде `TERMINATOR="\r\n"`.</span><span class="sxs-lookup"><span data-stu-id="9103a-415">Every row of the data files ends with a carriage return-line feed combination, {CR}{LF}, which the format file represents as `TERMINATOR="\r\n"`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT  
       xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharFixed" LENGTH="10"/>  
    <FIELD ID="2" xsi:type="CharFixed" LENGTH="6"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="C1" xsi:type="SQLINT" />  
    <COLUMN SOURCE="2" NAME="C2" xsi:type="SQLINT" />  
  </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="additional-examples"></a><a name="AdditionalExamples"></a> <span data-ttu-id="9103a-416">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="9103a-416">Additional Examples</span></span>  
 <span data-ttu-id="9103a-417">Дополнительные примеры как для файлов форматирования в формате, отличном от XML, так и для XML-файлов форматирования см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9103a-417">For additional examples of both non-XML format files and XML format files, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9103a-418">Пропуск столбца таблицы с помощью файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-418">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="9103a-419">Использование файла форматирования для пропуска поля данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-419">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="9103a-420">Использование файла форматирования для сопоставления столбцов таблицы с полями файла данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-420">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9103a-421">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9103a-421">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9103a-422">Создание файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-422">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="9103a-423">Использование файла форматирования для массового импорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-423">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="9103a-424">Пропуск столбца таблицы с помощью файла форматирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-424">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="9103a-425">Использование файла форматирования для пропуска поля данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-425">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="9103a-426">Использование файла форматирования для сопоставления столбцов таблицы с полями файла данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-426">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="9103a-427">См. также</span><span class="sxs-lookup"><span data-stu-id="9103a-427">Related Content</span></span>  
 <span data-ttu-id="9103a-428">Нет.</span><span class="sxs-lookup"><span data-stu-id="9103a-428">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9103a-429">См. также:</span><span class="sxs-lookup"><span data-stu-id="9103a-429">See Also</span></span>  
 <span data-ttu-id="9103a-430">[Массовый импорт и экспорт данных (SQL Server)](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9103a-430">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="9103a-431">[Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9103a-431">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="9103a-432">[Файлы формата, отличные от XML (SQL Server)](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9103a-432">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="9103a-433">Файлы форматирования для импорта или экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9103a-433">Format Files for Importing or Exporting Data &#40;SQL Server&#41;</span></span>](format-files-for-importing-or-exporting-data-sql-server.md)  
  
  
