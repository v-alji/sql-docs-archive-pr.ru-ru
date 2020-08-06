---
title: Процесс создания записей (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], record generation process
- node scopes [SQLXML]
- record subsets [SQLXML]
- scope [SQLXML]
- key ordering rules [SQLXML]
- record generation process for bulk loads [SQLXML]
- entering node scope [SQLXML]
- bulk load [SQLXML], record generation process
- leaving node scope [SQLXML]
- schema mapping [SQLXML]
ms.assetid: d8885bbe-6f15-4fb9-9684-ca7883cfe9ac
author: rothja
ms.author: jroth
ms.openlocfilehash: 5734776864aecbda7adaf0b9b16180b5ebd55ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728138"
---
# <a name="record-generation-process-sqlxml-40"></a><span data-ttu-id="ee2ea-102">Процесс создания записей (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ee2ea-102">Record Generation Process (SQLXML 4.0)</span></span>
  <span data-ttu-id="ee2ea-103">Массовая загрузка XML обрабатывает входные XML-данные и готовит записи для соответствующих таблиц в Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee2ea-103">XML Bulk Load processes the XML input data and prepares records for the appropriate tables in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ee2ea-104">Логика массовой загрузки XML определяет, когда формируется новая запись, какие значения дочерних элементов или атрибута копировать в поля записи, и когда запись завершена и готова к отправке в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для вставки.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-104">The logic in XML Bulk Load determines when to generate a new record, what child element or attribute values to copy into the fields of the record, and when the record is complete and ready to be sent to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="ee2ea-105">Массовая загрузка XML не загружает все входные XML-данные в память и не формирует полные наборы записей перед отправкой данных в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee2ea-105">XML Bulk Load does not load the entire XML input data into memory, and does not produce complete record sets before sending data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ee2ea-106">Это объясняется тем, что входные XML-данные могут быть большим документом, и загрузка всего документа в память может быть дорогостоящей.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-106">This is because XML input data can be a large document and loading the entire document in memory can be expensive.</span></span> <span data-ttu-id="ee2ea-107">Вместо этого массовая загрузка XML выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-107">Instead, XML Bulk Load does the following:</span></span>  
  
1.  <span data-ttu-id="ee2ea-108">Анализирует схему сопоставления и готовит необходимый план выполнения.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-108">Analyzes the mapping schema and prepares the necessary execution plan.</span></span>  
  
2.  <span data-ttu-id="ee2ea-109">Применяет план выполнения к данным во входном потоке.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-109">Applies the execution plan to the data in the input stream.</span></span>  
  
 <span data-ttu-id="ee2ea-110">В связи с такой последовательной обработкой важно представить входные XML-данные определенным образом.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-110">This sequential processing makes it important to provide the XML input data in a specific way.</span></span> <span data-ttu-id="ee2ea-111">Необходимо понимать, как массовая загрузка XML анализирует схему сопоставления и как происходит процесс создания записи.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-111">You must understand how XML Bulk Load analyzes the mapping schema and how the record generation process occurs.</span></span> <span data-ttu-id="ee2ea-112">Это поможет предоставить схему сопоставления для массовой загрузки XML, которая даст нужные результаты.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-112">With this understanding, you can provide a mapping schema to XML Bulk Load that produces the results you want.</span></span>  
  
 <span data-ttu-id="ee2ea-113">Массовая загрузка XML обрабатывает общие заметки схемы сопоставления, в том числе сопоставления столбцов и таблиц (указанных явно с помощью заметок или неявно через сопоставление по умолчанию) и связи соединений.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-113">XML Bulk Load handles common mapping schema annotations, including column and table mappings (specified explicitly by using annotations or implicitly through the default mapping), and join relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee2ea-114">Предполагается, что пользователь знаком со схемами сопоставления XSD и XDR с заметками.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-114">It is assumed that you are familiar with annotated XSD or XDR mapping schemas.</span></span> <span data-ttu-id="ee2ea-115">Дополнительные сведения о схемах см. в статьях [Знакомство с заметками XSD-схем &#40;sqlxml 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) или [схемой XDR с аннотацией &#40;не рекомендуется в SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ee2ea-115">For more information about schemas, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) or [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="ee2ea-116">Чтобы понять процесс создания записей, необходимо понимать следующие концепции.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-116">Understanding record generation requires understanding the following concepts:</span></span>  
  
-   <span data-ttu-id="ee2ea-117">Область узла</span><span class="sxs-lookup"><span data-stu-id="ee2ea-117">Scope of a node</span></span>  
  
-   <span data-ttu-id="ee2ea-118">Правило создания записей</span><span class="sxs-lookup"><span data-stu-id="ee2ea-118">Record Generation Rule</span></span>  
  
-   <span data-ttu-id="ee2ea-119">Подмножество записей и правило упорядочения ключа</span><span class="sxs-lookup"><span data-stu-id="ee2ea-119">Record subset and the Key Ordering Rule</span></span>  
  
-   <span data-ttu-id="ee2ea-120">Исключения из правила создания записей</span><span class="sxs-lookup"><span data-stu-id="ee2ea-120">Exceptions to the Record Generation Rule</span></span>  
  
## <a name="scope-of-a-node"></a><span data-ttu-id="ee2ea-121">Область узла</span><span class="sxs-lookup"><span data-stu-id="ee2ea-121">Scope of a Node</span></span>  
 <span data-ttu-id="ee2ea-122">Узел (элемент или атрибут) в XML-документе переходит *в область* , когда при выполнении XML-загрузки в поток входных данных XML возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-122">A node (an element or an attribute) in an XML document enters *into scope* when XML Bulk Load encounters it in the XML input data stream.</span></span> <span data-ttu-id="ee2ea-123">Для узла элемента открывающий тег элемента вводит элемент в область.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-123">For an element node, the start tag of the element brings the element in scope.</span></span> <span data-ttu-id="ee2ea-124">Для узла атрибута имя атрибута вводит атрибут в область.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-124">For an attribute node, the attribute name brings the attribute in scope.</span></span>  
  
 <span data-ttu-id="ee2ea-125">Узел выходит из области, когда в нем не остается данных: по закрывающему тегу (в случае узла элемента) или по окончанию значения атрибута (в случае узла атрибута).</span><span class="sxs-lookup"><span data-stu-id="ee2ea-125">A node leaves scope when there is no more data for it: either at the end tag (in the case of an element node) or at the end of an attribute value (in the case of an attribute node).</span></span>  
  
## <a name="record-generation-rule"></a><span data-ttu-id="ee2ea-126">Правило создания записей</span><span class="sxs-lookup"><span data-stu-id="ee2ea-126">Record Generation Rule</span></span>  
 <span data-ttu-id="ee2ea-127">Когда узел (элемент или атрибут) входит в область, появляется возможность формирования записи из этого узла.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-127">When a node (element or attribute) enters into scope, there is a potential for generating a record from that node.</span></span> <span data-ttu-id="ee2ea-128">Запись существует так же долго, как связанный узел в области.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-128">The record lives as long as the associated node is in scope.</span></span> <span data-ttu-id="ee2ea-129">Когда узел выходит из области, массовая загрузка XML рассматривает сформированную запись как завершенную (с данными) и отправляет ее в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для вставки.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-129">When the node goes out of scope, XML Bulk Load considers the generated record complete (with data) and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="ee2ea-130">Например, рассмотрим следующий фрагмент схемы XSD:</span><span class="sxs-lookup"><span data-stu-id="ee2ea-130">For example, consider the following XSD schema fragment:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Customers" >  
   <xsd:complexType>  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
     <xsd:attribute name="CompanyName" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="ee2ea-131">Схема задает **\<Customer>** элемент с атрибутами **CustomerID** и **CompanyName** .</span><span class="sxs-lookup"><span data-stu-id="ee2ea-131">The schema specifies a **\<Customer>** element with **CustomerID** and **CompanyName** attributes.</span></span> <span data-ttu-id="ee2ea-132">`sql:relation`Заметка сопоставляет **\<Customer>** элемент с таблицей Customers.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-132">The `sql:relation` annotation maps the **\<Customer>** element to the Customers table.</span></span>  
  
 <span data-ttu-id="ee2ea-133">Рассмотрим следующий фрагмент XML-документа:</span><span class="sxs-lookup"><span data-stu-id="ee2ea-133">Consider this fragment of an XML document:</span></span>  
  
```  
<Customer CustomerID="1" CompanyName="xyz" />  
<Customer CustomerID="2" CompanyName="abc" />  
...  
```  
  
 <span data-ttu-id="ee2ea-134">Когда массовой загрузке XML предоставляется схема, описанная в предыдущих абзацах, и XML-данные в качестве входных данных, она обрабатывает узлы (элементы и атрибуты) в источнике данных следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-134">When XML Bulk Load is provided with the schema described in the preceding paragraphs and XML data as input, it processes the nodes (elements and attributes) in the source data as follows:</span></span>  
  
-   <span data-ttu-id="ee2ea-135">Открывающий тег первого **\<Customer>** элемента приводит этот элемент в области.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-135">The start tag of the first **\<Customer>** element brings that element in scope.</span></span> <span data-ttu-id="ee2ea-136">Этот узел сопоставляется с таблицей Customers.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-136">This node maps to the Customers table.</span></span> <span data-ttu-id="ee2ea-137">Поэтому массовая загрузка XML формирует запись для таблицы Customers.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-137">Therefore, XML Bulk Load generates a record for the Customers table.</span></span>  
  
-   <span data-ttu-id="ee2ea-138">В схеме все атрибуты **\<Customer>** элемента сопоставляются со столбцами таблицы Customers.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-138">In the schema, all attributes of the **\<Customer>** element map to columns of the Customers table.</span></span> <span data-ttu-id="ee2ea-139">По мере входа этих атрибутов в область, массовая загрузка XML копирует их значения в запись клиента, уже сформированную родительской областью.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-139">As these attributes enter into scope, XML Bulk Load copies their values to the customer record that is already generated by the parent scope.</span></span>  
  
-   <span data-ttu-id="ee2ea-140">Когда при выполнении групповой загрузки XML достигается закрывающий тег **\<Customer>** элемента, элемент выходит за пределы области.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-140">When XML Bulk Load reaches the end tag for the **\<Customer>** element, the element goes out of scope.</span></span> <span data-ttu-id="ee2ea-141">В результате массовая загрузка XML рассматривает запись как завершенную и отправляет ее в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee2ea-141">This causes XML Bulk Load to consider the record complete and send it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ee2ea-142">При выполнении операции XML-загрузки для каждого последующего элемента следует выполнить этот процесс **\<Customer>** .</span><span class="sxs-lookup"><span data-stu-id="ee2ea-142">XML Bulk Load follows this process for each subsequent **\<Customer>** element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ee2ea-143">В этой модели, поскольку запись вставляется при достижении закрывающего тега (или выхода узла из области), необходимо определить все данные, связанные с записью в области узла.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-143">In this model, because a record is inserted when the end tag is reached (or the node is out of scope), you must define all of the data that is associated with the record within the scope of the node.</span></span>  
  
## <a name="record-subset-and-the-key-ordering-rule"></a><span data-ttu-id="ee2ea-144">Подмножество записей и правило упорядочения ключа</span><span class="sxs-lookup"><span data-stu-id="ee2ea-144">Record Subset and the Key Ordering Rule</span></span>  
 <span data-ttu-id="ee2ea-145">При указании схемы сопоставления, в которой используется заметка `<sql:relationship>`, термин «подмножество» относится к набору записей, сформированных на стороне внешнего ключа связи.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-145">When you specify a mapping schema that uses `<sql:relationship>`, the subset term refers to the set of records that is generated on the foreign side of the relationship.</span></span> <span data-ttu-id="ee2ea-146">В следующем примере записи таблицы CustOrder находятся на стороне внешнего ключа, `<sql:relationship>`.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-146">In the following example, the CustOrder records are on the foreign side, `<sql:relationship>`.</span></span>  
  
 <span data-ttu-id="ee2ea-147">Например, пусть база данных содержит следующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-147">For example, suppose a database contains the following tables:</span></span>  
  
-   <span data-ttu-id="ee2ea-148">Cust (CustomerID, CompanyName, City);</span><span class="sxs-lookup"><span data-stu-id="ee2ea-148">Cust (CustomerID, CompanyName, City)</span></span>  
  
-   <span data-ttu-id="ee2ea-149">CustOrder (CustomerID, OrderID).</span><span class="sxs-lookup"><span data-stu-id="ee2ea-149">CustOrder (CustomerID, OrderID)</span></span>  
  
 <span data-ttu-id="ee2ea-150">Столбец CustomerID в таблице CustOrder является внешним ключом, под которым понимается первичный ключ CustomerID в таблице Cust.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-150">The CustomerID in the CustOrder table is a foreign key that refers to the CustomerID primary key in the Cust table.</span></span>  
  
 <span data-ttu-id="ee2ea-151">Теперь рассмотрим представление XML, указанное в следующей схеме XSD с заметками.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-151">Now, consider the XML view as specified in the following annotated XSD schema.</span></span> <span data-ttu-id="ee2ea-152">В этой схеме используется заметка `<sql:relationship>`, чтобы указать связь между таблицами Cust и CustOrder.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-152">This schema uses `<sql:relationship>` to specify the relationship between the Cust and CustOrder tables.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="ee2ea-153">Ниже приведен образец XML-данных и шаги для создания рабочего образца.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-153">The sample XML data and the steps to create a working sample are given below.</span></span>  
  
-   <span data-ttu-id="ee2ea-154">Когда **\<Customer>** узел элемента в XML-файле данных входит в область, при выполнении операции XML-загрузки создается запись для таблицы Cust.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-154">When a **\<Customer>** element node in the XML data file enters into scope, XML Bulk Load generates a record for the Cust table.</span></span> <span data-ttu-id="ee2ea-155">При выполнении операции XML-загрузки выполняется копирование необходимых значений столбцов (CustomerID, CompanyName и City) из **\<CustomerID>** , **\<CompanyName>** и **\<City>** дочерних элементов, вводимых в область.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-155">XML Bulk Load then copies the necessary column values (CustomerID, CompanyName, and City) from the **\<CustomerID>**, **\<CompanyName>**, and the **\<City>** child elements as these elements enter into scope.</span></span>  
  
-   <span data-ttu-id="ee2ea-156">Когда **\<Order>** узел Element входит в область, при выполнении групповой загрузки XML создается запись для таблицы CustOrder.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-156">When an **\<Order>** element node enters into scope, XML Bulk Load generates a record for the CustOrder table.</span></span> <span data-ttu-id="ee2ea-157">При выполнении операции XML-загрузки в эту запись копируется значение атрибута **OrderID** .</span><span class="sxs-lookup"><span data-stu-id="ee2ea-157">XML Bulk Load copies the value of the **OrderID** attribute to this record.</span></span> <span data-ttu-id="ee2ea-158">Значение, необходимое для столбца CustomerID, получено из **\<CustomerID>** дочернего элемента **\<Customer>** элемента.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-158">The value required for the CustomerID column is obtained from the **\<CustomerID>** child element of the **\<Customer>** element.</span></span> <span data-ttu-id="ee2ea-159">При выполнении групповой загрузки XML данные, указанные в, используются `<sql:relationship>` для получения значения внешнего ключа CustomerID для этой записи, если только атрибут **CustomerID** не был указан в **\<Order>** элементе.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-159">XML Bulk Load uses the information that is specified in `<sql:relationship>` to obtain the CustomerID foreign key value for this record, unless the **CustomerID** attribute was specified in the **\<Order>** element.</span></span> <span data-ttu-id="ee2ea-160">Общее правило: если дочерний элемент явно указывает значение для атрибута внешнего ключа, то массовая загрузка XML использует это значение и не получает значение из родительского элемента с помощью указанной заметки `<sql:relationship>`.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-160">The general rule is that if the child element explicitly specifies a value for the foreign key attribute, XML Bulk Load uses that value and does not obtain the value from the parent element by using the specified `<sql:relationship>`.</span></span> <span data-ttu-id="ee2ea-161">Поскольку данный **\<Order>** узел элемента выходит за пределы области, при выполнении операции XML-загрузки происходит отправка записи в, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] а затем обработка всех последующих **\<Order>** узлов элементов аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-161">As this **\<Order>** element node goes out of scope, XML Bulk Load sends the record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then processes all the subsequent **\<Order>** element nodes in the same manner.</span></span>  
  
-   <span data-ttu-id="ee2ea-162">Наконец, **\<Customer>** узел Element выходит за пределы области.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-162">Finally, the **\<Customer>** element node goes out of scope.</span></span> <span data-ttu-id="ee2ea-163">В это время массовая загрузка XML отправляет запись клиента в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee2ea-163">At that time, XML Bulk Load sends the customer record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ee2ea-164">Массовая загрузка XML продолжает этот процесс для всех последующих клиентов в потоке XML-данных.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-164">XML Bulk Load follows this process for all the subsequent customers in the XML data stream.</span></span>  
  
 <span data-ttu-id="ee2ea-165">Два замечания о схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-165">Here are two observations about the mapping schema:</span></span>  
  
-   <span data-ttu-id="ee2ea-166">Если схема удовлетворяет правилу "вложенности" (например, все данные, связанные с клиентом и заказом, определяются в области связанных **\<Customer>** **\<Order>** узлов элементов и), то при выполнении такой загрузки происходит успешная операция.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-166">When the schema satisfies the "containment" rule (for example, all data that is associated with the customer and the order is defined within the scope of the associated **\<Customer>** and **\<Order>** element nodes), the bulk load succeeds.</span></span>  
  
-   <span data-ttu-id="ee2ea-167">В описании **\<Customer>** элемента его дочерние элементы указываются в соответствующем порядке.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-167">In describing the **\<Customer>** element, its child elements are specified in the appropriate order.</span></span> <span data-ttu-id="ee2ea-168">В этом случае **\<CustomerID>** дочерний элемент указывается перед **\<Order>** дочерним элементом.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-168">In this case, the **\<CustomerID>** child element is specified before the **\<Order>** child element.</span></span> <span data-ttu-id="ee2ea-169">Это означает, что во входном XML-файле данных **\<CustomerID>** значение элемента доступно как значение внешнего ключа, когда **\<Order>** элемент входит в область.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-169">This means that in the input XML data file, the **\<CustomerID>** element value is available as the foreign key value when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="ee2ea-170">Первыми указываются ключевые атрибуты — это «правило упорядочения ключа».</span><span class="sxs-lookup"><span data-stu-id="ee2ea-170">The key attributes are specified first; this is the "Key Ordering Rule."</span></span>  
  
     <span data-ttu-id="ee2ea-171">При указании **\<CustomerID>** дочернего элемента после **\<Order>** дочернего элемента значение недоступно, если **\<Order>** элемент входит в область.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-171">If you specify the **\<CustomerID>** child element after the **\<Order>** child element, the value is not available when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="ee2ea-172">После того как **\</Order>** закрывающий тег считывается, запись для таблицы CustOrder считается завершенной и вставляется в таблицу CustOrder со ЗНАЧЕНИЕМ NULL для столбца CustomerID, что не является нужным результатом.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-172">When the **\</Order>** end tag is then read, the record for CustOrder table is considered complete and is inserted in the CustOrder table with a NULL value for the CustomerID column, which is not the desired result.</span></span>  
  
#### <a name="to-create-a-working-sample"></a><span data-ttu-id="ee2ea-173">Создание рабочего образца</span><span class="sxs-lookup"><span data-stu-id="ee2ea-173">To create a working sample</span></span>  
  
1.  <span data-ttu-id="ee2ea-174">Сохраните схему, приведенную в этом примере, в файле SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-174">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="ee2ea-175">Создайте следующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-175">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                 OrderID        int         PRIMARY KEY,  
                 CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID))  
    GO  
    ```  
  
3.  <span data-ttu-id="ee2ea-176">Сохраните следующий образец входных XML-данных в файле SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="ee2ea-176">Save the following sample XML input data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>   
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
        <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="ee2ea-177">Чтобы выполнить массовую загрузку XML-данных, сохраните следующий пример на языке [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) в файле BulkLoad.vbs и выполните его.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-177">To execute XML Bulk Load, save and execute the following [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example (BulkLoad.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
## <a name="exceptions-to-the-record-generation-rule"></a><span data-ttu-id="ee2ea-178">Исключения из правила создания записей</span><span class="sxs-lookup"><span data-stu-id="ee2ea-178">Exceptions to the Record Generation Rule</span></span>  
 <span data-ttu-id="ee2ea-179">Массовая загрузка XML не формирует запись для узла, когда он входит в область, если этот узел типа IDREF или IDREFS.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-179">XML Bulk Load does not generate a record for a node when it enters into scope if that node is either an IDREF or IDREFS type.</span></span> <span data-ttu-id="ee2ea-180">Необходимо убедиться, что в схеме приведено полное описание записи.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-180">You must make sure that a complete description of the record occurs at some place in the schema.</span></span> <span data-ttu-id="ee2ea-181">Заметки `dt:type="nmtokens"` пропускаются так же, как пропускается тип IDREFS.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-181">The `dt:type="nmtokens"` annotations are ignored just as the IDREFS type is ignored.</span></span>  
  
 <span data-ttu-id="ee2ea-182">Например, рассмотрим следующую схему XSD, которая описывает **\<Customer>** элементы и **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="ee2ea-182">For example, consider the following XSD schema that describes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="ee2ea-183">**\<Customer>** Элемент включает атрибут **ORDERLIST** типа IDREFS.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-183">The **\<Customer>** element includes an **OrderList** attribute of the IDREFS type.</span></span> <span data-ttu-id="ee2ea-184">Тег `<sql:relationship>` задает связь «один ко многим» между заказчиком и списком заказов.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-184">The `<sql:relationship>` tag specifies the one-to-many relationship between the customer and list of orders.</span></span>  
  
 <span data-ttu-id="ee2ea-185">Схема:</span><span class="sxs-lookup"><span data-stu-id="ee2ea-185">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
                 parent="Cust"  
                 parent-key="CustomerID"  
                 child="CustOrder"  
                 child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="CompanyName" type="xsd:string" />  
    <xsd:attribute name="City" type="xsd:string" />  
    <xsd:attribute name="OrderList"   
                       type="xsd:IDREFS"   
                       sql:relation="CustOrder"   
                       sql:field="OrderID"  
                       sql:relationship="CustCustOrder" >  
    </xsd:attribute>  
  </xsd:complexType>  
 </xsd:element>  
  
  <xsd:element name="Order" sql:relation="CustOrder" >  
   <xsd:complexType>  
    <xsd:attribute name="OrderID" type="xsd:string" />  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="OrderDate" type="xsd:date" />  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="ee2ea-186">Так как при выполнении групповой загрузки игнорируются узлы типа IDREFS, при переходе узла атрибута **OrderList** в область не создается никаких операций создания записей.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-186">Because Bulk Load ignores the nodes of IDREFS type, there is no record generation when the **OrderList** attribute node enters into scope.</span></span> <span data-ttu-id="ee2ea-187">Поэтому, если нужно упорядочить записи, добавленные в таблицу Orders, необходимо описать эти заказы в каком-то месте схемы.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-187">Therefore, if you want the order records added to the Orders table, you must describe those orders somewhere in the schema.</span></span> <span data-ttu-id="ee2ea-188">В этой схеме указание **\<Order>** элемента гарантирует, что при выполнении операции XML-загрузки в таблицу Orders добавляются записи о заказах.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-188">In this schema, specifying the **\<Order>** element ensures that XML Bulk Load adds the order records to the Orders table.</span></span> <span data-ttu-id="ee2ea-189">**\<Order>** Элемент описывает все атрибуты, необходимые для заполнения записи для таблицы CustOrder.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-189">The **\<Order>** element describes all the attributes that are required to fill the record for the CustOrder table.</span></span>  
  
 <span data-ttu-id="ee2ea-190">Необходимо убедиться, что значения **CustomerID** и **OrderID** в **\<Customer>** элементе соответствуют значениям в **\<Order>** элементе.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-190">You must ensure that the **CustomerID** and **OrderID** values in the **\<Customer>** element match the values in the **\<Order>** element.</span></span> <span data-ttu-id="ee2ea-191">Программист ответственен за обеспечение ссылочной целостности.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-191">You are responsible for maintaining referential integrity.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="ee2ea-192">Проверка рабочего образца</span><span class="sxs-lookup"><span data-stu-id="ee2ea-192">To test a working sample</span></span>  
  
1.  <span data-ttu-id="ee2ea-193">Создайте следующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-193">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int          PRIMARY KEY,  
                  CompanyName    varchar(20)  NOT NULL,  
                  City           varchar(20)  DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID        varchar(10) PRIMARY KEY,  
                  CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID),  
                  OrderDate      datetime DEFAULT '2000-01-01')  
    GO  
    ```  
  
2.  <span data-ttu-id="ee2ea-194">Сохраните схему сопоставления, приведенную в этом примере, в файле SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-194">Save the mapping schema provided in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="ee2ea-195">Сохраните следующий образец XML-данных в файле SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-195">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1111" CompanyName="Sean Chai" City="NY"  
                 OrderList="Ord1 Ord2" />  
      <Customers CustomerID="1112" CompanyName="Dont Know" City="LA"  
                 OrderList="Ord3 Ord4" />  
      <Order OrderID="Ord1" CustomerID="1111" OrderDate="1999-01-01" />  
      <Order OrderID="Ord2" CustomerID="1111" OrderDate="1999-02-01" />  
      <Order OrderID="Ord3" CustomerID="1112" OrderDate="1999-03-01" />  
      <Order OrderID="Ord4" CustomerID="1112" OrderDate="1999-04-01" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="ee2ea-196">Чтобы выполнить массовую загрузку XML-данных, сохраните этот пример на языке VBScript в файле Sample.vbs и выполните его.</span><span class="sxs-lookup"><span data-stu-id="ee2ea-196">To execute XML Bulk Load, save and execute this VBScript example (SampleVB.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
