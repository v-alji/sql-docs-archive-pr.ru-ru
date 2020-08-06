---
title: Столбцы, по умолчанию содержащие значение NULL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- columns [XML in SQL Server], null default value
ms.assetid: 9381c07f-6887-4a62-9730-32661f9aa87c
author: rothja
ms.author: jroth
ms.openlocfilehash: 92ea51101f73695be2075a1b41deb62ca021f496
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654948"
---
# <a name="columns-that-contain-a-null-value-by-default"></a><span data-ttu-id="63d62-102">Столбцы, по умолчанию содержащие значение NULL</span><span class="sxs-lookup"><span data-stu-id="63d62-102">Columns that Contain a Null Value By Default</span></span>
  <span data-ttu-id="63d62-103">По умолчанию значение NULL в столбце сопоставляется с отсутствием атрибута, узла или элемента.</span><span class="sxs-lookup"><span data-stu-id="63d62-103">By default, a null value in a column maps to the absence of the attribute, node, or element.</span></span> <span data-ttu-id="63d62-104">Это поведение, установленное по умолчанию, может быть изменено с помощью запроса к элементно-ориентированному документу XML с использованием директивы ELEMENTS и указания ключевого слова XSINIL для добавления элементов для значений NULL, как показано в следующем запросе:</span><span class="sxs-lookup"><span data-stu-id="63d62-104">This default behavior can be overwritten by requesting element-centric XML using the ELEMENTS directive and specifying XSINIL to request adding elements for NULL values, as shown in the following query:</span></span>  
  
```  
SELECT EmployeeID as "@EmpID",   
       FirstName  as "EmpName/First",   
       MiddleName as "EmpName/Middle",   
       LastName   as "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="63d62-105">Ниже показан результат.</span><span class="sxs-lookup"><span data-stu-id="63d62-105">The following shows the result.</span></span> <span data-ttu-id="63d62-106">Обратите внимание, что, если ключевое слово XSINIL не указано, элемент <`Middle`> будет отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="63d62-106">Note that if XSINIL is not specified, the <`Middle`> element will be absent.</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63d62-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="63d62-107">See Also</span></span>  
 [<span data-ttu-id="63d62-108">Использование режима PATH совместно с FOR XML</span><span class="sxs-lookup"><span data-stu-id="63d62-108">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
