---
title: Вычисления (конструктор кубов) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationsview.f1
ms.assetid: 46e2fbe2-bb41-4eaa-91f8-eb2bd3b8d00d
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdbc35a8e47557923b90cda4e72280c3cca940dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657423"
---
# <a name="calculations-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="e91e1-102">Вычисления (конструктор кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="e91e1-102">Calculations (Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e91e1-103">Вкладка **Вычисления** в конструкторе кубов используется для просмотра и изменения вычислений, включая вычисляемые элементы, именованные наборы и команды скриптов многомерных выражений для выбранного куба.</span><span class="sxs-lookup"><span data-stu-id="e91e1-103">Use the **Calculations** tab in Cube Designer to view and edit calculations, including calculated members, named sets, and Multidimensional Expressions (MDX) script commands for the selected cube.</span></span>  
  
## <a name="form-view-and-script-view"></a><span data-ttu-id="e91e1-104">Представление формы и представление скрипта</span><span class="sxs-lookup"><span data-stu-id="e91e1-104">Form View and Script View</span></span>  
 <span data-ttu-id="e91e1-105">При просмотре или изменении вычислений на вкладке **Вычисления** используют два различных представления:</span><span class="sxs-lookup"><span data-stu-id="e91e1-105">The **Calculations** tab supports two different views when viewing or editing calculations:</span></span>  
  
-   <span data-ttu-id="e91e1-106">Представление формы</span><span class="sxs-lookup"><span data-stu-id="e91e1-106">Form view</span></span>  
  
     <span data-ttu-id="e91e1-107">Упорядоченное представление вычисляемых элементов, именованных наборов и команд скриптов, содержащихся в скрипте многомерных выражений, связанных с кубом. Редакторы формы позволяют просматривать и редактировать вычисляемые элементы и именованные наборы, а также просматривать доступные метаданные, функции и инструментальные средства, доступные в кубе.</span><span class="sxs-lookup"><span data-stu-id="e91e1-107">This view displays an organized view of the calculated members, named sets, and script commands contained in the MDX script associated with the cube and provides form editors to view and edit calculated members and named sets, as well as displaying the metadata, functions, and tools available to the cube.</span></span>  
  
-   <span data-ttu-id="e91e1-108">Представление скрипта</span><span class="sxs-lookup"><span data-stu-id="e91e1-108">Script view</span></span>  
  
     <span data-ttu-id="e91e1-109">Для опытных пользователей в этом представлении целиком отображается скрипт многомерных выражений, связанный с кубом, а также доступные в кубе метаданные, функции и инструментальные средства.</span><span class="sxs-lookup"><span data-stu-id="e91e1-109">For advanced users, this view displays the entire MDX script associated with the cube, as well as displaying the metadata, functions, and tools available to the cube.</span></span>  
  
## <a name="panes"></a><span data-ttu-id="e91e1-110">Панели</span><span class="sxs-lookup"><span data-stu-id="e91e1-110">Panes</span></span>  
 <span data-ttu-id="e91e1-111">**Панель инструментов**</span><span class="sxs-lookup"><span data-stu-id="e91e1-111">**Toolbar**</span></span>  
 <span data-ttu-id="e91e1-112">Используйте панель инструментов как в представлении формы, так и в представлении скриптов для выполнения общих операций на этой вкладке. Дополнительные сведения об этой панели см. в разделе [панель инструментов &#40;вычисления, конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e91e1-112">Use the toolbar in both form view and script view to perform common operations on this tab. For more information about this pane, see [Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e91e1-113">**Организатор скриптов**</span><span class="sxs-lookup"><span data-stu-id="e91e1-113">**Script Organizer**</span></span>  
 <span data-ttu-id="e91e1-114">Панель **Организатор скриптов** в представлении формы используется для отображения содержимого скрипта куба в заказном формате.</span><span class="sxs-lookup"><span data-stu-id="e91e1-114">Use the **Script Organizer** pane in form view to display the contents of the cube script in an ordered format.</span></span> <span data-ttu-id="e91e1-115">Дополнительные сведения об этой панели см. в разделе [Организатор скриптов (вкладка "Вычисления", конструктор кубов) (службы Analysis Services — многомерные данные)](script-organizer-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e91e1-115">For more information about this pane, see [Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e91e1-116">**Средства вычисления**</span><span class="sxs-lookup"><span data-stu-id="e91e1-116">**Calculation Tools**</span></span>  
 <span data-ttu-id="e91e1-117">Панель **Средства вычисления** в обоих представлениях (форма и скрипт) используется для отображения метаданных, функций и инструментальных средств, доступных в кубе.</span><span class="sxs-lookup"><span data-stu-id="e91e1-117">Use the **Calculation Tools** pane in both form view and script view to display metadata, functions, and tools available to the cube.</span></span> <span data-ttu-id="e91e1-118">Дополнительные сведения об этой панели см. в разделе [Средства вычисления (вкладка "Вычисления", конструктор кубов) (службы Analysis Services — многомерные данные)](calculation-tools-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e91e1-118">For more information about this pane, see [Calculation Tools &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e91e1-119">**Редактор скриптов**</span><span class="sxs-lookup"><span data-stu-id="e91e1-119">**Script Editor**</span></span>  
 <span data-ttu-id="e91e1-120">Панель **Редактор скриптов** в представлении скриптов используется для редактирования всего скрипта куба, в представлении формы — для редактирования команд скрипта куба.</span><span class="sxs-lookup"><span data-stu-id="e91e1-120">Use the **Script Editor** pane in script view to edit the entire cube script and in form view to edit script commands contained in the cube script.</span></span> <span data-ttu-id="e91e1-121">Дополнительные сведения об этой панели см. в разделе [Редактор скриптов (вкладка "Вычисления", конструктор кубов) (службы Analysis Services — многомерные данные)](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e91e1-121">For more information about this pane, see [Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e91e1-122">**Редактор формы вычисляемых элементов**</span><span class="sxs-lookup"><span data-stu-id="e91e1-122">**Calculated Member Form Editor**</span></span>  
 <span data-ttu-id="e91e1-123">Панель **Редактор формы вычисляемых элементов** в представлении формы используется для редактирования вычисляемых элементов в скрипте куба.</span><span class="sxs-lookup"><span data-stu-id="e91e1-123">Use the **Calculated Member Form Editor** pane in form view to edit calculated members in the cube script.</span></span> <span data-ttu-id="e91e1-124">Дополнительные сведения об этой панели см. в разделе [Редактор формы вычисляемых элементов (вкладка "Вычисления", конструктор кубов) (службы Analysis Services — многомерные данные)](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e91e1-124">For more information about this pane, see [Calculated Member Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e91e1-125">**Редактор формы именованных наборов**</span><span class="sxs-lookup"><span data-stu-id="e91e1-125">**Named Set Form Editor**</span></span>  
 <span data-ttu-id="e91e1-126">Панель **Редактор формы именованных наборов** в представлении формы используется для редактирования именованных наборов в скрипте куба.</span><span class="sxs-lookup"><span data-stu-id="e91e1-126">Use the **Named Set Form Editor** pane in form view to edit named sets in the cube script.</span></span> <span data-ttu-id="e91e1-127">Дополнительные сведения об этой панели см. в разделе [Редактор формы именованных наборов (вкладка "Вычисления", конструктор кубов) (службы Analysis Services — многомерные данные)](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e91e1-127">For more information about this pane, see [Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91e1-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="e91e1-128">See Also</span></span>  
 <span data-ttu-id="e91e1-129">[Объекты куба &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e91e1-129">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e91e1-130">[Времен](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="e91e1-130">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="e91e1-131">[Основные принципы создания скриптов многомерных выражений &#40;Analysis Services&#41;](multidimensional-models/mdx/mdx-scripting-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e91e1-131">[MDX Scripting Fundamentals &#40;Analysis Services&#41;](multidimensional-models/mdx/mdx-scripting-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="e91e1-132">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e91e1-132">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e91e1-133">Создание именованных наборов</span><span class="sxs-lookup"><span data-stu-id="e91e1-133">Create Named Sets</span></span>](multidimensional-models/create-named-sets.md)  
  
  
