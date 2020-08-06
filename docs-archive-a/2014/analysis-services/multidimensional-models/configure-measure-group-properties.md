---
title: Настройка свойств группы мер | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- properties [Analysis Services], measure groups
ms.assetid: fa66bdb6-60b8-413c-ac2a-00e4d09f60a2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 03dad3d8ee33ea8a78b08f9a354d0db3d177198c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737112"
---
# <a name="configure-measure-group-properties"></a><span data-ttu-id="f620a-102">Настройка свойств группы мер</span><span class="sxs-lookup"><span data-stu-id="f620a-102">Configure Measure Group Properties</span></span>
  <span data-ttu-id="f620a-103">Группы мер имеют свойства, которые позволяют определить функционирование групп мер.</span><span class="sxs-lookup"><span data-stu-id="f620a-103">Measures groups have properties that enable you to define how measure groups function.</span></span>  
  
## <a name="measure-group-properties"></a><span data-ttu-id="f620a-104">Свойства группы мер</span><span class="sxs-lookup"><span data-stu-id="f620a-104">Measure Group Properties</span></span>  
 <span data-ttu-id="f620a-105">Свойства группы мер определяют характеристики всей группы мер и устанавливают характеристики по умолчанию для определенных свойств мер в группе мер.</span><span class="sxs-lookup"><span data-stu-id="f620a-105">Measure group properties determine behaviors for the entire measure group and set the default behaviors for certain properties of measures within a measure group.</span></span>  
  
|<span data-ttu-id="f620a-106">Свойство</span><span class="sxs-lookup"><span data-stu-id="f620a-106">Property</span></span>|<span data-ttu-id="f620a-107">Определение</span><span class="sxs-lookup"><span data-stu-id="f620a-107">Definition</span></span>|  
|--------------|----------------|  
|`AggregationPrefix`|<span data-ttu-id="f620a-108">Применяется к режиму хранения ROLAP.</span><span class="sxs-lookup"><span data-stu-id="f620a-108">Applies to ROLAP storage.</span></span> <span data-ttu-id="f620a-109">Назначает общий префикс для индексированных представлений в SQL Server, используемых для хранения агрегатов для разделов, связанных с этой группой мер.</span><span class="sxs-lookup"><span data-stu-id="f620a-109">Assigns a common prefix to the indexed views in SQL Server, used to store aggregations for the partitions associated with this measure group.</span></span>|  
|`DataAggregation`|<span data-ttu-id="f620a-110">Это свойство зарезервировано для будущего использования и в настоящее время не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="f620a-110">This property is reserved for future use and currently has no effect.</span></span> <span data-ttu-id="f620a-111">Поэтому не рекомендуется изменять этот параметр.</span><span class="sxs-lookup"><span data-stu-id="f620a-111">Therefore, it is recommended that you do not modify this setting.</span></span>|  
|`Description`|<span data-ttu-id="f620a-112">Это свойство можно использовать для документирования группы мер.</span><span class="sxs-lookup"><span data-stu-id="f620a-112">You can use this property to document the measure group.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="f620a-113">Настраиваемые параметры обработки ошибок для обработки повторяющихся ключей, неизвестных ключей, ключей NULL, предельного количества ошибок, действий при обнаружении ошибки и файла журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="f620a-113">Configurable error handling settings for handling of duplicate keys, unknown keys, null keys, error limits, action upon error detection, and the error log file.</span></span> <span data-ttu-id="f620a-114">См раздел [Конфигурация ошибок при обработке кубов, секций и измерений (службы SSAS — многомерные данные)](error-configuration-for-cube-partition-and-dimension-processing.md).</span><span class="sxs-lookup"><span data-stu-id="f620a-114">See [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](error-configuration-for-cube-partition-and-dimension-processing.md).</span></span>|  
|`EstimatedRows`|<span data-ttu-id="f620a-115">Предполагаемое количество строк в таблице фактов.</span><span class="sxs-lookup"><span data-stu-id="f620a-115">Specifies the estimated number of rows in the fact table.</span></span>|  
|`EstimatedSize`|<span data-ttu-id="f620a-116">Предполагаемый размер группы мер в байтах.</span><span class="sxs-lookup"><span data-stu-id="f620a-116">Specifies the estimated size (in bytes) of the measure group.</span></span>|  
|`ID`|<span data-ttu-id="f620a-117">Идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="f620a-117">Specifies the identifier of the object.</span></span>|  
|`IgnoreUnrelatedDimensions`|<span data-ttu-id="f620a-118">Определяет, будут ли несвязанные измерения принудительно перемещаться на верхний уровень, если элементы измерений, не связанных с группой мер, включаются в запрос.</span><span class="sxs-lookup"><span data-stu-id="f620a-118">Determines whether unrelated dimensions are forced to their top level when members of dimensions that are unrelated to the measure group are included in a query.</span></span> <span data-ttu-id="f620a-119">Значение по умолчанию — `True`.</span><span class="sxs-lookup"><span data-stu-id="f620a-119">Default setting is `True`.</span></span>|  
|`Name`|<span data-ttu-id="f620a-120">Имя меры.</span><span class="sxs-lookup"><span data-stu-id="f620a-120">Name of the measure.</span></span> <span data-ttu-id="f620a-121">Это свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f620a-121">This property is read-only.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="f620a-122">Настраиваемые параметры обработки ошибок для обработки повторяющихся ключей, неизвестных ключей, ключей NULL, предельного количества ошибок, действий при обнаружении ошибки и файла журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="f620a-122">Configurable error handling settings for handling of duplicate keys, unknown keys, null keys, error limits, action upon error detection, and the error log file.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="f620a-123">Показывает, следует ли производить индексирование и статистическую обработку во время обработки или после нее.</span><span class="sxs-lookup"><span data-stu-id="f620a-123">Indicates whether indexing and aggregating should occur during or after processing.</span></span> <span data-ttu-id="f620a-124">Режимы — Regular и LazyAggregations.</span><span class="sxs-lookup"><span data-stu-id="f620a-124">Options are Regular and LazyAggregations.</span></span> <span data-ttu-id="f620a-125">LazyAggregations можно использовать для выполнения статистической обработки в качестве фоновой задачи.</span><span class="sxs-lookup"><span data-stu-id="f620a-125">LazyAggregations can be used to run aggregation as a background task.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="f620a-126">Определяет приоритет обработки куба во время фоновых операций, например отложенных статистических вычислений или индексирования.</span><span class="sxs-lookup"><span data-stu-id="f620a-126">Determines the processing priority of the cube during background operations, such as lazy aggregations and indexing.</span></span> <span data-ttu-id="f620a-127">Значение по умолчанию — **0**.</span><span class="sxs-lookup"><span data-stu-id="f620a-127">The default value is **0**.</span></span>|  
|`StorageLocation`|<span data-ttu-id="f620a-128">Место хранения в файловой системе для группы мер.</span><span class="sxs-lookup"><span data-stu-id="f620a-128">The file system storage location for the measure group.</span></span> <span data-ttu-id="f620a-129">Если расположение не указано, оно наследуется из куба, содержащего эту группу мер.</span><span class="sxs-lookup"><span data-stu-id="f620a-129">If none is specified, the location is inherited from the cube that contains the measure group.</span></span>|  
|`StorageMode`|<span data-ttu-id="f620a-130">Режим хранения для группы мер.</span><span class="sxs-lookup"><span data-stu-id="f620a-130">The storage mode for the measure group.</span></span> <span data-ttu-id="f620a-131">Доступные значения — MOLAP, ROLAP или HOLAP.</span><span class="sxs-lookup"><span data-stu-id="f620a-131">Available values are MOLAP, ROLAP, or HOLAP.</span></span>|  
|`Type`|<span data-ttu-id="f620a-132">Указывает тип группы мер.</span><span class="sxs-lookup"><span data-stu-id="f620a-132">Specifies the type of the measure group.</span></span>|  
  
  
