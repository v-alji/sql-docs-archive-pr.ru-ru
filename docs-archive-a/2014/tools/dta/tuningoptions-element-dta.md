---
title: Элемент TuningOptions (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningOptions element
ms.assetid: 58a22ba1-8e03-411f-bd46-85e4540f217a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fab1c55c9d036424142b2692e8335ea65c22340
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735725"
---
# <a name="tuningoptions-element-dta"></a><span data-ttu-id="fc52a-102">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-102">TuningOptions Element (DTA)</span></span>
  <span data-ttu-id="fc52a-103">Содержит параметры конкретного сеанса настройки.</span><span class="sxs-lookup"><span data-stu-id="fc52a-103">Contains the tuning options for a specific tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc52a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc52a-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="fc52a-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="fc52a-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="fc52a-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="fc52a-106">Characteristic</span></span>|<span data-ttu-id="fc52a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fc52a-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fc52a-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="fc52a-108">**Data type and length**</span></span>|<span data-ttu-id="fc52a-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="fc52a-109">None.</span></span>|  
|<span data-ttu-id="fc52a-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="fc52a-110">**Default value**</span></span>|<span data-ttu-id="fc52a-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="fc52a-111">None.</span></span>|  
|<span data-ttu-id="fc52a-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="fc52a-112">**Occurrence**</span></span>|<span data-ttu-id="fc52a-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="fc52a-113">Optional.</span></span> <span data-ttu-id="fc52a-114">В случае использования может применяться только один раз для каждого элемента `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="fc52a-114">If used, can only be used once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="fc52a-115">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="fc52a-115">Element Relationships</span></span>  
  
|<span data-ttu-id="fc52a-116">Связь</span><span class="sxs-lookup"><span data-stu-id="fc52a-116">Relationship</span></span>|<span data-ttu-id="fc52a-117">Элементы</span><span class="sxs-lookup"><span data-stu-id="fc52a-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="fc52a-118">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="fc52a-118">**Parent element**</span></span>|[<span data-ttu-id="fc52a-119">Элемент DTAInput (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-119">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="fc52a-120">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="fc52a-120">**Child elements**</span></span>|<span data-ttu-id="fc52a-121">Элемент `ReportSet`.</span><span class="sxs-lookup"><span data-stu-id="fc52a-121">`ReportSet` element.</span></span> <span data-ttu-id="fc52a-122">Дополнительные сведения см. в статье [XML-схема помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="fc52a-122">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="fc52a-123">Элемент `TuningLogTable`.</span><span class="sxs-lookup"><span data-stu-id="fc52a-123">`TuningLogTable` element.</span></span> <span data-ttu-id="fc52a-124">Дополнительные сведения см. в статье [XML-схема помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="fc52a-124">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="fc52a-125">Элемент `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="fc52a-125">`NumberOfEvents` element.</span></span> <span data-ttu-id="fc52a-126">Дополнительные сведения см. в статье [XML-схема помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="fc52a-126">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> [<span data-ttu-id="fc52a-127">Элемент TuningTimeInMin (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-127">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)<br /><br /> [<span data-ttu-id="fc52a-128">Элемент StorageBoundInMB (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-128">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)<br /><br /> <span data-ttu-id="fc52a-129">Элемент `MaxKeyColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="fc52a-129">`MaxKeyColumnsInIndex` element.</span></span> <span data-ttu-id="fc52a-130">Дополнительные сведения см. в статье [XML-схема помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="fc52a-130">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="fc52a-131">Элемент `MaxColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="fc52a-131">`MaxColumnsInIndex` element.</span></span> <span data-ttu-id="fc52a-132">Дополнительные сведения см. в статье [XML-схема помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="fc52a-132">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="fc52a-133">Элемент `MinPercentageImprovement`.</span><span class="sxs-lookup"><span data-stu-id="fc52a-133">`MinPercentageImprovement` element.</span></span> <span data-ttu-id="fc52a-134">Дополнительные сведения см. в статье [XML-схема помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100)</span><span class="sxs-lookup"><span data-stu-id="fc52a-134">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100)</span></span><br /><br /> [<span data-ttu-id="fc52a-135">Элемент TestServer (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-135">TestServer Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="fc52a-136">Элемент FeatureSet (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-136">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="fc52a-137">Элемент Partitioning (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-137">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> [<span data-ttu-id="fc52a-138">Элемент DropOnlyMode (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-138">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)<br /><br /> [<span data-ttu-id="fc52a-139">Элемент KeepExisting (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-139">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)<br /><br /> [<span data-ttu-id="fc52a-140">Элемент OnlineIndexOperation (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-140">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)<br /><br /> [<span data-ttu-id="fc52a-141">Элемент DatabaseToConnect (DTA)</span><span class="sxs-lookup"><span data-stu-id="fc52a-141">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)<br /><br /> <span data-ttu-id="fc52a-142">Элемент `IgnoreConstantsInWorkload`.</span><span class="sxs-lookup"><span data-stu-id="fc52a-142">`IgnoreConstantsInWorkload` element.</span></span> <span data-ttu-id="fc52a-143">Дополнительные сведения см. в статье [XML-схема помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="fc52a-143">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="fc52a-144">Элемент `RetainShellDB`.</span><span class="sxs-lookup"><span data-stu-id="fc52a-144">`RetainShellDB` element.</span></span> <span data-ttu-id="fc52a-145">Дополнительные сведения см. в статье [XML-схема помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="fc52a-145">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc52a-146">Пример</span><span class="sxs-lookup"><span data-stu-id="fc52a-146">Example</span></span>  
 <span data-ttu-id="fc52a-147">Примеры `TuningOptions` элемента см. в разделе [XML input file samples &#40;dta&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="fc52a-147">For examples of the `TuningOptions` element, see the [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc52a-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc52a-148">See Also</span></span>  
 [<span data-ttu-id="fc52a-149">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="fc52a-149">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
