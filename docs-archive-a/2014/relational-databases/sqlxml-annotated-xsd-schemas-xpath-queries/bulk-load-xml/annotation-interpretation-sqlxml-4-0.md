---
title: Интерпретация аннотации (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, XML Bulk Load
- XML Bulk Load [SQLXML], annotation intepretations
- annotations [SQLXML]
- bulk load [SQLXML], annotation interpretations
- annotated XDR schemas, XML Bulk Load
ms.assetid: 1c46bdb6-2812-4a13-b60b-7101c04b299f
author: rothja
ms.author: jroth
ms.openlocfilehash: c31d56f7dd577b4b5a5b582eb0e3b1db312109a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665973"
---
# <a name="annotation-interpretation-sqlxml-40"></a><span data-ttu-id="82b74-102">Интерпретация заметки (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="82b74-102">Annotation Interpretation (SQLXML 4.0)</span></span>
  <span data-ttu-id="82b74-103">В подразделах этого раздела приведено описание того, как осуществляется интерпретация заметок в схеме XSD при массовой загрузке XML.</span><span class="sxs-lookup"><span data-stu-id="82b74-103">The topics in this section describe how XML Bulk Load interprets annotations in the XSD schema.</span></span> <span data-ttu-id="82b74-104">Поведение, описанное здесь, применимо также к заметкам в схеме XDR.</span><span class="sxs-lookup"><span data-stu-id="82b74-104">The behavior described here also applies to the annotations in the XDR schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82b74-105">Сведения в этих разделах описывают только заметки, используемые средствами массовой загрузки XML при обработке.</span><span class="sxs-lookup"><span data-stu-id="82b74-105">The information in these topics describes only the annotations used by XML Bulk Load in its processing.</span></span> <span data-ttu-id="82b74-106">Полный список заметок для схемы XSD, поддерживаемых SQLXML 4,0, см. [в разделе Использование заметок в схемах xsd &#40;sqlxml 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="82b74-106">For a complete list of annotations for the XSD schema that are supported by SQLXML 4.0, see [Using Annotations in XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="82b74-107">Список поддерживаемых заметок для схем XDR см. [в разделе схемы XDR с Заметками &#40;нерекомендуемые в SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="82b74-107">For a list of supported annotations for XDR schemas, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82b74-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="82b74-108">In This Section</span></span>  
 [<span data-ttu-id="82b74-109">SQL: отношение и правило упорядочивания ключей &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="82b74-109">sql:relationship and the Key Ordering Rule &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-relationship-and-key-ordering-rule.md)  
 <span data-ttu-id="82b74-110">Описывает способ интерпретации заметки `sql:relationship` при массовой загрузке XML.</span><span class="sxs-lookup"><span data-stu-id="82b74-110">Describes how the `sql:relationship` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="82b74-111">SQL: сопоставленная &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="82b74-111">sql:mapped &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-mapped.md)  
 <span data-ttu-id="82b74-112">Описывает способ интерпретации заметки `sql:mapped` при массовой загрузке XML.</span><span class="sxs-lookup"><span data-stu-id="82b74-112">Describes how the `sql:mapped` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="82b74-113">SQL: limit-field и SQL: limit-value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="82b74-113">sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="82b74-114">Описывает способ интерпретации заметок `sql:limit-field` и `sql:limit-value` при массовой загрузке XML.</span><span class="sxs-lookup"><span data-stu-id="82b74-114">Describes how the `sql:limit-field` and `sql:limit-value` annotations are interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="82b74-115">SQL: overflow — поле &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="82b74-115">sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="82b74-116">Описывает способ интерпретации заметки `sql:overflow` при массовой загрузке XML.</span><span class="sxs-lookup"><span data-stu-id="82b74-116">Describes how the `sql:overflow` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="82b74-117">Другие заметки &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="82b74-117">Other Annotations &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-other-annotations.md)  
 <span data-ttu-id="82b74-118">Описывает интерпретацию следующих аннотаций при выполнении групповой загрузки XML: `sql:id-prefix` , `sql:use-cdata` , `sql:url-encode` , `sql:is-mapping-schema` , `sql:key-fields` .</span><span class="sxs-lookup"><span data-stu-id="82b74-118">Describes how the following annotations are interpreted in XML Bulk Load: `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span></span>  
  
  
