---
title: Элемент Configuration (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Configuration element
ms.assetid: 1478e56f-57c4-4441-bac9-1ac91453839b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d11938d9a9a694f994a3ea977022a393cbae23d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727678"
---
# <a name="configuration-element-dta"></a><span data-ttu-id="856bb-102">Элемент Configuration (DTA)</span><span class="sxs-lookup"><span data-stu-id="856bb-102">Configuration Element (DTA)</span></span>
  <span data-ttu-id="856bb-103">Задает определенную пользователем конфигурацию, состоящую из существующих и гипотетических структур физического проектирования и позволяющую помощнику по настройке ядра СУБД производить анализ при настройке рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="856bb-103">Specifies a user-specified configuration consisting of existing and hypothetical physical design structures for the Database Engine Tuning Advisor to analyze when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="856bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="856bb-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>...</Server>  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions  
    <Configuration [SpecificationMode="Relative" | "Absolute"]>  
    ...code removed here...  
    </Configuration>  
</DTAInput>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="856bb-105">Атрибуты элемента</span><span class="sxs-lookup"><span data-stu-id="856bb-105">Element Attributes</span></span>  
  
|<span data-ttu-id="856bb-106">Атрибут конфигурации</span><span class="sxs-lookup"><span data-stu-id="856bb-106">Configuration Attribute</span></span>|<span data-ttu-id="856bb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="856bb-107">Description</span></span>|  
|-----------------------------|-----------------|  
|`SpecificationMode`|<span data-ttu-id="856bb-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="856bb-108">Optional.</span></span> <span data-ttu-id="856bb-109">Указывает, должен ли помощник по настройке ядра СУБД анализировать указанную конфигурацию как связь с текущей существующей конфигурацией либо как совершенно новую, отдельную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="856bb-109">Specifies whether Database Engine Tuning Advisor should analyze the specified configuration in relation to the current existing configuration, or as a completely new, standalone one.</span></span> <span data-ttu-id="856bb-110">Используйте тип данных **string** для указания этого атрибута при помощи следующих допустимых значений:</span><span class="sxs-lookup"><span data-stu-id="856bb-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="856bb-111">`Relative`:</span><span class="sxs-lookup"><span data-stu-id="856bb-111">`Relative`:</span></span> <br />                  <span data-ttu-id="856bb-112">Вычисляет указанную конфигурацию как связь с существующей конфигурацией структур физического проектирования (индексы, индексированные представления, секционирование) в настраиваемой базе данных.</span><span class="sxs-lookup"><span data-stu-id="856bb-112">Evaluates the specified configuration in relation to the current existing configuration of physical design structures (indexes, indexed views, partitioning) in the database that is being tuned.</span></span> <span data-ttu-id="856bb-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="856bb-113">For example:</span></span> <br />`<Configuration SpecificationMode="Relative">`<br /><br /> <span data-ttu-id="856bb-114">`Absolute`:</span><span class="sxs-lookup"><span data-stu-id="856bb-114">`Absolute`:</span></span> <br />                  <span data-ttu-id="856bb-115">Вычисляет указанную конфигурацию как самостоятельную.</span><span class="sxs-lookup"><span data-stu-id="856bb-115">Evaluates the specified configuration as a standalone configuration.</span></span> <span data-ttu-id="856bb-116">Если указано «Absolute», помощник по настройке ядра СУБД не учитывает существующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="856bb-116">When Absolute is specified, Database Engine Tuning Advisor does not consider the existing configuration.</span></span> <span data-ttu-id="856bb-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="856bb-117">For example:</span></span><br />`<Configuration SpecificationMode="Absolute">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="856bb-118">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="856bb-118">Element Characteristics</span></span>  
  
|<span data-ttu-id="856bb-119">Характеристика</span><span class="sxs-lookup"><span data-stu-id="856bb-119">Characteristic</span></span>|<span data-ttu-id="856bb-120">Описание</span><span class="sxs-lookup"><span data-stu-id="856bb-120">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="856bb-121">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="856bb-121">**Data type and length**</span></span>|<span data-ttu-id="856bb-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="856bb-122">None.</span></span>|  
|<span data-ttu-id="856bb-123">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="856bb-123">**Default value**</span></span>|<span data-ttu-id="856bb-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="856bb-124">None.</span></span>|  
|<span data-ttu-id="856bb-125">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="856bb-125">**Occurrence**</span></span>|<span data-ttu-id="856bb-126">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="856bb-126">Optional.</span></span> <span data-ttu-id="856bb-127">Может использоваться один раз для каждого элемента `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="856bb-127">Can use once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="856bb-128">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="856bb-128">Element Relationships</span></span>  
  
|<span data-ttu-id="856bb-129">Связь</span><span class="sxs-lookup"><span data-stu-id="856bb-129">Relationship</span></span>|<span data-ttu-id="856bb-130">Элементы</span><span class="sxs-lookup"><span data-stu-id="856bb-130">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="856bb-131">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="856bb-131">**Parent element**</span></span>|[<span data-ttu-id="856bb-132">Элемент DTAInput (DTA)</span><span class="sxs-lookup"><span data-stu-id="856bb-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="856bb-133">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="856bb-133">**Child elements**</span></span>|[<span data-ttu-id="856bb-134">Элемент Server описания конфигурации (DTA)</span><span class="sxs-lookup"><span data-stu-id="856bb-134">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="856bb-135">Пример</span><span class="sxs-lookup"><span data-stu-id="856bb-135">Example</span></span>  
 <span data-ttu-id="856bb-136">Пример использования этого элемента см. в разделе [Образец входного XML-файла с пользовательской конфигурацией (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="856bb-136">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="856bb-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="856bb-137">See Also</span></span>  
 [<span data-ttu-id="856bb-138">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="856bb-138">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
