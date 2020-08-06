---
title: Пример Указание директив ID и IDREFS | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- IDREFS directive
- ID directive
ms.assetid: 99b9f0d8-ecbb-4225-859f-881066c09785
author: rothja
ms.author: jroth
ms.openlocfilehash: c21ba1bd19691014f179801421322970a3dd6dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667610"
---
# <a name="example-specifying-the-id-and-idrefs-directives"></a><span data-ttu-id="38b8b-102">Пример Указание директив ID и IDREFS</span><span class="sxs-lookup"><span data-stu-id="38b8b-102">Example: Specifying the ID and IDREFS Directives</span></span>
  <span data-ttu-id="38b8b-103">Атрибут элемента может быть указан в качестве атрибута с типом `ID`, а атрибут `IDREFS` может быть использован для ссылки на него.</span><span class="sxs-lookup"><span data-stu-id="38b8b-103">An element attribute can be specified as an `ID` type attribute, and the `IDREFS` attribute can then be used to refer to it.</span></span> <span data-ttu-id="38b8b-104">Этим включаются связи внутри документа, которые похожи на связи первичного и внешнего ключей в реляционных базах данных.</span><span class="sxs-lookup"><span data-stu-id="38b8b-104">This enables intra-document links and is similar to the primary key and foreign key relationships in relational databases.</span></span>  
  
 <span data-ttu-id="38b8b-105">Этот пример иллюстрирует, как директивы `ID` и `IDREFS` могут быть использованы для создания атрибутов с типами `ID` и `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="38b8b-105">This example illustrates how the `ID` and `IDREFS` directives can be used to create attributes of `ID` and `IDREFS` types.</span></span> <span data-ttu-id="38b8b-106">Так как идентификаторы не могут быть целочисленными, значения ID в этом примере преобразуются.</span><span class="sxs-lookup"><span data-stu-id="38b8b-106">Because IDs cannot be integer values, the ID values in this example are converted.</span></span> <span data-ttu-id="38b8b-107">Другими словами, они подвергаются приведению типа.</span><span class="sxs-lookup"><span data-stu-id="38b8b-107">In other words, they are type casted.</span></span> <span data-ttu-id="38b8b-108">Префиксы используются для значений ID.</span><span class="sxs-lookup"><span data-stu-id="38b8b-108">Prefixes are used for the ID values.</span></span>  
  
 <span data-ttu-id="38b8b-109">Предположим, что требуется создать следующий XML:</span><span class="sxs-lookup"><span data-stu-id="38b8b-109">Assume that you want to construct XML as shown in the following:</span></span>  
  
```  
<Customer CustomerID="C1" SalesOrderIDList=" O11 O22 O33..." >  
    <SalesOrder SalesOrderID="O11" OrderDate="..." />  
    <SalesOrder SalesOrderID="O22" OrderDate="..." />  
    <SalesOrder SalesOrderID="O33" OrderDate="..." />  
    ...  
</Customer>  
```  
  
 <span data-ttu-id="38b8b-110">Атрибут `SalesOrderIDList` элемента < `Customer` > является многозначным атрибутом, который ссылается на атрибут `SalesOrderID` элемента < `SalesOrder` >.</span><span class="sxs-lookup"><span data-stu-id="38b8b-110">The `SalesOrderIDList` attribute of the < `Customer` > element is a multivalued attribute that refers to the `SalesOrderID` attribute of the < `SalesOrder` > element.</span></span> <span data-ttu-id="38b8b-111">Для установления этой связи атрибут `SalesOrderID` должен быть объявлен с типом `ID`, а атрибут `SalesOrderIDList` элемента < `Customer`> должен быть объявлен с типом `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="38b8b-111">To establish this link, the `SalesOrderID` attribute must be declared of `ID` type, and the `SalesOrderIDList` attribute of the < `Customer`> element must be declared of `IDREFS` type.</span></span> <span data-ttu-id="38b8b-112">Так как заказчик может оставить несколько заказов, используется тип `IDREFS` .</span><span class="sxs-lookup"><span data-stu-id="38b8b-112">Because a customer can request several orders, the `IDREFS` type is used.</span></span>  
  
 <span data-ttu-id="38b8b-113">Элементы типа `IDREFS` также имеют более одного значения.</span><span class="sxs-lookup"><span data-stu-id="38b8b-113">Elements of `IDREFS` type also have more than one value.</span></span> <span data-ttu-id="38b8b-114">Поэтому следует использовать отдельные предложения выборки, которые будут повторно использовать одни и те же сведения столбцов тега, родителя и ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="38b8b-114">Therefore, you have to use a separate select clause that will reuse the same tag, parent, and key column information.</span></span> <span data-ttu-id="38b8b-115">Предложение `ORDER BY` обеспечивает отображение последовательностей строк, определяющих значения `IDREFS`, сгруппированных по родительскому элементу.</span><span class="sxs-lookup"><span data-stu-id="38b8b-115">The `ORDER BY` then has to ensure that the sequence of rows that make up the `IDREFS` values appears grouped together under their parent element.</span></span>  
  
 <span data-ttu-id="38b8b-116">Далее запрос, который создает желаемый XML.</span><span class="sxs-lookup"><span data-stu-id="38b8b-116">This is the query that produces the XML you want.</span></span> <span data-ttu-id="38b8b-117">В запросе используются директивы `ID` и `IDREFS` для перезаписи типов в именах столбцов (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span><span class="sxs-lookup"><span data-stu-id="38b8b-117">The query uses the `ID` and `IDREFS` directives to overwrite the types in the column names (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID       [Customer!1!CustomerID],  
        NULL               [Customer!1!SalesOrderIDList!IDREFS],  
        NULL               [SalesOrder!2!SalesOrderID!ID],  
        NULL               [SalesOrder!2!OrderDate]  
FROM   Sales.Customer C   
UNION ALL   
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID,  
        'O-'+CAST(SalesOrderID as varchar(10)),   
        NULL,  
        NULL  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
        C.CustomerID,  
        NULL,  
        'O-'+CAST(SalesOrderID as varchar(10)),  
        OrderDate  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerIDORDER BY [Customer!1!CustomerID] ,  
         [SalesOrder!2!SalesOrderID!ID],  
         [Customer!1!SalesOrderIDList!IDREFS]  
FOR XML EXPLICIT;  
```  
  
## <a name="see-also"></a><span data-ttu-id="38b8b-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="38b8b-118">See Also</span></span>  
 [<span data-ttu-id="38b8b-119">Использование режима EXPLICIT с предложением FOR XML</span><span class="sxs-lookup"><span data-stu-id="38b8b-119">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
