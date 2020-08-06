---
title: Элемент StorageBoundInMB (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- StorageBoundInMB element
ms.assetid: a8374910-bf68-4edb-b464-53a3a705e7f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea49b0af981b8f8d96efb087033d8f1466364c76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735753"
---
# <a name="storageboundinmb-element-dta"></a><span data-ttu-id="c4602-102">Элемент StorageBoundInMB (DTA)</span><span class="sxs-lookup"><span data-stu-id="c4602-102">StorageBoundInMB Element (DTA)</span></span>
  <span data-ttu-id="c4602-103">Определяет максимальный размер в мегабайтах, который может быть использован в рекомендациях по настройке помощника по настройке ядра СУБД (для набора индексов и секционирования).</span><span class="sxs-lookup"><span data-stu-id="c4602-103">Specifies the maximum space in megabytes that can be consumed by the Database Engine Tuning Advisor tuning recommendation (index and partitioning set).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4602-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4602-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <StorageBoundInMB>...</ StorageBoundInMB >  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="c4602-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="c4602-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="c4602-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="c4602-106">Characteristic</span></span>|<span data-ttu-id="c4602-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c4602-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c4602-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="c4602-108">**Data type and length**</span></span>|<span data-ttu-id="c4602-109">`unsignedInt`, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="c4602-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="c4602-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="c4602-110">**Default value**</span></span>|<span data-ttu-id="c4602-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="c4602-111">None.</span></span>|  
|<span data-ttu-id="c4602-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="c4602-112">**Occurrence**</span></span>|<span data-ttu-id="c4602-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="c4602-113">Optional.</span></span> <span data-ttu-id="c4602-114">Может быть использован только один раз для элемента `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="c4602-114">Can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c4602-115">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="c4602-115">Element Relationships</span></span>  
  
|<span data-ttu-id="c4602-116">Связь</span><span class="sxs-lookup"><span data-stu-id="c4602-116">Relationship</span></span>|<span data-ttu-id="c4602-117">Элементы</span><span class="sxs-lookup"><span data-stu-id="c4602-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c4602-118">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="c4602-118">**Parent element**</span></span>|[<span data-ttu-id="c4602-119">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="c4602-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="c4602-120">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="c4602-120">**Child elements**</span></span>|<span data-ttu-id="c4602-121">None</span><span class="sxs-lookup"><span data-stu-id="c4602-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4602-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4602-122">Remarks</span></span>  
 <span data-ttu-id="c4602-123">При настройке нескольких баз данных учитываются рекомендации по пространству всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="c4602-123">When multiple databases are tuned, recommendations for all databases are considered for the space calculation.</span></span> <span data-ttu-id="c4602-124">По умолчанию помощник по настройке ядра СУБД принимает минимальный из следующих размеров хранилищ:</span><span class="sxs-lookup"><span data-stu-id="c4602-124">By default, Database Engine Tuning Advisor assumes the smaller of the following storage sizes:</span></span>  
  
-   <span data-ttu-id="c4602-125">в 3 раза больше текущего размера необработанных данных, включая общий размер кучи и кластеризованных индексов таблиц;</span><span class="sxs-lookup"><span data-stu-id="c4602-125">Three times the current raw data size, which includes the total size of heaps and clustered indexes on tables.</span></span>  
  
-   <span data-ttu-id="c4602-126">свободное место на всех присоединенных дисках плюс размер необработанных данных.</span><span class="sxs-lookup"><span data-stu-id="c4602-126">The free space on all attached disk drives plus the raw data size.</span></span>  
  
 <span data-ttu-id="c4602-127">В размере хранилища по умолчанию не учитываются некластеризованные индексы и индексированные представления.</span><span class="sxs-lookup"><span data-stu-id="c4602-127">The default storage size does not include nonclustered indexes and indexed views.</span></span>  
  
 <span data-ttu-id="c4602-128">Если значение, предусмотренное для элемента `StorageBoundInMB`, превышает реальное свободное место на диске, помощник по настройке ядра СУБД возвращает ошибку, но продолжает настройку.</span><span class="sxs-lookup"><span data-stu-id="c4602-128">If the value specified for the `StorageBoundInMB` element exceeds the actual disk space, Database Engine Tuning Advisor returns an error, but continues tuning.</span></span> <span data-ttu-id="c4602-129">После завершения настройки можно увеличить место на диске, чтобы реализовать рекомендацию.</span><span class="sxs-lookup"><span data-stu-id="c4602-129">After tuning is complete, you can add disk space if you decide to implement the recommendation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4602-130">Пример</span><span class="sxs-lookup"><span data-stu-id="c4602-130">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="c4602-131">Описание</span><span class="sxs-lookup"><span data-stu-id="c4602-131">Description</span></span>  
 <span data-ttu-id="c4602-132">В следующем примере кода показано, как установить предел в 1 500 мегабайт в качестве максимального места на диске, которое может быть занято согласно рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="c4602-132">The following code example shows how to set a limit of 1500 megabytes as the maximum disk space that a tuning recommendation can consume:</span></span>  
  
## <a name="code"></a><span data-ttu-id="c4602-133">Код</span><span class="sxs-lookup"><span data-stu-id="c4602-133">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <StorageBoundInMB>1500</StorageBoundInMB>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4602-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4602-134">See Also</span></span>  
 [<span data-ttu-id="c4602-135">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="c4602-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
