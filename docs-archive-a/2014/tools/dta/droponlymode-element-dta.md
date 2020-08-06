---
title: Элемент DropOnlyMode (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DropOnlyMode element
ms.assetid: 80960676-7581-4074-889b-80ee665963dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b274dc394a933308cf2161cc271d09b8391900c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727645"
---
# <a name="droponlymode-element-dta"></a><span data-ttu-id="c5b98-102">Элемент DropOnlyMode (DTA)</span><span class="sxs-lookup"><span data-stu-id="c5b98-102">DropOnlyMode Element (DTA)</span></span>
  <span data-ttu-id="c5b98-103">Указывает, что помощник по настройке ядра СУБД должен в ходе сеанса настройки учитывать только возможность удаления существующих индексов, индексированных представлений или секций.</span><span class="sxs-lookup"><span data-stu-id="c5b98-103">Specifies that Database Engine Tuning Advisor should only consider dropping existing indexes, indexed views, or partitions during the tuning session.</span></span> <span data-ttu-id="c5b98-104">При задании этого параметра настройки никакие новые структуры физического проектирования не рассматриваются.</span><span class="sxs-lookup"><span data-stu-id="c5b98-104">No new physical design structures are considered when this tuning option is specified.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b98-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5b98-105">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <DropOnlyMode>...</DropOnlyMode>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="c5b98-106">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="c5b98-106">Element Characteristics</span></span>  
  
|<span data-ttu-id="c5b98-107">Характеристика</span><span class="sxs-lookup"><span data-stu-id="c5b98-107">Characteristic</span></span>|<span data-ttu-id="c5b98-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c5b98-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c5b98-109">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="c5b98-109">**Data type and length**</span></span>|<span data-ttu-id="c5b98-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="c5b98-110">None.</span></span>|  
|<span data-ttu-id="c5b98-111">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="c5b98-111">**Default value**</span></span>|<span data-ttu-id="c5b98-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="c5b98-112">None.</span></span>|  
|<span data-ttu-id="c5b98-113">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="c5b98-113">**Occurrence**</span></span>|<span data-ttu-id="c5b98-114">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="c5b98-114">Optional.</span></span> <span data-ttu-id="c5b98-115">Может использоваться только один раз для каждого элемента `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="c5b98-115">Can use only once for each `TuningOptions` element.</span></span> <span data-ttu-id="c5b98-116">Не может использоваться, если в элементе `TuningOptions` указаны следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="c5b98-116">Cannot be used if the following elements are specified in the `TuningOptions` element:</span></span><br /><br /> [<span data-ttu-id="c5b98-117">Элемент FeatureSet (DTA)</span><span class="sxs-lookup"><span data-stu-id="c5b98-117">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="c5b98-118">Элемент Partitioning (DTA)</span><span class="sxs-lookup"><span data-stu-id="c5b98-118">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> <span data-ttu-id="c5b98-119">[Элемент KeepExisting (DTA)](keepexisting-element-dta.md) имеет значение **ВСЕ**</span><span class="sxs-lookup"><span data-stu-id="c5b98-119">[KeepExisting Element &#40;DTA&#41;](keepexisting-element-dta.md) is set to **ALL**</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c5b98-120">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="c5b98-120">Element Relationships</span></span>  
  
|<span data-ttu-id="c5b98-121">Связь</span><span class="sxs-lookup"><span data-stu-id="c5b98-121">Relationship</span></span>|<span data-ttu-id="c5b98-122">Элементы</span><span class="sxs-lookup"><span data-stu-id="c5b98-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c5b98-123">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="c5b98-123">**Parent element**</span></span>|[<span data-ttu-id="c5b98-124">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="c5b98-124">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="c5b98-125">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="c5b98-125">**Child elements**</span></span>|<span data-ttu-id="c5b98-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="c5b98-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c5b98-127">Пример</span><span class="sxs-lookup"><span data-stu-id="c5b98-127">Example</span></span>  
 <span data-ttu-id="c5b98-128">В приведенном ниже примере показан раздел `TuningOptions` входного XML-файла помощника по настройке ядра СУБД, в котором указано ключевое слово `DropOnlyMode`.</span><span class="sxs-lookup"><span data-stu-id="c5b98-128">The following example shows the `TuningOptions` section of a Database Engine Tuning Advisor XML input file where the `DropOnlyMode` is specified.</span></span> <span data-ttu-id="c5b98-129">В данном примере время настройки ограничено 24 часами (1 440 минутами), а для всех существующих кластеризованных и некластеризованных индексов будет рассматриваться возможность их удаления.</span><span class="sxs-lookup"><span data-stu-id="c5b98-129">In this example the tuning time is limited to 24 hours (1440 minutes) and all existing clustered and nonclustered indexes will be considered for dropping:</span></span>  
  
```xml  
<TuningOptions  
  <TuningTimeInMin>1440</Name>  
  <KeepExisting>ALIGNED</KeepExisting>  
  <DropOnlyMode />  
</TuningOptions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5b98-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="c5b98-130">See Also</span></span>  
 [<span data-ttu-id="c5b98-131">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="c5b98-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
