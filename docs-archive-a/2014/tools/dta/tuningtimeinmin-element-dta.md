---
title: Элемент TuningTimeInMin (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningTimeInMin element
ms.assetid: 4973d9ac-20fd-4ac3-bc9f-5d60e39fdb7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4dae3fe4e9ac3126f43ec017c34d2bc548fda6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735722"
---
# <a name="tuningtimeinmin-element-dta"></a><span data-ttu-id="970fb-102">Элемент TuningTimeInMin (DTA)</span><span class="sxs-lookup"><span data-stu-id="970fb-102">TuningTimeInMin Element (DTA)</span></span>
  <span data-ttu-id="970fb-103">Позволяет задать максимальную длительность сеанса настройки в минутах.</span><span class="sxs-lookup"><span data-stu-id="970fb-103">Specifies the maximum length of a tuning session in minutes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="970fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="970fb-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <TuningTimeInMin>...</TuningTimeInMin>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="970fb-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="970fb-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="970fb-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="970fb-106">Characteristic</span></span>|<span data-ttu-id="970fb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="970fb-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="970fb-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="970fb-108">**Data type and length**</span></span>|<span data-ttu-id="970fb-109">`unsignedInt`, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="970fb-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="970fb-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="970fb-110">**Default value**</span></span>|<span data-ttu-id="970fb-111">480 минут (8 часов)</span><span class="sxs-lookup"><span data-stu-id="970fb-111">480 minutes (8 hours).</span></span>|  
|<span data-ttu-id="970fb-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="970fb-112">**Occurrence**</span></span>|<span data-ttu-id="970fb-113">Требуется в случае, если не задано значение элемента `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="970fb-113">Required unless a value has been specified for the `NumberOfEvents` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="970fb-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="970fb-114">Element Relationships</span></span>  
  
|<span data-ttu-id="970fb-115">Связь</span><span class="sxs-lookup"><span data-stu-id="970fb-115">Relationship</span></span>|<span data-ttu-id="970fb-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="970fb-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="970fb-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="970fb-117">**Parent element**</span></span>|[<span data-ttu-id="970fb-118">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="970fb-118">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="970fb-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="970fb-119">**Child elements**</span></span>|<span data-ttu-id="970fb-120">None</span><span class="sxs-lookup"><span data-stu-id="970fb-120">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="970fb-121">Пример</span><span class="sxs-lookup"><span data-stu-id="970fb-121">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="970fb-122">Описание</span><span class="sxs-lookup"><span data-stu-id="970fb-122">Description</span></span>  
 <span data-ttu-id="970fb-123">В следующем примере кода показано, как установить максимальное время настройки — 12 часов:</span><span class="sxs-lookup"><span data-stu-id="970fb-123">The following code example shows how to set 12 hours as the maximum tuning time:</span></span>  
  
## <a name="code"></a><span data-ttu-id="970fb-124">Код</span><span class="sxs-lookup"><span data-stu-id="970fb-124">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <TuningTimeInMin>720</TuningTimeInMin>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="970fb-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="970fb-125">See Also</span></span>  
 [<span data-ttu-id="970fb-126">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="970fb-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
