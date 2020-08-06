---
title: Указание явных функций преобразования в запросах XPath (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit conversion functions [SQLXML]
- string function
- number function
- XPath queries [SQLXML], explicit conversion functions
ms.assetid: 1111cb5d-2bd9-4bdb-8de2-dc0e47452dd6
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b4b9bd5f5665c8cb86cb74c1397e2bd06e113fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654996"
---
# <a name="specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="863cc-102">Определение явных функций преобразования в запросах XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="863cc-102">Specifying Explicit Conversion Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="863cc-103">Следующие примеры показывают, как явные функции преобразования указываются в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="863cc-103">The following examples show how explicit conversion functions are specified in XPath queries.</span></span> <span data-ttu-id="863cc-104">В данных примерах запросы XPath определены в соответствии со схемой сопоставления, которая содержится в файле SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="863cc-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="863cc-105">Дополнительные сведения об этом образце схемы см. в разделе [Пример схемы XSD с заметками для XPath-примеров &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="863cc-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="863cc-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="863cc-106">Examples</span></span>  
  
### <a name="a-use-the-number-explicit-conversion-function"></a><span data-ttu-id="863cc-107">A.</span><span class="sxs-lookup"><span data-stu-id="863cc-107">A.</span></span> <span data-ttu-id="863cc-108">Используйте функцию явного преобразования number()</span><span class="sxs-lookup"><span data-stu-id="863cc-108">Use the number() explicit conversion function</span></span>  
 <span data-ttu-id="863cc-109">Функция `number()` преобразует аргумент в число.</span><span class="sxs-lookup"><span data-stu-id="863cc-109">The `number()` function converts an argument to a number.</span></span>  
  
 <span data-ttu-id="863cc-110">Если значение параметра **ContactID** не является числовым, следующий запрос преобразует идентификатор **ContactID** в число и сравнивает его со значением 4.</span><span class="sxs-lookup"><span data-stu-id="863cc-110">Assuming the value of **ContactID** is nonnumeric, the following query converts **ContactID** to a number and compares it with the value 4.</span></span> <span data-ttu-id="863cc-111">Затем запрос возвращает все **\<Employee>** дочерние элементы узла контекста с атрибутом **ContactID** , имеющим числовое значение 4:</span><span class="sxs-lookup"><span data-stu-id="863cc-111">The query then returns all **\<Employee>** element children of the context node with the **ContactID** attribute that has a numeric value of 4:</span></span>  
  
```  
/child::Contact[number(attribute::ContactID)= 4]  
```  
  
 <span data-ttu-id="863cc-112">Может быть задано сокращенное обозначение оси `attribute` (@), а поскольку ось `child` является осью по умолчанию, в запросе ее можно опустить.</span><span class="sxs-lookup"><span data-stu-id="863cc-112">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[number(@ContactID) = 4]  
```  
  
 <span data-ttu-id="863cc-113">В реляционных терминах запрос возвращает сотрудника с параметром **ContactID** , равным 4.</span><span class="sxs-lookup"><span data-stu-id="863cc-113">In relational terms, the query returns an employee with a **ContactID** of 4.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="863cc-114">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="863cc-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="863cc-115">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="863cc-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="863cc-116">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="863cc-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="863cc-117">Создайте следующий шаблон (ExplicitConversionA.xml) и сохраните его в каталоге, в котором сохранен файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="863cc-117">Create the following template (ExplicitConversionA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact[number(@ContactID)=4]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="863cc-118">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="863cc-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="863cc-119">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="863cc-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="863cc-120">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="863cc-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="863cc-121">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="863cc-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="863cc-122">Результирующий набор для выполнения этого шаблона:</span><span class="sxs-lookup"><span data-stu-id="863cc-122">The result set for this template execution is:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
### <a name="b-use-the-string-explicit-conversion-function"></a><span data-ttu-id="863cc-123">Б.</span><span class="sxs-lookup"><span data-stu-id="863cc-123">B.</span></span> <span data-ttu-id="863cc-124">Используйте функцию явного преобразования string()</span><span class="sxs-lookup"><span data-stu-id="863cc-124">Use the string() explicit conversion function</span></span>  
 <span data-ttu-id="863cc-125">Функция `string()` преобразует аргумент в строку.</span><span class="sxs-lookup"><span data-stu-id="863cc-125">The `string()` function converts an argument to a string.</span></span>  
  
 <span data-ttu-id="863cc-126">Следующий запрос преобразует **ContactID** в строку и сравнивает его со строковым значением "4".</span><span class="sxs-lookup"><span data-stu-id="863cc-126">The following query converts **ContactID** to a string and compares it with the string value "4".</span></span> <span data-ttu-id="863cc-127">Запрос возвращает все **\<Employee>** дочерние элементы узла контекста с параметром **ContactID** со строковым значением "4":</span><span class="sxs-lookup"><span data-stu-id="863cc-127">The query returns all **\<Employee>** element children of the context node with a **ContactID** with a string value of "4":</span></span>  
  
```  
/child::Contact[string(attribute::ContactID)="4"]  
```  
  
 <span data-ttu-id="863cc-128">Может быть задано сокращенное обозначение оси `attribute` (@), а поскольку ось `child` является осью по умолчанию, в запросе ее можно опустить.</span><span class="sxs-lookup"><span data-stu-id="863cc-128">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[string(@ContactID)="4"]  
```  
  
 <span data-ttu-id="863cc-129">С функциональной точки зрения этот запрос возвращает те же результаты, что и предыдущий пример запроса, хотя выполняется сопоставление со строковым значением, а не числовым значением (то есть числом 4).</span><span class="sxs-lookup"><span data-stu-id="863cc-129">Functionally, this query returns the same results as the previous example query, though the evaluation is done against a string value and not the numeric value (that is, the number 4).</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="863cc-130">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="863cc-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="863cc-131">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="863cc-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="863cc-132">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="863cc-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="863cc-133">Создайте следующий шаблон (ExplicitConversionB.xml) и сохраните его в каталоге, в котором сохранен файл SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="863cc-133">Create the following template (ExplicitConversionB.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Contact[string(@ContactID)="4"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="863cc-134">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="863cc-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="863cc-135">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="863cc-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="863cc-136">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="863cc-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="863cc-137">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="863cc-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="863cc-138">Далее приведен результирующий набор, полученный в результате выполнения этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="863cc-138">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
  
