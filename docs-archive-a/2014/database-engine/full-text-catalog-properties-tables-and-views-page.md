---
title: Свойства полнотекстового каталога (страница «таблицы и представления») | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.tablesviews.f1
ms.assetid: 2d45fcd2-0f0f-4167-9027-316d6696c106
author: rothja
ms.author: jroth
ms.openlocfilehash: eb4d968af6c550d19fbb8934b5d76a1bd63cb8da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740292"
---
# <a name="full-text-catalog-properties-tables-and-views-page"></a><span data-ttu-id="21ae1-102">Свойства полнотекстового каталога (страница "Таблицы и представления")</span><span class="sxs-lookup"><span data-stu-id="21ae1-102">Full-Text Catalog Properties (Tables and Views Page)</span></span>
  <span data-ttu-id="21ae1-103">Используйте это диалоговое окно для просмотра и редактирования таблиц и представлений, назначенных полнотекстовому каталогу.</span><span class="sxs-lookup"><span data-stu-id="21ae1-103">Use this dialog page to view or modify the tables and views that are assigned to the full-text catalog.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="21ae1-104">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="21ae1-104">UI element list</span></span>  
 <span data-ttu-id="21ae1-105">**Все подходящие объекты таблиц и представлений в этой базе данных**</span><span class="sxs-lookup"><span data-stu-id="21ae1-105">**All eligible table/view objects in this database**</span></span>  
 <span data-ttu-id="21ae1-106">Перечисляет таблицы и представления, для которых задан уникальный индекс, но они еще не входят в полнотекстовый каталог.</span><span class="sxs-lookup"><span data-stu-id="21ae1-106">Lists the tables and views that have a unique index defined on them, but are not already a part of the full-text catalog.</span></span> <span data-ttu-id="21ae1-107">Чтобы выбрать таблицу или представление и назначить их каталогу, выберите элементы в списке и нажмите кнопку "->".</span><span class="sxs-lookup"><span data-stu-id="21ae1-107">To select a table or view and assign it to the catalog, select the items in the list box and press the "->" button.</span></span>  
  
 <span data-ttu-id="21ae1-108">**Объекты таблиц и представлений, связанные с данным каталогом**</span><span class="sxs-lookup"><span data-stu-id="21ae1-108">**Table/view objects assigned to the catalog**</span></span>  
 <span data-ttu-id="21ae1-109">Перечисляет таблицы и представления, назначенные полнотекстовому каталогу</span><span class="sxs-lookup"><span data-stu-id="21ae1-109">Lists the tables and views that are currently assigned to the full-text catalog</span></span>  
  
## <a name="selected-object-properties"></a><span data-ttu-id="21ae1-110">Свойства выбранного объекта</span><span class="sxs-lookup"><span data-stu-id="21ae1-110">Selected Object Properties</span></span>  
 <span data-ttu-id="21ae1-111">**Свойства выбранного объекта**</span><span class="sxs-lookup"><span data-stu-id="21ae1-111">**Selected object properties**</span></span>  
 <span data-ttu-id="21ae1-112">Отображает свойства выбранного объекта в поле со списком объектов, назначенных каталогу.</span><span class="sxs-lookup"><span data-stu-id="21ae1-112">Displays the properties of the selected object in the list box of objects assigned to the catalog.</span></span>  
  
 <span data-ttu-id="21ae1-113">**Уникальный индекс**</span><span class="sxs-lookup"><span data-stu-id="21ae1-113">**Unique Index**</span></span>  
 <span data-ttu-id="21ae1-114">Перечисляет доступные уникальные индексы таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="21ae1-114">Lists the available unique indexes of the table or view.</span></span>  
  
 <span data-ttu-id="21ae1-115">**Таблица поддерживает полнотекстовый поиск**</span><span class="sxs-lookup"><span data-stu-id="21ae1-115">**Table is full-text enabled**</span></span>  
 <span data-ttu-id="21ae1-116">Установите этот флажок, чтобы включить полнотекстовый индекс для таблицы.</span><span class="sxs-lookup"><span data-stu-id="21ae1-116">Select this check box to enable the full-text index on the table.</span></span> <span data-ttu-id="21ae1-117">Снимите этот флажок, чтобы отключить полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="21ae1-117">Clear the check box to disable the full-text index.</span></span>  
  
## <a name="eligible-columns-grid"></a><span data-ttu-id="21ae1-118">Сетка подходящих столбцов</span><span class="sxs-lookup"><span data-stu-id="21ae1-118">Eligible Columns Grid</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21ae1-119">**Доступные столбцы**</span><span class="sxs-lookup"><span data-stu-id="21ae1-119">**Available Columns**</span></span>|<span data-ttu-id="21ae1-120">Отображает все столбцы, поддерживающие полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="21ae1-120">Displays all the columns that are full-text indexed.</span></span> <span data-ttu-id="21ae1-121">Установите этот флажок, чтобы добавить столбец в полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="21ae1-121">Select a check box to add a column to the full-text index.</span></span>|  
|<span data-ttu-id="21ae1-122">**Язык для средства разбиения по словам**</span><span class="sxs-lookup"><span data-stu-id="21ae1-122">**Language for Word Breaker**</span></span>|<span data-ttu-id="21ae1-123">Отображает язык средства разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="21ae1-123">Displays the language of the word breaker.</span></span>|  
|<span data-ttu-id="21ae1-124">**Столбец типа данных**</span><span class="sxs-lookup"><span data-stu-id="21ae1-124">**Data Type Column**</span></span>|<span data-ttu-id="21ae1-125">Перечисляет имя столбца в таблице, который содержит тип документа столбца, указанного в списке **Доступные столбцы** , если столбец является столбцом `varbinary(max)` или `image` .</span><span class="sxs-lookup"><span data-stu-id="21ae1-125">Lists the name of the column in the table that holds the document type of the column listed in **Available Columns** if the column is a `varbinary(max)` or `image` column.</span></span>|  
|<span data-ttu-id="21ae1-126">**Статистическая семантика**</span><span class="sxs-lookup"><span data-stu-id="21ae1-126">**Statistical Semantics**</span></span>|<span data-ttu-id="21ae1-127">Укажите, следует ли включить статистическое семантическое индексирование для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="21ae1-127">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="21ae1-128">Дополнительные сведения см. в разделе [Семантический поиск (SQL Server)](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="21ae1-128">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="21ae1-129">Если **Язык** выбран до выбора режима **Статистическая семантика**и выбранный язык не имеет связанной семантической модели языка, флажок **Статистическая семантика** будет недоступным.</span><span class="sxs-lookup"><span data-stu-id="21ae1-129">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="21ae1-130">Если режим **Статистическая семантика** выбран до выбора **Языка**, в раскрывающемся поле со списком будут доступны только языки, имеющие семантическую модель языка.</span><span class="sxs-lookup"><span data-stu-id="21ae1-130">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="track-changes"></a><span data-ttu-id="21ae1-131">Отслеживать изменения</span><span class="sxs-lookup"><span data-stu-id="21ae1-131">Track Changes</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21ae1-132">**Автоматический**</span><span class="sxs-lookup"><span data-stu-id="21ae1-132">**Automatic**</span></span>|<span data-ttu-id="21ae1-133">Полнотекстовый индекс обновляется автоматически при редактировании, добавлении или удалении данных в базовой таблице.</span><span class="sxs-lookup"><span data-stu-id="21ae1-133">The full-text index is automatically updated when the data in the underlying table is modified, added, or deleted.</span></span>|  
|<span data-ttu-id="21ae1-134">**Manual** (Вручную)</span><span class="sxs-lookup"><span data-stu-id="21ae1-134">**Manual**</span></span>|<span data-ttu-id="21ae1-135">Когда происходит изменение, добавление или удаление индексированных данных, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] отслеживает изменения.</span><span class="sxs-lookup"><span data-stu-id="21ae1-135">When data is modified, added, or deleted in the indexed data, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tracks the changes.</span></span> <span data-ttu-id="21ae1-136">Если активировано отслеживание изменений по параметру **Вручную** , индекс автоматически не обновляется этими изменениями.</span><span class="sxs-lookup"><span data-stu-id="21ae1-136">When **Manual** change tracking is in effect, the index is not automatically updated with these changes.</span></span> <span data-ttu-id="21ae1-137">Вместо этого администратор может применить изменения вручную с помощью [инструкции ALTER FULLTEXT INDEX... ЗАПУСК инструкции обновления заполнения](/sql/t-sql/statements/alter-fulltext-index-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="21ae1-137">Instead, an administrator can apply the changes manually by using an [ALTER FULLTEXT INDEX ... START UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) statement.</span></span>|  
|<span data-ttu-id="21ae1-138">**Не отслеживать изменения**</span><span class="sxs-lookup"><span data-stu-id="21ae1-138">**Do not track change**</span></span>|<span data-ttu-id="21ae1-139">Если этот параметр включен, изменения в индексированные данные каталога не регистрируются.</span><span class="sxs-lookup"><span data-stu-id="21ae1-139">With this option in effect, changes to the indexed data in the catalog are not recorded.</span></span> <span data-ttu-id="21ae1-140">Администратор должен построить индекс с помощью инструкции ALTER FULLTEXT INDEX с параметром FULL POPULATION или INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="21ae1-140">An administrator must build the index by using ALTER FULLTEXT INDEX with either FULL POPULATION or INCREMENTAL POPULATION.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21ae1-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="21ae1-141">See Also</span></span>  
 <span data-ttu-id="21ae1-142">[CREATE FULLTEXT CATALOG (Transact-SQL)](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="21ae1-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span></span>  
 <span data-ttu-id="21ae1-143">[&#41;Transact-SQL &#40;инструкции ALTER FULLTEXT CATALOG](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="21ae1-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="21ae1-144">Заполнение полнотекстовых индексов</span><span class="sxs-lookup"><span data-stu-id="21ae1-144">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
