---
title: Атрибуты (вкладка «Структура измерения», конструктор измерений) (Analysis Services многомерных данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.attributespane.f1
ms.assetid: 627eaa08-7638-4edd-bdfa-0d8175a7cde5
author: minewiskan
ms.author: owend
ms.openlocfilehash: cb47a02d0b1118d34e8e282bb127444b6a03eb3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656873"
---
# <a name="attributes-dimension-structure-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="c1171-102">Атрибуты (вкладка «Структура измерения», конструктор измерений) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="c1171-102">Attributes (Dimension Structure Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="c1171-103">Используйте эту панель для управления атрибутами, связанными с выбранным измерением.</span><span class="sxs-lookup"><span data-stu-id="c1171-103">Use this pane to manage the attributes associated with the selected dimension.</span></span> <span data-ttu-id="c1171-104">Чтобы создать иерархии или уровни, можно перетаскивать атрибуты из этой панели на панель **Иерархии** .</span><span class="sxs-lookup"><span data-stu-id="c1171-104">Attributes can be dragged from this pane to the **Hierarchies** pane to create hierarchies and levels.</span></span> <span data-ttu-id="c1171-105">Дополнительные сведения см. в разделе [Hierarchies &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](hierarchies-dimension-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c1171-105">For more information, see [Hierarchies &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](hierarchies-dimension-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="c1171-106">Чтобы создать атрибут, перетащите столбец из панели **Представление источника данных** на панель **Атрибуты** , находясь в режиме списка, дерева или представления.</span><span class="sxs-lookup"><span data-stu-id="c1171-106">To create an attribute, drag a column from the **Data Source View** pane to the **Attributes** pane while in list, tree, or view mode.</span></span> <span data-ttu-id="c1171-107">Чтобы удалить атрибут, в контекстном меню выберите команду **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="c1171-107">To remove an attribute, select **Delete** on the shortcut menu.</span></span>  
  
 <span data-ttu-id="c1171-108">**Отображение панели «Атрибуты»**</span><span class="sxs-lookup"><span data-stu-id="c1171-108">**To display the Attributes pane**</span></span>  
  
1.  <span data-ttu-id="c1171-109">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , а затем откройте нужное измерение.</span><span class="sxs-lookup"><span data-stu-id="c1171-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then open the dimension that you want.</span></span>  
  
2.  <span data-ttu-id="c1171-110">Перейдите на вкладку **Структура измерения** , если она неактивна.</span><span class="sxs-lookup"><span data-stu-id="c1171-110">If not selected, click the **Dimension Structure** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c1171-111">Варианты</span><span class="sxs-lookup"><span data-stu-id="c1171-111">Options</span></span>  
 <span data-ttu-id="c1171-112">**Атрибуты**</span><span class="sxs-lookup"><span data-stu-id="c1171-112">**Attributes**</span></span>  
 <span data-ttu-id="c1171-113">Показывает атрибуты, доступные для выбранного измерения.</span><span class="sxs-lookup"><span data-stu-id="c1171-113">Displays the attributes available to the selected dimension.</span></span> <span data-ttu-id="c1171-114">Этот параметр доступен для просмотра в следующих режимах:</span><span class="sxs-lookup"><span data-stu-id="c1171-114">This option can be viewed in the following modes:</span></span>  
  
-   <span data-ttu-id="c1171-115">Режим списка</span><span class="sxs-lookup"><span data-stu-id="c1171-115">List mode</span></span>  
  
     <span data-ttu-id="c1171-116">В этом режиме создаются и редактируются иерархии.</span><span class="sxs-lookup"><span data-stu-id="c1171-116">Use this mode to create and modify hierarchies.</span></span> <span data-ttu-id="c1171-117">Чтобы просмотреть атрибуты в режиме списка, в контекстном меню выберите команду **Показать атрибуты в** и выберите пункт **Список**.</span><span class="sxs-lookup"><span data-stu-id="c1171-117">To view the attributes in list mode, select **Show Attributes in** on the shortcut menu, and then click **List**.</span></span>  
  
-   <span data-ttu-id="c1171-118">Режим дерева</span><span class="sxs-lookup"><span data-stu-id="c1171-118">Tree mode</span></span>  
  
     <span data-ttu-id="c1171-119">В этом режиме создаются и редактируются иерархии.</span><span class="sxs-lookup"><span data-stu-id="c1171-119">Use this mode to create and modify hierarchies.</span></span> <span data-ttu-id="c1171-120">Чтобы просмотреть атрибуты в режиме дерева, в контекстном меню выберите команду **Показать атрибуты в** и выберите пункт **Дерево**.</span><span class="sxs-lookup"><span data-stu-id="c1171-120">To view the attributes in tree mode, select **Show Attributes in** on the shortcut menu, and then click **Tree**.</span></span>  
  
-   <span data-ttu-id="c1171-121">Режим сетки</span><span class="sxs-lookup"><span data-stu-id="c1171-121">Grid mode</span></span>  
  
     <span data-ttu-id="c1171-122">Этот режим предназначен для ручного создания измерений и редактирования свойств атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c1171-122">Use this mode to create dimensions manually, or to modify attribute properties.</span></span> <span data-ttu-id="c1171-123">Чтобы просмотреть атрибуты в режиме сетки, в контекстном меню выберите команду **Показать атрибуты в** и выберите пункт **Сетка**.</span><span class="sxs-lookup"><span data-stu-id="c1171-123">To view the attributes in grid mode, select **Show Attributes in** on the shortcut menu, and then click **Grid**.</span></span>  
  
## <a name="grid-mode-options"></a><span data-ttu-id="c1171-124">Параметры режима сетки</span><span class="sxs-lookup"><span data-stu-id="c1171-124">Grid Mode Options</span></span>  
 <span data-ttu-id="c1171-125">При просмотре атрибутов в режиме сетки доступны столбцы, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c1171-125">When viewing attributes in grid mode, you have access to the columns listed in the following table.</span></span>  
  
 <span data-ttu-id="c1171-126">**имя**;</span><span class="sxs-lookup"><span data-stu-id="c1171-126">**Name**</span></span>  
 <span data-ttu-id="c1171-127">Показывает имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="c1171-127">Displays the name of the attribute.</span></span>  
  
 <span data-ttu-id="c1171-128">**Использование**</span><span class="sxs-lookup"><span data-stu-id="c1171-128">**Usage**</span></span>  
 <span data-ttu-id="c1171-129">Задает использование атрибута.</span><span class="sxs-lookup"><span data-stu-id="c1171-129">Sets the usage of the selected attribute.</span></span> <span data-ttu-id="c1171-130">Нажмите стрелку вниз, чтобы выбрать один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="c1171-130">Click the down arrow to select from the following choices:</span></span>  
  
|<span data-ttu-id="c1171-131">Значение</span><span class="sxs-lookup"><span data-stu-id="c1171-131">Value</span></span>|<span data-ttu-id="c1171-132">Описание</span><span class="sxs-lookup"><span data-stu-id="c1171-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c1171-133">Регулярно</span><span class="sxs-lookup"><span data-stu-id="c1171-133">Regular</span></span>|<span data-ttu-id="c1171-134">Указывает на обычный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c1171-134">Identifies a regular attribute.</span></span>|  
|<span data-ttu-id="c1171-135">Клавиши</span><span class="sxs-lookup"><span data-stu-id="c1171-135">Key</span></span>|<span data-ttu-id="c1171-136">Указывает на ключевой атрибут измерения.</span><span class="sxs-lookup"><span data-stu-id="c1171-136">Identifies the key attribute for the dimension.</span></span> <span data-ttu-id="c1171-137">Соответствует конечным элементам измерения.</span><span class="sxs-lookup"><span data-stu-id="c1171-137">This corresponds to the leaf members of the dimension.</span></span> <span data-ttu-id="c1171-138">У измерения может быть только один ключевой атрибут.</span><span class="sxs-lookup"><span data-stu-id="c1171-138">There can only be one key attribute per dimension.</span></span> <span data-ttu-id="c1171-139">Для редактирования нажмите кнопку с многоточием (**...**) рядом со свойством **KeyColumns** в панели **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="c1171-139">To modify, click the ellipsis button (**...**) next to the **KeyColumns** property in the **Properties** pane.</span></span>|  
|<span data-ttu-id="c1171-140">Parent</span><span class="sxs-lookup"><span data-stu-id="c1171-140">Parent</span></span>|<span data-ttu-id="c1171-141">Обозначает родительский атрибут в связи типа «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="c1171-141">Denotes the parent attribute for a parent-child relationship.</span></span> <span data-ttu-id="c1171-142">Дочерний атрибут в этой связи всегда должен быть ключевым.</span><span class="sxs-lookup"><span data-stu-id="c1171-142">The child attribute in this relationship must always be the key attribute.</span></span>|  
|<span data-ttu-id="c1171-143">AccountType</span><span class="sxs-lookup"><span data-stu-id="c1171-143">AccountType</span></span>|<span data-ttu-id="c1171-144">Обозначает атрибут типа учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c1171-144">Denotes an account type attribute.</span></span> <span data-ttu-id="c1171-145">Применяется сервером или ядром, если статистическая функция для меры имеет значение «по учетной записи».</span><span class="sxs-lookup"><span data-stu-id="c1171-145">This is used by the server or engine when the aggregation function for a measure is set to "by account."</span></span>|  
  
 <span data-ttu-id="c1171-146">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c1171-146">**Type**</span></span>  
 <span data-ttu-id="c1171-147">Задает тип атрибута.</span><span class="sxs-lookup"><span data-stu-id="c1171-147">Sets the type of the attribute.</span></span> <span data-ttu-id="c1171-148">Нажмите стрелку вниз, чтобы выбрать один из доступных параметров.</span><span class="sxs-lookup"><span data-stu-id="c1171-148">Click the down arrow to select from the available choices.</span></span>  
  
 <span data-ttu-id="c1171-149">**Ключевой столбец**</span><span class="sxs-lookup"><span data-stu-id="c1171-149">**Key Column**</span></span>  
 <span data-ttu-id="c1171-150">Отображает тип данных базового столбца.</span><span class="sxs-lookup"><span data-stu-id="c1171-150">Displays the data type of the underlying columns.</span></span> <span data-ttu-id="c1171-151">При создании нового атрибута нажмите стрелку вниз, чтобы выбрать один из доступных параметров.</span><span class="sxs-lookup"><span data-stu-id="c1171-151">When creating a new attribute, click the down arrow to select from the available choices.</span></span>  
  
 <span data-ttu-id="c1171-152">**Столбец имени**</span><span class="sxs-lookup"><span data-stu-id="c1171-152">**Name Column**</span></span>  
 <span data-ttu-id="c1171-153">Отображает расположение базового столбца.</span><span class="sxs-lookup"><span data-stu-id="c1171-153">Displays the location of the underlying column.</span></span> <span data-ttu-id="c1171-154">При создании нового атрибута нажмите стрелку вниз, чтобы выбрать либо **Тот же, что и ключ** , либо **Отдельный столбец**.</span><span class="sxs-lookup"><span data-stu-id="c1171-154">When creating a new attribute, click the down arrow to select between **Same as key** and **Separate column**.</span></span> <span data-ttu-id="c1171-155">Если выбран параметр **Отдельный столбец** , то свойство **NameColumn** на панели **Свойства** будет определять столбец, в котором хранится имя, применяемое для атрибута.</span><span class="sxs-lookup"><span data-stu-id="c1171-155">If **Separate column** is chosen, the **NameColumn** property in the **Properties** pane sets the column that stores the name to use for the attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1171-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="c1171-156">See Also</span></span>  
 <span data-ttu-id="c1171-157">[Структура измерения &#40;конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;](dimension-structure-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="c1171-157">[Dimension Structure &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](dimension-structure-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="c1171-158">[Иерархии &#40;вкладка «Структура измерения», конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;](hierarchies-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="c1171-158">[Hierarchies &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](hierarchies-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="c1171-159">Панель инструментов &#40;вкладка «Структура измерения», конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c1171-159">Toolbar &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](toolbar-dimension-structure-designer-analysis-services-multidimensional-data.md)  
  
  
