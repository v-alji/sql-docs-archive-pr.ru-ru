---
title: Элемент OnlineIndexOperation (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- OnlineIndexOperation element
ms.assetid: 7c5614cd-09aa-4a59-9591-347aa7d36473
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48943c1b31d7a0a24ae939050d44494476e50034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666316"
---
# <a name="onlineindexoperation-element-dta"></a><span data-ttu-id="3f078-102">Элемент OnlineIndexOperation (DTA)</span><span class="sxs-lookup"><span data-stu-id="3f078-102">OnlineIndexOperation Element (DTA)</span></span>
  <span data-ttu-id="3f078-103">Указывает, могут ли индексы, индексированные представления или секции, рекомендуемые помощником по настройке ядра СУБД, создаваться в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="3f078-103">Specifies whether the indexes, indexed views, or partitions that Database Engine Tuning Advisor recommends can be created online.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f078-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f078-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <OnlineIndexOperation>...</OnlineIndexOperation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="3f078-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="3f078-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="3f078-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="3f078-106">Characteristic</span></span>|<span data-ttu-id="3f078-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3f078-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3f078-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="3f078-108">**Data type and length**</span></span>|<span data-ttu-id="3f078-109">`string`, без ограничения длины</span><span class="sxs-lookup"><span data-stu-id="3f078-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="3f078-110">**Допустимые значения**</span><span class="sxs-lookup"><span data-stu-id="3f078-110">**Allowed values**</span></span>|<span data-ttu-id="3f078-111">**OFF**</span><span class="sxs-lookup"><span data-stu-id="3f078-111">**OFF**</span></span><br /> <span data-ttu-id="3f078-112">Рекомендованные структуры физического проектирования не могут быть созданы в оперативном режиме.</span><span class="sxs-lookup"><span data-stu-id="3f078-112">No recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="3f078-113">**ON**</span><span class="sxs-lookup"><span data-stu-id="3f078-113">**ON**</span></span><br /> <span data-ttu-id="3f078-114">Все рекомендованные структуры физического проектирования могут быть созданы в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="3f078-114">All recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="3f078-115">**MIXED**</span><span class="sxs-lookup"><span data-stu-id="3f078-115">**MIXED**</span></span><br /> <span data-ttu-id="3f078-116">Помощник по настройке ядра СУБД пытается рекомендовать структуры физического проектирования, которые могут быть созданы, по возможности, в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="3f078-116">Database Engine Tuning Advisor attempts to recommend physical design structures that can be created online when possible.</span></span><br /><br /> <span data-ttu-id="3f078-117">Используйте с данным элементом одно из этих значений.</span><span class="sxs-lookup"><span data-stu-id="3f078-117">Use one of these values with this element.</span></span> <span data-ttu-id="3f078-118">Если индексы создаются в режиме в сети, то к их определению объекта добавляется ключевое слово **ONLINE = ON** .</span><span class="sxs-lookup"><span data-stu-id="3f078-118">If indexes are created online, the keyword **ONLINE = ON** is appended to its object definition.</span></span>|  
|<span data-ttu-id="3f078-119">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="3f078-119">**Default value**</span></span>|<span data-ttu-id="3f078-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="3f078-120">None.</span></span>|  
|<span data-ttu-id="3f078-121">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="3f078-121">**Occurrence**</span></span>|<span data-ttu-id="3f078-122">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3f078-122">Optional.</span></span> <span data-ttu-id="3f078-123">В случае использования может быть использован один раз для элемента `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="3f078-123">If used, can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3f078-124">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="3f078-124">Element Relationships</span></span>  
  
|<span data-ttu-id="3f078-125">Связь</span><span class="sxs-lookup"><span data-stu-id="3f078-125">Relationship</span></span>|<span data-ttu-id="3f078-126">Элементы</span><span class="sxs-lookup"><span data-stu-id="3f078-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3f078-127">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="3f078-127">**Parent element**</span></span>|[<span data-ttu-id="3f078-128">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="3f078-128">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="3f078-129">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="3f078-129">**Child elements**</span></span>|<span data-ttu-id="3f078-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="3f078-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3f078-131">Пример</span><span class="sxs-lookup"><span data-stu-id="3f078-131">Example</span></span>  
 <span data-ttu-id="3f078-132">Пример использования этого элемента см. в разделе [Образец простого входного файла XML (DTA)](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3f078-132">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f078-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f078-133">See Also</span></span>  
 [<span data-ttu-id="3f078-134">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="3f078-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
