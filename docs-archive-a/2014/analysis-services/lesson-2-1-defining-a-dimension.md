---
title: Определение измерения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 112696db-3838-4b50-91bd-d2ce5fa04ee5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2eb7a695ffc2c0588396a4a9ea655983c26cc719
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654546"
---
# <a name="defining-a-dimension"></a><span data-ttu-id="411ce-102">Определение измерения</span><span class="sxs-lookup"><span data-stu-id="411ce-102">Defining a Dimension</span></span>
  <span data-ttu-id="411ce-103">В следующей задаче с помощью мастера измерений создается измерение Date.</span><span class="sxs-lookup"><span data-stu-id="411ce-103">In the following task, you will use the Dimension Wizard to build a Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="411ce-104">Приступать к этому занятию нужно только после завершения всех процедур из занятия 1.</span><span class="sxs-lookup"><span data-stu-id="411ce-104">This lesson requires that you have completed all the procedures in Lesson 1.</span></span>  
  
### <a name="to-define-a-dimension"></a><span data-ttu-id="411ce-105">Определение измерения</span><span class="sxs-lookup"><span data-stu-id="411ce-105">To define a dimension</span></span>  
  
1.  <span data-ttu-id="411ce-106">В обозревателе решений (справа в Microsoft Visual Studio) щелкните правой кнопкой мыши узел **Измерения**и выберите пункт **Создать измерение**.</span><span class="sxs-lookup"><span data-stu-id="411ce-106">In Solution Explorer (on the right side of Microsoft Visual Studio), right-click **Dimensions**, and then click **New Dimension**.</span></span> <span data-ttu-id="411ce-107">Появится мастер измерений.</span><span class="sxs-lookup"><span data-stu-id="411ce-107">The Dimension Wizard appears.</span></span>  
  
2.  <span data-ttu-id="411ce-108">На странице **Вас приветствует мастер измерений** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="411ce-108">On the **Welcome to the Dimension Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="411ce-109">На странице **Выбор метода создания** выберите параметр **Использовать существующую таблицу** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="411ce-109">On the **Select Creation Method** page, verify that the **Use an existing table** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="411ce-110">Убедитесь в том, что на странице **Определение исходных сведений** выбрано представление источника данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="411ce-110">On the **Specify Source Information** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="411ce-111">В списке **Основная таблица** выберите таблицу **Date**.</span><span class="sxs-lookup"><span data-stu-id="411ce-111">In the **Main table** list, select **Date**.</span></span>  
  
6.  <span data-ttu-id="411ce-112">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="411ce-112">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="411ce-113">На странице **Выбор атрибутов измерения** установите флажки для перечисленных ниже атрибутов:</span><span class="sxs-lookup"><span data-stu-id="411ce-113">On the **Select Dimension Attributes** page, select the check boxes next to the following attributes:</span></span>  
  
    -   <span data-ttu-id="411ce-114">**Ключ даты**</span><span class="sxs-lookup"><span data-stu-id="411ce-114">**Date Key**</span></span>  
  
    -   <span data-ttu-id="411ce-115">**Full Date Alternate Key**</span><span class="sxs-lookup"><span data-stu-id="411ce-115">**Full Date Alternate Key**</span></span>  
  
    -   <span data-ttu-id="411ce-116">**English Month Name**</span><span class="sxs-lookup"><span data-stu-id="411ce-116">**English Month Name**</span></span>  
  
    -   <span data-ttu-id="411ce-117">**Календарный квартал**</span><span class="sxs-lookup"><span data-stu-id="411ce-117">**Calendar Quarter**</span></span>  
  
    -   <span data-ttu-id="411ce-118">**Календарный год**</span><span class="sxs-lookup"><span data-stu-id="411ce-118">**Calendar Year**</span></span>  
  
    -   <span data-ttu-id="411ce-119">**Calendar Semester**</span><span class="sxs-lookup"><span data-stu-id="411ce-119">**Calendar Semester**</span></span>  
  
8.  <span data-ttu-id="411ce-120">Для атрибута **Резервный ключ полной даты** в столбце **Тип атрибута** вместо значения **Обычный** выберите **Дата**.</span><span class="sxs-lookup"><span data-stu-id="411ce-120">Change the setting of the **Full Date Alternate Key** attribute's **Attribute Type** column from **Regular** to **Date**.</span></span> <span data-ttu-id="411ce-121">Для этого щелкните значение **Обычный** в столбце **Тип атрибута** .</span><span class="sxs-lookup"><span data-stu-id="411ce-121">To do this, click **Regular** in the **Attribute Type** column.</span></span> <span data-ttu-id="411ce-122">Щелкните стрелку, чтобы раскрыть список параметров.</span><span class="sxs-lookup"><span data-stu-id="411ce-122">Then click the arrow to expand the options.</span></span> <span data-ttu-id="411ce-123">Затем щелкните **Дата**  >  **Календарь**  >  **Дата**.</span><span class="sxs-lookup"><span data-stu-id="411ce-123">Next, click **Date** > **Calendar** > **Date**.</span></span> <span data-ttu-id="411ce-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="411ce-124">Click **OK**.</span></span> <span data-ttu-id="411ce-125">Повторите эти действия, чтобы изменить тип атрибута в других атрибутах следующим образом:</span><span class="sxs-lookup"><span data-stu-id="411ce-125">Repeat these steps to change the attribute type of the attributes as follows:</span></span>  
  
    -   <span data-ttu-id="411ce-126">**English Month Name** выберите **Месяц**</span><span class="sxs-lookup"><span data-stu-id="411ce-126">**English Month Name** to **Month**</span></span>  
  
    -   <span data-ttu-id="411ce-127">**Calendar Quarter** выберите **Квартал**</span><span class="sxs-lookup"><span data-stu-id="411ce-127">**Calendar Quarter** to **Quarter**</span></span>  
  
    -   <span data-ttu-id="411ce-128">**Calendar Year** выберите **Год**</span><span class="sxs-lookup"><span data-stu-id="411ce-128">**Calendar Year** to **Year**</span></span>  
  
    -   <span data-ttu-id="411ce-129">**Calendar Semester** выберите **Полугодие**</span><span class="sxs-lookup"><span data-stu-id="411ce-129">**Calendar Semester** to **Half Year**</span></span>  
  
9. <span data-ttu-id="411ce-130">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="411ce-130">Click **Next**.</span></span>  
  
10. <span data-ttu-id="411ce-131">На странице **Завершение работы мастера** на панели просмотра будет отображено измерение **Date** и его атрибуты.</span><span class="sxs-lookup"><span data-stu-id="411ce-131">On the **Completing the Wizard** page, in the Preview pane, you can see the **Date** dimension and its attributes.</span></span>  
  
11. <span data-ttu-id="411ce-132">Чтобы завершить работу мастера, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="411ce-132">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="411ce-133">В обозревателе решений в проекте "Учебник по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] " в папке **Измерения** появится измерение Date.</span><span class="sxs-lookup"><span data-stu-id="411ce-133">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the Date dimension appears in the **Dimensions** folder.</span></span> <span data-ttu-id="411ce-134">В центральной части окна среды разработки это измерение отображается в конструкторе измерений.</span><span class="sxs-lookup"><span data-stu-id="411ce-134">In the center of the development environment, Dimension Designer displays the Date dimension.</span></span>  
  
12. <span data-ttu-id="411ce-135">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="411ce-135">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="411ce-136">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="411ce-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="411ce-137">Определение куба</span><span class="sxs-lookup"><span data-stu-id="411ce-137">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="411ce-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="411ce-138">See Also</span></span>  
 <span data-ttu-id="411ce-139">[Измерения в многомерных моделях](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="411ce-139">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="411ce-140">[Создание измерения с помощью существующей таблицы](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="411ce-140">[Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="411ce-141">Создание измерения с помощью мастера измерений</span><span class="sxs-lookup"><span data-stu-id="411ce-141">Create a Dimension Using the Dimension Wizard</span></span>](multidimensional-models/create-a-dimension-using-the-dimension-wizard.md)  
  
  
