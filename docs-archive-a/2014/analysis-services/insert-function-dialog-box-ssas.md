---
title: Диалоговое окно «Вставка функции» (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- SQL12.ASVS.BIDTOOLSET.INSERTFUNCTIONDB.F1
ms.assetid: c4b36d8f-2328-45f7-8bd4-cc0111571e25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0d92dd34e671dc026215d79e7eaed88bebfac15f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664619"
---
# <a name="insert-function-dialog-box-ssas"></a><span data-ttu-id="e9de7-102">Диалоговое окно «Вставка функции» (SSAS)</span><span class="sxs-lookup"><span data-stu-id="e9de7-102">Insert Function Dialog Box (SSAS)</span></span>
  <span data-ttu-id="e9de7-103">Диалоговое окно **Вставка функции** используется для выбора из списка тех функций, которые можно применять при построении формул.</span><span class="sxs-lookup"><span data-stu-id="e9de7-103">The **Insert Function** dialog box enables you to choose from a list of functions that can be used when building formulas.</span></span> <span data-ttu-id="e9de7-104">Для доступа к этому диалоговому окну из конструктора моделей нажмите кнопку функции (**fx**) в строке формул над каждой таблицей.</span><span class="sxs-lookup"><span data-stu-id="e9de7-104">To access this dialog box from the model designer, in the formula bar above each table, click the function (**fx**) button.</span></span> <span data-ttu-id="e9de7-105">Дополнительные сведения о выборе функций для применения в формулах см. в разделах «Введение в DAX» и «Построение формулы».</span><span class="sxs-lookup"><span data-stu-id="e9de7-105">For more information about choosing functions to use in formulas, see DAX Introduction and Build a Formula.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9de7-106">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9de7-106">Item</span></span>|<span data-ttu-id="e9de7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e9de7-107">Description</span></span>|  
|<span data-ttu-id="e9de7-108">**Выберите категорию**</span><span class="sxs-lookup"><span data-stu-id="e9de7-108">**Select a category**</span></span>|<span data-ttu-id="e9de7-109">Выберите категорию из списка, если имеется общее представление о том, какая функция нужна, или выберите **Все** для вывода списка функций в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="e9de7-109">If you have a general idea which kind of function you need, choose a category from the list; or select **All** to view an alphabetical list of functions.</span></span>|  
|<span data-ttu-id="e9de7-110">**Выбор функции**</span><span class="sxs-lookup"><span data-stu-id="e9de7-110">**Select a function**</span></span>|<span data-ttu-id="e9de7-111">Отображает список функций для выбранной категории.</span><span class="sxs-lookup"><span data-stu-id="e9de7-111">Displays a list of the functions in the selected category.</span></span>|  
|<span data-ttu-id="e9de7-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e9de7-112">**Description**</span></span>|<span data-ttu-id="e9de7-113">Отображает описание действия функции вместе с обязательными или необязательными аргументами, такими как имена столбцов, выражения и т. д.</span><span class="sxs-lookup"><span data-stu-id="e9de7-113">Displays a description of what the function does, together with any required or optional arguments, such as column names and expressions.</span></span>|  
  
## <a name="function-categories"></a><span data-ttu-id="e9de7-114">Категории функций</span><span class="sxs-lookup"><span data-stu-id="e9de7-114">Function Categories</span></span>  
 <span data-ttu-id="e9de7-115">В выражении анализа данных предусмотрены следующие типы категорий функций, которые представлены в диалоговом окне **Вставка функций** .</span><span class="sxs-lookup"><span data-stu-id="e9de7-115">Data Analysis Expressions (DAX) provides the following types of function categories in the **Insert Functions** dialog box.</span></span>  
  
 <span data-ttu-id="e9de7-116">Все</span><span class="sxs-lookup"><span data-stu-id="e9de7-116">All</span></span>  
  
 <span data-ttu-id="e9de7-117">Дата и время</span><span class="sxs-lookup"><span data-stu-id="e9de7-117">Date & Time</span></span>  
  
 <span data-ttu-id="e9de7-118">Filter</span><span class="sxs-lookup"><span data-stu-id="e9de7-118">Filter</span></span>  
  
 <span data-ttu-id="e9de7-119">Логический</span><span class="sxs-lookup"><span data-stu-id="e9de7-119">Logical</span></span>  
  
 <span data-ttu-id="e9de7-120">Арифметические и тригонометрические</span><span class="sxs-lookup"><span data-stu-id="e9de7-120">Math & Trig</span></span>  
  
 <span data-ttu-id="e9de7-121">Статистический</span><span class="sxs-lookup"><span data-stu-id="e9de7-121">Statistical</span></span>  
  
 <span data-ttu-id="e9de7-122">Text</span><span class="sxs-lookup"><span data-stu-id="e9de7-122">Text</span></span>  
  
## <a name="measures-and-formulas"></a><span data-ttu-id="e9de7-123">Меры и формулы</span><span class="sxs-lookup"><span data-stu-id="e9de7-123">Measures and Formulas</span></span>  
 <span data-ttu-id="e9de7-124">Диалоговое окно **Вставка функции** доступно только при построении формулы.</span><span class="sxs-lookup"><span data-stu-id="e9de7-124">The **Insert Function** dialog box is available only when you are building a formula.</span></span> <span data-ttu-id="e9de7-125">Вычисления можно создавать либо в вычисляемых столбцах, либо в сводных таблицах и сводных диаграммах.</span><span class="sxs-lookup"><span data-stu-id="e9de7-125">You can create calculations either in a calculated column, or in a PivotTable or PivotChart.</span></span> <span data-ttu-id="e9de7-126">Формулы, создаваемые явно для применения в сводной таблице, также называются *мерами*.</span><span class="sxs-lookup"><span data-stu-id="e9de7-126">Formulas that you build expressly for use in a PivotTable are also called *measures*.</span></span> <span data-ttu-id="e9de7-127">Дополнительные сведения см. в разделах [Создание вычисляемого столбца (табличные службы SSAS)](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) и [Создание мер и управление ими (табличные службы SSAS)](tabular-models/measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="e9de7-127">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) and [Create and Manage Measures &#40;SSAS Tabular&#41;](tabular-models/measures-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9de7-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9de7-128">See Also</span></span>  
 [<span data-ttu-id="e9de7-129">Вычисления (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="e9de7-129">Calculations &#40;SSAS Tabular&#41;</span></span>](tabular-models/calculations-ssas-tabular.md)  
  
  
