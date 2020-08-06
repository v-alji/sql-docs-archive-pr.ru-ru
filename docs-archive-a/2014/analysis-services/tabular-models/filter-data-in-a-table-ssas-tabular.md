---
title: Фильтрация данных в таблице (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.customfilterdb.f1
- sql12.asvs.bidtoolset.autofiltermenu.f1
- sql12.asvs.bidtoolset.notallitemsshowing.f1
ms.assetid: 3223059d-f525-4835-bf88-ebc195d9dbdc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f4003457df4068713e75e6bb5c0ab78c15ac03c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728838"
---
# <a name="filter-data-in-a-table-ssas-tabular"></a><span data-ttu-id="c3c1d-102">Фильтрация данных в таблице (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="c3c1d-102">Filter Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="c3c1d-103">Чтобы ограничить число строк, загружаемых в таблицу во время импорта данных, можно применить фильтры.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-103">You can apply filters when you import data to control the rows that are loaded into a table.</span></span> <span data-ttu-id="c3c1d-104">После выполнения импорта данных отдельные строки удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-104">After you have imported the data, you cannot delete individual rows.</span></span> <span data-ttu-id="c3c1d-105">Можно применить пользовательские фильтры для отображения строк.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-105">However, you can apply custom filters to control the way that rows are displayed.</span></span> <span data-ttu-id="c3c1d-106">Строки, не соответствующие условиям сортировки, скрыты.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-106">Rows that do not meet the filtering criteria are hidden.</span></span> <span data-ttu-id="c3c1d-107">Фильтрацию можно выполнять по одному или нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-107">You can filter by one or more columns.</span></span> <span data-ttu-id="c3c1d-108">Фильтры добавляются друг к другу, что означает, что каждый дополнительный фильтр основывается на текущем фильтре и еще более ограничивает подмножество данных.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-108">Filters are additive, which means that each additional filter is based on the current filter and further reduces the subset of data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3c1d-109">Окно предварительного просмотра фильтра ограничивает количество отображаемых значений.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-109">The filter preview window limits the number of different values displayed.</span></span> <span data-ttu-id="c3c1d-110">При превышении этого ограничения выводится сообщение.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-110">If the limit is exceeded, a message is displayed.</span></span>  
  
### <a name="to-filter-data-based-on-column-values"></a><span data-ttu-id="c3c1d-111">Фильтрация данных на основе значений столбцов</span><span class="sxs-lookup"><span data-stu-id="c3c1d-111">To filter data based on column values</span></span>  
  
1.  <span data-ttu-id="c3c1d-112">В конструкторе моделей выберите таблицу и щелкните стрелку в заголовке столбца, по которому необходимо выполнить фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-112">In the model designer, select a table, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="c3c1d-113">В меню автофильтра выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="c3c1d-114">В списке значений столбца выберите или удалите одно или несколько значений для фильтрации, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-114">In the list of column values, select or clear one or more values to filter by, and then click **OK**.</span></span>  
  
         <span data-ttu-id="c3c1d-115">Если количество значений слишком велико, некоторые элементы могут не войти в список.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-115">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="c3c1d-116">Появится сообщение «Слишком много элементов для отображения».</span><span class="sxs-lookup"><span data-stu-id="c3c1d-116">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="c3c1d-117">Щелкните **Числовые фильтры** или **текстовые фильтры** (в зависимости от типа столбца), а затем выберите команду оператора сравнения (например, **равно**) или щелкните **Настраиваемый фильтр**.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-117">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as **Equals**), or click **Custom Filter**.</span></span> <span data-ttu-id="c3c1d-118">В диалоговом окне **Настраиваемый фильтр** создайте фильтр и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-118">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
### <a name="to-clear-a-filter-for-a-column"></a><span data-ttu-id="c3c1d-119">Очистка фильтра для столбца</span><span class="sxs-lookup"><span data-stu-id="c3c1d-119">To clear a filter for a column</span></span>  
  
1.  <span data-ttu-id="c3c1d-120">Нажмите стрелку в заголовке столбца, для которого необходимо очистить фильтр.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-120">Click the arrow in the header of the column for which you want to clear a filter.</span></span>  
  
2.  <span data-ttu-id="c3c1d-121">Щелкните \*\*Очистить фильтр из \<Column Name> \*\*.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-121">Click **Clear Filter from \<Column Name>**.</span></span>  
  
### <a name="to-clear-all-filters-for-a-table"></a><span data-ttu-id="c3c1d-122">Очистка всех фильтров для таблицы</span><span class="sxs-lookup"><span data-stu-id="c3c1d-122">To clear all filters for a table</span></span>  
  
1.  <span data-ttu-id="c3c1d-123">В конструкторе моделей выберите таблицу, для которой необходимо сбросить фильтры.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-123">In the model designer, select the table for which you want to clear filters.</span></span>  
  
2.  <span data-ttu-id="c3c1d-124">В меню **Столбец** выберите пункт **Очистить все фильтры**.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-124">Click on the **Column** menu, and then click **Clear All Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c1d-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3c1d-125">See Also</span></span>  
 <span data-ttu-id="c3c1d-126">[Фильтрация и сортировка данных &#40;табличных&#41;SSAS](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c3c1d-126">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="c3c1d-127">[Перспективы &#40;табличные&#41;SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c3c1d-127">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c3c1d-128">Роли (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="c3c1d-128">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
