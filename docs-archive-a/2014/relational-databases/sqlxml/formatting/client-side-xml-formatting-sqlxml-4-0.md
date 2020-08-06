---
title: Форматирование XML на стороне клиента (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- FOR XML clause, formatting
- middle tier XML formatting [SQLXML]
- client-side XML formatting
- client-side-xml attribute
ms.assetid: 9630a21d-a93b-4d3b-8a25-c4b32399f993
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4a680d79a25d24ebdf779b41fd3be5a5d6a605
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665928"
---
# <a name="client-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="5ff37-102">Форматирование XML на стороне клиента (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5ff37-102">Client-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="5ff37-103">В этом разделе содержатся сведения о форматировании XML на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="5ff37-103">This topic provides information about client-side XML formatting.</span></span> <span data-ttu-id="5ff37-104">Форматирование на стороне означает форматирование XML на среднем уровне.</span><span class="sxs-lookup"><span data-stu-id="5ff37-104">Client-side formatting refers to the formatting of XML on the middle tier.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ff37-105">В этом разделе содержатся дополнительные сведения об использовании предложения FOR XML на стороне клиента и предполагается предварительное знакомство с предложением FOR XML.</span><span class="sxs-lookup"><span data-stu-id="5ff37-105">This topic provides additional information about using the FOR XML clause on the client side, and assumes you are already familiar with the FOR XML clause.</span></span> <span data-ttu-id="5ff37-106">Дополнительные сведения о XML см. в разделе [Создание XML с помощью for XML](../../xml/for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5ff37-106">For more information about FOR XML, see [Constructing XML Using FOR XML](../../xml/for-xml-sql-server.md).</span></span>  
  
 <span data-ttu-id="5ff37-107">**Важно!** Чтобы использовать функциональность XML на стороне клиента с новым `xml` типом данных, клиенты всегда должны использовать [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщик данных Native Client (SQLNCLI11) вместо поставщика SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="5ff37-107">**Important** To use client-side FOR XML functionality with the new `xml` data type, clients should always use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) data provider instead of the SQLOLEDB provider.</span></span> <span data-ttu-id="5ff37-108">SQLNCLI11 является самой последней версией поставщика SQL Server, поддерживающей все типы данных, появившиеся в [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ff37-108">SQLNCLI11 is the latest version of the SQL Server provider and fully understands data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="5ff37-109">FOR XML на стороне клиента с поставщиком SQLOLEDB воспринимает типы данных `xml` как строки.</span><span class="sxs-lookup"><span data-stu-id="5ff37-109">The behavior for client side FOR XML with the SQLOLEDB provider will treat `xml` data types as strings.</span></span>  
  
## <a name="formatting-xml-documents-on-the-client-side"></a><span data-ttu-id="5ff37-110">Форматирование XML-документов на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="5ff37-110">Formatting XML Documents on the Client Side</span></span>  
 <span data-ttu-id="5ff37-111">Предположим, клиентское приложение выполняет следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="5ff37-111">When a client application executes the following query:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
FOR XML RAW  
```  
  
 <span data-ttu-id="5ff37-112">Только этот фрагмент запроса будет отправлен на сервер.</span><span class="sxs-lookup"><span data-stu-id="5ff37-112">...only this part of the query is sent to the server:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
```  
  
 <span data-ttu-id="5ff37-113">Сервер выполняет запрос и возвращает клиенту набор строк (который содержит FirstName и Ластнамеколумнс).</span><span class="sxs-lookup"><span data-stu-id="5ff37-113">The server executes the query and returns a rowset (which contains FirstName and LastNamecolumns) to the client.</span></span> <span data-ttu-id="5ff37-114">Затем средний уровень применяет к набору строк преобразование FOR XML и возвращает XML-форматирование клиенту.</span><span class="sxs-lookup"><span data-stu-id="5ff37-114">The middle tier then applies the FOR XML transformation to the rowset and returns XML formatting to the client.</span></span>  
  
 <span data-ttu-id="5ff37-115">Аналогичным образом, при выполнении запроса XPath сервер возвращает клиенту набор строк, а затем к набору строк на стороне клиента применяется преобразование FOR XML EXPLICIT, создавая нужное XML-форматирование.</span><span class="sxs-lookup"><span data-stu-id="5ff37-115">Similarly, when you execute an XPath query, the server returns the rowset to the client and the FOR XML EXPLICIT transformation is applied to the rowset on the client, generating the desired XML formatting.</span></span>  
  
 <span data-ttu-id="5ff37-116">В следующей таблице приведены режимы, которые могут быть заданы для FOR XML на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="5ff37-116">The following table shows the modes you can specify with client-side FOR XML.</span></span>  
  
|<span data-ttu-id="5ff37-117">Режим FOR XML на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="5ff37-117">Client-side FOR XML mode</span></span>|<span data-ttu-id="5ff37-118">Комментировать</span><span class="sxs-lookup"><span data-stu-id="5ff37-118">Comment</span></span>|  
|-------------------------------|-------------|  
|<span data-ttu-id="5ff37-119">RAW</span><span class="sxs-lookup"><span data-stu-id="5ff37-119">RAW</span></span>|<span data-ttu-id="5ff37-120">Выдает одинаковый результат при указании в FOR XML на стороне клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="5ff37-120">Produces identical results when specified in client-side or server-side FOR XML.</span></span>|  
|<span data-ttu-id="5ff37-121">NESTED</span><span class="sxs-lookup"><span data-stu-id="5ff37-121">NESTED</span></span>|<span data-ttu-id="5ff37-122">Похож на режим FOR XML AUTO на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="5ff37-122">Is similar to FOR XML AUTO mode on the server-side.</span></span>|  
|<span data-ttu-id="5ff37-123">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="5ff37-123">EXPLICIT</span></span>|<span data-ttu-id="5ff37-124">Похож на режим FOR XML EXPLICIT на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="5ff37-124">Is similar to server-side FOR XML EXPLICIT mode.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="5ff37-125">Если указать режим AUTO и запросить XML-форматирование на стороне клиента, то запрос будет целиком отправлен на сервер, то есть XML-форматирование будет выполняться на сервере.</span><span class="sxs-lookup"><span data-stu-id="5ff37-125">If you specify AUTO mode and request client-side XML formatting, the entire query is sent to the server; that is, XML formatting occurs on the server.</span></span> <span data-ttu-id="5ff37-126">Это сделано для удобства, но обратите внимание, что режим NESTED возвращает имена базовых таблиц в созданном в XML-документе как имена элементов.</span><span class="sxs-lookup"><span data-stu-id="5ff37-126">This is done for convenience, but note that the NESTED mode returns base table names as element names in the XML document that is generated.</span></span> <span data-ttu-id="5ff37-127">Для некоторых создаваемых пользователем приложений могут потребоваться имена базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="5ff37-127">Some of the applications you write might require base table names.</span></span> <span data-ttu-id="5ff37-128">Например, можно выполнить хранимую процедуру и загрузить результирующие данные в Dataset (на платформе [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework), а затем создать дельту для обновления данных в таблицах.</span><span class="sxs-lookup"><span data-stu-id="5ff37-128">For example, you might execute a stored procedure and load the resulting data in a Dataset (in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework), and then later generate a DiffGram to update data in the tables.</span></span> <span data-ttu-id="5ff37-129">В таком случае потребуются сведения о базовой таблице, и поэтому придется использовать режим NESTED.</span><span class="sxs-lookup"><span data-stu-id="5ff37-129">In such a case, you would need the base table information and you would have to use the NESTED mode.</span></span>  
  
## <a name="benefits-of-client-side-xml-formatting"></a><span data-ttu-id="5ff37-130">Преимущества форматирования XML-кода на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="5ff37-130">Benefits of Client-side XML formatting</span></span>  
 <span data-ttu-id="5ff37-131">Ниже приведены некоторые преимущества форматирования XML-кода на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="5ff37-131">The following are some benefits of formatting XML on the client.</span></span>  
  
### <a name="if-you-have-stored-procedures-on-the-server-that-return-a-single-rowset-you-can-request-client-side-for-xml-transformation-to-generate-an-xml"></a><span data-ttu-id="5ff37-132">При наличии на сервере хранимых процедур, которые возвращают единственный набор строк, можно для создания XML запросить преобразование FOR XML на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="5ff37-132">If you have stored procedures on the server that return a single rowset, you can request client-side FOR XML transformation to generate an XML.</span></span>  
 <span data-ttu-id="5ff37-133">Например, рассмотрим следующую хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="5ff37-133">For example, consider the following stored procedure.</span></span> <span data-ttu-id="5ff37-134">Она возвращает имена и фамилии сотрудников из таблицы Person.Contact в базе AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5ff37-134">This procedure returns the first and last names of employees from the Person.Contact table in the AdventureWorks database:</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects  
   WHERE name = 'GetContacts' AND type = 'P')  
   DROP PROCEDURE GetContacts  
GO  
CREATE PROCEDURE GetContacts  
AS  
    SELECT   FirstName, LastName  
    FROM     Person.Contact  
```  
  
 <span data-ttu-id="5ff37-135">Следующий образец XML-шаблона выполняет хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="5ff37-135">The following sample XML template executes the stored procedure.</span></span> <span data-ttu-id="5ff37-136">Предложение FOR XML указывается после имени хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="5ff37-136">The FOR XML clause is specified after the stored procedure name.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    EXEC GetContacts FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="5ff37-137">Поскольку атрибут **Client-Side-XML** имеет значение 1 (true) в шаблоне, хранимая процедура выполняется на сервере, а набор строк с двумя столбцами, возвращаемый сервером, преобразуется в XML на среднем уровне и возвращается клиенту.</span><span class="sxs-lookup"><span data-stu-id="5ff37-137">Because the **client-side-xml** attribute is set to 1 (true) in the template, the stored procedure is executed on the server and the two-column rowset that is returned by the server is transformed into XML on the middle tier and returned to the client.</span></span> <span data-ttu-id="5ff37-138">(здесь показан только фрагмент результата).</span><span class="sxs-lookup"><span data-stu-id="5ff37-138">(Only a partial result is shown here.)</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact FirstName="Catherine" LastName="Abel" />  
</ROOT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="5ff37-139">При использовании поставщика SQLXMLOLEDB или управляемых классов SQLXML можно при помощи свойства `ClientSideXml` задать форматирование XML на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="5ff37-139">When you are using the SQLXMLOLEDB Provider or SQLXML Managed Classes, you can use the `ClientSideXml` property to request client-side XML formatting.</span></span>  
  
### <a name="the-workload-is-more-balanced"></a><span data-ttu-id="5ff37-140">Рабочая нагрузка лучше сбалансирована</span><span class="sxs-lookup"><span data-stu-id="5ff37-140">The workload is more balanced.</span></span>  
 <span data-ttu-id="5ff37-141">Поскольку клиент выполняет XML-форматирование, рабочая нагрузка будет балансироваться между сервером и клиентом, высвобождая серверные ресурсы для выполнения других задач.</span><span class="sxs-lookup"><span data-stu-id="5ff37-141">Because the client does the XML formatting, the workload is balanced between the server and client, freeing the server to do other things.</span></span>  
  
## <a name="supporting-client-side-xml-formatting"></a><span data-ttu-id="5ff37-142">Поддержка форматирования XML-кода на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="5ff37-142">Supporting Client-side XML Formatting</span></span>  
 <span data-ttu-id="5ff37-143">Поддержку форматирования XML-кода на стороне клиента обеспечивают следующие компоненты SQLXML:</span><span class="sxs-lookup"><span data-stu-id="5ff37-143">To support the client-side XML formatting functionality, SQLXML provides:</span></span>  
  
-   <span data-ttu-id="5ff37-144">SQLXMLOLEDB, поставщик</span><span class="sxs-lookup"><span data-stu-id="5ff37-144">SQLXMLOLEDB Provider</span></span>  
  
-   <span data-ttu-id="5ff37-145">управляемые классы SQLXML</span><span class="sxs-lookup"><span data-stu-id="5ff37-145">SQLXML Managed Classes</span></span>  
  
-   <span data-ttu-id="5ff37-146">Улучшенная поддержка XML-шаблонов</span><span class="sxs-lookup"><span data-stu-id="5ff37-146">Enhanced XML template support</span></span>  
  
-   <span data-ttu-id="5ff37-147">SqlXmlCommand. Клиентсидексмл, свойство</span><span class="sxs-lookup"><span data-stu-id="5ff37-147">SqlXmlCommand.ClientSideXml property</span></span>  
  
     <span data-ttu-id="5ff37-148">Установив это свойство управляемых классов SQLXML в значение true, можно задать форматирование на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="5ff37-148">You can specify client-side formatting by setting this property of the SQLXML managed classes to true.</span></span>  
  
## <a name="enhanced-xml-template-support"></a><span data-ttu-id="5ff37-149">Улучшенная поддержка XML-шаблонов</span><span class="sxs-lookup"><span data-stu-id="5ff37-149">Enhanced XML Template Support</span></span>  
 <span data-ttu-id="5ff37-150">Начиная с версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] , XML-шаблон в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] был дополнен добавлением атрибута на **стороне клиента XML** .</span><span class="sxs-lookup"><span data-stu-id="5ff37-150">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the XML template in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been enhanced with the addition of the **client-side-xml** attribute.</span></span> <span data-ttu-id="5ff37-151">Если значение этого атрибута установлено в значение true, то XML-форматирование выполняется на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="5ff37-151">If this attribute is set to true, XML is formatted on the client.</span></span> <span data-ttu-id="5ff37-152">Обратите внимание, что этот атрибут шаблона идентичен свойству Клиентсидексмл, зависящему от поставщика SQLXMLOLEDB, в функциональных возможностях.</span><span class="sxs-lookup"><span data-stu-id="5ff37-152">Note that this template attribute is identical in functionality to the SQLXMLOLEDB Provider-specific ClientSideXML property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ff37-153">Если вы выполняете XML-шаблон в приложении ADO, использующем поставщик SQLXMLOLEDB, и задаете атрибут **Client-Side-XML** в шаблоне и свойстве клиентсидексмл поставщика, приоритет получает значение, заданное в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="5ff37-153">If you execute an XML template in an ADO application that is using the SQLXMLOLEDB Provider, and you specify both the **client-side-xml** attribute in the template and the provider ClientSideXML property, the value specified in the template takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff37-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ff37-154">See Also</span></span>  
 <span data-ttu-id="5ff37-155">[Архитектура форматирования XML на стороне клиента и на стороне сервера &#40;SQLXML 4,0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="5ff37-155">[Architecture of Client-side and Server-side XML Formatting &#40;SQLXML 4.0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="5ff37-156">[ДЛЯ SQL Server &#40;XML&#41;](../../xml/for-xml-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5ff37-156">[FOR XML &#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span></span>  
 <span data-ttu-id="5ff37-157">[Рекомендации по безопасности XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="5ff37-157">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="5ff37-158">[Поддержка типов данных XML в SQLXML 4,0](../xml-data-type-support-in-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="5ff37-158">[xml Data Type Support in SQLXML 4.0](../xml-data-type-support-in-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="5ff37-159">[Управляемые классы SQLXML](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="5ff37-159">[SQLXML Managed Classes](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 <span data-ttu-id="5ff37-160">[Клиентское и серверное форматирование XML &#40;SQLXML 4,0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="5ff37-160">[Client-side vs. Server-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="5ff37-161">[Объект SqlXmlCommand &#40;управляемые классы SQLXML&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span><span class="sxs-lookup"><span data-stu-id="5ff37-161">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span></span>  
 [<span data-ttu-id="5ff37-162">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5ff37-162">XML Data &#40;SQL Server&#41;</span></span>](../../xml/xml-data-sql-server.md)  
  
  
