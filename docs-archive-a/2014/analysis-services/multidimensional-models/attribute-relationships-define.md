---
title: Определение связей атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
ms.assetid: 9184d344-e96d-4025-ad6f-3f75129746df
author: minewiskan
ms.author: owend
ms.openlocfilehash: a694c68a55de2533c4ce7791d3be865008b6321f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655418"
---
# <a name="define-attribute-relationships"></a><span data-ttu-id="1e420-102">Определение связей атрибутов</span><span class="sxs-lookup"><span data-stu-id="1e420-102">Define Attribute Relationships</span></span>
  <span data-ttu-id="1e420-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] атрибуты являются фундаментальным стандартным блоком измерения.</span><span class="sxs-lookup"><span data-stu-id="1e420-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes are the fundamental building block of a dimension.</span></span> <span data-ttu-id="1e420-104">Измерение содержит набор атрибутов, организованных на основе связей между ними.</span><span class="sxs-lookup"><span data-stu-id="1e420-104">A dimension contains a set of attributes that are organized based on attribute relationships.</span></span>  
  
 <span data-ttu-id="1e420-105">Для каждой таблицы, содержащейся в измерении, существует связь атрибутов, задающая связь ключевого атрибута таблицы с другими атрибутами из той же таблицы.</span><span class="sxs-lookup"><span data-stu-id="1e420-105">For each table included in a dimension, there is an attribute relationship that relates the table's key attribute to other attributes from that table.</span></span> <span data-ttu-id="1e420-106">Эта связь устанавливается при создании измерения.</span><span class="sxs-lookup"><span data-stu-id="1e420-106">You create this relationship when you create the dimension.</span></span>  
  
 <span data-ttu-id="1e420-107">Связь атрибутов дает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="1e420-107">An attribute relationship provides the following advantages:</span></span>  
  
-   <span data-ttu-id="1e420-108">Снижает объем памяти, необходимый для обработки измерения.</span><span class="sxs-lookup"><span data-stu-id="1e420-108">Reduces the amount of memory needed for dimension processing.</span></span> <span data-ttu-id="1e420-109">Это ускоряет обработку измерений, секций и запросов.</span><span class="sxs-lookup"><span data-stu-id="1e420-109">This speeds up dimension, partition, and query processing.</span></span>  
  
-   <span data-ttu-id="1e420-110">Повышает производительность запросов, поскольку ускоряется доступ к хранилищу и лучше оптимизируются планы выполнения.</span><span class="sxs-lookup"><span data-stu-id="1e420-110">Increases query performance because storage access is faster and execution plans are better optimized.</span></span>  
  
-   <span data-ttu-id="1e420-111">Приводит к выбору более эффективных алгоритмов создания статистических схем (при условии, что пользовательские иерархии были определены по путям связей).</span><span class="sxs-lookup"><span data-stu-id="1e420-111">Results in the selection of more effective aggregates by the aggregation design algorithms, provided that user-defined hierarchies have been defined along the relationship paths.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e420-112">Дополнительные сведения о важности и влиянии на определение и настройку связей атрибутов см. в разделе "повышение производительности запросов" статьи [SQL Server 2005 Analysis Services (обзор производительности](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide)).</span><span class="sxs-lookup"><span data-stu-id="1e420-112">For more information about the importance and implications of defining and configuring attribute relationships, see the section, "Enhancing query performance," in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="attribute-relationship-considerations"></a><span data-ttu-id="1e420-113">Сведения о связях атрибутов</span><span class="sxs-lookup"><span data-stu-id="1e420-113">Attribute Relationship Considerations</span></span>  
 <span data-ttu-id="1e420-114">Если базовые данные позволяют, следует задавать уникальную связь между атрибутами.</span><span class="sxs-lookup"><span data-stu-id="1e420-114">When the underlying data supports it, you should also define unique attribute relationships between attributes.</span></span> <span data-ttu-id="1e420-115">Для задания уникальных связей между атрибутами используется вкладка **Связи атрибутов** конструктора измерений.</span><span class="sxs-lookup"><span data-stu-id="1e420-115">To define unique attribute relationships, use the **Attribute Relationships** tab of Dimension Designer.</span></span>  
  
 <span data-ttu-id="1e420-116">Любой атрибут с исходящей связью должен иметь уникальный ключ для связанного с ним атрибута.</span><span class="sxs-lookup"><span data-stu-id="1e420-116">Any attribute that has an outgoing relationship must have a unique key relative to its related attribute.</span></span> <span data-ttu-id="1e420-117">Иными словами, элемент исходного атрибута должен однозначно задавать элемент в связанном с ним атрибуте.</span><span class="sxs-lookup"><span data-stu-id="1e420-117">In other words, a member in a source attribute must identify one and only one member in a related attribute.</span></span> <span data-ttu-id="1e420-118">Рассмотрим для примера связь «Город» -> «Страна».</span><span class="sxs-lookup"><span data-stu-id="1e420-118">For example, consider the relationship, City -> State.</span></span> <span data-ttu-id="1e420-119">В этой связи «Город» является исходным атрибутом, а «Страна» — связанным с ним.</span><span class="sxs-lookup"><span data-stu-id="1e420-119">In this relationship, the source attribute is City and the related attribute is State.</span></span> <span data-ttu-id="1e420-120">Исходным атрибутом является сторона «многие», а связанная сторона — это сторона «один» связи «многие к одному».</span><span class="sxs-lookup"><span data-stu-id="1e420-120">The source attribute is the "many" side and the related side is the "one" side of the many-to-one relationship.</span></span> <span data-ttu-id="1e420-121">Ключом для исходного атрибута будет «Город»+«Страна».</span><span class="sxs-lookup"><span data-stu-id="1e420-121">The key for the source attribute would be City + State.</span></span> <span data-ttu-id="1e420-122">Дополнительные сведения см. в разделе [Создание, изменение или удаление связи атрибутов](attribute-relationships-create-modify-or-delete-relationship.md).</span><span class="sxs-lookup"><span data-stu-id="1e420-122">For more information, see [Create, Modify, or Delete an Attribute Relationship](attribute-relationships-create-modify-or-delete-relationship.md).</span></span>  
  
 <span data-ttu-id="1e420-123">Дополнительные сведения о свойствах связей атрибутов см. в разделе [Настройка свойств связи атрибутов](attribute-relationships-configure-attribute-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1e420-123">For more information about properties of an attribute relationship, see [Configure Attribute Relationship Properties](attribute-relationships-configure-attribute-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e420-124">Если неправильно задать связь, запрос может дать неправильные результаты.</span><span class="sxs-lookup"><span data-stu-id="1e420-124">Defining attribute relationships incorrectly can cause invalid query results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e420-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e420-125">See Also</span></span>  
 [<span data-ttu-id="1e420-126">можно изменить расположение фигур на вкладке</span><span class="sxs-lookup"><span data-stu-id="1e420-126">Attribute Relationships</span></span>](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md)  
  
  
