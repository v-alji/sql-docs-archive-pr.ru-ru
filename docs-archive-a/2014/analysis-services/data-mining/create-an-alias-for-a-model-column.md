---
title: Создание псевдонима для столбца модели | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- mining models [Analysis Services], columns
- column names [Analysis Services]
ms.assetid: c80ebe66-a8f8-4f24-9fe8-8288de9d13bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 908c0a8d8caa810badf4b82dc3dd3f411d09f323
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656042"
---
# <a name="create-an-alias-for-a-model-column"></a><span data-ttu-id="172bb-102">создать псевдоним для столбца модели</span><span class="sxs-lookup"><span data-stu-id="172bb-102">Create an Alias for a Model Column</span></span>
  <span data-ttu-id="172bb-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]для столбца модели можно создать псевдоним.</span><span class="sxs-lookup"><span data-stu-id="172bb-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can create an alias for a model column.</span></span> <span data-ttu-id="172bb-104">Необходимость в этом может возникнуть, если имя структуры интеллектуального анализа данных имеет слишком большую длину и с ним неудобно работать, или если необходимо присвоить столбцу другое имя, более точно описывающее его содержимое или назначение в модели.</span><span class="sxs-lookup"><span data-stu-id="172bb-104">This might be useful when the mining structure name is too long to easily work with, or when you want to rename the column to be more descriptive of its contents or usage in the model.</span></span> <span data-ttu-id="172bb-105">Например, если создается копия столбца структуры, а затем дискретизация столбца выполняется различно для конкретной модели, можно переименовать столбец, чтобы его имя более точно отражало его содержимое.</span><span class="sxs-lookup"><span data-stu-id="172bb-105">For example, if you make a copy of a structure column and then discretize the column differently for a particular model, you can rename the column to reflect the content more accurately.</span></span>  
  
 <span data-ttu-id="172bb-106">Чтобы создать псевдоним для столбца модели, можно воспользоваться панелью **Свойства** и задать свойство [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) столбца.</span><span class="sxs-lookup"><span data-stu-id="172bb-106">To create an alias for a model column, you use the **Properties** pane and set the [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) property of the column.</span></span>  
  
 <span data-ttu-id="172bb-107">На вкладке **Модели интеллектуального анализа данных** конструктора моделей интеллектуального анализа данных псевдоним отображается в круглых скобках рядом с меткой использования столбца.</span><span class="sxs-lookup"><span data-stu-id="172bb-107">On the **Mining Models** tab of Data Mining Designer, the alias appears enclosed in parentheses next to the column usage label.</span></span>  
  
 <span data-ttu-id="172bb-108">Дополнительные сведения о задании свойств в модели интеллектуального анализа данных см. в разделе [Столбцы модели интеллектуального анализа данных](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="172bb-108">For information about how to set the properties of a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-add-an-alias-to-a-mining-model-column"></a><span data-ttu-id="172bb-109">Добавление псевдонима к столбцу модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="172bb-109">To add an alias to a mining model column</span></span>  
  
1.  <span data-ttu-id="172bb-110">На вкладке **Модели интеллектуального анализа данных** конструктора моделей интеллектуального анализа данных щелкните правой кнопкой мыши ячейку в модели интеллектуального анализа данных для столбца интеллектуального анализа, которую необходимо изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="172bb-110">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the mining model for the mining column that you want to change, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="172bb-111">В окне **Свойства** в правой части экрана щелкните ячейку рядом со свойством Name и удалите текущее значение.</span><span class="sxs-lookup"><span data-stu-id="172bb-111">In the **Properties** window on the right side of the screen, click the cell next to the Name property and delete the current value.</span></span> <span data-ttu-id="172bb-112">Введите новое имя столбца.</span><span class="sxs-lookup"><span data-stu-id="172bb-112">Type a new name for the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="172bb-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="172bb-113">See Also</span></span>  
 <span data-ttu-id="172bb-114">[Задачи и инструкции по модели интеллектуального анализа данных](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="172bb-114">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="172bb-115">Свойства модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="172bb-115">Mining Model Properties</span></span>](mining-model-properties.md)  
  
  
