---
title: Определение обучающих данных (мастер интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytrainingdata.f1
ms.assetid: cb04deeb-0f89-4bba-b3f1-efccada16825
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87a802256d287a3e8e9e7fb65bbd91687cb71a4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666760"
---
# <a name="specify-the-training-data-data-mining-wizard"></a><span data-ttu-id="bbca5-102">Определение обучающих данных (мастер интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="bbca5-102">Specify the Training Data (Data Mining Wizard)</span></span>
  <span data-ttu-id="bbca5-103">Определить столбцы, которые должны быть включены в структуру интеллектуального анализа данных, можно с помощью страницы **Определение обучающих данных** .</span><span class="sxs-lookup"><span data-stu-id="bbca5-103">Use the **Specify the Training Data** page to identify which columns to include in the mining structure.</span></span> <span data-ttu-id="bbca5-104">Для включения в структуру можно выбрать даже столбцы, которые не будут использоваться во всех моделях.</span><span class="sxs-lookup"><span data-stu-id="bbca5-104">You can select columns to include in the structure even if you do not use them in all models.</span></span> <span data-ttu-id="bbca5-105">Например, если необходимо выполнить детализацию столбцов модели интеллектуального анализа данных, можно включить их в структуру, а не в модель.</span><span class="sxs-lookup"><span data-stu-id="bbca5-105">For example, if you want to drill through to the columns from the mining model, you can include them in the structure but not in the model.</span></span>  
  
 <span data-ttu-id="bbca5-106">Каждая включенная в структуру таблица должна содержать по крайней мере один ключевой столбец.</span><span class="sxs-lookup"><span data-stu-id="bbca5-106">At least one key column is required for each table that is included in the structure.</span></span> <span data-ttu-id="bbca5-107">Выбор столбца в качестве ключа зависит от того, является ли таблица таблицей вариантов или вложенной таблицей.</span><span class="sxs-lookup"><span data-stu-id="bbca5-107">The column that you pick as the key depends on whether the table is a case table or a nested table.</span></span> <span data-ttu-id="bbca5-108">Для вложенной таблицы ключ часто является также прогнозируемым столбцом, а не реляционным внешним ключом.</span><span class="sxs-lookup"><span data-stu-id="bbca5-108">If the table is a nested table, the key is often also the predictable column, not the relational foreign key.</span></span> <span data-ttu-id="bbca5-109">Сведения о вложенных ключах см. в разделе [Вложенные таблицы (службы Analysis Services — интеллектуальный анализ данных)](data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="bbca5-109">To learn about nested keys, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bbca5-110">Различные алгоритмы интеллектуального анализа используют ключи по-разному.</span><span class="sxs-lookup"><span data-stu-id="bbca5-110">Different mining algorithms use keys differently.</span></span> <span data-ttu-id="bbca5-111">Сведения о различных видах ключей см. в разделе [Типы содержимого (интеллектуальный анализ данных)](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="bbca5-111">To learn about the different kinds of keys, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="bbca5-112">**Дополнительные сведения:** [Структуры интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/mining-structures-analysis-services-data-mining.md), [Столбцы модели интеллектуального анализа данных](data-mining/mining-model-columns.md), [Мастер интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Создание реляционной структуры интеллектуального анализа данных](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="bbca5-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="bbca5-113">Варианты</span><span class="sxs-lookup"><span data-stu-id="bbca5-113">Options</span></span>  
 <span data-ttu-id="bbca5-114">**Таблицы и столбцы**</span><span class="sxs-lookup"><span data-stu-id="bbca5-114">**Tables/Columns**</span></span>  
 <span data-ttu-id="bbca5-115">Отображает таблицы и столбцы, выбранные на предыдущей странице мастера.</span><span class="sxs-lookup"><span data-stu-id="bbca5-115">Displays the tables and columns that you selected on the previous page of the wizard.</span></span>  
  
 **\<check box>**  
 <span data-ttu-id="bbca5-116">Выберите столбцы для включения их в структуру интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="bbca5-116">Select the columns to include in the mining structure.</span></span>  
  
 <span data-ttu-id="bbca5-117">Если рассматриваемый источник данных включает вложенные таблицы или несколько представлений, разверните список столбцов, чтобы просмотреть вложенные таблицы.</span><span class="sxs-lookup"><span data-stu-id="bbca5-117">If your data source includes nested tables or multiple views, expand the column list to view the nested tables.</span></span>  
  
 <span data-ttu-id="bbca5-118">**Key**</span><span class="sxs-lookup"><span data-stu-id="bbca5-118">**Key**</span></span>  
 <span data-ttu-id="bbca5-119">Выберите, чтобы использовать столбец в качестве уникального идентификатора данных.</span><span class="sxs-lookup"><span data-stu-id="bbca5-119">Select to use the column as a unique identifier for the data.</span></span>  
  
 <span data-ttu-id="bbca5-120">Для таблицы вариантов ключом обычно является уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="bbca5-120">For a case table, the key is usually the unique identifier.</span></span>  
  
 <span data-ttu-id="bbca5-121">Для вложенной таблицы значение **Ключ** указывает идентификатор строки в контексте связанного варианта.</span><span class="sxs-lookup"><span data-stu-id="bbca5-121">For nested table, the **Key** indicates the identifier of a row in the context of the associated case.</span></span>  
  
 <span data-ttu-id="bbca5-122">**Ввод**</span><span class="sxs-lookup"><span data-stu-id="bbca5-122">**Input**</span></span>  
 <span data-ttu-id="bbca5-123">Выберите, чтобы использовать столбец для создания прогнозов.</span><span class="sxs-lookup"><span data-stu-id="bbca5-123">Select to use the column in creating predictions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bbca5-124">Этот столбец доступен, только если создается модель интеллектуального анализа данных вместе со структурой интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="bbca5-124">This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="bbca5-125">**Прогнозируемый**</span><span class="sxs-lookup"><span data-stu-id="bbca5-125">**Predictable**</span></span>  
 <span data-ttu-id="bbca5-126">Выберите, чтобы разрешить использование таблицы или столбца в качестве прогнозируемых на основе будущего дополнительного ввода.</span><span class="sxs-lookup"><span data-stu-id="bbca5-126">Select to enable the table or column to be predicted based on additional future input.</span></span>  
  
 <span data-ttu-id="bbca5-127">Если вложенная таблица также будет помечена как прогнозируемая, вся вложенная таблица становится прогнозируемой.</span><span class="sxs-lookup"><span data-stu-id="bbca5-127">If you also mark a nested table as predictable, the whole nested table becomes predictable.</span></span> <span data-ttu-id="bbca5-128">Если ни один столбец во вложенной таблице не помечен как входной или прогнозируемый, вложенная таблица будет отображена в структуре интеллектуального анализа данных, но не будет учитываться в модели.</span><span class="sxs-lookup"><span data-stu-id="bbca5-128">If no columns in the nested table are marked as input or predictable, the nested table will appear in the mining structure, but will be ignored in the model.</span></span>  
  
 <span data-ttu-id="bbca5-129">**Примечание.** Этот столбец доступен, только если создается модель интеллектуального анализа данных вместе со структурой интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="bbca5-129">**Note** This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="bbca5-130">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bbca5-130">**Suggest**</span></span>  
 <span data-ttu-id="bbca5-131">Нажмите, чтобы открыть диалоговое окно **Предложение связанных столбцов** , которое производит анализ образца данных для выявления входных столбцов с наиболее выраженной связью с выбранным **Прогнозируемым** столбцом на основе энтропии.</span><span class="sxs-lookup"><span data-stu-id="bbca5-131">Click to open the **Suggest Related Columns** dialog box, which performs an analysis on a sample of data to identify input columns that show the greatest relationship to the selected **Predictable** column based on entropy.</span></span> <span data-ttu-id="bbca5-132">Этот анализ также применяется к столбцам вложенных таблиц или структур интеллектуального анализа данных, основанных на источниках OLAP.</span><span class="sxs-lookup"><span data-stu-id="bbca5-132">This analysis also applies to nested table columns or mining structures that are based on OLAP sources.</span></span>  
  
 <span data-ttu-id="bbca5-133">**Примечание.** Этот столбец доступен, только если создается модель интеллектуального анализа данных вместе со структурой интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="bbca5-133">**Note** This column only available when you are creating a mining model together with the mining structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbca5-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="bbca5-134">See Also</span></span>  
 <span data-ttu-id="bbca5-135">[Справка F1 мастера интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="bbca5-135">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="bbca5-136">[Предлагать связанные столбцы &#40;мастер интеллектуального анализа данных&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="bbca5-136">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="bbca5-137">[Определение типов таблиц &#40;мастера интеллектуального анализа данных&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="bbca5-137">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="bbca5-138">Укажите содержимое столбца и тип данных &#40;мастер интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="bbca5-138">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
