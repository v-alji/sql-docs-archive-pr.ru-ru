---
title: Канонические формы и ограничения шаблона | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- pattern restrictions
- canonical forms
ms.assetid: 088314ec-7d0b-4a05-8a33-f35da5bfe59c
author: rothja
ms.author: jroth
ms.openlocfilehash: 569e8c4a01ed1eb9ae26ea9e2f6d471b9aad9fe0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654959"
---
# <a name="canonical-forms-and-pattern-restrictions"></a><span data-ttu-id="c812a-102">Канонические формы и ограничения шаблона</span><span class="sxs-lookup"><span data-stu-id="c812a-102">Canonical Forms and Pattern Restrictions</span></span>
  <span data-ttu-id="c812a-103">Аспект шаблона XSD позволяет вводить ограничение лексического пространства простых типов.</span><span class="sxs-lookup"><span data-stu-id="c812a-103">The XSD pattern facet allows for the restriction of the lexical space of simple types.</span></span> <span data-ttu-id="c812a-104">Когда ограничение шаблона наложено на тип, для которого есть больше одного возможного лексического представления, некоторые значения могут вызвать непредвиденное поведение в ходе проверки.</span><span class="sxs-lookup"><span data-stu-id="c812a-104">When a pattern restriction is put on a type for which there is more than one possible lexical representation, some values could cause unexpected behavior upon validation.</span></span>  
  
 <span data-ttu-id="c812a-105">Такое поведение возникает, потому что лексические представления этих значений не сохраняются в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c812a-105">This behavior occurs because lexical representations of these values are not stored in the database.</span></span> <span data-ttu-id="c812a-106">Поэтому значения будут преобразованы к их каноническим представлениям при сериализации вывода.</span><span class="sxs-lookup"><span data-stu-id="c812a-106">Therefore, the values are converted to their canonical representations when serialized as output.</span></span> <span data-ttu-id="c812a-107">Если документ содержит значение, каноническая форма которого не соответствует ограничению шаблона для его типа, то документ будет отклонен, если пользователь попытается вставить его повторно.</span><span class="sxs-lookup"><span data-stu-id="c812a-107">If a document contains a value whose canonical form does not comply with the pattern restriction for its type, the document is rejected if a user tries to reinsert it.</span></span>  
  
 <span data-ttu-id="c812a-108">Чтобы это предотвратить, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отклоняет любой документ XML, содержащий значения, которые не могут быть повторно вставлены из-за нарушения ограничений шаблона их каноническими формами.</span><span class="sxs-lookup"><span data-stu-id="c812a-108">To prevent this, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejects any XML document that contains values that cannot be reinserted, because of the violation of pattern restrictions by their canonical forms.</span></span> <span data-ttu-id="c812a-109">Например, значение "33.000" не пройдет проверку относительно типа, производного от **xs:decimal** с ограничением шаблона "33.\\.0+".</span><span class="sxs-lookup"><span data-stu-id="c812a-109">For example, the value "33.000" does not validate against a type derived from **xs:decimal** with a pattern restriction of "33\\.0+".</span></span> <span data-ttu-id="c812a-110">Хотя «33.000» соответствует этому шаблону, его каноническая форма «33» шаблону не соответствует.</span><span class="sxs-lookup"><span data-stu-id="c812a-110">Although "33.000" complies with this pattern, the canonical form, "33", does not.</span></span>  
  
 <span data-ttu-id="c812a-111">Поэтому следует быть внимательными при применении аспектов шаблона к типам, производным от следующих типов-примитивов: `boolean`, `decimal`, `float`, `double`, `dateTime`, `time`, `date`, `hexBinary` и `base64Binary`.</span><span class="sxs-lookup"><span data-stu-id="c812a-111">Therefore, you should be careful when you apply pattern facets to types derived from the following primitive types: `boolean`, `decimal`, `float`, `double`, `dateTime`, `time`, `date`, `hexBinary`, and `base64Binary`.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c812a-112">выдаст предупреждение при добавлении любых таких компонентов к коллекции схемы.</span><span class="sxs-lookup"><span data-stu-id="c812a-112">issues a warning when you add any such components to a schema collection.</span></span>  
  
 <span data-ttu-id="c812a-113">Неточная сериализация значений с плавающей запятой вызывает подобную проблему.</span><span class="sxs-lookup"><span data-stu-id="c812a-113">Imprecise serialization of floating-point values has a similar problem.</span></span> <span data-ttu-id="c812a-114">Из-за алгоритма сериализации с плавающей запятой, используемого [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], для подобных значений можно совместно использовать одну каноническую форму.</span><span class="sxs-lookup"><span data-stu-id="c812a-114">Because of the floating-point serialization algorithm used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is possible for similar values to share the same canonical form.</span></span> <span data-ttu-id="c812a-115">Когда значение с плавающей запятой сериализовано и затем повторно вставлено, его значение может немного измениться.</span><span class="sxs-lookup"><span data-stu-id="c812a-115">When a floating-point value is serialized and then reinserted, its value may change slightly.</span></span> <span data-ttu-id="c812a-116">В редких случаях это может привести к значению, нарушающему любой из следующих аспектов для его типа при повторной вставке: **enumeration**, **minInclusive**, **minExclusive**, **maxInclusive**или **maxExclusive**.</span><span class="sxs-lookup"><span data-stu-id="c812a-116">In rare cases, this may result in a value that violates any of the following facets for its type on reinsertion: **enumeration**, **minInclusive**, **minExclusive**, **maxInclusive**, or **maxExclusive**.</span></span> <span data-ttu-id="c812a-117">Чтобы это предотвратить, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отклоняет любые значения типов, полученных из `xs:float` или `xs:double` , которые не могут быть сериализованы и повторно вставлены.</span><span class="sxs-lookup"><span data-stu-id="c812a-117">To prevent this, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejects any values of types derived from `xs:float` or `xs:double` that cannot be serialized and reinserted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c812a-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="c812a-118">See Also</span></span>  
 [<span data-ttu-id="c812a-119">Требования и ограничения для коллекций схем XML на сервере</span><span class="sxs-lookup"><span data-stu-id="c812a-119">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  