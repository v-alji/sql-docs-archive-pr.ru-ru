---
title: Определение куба | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8aa4ac2d-857f-4048-baa0-0f314e207cf6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 354a05840dd2e091f956454858edd5c75c8c4bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654544"
---
# <a name="defining-a-cube"></a><span data-ttu-id="95eef-102">Определение куба</span><span class="sxs-lookup"><span data-stu-id="95eef-102">Defining a Cube</span></span>
  <span data-ttu-id="95eef-103">Мастер кубов помогает определить для куба группы мер и измерения.</span><span class="sxs-lookup"><span data-stu-id="95eef-103">The Cube Wizard helps you define the measure groups and dimensions for a cube.</span></span> <span data-ttu-id="95eef-104">В следующей задаче с помощью мастера кубов будет построен куб.</span><span class="sxs-lookup"><span data-stu-id="95eef-104">In the following task, you will use the Cube Wizard to build a cube.</span></span>  
  
### <a name="to-define-a-cube-and-its-properties"></a><span data-ttu-id="95eef-105">Определение куба и его свойств</span><span class="sxs-lookup"><span data-stu-id="95eef-105">To define a cube and its properties</span></span>  
  
1.  <span data-ttu-id="95eef-106">В обозревателе решений щелкните правой кнопкой мыши узел **Кубы**и выберите команду **Создать куб**.</span><span class="sxs-lookup"><span data-stu-id="95eef-106">In Solution Explorer, right-click **Cubes**, and then click **New Cube**.</span></span> <span data-ttu-id="95eef-107">Появится мастер кубов.</span><span class="sxs-lookup"><span data-stu-id="95eef-107">The Cube Wizard appears.</span></span>  
  
2.  <span data-ttu-id="95eef-108">На странице **Мастер кубов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95eef-108">On the **Welcome to the Cube Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="95eef-109">Убедитесь в том, что на странице **Выбор метода создания** выбран параметр **Использовать существующие таблицы** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95eef-109">On the **Select Creation Method** page, verify that the **Use existing tables** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="95eef-110">Убедитесь в том, что на странице **Выбор таблиц групп мер** выбрано представление источника данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="95eef-110">On the **Select Measure Group Tables** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="95eef-111">Нажмите кнопку **Предложить** , чтобы мастер кубов предложил таблицы для создания групп мер.</span><span class="sxs-lookup"><span data-stu-id="95eef-111">Click **Suggest** to have the cube wizard suggest tables to use to create measure groups.</span></span>  
  
     <span data-ttu-id="95eef-112">Мастер просматривает все таблицы и предлагает **InternetSales** в качестве таблицы группы мер.</span><span class="sxs-lookup"><span data-stu-id="95eef-112">The wizard examines the tables and suggests **InternetSales** as a measure group table.</span></span> <span data-ttu-id="95eef-113">Таблицы групп мер, также называемые таблицами фактов, содержат меры, которые могут представлять интерес (например, число проданных единиц).</span><span class="sxs-lookup"><span data-stu-id="95eef-113">Measure group tables, also called fact tables, contain the measures you are interested in, such as the number of units sold.</span></span>  
  
6.  <span data-ttu-id="95eef-114">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95eef-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="95eef-115">На странице **Выбор мер** просмотрите выбранные меры в группе мер **Интернет-продажи** и снимите флажки для следующих мер:</span><span class="sxs-lookup"><span data-stu-id="95eef-115">On the **Select Measures** page, review the selected measures in the **Internet Sales** measure group, and then clear the check boxes for the following measures:</span></span>  
  
    -   <span data-ttu-id="95eef-116">**Promotion Key**</span><span class="sxs-lookup"><span data-stu-id="95eef-116">**Promotion Key**</span></span>  
  
    -   <span data-ttu-id="95eef-117">**Currency Key**</span><span class="sxs-lookup"><span data-stu-id="95eef-117">**Currency Key**</span></span>  
  
    -   <span data-ttu-id="95eef-118">**Sales Territory Key**</span><span class="sxs-lookup"><span data-stu-id="95eef-118">**Sales Territory Key**</span></span>  
  
    -   <span data-ttu-id="95eef-119">**Revision Number**</span><span class="sxs-lookup"><span data-stu-id="95eef-119">**Revision Number**</span></span>  
  
     <span data-ttu-id="95eef-120">По умолчанию мастер выбирает в качестве мер все числовые столбцы в таблице фактов, которые не привязаны к измерениям.</span><span class="sxs-lookup"><span data-stu-id="95eef-120">By default, the wizard selects as measures all numeric columns in the fact table that are not linked to dimensions.</span></span> <span data-ttu-id="95eef-121">Однако эти четыре столбца не являются фактическими мерами.</span><span class="sxs-lookup"><span data-stu-id="95eef-121">However, these four columns are not actual measures.</span></span> <span data-ttu-id="95eef-122">Первые три представляют собой ключевые значения, связывающие таблицу фактов с таблицами измерений, которые не используются в первоначальной версии этого куба.</span><span class="sxs-lookup"><span data-stu-id="95eef-122">The first three are key values that link the fact table with dimension tables that are not used in the initial version of this cube.</span></span>  
  
8.  <span data-ttu-id="95eef-123">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95eef-123">Click **Next**.</span></span>  
  
9. <span data-ttu-id="95eef-124">Убедитесь в том, что на странице **Выбор существующих измерений** выбрано ранее созданное измерение **Дата** , и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95eef-124">On the **Select Existing Dimensions** page, make sure the **Date** dimension that you created earlier is selected, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="95eef-125">На странице **Выбор новых измерений** выберите новые измерения, которые необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="95eef-125">On the **Select New Dimensions** page, select the new dimensions to be created.</span></span> <span data-ttu-id="95eef-126">Для этого убедитесь в том, что установлены флажки **Заказчик**, **География**и **Продукт** , а флажок **InternetSales** снят.</span><span class="sxs-lookup"><span data-stu-id="95eef-126">To do this, verify that the **Customer**, **Geography**, and **Product** check boxes are selected, and then clear the **InternetSales** check box.</span></span>  
  
11. <span data-ttu-id="95eef-127">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95eef-127">Click **Next**.</span></span>  
  
12. <span data-ttu-id="95eef-128">На странице **Завершение работы мастера** измените имя куба на `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="95eef-128">On the **Completing the Wizard** page, change the name of the cube to `Analysis Services Tutorial`.</span></span> <span data-ttu-id="95eef-129">На панели просмотра отобразится группа мер **InternetSales** и входящие в нее меры.</span><span class="sxs-lookup"><span data-stu-id="95eef-129">In the Preview pane, you can see the **InternetSales** measure group and its measures.</span></span> <span data-ttu-id="95eef-130">Кроме того, будут показаны измерения **Дата**, **Заказчик** и **Продукт** .</span><span class="sxs-lookup"><span data-stu-id="95eef-130">You can also see the **Date**, **Customer,** and **Product** dimensions.</span></span>  
  
13. <span data-ttu-id="95eef-131">Чтобы завершить работу мастера, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="95eef-131">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="95eef-132">В обозревателе решений в проекте "Учебник по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] " появится куб "Учебник [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] " в папке **Кубы** , а измерения баз данных "Заказчик" и "Продукт" появятся в папке **Измерения** .</span><span class="sxs-lookup"><span data-stu-id="95eef-132">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube appears in the **Cubes** folder, and the Customer and Product database dimensions appear in the **Dimensions** folder.</span></span> <span data-ttu-id="95eef-133">Кроме того, в центре среды разработки на вкладке «Структура куба» будет отображен куб «Учебник [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ».</span><span class="sxs-lookup"><span data-stu-id="95eef-133">Additionally, in the center of the development environment, the Cube Structure tab displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
14. <span data-ttu-id="95eef-134">Чтобы лучше рассмотреть измерения и таблицы фактов в кубе, на панели инструментов вкладки "Структура куба" переключите **Масштаб** в значение 50 %.</span><span class="sxs-lookup"><span data-stu-id="95eef-134">On the toolbar of the Cube Structure tab, change the **Zoom** level to 50 percent, so that you can more easily see the dimensions and fact tables in the cube.</span></span> <span data-ttu-id="95eef-135">Обратите внимание, что таблицы фактов выделены желтым цветом, а таблицы измерений — синим.</span><span class="sxs-lookup"><span data-stu-id="95eef-135">Notice that the fact table is yellow and the dimension tables are blue.</span></span>  
  
15. <span data-ttu-id="95eef-136">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="95eef-136">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="95eef-137">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="95eef-137">Next Task in Lesson</span></span>  
 [<span data-ttu-id="95eef-138">Добавление атрибутов к измерениям</span><span class="sxs-lookup"><span data-stu-id="95eef-138">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
  
## <a name="see-also"></a><span data-ttu-id="95eef-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="95eef-139">See Also</span></span>  
 <span data-ttu-id="95eef-140">[Кубы в многомерных моделях](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="95eef-140">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="95eef-141">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="95eef-141">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
