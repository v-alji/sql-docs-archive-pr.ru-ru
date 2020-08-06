---
title: Исключить столбец из модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- excluding mining model columns
- mining models [Analysis Services], columns
- columns [data mining], excluding
ms.assetid: 404fe5fe-3ba2-4b9b-8780-0d02343d467f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30affebc143184c6287858f60b5d4f5d089c322a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657987"
---
# <a name="exclude-a-column-from-a-mining-model"></a><span data-ttu-id="50d89-102">исключить столбец из модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="50d89-102">Exclude a Column from a Mining Model</span></span>
  <span data-ttu-id="50d89-103">При создании новой модели интеллектуального анализа данных может отсутствовать необходимость использовать все столбцы, существующие в структуре интеллектуального анализа данных, на которой основывается модель.</span><span class="sxs-lookup"><span data-stu-id="50d89-103">When you create a new mining model, you may not want to use all the columns that exist in the mining structure on which the model is based.</span></span> <span data-ttu-id="50d89-104">Например, вы могли добавить столбец "имя клиента" для детализации, но не хотите использовать его для моделирования.</span><span class="sxs-lookup"><span data-stu-id="50d89-104">For example, you might have added a customer name column for drillthrough, but don't want to use it for modeling.</span></span> <span data-ttu-id="50d89-105">Или же может потребоваться создать несколько копий столбца с различной дискретизацией так, чтобы только одна из таких копий использовалась в каждой модели, а остальные пропускались.</span><span class="sxs-lookup"><span data-stu-id="50d89-105">Or, you might decide to create multiple copies of a column with different discretizations, and use only one of the copies in each model, and ignore the rest.</span></span> <span data-ttu-id="50d89-106">Также можно избирательно добавлять входные столбцы в некоторые модели для того, чтобы увидеть, как добавленные переменные повлияют на выходной столбец.</span><span class="sxs-lookup"><span data-stu-id="50d89-106">You could also selectively add input columns in several different models to see how the added variable affects the output column.</span></span>  
  
 <span data-ttu-id="50d89-107">Не требуется создавать новую структуру интеллектуального анализа данных для каждой комбинации столбцов. Вместо этого можно просто отметить столбцы, которые не будут использоваться в конкретной модели.</span><span class="sxs-lookup"><span data-stu-id="50d89-107">You do not need to create a new mining structure for each combination of columns; instead, you can simply flag a column as not being used in a particular model.</span></span>  
  
### <a name="to-exclude-a-column-from-a-mining-model"></a><span data-ttu-id="50d89-108">Исключение столбца из модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="50d89-108">To exclude a column from a mining model</span></span>  
  
1.  <span data-ttu-id="50d89-109">На вкладке **Модели интеллектуального анализа данных** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]выберите ячейку, которая соответствует столбцу, который необходимо исключить, под соответствующей моделью интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="50d89-109">In the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the cell that corresponds to the column you want to exclude, under the appropriate mining model.</span></span>  
  
2.  <span data-ttu-id="50d89-110">Выберите пункт **Пропустить** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="50d89-110">Select **Ignore** from the drop-down list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d89-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="50d89-111">See Also</span></span>  
 [<span data-ttu-id="50d89-112">Задачи и инструкции по модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="50d89-112">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
