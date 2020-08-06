---
title: Свойства полнотекстового индекса (страница «Столбцы») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.columns.f1
ms.assetid: 75e52edb-0d07-4393-9345-8b5af4561e35
author: rothja
ms.author: jroth
ms.openlocfilehash: f947af04463948ef551c6df866d5a306c248c6b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669062"
---
# <a name="full-text-index-properties-columns-page"></a><span data-ttu-id="58192-102">Свойства полнотекстового индекса (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="58192-102">Full-Text Index Properties (Columns Page)</span></span>
  <span data-ttu-id="58192-103">**Просмотр или изменение свойств полнотекстового индекса**</span><span class="sxs-lookup"><span data-stu-id="58192-103">**To view or change the properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="58192-104">Управление полнотекстовыми индексами</span><span class="sxs-lookup"><span data-stu-id="58192-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="58192-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="58192-105">UI element list</span></span>  
 <span data-ttu-id="58192-106">**Уникальный индекс**</span><span class="sxs-lookup"><span data-stu-id="58192-106">**Unique index**</span></span>  
 <span data-ttu-id="58192-107">Выберите индекс из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="58192-107">Select an index from the drop down list.</span></span> <span data-ttu-id="58192-108">Индекс должен иметь один ключевой столбец, быть уникальным и не допускающим значения NULL.</span><span class="sxs-lookup"><span data-stu-id="58192-108">The index must be a single-key-column, unique, non-nullable index.</span></span>  
  
 <span data-ttu-id="58192-109">**Выберите подходящие столбцы, для которых будет построен полнотекстовый индекс**</span><span class="sxs-lookup"><span data-stu-id="58192-109">**Select the eligible columns that will be full-text indexed**</span></span>  
 <span data-ttu-id="58192-110">В сетке отображаются столбцы таблицы, доступные для этого полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="58192-110">The grid displays the table columns that are available for this full-text index.</span></span> <span data-ttu-id="58192-111">Для столбцов, которые включены в полнотекстовый индекс, установлены флажки.</span><span class="sxs-lookup"><span data-stu-id="58192-111">Columns that are currently full-text indexed are checked.</span></span> <span data-ttu-id="58192-112">Можно установить флажки для дополнительных столбцов, которые нужно включить в полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="58192-112">Optionally, you can check additional columns that you want to be full-text indexed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="58192-113">Убедитесь, что выбран хотя бы один столбец, и нажмите кнопку «ОК».</span><span class="sxs-lookup"><span data-stu-id="58192-113">Ensure that at least one column is checked before you click OK.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="58192-114">**Доступные столбцы**</span><span class="sxs-lookup"><span data-stu-id="58192-114">**Available Columns**</span></span>|<span data-ttu-id="58192-115">Имя столбца.</span><span class="sxs-lookup"><span data-stu-id="58192-115">The column name.</span></span>|  
|<span data-ttu-id="58192-116">**Язык для средства разбиения по словам**</span><span class="sxs-lookup"><span data-stu-id="58192-116">**Language for Word Breaker**</span></span>|<span data-ttu-id="58192-117">Язык, для которого средства разбиения по словам и парадигматические модули выполняют лингвистический анализ данных, проходящих полнотекстовое индексирование.</span><span class="sxs-lookup"><span data-stu-id="58192-117">The language whose word breakers and stemmers perform linguistic analysis on all full-text indexed data.</span></span><br /><br /> <span data-ttu-id="58192-118">Дополнительные сведения см. в статьях [Настройка и Управление разделителями слов и парадигматические модули для поиска](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) и [Выбор языка при создании полнотекстового индекса](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span><span class="sxs-lookup"><span data-stu-id="58192-118">For more information, see [Configure and Manage Word Breakers and Stemmers for Search](../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md) and [Choose a Language When Creating a Full-Text Index](../relational-databases/search/choose-a-language-when-creating-a-full-text-index.md).</span></span>|  
|<span data-ttu-id="58192-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="58192-119">**Type**</span></span>|<span data-ttu-id="58192-120">Имя столбца таблицы, который содержит тип документа выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="58192-120">The name of the table column that holds the document type of the selected column.</span></span> <span data-ttu-id="58192-121">Это свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="58192-121">This is a read-only property.</span></span>|  
|<span data-ttu-id="58192-122">**Статистическая семантика**</span><span class="sxs-lookup"><span data-stu-id="58192-122">**Statistical Semantics**</span></span>|<span data-ttu-id="58192-123">Укажите, следует ли включить статистическое семантическое индексирование для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="58192-123">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="58192-124">Дополнительные сведения см. в разделе [Семантический поиск (SQL Server)](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="58192-124">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="58192-125">Если **Язык** выбран до выбора режима **Статистическая семантика**и выбранный язык не имеет связанной семантической модели языка, флажок **Статистическая семантика** будет недоступным.</span><span class="sxs-lookup"><span data-stu-id="58192-125">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="58192-126">Если режим **Статистическая семантика** выбран до выбора **Языка**, в раскрывающемся поле со списком будут доступны только языки, имеющие семантическую модель языка.</span><span class="sxs-lookup"><span data-stu-id="58192-126">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58192-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="58192-127">See Also</span></span>  
 [<span data-ttu-id="58192-128">Заполнение полнотекстовых индексов</span><span class="sxs-lookup"><span data-stu-id="58192-128">Populate Full-Text Indexes</span></span>](../relational-databases/search/populate-full-text-indexes.md)  
  
  
