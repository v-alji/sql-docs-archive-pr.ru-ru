---
title: Свойства измерения базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- metadata [Analysis Services]
- dimensions [Analysis Services], characteristics
- properties [Analysis Services], dimensions
ms.assetid: 075548ef-08a3-413c-8ee0-4a074c276fcc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 504e190f4c513a8c999c4d7d7ab9eaabb83298c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666249"
---
# <a name="database-dimension-properties"></a><span data-ttu-id="1d3c5-102">Свойства измерений базы данных</span><span class="sxs-lookup"><span data-stu-id="1d3c5-102">Database Dimension Properties</span></span>
  <span data-ttu-id="1d3c5-103">В службах [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] характеристики измерения определяются метаданными для измерения, основанными на параметрах различных свойств измерения, а также в атрибутах или иерархиях, содержащихся в измерении.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the characteristics of a dimension are defined by the metadata for the dimension, based on the settings of various dimension properties, and on the attributes or hierarchies that are contained by the dimension.</span></span> <span data-ttu-id="1d3c5-104">Следующая таблица содержит описания свойств измерений служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d3c5-104">The following table describes the dimension properties in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="1d3c5-105">Свойство</span><span class="sxs-lookup"><span data-stu-id="1d3c5-105">Property</span></span>|<span data-ttu-id="1d3c5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1d3c5-106">Description</span></span>|  
|--------------|-----------------|  
|`AttributeAllMemberName`|<span data-ttu-id="1d3c5-107">Задает имя элемента «Все» для атрибутов измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-107">Specifies the name of the All member for attributes in a dimension.</span></span>|  
|`Collation`|<span data-ttu-id="1d3c5-108">Задает параметры сортировки, применяемые в измерении.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-108">Determines the collation used by the dimension.</span></span>|  
|`CurrentStorageMode`|<span data-ttu-id="1d3c5-109">Содержит текущий режим хранения для измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-109">Contains the current storage mode for the dimension.</span></span>|  
|`DependsOnDimension`|<span data-ttu-id="1d3c5-110">Содержит идентификатор другого измерения, от которого зависит данное (если такое имеется).</span><span class="sxs-lookup"><span data-stu-id="1d3c5-110">Contains the ID of another dimension on which the dimension depends, if any.</span></span>|  
|`Description`|<span data-ttu-id="1d3c5-111">Содержит описание измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-111">Contains the description of the dimension.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="1d3c5-112">Настраиваемые параметры обработки ошибок для обработки ситуаций с повторяющимися ключами, неизвестными ключами, предельными значениями ошибок, действиями при обнаружении ошибки, файлом журнала ошибок и ключами со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-112">Configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`ID`|<span data-ttu-id="1d3c5-113">Содержит уникальный идентификатор измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-113">Contains the unique identifier (ID) of the dimension.</span></span>|  
|`Language`|<span data-ttu-id="1d3c5-114">Задает язык по умолчанию для измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-114">Specifies the default language for the dimension.</span></span>|  
|`MdxMissingMemberMode`|<span data-ttu-id="1d3c5-115">Определяет, как обрабатываются пропущенные элементы для инструкций многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-115">Determines how missing members are handled for Multidimensional Expressions (MDX) statements.</span></span>|  
|`MiningModelID`|<span data-ttu-id="1d3c5-116">Содержит идентификатор модели интеллектуального анализа данных, с которой связано измерение интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-116">Contains the ID of the mining model with which the data mining dimension is associated.</span></span> <span data-ttu-id="1d3c5-117">Применяется, только если измерение является измерением модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-117">This property is applicable only if the dimension is a mining model dimension.</span></span>|  
|`Name`|<span data-ttu-id="1d3c5-118">Указывает имя измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-118">Specifies the name of the dimension.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="1d3c5-119">Определяет настройки упреждающего кэширования для измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-119">Defines the proactive cache settings for the dimension.</span></span>|  
|`ProcessingGroup`|<span data-ttu-id="1d3c5-120">Указывает группу обработки.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-120">Specifies the processing group.</span></span> <span data-ttu-id="1d3c5-121">Значения: ByAttribute и ByTable.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-121">Values are ByAttribute or ByTable.</span></span> <span data-ttu-id="1d3c5-122">По умолчанию — `ByAttribute`.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-122">Default is `ByAttribute`.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="1d3c5-123">Показывает, следует ли службам [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] производить индексирование и статистическую обработку во время работы или после нее.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-123">Indicates whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should index and aggregate during or after processing.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="1d3c5-124">Определяет приоритет обработки для измерения во время работы в фоновом режиме, например отложенная статистическая обработка, индексирование или кластеризация.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-124">Determines the processing priority of the dimension during background operations such as lazy aggregation, indexing, or clustering.</span></span>|  
|`Source`|<span data-ttu-id="1d3c5-125">Определяет представление источника данных, к которому привязано измерение.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-125">Identifies the data source view to which the dimension is bound.</span></span>|  
|`StorageMode`|<span data-ttu-id="1d3c5-126">Определяет режим хранения измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-126">Determines the storage mode for the dimension.</span></span>|  
|`Type`|<span data-ttu-id="1d3c5-127">Указывает тип измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-127">Specifies the type of the dimension.</span></span>|  
|`UnknownMember`|<span data-ttu-id="1d3c5-128">Показывает, видим ли неизвестный элемент.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-128">Indicates whether the unknown member is visible.</span></span>|  
|`UnknownMemberName`|<span data-ttu-id="1d3c5-129">Указывает заголовок (на языке по умолчанию для измерения) для неизвестного элемента измерения.</span><span class="sxs-lookup"><span data-stu-id="1d3c5-129">Specifies the caption, in the default language of the dimension, for the unknown member of the dimension.</span></span>|  
|`WriteEnabled`|<span data-ttu-id="1d3c5-130">Показывает, доступна ли обратная запись в измерение (зависит от прав доступа).</span><span class="sxs-lookup"><span data-stu-id="1d3c5-130">Indicates whether dimension writebacks are available (subject to security permissions).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="1d3c5-131">Дополнительные сведения о задании значений свойств ErrorConfiguration и UnknownMember при работе со значениями NULL и другими проблемами целостности данных см. в разделе [обработка проблем целостности данных в Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="1d3c5-131">For more information about setting values for the ErrorConfiguration and UnknownMember properties when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d3c5-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="1d3c5-132">See Also</span></span>  
 <span data-ttu-id="1d3c5-133">[Атрибуты и иерархии атрибутов](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="1d3c5-133">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="1d3c5-134">[Пользовательские иерархии](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="1d3c5-134">[User Hierarchies](user-hierarchies.md) </span></span>  
 <span data-ttu-id="1d3c5-135">[Связи измерений](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="1d3c5-135">[Dimension Relationships](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 [<span data-ttu-id="1d3c5-136">Измерения (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="1d3c5-136">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
