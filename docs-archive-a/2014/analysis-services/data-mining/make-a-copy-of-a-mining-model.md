---
title: Создание копии модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], copying
- mining models [Analysis Services], creating
- mining models [Analysis Services], how-to topics
- copying mining models
ms.assetid: 7975bb02-f188-49a0-b7de-5b9b216254ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: a05eb75210ce9f601aeca515cd299f4204908705
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654616"
---
# <a name="make-a-copy-of-a-mining-model"></a><span data-ttu-id="12e6c-102">создать копию модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="12e6c-102">Make a Copy of a Mining Model</span></span>
  <span data-ttu-id="12e6c-103">Создание копии модели интеллектуального анализа полезно, если необходимо быстро создать несколько моделей интеллектуального анализа данных на основе одних и тех же данных.</span><span class="sxs-lookup"><span data-stu-id="12e6c-103">Creating a copy of a mining model is useful when you want to quickly create several mining models that are based on the same data.</span></span> <span data-ttu-id="12e6c-104">После копирования модели новую копию можно редактировать путем изменения параметров или добавления фильтра.</span><span class="sxs-lookup"><span data-stu-id="12e6c-104">After you copy the model, you can then edit the new copy by changing parameters or adding a filter.</span></span>  
  
 <span data-ttu-id="12e6c-105">Например, если существующая таблица Customers связана с таблицей данных о покупках, сделанных клиентами, можно создать отдельные модели интеллектуального анализа данных для каждого демографического показателя клиентов, такого как возраст или область.</span><span class="sxs-lookup"><span data-stu-id="12e6c-105">For example, if you have a Customers table that is linked to a table of purchases, you could create copies to generate separate mining models for each customer demographic, filtering on attributes such as age or region.</span></span>  
  
 <span data-ttu-id="12e6c-106">Дополнительные сведения о копировании содержимого модели (например, географического представления или шаблонов модели) в буфер памяти для использования в другим программах см. в разделе [Копирование представления модели интеллектуального анализа данных](copy-a-view-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="12e6c-106">For information about how to copy the content of the model (such as the graphical representation or the model patterns) to the Clipboard for use in other programs, see [Copy a View of a Mining Model](copy-a-view-of-a-mining-model.md).</span></span>  
  
### <a name="to-create-a-related-mining-model"></a><span data-ttu-id="12e6c-107">Создание связанной модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="12e6c-107">To create a related mining model</span></span>  
  
1.  <span data-ttu-id="12e6c-108">В обозревателе решений среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]щелкните структуру интеллектуального анализа данных, которая содержит модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="12e6c-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model.</span></span>  
  
2.  <span data-ttu-id="12e6c-109">Перейдите на вкладку **Модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="12e6c-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="12e6c-110">Выберите модель и щелкните правой кнопкой мыши, чтобы открыть контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="12e6c-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="12e6c-111">-или-</span><span class="sxs-lookup"><span data-stu-id="12e6c-111">-or-</span></span>  
  
     <span data-ttu-id="12e6c-112">Выберите модель.</span><span class="sxs-lookup"><span data-stu-id="12e6c-112">Select the model.</span></span> <span data-ttu-id="12e6c-113">В меню **Модель интеллектуального анализа данных** выберите пункт **Новая модель интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="12e6c-113">On the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="12e6c-114">Введите имя новой модели интеллектуального анализа данных и выберите алгоритм.</span><span class="sxs-lookup"><span data-stu-id="12e6c-114">Type a name for the new mining model, and select an algorithm.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-the-filter-on-the-copied-mining-model"></a><span data-ttu-id="12e6c-115">Изменение фильтра в скопированной модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="12e6c-115">To edit the filter on the copied mining model</span></span>  
  
1.  <span data-ttu-id="12e6c-116">Выберите модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="12e6c-116">Select the mining model.</span></span>  
  
2.  <span data-ttu-id="12e6c-117">В окне **Свойства** щелкните текстовое поле для свойства **Фильтр** и нажмите кнопку Построить **(...)** .</span><span class="sxs-lookup"><span data-stu-id="12e6c-117">In the **Properties** window, click the text box for the **Filter** property, and the click the build **(...)** button.</span></span>  
  
3.  <span data-ttu-id="12e6c-118">Измените условия фильтра.</span><span class="sxs-lookup"><span data-stu-id="12e6c-118">Change the filter conditions.</span></span>  
  
     <span data-ttu-id="12e6c-119">Дополнительные сведения об использовании диалоговых окон редактора фильтров см. в разделе [Применение фильтра к модели интеллектуального анализа данных](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="12e6c-119">For more information about how to use the filter editor dialog boxes, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
4.  <span data-ttu-id="12e6c-120">В окне **Свойства** в `AlgorithmParameters` текстовом поле щелкните **параметры задать**и при необходимости измените параметры алгоритма.</span><span class="sxs-lookup"><span data-stu-id="12e6c-120">In the **Properties** window, in the `AlgorithmParameters` text box, click **Setalgorithm parameters**, and change algorithm parameters, if desired.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="12e6c-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="12e6c-121">See Also</span></span>  
 <span data-ttu-id="12e6c-122">[Фильтры для моделей интеллектуального анализа данных &#40;Analysis Services интеллектуального анализа&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="12e6c-122">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="12e6c-123">[Задачи и инструкции по модели интеллектуального анализа данных](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="12e6c-123">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="12e6c-124">удалить фильтр из модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="12e6c-124">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
