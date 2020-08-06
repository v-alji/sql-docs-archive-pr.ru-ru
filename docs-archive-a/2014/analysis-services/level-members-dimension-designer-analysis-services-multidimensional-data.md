---
title: Уровень и элементы (вкладка «браузер», конструктор измерений) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.browsertab.levelsandmembers.f1
ms.assetid: 3f61e384-5b4e-4480-a7ed-b408de2fdea7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 21680f00b82b5410e2c7a67122fdcfeb78c999dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752483"
---
# <a name="level-and-members-browser-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="19645-102">Уровень и элементы (вкладка «Браузер» конструктора измерений) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="19645-102">Level and Members (Browser Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="19645-103">Данная панель используется для просмотра элементов выбранных в настоящий момент иерархии и языка.</span><span class="sxs-lookup"><span data-stu-id="19645-103">Use this pane to browse the members of the currently selected hierarchy and language.</span></span> <span data-ttu-id="19645-104">Чтобы выбрать иерархию или язык для просмотра, используйте параметры **Иерархия** и **Язык** на **Панели инструментов** .</span><span class="sxs-lookup"><span data-stu-id="19645-104">To select a hierarchy or language to browse, use the **Hierarchy** and **Language** options on the **Toolbar** pane.</span></span> <span data-ttu-id="19645-105">Дополнительные сведения об этой панели инструментов см. в разделе [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="19645-105">For more information about the Toolbar pane, see [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="writeback-mode"></a><span data-ttu-id="19645-106">Режим обратной записи</span><span class="sxs-lookup"><span data-stu-id="19645-106">Writeback Mode</span></span>  
 <span data-ttu-id="19645-107">При включении режима обратной записи функциональность данной панели изменяется.</span><span class="sxs-lookup"><span data-stu-id="19645-107">The functionality of this pane changes if writeback mode is enabled.</span></span> <span data-ttu-id="19645-108">Для включения режима обратной записи для выбранного измерения должна быть включена возможность записи (другими словами, свойство `WriteEnabled` измерения должно быть установлено равным true) и измерение должно быть развернуто на экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19645-108">The selected dimension must be write-enabled (in other words, the `WriteEnabled` property of the dimension must be set to true) and the dimension must be deployed to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance in order to enable writeback mode.</span></span>  
  
 <span data-ttu-id="19645-109">Для включения режима обратной записи можно либо выбрать элемент **Обратная запись** в области **Панель инструментов** , либо щелкнуть правой кнопкой мыши панель **Уровень и элементы** и выбрать пункт **Обратная запись** из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="19645-109">To enable writeback mode, you can either select **Writeback** from the **Toolbar** pane, or right-click the **Level and Members** pane and select **Writeback** from the context menu.</span></span>  
  
 <span data-ttu-id="19645-110">Если включен режим обратной записи, то на панели **Уровень и элементы** можно выполнять следующие дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="19645-110">If writeback mode is enabled, you can perform the following additional actions in the **Level and Members** pane:</span></span>  
  
|<span data-ttu-id="19645-111">Действие</span><span class="sxs-lookup"><span data-stu-id="19645-111">To do</span></span>|<span data-ttu-id="19645-112">Выполнение</span><span class="sxs-lookup"><span data-stu-id="19645-112">Perform</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="19645-113">Создать родственные и дочерние элементы в выбранной иерархии.</span><span class="sxs-lookup"><span data-stu-id="19645-113">Create sibling and child members within the selected hierarchy.</span></span>|<span data-ttu-id="19645-114">Щелкните правой кнопкой мыши выбранный элемент и выберите из контекстного меню либо пункт **Создать сестру**для создания родственного элемента, либо пункт **Создать потомка**для создания дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="19645-114">Right-click the selected member and select either **Create Sibling**, to create a sibling member, or **Create Child**, to create a child member, from the context menu.</span></span>|  
|<span data-ttu-id="19645-115">Переместить выбранный элемент вверх или вниз в иерархии.</span><span class="sxs-lookup"><span data-stu-id="19645-115">Move a selected member up or down the hierarchy.</span></span>|<span data-ttu-id="19645-116">Либо перетащите выбранный элемент на соответствующий родительский или дочерний элемент, или выберите элемент **Увеличить отступ** или **Уменьшить отступ** на **Панели инструментов** для перемещения выбранного элемента вверх или вниз по уровням иерархии.</span><span class="sxs-lookup"><span data-stu-id="19645-116">Either drag the selected member to the appropriate parent or child member, or click **Increase Indent** or **Decrease Indent** on the **Toolbar** pane to move the selected member up or down the levels of the hierarchy.</span></span>|  
|<span data-ttu-id="19645-117">Переименовать выбранный элемент.</span><span class="sxs-lookup"><span data-stu-id="19645-117">Rename a selected member.</span></span>|<span data-ttu-id="19645-118">Либо щелкните правой кнопкой мыши выбранный элемент и выберите пункт **Переименовать**, либо щелкните уже выбранный элемент.</span><span class="sxs-lookup"><span data-stu-id="19645-118">Either right-click the selected member and select **Rename**, or click an already-selected member.</span></span>|  
|<span data-ttu-id="19645-119">Изменить значения свойств элемента</span><span class="sxs-lookup"><span data-stu-id="19645-119">Edit member property values</span></span>|<span data-ttu-id="19645-120">Дважды щелкните значение в свойстве выбранного элемента для выбранного элемента для редактирования значения.</span><span class="sxs-lookup"><span data-stu-id="19645-120">Double-click the value in the selected member property for the selected member to edit the value.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="19645-121">Варианты</span><span class="sxs-lookup"><span data-stu-id="19645-121">Options</span></span>  
 <span data-ttu-id="19645-122">**Текущий уровень**</span><span class="sxs-lookup"><span data-stu-id="19645-122">**Current level**</span></span>  
 <span data-ttu-id="19645-123">Отображает уровень, к которому принадлежит выбранный в текущий момент элемент, относящийся к пункту **Дерево** .</span><span class="sxs-lookup"><span data-stu-id="19645-123">Displays the level to which the currently selected member in **Tree** belongs.</span></span>  
  
 <span data-ttu-id="19645-124">**Приклад**</span><span class="sxs-lookup"><span data-stu-id="19645-124">**Tree**</span></span>  
 <span data-ttu-id="19645-125">Отображает элементы выбранной в текущий момент иерархии и языка.</span><span class="sxs-lookup"><span data-stu-id="19645-125">Displays the members of the currently selected hierarchy and language.</span></span>  
  
 <span data-ttu-id="19645-126">Если выбраны свойства элемента из параметра **Свойства элемента** на Панели инструментов, то каждое свойство элемента будет отображаться в виде столбца.</span><span class="sxs-lookup"><span data-stu-id="19645-126">If member properties are selected from the **Member Properties** option of the Toolbar pane, each member property is displayed as a column.</span></span>  
  
 <span data-ttu-id="19645-127">Если включен режим обратной записи, то отображается один столбец для каждого ключевого столбца, связанного с ключевым атрибутом в измерении.</span><span class="sxs-lookup"><span data-stu-id="19645-127">If writeback mode is enabled, one column for each key column associated with the key attribute in the dimension is displayed.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="19645-128">Контекстное меню</span><span class="sxs-lookup"><span data-stu-id="19645-128">Context Menu</span></span>  
 <span data-ttu-id="19645-129">Из контекстного меню, отображаемого с помощью правого щелчка в любой части панели **Уровень и элементы** для выбранного элемента, доступны следующие пункты:</span><span class="sxs-lookup"><span data-stu-id="19645-129">The following options are available in the context menu displayed by right-clicking any part of the **Level and Members** pane for the selected member:</span></span>  
  
 <span data-ttu-id="19645-130">**Создать сестру**</span><span class="sxs-lookup"><span data-stu-id="19645-130">**Create sibling**</span></span>  
 <span data-ttu-id="19645-131">Создает новый элемент на том же уровне, что и выбранный.</span><span class="sxs-lookup"><span data-stu-id="19645-131">Creates a new member at the same level as the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-132">Этот параметр включен, только если выбран элемент на уровне, отличающемся от уровня (Все).</span><span class="sxs-lookup"><span data-stu-id="19645-132">This option is enabled only if a member at a level other than the (All) level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-133">Этот параметр отображается только при включенной обратной записи.</span><span class="sxs-lookup"><span data-stu-id="19645-133">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="19645-134">**Создать потомка**</span><span class="sxs-lookup"><span data-stu-id="19645-134">**Create child**</span></span>  
 <span data-ttu-id="19645-135">Создает новый элемент на следующем более низком уровне, чем у выбранного элемента, в виде подчиненного элемента выбранному.</span><span class="sxs-lookup"><span data-stu-id="19645-135">Creates a new member at the next lower level as the selected member, as a child of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-136">Этот параметр задействуется, только если выбран элемент на уровне, более высоком, чем самый нижний.</span><span class="sxs-lookup"><span data-stu-id="19645-136">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-137">Этот параметр отображается только при включенной обратной записи.</span><span class="sxs-lookup"><span data-stu-id="19645-137">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="19645-138">**Вырезать**</span><span class="sxs-lookup"><span data-stu-id="19645-138">**Cut**</span></span>  
 <span data-ttu-id="19645-139">Копирует выбранные элементы в буфер обмена и удаляет их из иерархии.</span><span class="sxs-lookup"><span data-stu-id="19645-139">Copies the selected members to the clipboard and removes them from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-140">Этот параметр задействуется, только если выбран любой элемент, кроме «Все».</span><span class="sxs-lookup"><span data-stu-id="19645-140">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-141">Этот параметр отображается только при включенной обратной записи.</span><span class="sxs-lookup"><span data-stu-id="19645-141">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="19645-142">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="19645-142">**Paste**</span></span>  
 <span data-ttu-id="19645-143">Вставляет элементы, удаленные ранее с помощью действия **Вырезать** , сразу после выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="19645-143">Pastes members previously removed using **Cut** immediately after the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-144">Этот параметр отображается только при включенной обратной записи.</span><span class="sxs-lookup"><span data-stu-id="19645-144">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="19645-145">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="19645-145">**Delete**</span></span>  
 <span data-ttu-id="19645-146">Удаляет выбранные элементы из иерархии.</span><span class="sxs-lookup"><span data-stu-id="19645-146">Removes the selected members from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-147">Этот параметр задействуется, только если выбран любой элемент, кроме «Все».</span><span class="sxs-lookup"><span data-stu-id="19645-147">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-148">Этот параметр отображается только при включенной обратной записи.</span><span class="sxs-lookup"><span data-stu-id="19645-148">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="19645-149">**Переименование**</span><span class="sxs-lookup"><span data-stu-id="19645-149">**Rename**</span></span>  
 <span data-ttu-id="19645-150">Выберите для редактирования имени выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="19645-150">Select to edit the name of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-151">Этот параметр задействуется, только если выбран любой элемент, кроме «Все».</span><span class="sxs-lookup"><span data-stu-id="19645-151">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-152">Этот параметр отображается только при включенной обратной записи.</span><span class="sxs-lookup"><span data-stu-id="19645-152">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="19645-153">**Фильтрация элементов**</span><span class="sxs-lookup"><span data-stu-id="19645-153">**Filter Members**</span></span>  
 <span data-ttu-id="19645-154">Отображает диалоговое окно **Фильтрация элементов** для фильтрации элементов, отображаемых на панели **Уровень и элементы** для выбранной иерархии.</span><span class="sxs-lookup"><span data-stu-id="19645-154">Displays the **Filter Members** dialog box to filter members displayed in **Level and Members** for the selected hierarchy.</span></span> <span data-ttu-id="19645-155">Дополнительные сведения о диалоговом окне **Фильтрация элементов** см. в разделе [Диалоговое окно "Фильтрация элементов" (службы Analysis Services — многомерные данные)](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="19645-155">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="19645-156">**Развернуть все**</span><span class="sxs-lookup"><span data-stu-id="19645-156">**Expand All**</span></span>  
 <span data-ttu-id="19645-157">Развертывает все элементы в области **Дерево**.</span><span class="sxs-lookup"><span data-stu-id="19645-157">Expands all members in **Tree**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19645-158">Этот параметр задействуется, только если выбран элемент на уровне, более высоком, чем самый нижний.</span><span class="sxs-lookup"><span data-stu-id="19645-158">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
 <span data-ttu-id="19645-159">**Свернуть все**</span><span class="sxs-lookup"><span data-stu-id="19645-159">**Collapse All**</span></span>  
 <span data-ttu-id="19645-160">Сворачивает все элементы в области **Дерево**.</span><span class="sxs-lookup"><span data-stu-id="19645-160">Collapse all members in **Tree**.</span></span>  
  
 <span data-ttu-id="19645-161">**Развернуть элемент**</span><span class="sxs-lookup"><span data-stu-id="19645-161">**Expand Member**</span></span>  
 <span data-ttu-id="19645-162">Развертывается выбранный элемент в области **Дерево**.</span><span class="sxs-lookup"><span data-stu-id="19645-162">Expand the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="19645-163">**Свернуть элемент**</span><span class="sxs-lookup"><span data-stu-id="19645-163">**Collapse Member**</span></span>  
 <span data-ttu-id="19645-164">Сворачивает выбранный элемент в области **Дерево**.</span><span class="sxs-lookup"><span data-stu-id="19645-164">Collapse the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="19645-165">**Обратная запись**</span><span class="sxs-lookup"><span data-stu-id="19645-165">**Writeback**</span></span>  
 <span data-ttu-id="19645-166">Выберите, чтобы включить режим обратной записи.</span><span class="sxs-lookup"><span data-stu-id="19645-166">Select to enable writeback mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19645-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="19645-167">See Also</span></span>  
 <span data-ttu-id="19645-168">[Панель инструментов &#40;вкладка «браузер», конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="19645-168">[Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="19645-169">Конструктор измерений &#40;конструктора&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="19645-169">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
