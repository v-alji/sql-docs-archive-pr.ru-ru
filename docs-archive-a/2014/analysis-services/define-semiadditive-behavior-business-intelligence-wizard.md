---
title: Определение полуаддитивный поведения (мастер бизнес-аналитики) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.semiadditivememberdetection.f1
ms.assetid: e57080ba-ce96-40f8-bca7-6701d1725b3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5a3c46de038a7e45dcb39805e324260676a03228
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728953"
---
# <a name="define-semiadditive-behavior-business-intelligence-wizard"></a><span data-ttu-id="82fe7-102">Определение полуаддитивного режима (мастер бизнес-аналитики)</span><span class="sxs-lookup"><span data-stu-id="82fe7-102">Define Semiadditive Behavior (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="82fe7-103">Страница **Определение полуаддитивного режима** используется для включения или выключения полуаддитивного режима в мерах.</span><span class="sxs-lookup"><span data-stu-id="82fe7-103">Use the **Define Semiadditive Behavior** page to enable or disable semi-additive behavior on measures.</span></span> <span data-ttu-id="82fe7-104">Полуаддитивный режим определяет, каким образом меры, содержащиеся в кубе, объединяются по измерению времени.</span><span class="sxs-lookup"><span data-stu-id="82fe7-104">Semi-additive behavior determines how measures that are contained by a cube are aggregated over a time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82fe7-105">За исключением режима LastChild, который доступен в выпуске Standard Edition, полуаддитивные режимы доступны только в бизнес-аналитике или в выпуске Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="82fe7-105">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span> <span data-ttu-id="82fe7-106">Более того, поскольку полуаддитивный режим определен только для мер и отсутствует для измерений, этой страницы не будет в мастере бизнес-аналитики, если он был запущен из конструктора измерений или щелчком правой кнопкой мыши измерения в обозревателе решений в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82fe7-106">Furthermore, because semiadditive behavior is defined only on measures and not dimensions, you will not find this page in the Business Intelligence Wizard if it was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="82fe7-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="82fe7-107">Options</span></span>  
 <span data-ttu-id="82fe7-108">**Отключить полуаддитивный режим**</span><span class="sxs-lookup"><span data-stu-id="82fe7-108">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="82fe7-109">Отключает полуаддитивный режим для всех мер, содержащихся в кубе.</span><span class="sxs-lookup"><span data-stu-id="82fe7-109">Disables semi-additive behavior in all measures contained by the cube.</span></span>  
  
 <span data-ttu-id="82fe7-110">**Мастер обнаружил \<dimension name> измерение счетов, которое содержит полуаддитивные элементы. Сервер будет выполнять статистическую обработку элементов этого измерения в соответствии с полуаддитивный поведением, заданным для каждого типа учетной записи.**</span><span class="sxs-lookup"><span data-stu-id="82fe7-110">**The wizard has detected the \<dimension name> account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="82fe7-111">Включает полуаддитивный режим для измерений счетов, содержащих полуаддитивные элементы.</span><span class="sxs-lookup"><span data-stu-id="82fe7-111">Enables semi-additive behavior for account dimensions that contain semi-additive members.</span></span> <span data-ttu-id="82fe7-112">При выборе этого параметра для всех мер в группах, которые ссылаются на измерение счетов, назначается статистическая функция `ByAccount`.</span><span class="sxs-lookup"><span data-stu-id="82fe7-112">Selecting this option sets the aggregation function of all measures in measure groups that reference the account dimension to `ByAccount`.</span></span>  
  
 <span data-ttu-id="82fe7-113">Дополнительные сведения об измерениях счетов см. в разделе [Создание учетной записи Finance с измерением типа "родитель-потомок"](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span><span class="sxs-lookup"><span data-stu-id="82fe7-113">For more information about account dimensions, see [Create a Finance Account of parent-child type Dimension](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span></span>  
  
 <span data-ttu-id="82fe7-114">**Определить полуаддитивный режим для конкретных элементов**</span><span class="sxs-lookup"><span data-stu-id="82fe7-114">**Define semiadditive behavior for individual members**</span></span>  
 <span data-ttu-id="82fe7-115">Включает полуаддитивный режим и указывает полуаддитивную статистическую функцию для определенных мер.</span><span class="sxs-lookup"><span data-stu-id="82fe7-115">Enables semi-additive behavior and specifies the semi-additive aggregation function for specific measures.</span></span> <span data-ttu-id="82fe7-116">Статистическая функция относится ко всем измерениям, на которые ссылается группа мер, содержащая данную меру.</span><span class="sxs-lookup"><span data-stu-id="82fe7-116">The aggregation function applies to all dimensions that are referenced by the measure group that contains the measure.</span></span>  
  
 <span data-ttu-id="82fe7-117">**Мерам**</span><span class="sxs-lookup"><span data-stu-id="82fe7-117">**Measures**</span></span>  
 <span data-ttu-id="82fe7-118">Отображает имя меры, содержащейся в кубе.</span><span class="sxs-lookup"><span data-stu-id="82fe7-118">Displays the name of a measure contained by the cube.</span></span>  
  
 <span data-ttu-id="82fe7-119">**Полуаддитивная функция**</span><span class="sxs-lookup"><span data-stu-id="82fe7-119">**Semiadditive Function**</span></span>  
 <span data-ttu-id="82fe7-120">Выберите статистическую функцию для выбранной меры.</span><span class="sxs-lookup"><span data-stu-id="82fe7-120">Select the aggregation function for the selected measure.</span></span> <span data-ttu-id="82fe7-121">В следующей таблице перечислены имеющиеся статистические функции.</span><span class="sxs-lookup"><span data-stu-id="82fe7-121">The following table lists the aggregation functions that are available.</span></span>  
  
|<span data-ttu-id="82fe7-122">Значение</span><span class="sxs-lookup"><span data-stu-id="82fe7-122">Value</span></span>|<span data-ttu-id="82fe7-123">Описание</span><span class="sxs-lookup"><span data-stu-id="82fe7-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82fe7-124">**AverageOfChildren**</span><span class="sxs-lookup"><span data-stu-id="82fe7-124">**AverageOfChildren**</span></span>|<span data-ttu-id="82fe7-125">Статистическая обработка проводится путем возвращения среднего значения дочерних элементов меры.</span><span class="sxs-lookup"><span data-stu-id="82fe7-125">Aggregated by returning the average of the measure's children.</span></span>|  
|`ByAccount`|<span data-ttu-id="82fe7-126">Статистическая обработка проводится статистической функцией, связанной с типом счета, определяемой атрибутом в измерении счетов.</span><span class="sxs-lookup"><span data-stu-id="82fe7-126">Aggregated by the aggregation function associated with the specified account type of an attribute in an account dimension.</span></span>|  
|`Count`|<span data-ttu-id="82fe7-127">Статистическая обработка проводится с использованием функции `Count`.</span><span class="sxs-lookup"><span data-stu-id="82fe7-127">Aggregated using the `Count` function.</span></span>|  
|`DistinctCount`|<span data-ttu-id="82fe7-128">Статистическая обработка проводится с использованием функции `DistinctCount`.</span><span class="sxs-lookup"><span data-stu-id="82fe7-128">Aggregated using the `DistinctCount` function.</span></span>|  
|<span data-ttu-id="82fe7-129">**FirstChild**</span><span class="sxs-lookup"><span data-stu-id="82fe7-129">**FirstChild**</span></span>|<span data-ttu-id="82fe7-130">Статистическая обработка проводится путем возвращения первого дочернего элемента меры по измерению времени.</span><span class="sxs-lookup"><span data-stu-id="82fe7-130">Aggregated by returning the measure's first child member over a time dimension.</span></span>|  
|<span data-ttu-id="82fe7-131">**FirstNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="82fe7-131">**FirstNonEmpty**</span></span>|<span data-ttu-id="82fe7-132">Статистическая обработка проводится путем возвращения элемента меры, который не является пустым, по измерению времени.</span><span class="sxs-lookup"><span data-stu-id="82fe7-132">Aggregated by returning the measure's first nonempty member over a time dimension.</span></span>|  
|<span data-ttu-id="82fe7-133">**LastChild**</span><span class="sxs-lookup"><span data-stu-id="82fe7-133">**LastChild**</span></span>|<span data-ttu-id="82fe7-134">Статистическая обработка проводится путем возвращения последнего дочернего элемента меры по измерению времени.</span><span class="sxs-lookup"><span data-stu-id="82fe7-134">Aggregated by returning the measure's last child member over a time dimension.</span></span>|  
|<span data-ttu-id="82fe7-135">**LastNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="82fe7-135">**LastNonEmpty**</span></span>|<span data-ttu-id="82fe7-136">Статистическая обработка проводится путем возвращения последнего элемента меры, который не является пустым, по измерению времени.</span><span class="sxs-lookup"><span data-stu-id="82fe7-136">Aggregated by returning the measure's last nonempty member over a time dimension.</span></span>|  
|`Max`|<span data-ttu-id="82fe7-137">Статистическая обработка проводится с использованием функции `Max`.</span><span class="sxs-lookup"><span data-stu-id="82fe7-137">Aggregated using the `Max` function.</span></span>|  
|`Min`|<span data-ttu-id="82fe7-138">Статистическая обработка проводится с использованием функции `Min`.</span><span class="sxs-lookup"><span data-stu-id="82fe7-138">Aggregated using the `Min` function.</span></span>|  
|<span data-ttu-id="82fe7-139">**None**</span><span class="sxs-lookup"><span data-stu-id="82fe7-139">**None**</span></span>|<span data-ttu-id="82fe7-140">Статистическая обработка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="82fe7-140">No aggregation performed.</span></span>|  
|`Sum`|<span data-ttu-id="82fe7-141">Статистическая обработка проводится с использованием функции `Sum`.</span><span class="sxs-lookup"><span data-stu-id="82fe7-141">Aggregated using the `Sum` function.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="82fe7-142">Установки для этого параметра используются только в том случае, если выбран параметр **Определить полуаддитивный режим для конкретных элементов** .</span><span class="sxs-lookup"><span data-stu-id="82fe7-142">Selections made for this option apply only if **Define semiadditive behavior for individual members** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82fe7-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="82fe7-143">See Also</span></span>  
 <span data-ttu-id="82fe7-144">[Справка F1 мастера бизнес-аналитики](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="82fe7-144">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="82fe7-145">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="82fe7-145">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="82fe7-146">Конструктор измерений &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="82fe7-146">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
