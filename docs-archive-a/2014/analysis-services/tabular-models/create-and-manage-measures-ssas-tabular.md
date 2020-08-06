---
title: Создание мер и управление ими (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: edc1a4b2-96d3-4f34-bb70-6cacec79e819
author: minewiskan
ms.author: owend
ms.openlocfilehash: da507bf48b285a1414ffb85ba79da50508a2ae2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657923"
---
# <a name="create-and-manage-measures-ssas-tabular"></a><span data-ttu-id="06ac2-102">Создание мер и управление ими (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="06ac2-102">Create and Manage Measures (SSAS Tabular)</span></span>
  <span data-ttu-id="06ac2-103">Мера — это формула, которая создается специально для использования в отчете или сводной таблице (или сводной диаграмме) Excel.</span><span class="sxs-lookup"><span data-stu-id="06ac2-103">A measure is a formula that is created for use in a report or Excel PivotTable (or PivotChart).</span></span> <span data-ttu-id="06ac2-104">Меры могут быть основаны на стандартных агрегатных функциях, например COUNT или SUM, либо на пользовательских формулах на языке выражений анализа данных (DAX).</span><span class="sxs-lookup"><span data-stu-id="06ac2-104">Measures can be based on standard aggregation functions, such as COUNT or SUM, or you can define your own formula by using DAX.</span></span> <span data-ttu-id="06ac2-105">Задачи в этом разделе описывают создание мер и управление ими с помощью сетки мер таблицы.</span><span class="sxs-lookup"><span data-stu-id="06ac2-105">The tasks in this topic describe how to create and manage measures by using a table's measure grid.</span></span>  
  
 <span data-ttu-id="06ac2-106">В этот раздел включены следующее задачи:</span><span class="sxs-lookup"><span data-stu-id="06ac2-106">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="06ac2-107">Создание меры с помощью стандартной формулы агрегата</span><span class="sxs-lookup"><span data-stu-id="06ac2-107">To create a measure using a standard aggregation formula</span></span>](#bkmk_create_stand)  
  
-   [<span data-ttu-id="06ac2-108">Создание меры с помощью пользовательской формулы</span><span class="sxs-lookup"><span data-stu-id="06ac2-108">To create a measure using a custom formula</span></span>](#bkmk_create_custom)  
  
-   [<span data-ttu-id="06ac2-109">Изменение свойств меры</span><span class="sxs-lookup"><span data-stu-id="06ac2-109">To edit measure properties</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="06ac2-110">Переименование меры</span><span class="sxs-lookup"><span data-stu-id="06ac2-110">To rename a measure</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="06ac2-111">Удаление меры</span><span class="sxs-lookup"><span data-stu-id="06ac2-111">To delete a measure</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="06ac2-112">Задания</span><span class="sxs-lookup"><span data-stu-id="06ac2-112">Tasks</span></span>  
 <span data-ttu-id="06ac2-113">Для создания мер и управления ими будет использоваться сетка мер таблицы.</span><span class="sxs-lookup"><span data-stu-id="06ac2-113">To create and manage measures, you will use a table's measure grid.</span></span> <span data-ttu-id="06ac2-114">Просматривать сетку мер таблицы в конструкторе моделей можно только в представлении данных.</span><span class="sxs-lookup"><span data-stu-id="06ac2-114">You can view the measure grid for a table in the model designer in Data View only.</span></span> <span data-ttu-id="06ac2-115">В представлении диаграммы создавать меры или увидеть сетку мер нельзя. Однако в этом представлении отображаются существующие меры.</span><span class="sxs-lookup"><span data-stu-id="06ac2-115">You cannot create measures or view the measure grid when in Diagram View; however, you can view existing measures in Diagram View.</span></span> <span data-ttu-id="06ac2-116">Чтобы отобразить сетку мер таблицы, в меню **Таблица** выберите команду **Показать сетку мер**.</span><span class="sxs-lookup"><span data-stu-id="06ac2-116">To show the measure grid for a table, click the **Table** menu, and then click **Show Measure Grid**.</span></span>  
  
###  <a name="to-create-a-measure-using-a-standard-aggregation-formula"></a><a name="bkmk_create_stand"></a><span data-ttu-id="06ac2-117">Создание меры с помощью стандартной формулы статистической обработки</span><span class="sxs-lookup"><span data-stu-id="06ac2-117">To create a measure using a standard aggregation formula</span></span>  
  
-   <span data-ttu-id="06ac2-118">Щелкните столбец, для которого необходимо создать меру, а затем выберите меню **Столбец** , наведите указатель мыши на пункт **AutoSum**и выберите тип агрегата.</span><span class="sxs-lookup"><span data-stu-id="06ac2-118">Click on the column for which you want to create the measure, then click the **Column** menu, then point to **AutoSum**, and then click an aggregation type.</span></span>  
  
     <span data-ttu-id="06ac2-119">Мера создается автоматически именем по умолчанию, за которым следует формула в первой ячейке сетки мер, расположенной непосредственно под столбцом.</span><span class="sxs-lookup"><span data-stu-id="06ac2-119">The measure will be created automatically with a default name, followed by the formula in the first cell in the measure grid directly beneath the column.</span></span>  
  
###  <a name="to-create-a-measure-using-a-custom-formula"></a><a name="bkmk_create_custom"></a> <span data-ttu-id="06ac2-120">Создание меры с помощью пользовательской формулы</span><span class="sxs-lookup"><span data-stu-id="06ac2-120">To create a measure using a custom formula</span></span>  
  
-   <span data-ttu-id="06ac2-121">В сетке мер под столбцом, для которого необходимо создать меру, щелкните ячейку, а затем в строке формулы введите имя, затем двоеточие (:), знак равенства (=) и формулу.</span><span class="sxs-lookup"><span data-stu-id="06ac2-121">In the measure grid, beneath the column for which you want to create the measure, click a cell, then in the formula bar, type a name, followed by a colon (:), followed by an equals sign (=), followed by the formula.</span></span> <span data-ttu-id="06ac2-122">Нажмите клавишу ВВОД, чтобы принять формулу.</span><span class="sxs-lookup"><span data-stu-id="06ac2-122">Press ENTER to accept the formula.</span></span>  
  
###  <a name="to-edit-measure-properties"></a><a name="bkmk_edit"></a><span data-ttu-id="06ac2-123">Изменение свойств меры</span><span class="sxs-lookup"><span data-stu-id="06ac2-123">To edit measure properties</span></span>  
  
-   <span data-ttu-id="06ac2-124">Щелкните меру в сетке мер, а затем в окне **Свойства** введите или выберите другое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="06ac2-124">In the measure grid, click a measure, and then In the **Properties** window, type or select a different property value.</span></span>  
  
###  <a name="to-rename-a-measure"></a><a name="bkmk_rename"></a><span data-ttu-id="06ac2-125">Переименование меры</span><span class="sxs-lookup"><span data-stu-id="06ac2-125">To rename a measure</span></span>  
  
-   <span data-ttu-id="06ac2-126">Щелкните меру в сетке мер, а затем в окне **Свойства** в поле **Имя меры**введите новое имя и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="06ac2-126">In the measure grid, click on a measure, and then In the **Properties** window, in **Measure Name**, type a new name, and then click ENTER.</span></span>  
  
     <span data-ttu-id="06ac2-127">Переименовать меру также можно в строке формулы.</span><span class="sxs-lookup"><span data-stu-id="06ac2-127">You can also rename a measure in the formula bar.</span></span> <span data-ttu-id="06ac2-128">Имя меры идет перед формулой и отделяется от нее двоеточием.</span><span class="sxs-lookup"><span data-stu-id="06ac2-128">The measure name precedes the formula, followed by a colon.</span></span>  
  
###  <a name="to-delete-a-measure"></a><a name="bkmk_delete"></a><span data-ttu-id="06ac2-129">Удаление меры</span><span class="sxs-lookup"><span data-stu-id="06ac2-129">To delete a measure</span></span>  
  
-   <span data-ttu-id="06ac2-130">Щелкните меру правой кнопкой мыши в сетке мер и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="06ac2-130">In the measure grid, right-click a measure, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ac2-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="06ac2-131">See Also</span></span>  
 <span data-ttu-id="06ac2-132">[Меры &#40;табличных&#41;SSAS](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="06ac2-132">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 <span data-ttu-id="06ac2-133">[Ключевые показатели эффективности &#40;табличные&#41;SSAS](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="06ac2-133">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="06ac2-134">Вычисляемые столбцы (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="06ac2-134">Calculated Columns &#40;SSAS Tabular&#41;</span></span>](ssas-calculated-columns.md)  
  
  
