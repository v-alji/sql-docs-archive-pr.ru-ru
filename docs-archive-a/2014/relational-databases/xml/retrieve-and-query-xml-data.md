---
title: Получение и запрос данных XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], retrieving
- XML instance retrieval
ms.assetid: 24a28760-1225-42b3-9c89-c9c0332d9c51
author: rothja
ms.author: jroth
ms.openlocfilehash: d387d1b96a57dcc7100368779f8ec6078fad5c7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730230"
---
# <a name="retrieve-and-query-xml-data"></a><span data-ttu-id="cdaca-102">Получение и запрос XML-данных</span><span class="sxs-lookup"><span data-stu-id="cdaca-102">Retrieve and Query XML Data</span></span>
  <span data-ttu-id="cdaca-103">В этом разделе описываются параметры запроса, которые необходимо указать для запроса XML-данных.</span><span class="sxs-lookup"><span data-stu-id="cdaca-103">This topic describes the query options that you have to specify to query XML data.</span></span> <span data-ttu-id="cdaca-104">Кроме того, в нем описаны компоненты экземпляров XML, нефиксируемых при сохранении экземпляров в базах данных.</span><span class="sxs-lookup"><span data-stu-id="cdaca-104">It also describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>  
  
##  <a name="features-of-an-xml-instance-that-are-not-preserved"></a><a name="features"></a> <span data-ttu-id="cdaca-105">Компоненты экземпляра XML, которые не сохраняются</span><span class="sxs-lookup"><span data-stu-id="cdaca-105">Features of an XML Instance That Are Not Preserved</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cdaca-106">сохраняется содержимое экземпляра XML, но не сохраняются его аспекты, которые в модели XML-данных не рассматриваются как значительные.</span><span class="sxs-lookup"><span data-stu-id="cdaca-106">preserves the content of the XML instance, but does not preserve aspects of the XML instance that are not considered to be significant in the XML data model.</span></span> <span data-ttu-id="cdaca-107">Это означает, что полученный экземпляр XML может отличаться от экземпляра, сохраненного на сервере, но при этом будет содержать те же самые данные.</span><span class="sxs-lookup"><span data-stu-id="cdaca-107">This means that a retrieved XML instance might not be identical to the instance that was stored in the server, but will contain the same information.</span></span>  
  
### <a name="xml-declaration"></a><span data-ttu-id="cdaca-108">XML-декларация</span><span class="sxs-lookup"><span data-stu-id="cdaca-108">XML Declaration</span></span>  
 <span data-ttu-id="cdaca-109">XML-декларация экземпляра не сохраняется при сохранении экземпляра в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cdaca-109">The XML declaration in an instance is not preserved when the instance is stored in the database.</span></span> <span data-ttu-id="cdaca-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="cdaca-110">For example:</span></span>  
  
```  
CREATE TABLE T1 (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T1 values (1, '<?xml version="1.0" encoding="windows-1252" ?><doc></doc>')  
GO  
SELECT Col2  
FROM T1  
```  
  
 <span data-ttu-id="cdaca-111">Результат `<doc/>`.</span><span class="sxs-lookup"><span data-stu-id="cdaca-111">The result is `<doc/>`.</span></span>  
  
 <span data-ttu-id="cdaca-112">XML-декларация, например `<?xml version='1.0'?>`, не сохраняется при сохранении XML-данных в экземпляре типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="cdaca-112">The XML declaration, such as `<?xml version='1.0'?>`, is not preserved when storing XML data in an `xml` data type instance.</span></span> <span data-ttu-id="cdaca-113">Это сделано намеренно.</span><span class="sxs-lookup"><span data-stu-id="cdaca-113">This is by design.</span></span> <span data-ttu-id="cdaca-114">После преобразования данных в тип XML-декларация () и его атрибуты (версия/кодировка/автономные) теряются `xml` .</span><span class="sxs-lookup"><span data-stu-id="cdaca-114">The XML declaration () and its attributes (version/encoding/stand-alone) are lost after data is converted to type `xml`.</span></span> <span data-ttu-id="cdaca-115">XML-декларация обрабатывается как директива для синтаксического анализатора XML.</span><span class="sxs-lookup"><span data-stu-id="cdaca-115">The XML declaration is treated as a directive to the XML parser.</span></span> <span data-ttu-id="cdaca-116">Все данные XML внутренне хранятся в кодировке UCS-2.</span><span class="sxs-lookup"><span data-stu-id="cdaca-116">The XML data is stored internally as ucs-2.</span></span> <span data-ttu-id="cdaca-117">Все другие инструкции по обработке (PI) в экземпляре XML сохраняются.</span><span class="sxs-lookup"><span data-stu-id="cdaca-117">All other PIs in the XML instance are preserved.</span></span>  
  
  
### <a name="order-of-attributes"></a><span data-ttu-id="cdaca-118">Порядок атрибутов</span><span class="sxs-lookup"><span data-stu-id="cdaca-118">Order of Attributes</span></span>  
 <span data-ttu-id="cdaca-119">Порядок атрибутов экземпляра XML не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="cdaca-119">The order of attributes in an XML instance is not preserved.</span></span> <span data-ttu-id="cdaca-120">При запросе экземпляра XML, хранящегося в столбце типа `xml`, порядок атрибутов в результирующем XML может отличаться от порядка в исходном экземпляре XML.</span><span class="sxs-lookup"><span data-stu-id="cdaca-120">When you query the XML instance stored in the `xml` type column, the order of attributes in the resulting XML may be different from the original XML instance.</span></span>  
  
  
### <a name="quotation-marks-around-attribute-values"></a><span data-ttu-id="cdaca-121">Кавычки вокруг значений атрибутов</span><span class="sxs-lookup"><span data-stu-id="cdaca-121">Quotation Marks Around Attribute Values</span></span>  
 <span data-ttu-id="cdaca-122">Одинарные и двойные кавычки вокруг значений атрибутов не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="cdaca-122">Single quotation marks and double quotations marks around attribute values are not preserved.</span></span> <span data-ttu-id="cdaca-123">Значения атрибутов хранятся в базе данных в виде пар имени и значения.</span><span class="sxs-lookup"><span data-stu-id="cdaca-123">The attribute values are stored in the database as a name and value pair.</span></span> <span data-ttu-id="cdaca-124">Кавычки не хранятся.</span><span class="sxs-lookup"><span data-stu-id="cdaca-124">The quotation marks are not stored.</span></span> <span data-ttu-id="cdaca-125">При выполнении запроса XQuery к экземпляру XML результирующий XML сериализуется с использованием двойных кавычек вокруг значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="cdaca-125">When an XQuery is executed against an XML instance, the resulting XML is serialized with double quotation marks around the attribute values.</span></span>  
  
```  
DECLARE @x xml  
-- Use double quotation marks.  
SET @x = '<root a="1" />'  
SELECT @x  
GO  
DECLARE @x xml  
-- Use single quotation marks.  
SET @x = '<root a=''1'' />'  
SELECT @x  
GO  
```  
  
 <span data-ttu-id="cdaca-126">Оба запроса вернут `<root a="1" />`.</span><span class="sxs-lookup"><span data-stu-id="cdaca-126">Both queries return = `<root a="1" />`.</span></span>  
  
  
### <a name="namespace-prefixes"></a><span data-ttu-id="cdaca-127">Префиксы пространства имен</span><span class="sxs-lookup"><span data-stu-id="cdaca-127">Namespace Prefixes</span></span>  
 <span data-ttu-id="cdaca-128">Префиксы пространств имен не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="cdaca-128">Namespace prefixes are not preserved.</span></span> <span data-ttu-id="cdaca-129">При выполнении запроса XQuery к столбцу типа `xml` для сериализации результирующего XML могут использоваться другие префиксы пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cdaca-129">When you specify XQuery against an `xml` type column, the serialized XML result may return different namespace prefixes.</span></span>  
  
```  
DECLARE @x xml  
SET @x = '<ns1:root xmlns:ns1="abc" xmlns:ns2="abc">  
            <ns2:SomeElement/>  
          </ns1:root>'  
SELECT @x  
SELECT @x.query('/*')  
GO  
```  
  
 <span data-ttu-id="cdaca-130">Префикс пространства имен в результате может быть другим.</span><span class="sxs-lookup"><span data-stu-id="cdaca-130">The namespace prefix in the result may be different.</span></span> <span data-ttu-id="cdaca-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="cdaca-131">For example:</span></span>  
  
```  
<p1:root xmlns:p1="abc"><p1:SomeElement/></p1:root>  
```  
  
  
##  <a name="setting-required-query-options"></a><a name="query"></a> <span data-ttu-id="cdaca-132">Задание обязательных параметров запроса</span><span class="sxs-lookup"><span data-stu-id="cdaca-132">Setting Required Query Options</span></span>  
 <span data-ttu-id="cdaca-133">При запросе `xml` столбцов или переменных типа с помощью `xml` методов типа данных необходимо задать следующие параметры, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="cdaca-133">When querying `xml` type columns or variables using `xml` data type methods, the following options must be set as shown.</span></span>  
  
|<span data-ttu-id="cdaca-134">Параметры SET</span><span class="sxs-lookup"><span data-stu-id="cdaca-134">SET Options</span></span>|<span data-ttu-id="cdaca-135">Необходимые значения</span><span class="sxs-lookup"><span data-stu-id="cdaca-135">Required Values</span></span>|  
|-----------------|---------------------|  
|<span data-ttu-id="cdaca-136">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="cdaca-136">ANSI_NULLS</span></span>|<span data-ttu-id="cdaca-137">ON</span><span class="sxs-lookup"><span data-stu-id="cdaca-137">ON</span></span>|  
|<span data-ttu-id="cdaca-138">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="cdaca-138">ANSI_PADDING</span></span>|<span data-ttu-id="cdaca-139">ON</span><span class="sxs-lookup"><span data-stu-id="cdaca-139">ON</span></span>|  
|<span data-ttu-id="cdaca-140">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="cdaca-140">ANSI_WARNINGS</span></span>|<span data-ttu-id="cdaca-141">ON</span><span class="sxs-lookup"><span data-stu-id="cdaca-141">ON</span></span>|  
|<span data-ttu-id="cdaca-142">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="cdaca-142">ARITHABORT</span></span>|<span data-ttu-id="cdaca-143">ON</span><span class="sxs-lookup"><span data-stu-id="cdaca-143">ON</span></span>|  
|<span data-ttu-id="cdaca-144">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="cdaca-144">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="cdaca-145">ON</span><span class="sxs-lookup"><span data-stu-id="cdaca-145">ON</span></span>|  
|<span data-ttu-id="cdaca-146">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="cdaca-146">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="cdaca-147">OFF</span><span class="sxs-lookup"><span data-stu-id="cdaca-147">OFF</span></span>|  
|<span data-ttu-id="cdaca-148">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="cdaca-148">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="cdaca-149">ON</span><span class="sxs-lookup"><span data-stu-id="cdaca-149">ON</span></span>|  
  
 <span data-ttu-id="cdaca-150">Если параметры не заданы так, как показано, запросы и изменения `xml` методов типа данных завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cdaca-150">If the options are not set as shown, queries and modifications on `xml` data type methods will fail.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="cdaca-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="cdaca-151">See Also</span></span>  
 [<span data-ttu-id="cdaca-152">Создание экземпляров данных XML</span><span class="sxs-lookup"><span data-stu-id="cdaca-152">Create Instances of XML Data</span></span>](create-instances-of-xml-data.md)  
  
  
