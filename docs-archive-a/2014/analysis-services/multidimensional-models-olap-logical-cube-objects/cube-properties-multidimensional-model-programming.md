---
title: Свойства куба | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Collation property
- ID property
- ErrorConfiguration property
- cubes [Analysis Services], properties
- Description property
- DefaultMeasure property
- ProcessingMode property
- AggregationPrefix property
- EstimatedRows property
- Visible property
- StorageLocation property
- StorageMode property
- ScriptErrorHandlingMode property
- Source property
- ScriptCacheProcessingMode property
- Language property
- Name property
- properties [Analysis Services], cubes
- ProcessingPriority property
- ProactiveCaching property
ms.assetid: 72ca3387-620d-4473-8e23-7fe1f2b3d5bf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 27d4202774107795eaddf76c27e21010d534d977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656024"
---
# <a name="cube-properties"></a><span data-ttu-id="ac5e0-102">Свойства куба</span><span class="sxs-lookup"><span data-stu-id="ac5e0-102">Cube Properties</span></span>
  <span data-ttu-id="ac5e0-103">Кубы имеют ряд свойств, изменение которых оказывает непосредственное влияние на их работу.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-103">Cubes have a number of properties that you can set to affect cube-wide behavior.</span></span> <span data-ttu-id="ac5e0-104">Эти свойства перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-104">These properties are summarized in the following table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac5e0-105">Некоторые свойства устанавливаются автоматически при создании куба и не могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-105">Some properties are set automatically when the cube is created and cannot be changed.</span></span>  
  
 <span data-ttu-id="ac5e0-106">Дополнительные сведения о настройке свойств куба см. в разделе [конструктор кубов &#40;Analysis Services многомерных данных&#41;](../cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ac5e0-106">For more information about how to set cube properties, see [Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](../cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
|<span data-ttu-id="ac5e0-107">Свойство</span><span class="sxs-lookup"><span data-stu-id="ac5e0-107">Property</span></span>|<span data-ttu-id="ac5e0-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ac5e0-108">Description</span></span>|  
|--------------|-----------------|  
|`AggregationPrefix`|<span data-ttu-id="ac5e0-109">Общий префикс, используемый для имен агрегатов.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-109">Specifies the common prefix that is used for aggregation names.</span></span>|  
|`Collation`|<span data-ttu-id="ac5e0-110">Код локали (LCID) и флаг сравнения, отделенный символом подчеркивания, например Latin1_General_C1_AS.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-110">Specifies the locale identifier (LCID) and the comparison flag, separated by an underscore: for example, Latin1_General_C1_AS.</span></span>|  
|`DefaultMeasure`|<span data-ttu-id="ac5e0-111">Содержит многомерное выражение, определяющее меру для куба по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-111">Contains a Multidimensional Expressions (MDX) expression that defines the default measure for the cube.</span></span>|  
|`Description`|<span data-ttu-id="ac5e0-112">Содержит описание куба, которое может отображаться в клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-112">Provides a description of the cube, which may be exposed in client applications.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="ac5e0-113">Содержит настраиваемые параметры обработки ошибок, которые относятся к обработке ситуаций с повторяющимися и неизвестными ключами, действиями при обнаружении ошибок и их предельному числу, файлам журналов ошибок и обработки ключей NULL.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-113">Contains configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`EstimatedRows`|<span data-ttu-id="ac5e0-114">Указывает предполагаемое количество строк в кубе.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-114">Specifies the number of estimated rows in the cube.</span></span>|  
|`ID`|<span data-ttu-id="ac5e0-115">Содержит уникальный идентификатор куба.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-115">Contains the unique identifier (ID) of the cube.</span></span>|  
|`Language`|<span data-ttu-id="ac5e0-116">Указывает идентификатор языка куба по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-116">Specifies the default language identifier of the cube.</span></span>|  
|`Name`|<span data-ttu-id="ac5e0-117">Указывает понятное имя куба.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-117">Specifies the user-friendly name of the cube.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="ac5e0-118">Определяет настройки упреждающего кэша для куба.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-118">Defines proactive cache settings for the cube.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="ac5e0-119">Показывает, следует ли производить индексирование и статистическую обработку во время обработки или после нее.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-119">Indicates whether indexing and aggregating should occur during or after processing.</span></span> <span data-ttu-id="ac5e0-120">Параметры являются **обычными** или `lazy` .</span><span class="sxs-lookup"><span data-stu-id="ac5e0-120">Options are **regular** or `lazy`.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="ac5e0-121">Определяет приоритет обработки куба во время фоновых операций, например отложенных статистических вычислений или индексирования.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-121">Determines the processing priority of the cube during background operations, such as lazy aggregations and indexing.</span></span> <span data-ttu-id="ac5e0-122">Значение по умолчанию — **0**.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-122">The default value is **0**.</span></span>|  
|`ScriptCacheProcessingMode`|<span data-ttu-id="ac5e0-123">Определяет, когда должен создаваться кэш скрипта: во время обработки или после нее.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-123">Indicates whether the script cache should be built during or after processing.</span></span> <span data-ttu-id="ac5e0-124">Параметры являются **обычными** и `lazy` .</span><span class="sxs-lookup"><span data-stu-id="ac5e0-124">Options are **regular** and `lazy`.</span></span>|  
|`ScriptErrorHandlingMode`|<span data-ttu-id="ac5e0-125">Определяет обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-125">Determines error handling.</span></span> <span data-ttu-id="ac5e0-126">Может принимать значение `IgnoreNone` или `IgnoreAll`.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-126">Options are `IgnoreNone` or `IgnoreAll`</span></span>|  
|`Source`|<span data-ttu-id="ac5e0-127">Отображает представление источника данных, используемое для куба.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-127">Displays the data source view used for the cube.</span></span>|  
|`StorageLocation`|<span data-ttu-id="ac5e0-128">Указывает для куба место хранения в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-128">Specifies the file system storage location for the cube.</span></span> <span data-ttu-id="ac5e0-129">Если не задано иное, то место хранения наследуется из базы данных, содержащей объект куба.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-129">If none is specified, the location is inherited from the database that contains the cube object.</span></span>|  
|`StorageMode`|<span data-ttu-id="ac5e0-130">Указывает для куба режим хранения.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-130">Specifies the storage mode for the cube.</span></span> <span data-ttu-id="ac5e0-131">Значения: `MOLAP` , `ROLAP` или`HOLAP``.`</span><span class="sxs-lookup"><span data-stu-id="ac5e0-131">Values are `MOLAP`, `ROLAP`, or `HOLAP``.`</span></span>|  
|`Visible`|<span data-ttu-id="ac5e0-132">Определяет, отображается куб или скрыт.</span><span class="sxs-lookup"><span data-stu-id="ac5e0-132">Determines the visibility of the cube.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="ac5e0-133">Дополнительные сведения о задании значений для свойства ErrorConfiguration при работе со значениями NULL и другими проблемами целостности данных см. [в разделе Обработка проблем целостности данных в Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="ac5e0-133">For more information about setting values for the ErrorConfiguration property when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5e0-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac5e0-134">See Also</span></span>  
 [<span data-ttu-id="ac5e0-135">Упреждающее кэширование &#40;секций&#41;</span><span class="sxs-lookup"><span data-stu-id="ac5e0-135">Proactive Caching &#40;Partitions&#41;</span></span>](partitions-proactive-caching.md)  
  
  
