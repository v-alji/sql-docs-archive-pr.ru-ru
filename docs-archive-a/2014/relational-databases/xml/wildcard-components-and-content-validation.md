---
title: Компоненты-шаблоны и проверка достоверности содержимого | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- wildcard components [XML]
- content validation [XML]
ms.assetid: ffa7d974-3645-446c-8425-f0b22b6b060a
author: rothja
ms.author: jroth
ms.openlocfilehash: 76ff2b48efb8cff0b98827fe8522405682c294e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656265"
---
# <a name="wildcard-components-and-content-validation"></a><span data-ttu-id="dd571-102">Компоненты-шаблоны и проверка достоверности содержимого</span><span class="sxs-lookup"><span data-stu-id="dd571-102">Wildcard Components and Content Validation</span></span>
  <span data-ttu-id="dd571-103">Компоненты-шаблоны используются для увеличения гибкости в том, в чем это разрешено для модели содержимого.</span><span class="sxs-lookup"><span data-stu-id="dd571-103">Wildcard components are used to increase flexibility in what is allowed to appear in a content model.</span></span> <span data-ttu-id="dd571-104">Эти компоненты поддерживаются в языке XSD следующими способами.</span><span class="sxs-lookup"><span data-stu-id="dd571-104">These components are supported in the XSD language in the following ways:</span></span>  
  
-   <span data-ttu-id="dd571-105">Компоненты-шаблоны элемента.</span><span class="sxs-lookup"><span data-stu-id="dd571-105">Element wildcard components.</span></span> <span data-ttu-id="dd571-106">Они представлены элементом **\<xsd:any>** .</span><span class="sxs-lookup"><span data-stu-id="dd571-106">These are represented by the **\<xsd:any>** element.</span></span>  
  
-   <span data-ttu-id="dd571-107">Компоненты-шаблоны атрибута.</span><span class="sxs-lookup"><span data-stu-id="dd571-107">Attribute wildcard components.</span></span> <span data-ttu-id="dd571-108">Они представлены элементом **\<xsd:anyAttribute>** .</span><span class="sxs-lookup"><span data-stu-id="dd571-108">These are represented by the **\<xsd:anyAttribute>** element.</span></span>  
  
 <span data-ttu-id="dd571-109">Оба элемента подстановочного знака, **\<xsd:any>** и **\<xsd:anyAttribute>** , поддерживают использование атрибута **processContents**.</span><span class="sxs-lookup"><span data-stu-id="dd571-109">Both wildcard character elements, **\<xsd:any>** and **\<xsd:anyAttribute>**, support the use of a **processContents** attribute.</span></span> <span data-ttu-id="dd571-110">Это позволяет задать значение, указывающее, как приложения XML обрабатывают проверку правильности содержимого документа, связанную с этими элементами символа-шаблона.</span><span class="sxs-lookup"><span data-stu-id="dd571-110">This lets you specify a value that indicates how XML applications handle the validation of document content associated with these wildcard character elements.</span></span> <span data-ttu-id="dd571-111">Они являются различными значениями, и их действие заключается в следующем.</span><span class="sxs-lookup"><span data-stu-id="dd571-111">These are the different values and their effect:</span></span>  
  
-   <span data-ttu-id="dd571-112">Значение **strict** указывает, что содержимое полностью подтверждено.</span><span class="sxs-lookup"><span data-stu-id="dd571-112">The **strict** value specifies that the contents are fully validated.</span></span>  
  
-   <span data-ttu-id="dd571-113">Значение **skip** указывает, что содержимое не подтверждено.</span><span class="sxs-lookup"><span data-stu-id="dd571-113">The **skip** value specifies that the contents are not validated.</span></span>  
  
-   <span data-ttu-id="dd571-114">Значение **lax** указывает, что только элементы и атрибуты, для которых определения схемы являются доступными, будут подтверждены.</span><span class="sxs-lookup"><span data-stu-id="dd571-114">The **lax** value specifies that only elements and attributes for which schema definitions are available are validated.</span></span>  
  
## <a name="lax-validation-and-xsanytype-elements"></a><span data-ttu-id="dd571-115">Нестрогая проверка и элементы xs:anyType</span><span class="sxs-lookup"><span data-stu-id="dd571-115">Lax Validation and xs:anyType Elements</span></span>  
 <span data-ttu-id="dd571-116">В спецификации XML-схемы для элементов типа **anyType** используется **нестрогая** проверка.</span><span class="sxs-lookup"><span data-stu-id="dd571-116">The XML Schema specification uses **lax** validation for elements of the **anyType** type.</span></span> <span data-ttu-id="dd571-117">Поскольку в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] нестрогая проверка не поддерживалась, к элементам **anyType**применялась строгая проверка.</span><span class="sxs-lookup"><span data-stu-id="dd571-117">Because [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] did not support lax validation, strict validation was applied for elements of the **anyType**.</span></span> <span data-ttu-id="dd571-118">Начиная с версии [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], предоставляется поддержка нестрогой проверки.</span><span class="sxs-lookup"><span data-stu-id="dd571-118">Beginning with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], lax validation is supported.</span></span> <span data-ttu-id="dd571-119">Содержимое элементов типа **anyType** будет осуществляться при помощи нестрогой проверки.</span><span class="sxs-lookup"><span data-stu-id="dd571-119">Content of elements of type **anyType** will be validated using lax validation.</span></span>  
  
 <span data-ttu-id="dd571-120">Следующий пример демонстрирует использование нестрогой проверки.</span><span class="sxs-lookup"><span data-stu-id="dd571-120">The following example illustrates the lax validation.</span></span> <span data-ttu-id="dd571-121">Элемент `e` схемы принадлежит типу **anyType** .</span><span class="sxs-lookup"><span data-stu-id="dd571-121">The schema element `e` is of the **anyType** type.</span></span> <span data-ttu-id="dd571-122">В примере создаются типизированные переменные **xml** и демонстрируется нестрогая проверка элемента типа **anyType** .</span><span class="sxs-lookup"><span data-stu-id="dd571-122">The example creates typed **xml** variables and illustrates the lax validation of the element of the **anyType** type.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="http://ns">  
   <element name="e" type="anyType"/>  
   <element name="a" type="byte"/>  
   <element name="b" type="string"/>  
 </schema>'  
GO  
```  
  
 <span data-ttu-id="dd571-123">Выполнение следующего примера завершится без ошибок, поскольку успешно завершается проверка `<e>` :</span><span class="sxs-lookup"><span data-stu-id="dd571-123">The following example succeeds, because the validation of `<e>` is successful:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="dd571-124">Следующий пример завершается успешно.</span><span class="sxs-lookup"><span data-stu-id="dd571-124">The following example succeeds.</span></span> <span data-ttu-id="dd571-125">Экземпляр принимается, несмотря на то, что элементы `<c>` в схеме не определены.</span><span class="sxs-lookup"><span data-stu-id="dd571-125">The instance is accepted, even though no element `<c>` is defined in the schema:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><c>Wrong</c><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="dd571-126">В следующем примере экземпляр XML отклонен, потому что определение элемента `<a>` не допускает строковых значений.</span><span class="sxs-lookup"><span data-stu-id="dd571-126">The XML instance in the following example is rejected, because the definition of the `<a>` element does not allow a string value.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>Wrong</a><b>data</b></e>'  
SELECT @var  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd571-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd571-127">See Also</span></span>  
 [<span data-ttu-id="dd571-128">Требования и ограничения для коллекций схем XML на сервере</span><span class="sxs-lookup"><span data-stu-id="dd571-128">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
