---
title: Определение ссылочной связи и свойств ссылочной связи | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- referenced dimension relationship
- relationships [Analysis Services], referenced dimensions
ms.assetid: 5bb44b41-635b-4398-8fe9-0bfbb142553e
author: minewiskan
ms.author: owend
ms.openlocfilehash: a84cf2ed95ab3660c5a6b3c039dc58351dc43264
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732129"
---
# <a name="define-a-referenced-relationship-and-referenced-relationship-properties"></a><span data-ttu-id="1eac3-102">Определение ссылочной связи и свойств ссылочной связи</span><span class="sxs-lookup"><span data-stu-id="1eac3-102">Define a Referenced Relationship and Referenced Relationship Properties</span></span>
  <span data-ttu-id="1eac3-103">Связь ссылочного измерения определяется на вкладке **Использование измерений** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="1eac3-103">A reference dimension relationship is defined on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="1eac3-104">Связь ссылочного измерения определяется путем указания следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="1eac3-104">The reference dimension relationship is defined by specifying the following:</span></span>  
  
-   <span data-ttu-id="1eac3-105">Промежуточное измерение, с которым необходимо соединяться.</span><span class="sxs-lookup"><span data-stu-id="1eac3-105">The intermediate dimension to which to join.</span></span> <span data-ttu-id="1eac3-106">Это может быть обычное измерение или другое ссылочное измерение.</span><span class="sxs-lookup"><span data-stu-id="1eac3-106">This can be a regular dimension or another reference dimension.</span></span>  
  
-   <span data-ttu-id="1eac3-107">Атрибут ссылочного измерения, который определяет самый низкий уровень, для которого измерение доступно для статистической обработки по отношению к группе мер.</span><span class="sxs-lookup"><span data-stu-id="1eac3-107">A reference dimension attribute that defines the lowest level that the dimension is available for aggregation with regard to the measure group.</span></span>  
  
-   <span data-ttu-id="1eac3-108">Атрибут (внешний ключ) в промежуточном измерении, соответствующий атрибуту ссылочного измерения.</span><span class="sxs-lookup"><span data-stu-id="1eac3-108">The (foreign key) attribute in the intermediate dimension that corresponds to the reference dimension attribute.</span></span>  
  
 <span data-ttu-id="1eac3-109">Обратим внимание, что столбец, соединяющий ссылочное измерение с таблицей фактов, который обычно является ключевым атрибутом ссылочного измерения, должен также быть определен в качестве атрибута в промежуточном измерении.</span><span class="sxs-lookup"><span data-stu-id="1eac3-109">Notice that the column that links the reference dimension to the fact table, which is generally the key attribute in the reference dimension, must also be defined as an attribute in the intermediate dimension.</span></span> <span data-ttu-id="1eac3-110">При создании цепи ссылочных измерений необходимо начать с создания обычной связи между первым измерением в цепи и группой мер.</span><span class="sxs-lookup"><span data-stu-id="1eac3-110">When you create a chain of reference dimensions, start by creating the regular relationship between the first dimension in the chain and the measure group.</span></span> <span data-ttu-id="1eac3-111">Затем по порядку создайте все дополнительные ссылочные связи.</span><span class="sxs-lookup"><span data-stu-id="1eac3-111">Then create each additional referenced relationship in order.</span></span> <span data-ttu-id="1eac3-112">Ссылочная связь может быть создана только c измерением, в котором существует связь с группой мер.</span><span class="sxs-lookup"><span data-stu-id="1eac3-112">A referenced relationship can only be made to a dimension that has an existing relationship to the measure group.</span></span>  
  
 <span data-ttu-id="1eac3-113">При создании связи ссылочного измерения связь атрибутов измерения материализуется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1eac3-113">When you create a reference dimension relationship, the dimension attribute link is materialized by default.</span></span> <span data-ttu-id="1eac3-114">Материализация связи атрибута измерения заставляет значение связи между таблицей фактов и ссылочным измерением для каждой строки материализоваться, то есть сохраняться, в структуре MOLAP измерения во время обработки.</span><span class="sxs-lookup"><span data-stu-id="1eac3-114">Materializing a dimension attribute link causes the value of the link between the fact table and the reference dimension for each row to be materialized, or stored, in the MOLAP structure for the dimension during processing.</span></span> <span data-ttu-id="1eac3-115">Это оказывает незначительное влияние на производительность и требования к хранению данных, но увеличивает производительность запросов.</span><span class="sxs-lookup"><span data-stu-id="1eac3-115">This will have a minor effect on processing performance and storage requirements, but will improve query performance.</span></span>  
  
 <span data-ttu-id="1eac3-116">В ссылочном измерении гранулярность указывается путем идентификации атрибута, определяющего связь между ссылочным измерением и группой мер, соответствующей главной таблице измерения.</span><span class="sxs-lookup"><span data-stu-id="1eac3-116">In a reference dimension, granularity is specified by identifying the attribute that defines the relationship between a reference dimension and the measure group corresponding to the main table of the dimension.</span></span> <span data-ttu-id="1eac3-117">Когда несколько ссылочных измерений последовательно соединены вместе, ссылки определяют связь между самым внешним измерением и группой мер.</span><span class="sxs-lookup"><span data-stu-id="1eac3-117">When multiple reference dimensions are chained together, the references define the relationship from the outermost dimension to the measure group.</span></span>  
  
  
