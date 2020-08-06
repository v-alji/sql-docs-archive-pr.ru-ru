---
title: Определение метасвойств в инструкции OPENXML | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- overflow in XML document [SQL Server]
- metaproperties [XML in SQL Server]
- unconsumed data
- extracting information of XML nodes [SQL Server]
- OPENXML statement, metaproperties
ms.assetid: 29bfd1c6-3f9a-43c4-924a-53d438e442f4
author: rothja
ms.author: jroth
ms.openlocfilehash: c52d1162aa495deff8a0fde314fdcde0735d9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735142"
---
# <a name="specify-metaproperties-in-openxml"></a><span data-ttu-id="dcd3f-102">Определение метасвойств в инструкции OPENXML</span><span class="sxs-lookup"><span data-stu-id="dcd3f-102">Specify Metaproperties in OPENXML</span></span>
  <span data-ttu-id="dcd3f-103">Атрибутами метасвойств в документе XML называются атрибуты, описывающие свойства сущностей XML, например элементов, атрибутов и других узлов DOM.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-103">Metaproperty attributes in an XML document are attributes that describe the properties of an XML item, such as element, attribute, or any other DOM node.</span></span> <span data-ttu-id="dcd3f-104">Физически эти атрибуты отсутствуют в тексте документа XML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-104">These attributes do not physically exist in the XML document text.</span></span> <span data-ttu-id="dcd3f-105">Тем не менее инструкция OPENXML предоставляет эти метасвойства для всех сущностей XML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-105">However, OPENXML provides these metaproperties for all the XML items.</span></span> <span data-ttu-id="dcd3f-106">Эти метасвойства позволяют извлекать сведения, например данные о локальном положении и пространстве имен, об узлах XML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-106">These metaproperties allow you to extract information, such as local positioning and namespace information, of XML nodes.</span></span> <span data-ttu-id="dcd3f-107">Эти сведения предоставляют более подробные данные, чем текстовое представление.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-107">This information provides you with more details than are apparent in the textual representation.</span></span>  
  
 <span data-ttu-id="dcd3f-108">Метасвойства можно сопоставить со столбцами набора строк инструкции OPENXML при помощи параметра *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="dcd3f-108">You can map these metaproperties to the rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span> <span data-ttu-id="dcd3f-109">Столбцы будут содержать значения метасвойств, с которыми они связаны.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-109">The columns will contain the values of the metaproperties to which they are mapped.</span></span> <span data-ttu-id="dcd3f-110">Дополнительные сведения о синтаксисе инструкции OPENXML см. в разделе [OPENXML (Transact-SQL)](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcd3f-110">For more information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span>  
  
 <span data-ttu-id="dcd3f-111">Для доступа к атрибутам метасвойств предоставлено характерное для сервера SQL Server пространство имен.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-111">To access the metaproperty attributes, a namespace that is specific to SQL Server is provided.</span></span> <span data-ttu-id="dcd3f-112">Это пространство имен, **urn:schemas-microsoft-com:xml-metaprop** , позволяет пользователям обращаться к атрибутам метасвойств.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-112">This namespace, **urn:schemas-microsoft-com:xml-metaprop** allows the user to access the metaproperty attributes.</span></span> <span data-ttu-id="dcd3f-113">Инструкция OPENXML может возвращать результат запроса в виде таблицы, которая содержит столбец для каждого атрибута метасвойств, кроме метасвойства **xmltext** .</span><span class="sxs-lookup"><span data-stu-id="dcd3f-113">If the result of an OPENXML query is returned in an edge table format, the edge table contains one column for each metaproperty attribute, except the **xmltext** metaproperty.</span></span>  
  
 <span data-ttu-id="dcd3f-114">Некоторые атрибуты метасвойств используются в целях обработки.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-114">Some of the metaproperty attributes are used for processing purposes.</span></span> <span data-ttu-id="dcd3f-115">Например, атрибут метасвойства **xmltext** применяется для управления переполнением.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-115">For example, the **xmltext** metaproperty attribute is used for overflow handling.</span></span> <span data-ttu-id="dcd3f-116">Управление переполнением подразумевает обработку невостребованных, необработанных данных документа.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-116">Overflow handling refers to the unconsumed, unprocessed data in the document.</span></span> <span data-ttu-id="dcd3f-117">Один столбец набора строк, сформированного инструкцией OPENXML, можно назначить столбцом переполнения.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-117">One of the columns in the rowset that is generated by OPENXML can be identified as the overflow column.</span></span> <span data-ttu-id="dcd3f-118">Для этого необходимо связать его с метасвойством **xmltext** при помощи параметра *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="dcd3f-118">You do this by mapping it to the **xmltext** metaproperty by using the *ColPattern* parameter.</span></span> <span data-ttu-id="dcd3f-119">После этого в столбец будут копироваться данные переполнения.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-119">The column then receives the overflow data.</span></span> <span data-ttu-id="dcd3f-120">Параметр *flags* определяет, какие данные содержит столбец: все или только невостребованные.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-120">The *flags* parameter determines whether the column contains everything or only the unconsumed data.</span></span>  
  
 <span data-ttu-id="dcd3f-121">В следующей таблице перечислены атрибуты метасвойств, которыми обладают все анализируемые элементы XML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-121">The following table lists the metaproperty attributes that each parsed XML element possesses.</span></span> <span data-ttu-id="dcd3f-122">К атрибутам метасвойств можно обращаться при помощи пространства имен **urn:schemas-microsoft-com:xml-metaprop**.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-122">These metaproperty attributes can be accessed by using the namespace **urn:schemas-microsoft-com:xml-metaprop**.</span></span> <span data-ttu-id="dcd3f-123">Значение, заданное непосредственно в документе XML с помощью метасвойств, игнорируется.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-123">Any value that the user sets directly in the XML document by using these metaproperties is ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcd3f-124">На метасвойства нельзя ссылаться при перемещении по XML с помощью XPath.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-124">You cannot reference these metaproperties in any XPath navigation.</span></span>  
  
|<span data-ttu-id="dcd3f-125">Атрибут метасвойства</span><span class="sxs-lookup"><span data-stu-id="dcd3f-125">Metaproperty attribute</span></span>|<span data-ttu-id="dcd3f-126">Описание</span><span class="sxs-lookup"><span data-stu-id="dcd3f-126">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="dcd3f-127">**\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-127">**\@mp:id**</span></span>|<span data-ttu-id="dcd3f-128">Формируемый системой идентификатор узла DOM, действующий в пределах документа.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-128">Provides a system-generated, document-wide identifier of the DOM node.</span></span> <span data-ttu-id="dcd3f-129">Если документ не подлежит повторному синтаксическому анализу, этот идентификатор ссылается на тот же узел XML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-129">As long as the document is not reparsed, this ID refers to the same XML node.</span></span><br /><br /> <span data-ttu-id="dcd3f-130">Идентификатор XML, равный **0** , обозначает корневой элемент.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-130">An XML ID of **0** indicates that the element is a root element.</span></span> <span data-ttu-id="dcd3f-131">У такого узла идентификатор XML родительского элемента равен значению NULL.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-131">Its parent XML ID is NULL.</span></span>|  
|<span data-ttu-id="dcd3f-132">**\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-132">**\@mp:localname**</span></span>|<span data-ttu-id="dcd3f-133">Локальная часть имени узла.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-133">Stores the local part of the name of the node.</span></span> <span data-ttu-id="dcd3f-134">Применяется вместе с префиксом и URI пространства имен для обозначения элементов и узлов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-134">It is used with a prefix and a namespace URI to name element or attribute nodes.</span></span>|  
|<span data-ttu-id="dcd3f-135">**\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-135">**\@mp:namespaceuri**</span></span>|<span data-ttu-id="dcd3f-136">URI пространства имен текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-136">Provides the namespace URI of the current element.</span></span> <span data-ttu-id="dcd3f-137">Если значение атрибута равно NULL, пространство имен не существует.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-137">If the value of this attribute is NULL, no namespace is present</span></span>|  
|<span data-ttu-id="dcd3f-138">**\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-138">**\@mp:prefix**</span></span>|<span data-ttu-id="dcd3f-139">Префикс пространства имен текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-139">Stores the namespace prefix of the current element name.</span></span><br /><br /> <span data-ttu-id="dcd3f-140">Если префикс отсутствует (равен значению NULL), а URI задан, значит, указанное пространство имен используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-140">If no prefix is present (NULL) and a URI is given, it indicates that the specified namespace is the default namespace.</span></span> <span data-ttu-id="dcd3f-141">Если URI не задан, пространство имен не присоединяется.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-141">If no URI is given, no namespace is attached.</span></span>|  
|<span data-ttu-id="dcd3f-142">**\@mp:prev**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-142">**\@mp:prev**</span></span>|<span data-ttu-id="dcd3f-143">Предыдущий элемент того же уровня.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-143">Stores the previous sibling relative to a node.</span></span> <span data-ttu-id="dcd3f-144">Благодаря этому можно получить сведения о порядке элементов документа.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-144">This provides information about the ordering of elements in the document.</span></span><br /><br /> <span data-ttu-id="dcd3f-145">Атрибут **\@mp:prev** содержит идентификатор XML предыдущего соседнего элемента с тем же родительским элементом.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-145">**\@mp:prev** contains the XML ID of the previous sibling that has the same parent element.</span></span> <span data-ttu-id="dcd3f-146">У первого элемента в списке соседних узлов атрибут **\@mp:prev** равен значению NULL.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-146">If an element is at the front of the sibling list, **\@mp:prev** is NULL.</span></span>|  
|<span data-ttu-id="dcd3f-147">**\@mp:xmltext**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-147">**\@mp:xmltext**</span></span>|<span data-ttu-id="dcd3f-148">Применяется для обработки.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-148">Used for processing purposes.</span></span> <span data-ttu-id="dcd3f-149">Текстовая сериализация элемента, его атрибутов и подэлементов, которая используется при управлении переполнением в инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-149">It is the textual serialization of the element and its attributes, and also the subelements, as used in the overflow handling of OPENXML.</span></span>|  
  
 <span data-ttu-id="dcd3f-150">В следующей таблице перечислены дополнительные родительские свойства, которые позволяют получить сведения об иерархии.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-150">This table shows the additional parent properties that are provided and which allow you to retrieve information about the hierarchy.</span></span>  
  
|<span data-ttu-id="dcd3f-151">Родительский атрибут метасвойства</span><span class="sxs-lookup"><span data-stu-id="dcd3f-151">Parent metaproperty attribute</span></span>|<span data-ttu-id="dcd3f-152">Описание</span><span class="sxs-lookup"><span data-stu-id="dcd3f-152">Description</span></span>|  
|-----------------------------------|-----------------|  
|<span data-ttu-id="dcd3f-153">**\@mp:parentid**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-153">**\@mp:parentid**</span></span>|<span data-ttu-id="dcd3f-154">Соответствует **../\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-154">Corresponds to **../\@mp:id**</span></span>|  
|<span data-ttu-id="dcd3f-155">**\@mp:parentlocalname**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-155">**\@mp:parentlocalname**</span></span>|<span data-ttu-id="dcd3f-156">Соответствует **../\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-156">Corresponds to **../\@mp:localname**</span></span>|  
|<span data-ttu-id="dcd3f-157">**\@mp:parentnamespacerui**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-157">**\@mp:parentnamespacerui**</span></span>|<span data-ttu-id="dcd3f-158">Соответствует **../\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-158">Corresponds to **../\@mp:namespaceuri**</span></span>|  
|<span data-ttu-id="dcd3f-159">**\@mp:parentprefix**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-159">**\@mp:parentprefix**</span></span>|<span data-ttu-id="dcd3f-160">Соответствует **../\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="dcd3f-160">Corresponds to **../\@mp:prefix**</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="dcd3f-161">Примеры</span><span class="sxs-lookup"><span data-stu-id="dcd3f-161">Examples</span></span>  
 <span data-ttu-id="dcd3f-162">Следующие примеры демонстрируют, как при помощи инструкции OPENXML создать различные представления наборов строк.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-162">The following examples illustrate how OPENXML is used to create different rowset views.</span></span>  
  
### <a name="a-mapping-the-openxml-rowset-columns-to-the-metaproperties"></a><span data-ttu-id="dcd3f-163">A.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-163">A.</span></span> <span data-ttu-id="dcd3f-164">Сопоставление столбцов набора строк OPENXML с метасвойствами</span><span class="sxs-lookup"><span data-stu-id="dcd3f-164">Mapping the OPENXML rowset columns to the metaproperties</span></span>  
 <span data-ttu-id="dcd3f-165">В этом примере инструкция OPENXML применяется для создания представления набора строк учебного документа XML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-165">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="dcd3f-166">В частности, пример демонстрирует, как различные атрибуты метасвойств можно связать со столбцами набора строк инструкции OPENXML при помощи параметра *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="dcd3f-166">Specifically, it shows how the various metaproperty attributes can be mapped to rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="dcd3f-167">Инструкция OPENXML иллюстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="dcd3f-167">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="dcd3f-168">Столбец **id** привязан к атрибуту метасвойства **\@mp:id**, который указывает, что столбец содержит сформированный системой уникальный идентификатор XML элемента.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-168">The **id** column is mapped to the **\@mp:id** metaproperty attribute and indicates that the column contains the system-generated unique XML ID of the element.</span></span>  
  
-   <span data-ttu-id="dcd3f-169">Столбец **parent** привязан к атрибуту **\@mp:parentid**, который указывает, что столбец содержит идентификатор XML родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-169">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent of the element.</span></span>  
  
-   <span data-ttu-id="dcd3f-170">Столбец **parentLocalName** привязан к атрибуту **\@mp:parentlocalname**, который указывает, что столбец содержит локальное имя родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-170">The **parentLocalName** column is mapped to **\@mp:parentlocalname** and indicates that the column contains the local name of the parent.</span></span>  
  
 <span data-ttu-id="dcd3f-171">Инструкция SELECT возвращает набор строк, предоставленных OPENXML:</span><span class="sxs-lookup"><span data-stu-id="dcd3f-171">The SELECT statement then returns the rowset that is provided by OPENXML:</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- Sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (id int '@mp:id',   
            oid char(5),   
            date datetime,   
            amount real,   
            parentIDNo int '@mp:parentid',   
            parentLocalName varchar(40) '@mp:parentlocalname')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="dcd3f-172">Результат:</span><span class="sxs-lookup"><span data-stu-id="dcd3f-172">This is the result:</span></span>  
  
```  
id   oid         date                amount    parentIDNo  parentLocalName    
--- ------- ---------------------- ---------- ------------ ---------------  
6    O1    1996-01-20 00:00:00.000     3.5         2        Customer  
10   O2    1997-04-30 00:00:00.000     13.4        2        Customer  
19   O3    1999-07-14 00:00:00.000     100.0       15       Customer  
25   O4    1996-01-20 00:00:00.000     10000.0     15       Customer  
```  
  
### <a name="b-retrieving-the-whole-xml-document"></a><span data-ttu-id="dcd3f-173">Б.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-173">B.</span></span> <span data-ttu-id="dcd3f-174">Получение всего XML-документа</span><span class="sxs-lookup"><span data-stu-id="dcd3f-174">Retrieving the whole XML document</span></span>  
 <span data-ttu-id="dcd3f-175">В этом примере инструкция OPENXML применяется для создания представления набора строк из одного столбца учебного XML-документа.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-175">In this example, OPENXML is used to create a one-column rowset view of the sample XML document.</span></span> <span data-ttu-id="dcd3f-176">Этот столбец ( **Col1**) связан с метасвойством **xmltext** и является столбцом переполнения.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-176">This column, **Col1**, is mapped to the **xmltext** metaproperty and becomes an overflow column.</span></span> <span data-ttu-id="dcd3f-177">В результате столбец получает невостребованные данные.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-177">As a result, the column receives the unconsumed data.</span></span> <span data-ttu-id="dcd3f-178">В нашем случае этими данными является весь документ.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-178">In this case, it is the whole document.</span></span>  
  
 <span data-ttu-id="dcd3f-179">Затем инструкция SELECT возвращает полный набор строк.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-179">The SELECT statement then returns the complete rowset.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
SET @doc = N'<?xml version="1.0"?>  
<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
     <MyTag>Testing to see if all the subelements are returned</MyTag>  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/')  
   WITH (Col1 ntext '@mp:xmltext')  
```  
  
 <span data-ttu-id="dcd3f-180">Чтобы получить весь документ без объявления XML, запрос можно указать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dcd3f-180">To retrieve the whole document without the XML declaration, the query can be specified as shown in the following:</span></span>  
  
```  
SELECT *  
FROM OPENXML (@idoc, '/root')  
   WITH (Col1 ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="dcd3f-181">Запрос возвращает корневой элемент, имеющий имя, и данные, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-181">The query returns the root element that has the name root and the data that is contained by the root element</span></span>  
  
### <a name="c-specifying-the-xmltext-metaproperty-to-retrieve-the-unconsumed-data-in-a-column"></a><span data-ttu-id="dcd3f-182">В.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-182">C.</span></span> <span data-ttu-id="dcd3f-183">Определение метасвойства xmltext для получения невостребованных данных в столбце</span><span class="sxs-lookup"><span data-stu-id="dcd3f-183">Specifying the xmltext metaproperty to retrieve the unconsumed data in a column</span></span>  
 <span data-ttu-id="dcd3f-184">В этом примере инструкция OPENXML применяется для создания представления набора строк учебного документа XML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-184">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="dcd3f-185">Пример демонстрирует, как получить невостребованные данные XML, связав атрибут метасвойства **xmltext** со столбцом набора строк в OPENXML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-185">The example shows how to retrieve unconsumed XML data by mapping the **xmltext** metaproperty attribute to a rowset column in OPENXML.</span></span>  
  
 <span data-ttu-id="dcd3f-186">Столбец **comment** указан в качестве столбца переполнения путем привязки к метасвойству **\@mp:xmltext**.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-186">The **comment** column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span> <span data-ttu-id="dcd3f-187">Для параметра *flags* установлено значение **9** (XML_ATTRIBUTE and XML_NOCOPY).</span><span class="sxs-lookup"><span data-stu-id="dcd3f-187">The *flags* parameter is set to **9** (XML_ATTRIBUTE and XML_NOCOPY).</span></span> <span data-ttu-id="dcd3f-188">Оно соответствует **атрибутивному** сопоставлению и указывает, что в столбец переполнения необходимо скопировать только невостребованные данные.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-188">This indicates **attribute-centric** mapping and indicates that only the unconsumed data should be copied to the overflow column.</span></span>  
  
 <span data-ttu-id="dcd3f-189">Затем инструкция SELECT возвращает набор строк, предоставленных OPENXML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-189">The SELECT statement then returns the rowset provided by OPENXML.</span></span>  
  
 <span data-ttu-id="dcd3f-190">В этом примере метасвойство **\@mp:parentlocalname** задано для столбца **ParentLocalName** в наборе строк, созданном инструкцией OPENXML.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-190">In this example, the **\@mp:parentlocalname** metaproperty is set for a column, **ParentLocalName**, in the rowset generated by OPENXML.</span></span> <span data-ttu-id="dcd3f-191">В результате этот столбец содержит локальное имя родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-191">As a result, this column contains the local name of the parent element.</span></span>  
  
 <span data-ttu-id="dcd3f-192">Кроме него, набор строк содержит два столбца: **parent** и **comment**.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-192">Two additional columns are specified in the rowset, **parent** and **comment**.</span></span> <span data-ttu-id="dcd3f-193">Столбец **parent** привязан к атрибуту **\@mp:parentid**, который указывает, что столбец содержит идентификатор XML родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-193">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent element of the element.</span></span> <span data-ttu-id="dcd3f-194">Столбец comment указан в качестве столбца переполнения путем привязки к метасвойству **\@mp:xmltext**.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-194">The comment column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>  
'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (oid char(5),   
            date datetime,  
            comment ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="dcd3f-195">Результат.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-195">This is the result.</span></span> <span data-ttu-id="dcd3f-196">Поскольку столбцы идентификаторов объектов и столбцы даты уже востребованы, они отсутствуют в столбце переполнения.</span><span class="sxs-lookup"><span data-stu-id="dcd3f-196">Because the oid columns and date columns are already consumed, they do not appear in the overflow column.</span></span>  
  
```  
oid   date                        comment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
----- --------------------------- ----------------------------------------  
O1    1996-01-20 00:00:00.000     <Order amount="3.5"/>  
O2    1997-04-30 00:00:00.000     <Order amount="13.4">Customer was very   
                                   satisfied</Order>  
O3    1999-07-14 00:00:00.000     <Order amount="100" note="Wrap it blue   
                                   white red"><Urgency>   
                                   Important</Urgency></Order>  
O4    1996-01-20 00:00:00.000     <Order amount="10000"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcd3f-197">См. также:</span><span class="sxs-lookup"><span data-stu-id="dcd3f-197">See Also</span></span>  
 <span data-ttu-id="dcd3f-198">[OPENXML (Transact-SQL)](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcd3f-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="dcd3f-199">OPENXML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dcd3f-199">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
