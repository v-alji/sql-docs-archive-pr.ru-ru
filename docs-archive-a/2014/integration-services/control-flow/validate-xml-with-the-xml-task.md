---
title: Проверка XML с использованием задачи "XML" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- XML validation
- XML, validating
ms.assetid: 224fc025-c21f-4d43-aa9d-5ffac337f9b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 633a269f53c85353c956b33bff8fd3af518dad56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654418"
---
# <a name="validate-xml-with-the-xml-task"></a><span data-ttu-id="28f99-102">Validate XML with the XML Task</span><span class="sxs-lookup"><span data-stu-id="28f99-102">Validate XML with the XML Task</span></span>
  <span data-ttu-id="28f99-103">Активировав в задаче XML свойство `ValidationDetails`, вы сможете получить подробные результаты проверки XML-документа.</span><span class="sxs-lookup"><span data-stu-id="28f99-103">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span>

 <span data-ttu-id="28f99-104">На следующем снимке экрана показано окно **редактора задачи XML** с необходимыми параметрами для проверки XML, позволяющими настроить вывод подробных сведений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="28f99-104">The following screen shot shows the **XML Task Editor** with the settings required for XML validation with rich error output.</span></span>

 <span data-ttu-id="28f99-105">![Свойства задачи "XML" в редакторе задач "XML"](../media/xmltaskproperties.jpg "Свойства задачи "XML" в редакторе задач "XML"")</span><span class="sxs-lookup"><span data-stu-id="28f99-105">![XML task properties in the XML Task Editor](../media/xmltaskproperties.jpg "XML task properties in the XML Task Editor")</span></span>

 <span data-ttu-id="28f99-106">До появления свойства `ValidationDetails` проверка XML в задачах XML возвращала информацию только о том, есть ошибка в документе или нет. Сведения о самих ошибках и их расположении были недоступны.</span><span class="sxs-lookup"><span data-stu-id="28f99-106">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="28f99-107">Теперь, если для свойства `ValidationDetails` задать значение True, выходной файл будет содержать подробные сведения обо всех ошибках, включая номера строк и позиции.</span><span class="sxs-lookup"><span data-stu-id="28f99-107">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="28f99-108">Эти сведения можно использовать для анализа, поиска и исправления ошибок в XML-документах.</span><span class="sxs-lookup"><span data-stu-id="28f99-108">You can use this information to understand, locate, and fix errors in XML documents.</span></span>

 <span data-ttu-id="28f99-109">Функция проверки XML легко масштабируется в соответствии с размером XML-документов и количеством ошибок.</span><span class="sxs-lookup"><span data-stu-id="28f99-109">The XML validation functionality scales easily for large XML documents and large numbers of errors.</span></span> <span data-ttu-id="28f99-110">Так как выходной файл имеет формат XML, можно запрашивать и анализировать содержащиеся в нем данные.</span><span class="sxs-lookup"><span data-stu-id="28f99-110">Since the output file itself is in XML format, you can query and analyze the output.</span></span> <span data-ttu-id="28f99-111">Например, если выходные данные содержат большое количество ошибок, их можно сгруппировать, используя запрос [!INCLUDE[tsql](../../../includes/tsql-md.md)] , как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="28f99-111">For example, if the output contains a large number of errors, you can group the errors by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, as described in this topic.</span></span>

> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="28f99-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) представил `ValidationDetails` свойство в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] пакете обновления 2 (SP2).</span><span class="sxs-lookup"><span data-stu-id="28f99-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="28f99-113">Свойство также доступно в [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] и в SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="28f99-113">The property is also available in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>

## <a name="sample-output-for-xml-thats-valid"></a><span data-ttu-id="28f99-114">Пример выходных данных в допустимом XML-файле</span><span class="sxs-lookup"><span data-stu-id="28f99-114">Sample output for XML that's valid</span></span>
 <span data-ttu-id="28f99-115">Ниже приведен пример допустимого выходного XML-файла с результатами проверки.</span><span class="sxs-lookup"><span data-stu-id="28f99-115">Here is a sample output file with validation results for a valid XML file.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>true</result>
        <errors>0</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:27:22.087</startTime>
        <endTime>2015-05-28T10:29:07.007</endTime>
        <xmlFile>d:\Temp\TestData.xml</xmlFile>
        <xsdFile>d:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages />
</root>
```

## <a name="sample-output-for-xml-thats-not-valid"></a><span data-ttu-id="28f99-116">Пример выходных данных в недопустимом XML-файле</span><span class="sxs-lookup"><span data-stu-id="28f99-116">Sample output for XML that's not valid</span></span>
 <span data-ttu-id="28f99-117">Ниже приведен пример выходного XML-файла с результатами проверки, который содержит небольшое количество ошибок.</span><span class="sxs-lookup"><span data-stu-id="28f99-117">Here is a sample output file with validation results for an XML file that contains a small number of errors.</span></span> <span data-ttu-id="28f99-118">Текст элементов\<error> скрыт для удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="28f99-118">The text of the \<error> elements has been wrapped for readability.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>false</result>
        <errors>2</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:45:09.538</startTime>
        <endTime>2015-05-28T10:45:09.558</endTime>
        <xmlFile>C:\Temp\TestData.xml</xmlFile>
        <xsdFile>C:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages>
        <error line="5" position="26">The 'ApplicantRole' element is invalid - The value 'wer3' is invalid
    according to its datatype 'ApplicantRoleType' - The Enumeration constraint failed.</error>
        <error line="16" position="28">The 'Phone' element is invalid - The value 'we3056666666' is invalid
     according to its datatype 'phone' - The Pattern constraint failed.</error>
    </messages>
</root>
```

## <a name="analyze-xml-validation-output-with-a-transact-sql-query"></a><span data-ttu-id="28f99-119">Анализ выходных данных проверки XML с помощью запроса Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28f99-119">Analyze XML validation output with a Transact-SQL query</span></span>
 <span data-ttu-id="28f99-120">Если результат проверки XML содержит большое количество ошибок, можно использовать запрос [!INCLUDE[tsql](../../../includes/tsql-md.md)] , чтобы загрузить выходные данные в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28f99-120">If the output of XML validation contains a large number of errors, you can use a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query to load the output in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="28f99-121">Затем можно проанализировать список ошибок, используя все возможности языка T-SQL, включая предложения WHERE, GROUP BY, ORDER BY, JOIN и т. д.</span><span class="sxs-lookup"><span data-stu-id="28f99-121">Then you can analyze the error list with all the capabilities of the T-SQL language including WHERE, GROUP BY, ORDER BY, JOIN, and so forth.</span></span>

```sql
DECLARE @xml XML;

SELECT @xml = XmlDoc   
FROM OPENROWSET (BULK N'C:\Temp\XMLValidation_2016-02-212T10-41-00.xml', SINGLE_BLOB) AS Tab(XmlDoc);

-- Query # 1, flat list of errors
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT * FROM rs;
-- WHERE error LIKE '%whatever_string%'

-- Query # 2, count of errors grouped by the error message
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT COALESCE(error,'Total # of errors:') AS [error], COUNT(*) AS [counter]
FROM rs
GROUP BY GROUPING SETS ((error), ())
ORDER BY 2 DESC, COALESCE(error, 'Z');

```

 <span data-ttu-id="28f99-122">Ниже приведен результат запроса к [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] из второго примера, показанного выше.</span><span class="sxs-lookup"><span data-stu-id="28f99-122">Here is the result in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] of the second sample query shown in the preceding text.</span></span>

 <span data-ttu-id="28f99-123">![Запрос для группировки ошибок XML в среде Management Studio](../media/queryforxmlerrors.jpg "Запрос для группировки ошибок XML в среде Management Studio")</span><span class="sxs-lookup"><span data-stu-id="28f99-123">![Query to group XML errors in Management Studio](../media/queryforxmlerrors.jpg "Query to group XML errors in Management Studio")</span></span>

## <a name="see-also"></a><span data-ttu-id="28f99-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="28f99-124">See Also</span></span>
 <span data-ttu-id="28f99-125">[XML Task](xml-task.md) [Редактор задачи xml задачи xml &#40;общие&#41;страницы](../xml-task-editor-general-page.md)</span><span class="sxs-lookup"><span data-stu-id="28f99-125">[XML Task](xml-task.md) [XML Task Editor &#40;General Page&#41;](../xml-task-editor-general-page.md)</span></span>


