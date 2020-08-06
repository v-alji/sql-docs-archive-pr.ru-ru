---
title: Добавление модели интеллектуального анализа данных в существующую структуру интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], adding
- mining structures [Analysis Services], mining models
- adding mining models
ms.assetid: fcf72300-0674-4e73-a826-9b8eeffefbb5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0afdf5f795303eaa8bb672aa80e68e0f1f891607
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666285"
---
# <a name="add-a-mining-model-to-an-existing-mining-structure"></a><span data-ttu-id="03b96-102">добавить модель интеллектуального анализа данных к существующей структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="03b96-102">Add a Mining Model to an Existing Mining Structure</span></span>
  <span data-ttu-id="03b96-103">После определения первой модели к структуре интеллектуального анализа данных можно добавить еще несколько моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="03b96-103">You can add more mining models to a mining structure, after you add the initial model.</span></span> <span data-ttu-id="03b96-104">В каждой модели должны содержаться столбцы, существующие в структуре, но использование столбцов можно определять отдельно для каждой модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="03b96-104">Each model must contain columns that exist in the structure, but you can define the usage of the columns differently for each mining model.</span></span> <span data-ttu-id="03b96-105">Дополнительные сведения об определении столбцов моделей интеллектуального анализа данных см. в разделе [Столбцы модели интеллектуального анализа данных](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="03b96-105">For more information about how to define mining models columns, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-add-a-mining-model-to-the-structure"></a><span data-ttu-id="03b96-106">Добавление модели интеллектуального анализа данных к структуре</span><span class="sxs-lookup"><span data-stu-id="03b96-106">To add a mining model to the structure</span></span>  
  
1.  <span data-ttu-id="03b96-107">В меню **Модель интеллектуального анализа данных** в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]выберите пункт **Создать модель интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="03b96-107">From the **Mining Model** menu item in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select **New Mining Model**.</span></span>  
  
     <span data-ttu-id="03b96-108">Откроется диалоговое окно **Создание модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="03b96-108">The **New Mining Model** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="03b96-109">В разделе **Название модели**введите имя новой модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="03b96-109">Under **Model name**, enter a name for the new mining model.</span></span>  
  
3.  <span data-ttu-id="03b96-110">В списке **Имя алгоритма**выберите алгоритм, который будет использоваться для построения модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="03b96-110">Under **Algorithm name**, select the algorithm that the mining model will be built from.</span></span>  
  
4.  <span data-ttu-id="03b96-111">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="03b96-111">Click **OK**.</span></span>  
  
 <span data-ttu-id="03b96-112">На вкладке **модели интеллектуального анализа данных** появится новая модель интеллектуального анализа данных. Модель использует столбцы по умолчанию, существующие в структуре.</span><span class="sxs-lookup"><span data-stu-id="03b96-112">A new mining model appears in the **Mining Models** tab. The model uses the default columns that exist in the structure.</span></span> <span data-ttu-id="03b96-113">Дополнительные сведения об изменении столбцов см. в разделе [Изменение свойств модели интеллектуального анализа данных](change-the-properties-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="03b96-113">For information about how to modify the columns, see [Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b96-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="03b96-114">See Also</span></span>  
 [<span data-ttu-id="03b96-115">Задачи и инструкции по модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="03b96-115">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
