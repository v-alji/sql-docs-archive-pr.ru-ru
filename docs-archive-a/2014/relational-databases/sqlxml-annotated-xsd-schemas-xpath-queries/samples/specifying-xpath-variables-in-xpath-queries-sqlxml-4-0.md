---
title: Указание переменных XPath в запросах XPath (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], XPath variables
- XPath variables [SQLXML]
ms.assetid: c11ab816-11b8-4131-8b77-c03fe500fa10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5045831f627722f7dbb9a9189be5c48d830f2add
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654989"
---
# <a name="specifying-xpath-variables-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="86767-102">Указание переменных XPath в запросах XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="86767-102">Specifying XPath Variables in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="86767-103">В следующих примерах показано, как передаются переменные в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="86767-103">The following examples show how XPath variables are passed in XPath queries.</span></span> <span data-ttu-id="86767-104">В данных примерах запросы XPath определены в соответствии со схемой сопоставления, которая содержится в файле SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="86767-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="86767-105">Дополнительные сведения об этом образце схемы см. в разделе [Пример схемы XSD с заметками для XPath-примеров &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="86767-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="86767-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="86767-106">Examples</span></span>  
  
### <a name="a-use-the-xpath-variables"></a><span data-ttu-id="86767-107">A.</span><span class="sxs-lookup"><span data-stu-id="86767-107">A.</span></span> <span data-ttu-id="86767-108">Использование переменных XPath</span><span class="sxs-lookup"><span data-stu-id="86767-108">Use the XPath variables</span></span>  
 <span data-ttu-id="86767-109">Образец шаблона содержит два запроса XPath.</span><span class="sxs-lookup"><span data-stu-id="86767-109">A sample template consists of two XPath queries.</span></span> <span data-ttu-id="86767-110">Каждый из запросов принимает один параметр.</span><span class="sxs-lookup"><span data-stu-id="86767-110">Each of the XPath queries takes one parameter.</span></span> <span data-ttu-id="86767-111">Шаблон также задает для этих параметров значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="86767-111">The template also specifies default values for these parameters.</span></span> <span data-ttu-id="86767-112">Они используются, если значения не заданы.</span><span class="sxs-lookup"><span data-stu-id="86767-112">The default values are used if parameter values are not specified.</span></span> <span data-ttu-id="86767-113">Два параметра со значениями по умолчанию задаются в **\<sql:header>** .</span><span class="sxs-lookup"><span data-stu-id="86767-113">Two parameters with default values are specified in **\<sql:header>**.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='CustomerID'>1</sql:param>  
     <sql:param name='ContactID'>1</sql:param>   
  </sql:header>  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
    Customer[@CustomerID=$CustomerID]   
  </sql:xpath-query >  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
   Contact[@ContactID=$ContactID]   
  </sql:xpath-query>  
</ROOT>  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="86767-114">Проверка запроса XPath к схеме сопоставления</span><span class="sxs-lookup"><span data-stu-id="86767-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="86767-115">Скопируйте [пример кода схемы](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="86767-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="86767-116">Сохраните файл с именем SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="86767-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="86767-117">Создайте следующий шаблон (XPathVariables.xml) и сохраните его в каталоге, где</span><span class="sxs-lookup"><span data-stu-id="86767-117">Create the following template (XPathVariables.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:header>  
         <sql:param name='CustomerID'>1</sql:param>  
         <sql:param name='ContactID'>1</sql:param>   
      </sql:header>  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[@CustomerID=$CustomerID]   
      </sql:xpath-query >  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
       Contact[@ContactID=$ContactID]   
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="86767-118">Путь к каталогу схемы сопоставления (файл SampleSchema1.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="86767-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="86767-119">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="86767-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="86767-120">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="86767-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="86767-121">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="86767-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86767-122">В данном примере никакие параметры не передаются.</span><span class="sxs-lookup"><span data-stu-id="86767-122">In this example, no parameters are passed.</span></span> <span data-ttu-id="86767-123">Поэтому используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="86767-123">Therefore, the default parameter values are used.</span></span>  
  
  
