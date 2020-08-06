---
title: Рекомендации по безопасности XML (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- client-side XML formatting
- FOR XML clause, security
- server-side XML formatting
- AUTO mode
- security [SQLXML], FOR XML
ms.assetid: facba279-df93-475b-ad43-0043dc5bae03
author: rothja
ms.author: jroth
ms.openlocfilehash: 9a64fa61848e4b5435b2aa944c53953a8c083ab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666997"
---
# <a name="for-xml-security-considerations-sqlxml-40"></a><span data-ttu-id="f7bd4-102">Вопросы безопасности FOR XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f7bd4-102">FOR XML Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="f7bd4-103">Режим FOR XML AUTO создает иерархию XML, в которой имена элементов совпадают с именами таблиц, а имена атрибутов — с именами столбцов.</span><span class="sxs-lookup"><span data-stu-id="f7bd4-103">The FOR XML AUTO mode generates an XML hierarchy in which element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="f7bd4-104">Он предоставляет сведения о таблицах и столбцах базы данных.</span><span class="sxs-lookup"><span data-stu-id="f7bd4-104">This exposes the database table and column information.</span></span> <span data-ttu-id="f7bd4-105">При использовании режима AUTO (форматирование на стороне сервера) сведения о базе данных можно скрыть, указав в запросе псевдонимы таблиц и столбцов.</span><span class="sxs-lookup"><span data-stu-id="f7bd4-105">You can hide the database information when you use AUTO mode (server-side formatting) by specifying table and column aliases in the query.</span></span> <span data-ttu-id="f7bd4-106">Эти псевдонимы возвращаются в результирующем XML-документе в виде имен элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f7bd4-106">These aliases are returned in the resulting XML document as element and attribute names.</span></span>  
  
 <span data-ttu-id="f7bd4-107">Например, следующий запрос указывает режим AUTO. Таким образом, на сервере выполняется форматирование XML-кода.</span><span class="sxs-lookup"><span data-stu-id="f7bd4-107">For example, the following query specifies AUTO mode; therefore, the XML formatting is done on the server:</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="f7bd4-108">В результирующем XML-документе псевдонимы используются для имен элементов и атрибутов:</span><span class="sxs-lookup"><span data-stu-id="f7bd4-108">In the resulting XML document, the aliases are used for element and attribute names:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <C F="Nancy" L="Fuller" />   
  <CE F="Andrew" L="Peacock" />   
  <C F="Janet" L="Leverling" />   
  ...  
</root>  
```  
  
 <span data-ttu-id="f7bd4-109">При использовании режима NESTED (форматирование на стороне клиента) псевдонимы возвращаются только для атрибутов в результирующем XML-документе.</span><span class="sxs-lookup"><span data-stu-id="f7bd4-109">When you use NESTED mode (client-side formatting), aliases are returned only for attributes in the resulting XML document.</span></span> <span data-ttu-id="f7bd4-110">Имена базовых таблиц всегда возвращаются в виде имен элементов.</span><span class="sxs-lookup"><span data-stu-id="f7bd4-110">The names of the base tables are always returned as element names.</span></span> <span data-ttu-id="f7bd4-111">Например, следующий запрос указывает режим NESTED.</span><span class="sxs-lookup"><span data-stu-id="f7bd4-111">For example, the following query specifies NESTED mode.</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="f7bd4-112">В результирующем XML-документе имена базовых таблиц, возвращаемые в виде имен элементов и псевдонимов таблиц, не используются:</span><span class="sxs-lookup"><span data-stu-id="f7bd4-112">In the resulting XML document, the names of the base tables are returned as element names and table aliases are not used:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Person.Contact F="Nancy" L="Fuller" />   
  <Person.Contact F="Andrew" L="Peacock" />   
  <Person.Contact F="Janet" L="Leverling" />   
       ...  
</root>  
```  
  
  
