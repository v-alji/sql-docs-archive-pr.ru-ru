---
title: Срез исходного куба (мастер интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.slicesourcecube.f1
ms.assetid: 16485608-d3b9-49ee-8baa-948038cdd7ec
author: minewiskan
ms.author: owend
ms.openlocfilehash: 762248d4c2a268ac36b0dfa3ffeba20123017017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736860"
---
# <a name="slice-source-cube-data-mining-wizard"></a><span data-ttu-id="a5824-102">Срез исходного куба (мастер интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="a5824-102">Slice Source Cube (Data Mining Wizard)</span></span>
  <span data-ttu-id="a5824-103">Можно использовать диалоговое окно **Срез исходного куба** для ограничения данных, используемых при обучении модели.</span><span class="sxs-lookup"><span data-stu-id="a5824-103">You can use the **Slice Source Cube** dialog box to restrict the data used to train the model.</span></span> <span data-ttu-id="a5824-104">Обычно куб содержит данные, относящиеся к разным измерениям и атрибутам, такие как все магазины, все регионы и все товары.</span><span class="sxs-lookup"><span data-stu-id="a5824-104">Typically a cube contains data related to many different dimensions and attributes, such as all stores, all regions, and all products.</span></span> <span data-ttu-id="a5824-105">Не имеет смысла обучать модель на неограниченных сочетаниях атрибутов, поэтому следует использовать это диалоговое окно в целях выбора конкретного набора для использования в обучении модели.</span><span class="sxs-lookup"><span data-stu-id="a5824-105">It is not practical to train a model on unlimited combinations of attributes, so you use this dialog box to choose a specific set to use in training a model.</span></span>  
  
 <span data-ttu-id="a5824-106">Например, в кубе AdventureWorks можно применить разделение по определенной линии товаров, региону и году для получения доступа к части данных.</span><span class="sxs-lookup"><span data-stu-id="a5824-106">For example, in the AdventureWorks cube, you might slice by a particular product line, region, or year, to get a portion of the data.</span></span>  
  
 <span data-ttu-id="a5824-107">Если вы не знакомы со срезами и кубами, рекомендуется просмотреть следующие статьи.</span><span class="sxs-lookup"><span data-stu-id="a5824-107">If you are unfamiliar with slices and cubes, we recommend that you review these articles:</span></span>  
  
-   [<span data-ttu-id="a5824-108">Задайте &#40;свойству среза секции Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a5824-108">Set the Partition Slice Property &#40;Analysis Services&#41;</span></span>](multidimensional-models/set-the-partition-slice-property-analysis-services.md)  
  
-   [<span data-ttu-id="a5824-109">Создание локальной секции и управление ею (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="a5824-109">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](multidimensional-models/create-and-manage-a-local-partition-analysis-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="a5824-110">Обратите внимание, что динамические функции многомерных выражений (такие как [Generate (многомерное выражение)](/sql/mdx/generate-mdx) или [Except (многомерное выражение)](/sql/mdx/except-mdx-function)) не поддерживаются в свойстве Slice для секций.</span><span class="sxs-lookup"><span data-stu-id="a5824-110">Note that dynamic MDX functions (such as [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) or [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) are not supported in the Slice property for partitions.</span></span> <span data-ttu-id="a5824-111">Необходимо определить срез с помощью явных кортежей или ссылок на элементы.</span><span class="sxs-lookup"><span data-stu-id="a5824-111">You must define the slice by using explicit tuples or member references.</span></span>  
>   
>  <span data-ttu-id="a5824-112">Например, вместо использования [: &#40;range&#41; &#40;&#41;многомерных выражений](/sql/mdx/range-mdx) для определения диапазона необходимо перечислить каждый элемент по определенному году.</span><span class="sxs-lookup"><span data-stu-id="a5824-112">For example, rather than using  [: &#40;Range&#41; &#40;MDX&#41;](/sql/mdx/range-mdx) to define a range, you would need to enumerate each member by the specific years.</span></span>  
>   
>  <span data-ttu-id="a5824-113">Если необходимо определить сложный срез, рекомендуется идентифицировать кортежи в срезе с помощью скрипта изменения XMLA.</span><span class="sxs-lookup"><span data-stu-id="a5824-113">If you need to define a complex slice, we recommend that you define the tuples in the slice by using an XMLA Alter script.</span></span> <span data-ttu-id="a5824-114">Затем вы можете использовать средство командной строки ascmd или SSIS [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) для запуска скрипта и создания указанного набора элементов непосредственно перед секционированием.</span><span class="sxs-lookup"><span data-stu-id="a5824-114">Then, you can use either the ascmd command-line tool or the SSIS [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) to run the script and create the specified set of members immediately before you process the partition.</span></span>  
  
 <span data-ttu-id="a5824-115">**Дополнительные сведения:** [Мастер интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Создание реляционной структуры интеллектуального анализа данных](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="a5824-115">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="a5824-116">Варианты</span><span class="sxs-lookup"><span data-stu-id="a5824-116">Options</span></span>  
 <span data-ttu-id="a5824-117">**Измерение**</span><span class="sxs-lookup"><span data-stu-id="a5824-117">**Dimension**</span></span>  
 <span data-ttu-id="a5824-118">Выберите измерение, которое необходимо разделить.</span><span class="sxs-lookup"><span data-stu-id="a5824-118">Select the dimension that you want to slice.</span></span>  
  
 <span data-ttu-id="a5824-119">**Иерархия**</span><span class="sxs-lookup"><span data-stu-id="a5824-119">**Hierarchy**</span></span>  
 <span data-ttu-id="a5824-120">Выберите иерархию, которую необходимо разделить.</span><span class="sxs-lookup"><span data-stu-id="a5824-120">Select the hierarchy that you want to slice.</span></span> <span data-ttu-id="a5824-121">Можно выбрать любой уровень иерархии, но атрибуты, используемые в модели, будут представлены только на выбранном уровне.</span><span class="sxs-lookup"><span data-stu-id="a5824-121">You can choose any level of a hierarchy, but the attributes used in the model will be only at the level that you choose.</span></span>  
  
 <span data-ttu-id="a5824-122">Например, если выбрать иерархию Geography и выбрать в качестве уровня Country, то нельзя создать модель, в которой используется City в качестве атрибута.</span><span class="sxs-lookup"><span data-stu-id="a5824-122">For example, if you choose the Geography hierarchy, and select Country as the level, you cannot build a model that uses City as the attributes.</span></span> <span data-ttu-id="a5824-123">И наоборот, если выбран City как уровень иерархии, по которому производится срез, то нельзя создать модель интеллектуального анализа данных на основе Country.</span><span class="sxs-lookup"><span data-stu-id="a5824-123">Conversely, if you choose City as the level of the hierarchy on which to slice, you cannot create a mining model based on Country.</span></span>  
  
 <span data-ttu-id="a5824-124">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="a5824-124">**Operator**</span></span>  
 <span data-ttu-id="a5824-125">Выберите оператор для использования при создании выражения среза.</span><span class="sxs-lookup"><span data-stu-id="a5824-125">Select the operator to use in building a slice expression.</span></span>  
  
 <span data-ttu-id="a5824-126">Например, если в качестве иерархии выбрана география, можно выбрать оператор =, а затем ввести "Европа" в качестве фильтра, чтобы получить данные куба только для Европы.</span><span class="sxs-lookup"><span data-stu-id="a5824-126">For example, if you chose Geography as the hierarchy, you could select the operator = and then type "Europe" as the filter, to get cube data for Europe only.</span></span>  
  
 <span data-ttu-id="a5824-127">**Критерий фильтра**</span><span class="sxs-lookup"><span data-stu-id="a5824-127">**Filter Expression**</span></span>  
 <span data-ttu-id="a5824-128">Введите выражение, используемое в качестве критерия фильтрации куба в выбранном измерении.</span><span class="sxs-lookup"><span data-stu-id="a5824-128">Type an expression to use as a criterion when filtering the cube on the selected dimension.</span></span>  
  
 <span data-ttu-id="a5824-129">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="a5824-129">**Parameters**</span></span>  
 <span data-ttu-id="a5824-130">Этот параметр не используется для моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="a5824-130">This option is not used for data mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5824-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="a5824-131">See Also</span></span>  
 <span data-ttu-id="a5824-132">[Завершение работы мастера &#40;мастера интеллектуального анализа данных&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="a5824-132">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="a5824-133">[Справка F1 мастера интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a5824-133">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="a5824-134">Определение использования столбцов модели интеллектуального анализа данных &#40;мастер интеллектуального анализа&#41;</span><span class="sxs-lookup"><span data-stu-id="a5824-134">Specify Mining Model Column Usage &#40;Data Mining Wizard&#41;</span></span>](specify-mining-model-column-usage-data-mining-wizard.md)  
  
  
