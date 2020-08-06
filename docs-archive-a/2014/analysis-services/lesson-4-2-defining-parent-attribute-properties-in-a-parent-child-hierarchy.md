---
title: Определение свойств родительского атрибута в иерархии типа «родители-потомки» | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d78fa73-a13b-4e12-bbd0-43e5307f760c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1dfa4340bdc161809cf3821e5cb1f0609399e1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665640"
---
# <a name="defining-parent-attribute-properties-in-a-parent-child-hierarchy"></a><span data-ttu-id="8560c-102">Определение свойств родительского атрибута в иерархии «родители-потомки»</span><span class="sxs-lookup"><span data-stu-id="8560c-102">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>
  <span data-ttu-id="8560c-103">Иерархия типа «родители-потомки» представляет собой иерархию в измерении, которая основана на двух столбцах таблицы.</span><span class="sxs-lookup"><span data-stu-id="8560c-103">A parent-child hierarchy is a hierarchy in a dimension that is based on two table columns.</span></span> <span data-ttu-id="8560c-104">Вместе эти столбцы определяют иерархическую связь между элементами измерения.</span><span class="sxs-lookup"><span data-stu-id="8560c-104">Together, these columns define the hierarchical relationships among the members of the dimension.</span></span> <span data-ttu-id="8560c-105">Первый столбец, называемый *ключевым столбцом элемента*, идентифицирует каждый элемент измерения.</span><span class="sxs-lookup"><span data-stu-id="8560c-105">The first column, called the *member key column*, identifies each dimension member.</span></span> <span data-ttu-id="8560c-106">Второй столбец, называемый *родительским столбцом*, идентифицирует родителя для каждого из элементов измерения.</span><span class="sxs-lookup"><span data-stu-id="8560c-106">The other column, called the *parent column*, identifies the parent of each dimension member.</span></span> <span data-ttu-id="8560c-107">Свойство **NamingTemplate** родительского атрибута определяет имя каждого уровня в иерархии типа "родители-потомки", а свойство **MembersWithData** — будут ли отображаться данные для родительских элементов.</span><span class="sxs-lookup"><span data-stu-id="8560c-107">The **NamingTemplate** property of a parent attribute determines the name of each level in the parent-child hierarchy, and the **MembersWithData** property determines whether data for parent members should be displayed.</span></span>

 <span data-ttu-id="8560c-108">Дополнительные сведения см. в разделе [Иерархия "родители-потомки](multidimensional-models/parent-child-dimension.md)", [атрибуты в иерархиях "родители-потомки](multidimensional-models/parent-child-dimension-attributes.md) "</span><span class="sxs-lookup"><span data-stu-id="8560c-108">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md), [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>

> [!NOTE]
>  <span data-ttu-id="8560c-109">Если измерение создается с помощью мастера измерений, мастер распознает таблицы, которые имеют связи типа «родители-потомки», и автоматически определяет иерархию типа «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="8560c-109">When you use the Dimension Wizard to create a dimension, the wizard recognizes the tables that have parent-child relationships and automatically defines the parent-child hierarchy for you.</span></span>

 <span data-ttu-id="8560c-110">При выполнении задач этого раздела будет создан шаблон именования, определяющий имя каждого из уровней в иерархии типа "родители-потомки" в измерении **Сотрудник** .</span><span class="sxs-lookup"><span data-stu-id="8560c-110">In the tasks in this topic, you will create a naming template that defines the name for each level in the parent-child hierarchy in the **Employee** dimension.</span></span> <span data-ttu-id="8560c-111">Затем этот родительский атрибут будет настроен таким образом, чтобы все данные о родителях были скрыты и отображались только данные по продажам для элементов конечного уровня.</span><span class="sxs-lookup"><span data-stu-id="8560c-111">You will then configure the parent attribute to hide all parent data, so that only the sales for leaf-level members are displayed.</span></span>

## <a name="browsing-the-employee-dimension"></a><span data-ttu-id="8560c-112">Просмотр измерения Employee</span><span class="sxs-lookup"><span data-stu-id="8560c-112">Browsing the Employee Dimension</span></span>

1.  <span data-ttu-id="8560c-113">В обозревателе решений дважды щелкните файл **Employee.dim** в папке **Измерения** , чтобы открыть конструктор измерений для измерения "Сотрудник".</span><span class="sxs-lookup"><span data-stu-id="8560c-113">In Solution Explorer, double-click **Employee.dim** in the **Dimensions** folder to open Dimension Designer for the Employee dimension.</span></span>

2.  <span data-ttu-id="8560c-114">Перейдите на вкладку **Браузер** , убедитесь в том, что в списке **Иерархия** выбран элемент **Сотрудники** , а затем разверните элемент **Все сотрудники** .</span><span class="sxs-lookup"><span data-stu-id="8560c-114">Click the **Browser** tab, verify that **Employees** is selected in the **Hierarchy** list, and then expand the **All Employees** member.</span></span>

     <span data-ttu-id="8560c-115">Обратите внимание, что сотрудник **Кен Дж. Санчес** — менеджер высшего уровня в этой иерархии типа "родители-потомки".</span><span class="sxs-lookup"><span data-stu-id="8560c-115">Notice that **Ken J. Sánchez** is the top-level manager in this parent-child hierarchy.</span></span>

3.  <span data-ttu-id="8560c-116">Выберите элемент **Кен Дж. Санчес** .</span><span class="sxs-lookup"><span data-stu-id="8560c-116">Select the **Ken J. Sánchez** member.</span></span>

     <span data-ttu-id="8560c-117">Обратите внимание, что имя уровня для этого элемента — **Уровень 02**.</span><span class="sxs-lookup"><span data-stu-id="8560c-117">Notice that the level name for this member is **Level 02**.</span></span> <span data-ttu-id="8560c-118">(Имя уровня указано сразу после значения **Текущий уровень:** над элементом **Все сотрудники** .) В следующей задаче будут определены более понятные имена для каждого уровня.</span><span class="sxs-lookup"><span data-stu-id="8560c-118">(The level name appears after **Current level:** immediately above the **All Employees** member.) In the next task, you will define more descriptive names for each level.</span></span>

4.  <span data-ttu-id="8560c-119">Разверните элемент **Кен Дж. Санчес** , чтобы увидеть имена всех сотрудников, подчиняющихся этому менеджеру, а затем выберите элемент **Брайан С. Уэлкер** , чтобы узнать имя этого уровня.</span><span class="sxs-lookup"><span data-stu-id="8560c-119">Expand **Ken J. Sánchez** to view the names of the employees who report to this manager, and then select **Brian S. Welcker** to view the name of this level.</span></span>

     <span data-ttu-id="8560c-120">Обратите внимание, что имя уровня для этого элемента — **Уровень 03**.</span><span class="sxs-lookup"><span data-stu-id="8560c-120">Notice that the level name for this member is **Level 03**.</span></span>

5.  <span data-ttu-id="8560c-121">В обозревателе решений дважды щелкните файл **Analysis Services Tutorial.cube** в папке **Кубы** , чтобы открыть конструктор кубов для куба "Учебник по [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ".</span><span class="sxs-lookup"><span data-stu-id="8560c-121">In Solution Explorer, double-click **Analysis Services Tutorial.cube** in the **Cubes** folder to open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>

6.  <span data-ttu-id="8560c-122">Перейдите на вкладку **Браузер** .</span><span class="sxs-lookup"><span data-stu-id="8560c-122">Click the **Browser** tab.</span></span>

7.  <span data-ttu-id="8560c-123">Щелкните значок Excel, а затем выберите **Включить** при появлении запроса на включение подключений.</span><span class="sxs-lookup"><span data-stu-id="8560c-123">Click the Excel icon, and then click **Enable** when prompted to enable connections.</span></span>

8.  <span data-ttu-id="8560c-124">В списке полей сводной таблицы разверните узел **Продажи через торговых посредников**.</span><span class="sxs-lookup"><span data-stu-id="8560c-124">In the PivotTable Field List, expand **Reseller Sales**.</span></span> <span data-ttu-id="8560c-125">Перетащите меру **Товарооборот посредников — объем продаж** в область значений.</span><span class="sxs-lookup"><span data-stu-id="8560c-125">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

9. <span data-ttu-id="8560c-126">В списке полей сводной таблицы разверните узел **Сотрудник**, а затем перетащите иерархию **Сотрудники** в область **Строки** .</span><span class="sxs-lookup"><span data-stu-id="8560c-126">In the PivotTable Field List, expand **Employee**, and then drag the **Employees** hierarchy to the **Rows** area.</span></span>

     <span data-ttu-id="8560c-127">Все элементы иерархии Employees будут добавлены в столбец A в отчете сводной таблицы.</span><span class="sxs-lookup"><span data-stu-id="8560c-127">All the members of the Employees hierarchy are added to column A of the PivotTable report.</span></span>

     <span data-ttu-id="8560c-128">На следующем рисунке показана развернутая иерархия Employees.</span><span class="sxs-lookup"><span data-stu-id="8560c-128">The following image shows the Employees hierarchy expanded.</span></span>

10. <span data-ttu-id="8560c-129">![Сводная таблица, отображающая иерархию Employees](../../2014/tutorials/media/l4-employee-1.gif "Сводная таблица, отображающая иерархию Employees")</span><span class="sxs-lookup"><span data-stu-id="8560c-129">![PivotTable showing Employees hierarchy](../../2014/tutorials/media/l4-employee-1.gif "PivotTable showing Employees hierarchy")</span></span>

     <span data-ttu-id="8560c-130">Обратите внимание, что продажи, совершенные каждым менеджером уровня 03, отображаются и на уровне 04.</span><span class="sxs-lookup"><span data-stu-id="8560c-130">Notice that the sales made by each manager in Level 03 are also displayed in Level 04.</span></span> <span data-ttu-id="8560c-131">Это связано с тем, что каждый менеджер является также подчиненным другого менеджера.</span><span class="sxs-lookup"><span data-stu-id="8560c-131">This is because each manager is also an employee of another manager.</span></span> <span data-ttu-id="8560c-132">В следующей задаче предстоит скрыть эти суммы продаж.</span><span class="sxs-lookup"><span data-stu-id="8560c-132">In the next task, you will hide these sale amounts.</span></span>

## <a name="modifying-parent-attribute-properties-in-the-employee-dimension"></a><span data-ttu-id="8560c-133">Изменение свойств родительского атрибута в измерении Employee</span><span class="sxs-lookup"><span data-stu-id="8560c-133">Modifying Parent Attribute Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="8560c-134">В конструкторе измерений откройте измерение **Сотрудник** .</span><span class="sxs-lookup"><span data-stu-id="8560c-134">Switch to Dimension Designer for the **Employee** dimension.</span></span>

2.  <span data-ttu-id="8560c-135">Перейдите на вкладку **Структура измерения** , а затем выберите иерархию атрибута **Сотрудники** на панели **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="8560c-135">Click the **Dimension Structure** tab, and then select the **Employees** attribute hierarchy in the **Attributes** pane.</span></span>

     <span data-ttu-id="8560c-136">Обратите внимание на уникальный значок атрибута.</span><span class="sxs-lookup"><span data-stu-id="8560c-136">Notice the unique icon for this attribute.</span></span> <span data-ttu-id="8560c-137">Этот значок указывает, что атрибут является ключом родителя в иерархии типа «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="8560c-137">This icon signifies that the attribute is the parent key in a parent-child hierarchy.</span></span> <span data-ttu-id="8560c-138">Обратите внимание, что в окне свойств свойство **Использование** для этого атрибута определено как **Родитель**.</span><span class="sxs-lookup"><span data-stu-id="8560c-138">Notice also, in the Properties window, that the **Usage** property for the attribute is defined as **Parent**.</span></span> <span data-ttu-id="8560c-139">Это свойство устанавливается мастером измерений во время создания измерения.</span><span class="sxs-lookup"><span data-stu-id="8560c-139">This property was set by the Dimension Wizard when the dimension was designed.</span></span> <span data-ttu-id="8560c-140">Мастер автоматически выявляет связи типа «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="8560c-140">The wizard automatically detected the parent-child relationship.</span></span>

3.  <span data-ttu-id="8560c-141">В окне свойств в ячейке свойств**NamingTemplate**нажмите кнопку с многоточием ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="8560c-141">In the Properties window, click the ellipsis button (**...**) in the **NamingTemplate** property cell.</span></span>

     <span data-ttu-id="8560c-142">В диалоговом окне **Шаблон именования уровней** необходимо задать шаблон именования уровней, который определяет имена уровней в иерархии типа "родители-потомки", отображаемых при просмотре кубов.</span><span class="sxs-lookup"><span data-stu-id="8560c-142">In the **Level Naming Template** dialog box, you define the level naming template that determines the level names in the parent-child hierarchy that are displayed to users as they browse cubes.</span></span>

4.  <span data-ttu-id="8560c-143">Во второй строке **\*** введите в столбце **имя** значение **уровень \* сотрудника** , а затем щелкните третью строку.</span><span class="sxs-lookup"><span data-stu-id="8560c-143">In the second row, the **\*** row, type **Employee Level \*** in the **Name** column, and then click the third row.</span></span>

     <span data-ttu-id="8560c-144">Обратите внимание, что в поле **Результат** каждый уровень теперь называется "Уровень сотрудника", за которым следует последовательно увеличивающееся число.</span><span class="sxs-lookup"><span data-stu-id="8560c-144">Notice under **Result** that each level will now be named "Employee Level" followed by a sequentially increasing number.</span></span>

     <span data-ttu-id="8560c-145">На рисунке ниже показаны изменения в диалоговом окне **Шаблон именования уровней** .</span><span class="sxs-lookup"><span data-stu-id="8560c-145">The following image shows the changes in the **Level Naming Template** dialog box.</span></span>

     <span data-ttu-id="8560c-146">![Диалоговое окно «Шаблон именования уровней»](../../2014/tutorials/media/l4-namingtemplate.gif "Диалоговое окно «Шаблон именования уровней»")</span><span class="sxs-lookup"><span data-stu-id="8560c-146">![Level Naming Template dialog box](../../2014/tutorials/media/l4-namingtemplate.gif "Level Naming Template dialog box")</span></span>

5.  <span data-ttu-id="8560c-147">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8560c-147">Click **OK**.</span></span>

6.  <span data-ttu-id="8560c-148">В окне "Свойства" для атрибута **Сотрудники** в ячейке свойств **MembersWithData** выберите **NonLeafDataHidden** , чтобы изменить это значение для атрибута **Сотрудники** .</span><span class="sxs-lookup"><span data-stu-id="8560c-148">In the Properties window for the **Employees** attribute, in the **MembersWithData** property cell, select **NonLeafDataHidden** to change this value for the **Employees** attribute.</span></span>

     <span data-ttu-id="8560c-149">Данные в иерархии типа «родители-потомки», которые относятся к элементам уровня, не являющегося конечными, будут скрыты.</span><span class="sxs-lookup"><span data-stu-id="8560c-149">This will cause data that is related to non-leaf level members in the parent-child hierarchy to be hidden.</span></span>

## <a name="browsing-the-employee-dimension-with-the-modified-attributes"></a><span data-ttu-id="8560c-150">Просмотр измерения Employee с измененными атрибутами</span><span class="sxs-lookup"><span data-stu-id="8560c-150">Browsing the Employee Dimension with the Modified Attributes</span></span>

1.  <span data-ttu-id="8560c-151">В меню **Построение** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="8560c-151">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="8560c-152">После успешного завершения развертывания перейдите в конструктор кубов и откройте куб "Учебник по [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ". Затем нажмите кнопку **Повторное соединение** на панели инструментов вкладки **Браузер** .</span><span class="sxs-lookup"><span data-stu-id="8560c-152">When deployment has successfully completed, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Reconnect** on the toolbar of the **Browser** tab.</span></span>

3.  <span data-ttu-id="8560c-153">Щелкните ярлык Excel, а затем выберите **Включить**.</span><span class="sxs-lookup"><span data-stu-id="8560c-153">Click the Excel icon, and then click **Enable**.</span></span>

4.  <span data-ttu-id="8560c-154">Перетащите меру **Товарооборот посредников — объем продаж** в область значений.</span><span class="sxs-lookup"><span data-stu-id="8560c-154">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

5.  <span data-ttu-id="8560c-155">Перетащите иерархию **Сотрудники** в область "Метки строк".</span><span class="sxs-lookup"><span data-stu-id="8560c-155">Drag the **Employees** hierarchy to the Row Labels area.</span></span>

     <span data-ttu-id="8560c-156">На следующем рисунке показаны изменения, внесенные в иерархию Employees.</span><span class="sxs-lookup"><span data-stu-id="8560c-156">The following image shows the changes that you made to the Employees hierarchy.</span></span> <span data-ttu-id="8560c-157">Обратите внимание на то, что Stephen Y. Jiang больше не отображается как сотрудник самого себя.</span><span class="sxs-lookup"><span data-stu-id="8560c-157">Notice that Stephen Y. Jiang no longer appears as an employee of himself.</span></span>

     <span data-ttu-id="8560c-158">![Измененная иерархия Employees](../../2014/tutorials/media/l4-employee-2.png "Измененная иерархия Employees")</span><span class="sxs-lookup"><span data-stu-id="8560c-158">![Modified Employees hierarchy](../../2014/tutorials/media/l4-employee-2.png "Modified Employees hierarchy")</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="8560c-159">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="8560c-159">Next Task in Lesson</span></span>
 [<span data-ttu-id="8560c-160">Автоматическое группирование элементов атрибута</span><span class="sxs-lookup"><span data-stu-id="8560c-160">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)

## <a name="see-also"></a><span data-ttu-id="8560c-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="8560c-161">See Also</span></span>
 <span data-ttu-id="8560c-162">Атрибуты [иерархии «родители-потомки](multidimensional-models/parent-child-dimension.md) [» в иерархиях «родители-потомки](multidimensional-models/parent-child-dimension-attributes.md) »</span><span class="sxs-lookup"><span data-stu-id="8560c-162">[Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>


