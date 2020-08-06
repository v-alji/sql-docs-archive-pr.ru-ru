---
title: Элемент KeepExisting (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- KeepExisting element
ms.assetid: e67aae61-d06d-4a03-85ba-6516c3502dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: cde9b3091b75f55e4b9c79137853fbd7d4e0daf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734797"
---
# <a name="keepexisting-element-dta"></a><span data-ttu-id="b2a65-102">Элемент KeepExisting (DTA)</span><span class="sxs-lookup"><span data-stu-id="b2a65-102">KeepExisting Element (DTA)</span></span>
  <span data-ttu-id="b2a65-103">Задает структуры физического проектирования (индексы, индексированные представления или секции), по которым помощник по настройке ядра СУБД должен формировать свои рекомендации.</span><span class="sxs-lookup"><span data-stu-id="b2a65-103">Specifies the physical design structures (indexes, indexed views, or partitioning) that Database Engine Tuning Advisor must retain when generating its recommendation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2a65-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <KeepExisting>...</KeepExisting>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="b2a65-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="b2a65-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="b2a65-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="b2a65-106">Characteristic</span></span>|<span data-ttu-id="b2a65-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b2a65-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b2a65-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="b2a65-108">**Data type and length**</span></span>|<span data-ttu-id="b2a65-109">`string`, ограничение длины определяется сервером.</span><span class="sxs-lookup"><span data-stu-id="b2a65-109">`string`, length limit enforced by the server.</span></span>|  
|<span data-ttu-id="b2a65-110">**Допустимые значения**</span><span class="sxs-lookup"><span data-stu-id="b2a65-110">**Allowed values**</span></span>|<span data-ttu-id="b2a65-111">**NONE**</span><span class="sxs-lookup"><span data-stu-id="b2a65-111">**NONE**</span></span><br /> <span data-ttu-id="b2a65-112">Существующих структур нет.</span><span class="sxs-lookup"><span data-stu-id="b2a65-112">No existing structures.</span></span><br /><br /> <span data-ttu-id="b2a65-113">**ALL**</span><span class="sxs-lookup"><span data-stu-id="b2a65-113">**ALL**</span></span><br /> <span data-ttu-id="b2a65-114">Все существующие структуры.</span><span class="sxs-lookup"><span data-stu-id="b2a65-114">All existing structures.</span></span><br /><br /> <span data-ttu-id="b2a65-115">**ALIGNED**</span><span class="sxs-lookup"><span data-stu-id="b2a65-115">**ALIGNED**</span></span><br /> <span data-ttu-id="b2a65-116">Все структуры, выровненные по секциям.</span><span class="sxs-lookup"><span data-stu-id="b2a65-116">All partition-aligned structures.</span></span><br /><br /> <span data-ttu-id="b2a65-117">**CL_IDX**</span><span class="sxs-lookup"><span data-stu-id="b2a65-117">**CL_IDX**</span></span><br /> <span data-ttu-id="b2a65-118">Все кластеризованные индексы по таблицам.</span><span class="sxs-lookup"><span data-stu-id="b2a65-118">All clustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="b2a65-119">**IDX**</span><span class="sxs-lookup"><span data-stu-id="b2a65-119">**IDX**</span></span><br /> <span data-ttu-id="b2a65-120">Все кластеризованные и некластеризованные индексы по таблицам.</span><span class="sxs-lookup"><span data-stu-id="b2a65-120">All clustered and nonclustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="b2a65-121">С этим элементом следует использовать только одно из данных значений.</span><span class="sxs-lookup"><span data-stu-id="b2a65-121">Use only one of these values with this element.</span></span>|  
|<span data-ttu-id="b2a65-122">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="b2a65-122">**Default value**</span></span>|<span data-ttu-id="b2a65-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="b2a65-123">None.</span></span>|  
|<span data-ttu-id="b2a65-124">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="b2a65-124">**Occurrence**</span></span>|<span data-ttu-id="b2a65-125">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b2a65-125">Optional.</span></span> <span data-ttu-id="b2a65-126">Может использоваться только один раз для каждого элемента `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="b2a65-126">Can use only once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b2a65-127">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="b2a65-127">Element Relationships</span></span>  
  
|<span data-ttu-id="b2a65-128">Связь</span><span class="sxs-lookup"><span data-stu-id="b2a65-128">Relationship</span></span>|<span data-ttu-id="b2a65-129">Элементы</span><span class="sxs-lookup"><span data-stu-id="b2a65-129">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b2a65-130">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="b2a65-130">**Parent element**</span></span>|[<span data-ttu-id="b2a65-131">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="b2a65-131">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="b2a65-132">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="b2a65-132">**Child elements**</span></span>|<span data-ttu-id="b2a65-133">Нет.</span><span class="sxs-lookup"><span data-stu-id="b2a65-133">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2a65-134">Пример</span><span class="sxs-lookup"><span data-stu-id="b2a65-134">Example</span></span>  
 <span data-ttu-id="b2a65-135">Пример использования этого элемента см. в разделе [Образец простого входного файла XML (DTA)](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="b2a65-135">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a65-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2a65-136">See Also</span></span>  
 [<span data-ttu-id="b2a65-137">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="b2a65-137">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
