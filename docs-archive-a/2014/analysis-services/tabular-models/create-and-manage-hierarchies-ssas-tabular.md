---
title: Создание иерархий и управление ими (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8dd30cd0-a831-4d25-b577-648d7f3c7fa6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0bab3e09aadb4e0c857b9c1da3111e03e90f777e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657926"
---
# <a name="create-and-manage-hierarchies-ssas-tabular"></a><span data-ttu-id="1273a-102">Создание иерархий и управление ими (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="1273a-102">Create and Manage Hierarchies (SSAS Tabular)</span></span>
  <span data-ttu-id="1273a-103">Создавать иерархии и управлять ими можно в конструкторе моделей, в представлении диаграммы.</span><span class="sxs-lookup"><span data-stu-id="1273a-103">Hierarchies can be created and managed in the model designer, in Diagram View.</span></span> <span data-ttu-id="1273a-104">Чтобы просмотреть представление диаграммы в конструкторе моделей в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], укажите в меню **Модель** пункт **Представление модели**, а затем выберите пункт **Представление диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="1273a-104">To view the model designer in Diagram View, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
 <span data-ttu-id="1273a-105">В этот раздел включены следующее задачи:</span><span class="sxs-lookup"><span data-stu-id="1273a-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="1273a-106">Создание иерархии</span><span class="sxs-lookup"><span data-stu-id="1273a-106">Create a Hierarchy</span></span>](#bkmk_create)  
  
-   [<span data-ttu-id="1273a-107">Изменение иерархии</span><span class="sxs-lookup"><span data-stu-id="1273a-107">Edit a Hierarchy</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="1273a-108">Удаление иерархии</span><span class="sxs-lookup"><span data-stu-id="1273a-108">Delete a Hierarchy</span></span>](#bkmk_delete)  
  
##  <a name="create-a-hierarchy"></a><a name="bkmk_create"></a> <span data-ttu-id="1273a-109">Создание иерархии</span><span class="sxs-lookup"><span data-stu-id="1273a-109">Create a Hierarchy</span></span>  
 <span data-ttu-id="1273a-110">Иерархию можно создать, используя контекстное меню таблицы и столбцов.</span><span class="sxs-lookup"><span data-stu-id="1273a-110">You can create a hierarchy by using the columns and table context menu.</span></span> <span data-ttu-id="1273a-111">При создании иерархии новый родительский уровень отображает выбранные столбцы как дочерние уровни.</span><span class="sxs-lookup"><span data-stu-id="1273a-111">When you create a hierarchy, a new parent level displays with selected columns as child levels.</span></span>  
  
#### <a name="to-create-a-hierarchy-from-the-context-menu"></a><span data-ttu-id="1273a-112">Создание иерархии из контекстного меню</span><span class="sxs-lookup"><span data-stu-id="1273a-112">To create a hierarchy from the context menu</span></span>  
  
1.  <span data-ttu-id="1273a-113">В конструкторе моделей (представление диаграммы) в окне таблицы щелкните правой кнопкой мыши столбец и выберите пункт **Создать иерархию**.</span><span class="sxs-lookup"><span data-stu-id="1273a-113">In the model designer (Diagram View), in a table window, right-click on a column, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="1273a-114">Для выбора нескольких столбцов щелкните каждый столбец, а затем щелкните правой кнопкой мыши для открытия контекстного меню и выберите пункт **Создать иерархию**.</span><span class="sxs-lookup"><span data-stu-id="1273a-114">To select multiple columns, click each column, then right-click to open the context menu, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="1273a-115">В нижней части окна таблицы будет создан родительский уровень иерархии, а выбранные столбцы будут скопированы в иерархию в качестве дочерних уровней.</span><span class="sxs-lookup"><span data-stu-id="1273a-115">A parent hierarchy level is created at the bottom of the table window and the selected columns are copied under the hierarchy as child levels.</span></span>  
  
2.  <span data-ttu-id="1273a-116">Введите имя иерархии.</span><span class="sxs-lookup"><span data-stu-id="1273a-116">Type a name for the hierarchy.</span></span>  
  
 <span data-ttu-id="1273a-117">Можно перетаскивать дополнительные столбцы в родительский уровень иерархии, который копирует столбцы.</span><span class="sxs-lookup"><span data-stu-id="1273a-117">You can drag additional columns into your hierarchy's parent level, which copies the columns.</span></span> <span data-ttu-id="1273a-118">Перетащите дочерний уровень в то место, где он должен появиться в иерархии.</span><span class="sxs-lookup"><span data-stu-id="1273a-118">Drop the child level to place it where you want it to appear in the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1273a-119">Если вместе с одним или более столбцами выбрано несколько мер или выбраны столбцы из нескольких таблиц, команда «Создать иерархию» в контекстном меню будет недоступна.</span><span class="sxs-lookup"><span data-stu-id="1273a-119">The Create Hierarchy command is disabled in the context menu if you multi-select a measure along with one or more columns or you select columns from multiple tables.</span></span>  
  
##  <a name="edit-a-hierarchy"></a><a name="bkmk_edit"></a><span data-ttu-id="1273a-120">Изменение иерархии</span><span class="sxs-lookup"><span data-stu-id="1273a-120">Edit a Hierarchy</span></span>  
 <span data-ttu-id="1273a-121">Иерархию можно переименовать, переименовать ее дочерний узел, изменить порядок следования дочерних узлов, добавить дополнительные столбцы в качестве дочерних узлов, удалить дочерний узел из иерархии, отобразить имя источника дочернего узла (т. е. имя столбца), а также скрыть дочерний узел, если его имя совпадает с именем родительского узла иерархии.</span><span class="sxs-lookup"><span data-stu-id="1273a-121">You can rename a hierarchy, rename a child level, change the order of the child levels, add additional columns as child levels, remove a child level from a hierarchy, show the source name of a child level (the column name), and hide a child level if it has the same name as the hierarchy parent level.</span></span>  
  
#### <a name="to-change-the-name-of-a-hierarchy-or-child-level"></a><span data-ttu-id="1273a-122">Изменение имени иерархии или дочернего уровня</span><span class="sxs-lookup"><span data-stu-id="1273a-122">To change the name of a hierarchy or child level</span></span>  
  
1.  <span data-ttu-id="1273a-123">Щелкните правой кнопкой мыши родительский или дочерний уровень иерархии и выберите пункт **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="1273a-123">Right-click the hierarchy parent level or a child level, and the click **Rename**.</span></span>  
  
2.  <span data-ttu-id="1273a-124">Введите новое имя или измените существующее.</span><span class="sxs-lookup"><span data-stu-id="1273a-124">Type a new name or edit the existing name.</span></span>  
  
#### <a name="to-change-the-order-of-a-child-level-in-a-hierarchy"></a><span data-ttu-id="1273a-125">Изменение порядка следования дочернего уровня в иерархии</span><span class="sxs-lookup"><span data-stu-id="1273a-125">To change the order of a child level in a hierarchy</span></span>  
  
-   <span data-ttu-id="1273a-126">Перетащите дочерний уровень в новое положение в иерархии.</span><span class="sxs-lookup"><span data-stu-id="1273a-126">Click and drag a child level into a new position in the hierarchy.</span></span>  
  
-   <span data-ttu-id="1273a-127">Можно также щелкнуть правой кнопкой мыши дочерний уровень иерархии и выбрать пункт Переместить вверх для перемещения уровня вверх по списку или Переместить вниз для перемещения уровня вниз по списку.</span><span class="sxs-lookup"><span data-stu-id="1273a-127">Or, right-click a child level of the hierarchy, and then click Move Up to move the level up in the list, or click Move Down to move the level down in the list.</span></span>  
  
-   <span data-ttu-id="1273a-128">Можно также щелкнуть дочерний уровень иерархии, чтобы выделить его, затем нажать комбинацию клавиш Alt + «Стрелка вверх» для перемещения уровня вверх или комбинацию клавиш Alt + «Стрелка вниз» для перемещения уровня вниз по списку.</span><span class="sxs-lookup"><span data-stu-id="1273a-128">Or, click a child level to select it, and then press Alt + Up Arrow to move the level up, or press Alt+Down Arrow to move the level down in the list.</span></span>  
  
#### <a name="to-add-another-child-level-to-a-hierarchy"></a><span data-ttu-id="1273a-129">Добавление в иерархию нового дочернего уровня</span><span class="sxs-lookup"><span data-stu-id="1273a-129">To add another child level to a hierarchy</span></span>  
  
-   <span data-ttu-id="1273a-130">Перетащите столбец на родительский уровень или в определенное место в иерархии.</span><span class="sxs-lookup"><span data-stu-id="1273a-130">Click and drag a column onto the parent level or into a specific location of the hierarchy.</span></span> <span data-ttu-id="1273a-131">Столбец копируется в качестве дочернего уровня иерархии.</span><span class="sxs-lookup"><span data-stu-id="1273a-131">The column is copied as a child level of the hierarchy.</span></span>  
  
-   <span data-ttu-id="1273a-132">Также можно щелкнуть правой кнопкой мыши столбец, выбрать пункт **Добавить в иерархию**, а затем выбрать иерархию.</span><span class="sxs-lookup"><span data-stu-id="1273a-132">Or, right-click a column, point to **Add to Hierarchy**, and then click the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1273a-133">В качестве дочернего уровня иерархии можно добавить скрытый столбец (невидимый в отчетах).</span><span class="sxs-lookup"><span data-stu-id="1273a-133">You can add a hidden column (a column that is hidden from reports) as a child level to the hierarchy.</span></span> <span data-ttu-id="1273a-134">Дочерний уровень при этом скрыт не будет.</span><span class="sxs-lookup"><span data-stu-id="1273a-134">The child level is not hidden.</span></span>  
  
#### <a name="to-remove-a-child-level-from-a-hierarchy"></a><span data-ttu-id="1273a-135">Удаление дочернего уровня из иерархии</span><span class="sxs-lookup"><span data-stu-id="1273a-135">To remove a child level from a hierarchy</span></span>  
  
-   <span data-ttu-id="1273a-136">Щелкните правой кнопкой мыши дочерний уровень и выберите пункт **Удалить из иерархии**.</span><span class="sxs-lookup"><span data-stu-id="1273a-136">Right-click a child level, and then click **Remove from Hierarchy**.</span></span>  
  
-   <span data-ttu-id="1273a-137">Можно также щелкнуть дочерний уровень иерархии и нажать клавишу **Delete**.</span><span class="sxs-lookup"><span data-stu-id="1273a-137">Or, click a child level, and then press **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1273a-138">Если дочерний уровень иерархии был переименован, его имя уже не будет совпадать с именем столбца, из которого уровень был скопирован.</span><span class="sxs-lookup"><span data-stu-id="1273a-138">If you rename a hierarchy child level, it no longer shares the same name as the column that it is copied from.</span></span> <span data-ttu-id="1273a-139">Для просмотра столбца, из которого был скопирован уровень, используйте команду **Отобразить имя источника** .</span><span class="sxs-lookup"><span data-stu-id="1273a-139">Use the **Show Source Name** command to see which column it was copied from.</span></span>  
  
#### <a name="to-show-a-source-name"></a><span data-ttu-id="1273a-140">Отображение имени источника</span><span class="sxs-lookup"><span data-stu-id="1273a-140">To show a source name</span></span>  
  
-   <span data-ttu-id="1273a-141">Щелкните правой кнопкой мыши дочерний уровень иерархии и выберите пункт **Отобразить имя источника**.</span><span class="sxs-lookup"><span data-stu-id="1273a-141">Right-click a hierarchy child level, and then click **Show Source Name**.</span></span> <span data-ttu-id="1273a-142">Появится имя столбца, из которого он был скопирован.</span><span class="sxs-lookup"><span data-stu-id="1273a-142">The name of the column that it was copied from appears.</span></span>  
  
##  <a name="delete-a-hierarchy"></a><a name="bkmk_delete"></a><span data-ttu-id="1273a-143">Удаление иерархии</span><span class="sxs-lookup"><span data-stu-id="1273a-143">Delete a Hierarchy</span></span>  
  
#### <a name="to-delete-a-hierarchy-and-remove-its-child-levels"></a><span data-ttu-id="1273a-144">Удаление иерархии и ее дочерних уровней</span><span class="sxs-lookup"><span data-stu-id="1273a-144">To delete a hierarchy and remove its child levels</span></span>  
  
-   <span data-ttu-id="1273a-145">Щелкните правой кнопкой мыши родительский уровень иерархии и выберите пункт «Удалить иерархию».</span><span class="sxs-lookup"><span data-stu-id="1273a-145">Right-click the parent hierarchy level, and then click Delete Hierarchy.</span></span>  
  
-   <span data-ttu-id="1273a-146">Можно также щелкнуть родительский уровень иерархии и нажать клавишу «Delete».</span><span class="sxs-lookup"><span data-stu-id="1273a-146">Or, click the parent hierarchy level, and then press Delete.</span></span> <span data-ttu-id="1273a-147">При этом также удаляются все дочерние уровни.</span><span class="sxs-lookup"><span data-stu-id="1273a-147">This also removes all the child levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1273a-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="1273a-148">See Also</span></span>  
 <span data-ttu-id="1273a-149">[Конструктор табличных моделей &#40;табличные&#41;SSAS](../tabular-model-designer-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="1273a-149">[Tabular Model Designer &#40;SSAS Tabular&#41;](../tabular-model-designer-ssas-tabular.md) </span></span>  
 <span data-ttu-id="1273a-150">[Иерархии &#40;табличные&#41;SSAS](hierarchies-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="1273a-150">[Hierarchies &#40;SSAS Tabular&#41;](hierarchies-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="1273a-151">Меры (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="1273a-151">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
