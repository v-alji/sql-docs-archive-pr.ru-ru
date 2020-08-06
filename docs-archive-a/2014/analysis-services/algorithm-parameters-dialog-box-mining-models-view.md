---
title: Диалоговое окно «Параметры алгоритма» (представление моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.models.algorithmparameters.f1
helpviewer_keywords:
- Algorithm Parameters dialog box
ms.assetid: 57f9f6f8-8ca4-4a6e-8f18-85f0571b7060
author: minewiskan
ms.author: owend
ms.openlocfilehash: 303d8b5bd3437690c65873e106a94cf2ce8eb9f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656935"
---
# <a name="algorithm-parameters-dialog-box-mining-models-view"></a><span data-ttu-id="39661-102">Диалоговое окно «Параметры алгоритма» (представление моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="39661-102">Algorithm Parameters Dialog Box (Mining Models View)</span></span>
  <span data-ttu-id="39661-103">Используйте диалоговое окно **Параметры алгоритма** для регулировки параметров алгоритма, которые относятся к выбранной модели.</span><span class="sxs-lookup"><span data-stu-id="39661-103">Use the **Algorithm Parameters** dialog box to adjust algorithm parameters that are specific to the selected model.</span></span> <span data-ttu-id="39661-104">При изменении параметра алгоритма обычно меняются результаты модели интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="39661-104">When you change an algorithm parameter, you will usually change the results of the mining model.</span></span> <span data-ttu-id="39661-105">Способ, при котором каждый параметр влияет на результаты, зависит от данных используемого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="39661-105">The way that each parameter affects the results depends on the algorithm you are using, and on your data.</span></span> <span data-ttu-id="39661-106">Дополнительные сведения см. в разделе [Настройка структуры и моделей интеллектуального анализа данных](data-mining/customize-mining-models-and-structure.md).</span><span class="sxs-lookup"><span data-stu-id="39661-106">For more information, see [Customize Mining Models and Structure](data-mining/customize-mining-models-and-structure.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="39661-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="39661-107">Options</span></span>  
 <span data-ttu-id="39661-108">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="39661-108">**Parameters**</span></span>  
 <span data-ttu-id="39661-109">Позволяет отобразить список параметров, доступных для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="39661-109">Lists the parameters that are available for the selected mining model.</span></span>  
  
 <span data-ttu-id="39661-110">В следующем списке описываются доступные столбцы.</span><span class="sxs-lookup"><span data-stu-id="39661-110">The following list describes the available columns.</span></span>  
  
|<span data-ttu-id="39661-111">Столбец</span><span class="sxs-lookup"><span data-stu-id="39661-111">Column</span></span>|<span data-ttu-id="39661-112">Описание</span><span class="sxs-lookup"><span data-stu-id="39661-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="39661-113">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="39661-113">**Parameter**</span></span>|<span data-ttu-id="39661-114">Выведите список имен параметров.</span><span class="sxs-lookup"><span data-stu-id="39661-114">List the name of the parameter.</span></span>|  
|<span data-ttu-id="39661-115">**Значение**</span><span class="sxs-lookup"><span data-stu-id="39661-115">**Value**</span></span>|<span data-ttu-id="39661-116">Вводите значение только в том случае, если необходимо изменить значение параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="39661-116">Enter a value only if you want to change the default value of the parameter.</span></span>|  
|<span data-ttu-id="39661-117">**Default**</span><span class="sxs-lookup"><span data-stu-id="39661-117">**Default**</span></span>|<span data-ttu-id="39661-118">Выведите список значений по умолчанию для параметра, который будет использован в алгоритме, если не нужно вводить значение в столбец **Значение** .</span><span class="sxs-lookup"><span data-stu-id="39661-118">List the default value of the parameter that the algorithm will use if you do not supply a value in the **Value** column.</span></span>|  
|<span data-ttu-id="39661-119">**Range**</span><span class="sxs-lookup"><span data-stu-id="39661-119">**Range**</span></span>|<span data-ttu-id="39661-120">Выведите список диапазонов возможных значений, которые можно ввести в столбец **Значение** .</span><span class="sxs-lookup"><span data-stu-id="39661-120">List the range of possible values that you can enter into the **Value** column.</span></span> <span data-ttu-id="39661-121">Диапазон может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="39661-121">The ranges can be one of the following:</span></span><br /><br /> <span data-ttu-id="39661-122">Дискретный список, например 1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="39661-122">A discrete list, such as 1, 2, 3</span></span><br /><br /> <span data-ttu-id="39661-123">Включающий диапазон, например [0, 100]</span><span class="sxs-lookup"><span data-stu-id="39661-123">An inclusive range, such as [0, 100]</span></span><br /><br /> <span data-ttu-id="39661-124">Эксклюзивный диапазон, например (0,...)</span><span class="sxs-lookup"><span data-stu-id="39661-124">An exclusive range, such as (0,...)</span></span><br /><br /> <span data-ttu-id="39661-125">Сочетание, например [0,...)</span><span class="sxs-lookup"><span data-stu-id="39661-125">A combination, such as [0,...)</span></span>|  
  
 <span data-ttu-id="39661-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="39661-126">**Description**</span></span>  
 <span data-ttu-id="39661-127">Позволяет описать параметр, выбранный в списке **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="39661-127">Describes the selected parameter in the **Parameters** list.</span></span>  
  
 <span data-ttu-id="39661-128">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="39661-128">**Add**</span></span>  
 <span data-ttu-id="39661-129">Нажмите, чтобы добавить в список дополнительные параметры, относящиеся к алгоритму.</span><span class="sxs-lookup"><span data-stu-id="39661-129">Click to add additional, algorithm specific-parameters to the list.</span></span> <span data-ttu-id="39661-130">После добавления параметра можно ввести правильное имя в столбец **Параметр** и ввести значение в столбец **Значение** .</span><span class="sxs-lookup"><span data-stu-id="39661-130">After adding the parameter, you can enter the correct name in the **Parameter** column and provide a value in the **Value** column.</span></span>  
  
 <span data-ttu-id="39661-131">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="39661-131">**Remove**</span></span>  
 <span data-ttu-id="39661-132">Нажмите, чтобы удалить пользовательский параметр из списка.</span><span class="sxs-lookup"><span data-stu-id="39661-132">Click to delete a custom parameter from the list.</span></span>  
  
 <span data-ttu-id="39661-133">Если удалить из списка один из параметров стандартного алгоритма служб Analysis Services, то он по-прежнему будет использоваться в модели, но со значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="39661-133">If you delete one of the standard Analysis Services algorithm parameters from the list, the parameter will still be used in the model, but with the default values for that parameter.</span></span> <span data-ttu-id="39661-134">Параметр не удаляется окончательно и появится при следующем открытии диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="39661-134">The parameter is not permanently deleted and will appear the next time that you open the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39661-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="39661-135">See Also</span></span>  
 <span data-ttu-id="39661-136">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="39661-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="39661-137">[Представление моделей интеллектуального анализа данных в конструкторе моделей интеллектуального анализа &#40;&#41;](mining-models-view-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="39661-137">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="39661-138">Перемещение объектов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="39661-138">Moving Data Mining Objects</span></span>](data-mining/moving-data-mining-objects.md)  
  
  
