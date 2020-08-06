---
title: Элемент "список_компонентов" (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- FeatureSet element
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d36c28b24a56ef2dcdf69578fb7e8c196306a416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737286"
---
# <a name="featureset-element-dta"></a><span data-ttu-id="c5a13-102">Элемент FeatureSet (DTA)</span><span class="sxs-lookup"><span data-stu-id="c5a13-102">FeatureSet Element (DTA)</span></span>
  <span data-ttu-id="c5a13-103">Содержит структуры физического проектирования (индексы или индексированные представления), которые помощник по настройке ядра СУБД должен использовать во время анализа.</span><span class="sxs-lookup"><span data-stu-id="c5a13-103">Contains the physical design structures (indexes or indexed views) that you would like Database Engine Tuning Advisor to use during analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5a13-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5a13-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="c5a13-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="c5a13-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="c5a13-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="c5a13-106">Characteristic</span></span>|<span data-ttu-id="c5a13-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c5a13-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c5a13-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="c5a13-108">**Data type and length**</span></span>|<span data-ttu-id="c5a13-109">`string`, без ограничения длины</span><span class="sxs-lookup"><span data-stu-id="c5a13-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="c5a13-110">**Допустимые значения**</span><span class="sxs-lookup"><span data-stu-id="c5a13-110">**Allowed values**</span></span>|<span data-ttu-id="c5a13-111">**IDX_IV**</span><span class="sxs-lookup"><span data-stu-id="c5a13-111">**IDX_IV**</span></span><br /> <span data-ttu-id="c5a13-112">Индексы и индексированные представления.</span><span class="sxs-lookup"><span data-stu-id="c5a13-112">Indexes and indexed views.</span></span><br /><br /> <span data-ttu-id="c5a13-113">**IDX**</span><span class="sxs-lookup"><span data-stu-id="c5a13-113">**IDX**</span></span><br /> <span data-ttu-id="c5a13-114">Только индексы.</span><span class="sxs-lookup"><span data-stu-id="c5a13-114">Indexes only.</span></span><br /><br /> <span data-ttu-id="c5a13-115">**IV**</span><span class="sxs-lookup"><span data-stu-id="c5a13-115">**IV**</span></span><br /> <span data-ttu-id="c5a13-116">Только индексированные представления.</span><span class="sxs-lookup"><span data-stu-id="c5a13-116">Indexed views only.</span></span><br /><br /> <span data-ttu-id="c5a13-117">**NCL_IDX**</span><span class="sxs-lookup"><span data-stu-id="c5a13-117">**NCL_IDX**</span></span><br /> <span data-ttu-id="c5a13-118">Только некластеризованные индексы.</span><span class="sxs-lookup"><span data-stu-id="c5a13-118">Nonclustered indexes only.</span></span><br /><br /> <span data-ttu-id="c5a13-119">Используйте с данным элементом одно из этих значений.</span><span class="sxs-lookup"><span data-stu-id="c5a13-119">Use one of these values with this element.</span></span>|  
|<span data-ttu-id="c5a13-120">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="c5a13-120">**Default value**</span></span>|<span data-ttu-id="c5a13-121">**IDX**</span><span class="sxs-lookup"><span data-stu-id="c5a13-121">**IDX**</span></span>|  
|<span data-ttu-id="c5a13-122">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="c5a13-122">**Occurrence**</span></span>|<span data-ttu-id="c5a13-123">Требуется для каждого элемента `TuningOptions`, если не используется элемент `DropOnlyMode`.</span><span class="sxs-lookup"><span data-stu-id="c5a13-123">Required once for each `TuningOptions` element, unless the `DropOnlyMode` element is used.</span></span> <span data-ttu-id="c5a13-124">Если используется элемент `DropOnlyMode`, элемент `FeatureSet` нельзя использовать.</span><span class="sxs-lookup"><span data-stu-id="c5a13-124">If `DropOnlyMode` is used, you cannot use `FeatureSet`.</span></span> <span data-ttu-id="c5a13-125">Эти элементы являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="c5a13-125">These elements are mutually exclusive.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c5a13-126">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="c5a13-126">Element Relationships</span></span>  
  
|<span data-ttu-id="c5a13-127">Связь</span><span class="sxs-lookup"><span data-stu-id="c5a13-127">Relationship</span></span>|<span data-ttu-id="c5a13-128">Элементы</span><span class="sxs-lookup"><span data-stu-id="c5a13-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c5a13-129">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="c5a13-129">**Parent element**</span></span>|[<span data-ttu-id="c5a13-130">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="c5a13-130">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="c5a13-131">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="c5a13-131">**Child elements**</span></span>|<span data-ttu-id="c5a13-132">Нет.</span><span class="sxs-lookup"><span data-stu-id="c5a13-132">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c5a13-133">Пример</span><span class="sxs-lookup"><span data-stu-id="c5a13-133">Example</span></span>  
 <span data-ttu-id="c5a13-134">Пример использования этого элемента см. в разделе [Образец простого входного файла XML (DTA)](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="c5a13-134">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a13-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="c5a13-135">See Also</span></span>  
 [<span data-ttu-id="c5a13-136">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="c5a13-136">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
