---
title: Элемент EventString (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- EventString element
ms.assetid: f76c37b4-2f6e-4274-8ee2-87e89d98e8a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 981cd0be06fd0972426fcb2fa67b0c4143cf9178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737316"
---
# <a name="eventstring-element-dta"></a><span data-ttu-id="150c7-102">Элемент EventString (DTA)</span><span class="sxs-lookup"><span data-stu-id="150c7-102">EventString Element (DTA)</span></span>
  <span data-ttu-id="150c7-103">Задает скрипт рабочей нагрузки [!INCLUDE[tsql](../../includes/tsql-md.md)] непосредственно во входном XML-файле.</span><span class="sxs-lookup"><span data-stu-id="150c7-103">Specifies a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload directly in the XML input file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="150c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="150c7-104">Syntax</span></span>  
  
```  
  
<Workload>  
    <EventString Weight="...">  
    ...code removed here...  
    </EventString>  
</Workload>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="150c7-105">Атрибуты элемента</span><span class="sxs-lookup"><span data-stu-id="150c7-105">Element Attributes</span></span>  
  
|<span data-ttu-id="150c7-106">attribute</span><span class="sxs-lookup"><span data-stu-id="150c7-106">Attribute</span></span>|<span data-ttu-id="150c7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="150c7-107">Description</span></span>|  
|---------------|-----------------|  
|`Weight`|<span data-ttu-id="150c7-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="150c7-108">Optional.</span></span> <span data-ttu-id="150c7-109">Задает весовой коэффициент запроса (коэффициент важности) для указанного события.</span><span class="sxs-lookup"><span data-stu-id="150c7-109">Specifies the query weight factor (a factor of importance) for the specified event.</span></span> <span data-ttu-id="150c7-110">Для указания весового коэффициента используется тип данных `float`.</span><span class="sxs-lookup"><span data-stu-id="150c7-110">Use a `float` data type to specify the weight.</span></span> <span data-ttu-id="150c7-111">Например, `Weight`="100,01".</span><span class="sxs-lookup"><span data-stu-id="150c7-111">For example, `Weight`="100.01".</span></span> <span data-ttu-id="150c7-112">Минимальное значение, которое можно задать для коэффициента `Weight`, равно 0.</span><span class="sxs-lookup"><span data-stu-id="150c7-112">The minimum value you can specify for `Weight` is "0".</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="150c7-113">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="150c7-113">Element Characteristics</span></span>  
  
|<span data-ttu-id="150c7-114">Характеристика</span><span class="sxs-lookup"><span data-stu-id="150c7-114">Characteristic</span></span>|<span data-ttu-id="150c7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="150c7-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="150c7-116">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="150c7-116">**Data type and length**</span></span>|<span data-ttu-id="150c7-117">`string`, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="150c7-117">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="150c7-118">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="150c7-118">**Default value**</span></span>|<span data-ttu-id="150c7-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="150c7-119">None.</span></span>|  
|<span data-ttu-id="150c7-120">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="150c7-120">**Occurrence**</span></span>|<span data-ttu-id="150c7-121">Необходимо наличие одного такого элемента, если не задан никакой другой тип рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="150c7-121">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="150c7-122">Для родительского элемента `EventString` необходимо задать дочерний элемент `File`, `Database` или `Workload`, однако одновременно может использоваться только один из них.</span><span class="sxs-lookup"><span data-stu-id="150c7-122">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="150c7-123">Например, если рабочая нагрузка задается элементом `EventString`, то нельзя задавать рабочую нагрузку также элементом `File` в том же входном XML-файле.</span><span class="sxs-lookup"><span data-stu-id="150c7-123">For example, if you specify a workload with the `EventString` element, then you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="150c7-124">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="150c7-124">Element Relationships</span></span>  
  
|<span data-ttu-id="150c7-125">Связь</span><span class="sxs-lookup"><span data-stu-id="150c7-125">Relationship</span></span>|<span data-ttu-id="150c7-126">Элементы</span><span class="sxs-lookup"><span data-stu-id="150c7-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="150c7-127">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="150c7-127">**Parent element**</span></span>|[<span data-ttu-id="150c7-128">Элемент Workload (DTA)</span><span class="sxs-lookup"><span data-stu-id="150c7-128">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="150c7-129">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="150c7-129">**Child elements**</span></span>|<span data-ttu-id="150c7-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="150c7-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="150c7-131">Пример</span><span class="sxs-lookup"><span data-stu-id="150c7-131">Example</span></span>  
 <span data-ttu-id="150c7-132">Пример использования этого элемента см. в разделе [Образец входного XML-файла с описанием встроенной рабочей нагрузки (DTA)](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="150c7-132">For a usage example of this element, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md) .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="150c7-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="150c7-133">See Also</span></span>  
 [<span data-ttu-id="150c7-134">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="150c7-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
