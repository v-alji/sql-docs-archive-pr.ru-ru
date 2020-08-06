---
title: Ограничение однозначного соответствия примитивов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
f1_keywords:
- unique particle attribution
helpviewer_keywords:
- schema collections [SQL Server], unique particle attribution
- XML schema collections [SQL Server], unique particle attribution
- UPA constraint rule
- unique particle attribution constraint rule
ms.assetid: 6bb879e9-a5ee-402e-94e4-fe8cec5966b0
author: rothja
ms.author: jroth
ms.openlocfilehash: 7416aa4ea14539f3bf633207768783aa439ec818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728098"
---
# <a name="unique-particle-attribution-constraint"></a><span data-ttu-id="c1f0e-102">Ограничение однозначного соответствия примитивов</span><span class="sxs-lookup"><span data-stu-id="c1f0e-102">Unique Particle Attribution Constraint</span></span>
  <span data-ttu-id="c1f0e-103">В XSD сложные модели содержимого ограничены правилом ограничения однозначного соответствия примитивов.</span><span class="sxs-lookup"><span data-stu-id="c1f0e-103">In XSD, complex content models are constrained by the unique particle attribution (UPA) constraint rule.</span></span> <span data-ttu-id="c1f0e-104">Это правило требует, чтобы каждый элемент в экземпляре документа однозначно соответствовал единственному примитиву `<xsd:element>` или `<xsd:any>` в родительской модели содержимого.</span><span class="sxs-lookup"><span data-stu-id="c1f0e-104">This rule requires that each element in an instance document correspond unambiguously to exactly one `<xsd:element>` or `<xsd:any>` particle in its parent's content model.</span></span> <span data-ttu-id="c1f0e-105">Любая схема, которая содержит тип с потенциально неоднозначной моделью содержимого, отклоняется.</span><span class="sxs-lookup"><span data-stu-id="c1f0e-105">Any schema that contains a type with a potentially ambiguous content model is rejected.</span></span>  
  
 <span data-ttu-id="c1f0e-106">Чаще всего неоднозначность возникает при использовании символов-шаблонов `<xsd:any>` и примитивов, имеющих переменные диапазоны, например minOccurs < maxOccurs.</span><span class="sxs-lookup"><span data-stu-id="c1f0e-106">The most common causes of ambiguity are `<xsd:any>` wildcard characters and particles that have variable occurrence ranges, such as minOccurs < maxOccurs.</span></span> <span data-ttu-id="c1f0e-107">Приведенная ниже модель содержимого является неоднозначной, так как элемент <`e1`> может соответствовать элементам `<xsd:element>` и `<xsd:any>`.</span><span class="sxs-lookup"><span data-stu-id="c1f0e-107">For example, the following content model is ambiguous, because an <`e1`> element could match either the `<xsd:element>` or the `<xsd:any>` element.</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
            <xsd:element name="e1"/>  
            <xsd:any namespace="##any"/>  
        </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="c1f0e-108">Следующая модель содержимого также является неоднозначной:</span><span class="sxs-lookup"><span data-stu-id="c1f0e-108">The following content model is also ambiguous:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:sequence>  
            <xsd:element name="e1" maxOccurs="2"/>  
            <xsd:element name="e2" minOccurs="0"/>  
            <xsd:element name="e1"/>  
        </xsd:sequence>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="c1f0e-109">В отличие от документа `<root><e1/><e2/><e1/></root>` , документ `<root><e1/><e1/></root>` является неоднозначным, поскольку неясно, к какому элементу `<xsd:element>` относится второй элемент `<e1/>` .</span><span class="sxs-lookup"><span data-stu-id="c1f0e-109">Although a document such as `<root><e1/><e2/><e1/></root>` can be validated unambiguously, a document such as `<root><e1/><e1/></root>` cannot, because it is not clear to which `<xsd:element>` the second `<e1/>` corresponds.</span></span> <span data-ttu-id="c1f0e-110">Даже если документы можно проверить однозначно, схема будет отклонена, поскольку возможность неоднозначности существует.</span><span class="sxs-lookup"><span data-stu-id="c1f0e-110">Even though some documents can be validated unambiguously, the schema will be rejected, because of the potential for ambiguity.</span></span>  
  
 <span data-ttu-id="c1f0e-111">Чтобы модель содержимого была допустимой, должна существовать возможность однозначно проверить любой экземпляр, не заглядывая вперед.</span><span class="sxs-lookup"><span data-stu-id="c1f0e-111">Note that for a content model to be valid, it must be possible to validate any instance unambiguously without looking ahead.</span></span> <span data-ttu-id="c1f0e-112">Например, рассмотрим следующую модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="c1f0e-112">For example, consider the following content model:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e2"/>  
           </xsd:sequence>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e3"/>  
           </xsd:sequence>  
       </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="c1f0e-113">Для такого документа, как `<root><e1/><e3/></root>`, последовательность `<e1/><e3/>` однозначно совпадает со вторым элементом `<xsd:sequence>`.</span><span class="sxs-lookup"><span data-stu-id="c1f0e-113">For a document such as `<root><e1/><e3/></root>`, the sequence `<e1/><e3/>` unambiguously matches the second `<xsd:sequence>`.</span></span> <span data-ttu-id="c1f0e-114">Тем не менее, поскольку элемент `<xsd:element>` , к которому относится `<e1/>` , нельзя определить, не заглядывая вперед в `<e3/>`, модель содержимого нарушает правило ограничения однозначного соответствия примитивов.</span><span class="sxs-lookup"><span data-stu-id="c1f0e-114">However, because the `<xsd:element>` to which `<e1/>` corresponds cannot be determined without looking ahead to `<e3/>`, the content model violates the UPA constraint rule.</span></span>  
  
## <a name="finding-more-information"></a><span data-ttu-id="c1f0e-115">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c1f0e-115">Finding More Information</span></span>  
 <span data-ttu-id="c1f0e-116">Следующий документ опубликован консорциумом World Wide Web (W3C) и содержит техническое описание ограничения однозначного соответствия примитивов:</span><span class="sxs-lookup"><span data-stu-id="c1f0e-116">The following document is published by the World Wide Web Consortium (W3C) and contains the technical description of the unique particle attribution constraint:</span></span>  
  
 <span data-ttu-id="c1f0e-117">"Схема XML. Часть 1: структуры, второе издание, W3C Proposed Edited Recommendation":</span><span class="sxs-lookup"><span data-stu-id="c1f0e-117">"XML Schema Part 1: Structures Second Edition, W3C Proposed Edited Recommendation":</span></span>  
  
-   <span data-ttu-id="c1f0e-118">раздел 3.8.6. Ограничения компонентов схемы группы моделей</span><span class="sxs-lookup"><span data-stu-id="c1f0e-118">Section 3.8.6: Constraints on Model Group Schema Components</span></span>  
  
-   <span data-ttu-id="c1f0e-119">Приложение H. Анализ ограничения однозначного соответствия примитивов (ненормативный)</span><span class="sxs-lookup"><span data-stu-id="c1f0e-119">Appendix H: Analysis of the Unique Particle Attribution Constraint (non-normative)</span></span>  
  
 <span data-ttu-id="c1f0e-120">Чтобы просмотреть документ, перейдите по адресу [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881).</span><span class="sxs-lookup"><span data-stu-id="c1f0e-120">To see the document, visit [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f0e-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c1f0e-121">See Also</span></span>  
 [<span data-ttu-id="c1f0e-122">Коллекции XML-схем (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c1f0e-122">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
