---
title: Занятие 10. Создание иерархий | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e2561d3-4890-4495-a9cd-84eb88508938
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d0982a05c37c28167e44e3f9f082ea5113b59bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732174"
---
# <a name="lesson-10-create-hierarchies"></a><span data-ttu-id="d05eb-102">Урок 10. Создание иерархий</span><span class="sxs-lookup"><span data-stu-id="d05eb-102">Lesson 10: Create Hierarchies</span></span>
  <span data-ttu-id="d05eb-103">На этом занятии мы создадим иерархии.</span><span class="sxs-lookup"><span data-stu-id="d05eb-103">In this lesson, you will create hierarchies.</span></span> <span data-ttu-id="d05eb-104">Иерархии представляют собой группы столбцов, расположенных по уровням; например иерархия География может иметь подуровни для страны, государства, округа и города.</span><span class="sxs-lookup"><span data-stu-id="d05eb-104">Hierarchies are groups of columns arranged in levels; for example, a Geography hierarchy might have sub-levels for Country, State, County, and City.</span></span> <span data-ttu-id="d05eb-105">Иерархии могут отображаться отдельно от других столбцов в списке полей клиентского приложения отчетов, что упрощает для пользователей клиента навигацию и включение в отчет.</span><span class="sxs-lookup"><span data-stu-id="d05eb-105">Hierarchies can appear separate from other columns in a reporting client application field list, making them easier for client users to navigate and include in a report.</span></span> <span data-ttu-id="d05eb-106">Дополнительные сведения см. в разделе [Иерархии (табличные службы SSAS)](tabular-models/hierarchies-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d05eb-106">To learn more, see [Hierarchies &#40;SSAS Tabular&#41;](tabular-models/hierarchies-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="d05eb-107">Для создания иерархий в конструкторе моделей используется *Представление диаграмм*.</span><span class="sxs-lookup"><span data-stu-id="d05eb-107">To create hierarchies, you will use the model designer in *Diagram View*.</span></span> <span data-ttu-id="d05eb-108">Создание иерархий и управление ими с помощью конструктора моделей в представлении данных не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d05eb-108">Creating and managing hierarchies is not supported in the model designer in Data View.</span></span>  
  
 <span data-ttu-id="d05eb-109">Предполагаемое время выполнения этого занятия: **20 минут**</span><span class="sxs-lookup"><span data-stu-id="d05eb-109">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d05eb-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d05eb-110">Prerequisites</span></span>  
 <span data-ttu-id="d05eb-111">Этот раздел входит в учебник по табличному моделированию, который следует изучать в предложенном порядке.</span><span class="sxs-lookup"><span data-stu-id="d05eb-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="d05eb-112">Прежде чем выполнять задания в этом занятии, необходимо завершить предыдущее [Занятие 9. Создание перспектив](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="d05eb-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
## <a name="create-hierarchies"></a><span data-ttu-id="d05eb-113">Создание иерархий</span><span class="sxs-lookup"><span data-stu-id="d05eb-113">Create Hierarchies</span></span>  
  
#### <a name="to-create-a-category-hierarchy-in-the-product-table"></a><span data-ttu-id="d05eb-114">Создание иерархии «Категория» в таблице «Продукт»</span><span class="sxs-lookup"><span data-stu-id="d05eb-114">To create a Category hierarchy in the Product table</span></span>  
  
1.  <span data-ttu-id="d05eb-115">В конструкторе моделей в `Model` меню выберите пункт **представление модели**, а затем пункт **представление диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="d05eb-115">In the model designer, click on the `Model` menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="d05eb-116">Для изменения просмотра объектов в представлении диаграмм воспользуйтесь элементами управления «Мини-карта» в верхнем правом углу конструктора моделей.</span><span class="sxs-lookup"><span data-stu-id="d05eb-116">Use the Minimap controls at the top-right of the model designer to change how you can view objects in Diagram View.</span></span> <span data-ttu-id="d05eb-117">При изменении объектов в представлении диаграмм новое представление будет сохранено при сохранении проекта.</span><span class="sxs-lookup"><span data-stu-id="d05eb-117">If you reposition objects in Diagram View, that view will be retained when you save the project.</span></span>  
  
2.  <span data-ttu-id="d05eb-118">В конструкторе моделей щелкните правой кнопкой мыши `Product` таблицу и выберите команду **создать иерархию**.</span><span class="sxs-lookup"><span data-stu-id="d05eb-118">In the model designer, right-click the `Product` table, and then click **Create Hierarchy**.</span></span> <span data-ttu-id="d05eb-119">Внизу окна таблицы появится новая иерархия.</span><span class="sxs-lookup"><span data-stu-id="d05eb-119">A new hierarchy appears at the bottom of the table window.</span></span>  
  
3.  <span data-ttu-id="d05eb-120">В поле имя иерархии Переименуйте иерархию, введя `Category` , и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="d05eb-120">In the hierarchy name, rename the hierarchy by typing `Category`, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="d05eb-121">В `Product` таблице щелкните столбец **имя категории продуктов** , а затем перетащите его в `Category` иерархию, а затем выпустите поверх `Category` имени.</span><span class="sxs-lookup"><span data-stu-id="d05eb-121">In the `Product` table, click the **Product Category Name** column, then drag it to the `Category` hierarchy, and then release on top of the `Category` name.</span></span>  
  
5.  <span data-ttu-id="d05eb-122">В `Category` иерархии щелкните правой кнопкой мыши столбец **имя категории продуктов** , выберите команду **Переименовать**, а затем введите `Category` .</span><span class="sxs-lookup"><span data-stu-id="d05eb-122">In the `Category` hierarchy, right-click the **Product Category Name** column, then click **Rename**, and then type `Category`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d05eb-123">Изменение имени столбца в иерархии не влияет на имя этого столбца в таблице.</span><span class="sxs-lookup"><span data-stu-id="d05eb-123">Renaming a column in a hierarchy does not rename that column in the table.</span></span> <span data-ttu-id="d05eb-124">Столбец в иерархии является просто представлением столбца в таблице.</span><span class="sxs-lookup"><span data-stu-id="d05eb-124">A column in a hierarchy is just a representation of the column in the table.</span></span>  
  
6.  <span data-ttu-id="d05eb-125">В `Product` таблице щелкните правой кнопкой мыши столбец **Имя подкатегории продуктов** , затем в контекстном меню выберите **Добавить в иерархию**, а затем щелкните `Category` .</span><span class="sxs-lookup"><span data-stu-id="d05eb-125">In the `Product` table, right-click the **Product Subcategory Name** column, then in the context menu, point to **Add to Hierarchy**, and then click `Category`.</span></span>  
  
7.  <span data-ttu-id="d05eb-126">Переименуйте **Имя подкатегории продуктов** в `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="d05eb-126">Rename **Product Subcategory Name** to `Subcategory`.</span></span>  
  
8.  <span data-ttu-id="d05eb-127">С помощью перетаскивания или с помощью команды **Добавить в иерархию** в контекстном меню добавьте столбцы **имя модели** и **Название продукта** (по порядку) и поместите их под столбцом **Имя подкатегории продуктов** .</span><span class="sxs-lookup"><span data-stu-id="d05eb-127">By using click and drag, or by using the **Add to Hierarchy** command in the context menu, add the **Model Name** and **Product Name** columns (in order) and place them beneath the **Product Subcategory Name** column.</span></span> <span data-ttu-id="d05eb-128">Переименуйте эти столбцы `Model` и `Product` соответственно.</span><span class="sxs-lookup"><span data-stu-id="d05eb-128">Rename these columns `Model` and `Product`, respectively.</span></span>  
  
#### <a name="to-create-hierarchies-in-the-date-table"></a><span data-ttu-id="d05eb-129">Создание иерархий в таблице «Дата»</span><span class="sxs-lookup"><span data-stu-id="d05eb-129">To create hierarchies in the Date table</span></span>  
  
1.  <span data-ttu-id="d05eb-130">В конструкторе моделей щелкните правой кнопкой мыши таблицу **Дата** и выберите команду **Создать иерархию**.</span><span class="sxs-lookup"><span data-stu-id="d05eb-130">In the model designer, right-click the **Date** table, and then click **Create Hierarchy**.</span></span>  
  
2.  <span data-ttu-id="d05eb-131">Переименуйте иерархию в **Календарь**.</span><span class="sxs-lookup"><span data-stu-id="d05eb-131">Rename the hierarchy to **Calendar**.</span></span>  
  
3.  <span data-ttu-id="d05eb-132">Добавьте следующие столбцы по порядку, а затем переименуйте их.</span><span class="sxs-lookup"><span data-stu-id="d05eb-132">Add the following columns, in-order, and then rename them:</span></span>  
  
    |<span data-ttu-id="d05eb-133">Столбец</span><span class="sxs-lookup"><span data-stu-id="d05eb-133">Column</span></span>|<span data-ttu-id="d05eb-134">Переименовать в:</span><span class="sxs-lookup"><span data-stu-id="d05eb-134">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="d05eb-135">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="d05eb-135">Calendar Year</span></span>|<span data-ttu-id="d05eb-136">Год</span><span class="sxs-lookup"><span data-stu-id="d05eb-136">Year</span></span>|  
    |<span data-ttu-id="d05eb-137">Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="d05eb-137">Calendar Semester</span></span>|<span data-ttu-id="d05eb-138">Семестр</span><span class="sxs-lookup"><span data-stu-id="d05eb-138">Semester</span></span>|  
    |<span data-ttu-id="d05eb-139">Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="d05eb-139">Calendar Quarter</span></span>|<span data-ttu-id="d05eb-140">Quarter</span><span class="sxs-lookup"><span data-stu-id="d05eb-140">Quarter</span></span>|  
    |<span data-ttu-id="d05eb-141">Месячный календарь</span><span class="sxs-lookup"><span data-stu-id="d05eb-141">Month Calendar</span></span>|<span data-ttu-id="d05eb-142">Месяц</span><span class="sxs-lookup"><span data-stu-id="d05eb-142">Month</span></span>|  
    |<span data-ttu-id="d05eb-143">День месяца</span><span class="sxs-lookup"><span data-stu-id="d05eb-143">Day Of Month</span></span>|<span data-ttu-id="d05eb-144">День</span><span class="sxs-lookup"><span data-stu-id="d05eb-144">Day</span></span>|  
  
4.  <span data-ttu-id="d05eb-145">В таблице **Дата** повторите указанные выше шаги и создайте иерархию **Финансовый период** , включив перечисленные ниже столбцы.</span><span class="sxs-lookup"><span data-stu-id="d05eb-145">In the **Date** table, repeat the above steps, creating a **Fiscal** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="d05eb-146">Столбец</span><span class="sxs-lookup"><span data-stu-id="d05eb-146">Column</span></span>|<span data-ttu-id="d05eb-147">Переименовать в:</span><span class="sxs-lookup"><span data-stu-id="d05eb-147">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="d05eb-148">Финансовый год</span><span class="sxs-lookup"><span data-stu-id="d05eb-148">Fiscal Year</span></span>|<span data-ttu-id="d05eb-149">Год</span><span class="sxs-lookup"><span data-stu-id="d05eb-149">Year</span></span>|  
    |<span data-ttu-id="d05eb-150">Финансовый семестр</span><span class="sxs-lookup"><span data-stu-id="d05eb-150">Fiscal Semester</span></span>|<span data-ttu-id="d05eb-151">Семестр</span><span class="sxs-lookup"><span data-stu-id="d05eb-151">Semester</span></span>|  
    |<span data-ttu-id="d05eb-152">Финансовый квартал</span><span class="sxs-lookup"><span data-stu-id="d05eb-152">Fiscal Quarter</span></span>|<span data-ttu-id="d05eb-153">Quarter</span><span class="sxs-lookup"><span data-stu-id="d05eb-153">Quarter</span></span>|  
    |<span data-ttu-id="d05eb-154">Месячный календарь</span><span class="sxs-lookup"><span data-stu-id="d05eb-154">Month Calendar</span></span>|<span data-ttu-id="d05eb-155">Месяц</span><span class="sxs-lookup"><span data-stu-id="d05eb-155">Month</span></span>|  
    |<span data-ttu-id="d05eb-156">День месяца</span><span class="sxs-lookup"><span data-stu-id="d05eb-156">Day Of Month</span></span>|<span data-ttu-id="d05eb-157">День</span><span class="sxs-lookup"><span data-stu-id="d05eb-157">Day</span></span>|  
  
5.  <span data-ttu-id="d05eb-158">Наконец, в таблице **Дата** повторите указанные выше шаги и создайте иерархию **Производственный календарь** , включив перечисленные ниже столбцы.</span><span class="sxs-lookup"><span data-stu-id="d05eb-158">Finally, in the **Date** table, repeat the above steps, creating a **Production Calendar** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="d05eb-159">Столбец</span><span class="sxs-lookup"><span data-stu-id="d05eb-159">Column</span></span>|<span data-ttu-id="d05eb-160">Переименовать в:</span><span class="sxs-lookup"><span data-stu-id="d05eb-160">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="d05eb-161">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="d05eb-161">Calendar Year</span></span>|<span data-ttu-id="d05eb-162">Год</span><span class="sxs-lookup"><span data-stu-id="d05eb-162">Year</span></span>|  
    |<span data-ttu-id="d05eb-163">Номер недели года</span><span class="sxs-lookup"><span data-stu-id="d05eb-163">Week Number Of Year</span></span>|<span data-ttu-id="d05eb-164">Неделя</span><span class="sxs-lookup"><span data-stu-id="d05eb-164">Week</span></span>|  
    |<span data-ttu-id="d05eb-165">День недели</span><span class="sxs-lookup"><span data-stu-id="d05eb-165">Day Of Week</span></span>|<span data-ttu-id="d05eb-166">День</span><span class="sxs-lookup"><span data-stu-id="d05eb-166">Day</span></span>|  
  
## <a name="next-steps"></a><span data-ttu-id="d05eb-167">Next Steps</span><span class="sxs-lookup"><span data-stu-id="d05eb-167">Next Steps</span></span>  
 <span data-ttu-id="d05eb-168">Чтобы продолжить изучение этого учебника, перейдите к следующему занятию [Занятие 11. Создание секций](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="d05eb-168">To continue this tutorial, go to the next lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
  
