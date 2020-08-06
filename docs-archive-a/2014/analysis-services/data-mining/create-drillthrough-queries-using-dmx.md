---
title: Создание запросов детализации с помощью расширений интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42c896ee-e5ee-4017-b66e-31d1fe66d369
author: minewiskan
ms.author: owend
ms.openlocfilehash: 618732bfe48f7b1fe777f7841d686b07877d10ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666278"
---
# <a name="create-drillthrough-queries-using-dmx"></a><span data-ttu-id="86c39-102">Создание запросов детализации с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="86c39-102">Create Drillthrough Queries using DMX</span></span>
  <span data-ttu-id="86c39-103">Для всех моделей с поддержкой детализации можно извлечь данные вариантов и структуры путем создания запроса DMX в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или любом другом клиенте с поддержкой DMX.</span><span class="sxs-lookup"><span data-stu-id="86c39-103">For all models that support drillthrough, you can retrieve case data and structure data by creating a DMX query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any other client that supports DMX.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="86c39-104">Для просмотра нужных данных необходимо включить детализацию и иметь соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="86c39-104">To view the data, drillthrough must have been enabled, and you must have the necessary permissions.</span></span>  
  
## <a name="specifying-drillthrough-options"></a><span data-ttu-id="86c39-105">Указание параметров детализации</span><span class="sxs-lookup"><span data-stu-id="86c39-105">Specifying Drillthrough Options</span></span>  
 <span data-ttu-id="86c39-106">Ниже приведен общий синтаксис для получения вариантов модели и структуры:</span><span class="sxs-lookup"><span data-stu-id="86c39-106">The general syntax is for retrieving model cases and structure cases is as follows:</span></span>  
  
```  
SELECT <model column list>, StructureColumn('<structure column name') FROM <modelname>.CASES  
```  
  
 <span data-ttu-id="86c39-107">Дополнительные сведения об использовании запросов DMX для возвращения данных по вариантам см. в разделах [SELECT FROM <модель>.CASES (расширения интеллектуального анализа данных)](/sql/dmx/select-from-model-content-dmx) и [SELECT FROM <структура>.CASES](/sql/dmx/select-from-structure-cases).</span><span class="sxs-lookup"><span data-stu-id="86c39-107">For additional information about using DMX queries to return case data, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) and [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="86c39-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="86c39-108">Examples</span></span>  
 <span data-ttu-id="86c39-109">Например, приведенный ниже DMX-запрос возвращает варианты для конкретной линейки продуктов в модели временных рядов.</span><span class="sxs-lookup"><span data-stu-id="86c39-109">The following DMX query returns the case data for a specific product series, from a time series model.</span></span> <span data-ttu-id="86c39-110">Этот запрос также возвращает столбец `Amount`, который не был использован в модели, но доступен в структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="86c39-110">The query also returns the column `Amount`, which was not used in the model but is available in the mining structure.</span></span>  
  
```  
SELECT [DateSeries], [Model Region], Quantity, StructureColumn('Amount') AS [M200 Pacific Amount]  
FROM Forecasting.CASES  
WHERE [Model Region] = 'M200 Pacific'  
```  
  
 <span data-ttu-id="86c39-111">Обратите внимание, что в этом примере столбец структуры переименован с использованием псевдонима.</span><span class="sxs-lookup"><span data-stu-id="86c39-111">Note that in this example, an alias has been used to rename the structure column.</span></span> <span data-ttu-id="86c39-112">Если столбцу структуры не присвоить псевдоним, то он будет возвращен с именем Expression.</span><span class="sxs-lookup"><span data-stu-id="86c39-112">If you do not assign an alias to the structure column, the column is returned with the name 'Expression'.</span></span> <span data-ttu-id="86c39-113">Это поведение по умолчанию для всех безымянных столбцов.</span><span class="sxs-lookup"><span data-stu-id="86c39-113">This is the default behavior for all unnamed columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c39-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="86c39-114">See Also</span></span>  
 <span data-ttu-id="86c39-115">[Запросы детализации &#40;&#41;интеллектуального анализа данных](drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="86c39-115">[Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="86c39-116">Детализация структур интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="86c39-116">Drillthrough on Mining Structures</span></span>](drillthrough-on-mining-structures.md)  
  
  
