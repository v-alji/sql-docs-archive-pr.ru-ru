---
title: 'Указание атрибута SQL: инверсия в SQL: Relationship (SQLXML 4,0) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:relationship
- bulk load [SQLXML]
- inverse attribute
- relationships [SQLXML], inverse orders
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- updategrams [SQLXML], relationships
- sql:inverse
ms.assetid: 08904cbd-9c86-493d-90c3-f5e1d13ce59d
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b0781102371b98cced72a5a0edee70c9567c372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664118"
---
# <a name="specifying-the-sqlinverse-attribute-on-sqlrelationship-sqlxml-40"></a><span data-ttu-id="b672e-102">Задание значения атрибута sql:inverse для sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b672e-102">Specifying the sql:inverse Attribute on sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="b672e-103">Атрибут `sql:inverse` полезен только при использовании схемы XSD диаграммой обновления или при массовой загрузке.</span><span class="sxs-lookup"><span data-stu-id="b672e-103">The `sql:inverse` attribute is useful only when the XSD schema is used for either bulk load or by an updategram.</span></span> <span data-ttu-id="b672e-104">`sql:inverse`Атрибут может быть указан в **\<sql:relationship>** элементе.</span><span class="sxs-lookup"><span data-stu-id="b672e-104">The `sql:inverse` attribute can be specified on the **\<sql:relationship>** element.</span></span> <span data-ttu-id="b672e-105">В диаграммах обновления их логика задействует схему при определении таблиц и столбцов, обновляемых операцией диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="b672e-105">In updategrams, the updategram logic interprets the schema in determining the tables and columns that are updated by the updategram operation.</span></span> <span data-ttu-id="b672e-106">Связи типа «родители-потомки», заданные в схеме, определяют порядок, в котором записи будут изменены (вставлены или удалены).</span><span class="sxs-lookup"><span data-stu-id="b672e-106">The parent-child relationships that are specified in the schema determine the order in which the records are modified (inserted or deleted).</span></span>  
  
 <span data-ttu-id="b672e-107">Если в схеме XSD связь «родители-потомки» задана в обратном порядке отношения «первичный ключ — внешний ключ» между соответствующими столбцами базы данных, операции вставки или удаления диаграммы обновления завершатся ошибкой из-за нарушения первичного ключа или внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="b672e-107">If you have an XSD schema in which the parent-child relationship is specified in the inverse order of the primary-key/foreign-key relationship between the corresponding database columns, the insert or delete updategram operation will fail because of the primary-key/foreign-key violation.</span></span> <span data-ttu-id="b672e-108">В таких случаях `sql:inverse` атрибут указывается ( `sql:inverse="true"` ) в **\<sql:relationship>** элементе, а логика диаграмма обновления обратно интерпретирует связь типа «родители-потомки», указанную в схеме.</span><span class="sxs-lookup"><span data-stu-id="b672e-108">In such cases, the `sql:inverse` attribute is specified (`sql:inverse="true"`) in the **\<sql:relationship>** element, and the updategram logic inverses its interpretation of the parent-child relationship specified in the schema.</span></span>  
  
 <span data-ttu-id="b672e-109">Атрибут `sql:inverse` имеет логическое значение (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="b672e-109">The `sql:inverse` attribute takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="b672e-110">Допустимые значения: 0, 1, true и false.</span><span class="sxs-lookup"><span data-stu-id="b672e-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="b672e-111">Рабочий пример с помощью `sql:inverse` заметки см. в разделе [указание схемы сопоставления с заметками в диаграмма обновления](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="b672e-111">For a working sample using the `sql:inverse` annotation, see [Specifying an Annotated Mapping Schema in an Updategram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b672e-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="b672e-112">See Also</span></span>  
 [<span data-ttu-id="b672e-113">Указание связей с помощью SQL: relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b672e-113">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
  
  
