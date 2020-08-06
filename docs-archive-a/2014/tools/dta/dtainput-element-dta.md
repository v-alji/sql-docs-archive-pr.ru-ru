---
title: Элемент DTAInput (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAInput element
ms.assetid: 40c19abf-ded5-43de-be96-5b43b1b81b03
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7d2ff380a4ae1595e50aae472efc5fb4ac72efe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728997"
---
# <a name="dtainput-element-dta"></a><span data-ttu-id="7a1f3-102">Элемент DTAInput (DTA)</span><span class="sxs-lookup"><span data-stu-id="7a1f3-102">DTAInput Element (DTA)</span></span>
  <span data-ttu-id="7a1f3-103">Содержит определение входных XML-данных для помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="7a1f3-103">Contains the definition of XML input for Database Engine Tuning Advisor.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a1f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a1f3-104">Syntax</span></span>  
  
```  
  
<DTAXML>  
    <DTAInput>  
    ...code removed here...  
    </DTAInput>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="7a1f3-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="7a1f3-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="7a1f3-106">Характеристики</span><span class="sxs-lookup"><span data-stu-id="7a1f3-106">Characteristics</span></span>|<span data-ttu-id="7a1f3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7a1f3-107">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="7a1f3-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="7a1f3-108">**Data type and length**</span></span>|<span data-ttu-id="7a1f3-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="7a1f3-109">None.</span></span>|  
|<span data-ttu-id="7a1f3-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="7a1f3-110">**Default value**</span></span>|<span data-ttu-id="7a1f3-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="7a1f3-111">None.</span></span>|  
|<span data-ttu-id="7a1f3-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="7a1f3-112">**Occurrence**</span></span>|<span data-ttu-id="7a1f3-113">Может быть при необходимости указан один раз для каждого элемента **DTAXML** .</span><span class="sxs-lookup"><span data-stu-id="7a1f3-113">Optional once per **DTAXML** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7a1f3-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="7a1f3-114">Element Relationships</span></span>  
  
|<span data-ttu-id="7a1f3-115">Связь</span><span class="sxs-lookup"><span data-stu-id="7a1f3-115">Relationship</span></span>|<span data-ttu-id="7a1f3-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="7a1f3-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7a1f3-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="7a1f3-117">**Parent element**</span></span>|[<span data-ttu-id="7a1f3-118">Элемент DTAXML (DTA)</span><span class="sxs-lookup"><span data-stu-id="7a1f3-118">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)|  
|<span data-ttu-id="7a1f3-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="7a1f3-119">**Child elements**</span></span>|[<span data-ttu-id="7a1f3-120">Элемент Server (DTA)</span><span class="sxs-lookup"><span data-stu-id="7a1f3-120">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="7a1f3-121">Элемент Workload (DTA)</span><span class="sxs-lookup"><span data-stu-id="7a1f3-121">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)<br /><br /> [<span data-ttu-id="7a1f3-122">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="7a1f3-122">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)<br /><br /> [<span data-ttu-id="7a1f3-123">Элемент Configuration (DTA)</span><span class="sxs-lookup"><span data-stu-id="7a1f3-123">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="7a1f3-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a1f3-124">Remarks</span></span>  
 <span data-ttu-id="7a1f3-125">Этот элемент является корневым в иерархии входной схемы помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="7a1f3-125">This element is the root of the Database Engine Tuning Advisor input schema hierarchy.</span></span> <span data-ttu-id="7a1f3-126">С помощью входных аргументов помощника по настройке ядра СУБД можно задавать серверы с подлежащими настройке базами данных, рабочие нагрузки, параметры настройки или пользовательскую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7a1f3-126">Input to Database Engine Tuning Advisor can be arguments that specify the servers whose databases you want to tune, workloads, tuning options, or a user-specified configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a1f3-127">Пример</span><span class="sxs-lookup"><span data-stu-id="7a1f3-127">Example</span></span>  
 <span data-ttu-id="7a1f3-128">Пример использования элемента **DTAInput** см. в разделе [Образец простого входного файла XML (DTA)](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="7a1f3-128">For a usage example of the **DTAInput** element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a1f3-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a1f3-129">See Also</span></span>  
 [<span data-ttu-id="7a1f3-130">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="7a1f3-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
