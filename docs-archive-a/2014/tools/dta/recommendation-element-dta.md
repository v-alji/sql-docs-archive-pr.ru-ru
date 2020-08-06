---
title: Элемент рекомендаций (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Recommendation element
ms.assetid: 679ea535-865a-4633-a4d3-5b3090515158
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4eb54a106d67f0217a2604b2d08754d0d2c0765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656127"
---
# <a name="recommendation-element-dta"></a><span data-ttu-id="23d85-102">Элемент Recommendation (DTA)</span><span class="sxs-lookup"><span data-stu-id="23d85-102">Recommendation Element (DTA)</span></span>
  <span data-ttu-id="23d85-103">Содержит данные о гипотетических индексах, являющихся частью пользовательской конфигурации.</span><span class="sxs-lookup"><span data-stu-id="23d85-103">Contains information about the hypothetical indexes that are part of a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23d85-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    ...code removed here...  
    <Table>  
      <Name>...</Name>  
      <Recommendation>  
      ...code removed here...  
      </Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="23d85-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="23d85-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="23d85-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="23d85-106">Characteristic</span></span>|<span data-ttu-id="23d85-107">Описание</span><span class="sxs-lookup"><span data-stu-id="23d85-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="23d85-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="23d85-108">**Data type and length**</span></span>|<span data-ttu-id="23d85-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="23d85-109">None.</span></span>|  
|<span data-ttu-id="23d85-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="23d85-110">**Default value**</span></span>|<span data-ttu-id="23d85-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="23d85-111">None.</span></span>|  
|<span data-ttu-id="23d85-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="23d85-112">**Occurrence**</span></span>|<span data-ttu-id="23d85-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="23d85-113">Optional.</span></span> <span data-ttu-id="23d85-114">Может использоваться один раз для каждого элемента `Table`.</span><span class="sxs-lookup"><span data-stu-id="23d85-114">Can use once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="23d85-115">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="23d85-115">Element Relationships</span></span>  
  
|<span data-ttu-id="23d85-116">Связь</span><span class="sxs-lookup"><span data-stu-id="23d85-116">Relationship</span></span>|<span data-ttu-id="23d85-117">Элементы</span><span class="sxs-lookup"><span data-stu-id="23d85-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="23d85-118">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="23d85-118">**Parent element**</span></span>|[<span data-ttu-id="23d85-119">Элемент Table для схемы (DTA)</span><span class="sxs-lookup"><span data-stu-id="23d85-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="23d85-120">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="23d85-120">**Child elements**</span></span>|[<span data-ttu-id="23d85-121">Элемент Create (DTA)</span><span class="sxs-lookup"><span data-stu-id="23d85-121">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)<br /><br /> <span data-ttu-id="23d85-122">Элемент `Drop`.</span><span class="sxs-lookup"><span data-stu-id="23d85-122">`Drop` element.</span></span> <span data-ttu-id="23d85-123">Дополнительные сведения см. в статье [XML-схема помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="23d85-123">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23d85-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="23d85-124">Remarks</span></span>  
 <span data-ttu-id="23d85-125">Этот элемент с именем **RecommendationTypecomplexType** определен в схеме XML помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="23d85-125">This element is of the **RecommendationTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="23d85-126">Он используется для задания индексов в гипотетической конфигурации.</span><span class="sxs-lookup"><span data-stu-id="23d85-126">It is used to specify indexes for a hypothetical configuration.</span></span> <span data-ttu-id="23d85-127">Не путайте этот элемент `Recommendation` с другими типами, используемыми для задания секционирования (`RecommendationPType`) или представлений (`RecommendationViewType`).</span><span class="sxs-lookup"><span data-stu-id="23d85-127">Do not confuse this `Recommendation` element with the other types that can be used to specify partitioning (`RecommendationPType`) or views (`RecommendationViewType`).</span></span> <span data-ttu-id="23d85-128">Дополнительные сведения об этих `Recommendation` типах элементов см. в [Помощник по настройке ядра СУБД схеме XML](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="23d85-128">For information about these other `Recommendation` element types, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d85-129">Пример</span><span class="sxs-lookup"><span data-stu-id="23d85-129">Example</span></span>  
 <span data-ttu-id="23d85-130">Пример использования этого элемента см. в разделе [Образец входного XML-файла с пользовательской конфигурацией (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="23d85-130">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d85-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="23d85-131">See Also</span></span>  
 [<span data-ttu-id="23d85-132">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="23d85-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
