---
title: Добавление фильтра к набору данных (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eed37e74-6a43-4d7c-9959-2d5fa6a6aba9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f51411d31d8ee29bf0f163085077dcee8fd79bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654855"
---
# <a name="add-a-filter-to-a-dataset-report-builder-and-ssrs"></a><span data-ttu-id="6da02-102">Добавление фильтра к набору данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6da02-102">Add a Filter to a Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6da02-103">Добавление фильтра к набору данных ограничивает данные в отчете после извлечения данных из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="6da02-103">Add a filter to a dataset to limit the data in a report after the data is retrieved from an external data source.</span></span> <span data-ttu-id="6da02-104">При добавлении фильтра к набору данных все элементы отчета или области данных используют только данные, соответствующие условиям фильтра.</span><span class="sxs-lookup"><span data-stu-id="6da02-104">When you add a filter to a dataset, all report parts or data regions use only data that matches the filter conditions.</span></span>  
  
 <span data-ttu-id="6da02-105">Для общих источников данных фильтр, примененный ко всем зависимым элементам, должен быть частью определения общего набора данных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="6da02-105">For a shared dataset, a filter that applies to all dependent items must be part of the shared dataset definition on the report server.</span></span> <span data-ttu-id="6da02-106">Отчет или элемент отчета, содержащий экземпляр общего набора данных, допускает создание дополнительного фильтра, который применяется только к этому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="6da02-106">A report or report part that contains an instance of a shared dataset can create an additional filter that applies only to the instance.</span></span>  
  
 <span data-ttu-id="6da02-107">Чтобы добавить фильтр, необходимо указать одно или несколько условий, являющихся уравнениями фильтра.</span><span class="sxs-lookup"><span data-stu-id="6da02-107">To add a filter, you must specify one or more conditions that are filter equations.</span></span> <span data-ttu-id="6da02-108">Уравнение фильтра состоит из выражения, определяющего фильтруемые данные, оператор и значения сравнения.</span><span class="sxs-lookup"><span data-stu-id="6da02-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="6da02-109">Тип данных фильтруемых данных и тип данных значения должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="6da02-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="6da02-110">Фильтрация статистических значений набора данных не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6da02-110">Filtering on aggregate values for a dataset is not supported.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-filter-to-a-shared-dataset"></a><span data-ttu-id="6da02-111">Добавление фильтра в общий набор данных</span><span class="sxs-lookup"><span data-stu-id="6da02-111">To add a filter to a shared dataset</span></span>  
  
1.  <span data-ttu-id="6da02-112">Откройте общий набор данных в режиме общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="6da02-112">Open a shared dataset in shared dataset mode.</span></span>  
  
2.  <span data-ttu-id="6da02-113">На вкладке **Корневая папка** в группе **Общие наборы данных** нажмите «Наборы данных».</span><span class="sxs-lookup"><span data-stu-id="6da02-113">On the **Home** tab, in the **Shared Datasets** group, click Datasets.</span></span> <span data-ttu-id="6da02-114">Откроется диалоговое окно **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="6da02-114">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="6da02-115">Перейдите на вкладку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="6da02-115">Click **Filters**.</span></span> <span data-ttu-id="6da02-116">Откроется список текущих уравнений фильтра.</span><span class="sxs-lookup"><span data-stu-id="6da02-116">This displays the current list of filter equations.</span></span> <span data-ttu-id="6da02-117">По умолчанию этот список пустой.</span><span class="sxs-lookup"><span data-stu-id="6da02-117">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="6da02-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6da02-118">Click **Add**.</span></span> <span data-ttu-id="6da02-119">Появится новое пустое уравнение фильтра.</span><span class="sxs-lookup"><span data-stu-id="6da02-119">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="6da02-120">В поле **Выражение**введите или выберите выражение для фильтра.</span><span class="sxs-lookup"><span data-stu-id="6da02-120">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="6da02-121">Чтобы изменить выражение, нажмите кнопку "Выражение" (*fx*).</span><span class="sxs-lookup"><span data-stu-id="6da02-121">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="6da02-122">Из списка выберите тип данных, соответствующий типу данных в выражении, созданном на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="6da02-122">From the list box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="6da02-123">В поле **Оператор** выберите оператор, который фильтр должен использовать для сравнения значений в полях **Выражение** и **Значение** .</span><span class="sxs-lookup"><span data-stu-id="6da02-123">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="6da02-124">Выбранный оператор определяет число значений, которые используются в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="6da02-124">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="6da02-125">В поле **Значение** введите выражение или значение, с которым фильтр будет сравнивать значение в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="6da02-125">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="6da02-126">Примеры уравнений фильтра см. в разделе [Примеры уравнений фильтра (построитель отчетов и службы SSRS)](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6da02-126">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-filter-to-an-embedded-dataset-or-a-shared-dataset-instance"></a><span data-ttu-id="6da02-127">Добавление фильтра для внедренного набора данных или экземпляра общего набора данных</span><span class="sxs-lookup"><span data-stu-id="6da02-127">To add a filter to an embedded dataset or a shared dataset instance</span></span>  
  
1.  <span data-ttu-id="6da02-128">Откройте отчет в режиме конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="6da02-128">Open a report in report design mode.</span></span>  
  
2.  <span data-ttu-id="6da02-129">В области **Данные отчета** щелкните правой кнопкой мыши набор данных и выберите пункт **Свойства набора данных**.</span><span class="sxs-lookup"><span data-stu-id="6da02-129">Right-click a dataset in the **Report Data** pane and then click **Dataset Properties**.</span></span> <span data-ttu-id="6da02-130">Откроется диалоговое окно **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="6da02-130">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="6da02-131">Перейдите на вкладку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="6da02-131">Click **Filters**.</span></span> <span data-ttu-id="6da02-132">Откроется список текущих уравнений фильтра.</span><span class="sxs-lookup"><span data-stu-id="6da02-132">This displays the current list of filter equations.</span></span> <span data-ttu-id="6da02-133">По умолчанию этот список пустой.</span><span class="sxs-lookup"><span data-stu-id="6da02-133">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="6da02-134">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6da02-134">Click **Add**.</span></span> <span data-ttu-id="6da02-135">Появится новое пустое уравнение фильтра.</span><span class="sxs-lookup"><span data-stu-id="6da02-135">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="6da02-136">В поле **Выражение**введите или выберите выражение для фильтра.</span><span class="sxs-lookup"><span data-stu-id="6da02-136">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="6da02-137">Чтобы изменить выражение, нажмите кнопку "Выражение" (*fx*).</span><span class="sxs-lookup"><span data-stu-id="6da02-137">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="6da02-138">Из раскрывающегося списка выберите тип данных, соответствующий типу данных в выражении, созданном на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="6da02-138">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="6da02-139">В поле **Оператор** выберите оператор, который фильтр должен использовать для сравнения значений в полях **Выражение** и **Значение** .</span><span class="sxs-lookup"><span data-stu-id="6da02-139">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="6da02-140">Выбранный оператор определяет число значений, которые используются в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="6da02-140">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="6da02-141">В поле **Значение** введите выражение или значение, с которым фильтр будет сравнивать значение в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="6da02-141">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="6da02-142">Примеры уравнений фильтра см. в разделе [Примеры уравнений фильтра (построитель отчетов и службы SSRS)](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6da02-142">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6da02-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="6da02-143">See Also</span></span>  
 <span data-ttu-id="6da02-144">[Добавление фильтров набора данных, фильтров области данных и групповых фильтров (построитель отчетов и службы SSRS)](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="6da02-144">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="6da02-145">[Примеры выражений (построитель отчетов и службы SSRS)](../report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6da02-145">[Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6da02-146">Добавление фильтра (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6da02-146">Add a Filter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/add-a-filter-report-builder-and-ssrs.md)  
  
  
