---
title: Автоматическое группирование элементов атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9fb2cda3-a122-4a4c-82e0-3454865eef04
author: minewiskan
ms.author: owend
ms.openlocfilehash: 820231263362a92584a15556e999d69f286349b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751551"
---
# <a name="automatically-grouping-attribute-members"></a><span data-ttu-id="2c7d5-102">Автоматическое группирование элементов атрибута</span><span class="sxs-lookup"><span data-stu-id="2c7d5-102">Automatically Grouping Attribute Members</span></span>
  <span data-ttu-id="2c7d5-103">При просмотре куба обычно выполняется распределение по измерениям элементов одной иерархии атрибута на основе элементов другой иерархии атрибута.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-103">When you browse a cube, you typically dimension the members of one attribute hierarchy by the members of another attribute hierarchy.</span></span> <span data-ttu-id="2c7d5-104">Например, можно сгруппировать продажи по таким признакам, как город, приобретенный товар или пол.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-104">For example, you might group customer sales by city, by product purchased, or by gender.</span></span> <span data-ttu-id="2c7d5-105">Однако с определенными типами атрибутов полезно [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] автоматически создавать группирование элементов атрибутов на основе распределения элементов в иерархии атрибутов.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-105">However, with certain types of attributes, it is useful to have [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] automatically create groupings of attribute members based on the distribution of the members within an attribute hierarchy.</span></span> <span data-ttu-id="2c7d5-106">Например, с помощью служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] можно объединить заказчиков в группы на основе их годового дохода.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-106">For example, you can have [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] create groups of yearly income values for customers.</span></span> <span data-ttu-id="2c7d5-107">При этом пользователь, просматривающий иерархию атрибута, будет видеть названия и значения групп вместо самих элементов групп.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-107">When you do this, users who browse the attribute hierarchy will see the names and values of the groups instead of the members themselves.</span></span> <span data-ttu-id="2c7d5-108">Данный подход ограничивает количество отображаемых уровней, что упрощает анализ данных.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-108">This limits the number of levels that are presented to users, which can be more useful for analysis.</span></span>

 <span data-ttu-id="2c7d5-109">Свойство **DiscretizationMethod** определяет, создают ли службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] группирования, а также определяет тип выполняемого группирования.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-109">The **DiscretizationMethod** property determines whether [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates groupings, and determines the type of grouping that is performed.</span></span> <span data-ttu-id="2c7d5-110">По умолчанию в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] группирование не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-110">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] does not perform any groupings.</span></span> <span data-ttu-id="2c7d5-111">При включении автоматического группирования можно настроить параметры служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] таким образом, чтобы выполнялся автоматический выбор оптимального метода группирования, основанного на структуре данного атрибута, либо выбрать один из алгоритмов группирования в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="2c7d5-111">When you enable automatic groupings, you can allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to automatically determine the best grouping method based on the structure of the attribute, or you can choose one of the grouping algorithms in the following list to specify the grouping method:</span></span>

 <span data-ttu-id="2c7d5-112">**EqualAreas** [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] диапазоны групп создаются таким образом, что элементы измерения распределяются по группам пропорционально.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-112">**EqualAreas** [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates group ranges so that the total population of dimension members is distributed equally across the groups.</span></span>

 <span data-ttu-id="2c7d5-113">**Кластеры** [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] создает группы, выполняя одномерный кластеризацию входных значений с помощью метода кластеризации K-средних с распределениями по Гауссу.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-113">**Clusters** [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates groups by performing single-dimensional clustering on the input values by using the K-Means clustering method with Gaussian distributions.</span></span> <span data-ttu-id="2c7d5-114">Эта функция применима только в отношении числовых столбцов.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-114">This option is valid only for numeric columns.</span></span>

 <span data-ttu-id="2c7d5-115">После выбора метода группирования необходимо указать количество групп, используя свойство **DiscretizationBucketCount** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-115">After you specify a grouping method, you must specify the number of groups, by using the **DiscretizationBucketCount** property.</span></span> <span data-ttu-id="2c7d5-116">Дополнительные сведения см. в разделе [группирование членов атрибутов &#40;дискретизация&#41;](multidimensional-models/attribute-properties-group-attribute-members.md)</span><span class="sxs-lookup"><span data-stu-id="2c7d5-116">For more information, see [Group Attribute Members &#40;Discretization&#41;](multidimensional-models/attribute-properties-group-attribute-members.md)</span></span>

 <span data-ttu-id="2c7d5-117">В ходе выполнения задач данного раздела будут опробованы следующие критерии группирования: значение годового дохода в измерении **Заказчик** , количество часов отсутствия по болезни в измерении **Сотрудники** , данные о количестве часов отпуска сотрудников в измерении **Сотрудники** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-117">In the tasks in this topic, you will enable different types of groupings for the following: the yearly income values in the **Customer** dimension; the number of employee sick leave hours in the **Employees** dimension; and the number of employee vacation hours in the **Employees** dimension.</span></span> <span data-ttu-id="2c7d5-118">Затем предстоит выполнить обработку куба учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и просмотреть результаты группирования элементов.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-118">You will then process and browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube to view the effect of the member groups.</span></span> <span data-ttu-id="2c7d5-119">На конечной стадии будут изменены свойства групп элементов, чтобы выявить эффект от изменения типа группирования.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-119">Finally, you will modify the member group properties to see the effect of the change in grouping type.</span></span>

## <a name="grouping-attribute-hierarchy-members-in-the-customer-dimension"></a><span data-ttu-id="2c7d5-120">Группирование элементов иерархии атрибута в измерении «Заказчик»</span><span class="sxs-lookup"><span data-stu-id="2c7d5-120">Grouping Attribute Hierarchy Members in the Customer Dimension</span></span>

1.  <span data-ttu-id="2c7d5-121">В обозревателе решений дважды щелкните элемент **Заказчик** в папке **Измерения** . Откроется конструктор измерений для измерения "Заказчик".</span><span class="sxs-lookup"><span data-stu-id="2c7d5-121">In Solution Explorer, double-click **Customer** in the **Dimensions** folder to open Dimension Designer for the Customer dimension.</span></span>

2.  <span data-ttu-id="2c7d5-122">На панели **Представление источника данных** щелкните правой кнопкой мыши таблицу **Заказчик** и выберите пункт **Просмотр данных**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-122">In the **Data Source View** pane, right-click the **Customer** table, and then click **Explore Data**.</span></span>

     <span data-ttu-id="2c7d5-123">Обратите внимание на диапазон данных в столбце **YearlyIncome** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-123">Notice the range of values for the **YearlyIncome** column.</span></span> <span data-ttu-id="2c7d5-124">Указанные значения используются для заполнения иерархии атрибута **Yearly Income** , если не включено группирование элементов.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-124">These values become the members of the **Yearly Income** attribute hierarchy, unless you enable member grouping.</span></span>

3.  <span data-ttu-id="2c7d5-125">Закройте вкладку **Просмотр таблицы Customer** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-125">Close the **Explore Customer Table** tab.</span></span>

4.  <span data-ttu-id="2c7d5-126">На панели **Атрибуты** выберите атрибут **Yearly Income**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-126">In the **Attributes** pane, select **Yearly Income**.</span></span>

5.  <span data-ttu-id="2c7d5-127">В окно свойств измените значение свойства **DiscretizationMethod** на **автоматически** и измените значение свойства **DiscretizationBucketCount** на `5` .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-127">In the Properties window, change the value for the **DiscretizationMethod** property to **Automatic** and change the value for the **DiscretizationBucketCount** property to `5`.</span></span>

     <span data-ttu-id="2c7d5-128">На следующем рисунке показаны измененные свойства атрибута **Yearly Income**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-128">The following image shows the modified properties for **Yearly Income**.</span></span>

     <span data-ttu-id="2c7d5-129">![Измененные свойства столбца Yearly Income](../../2014/tutorials/media/l4-discretizationmethod-1.gif "Измененные свойства столбца Yearly Income")</span><span class="sxs-lookup"><span data-stu-id="2c7d5-129">![Modified properties for Yearly Income](../../2014/tutorials/media/l4-discretizationmethod-1.gif "Modified properties for Yearly Income")</span></span>

## <a name="grouping-attribute-hierarchy-members-in-the-employee-dimension"></a><span data-ttu-id="2c7d5-130">Группирование элементов иерархии атрибута в измерении Employee</span><span class="sxs-lookup"><span data-stu-id="2c7d5-130">Grouping Attribute Hierarchy Members in the Employee Dimension</span></span>

1.  <span data-ttu-id="2c7d5-131">В конструкторе измерений откройте измерение «Сотрудник».</span><span class="sxs-lookup"><span data-stu-id="2c7d5-131">Switch to Dimension Designer for the Employee dimension.</span></span>

2.  <span data-ttu-id="2c7d5-132">На панели **Представление источника данных** щелкните правой кнопкой мыши таблицу **Сотрудник** и выберите пункт **Просмотр данных**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-132">In the **Data Source View** pane, right-click the **Employee** table, and then click **Explore Data**.</span></span>

     <span data-ttu-id="2c7d5-133">Обратите внимание на значения столбцов **SickLeaveHours** и **VacationHours** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-133">Notice the values for the **SickLeaveHours** column and the **VacationHours** column.</span></span>

3.  <span data-ttu-id="2c7d5-134">Закройте вкладку **Просмотр таблицы Employee** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-134">Close the **Explore Employee Table** tab.</span></span>

4.  <span data-ttu-id="2c7d5-135">На панели **Атрибуты** выберите атрибут **Sick Leave Hours**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-135">In the **Attributes** pane, select **Sick Leave Hours**.</span></span>

5.  <span data-ttu-id="2c7d5-136">В окно свойств измените значение свойства **DiscretizationMethod** на **Clusters** и измените значение свойства **DiscretizationBucketCount** на `5` .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-136">In the Properties window, change the value for the **DiscretizationMethod** property to **Clusters** and change the value for the **DiscretizationBucketCount** property to `5`.</span></span>

6.  <span data-ttu-id="2c7d5-137">На панели **Атрибуты** выберите атрибут **Vacation Hours**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-137">In the **Attributes** pane, select **Vacation Hours**.</span></span>

7.  <span data-ttu-id="2c7d5-138">В окно свойств измените значение свойства **DiscretizationMethod** на **равные области** и измените значение свойства **DiscretizationBucketCount** на `5` .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-138">In the Properties window, change the value for the **DiscretizationMethod** property to **Equal Areas** and change the value for the **DiscretizationBucketCount** property to `5`.</span></span>

## <a name="browsing-the-modified-attribute-hierarchies"></a><span data-ttu-id="2c7d5-139">Просмотр измененных иерархий атрибутов</span><span class="sxs-lookup"><span data-stu-id="2c7d5-139">Browsing the Modified Attribute Hierarchies</span></span>

1.  <span data-ttu-id="2c7d5-140">В меню **Построение** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-140">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="2c7d5-141">После завершения развертывания переключитесь в конструктор кубов на куб по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial, а затем нажмите кнопку **Повторное соединение** на вкладке **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-141">When deployment has successfully completed, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Reconnect** on the **Browser** tab.</span></span>

3.  <span data-ttu-id="2c7d5-142">Щелкните ярлык Excel, а затем выберите **Включить**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-142">Click the Excel icon, and then click **Enable**.</span></span>

4.  <span data-ttu-id="2c7d5-143">Перетащите меру **Продажи через Интернет — сумма продаж** в область значений списка полей сводной таблицы.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-143">Drag the **Internet Sales-Sales Amount** measure to the Values area of the PivotTable Field List.</span></span>

5.  <span data-ttu-id="2c7d5-144">В списке полей разверните измерение **Продукт** , а затем перетащите пользовательскую иерархию **Линии моделей товаров** в область **Метки строк** списка полей.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-144">In the field list, expand the **Product** dimension, and then drag the **Product Model Lines** user hierarchy to the **Row Labels** area of the field list.</span></span>

6.  <span data-ttu-id="2c7d5-145">В списке полей разверните измерение **Заказчик** , разверните папку отображения **Демография** и перетащите иерархию атрибута **Годовой доход** в область **Метки столбцов** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-145">Expand the **Customer** dimension in the field list, expand the **Demographic** display folder, and then drag the **Yearly Income** attribute hierarchy to the **Column Labels** area.</span></span>

     <span data-ttu-id="2c7d5-146">Теперь элементы иерархии атрибута **Годовой доход** сгруппированы в шесть сегментов, один из которых содержит данные о клиентах с неизвестным годовым доходом.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-146">The members of the **Yearly Income** attribute hierarchy are now grouped into six buckets, including a bucket for sales to customers whose yearly income is unknown.</span></span> <span data-ttu-id="2c7d5-147">Отображаются не все сегменты.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-147">Not all buckets are displayed.</span></span>

7.  <span data-ttu-id="2c7d5-148">Удалите иерархию атрибута **Годовой доход** из области столбцов и удалите меру **Продажи через Интернет — сумма продаж** из области **Значения** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-148">Remove the **Yearly Income** attribute hierarchy from the columns area and remove the **Internet Sales-Sales Amount** measure from the **Values** area.</span></span>

8.  <span data-ttu-id="2c7d5-149">Добавьте меру **Товарооборот посредников — сумма продаж** в область данных.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-149">Add the **Reseller Sales-Sales Amount** measure to the data area.</span></span>

9. <span data-ttu-id="2c7d5-150">В списке полей разверните измерение **Сотрудник** , затем узел **Организация**, а затем перетащите **Часы отсутствия по болезни** в область **Метки столбцов**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-150">In the field list, expand the **Employee** dimension, expand **Organization**, then drag **Sick Leave Hours** to **Column Labels**.</span></span>

     <span data-ttu-id="2c7d5-151">Обратите внимание, что все продажи были сделаны сотрудниками, включенными в одну из двух групп.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-151">Notice that all sales are made by employees within one of two groups.</span></span> <span data-ttu-id="2c7d5-152">Кроме того, обратите внимание, что сотрудники, отсутствовавшие по болезни от 32 до 42 часов, сделали существенно больше продаж, чем сотрудники, отсутствовавшие от 20 часов до 31 часа.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-152">Notice also that the employees with 32 - 42 sick leave hours made significantly more sales than employees with 20 - 31 sick leave hours.</span></span>

     <span data-ttu-id="2c7d5-153">На приведенном ниже рисунке приведена зависимость объемов продаж от количества часов отпуска по болезни.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-153">The following image shows sales dimensioned by employee sick leave hours.</span></span>

     <span data-ttu-id="2c7d5-154">![Таблица Sales, разбитая на измерения по количеству часов отпуска сотрудников по болезни](../../2014/tutorials/media/l4-discretizationmethod-2.gif "Таблица Sales, разбитая на измерения по количеству часов отпуска сотрудников по болезни")</span><span class="sxs-lookup"><span data-stu-id="2c7d5-154">![Sales dimensioned by employee sick leave hours](../../2014/tutorials/media/l4-discretizationmethod-2.gif "Sales dimensioned by employee sick leave hours")</span></span>

10. <span data-ttu-id="2c7d5-155">Удалите иерархию атрибута **Sick Leave Hours** из раздела столбцов панели **Данные** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-155">Remove the **Sick Leave Hours** attribute hierarchy from the column area of the **Data** pane.</span></span>

11. <span data-ttu-id="2c7d5-156">Добавьте столбец **Vacation Hours** к разделу столбцов панели **Данные** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-156">Add **Vacation Hours** to the column area of the **Data** pane.</span></span>

     <span data-ttu-id="2c7d5-157">Обратите внимание, что отображаются две группы, созданные с помощью метода группирования по равным областям.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-157">Notice that two groups appear, based on the equal areas grouping method.</span></span> <span data-ttu-id="2c7d5-158">Остальные три группы не показаны, так как не содержат значений.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-158">Three other groups are hidden because they contain no data values.</span></span>

## <a name="modifying-grouping-properties-and-reviewing-the-effect-of-the-changes"></a><span data-ttu-id="2c7d5-159">Изменение свойств группирования и просмотр результата изменений</span><span class="sxs-lookup"><span data-stu-id="2c7d5-159">Modifying Grouping Properties and Reviewing the Effect of the Changes</span></span>

1.  <span data-ttu-id="2c7d5-160">Откройте в конструкторе измерений измерение **Сотрудник** и выберите на панели **Атрибуты** атрибут **Часы отпуска** .</span><span class="sxs-lookup"><span data-stu-id="2c7d5-160">Switch to Dimension Designer for the **Employee** dimension, and then select **Vacation Hours** in the **Attributes** pane.</span></span>

2.  <span data-ttu-id="2c7d5-161">В окне свойств задайте для свойства **DiscretizationBucketCount** значение **10.**</span><span class="sxs-lookup"><span data-stu-id="2c7d5-161">In the Properties window, change the value of the **DiscretizationBucketCount** property to **10.**</span></span>

3.  <span data-ttu-id="2c7d5-162">В меню **Построение** среды [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-162">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

4.  <span data-ttu-id="2c7d5-163">После завершения развертывания переключитесь обратно в конструктор кубов на куб по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-163">When deployment has successfully completed, switch back to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>

5.  <span data-ttu-id="2c7d5-164">На вкладке **Обозреватель** нажмите кнопку **Повторное подключение** , щелкните значок Excel и снова создайте сводную таблицу, чтобы просмотреть результаты изменения метода группирования.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-164">Click **Reconnect** on the **Browser** tab, click the Excel icon, and then reconstruct the PivotTable so that you can view the effect of the change to the grouping method:</span></span>

    1.  <span data-ttu-id="2c7d5-165">Перетащите меру «Товарооборот посредников — сумма продаж» в область значений</span><span class="sxs-lookup"><span data-stu-id="2c7d5-165">Drag Reseller Sales-Sales Amount to Values</span></span>

    2.  <span data-ttu-id="2c7d5-166">Перетащите атрибут «Часы отпуска» (в папке «Организация сотрудников») в область столбцов</span><span class="sxs-lookup"><span data-stu-id="2c7d5-166">Drag Vacation Hours (in the Employees Organization folder) to Columns</span></span>

    3.  <span data-ttu-id="2c7d5-167">Перетащите атрибут «Линии моделей товаров» в область строк</span><span class="sxs-lookup"><span data-stu-id="2c7d5-167">Drag Product Model Lines to Rows</span></span>

     <span data-ttu-id="2c7d5-168">Обратите внимание, что созданы три группы элементов атрибута **Часы отпуска** , в которых содержатся значения по продажам товаров.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-168">Notice that there are now three groups of members of the **Vacation Hours** attribute that have sales values for products.</span></span> <span data-ttu-id="2c7d5-169">В остальных 7 группах содержатся элементы без данных о продажах.</span><span class="sxs-lookup"><span data-stu-id="2c7d5-169">(The other seven groups contain members with no sales data.)</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="2c7d5-170">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="2c7d5-170">Next Task in Lesson</span></span>
 [<span data-ttu-id="2c7d5-171">Скрытие и отключение иерархий атрибутов</span><span class="sxs-lookup"><span data-stu-id="2c7d5-171">Hiding and Disabling Attribute Hierarchies</span></span>](lesson-4-4-hiding-and-disabling-attribute-hierarchies.md)

## <a name="see-also"></a><span data-ttu-id="2c7d5-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c7d5-172">See Also</span></span>
 [<span data-ttu-id="2c7d5-173">Группирование элементов атрибутов (дискретизация)</span><span class="sxs-lookup"><span data-stu-id="2c7d5-173">Group Attribute Members &#40;Discretization&#41;</span></span>](multidimensional-models/attribute-properties-group-attribute-members.md)


