---
title: Классифицированные столбцы (интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content types [data mining]
- STDEV column
- VARIANCE column
- PROBABLILITY column
- PROBABILITY_STDEV column
- columns [data mining], classified
- classified columns [data mining]
- PROBABILITY_VARIANCE column
- SUPPORT column
ms.assetid: 68bf3b78-dc12-497c-898f-b43a45646123
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c264dfb6a97b8b8f576966e8929f6b0dc51e4ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666897"
---
# <a name="classified-columns-data-mining"></a><span data-ttu-id="3331c-102">Классифицированные столбцы (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="3331c-102">Classified Columns (Data Mining)</span></span>
  <span data-ttu-id="3331c-103">При определении классифицированного столбца создается связь между текущим столбцом и другим столбцом в структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="3331c-103">When you define a classified column, you create a relationship between the current column and another column in the mining structure.</span></span> <span data-ttu-id="3331c-104">Данные в столбце структуры интеллектуального анализа, обозначенном как классифицированный столбец, содержат сведения о разбивке по категориям, описывающие значения в другом столбце структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="3331c-104">The data in the mining structure column that you designate as the classified column contains categorical information that describes the values in another column in the mining structure.</span></span>  
  
 <span data-ttu-id="3331c-105">Например, предположим, что есть два столбца с числовыми данными. Первый столбец, [Yearly Purchases], содержит все покупки каждого заказчика в течение определенного года, а второй столбец, [Standard Deviations], содержит стандартные отклонения для этих значений.</span><span class="sxs-lookup"><span data-stu-id="3331c-105">For example, suppose you have two columns with numerical data: one column, [Yearly Purchases], contains the total yearly purchases per customer for a specific calendar year, and the other column, [Standard Deviations], contains the standard deviations for those values.</span></span> <span data-ttu-id="3331c-106">В этом случае можно обозначить столбец [Yearly Purchases] в качестве классифицированного, чтобы модель позволяла использовать эту связь в анализе.</span><span class="sxs-lookup"><span data-stu-id="3331c-106">In this case you could designate the [Yearly Purchases] column as the classified column, and the model would be able to use this relationship in analysis.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3331c-107">Алгоритмы в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не поддерживают использование классифицированных столбцов. Эта функция предназначена для использования при создании пользовательских алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="3331c-107">The algorithms provided in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not support the use of classified columns; this feature is provided for use in creating custom algorithms.</span></span>  
  
## <a name="defining-a-classified-column"></a><span data-ttu-id="3331c-108">Определение классифицированного столбца</span><span class="sxs-lookup"><span data-stu-id="3331c-108">Defining a Classified Column</span></span>  
 <span data-ttu-id="3331c-109">Тип данных, используемый в классифицированном столбце, должен быть либо `Long`, либо `Double`.</span><span class="sxs-lookup"><span data-stu-id="3331c-109">The data type of a classified column must be either `Long` or `Double`.</span></span>  
  
 <span data-ttu-id="3331c-110">В следующем списке описываются типы содержимого, поддерживаемые службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для классифицированных столбцов.</span><span class="sxs-lookup"><span data-stu-id="3331c-110">The following list describes the content types that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports for classified columns.</span></span>  
  
 <span data-ttu-id="3331c-111">**Воспроизведение**</span><span class="sxs-lookup"><span data-stu-id="3331c-111">**PROBABILITY**</span></span>  
 <span data-ttu-id="3331c-112">Значение в столбце является вероятностью связанного значения и представлено числом от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="3331c-112">The value in the column is the probability of the associated value, and is a number between 0 and 1.</span></span>  
  
 <span data-ttu-id="3331c-113">**ВАРИАЦИЯ**</span><span class="sxs-lookup"><span data-stu-id="3331c-113">**VARIANCE**</span></span>  
 <span data-ttu-id="3331c-114">Значение в столбце является отклонением связанного значения.</span><span class="sxs-lookup"><span data-stu-id="3331c-114">The value in the column is the variance of the associated value.</span></span>  
  
 <span data-ttu-id="3331c-115">**STDEV**</span><span class="sxs-lookup"><span data-stu-id="3331c-115">**STDEV**</span></span>  
 <span data-ttu-id="3331c-116">Значение в столбце является среднеквадратичным отклонением связанного значения.</span><span class="sxs-lookup"><span data-stu-id="3331c-116">The value in the column is the standard deviation of the associated value.</span></span>  
  
 <span data-ttu-id="3331c-117">**PROBABILITY_VARIANCE**</span><span class="sxs-lookup"><span data-stu-id="3331c-117">**PROBABILITY_VARIANCE**</span></span>  
 <span data-ttu-id="3331c-118">Значение в столбце является отклонением вероятности для связанного значения.</span><span class="sxs-lookup"><span data-stu-id="3331c-118">The value in the column is the variance of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="3331c-119">**PROBABILITY_STDEV**</span><span class="sxs-lookup"><span data-stu-id="3331c-119">**PROBABILITY_STDEV**</span></span>  
 <span data-ttu-id="3331c-120">Значение в столбце является среднеквадратичным отклонением вероятности для связанного значения.</span><span class="sxs-lookup"><span data-stu-id="3331c-120">The value in the column is the standard deviation of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="3331c-121">**ТЕХНИЧЕСКОЙ**</span><span class="sxs-lookup"><span data-stu-id="3331c-121">**SUPPORT**</span></span>  
 <span data-ttu-id="3331c-122">Значение в столбце является весом, коэффициентом репликации объекта, связанного значения.</span><span class="sxs-lookup"><span data-stu-id="3331c-122">The value in the column is the weight, or case replication factor, of the associated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3331c-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="3331c-123">See Also</span></span>  
 <span data-ttu-id="3331c-124">[Типы содержимого &#40;&#41;интеллектуального анализа данных](content-types-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3331c-124">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) </span></span>  
 <span data-ttu-id="3331c-125">[Структуры интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3331c-125">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="3331c-126">Типы данных (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="3331c-126">Data Types &#40;Data Mining&#41;</span></span>](data-types-data-mining.md)  
  
  
