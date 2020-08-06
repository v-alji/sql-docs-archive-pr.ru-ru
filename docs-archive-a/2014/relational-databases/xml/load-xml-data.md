---
title: Загрузка XML-данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], loading
- loading XML data
ms.assetid: d1741e8d-f44e-49ec-9f14-10208b5468a7
author: rothja
ms.author: jroth
ms.openlocfilehash: c48d1d6feccb7df9fec9801ee56abcab99884754
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733673"
---
# <a name="load-xml-data"></a><span data-ttu-id="a9f8d-102">Загрузка XML-данных</span><span class="sxs-lookup"><span data-stu-id="a9f8d-102">Load XML Data</span></span>
  <span data-ttu-id="a9f8d-103">Есть несколько способов передачи XML-данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9f8d-103">You can transfer XML data into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in several ways.</span></span> <span data-ttu-id="a9f8d-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="a9f8d-104">For example:</span></span>  
  
-   <span data-ttu-id="a9f8d-105">Если в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] данные хранятся в столбце типа [n]text или image, то эту таблицу можно импортировать с помощью служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9f8d-105">If you have your data in an [n]text or image column in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, you can import the table by using [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="a9f8d-106">Изменить тип столбца на XML можно с использованием инструкции ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-106">Change the column type to XML by using the ALTER TABLE statement.</span></span>  
  
-   <span data-ttu-id="a9f8d-107">Массовое копирование данных из другой базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно выполнить с использованием команды bcp out, после чего с помощью команды bcp in произвести массовую вставку данных в базу данных более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-107">You can bulk copy your data from another [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using bcp out, and then bulk insert the data into the later version database by using bcp in.</span></span>  
  
-   <span data-ttu-id="a9f8d-108">Если в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] данные хранятся в реляционных столбцах, необходимо создать новую таблицу со столбцом [n]text и, возможно, с первичным ключевым столбцом для идентификации строк.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-108">If you have data in relational columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, create a new table with an [n]text column and, optionally, a primary key column for a row identifier.</span></span> <span data-ttu-id="a9f8d-109">Чтобы получить XML-данные, созданные на сервере при помощи инструкции FOR XML, и записать их в столбец `[n]text`, требуется программный код на клиентской стороне.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-109">Use client-side programming to retrieve the XML that is generated at the server with FOR XML and write it into the `[n]text` column.</span></span> <span data-ttu-id="a9f8d-110">Затем эти данные необходимо передать в базу данных более поздней версии, выбрав любую из вышеупомянутых методик.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-110">Then, use the previously mentioned techniques to transfer data to a later version database.</span></span> <span data-ttu-id="a9f8d-111">XML-данные можно напрямую записать в XML-столбец базы данных более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-111">You can choose to write the XML into an XML column in the later version database directly.</span></span>  
  
## <a name="bulk-loading-xml-data"></a><span data-ttu-id="a9f8d-112">Массовая загрузка XML-данных</span><span class="sxs-lookup"><span data-stu-id="a9f8d-112">Bulk loading XML data</span></span>  
 <span data-ttu-id="a9f8d-113">Массовую загрузку XML-данных на сервер можно осуществить при помощи реализованных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]средств массовой загрузки, таких как bcp.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-113">You can bulk load XML data into the server by using the bulk loading capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as bcp.</span></span> <span data-ttu-id="a9f8d-114">Инструкция OPENROWSET позволяет загрузить данные в XML-столбец из файлов.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-114">OPENROWSET allows you to load data into an XML column from files.</span></span> <span data-ttu-id="a9f8d-115">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-115">The following example illustrates this point.</span></span>  
  
##### <a name="example-loading-xml-from-files"></a><span data-ttu-id="a9f8d-116">Пример Загрузка XML-данных из файлов</span><span class="sxs-lookup"><span data-stu-id="a9f8d-116">Example: Loading XML from Files</span></span>  
 <span data-ttu-id="a9f8d-117">Следующий пример показывает, как вставить строку в таблицу T. Значение XML-столбца загружается из файла «C:\MyFile\xmlfile.xml» как объект CLOB, а целочисленному столбцу назначается значение 10.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-117">This example shows how to insert a row in table T. The value of the XML column is loaded from file C:\MyFile\xmlfile.xml as CLOB, and the integer column is supplied the value 10.</span></span>  
  
```  
INSERT INTO T  
SELECT 10, xCol  
FROM    (SELECT *      
    FROM OPENROWSET (BULK 'C:\MyFile\xmlfile.xml', SINGLE_CLOB)   
 AS xCol) AS R(xCol)  
```  
  
## <a name="text-encoding"></a><span data-ttu-id="a9f8d-118">Кодировка текста</span><span class="sxs-lookup"><span data-stu-id="a9f8d-118">Text Encoding</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a9f8d-119">хранит XML-данные в кодировке Юникод (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="a9f8d-119">stores XML data in Unicode (UTF-16).</span></span> <span data-ttu-id="a9f8d-120">XML-данные, извлекаемые из баз данных сервера, предоставляются в кодировке UTF-16.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-120">XML data retrieved from the server comes out in UTF-16 encoding.</span></span> <span data-ttu-id="a9f8d-121">Если требуются данные в другой кодировке, извлеченные данные нужно преобразовать.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-121">If you want a different encoding, you have to perform the required conversion on the retrieved data.</span></span> <span data-ttu-id="a9f8d-122">Иногда XML-данные могут быть представлены в другой кодировке.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-122">Sometimes, the XML data may be in a different encoding.</span></span> <span data-ttu-id="a9f8d-123">Если это так, во время загрузки данных нужно быть внимательным.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-123">If it is, you have to use care during data loading.</span></span> <span data-ttu-id="a9f8d-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="a9f8d-124">For example:</span></span>  
  
-   <span data-ttu-id="a9f8d-125">Если текст XML представлен в кодировке Юникод (UCS-2, UTF-16), можно назначить его XML-столбцу, переменной или параметру без каких-либо проблем.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-125">If your text XML is in Unicode (UCS-2, UTF-16), you can assign it to an XML column, variable, or parameter  without any problems.</span></span>  
  
-   <span data-ttu-id="a9f8d-126">Если кодировка отлична от Юникода и неявна из-за исходной кодовой страницы, строковая кодовая страница в базе данных должна быть той же самой или совместимой с элементами кода, которые следует загрузить.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-126">If the encoding is not Unicode and is implicit, because of the source code page, the string code page in the database should be the same as or compatible with the code points that you want to load.</span></span> <span data-ttu-id="a9f8d-127">Если нужно, используйте предложение COLLATE.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-127">If required, use COLLATE.</span></span> <span data-ttu-id="a9f8d-128">Если такой кодовой страницы на сервере не существует, необходимо добавить явную XML-декларацию с корректной кодировкой.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-128">If no such server code page exists, you have to add an explicit XML declaration with the correct encoding.</span></span>  
  
-   <span data-ttu-id="a9f8d-129">Чтобы явно задать кодировку, воспользуйтесь типом `varbinary()`, поскольку он не работает с кодовыми страницами либо символьный тип для соответствующей кодовой страницы.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-129">To use an explicit encoding, use either the `varbinary()` type, which has no interaction with code pages, or use a string type of the appropriate code page.</span></span> <span data-ttu-id="a9f8d-130">После этого назначьте данные XML-столбцу, переменной или параметру.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-130">Then, assign the data to an XML column, variable, or parameter.</span></span>  
  
### <a name="example-explicitly-specifying-an-encoding"></a><span data-ttu-id="a9f8d-131">Пример явное указание кодировки</span><span class="sxs-lookup"><span data-stu-id="a9f8d-131">Example: Explicitly Specifying an Encoding</span></span>  
 <span data-ttu-id="a9f8d-132">Предположим, что есть XML-документ vcdoc, хранящийся в типе данных `varchar(max)`, который не объявлен явно как XML.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-132">Assume that you have an XML document, vcdoc, stored as `varchar(max)` that does not have an explicit XML declaration.</span></span> <span data-ttu-id="a9f8d-133">Следующая инструкция добавляет объявление XML с кодировкой «iso8859-1», присоединяет к нему XML-документ, приводит результат к типу `varbinary(max)` (чтобы сохранить двоичное представление) и, наконец, приводит его к типу XML.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-133">The following statement adds an XML declaration with the encoding "iso8859-1", concatenates the XML document, casts the result to `varbinary(max)` so that the byte representation is preserved, and then finally casts it to XML.</span></span> <span data-ttu-id="a9f8d-134">Это позволяет процессору XML выполнять синтаксический анализ данных в соответствии с указанной кодировкой «iso8859-1» и создавать для строковых значений соответствующее представление UTF-16.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-134">This enables the XML processor to parse the data according to the specified encoding "iso8859-1" and generate the corresponding UTF-16 representation for string values.</span></span>  
  
```  
SELECT CAST(   
CAST (('<?xml version="1.0" encoding="iso8859-1"?>'+ vcdoc) AS VARBINARY (MAX))   
 AS XML)  
```  
  
### <a name="string-encoding-incompatibilities"></a><span data-ttu-id="a9f8d-135">Несоответствия кодировок строк</span><span class="sxs-lookup"><span data-stu-id="a9f8d-135">String Encoding Incompatibilities</span></span>  
 <span data-ttu-id="a9f8d-136">При копировании и вставке XML как строкового литерала в окно редактора запросов служб в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]могут возникнуть несоответствия с кодировкой строк типа (N)VARCHAR.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-136">If you copy and paste XML as a string literal into the Query Editor window in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you might experience [N]VARCHAR string encoding incompatibilities.</span></span> <span data-ttu-id="a9f8d-137">Это будет зависеть от кодировки копируемого экземпляра XML.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-137">This will depend on the encoding of your XML instance.</span></span> <span data-ttu-id="a9f8d-138">Во многих случаях может возникнуть необходимость удаления XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-138">In many cases, you may want to remove the XML declaration.</span></span> <span data-ttu-id="a9f8d-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="a9f8d-139">For example:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
  <xsd:schema ...  
```  
  
 <span data-ttu-id="a9f8d-140">Затем нужно будет добавить N, чтобы сделать экземпляр XML экземпляром Юникода.</span><span class="sxs-lookup"><span data-stu-id="a9f8d-140">You should then include an N to make the XML instance an instance of Unicode.</span></span> <span data-ttu-id="a9f8d-141">Пример:</span><span class="sxs-lookup"><span data-stu-id="a9f8d-141">For example:</span></span>  
  
```  
-- Assign XML instance to a variable.  
DECLARE @X XML  
SET @X = N'...'  
-- Insert XML instance into an xml type column.  
INSERT INTO T VALUES (N'...')  
-- Create an XML schema collection  
CREATE XML SCHEMA COLLECTION XMLCOLL1 AS N'<xsd:schema ... '  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9f8d-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="a9f8d-142">See Also</span></span>  
 [<span data-ttu-id="a9f8d-143">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a9f8d-143">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
