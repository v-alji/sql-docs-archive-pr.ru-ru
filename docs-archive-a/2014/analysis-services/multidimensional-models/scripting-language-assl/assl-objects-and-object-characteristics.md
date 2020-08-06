---
title: Объекты и характеристики объектов ASSL | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- reference exceptions [Analysis Services Scripting Language]
- ASSL, objects
- inheritance [Analysis Services Scripting Language]
- localized names [Analysis Services Scripting Language]
- objects [Analysis Services Scripting Language]
- names [Analysis Services Scripting Language]
- Analysis Services Scripting Language, objects
- expansion [Analysis Services Scripting Language]
ms.assetid: 6e5c28b5-c0bc-4ccd-82e5-e174bbb71386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d57bb421a7f486983476a6549a5121ce88ee9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666242"
---
# <a name="assl-objects-and-object-characteristics"></a><span data-ttu-id="d5d30-102">Объекты ASSL и характеристики объектов</span><span class="sxs-lookup"><span data-stu-id="d5d30-102">ASSL Objects and Object Characteristics</span></span>
  <span data-ttu-id="d5d30-103">В языке ASSL объекты следуют специальным рекомендациям в отношении групп объектов, наследования, именования, расширения и обработки.</span><span class="sxs-lookup"><span data-stu-id="d5d30-103">Objects in Analysis Services Scripting Language (ASSL) follow specific guidelines in regards to object groups, inheritance, naming, expansion, and processing.</span></span>  
  
## <a name="object-groups"></a><span data-ttu-id="d5d30-104">Группы объектов</span><span class="sxs-lookup"><span data-stu-id="d5d30-104">Object Groups</span></span>  
 <span data-ttu-id="d5d30-105">Все [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] объекты имеют XML-представление.</span><span class="sxs-lookup"><span data-stu-id="d5d30-105">All [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objects have an XML representation.</span></span> <span data-ttu-id="d5d30-106">Объекты разделены на две группы.</span><span class="sxs-lookup"><span data-stu-id="d5d30-106">The objects are divided into two groups:</span></span>  
  
 <span data-ttu-id="d5d30-107">**Основные объекты**</span><span class="sxs-lookup"><span data-stu-id="d5d30-107">**Major objects**</span></span>  
 <span data-ttu-id="d5d30-108">Основные объекты можно создавать, изменять и удалять независимо.</span><span class="sxs-lookup"><span data-stu-id="d5d30-108">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="d5d30-109">К основным объектам относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="d5d30-109">Major objects include:</span></span>  
  
-   <span data-ttu-id="d5d30-110">Серверы</span><span class="sxs-lookup"><span data-stu-id="d5d30-110">Servers</span></span>  
  
-   <span data-ttu-id="d5d30-111">Базы данных</span><span class="sxs-lookup"><span data-stu-id="d5d30-111">Databases</span></span>  
  
-   <span data-ttu-id="d5d30-112">Измерения</span><span class="sxs-lookup"><span data-stu-id="d5d30-112">Dimensions</span></span>  
  
-   <span data-ttu-id="d5d30-113">Кубы</span><span class="sxs-lookup"><span data-stu-id="d5d30-113">Cubes</span></span>  
  
-   <span data-ttu-id="d5d30-114">Группы мер</span><span class="sxs-lookup"><span data-stu-id="d5d30-114">Measure groups</span></span>  
  
-   <span data-ttu-id="d5d30-115">Секции</span><span class="sxs-lookup"><span data-stu-id="d5d30-115">Partitions</span></span>  
  
-   <span data-ttu-id="d5d30-116">Перспективы</span><span class="sxs-lookup"><span data-stu-id="d5d30-116">Perspectives</span></span>  
  
-   <span data-ttu-id="d5d30-117">Модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="d5d30-117">Mining models</span></span>  
  
-   <span data-ttu-id="d5d30-118">Роли</span><span class="sxs-lookup"><span data-stu-id="d5d30-118">Roles</span></span>  
  
-   <span data-ttu-id="d5d30-119">Команды, связанные с сервером или базой данных</span><span class="sxs-lookup"><span data-stu-id="d5d30-119">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="d5d30-120">Источники данных</span><span class="sxs-lookup"><span data-stu-id="d5d30-120">Data sources</span></span>  
  
 <span data-ttu-id="d5d30-121">Для отслеживания истории и состояния у основных объектов предусмотрены следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="d5d30-121">Major objects have the following properties to track their history and status.</span></span>  
  
-   `CreatedTimestamp`  
  
-   `LastSchemaUpdate`  
  
-   <span data-ttu-id="d5d30-122">`LastProcessed` (когда это целесообразно)</span><span class="sxs-lookup"><span data-stu-id="d5d30-122">`LastProcessed` (where appropriate)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5d30-123">Отнесение объекта к основным влияет на то, как этот объект рассматривается в экземпляре служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], а также на то, как он обрабатывается в языке определения объектов.</span><span class="sxs-lookup"><span data-stu-id="d5d30-123">The classification of an object as a major object affects how an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] treats that object and how that object is handled in the object definition language.</span></span> <span data-ttu-id="d5d30-124">Однако такая классификация не гарантирует, что средства управления и разработки служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] разрешат независимое создание, изменение или удаление этих объектов.</span><span class="sxs-lookup"><span data-stu-id="d5d30-124">However, this classification does not guarantee that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] management and development tools will allow the independent creation, modification, or deletion of these objects.</span></span>  
  
 <span data-ttu-id="d5d30-125">**Второстепенные объекты**</span><span class="sxs-lookup"><span data-stu-id="d5d30-125">**Minor objects**</span></span>  
 <span data-ttu-id="d5d30-126">Создавать, изменять или удалять второстепенные объекты можно только в рамках создания, изменения или удаления родительского основного объекта.</span><span class="sxs-lookup"><span data-stu-id="d5d30-126">Minor objects can only be created, altered, or deleted as part of creating, altering, or deleting the parent major object.</span></span> <span data-ttu-id="d5d30-127">К второстепенным объектам относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="d5d30-127">Minor objects include:</span></span>  
  
-   <span data-ttu-id="d5d30-128">Иерархии и уровни</span><span class="sxs-lookup"><span data-stu-id="d5d30-128">Hierarchies and levels</span></span>  
  
-   <span data-ttu-id="d5d30-129">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5d30-129">Attributes</span></span>  
  
-   <span data-ttu-id="d5d30-130">Меры</span><span class="sxs-lookup"><span data-stu-id="d5d30-130">Measures</span></span>  
  
-   <span data-ttu-id="d5d30-131">Столбцы модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="d5d30-131">Mining model columns</span></span>  
  
-   <span data-ttu-id="d5d30-132">Команды, связанные с кубом</span><span class="sxs-lookup"><span data-stu-id="d5d30-132">Commands associated with a cube</span></span>  
  
-   <span data-ttu-id="d5d30-133">Агрегации</span><span class="sxs-lookup"><span data-stu-id="d5d30-133">Aggregations</span></span>  
  
## <a name="object-expansion"></a><span data-ttu-id="d5d30-134">Раскрытие объектов</span><span class="sxs-lookup"><span data-stu-id="d5d30-134">Object Expansion</span></span>  
 <span data-ttu-id="d5d30-135">Ограничение `ObjectExpansion` используется для управления степенью раскрытия кода XML на языке ASSL, возвращаемого сервером.</span><span class="sxs-lookup"><span data-stu-id="d5d30-135">The `ObjectExpansion` restriction can be used to control the degree of expansion of ASSL XML returned by the server.</span></span> <span data-ttu-id="d5d30-136">Параметры этого ограничения приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d5d30-136">This restriction has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d5d30-137">Значение перечисления</span><span class="sxs-lookup"><span data-stu-id="d5d30-137">Enumeration value</span></span>|<span data-ttu-id="d5d30-138">Разрешено для\<Alter></span><span class="sxs-lookup"><span data-stu-id="d5d30-138">Allowed for \<Alter></span></span>|<span data-ttu-id="d5d30-139">Описание</span><span class="sxs-lookup"><span data-stu-id="d5d30-139">Description</span></span>|  
|-----------------------|---------------------------|-----------------|  
|<span data-ttu-id="d5d30-140">*референцеонли*</span><span class="sxs-lookup"><span data-stu-id="d5d30-140">*ReferenceOnly*</span></span>|<span data-ttu-id="d5d30-141">Нет</span><span class="sxs-lookup"><span data-stu-id="d5d30-141">no</span></span>|<span data-ttu-id="d5d30-142">Возвращает только имя, идентификатор и отметку времени для запрошенного объекта, а также рекурсивно для всех содержащихся в нем основных объектов.</span><span class="sxs-lookup"><span data-stu-id="d5d30-142">Returns only the name, ID, and timestamp for the requested object and for all contained major objects recursively.</span></span>|  
|<span data-ttu-id="d5d30-143">*ObjectProperties*</span><span class="sxs-lookup"><span data-stu-id="d5d30-143">*ObjectProperties*</span></span>|<span data-ttu-id="d5d30-144">да</span><span class="sxs-lookup"><span data-stu-id="d5d30-144">yes</span></span>|<span data-ttu-id="d5d30-145">Раскрывает запрошенные объект и содержащиеся в нем второстепенные объекты, но не возвращает содержащиеся в нем основные объекты.</span><span class="sxs-lookup"><span data-stu-id="d5d30-145">Expands the requested object and minor contained objects, but does not return major contained objects.</span></span>|  
|<span data-ttu-id="d5d30-146">*експандобжект*</span><span class="sxs-lookup"><span data-stu-id="d5d30-146">*ExpandObject*</span></span>|<span data-ttu-id="d5d30-147">Нет</span><span class="sxs-lookup"><span data-stu-id="d5d30-147">no</span></span>|<span data-ttu-id="d5d30-148">Аналогичен параметру *ObjectProperties*, но также возвращает имя, идентификатор и отметку времени для вложенных основных объектов.</span><span class="sxs-lookup"><span data-stu-id="d5d30-148">Same as *ObjectProperties*, but also returns the name, ID, and timestamp for contained major objects.</span></span>|  
|<span data-ttu-id="d5d30-149">*ExpandFull*</span><span class="sxs-lookup"><span data-stu-id="d5d30-149">*ExpandFull*</span></span>|<span data-ttu-id="d5d30-150">да</span><span class="sxs-lookup"><span data-stu-id="d5d30-150">yes</span></span>|<span data-ttu-id="d5d30-151">Полностью раскрывает запрошенный объект и, рекурсивно, все содержащиеся в нем объекты.</span><span class="sxs-lookup"><span data-stu-id="d5d30-151">Fully expands the requested object and all contained objects recursively.</span></span>|  
  
 <span data-ttu-id="d5d30-152">В этом справочном разделе по ASSL описывается представление *ExpandFull* .</span><span class="sxs-lookup"><span data-stu-id="d5d30-152">This ASSL reference section describes the *ExpandFull* representation.</span></span> <span data-ttu-id="d5d30-153">Все остальные уровни `ObjectExpansion` являются производными от этого уровня.</span><span class="sxs-lookup"><span data-stu-id="d5d30-153">All other `ObjectExpansion` levels are derived from this level.</span></span>  
  
## <a name="object-processing"></a><span data-ttu-id="d5d30-154">Обработка объектов</span><span class="sxs-lookup"><span data-stu-id="d5d30-154">Object Processing</span></span>  
 <span data-ttu-id="d5d30-155">В языке ASSL есть элементы и свойства, доступные только для чтения (например, `LastProcessed`), которые можно считывать из экземпляра служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], но которые пропускаются при подаче в экземпляр командных скриптов.</span><span class="sxs-lookup"><span data-stu-id="d5d30-155">ASSL includes read-only elements or properties (for example, `LastProcessed`) that can be read from the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance, but which are omitted when command scripts are submitted to the instance.</span></span> <span data-ttu-id="d5d30-156">Службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] не учитывают измененные значения для элементов, которые доступны только для чтения, не выдавая при этом предупреждений или сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d5d30-156">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ignores modified values for read-only elements without warning or error.</span></span>  
  
 <span data-ttu-id="d5d30-157">Службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] также пропускают несоответствующие свойства, не формируя при этом ошибок проверки правильности.</span><span class="sxs-lookup"><span data-stu-id="d5d30-157">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] also ignores inappropriate or irrelevant properties without raising validation errors.</span></span> <span data-ttu-id="d5d30-158">Например, допустим, что элемент Х должен присутствовать, только если элемент Y имеет определенное значение.</span><span class="sxs-lookup"><span data-stu-id="d5d30-158">For example, the X element should only be present when the Y element has a particular value.</span></span> <span data-ttu-id="d5d30-159">Экземпляр служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] не учитывает элемент X вместо проверки правильности этого элемента по значению элемента Y.</span><span class="sxs-lookup"><span data-stu-id="d5d30-159">The [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance ignores the X element instead of validating that element against the value of the Y element.</span></span>  
  
  
