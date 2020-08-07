---
title: Элемент Create (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Create element (DTA)
ms.assetid: 9d076c90-f933-45f4-b6d9-447793f6528b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 407f16c3898e56cd393e36c39ed799b83e0092ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727658"
---
# <a name="create-element-dta"></a><span data-ttu-id="131d2-102">элемент Create (DTA)</span><span class="sxs-lookup"><span data-stu-id="131d2-102">Create Element (DTA)</span></span>
  <span data-ttu-id="131d2-103">Содержит сведения об индексах, статистике или структурах кучи в указанной пользователем конфигурации.</span><span class="sxs-lookup"><span data-stu-id="131d2-103">Contains information about the indexes, statistics, or heap structures in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="131d2-104">Syntax</span></span>  
  
```  
  
<Recommendation>  
    <Create>  
    ...code removed here...  
    </Create>  
</Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="131d2-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="131d2-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="131d2-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="131d2-106">Characteristic</span></span>|<span data-ttu-id="131d2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="131d2-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="131d2-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="131d2-108">**Data type and length**</span></span>|<span data-ttu-id="131d2-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="131d2-109">None.</span></span>|  
|<span data-ttu-id="131d2-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="131d2-110">**Default value**</span></span>|<span data-ttu-id="131d2-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="131d2-111">None.</span></span>|  
|<span data-ttu-id="131d2-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="131d2-112">**Occurrence**</span></span>|<span data-ttu-id="131d2-113">Данный элемент должен быть указан один раз для каждого типа структур физического проектирования (индексов, статистики или структур кучи).</span><span class="sxs-lookup"><span data-stu-id="131d2-113">Required once for each physical design structure type (indexes, statistics, or heap structures).</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="131d2-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="131d2-114">Element Relationships</span></span>  
  
|<span data-ttu-id="131d2-115">Связь</span><span class="sxs-lookup"><span data-stu-id="131d2-115">Relationship</span></span>|<span data-ttu-id="131d2-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="131d2-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="131d2-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="131d2-117">**Parent element**</span></span>|[<span data-ttu-id="131d2-118">Элемент Recommendation (DTA)</span><span class="sxs-lookup"><span data-stu-id="131d2-118">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
|<span data-ttu-id="131d2-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="131d2-119">**Child elements**</span></span>|[<span data-ttu-id="131d2-120">Элемент Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="131d2-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)<br /><br /> <span data-ttu-id="131d2-121">`Statistics`Элемент (сведения см. в разделе [Помощник по настройке ядра СУБД XML Schema](https://schemas.microsoft.com/sqlserver/) )</span><span class="sxs-lookup"><span data-stu-id="131d2-121">`Statistics` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span><br /><br /> <span data-ttu-id="131d2-122">`Heap`Элемент (сведения см. в разделе [Помощник по настройке ядра СУБД XML Schema](https://schemas.microsoft.com/sqlserver/) )</span><span class="sxs-lookup"><span data-stu-id="131d2-122">`Heap` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="131d2-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="131d2-123">Remarks</span></span>  
 <span data-ttu-id="131d2-124">Этот элемент с именем **CreateTypecomplexType** определен в схеме XML помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="131d2-124">This element is of the **CreateTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="131d2-125">Он используется для создания индексов, статистики и структур кучи для указанной пользователем конфигурации.</span><span class="sxs-lookup"><span data-stu-id="131d2-125">It is used to create indexes, statistics, and heap structures for a user-specified configuration.</span></span> <span data-ttu-id="131d2-126">Не путайте этот элемент `Create` с другими типами, которые можно использовать для создания представлений (`CreateViewType`) секционирования (`CreatePType`).</span><span class="sxs-lookup"><span data-stu-id="131d2-126">Do not confuse this `Create` element with the other types that can be used to create views (`CreateViewType`) or partitioning (`CreatePType`).</span></span> <span data-ttu-id="131d2-127">Сведения об этих типах элементов см. в [Помощник по настройке ядра СУБД схеме XML](https://schemas.microsoft.com/sqlserver/) `Create` .</span><span class="sxs-lookup"><span data-stu-id="131d2-127">Refer to the [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information about these other `Create` element types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="131d2-128">Пример</span><span class="sxs-lookup"><span data-stu-id="131d2-128">Example</span></span>  
 <span data-ttu-id="131d2-129">Пример использования этого элемента см. в разделе [Образец входного XML-файла с пользовательской конфигурацией (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="131d2-129">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131d2-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="131d2-130">See Also</span></span>  
 [<span data-ttu-id="131d2-131">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="131d2-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
