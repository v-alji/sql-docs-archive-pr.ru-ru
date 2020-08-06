---
title: Замена существующих столбцов на столбцы XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- tables [XML]
ms.assetid: 0d951424-9862-41fe-bd46-127f1c059bcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 32447851fcfe2a54143a028a94539532bba6708d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654957"
---
# <a name="change-existing-columns-to-xml-columns"></a><span data-ttu-id="f1b25-102">Замена существующих столбцов на XML-столбцы</span><span class="sxs-lookup"><span data-stu-id="f1b25-102">Change Existing Columns to XML Columns</span></span>
  <span data-ttu-id="f1b25-103">Инструкция ALTER TABLE поддерживает тип данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="f1b25-103">The ALTER TABLE statement supports the `xml` data type.</span></span> <span data-ttu-id="f1b25-104">Например, можно преобразовать столбец любого строкового типа в тип данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="f1b25-104">For example, you can alter any string type column to the `xml` data type.</span></span> <span data-ttu-id="f1b25-105">Учтите, что в этом случае документы, содержащиеся в этом столбце, должны быть корректными.</span><span class="sxs-lookup"><span data-stu-id="f1b25-105">Note that in these cases, the documents contained in the column must be well formed.</span></span> <span data-ttu-id="f1b25-106">Также при изменении типа столбца со строкового на типизированный xml, содержащиеся в столбце документы должны проходить проверку по указанным XSD-схемам.</span><span class="sxs-lookup"><span data-stu-id="f1b25-106">Also, if you are changing the type of the column from string to typed xml, the documents in the column are validated against the specified XSD schemas.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 nvarchar(max))  
GO  
INSERT INTO T   
VALUES (1, '<Root><Product ProductID="1"/></Root>')  
GO  
ALTER TABLE T   
ALTER COLUMN Col2 xml  
GO  
```  
  
 <span data-ttu-id="f1b25-107">Можно изменить тип содержащихся в столбце `xml` данных с нетипизированного на типизированный XML.</span><span class="sxs-lookup"><span data-stu-id="f1b25-107">You can change an `xml` type column from untyped XML to typed XML.</span></span> <span data-ttu-id="f1b25-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="f1b25-108">For example:</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T   
values (1, '<p1:ProductDescription ProductModelID="1"   
xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
            </p1:ProductDescription>')  
GO   
-- Make it a typed xml column by specifying a schema collection.  
ALTER TABLE T   
ALTER COLUMN Col2 xml (Production.ProductDescriptionSchemaCollection)  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f1b25-109">Cкрипт будет работать с базой данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , потому что коллекция XML-схем `Production.ProductDescriptionSchemaCollection`создана в виде части базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1b25-109">The script will run against [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, because the XML schema collection, `Production.ProductDescriptionSchemaCollection`, is created as part of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="f1b25-110">В предыдущем примере все сохраненные в столбце экземпляры проверяются на корректность и типизацию в соответствии с XSD-схемами из указанной коллекции.</span><span class="sxs-lookup"><span data-stu-id="f1b25-110">In the previous example, all the instances stored in the column are validated and typed against the XSD schemas in the specified collection.</span></span> <span data-ttu-id="f1b25-111">Если столбец содержит хотя бы один экземпляр XML, не проходящий проверку на соответствие указанной схеме, выполнение инструкции `ALTER TABLE` завершится ошибкой, и преобразование нетипизированного XML-столбца в типизированный будет невозможно.</span><span class="sxs-lookup"><span data-stu-id="f1b25-111">If the column contains one or more XML instances that are invalid with regard to the specified schema, the `ALTER TABLE` statement will fail and you will not be able to change your untyped XML column into typed XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1b25-112">Если таблица имеет большой размер, операция изменения столбца типа `xml` может требовать много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f1b25-112">If a table is large, modifying an `xml` type column can be costly.</span></span> <span data-ttu-id="f1b25-113">Причиной этого является необходимость проверки каждого документа на корректность, а для типизированного XML — также и проверки соответствия схеме.</span><span class="sxs-lookup"><span data-stu-id="f1b25-113">This is because each document must be checked for being well formed and, for typed XML, must also be validated.</span></span>  
  
 <span data-ttu-id="f1b25-114">Дополнительные сведения о типизированном XML см. в разделе [Сравнение типизированного и нетипизированного XML](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f1b25-114">For more information about typed XML, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
  
