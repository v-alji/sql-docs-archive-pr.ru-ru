---
title: Изменение мер | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7bd48810-15ce-45ff-862b-372d08606995
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd352cbca1d21f5842e075d9cb8e5e766aa369b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666854"
---
# <a name="modifying-measures"></a><span data-ttu-id="32a83-102">Изменение мер</span><span class="sxs-lookup"><span data-stu-id="32a83-102">Modifying Measures</span></span>
  <span data-ttu-id="32a83-103">Свойство **FormatString** позволяет определить параметры форматирования, управляющие способом отображения мер для пользователей.</span><span class="sxs-lookup"><span data-stu-id="32a83-103">You can use the **FormatString** property to define formatting settings that control how measures are displayed to users.</span></span> <span data-ttu-id="32a83-104">В этой задаче предстоит указать свойства форматирования мер валюты и процентов в кубе учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32a83-104">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
### <a name="to-modify-the-measures-of-the-cube"></a><span data-ttu-id="32a83-105">Изменение мер куба</span><span class="sxs-lookup"><span data-stu-id="32a83-105">To modify the measures of the cube</span></span>  
  
1.  <span data-ttu-id="32a83-106">Перейдите на вкладку **Структура куба** конструктора кубов для куба учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , разверните группу мер **Internet Sales** на панели **Меры** , щелкните правой кнопкой мыши элемент **Order Quantity**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="32a83-106">Switch to the **Cube Structure** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, expand the **Internet Sales** measure group in the **Measures** pane, right-click **Order Quantity**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="32a83-107">В окне свойств нажмите значок канцелярской кнопки **Автоматически скрыть** , чтобы оставить окно свойств постоянно открытым.</span><span class="sxs-lookup"><span data-stu-id="32a83-107">In the Properties window, click the **Auto Hide** pushpin icon to pin the Properties window open.</span></span>  
  
     <span data-ttu-id="32a83-108">Если окно свойств остается постоянно открытым, изменять свойства нескольких элементов куба проще.</span><span class="sxs-lookup"><span data-stu-id="32a83-108">It is easier to change properties for several items in the cube when the Properties window remains open.</span></span>  
  
3.  <span data-ttu-id="32a83-109">В окне свойств щелкните список **FormatString** и введите **#,#**.</span><span class="sxs-lookup"><span data-stu-id="32a83-109">In the Properties window, click the **FormatString** list, and then type **#,#**.</span></span>  
  
4.  <span data-ttu-id="32a83-110">На панели инструментов вкладки **Структура куба** нажмите значок **Показывать сетку мер** слева.</span><span class="sxs-lookup"><span data-stu-id="32a83-110">On the toolbar of the **Cube Structure** tab, click the **Show Measures Grid** icon on the left.</span></span>  
  
     <span data-ttu-id="32a83-111">Сетка просмотра позволяет выбрать несколько мер одновременно.</span><span class="sxs-lookup"><span data-stu-id="32a83-111">The grid view lets you select multiple measures at the same time.</span></span>  
  
5.  <span data-ttu-id="32a83-112">Выберите следующие меры.</span><span class="sxs-lookup"><span data-stu-id="32a83-112">Select the following measures.</span></span> <span data-ttu-id="32a83-113">Можно выбрать несколько мер. Для этого щелкните каждую из них, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="32a83-113">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="32a83-114">**Unit Price**</span><span class="sxs-lookup"><span data-stu-id="32a83-114">**Unit Price**</span></span>  
  
    -   <span data-ttu-id="32a83-115">**Extended Amount**</span><span class="sxs-lookup"><span data-stu-id="32a83-115">**Extended Amount**</span></span>  
  
    -   <span data-ttu-id="32a83-116">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="32a83-116">**Discount Amount**</span></span>  
  
    -   <span data-ttu-id="32a83-117">**Product Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="32a83-117">**Product Standard Cost**</span></span>  
  
    -   <span data-ttu-id="32a83-118">**Total Product Cost**</span><span class="sxs-lookup"><span data-stu-id="32a83-118">**Total Product Cost**</span></span>  
  
    -   <span data-ttu-id="32a83-119">**Объем продаж**</span><span class="sxs-lookup"><span data-stu-id="32a83-119">**Sales Amount**</span></span>  
  
    -   <span data-ttu-id="32a83-120">**Tax Amt**</span><span class="sxs-lookup"><span data-stu-id="32a83-120">**Tax Amt**</span></span>  
  
    -   <span data-ttu-id="32a83-121">**Freight**</span><span class="sxs-lookup"><span data-stu-id="32a83-121">**Freight**</span></span>  
  
6.  <span data-ttu-id="32a83-122">В окне свойств в списке **FormatString** выберите параметр **Валюта**.</span><span class="sxs-lookup"><span data-stu-id="32a83-122">In the Properties window, in the **FormatString** list, select **Currency**.</span></span>  
  
7.  <span data-ttu-id="32a83-123">В раскрывающемся списке в верхней части окна свойств (под строкой названия) выберите меру **Процент скидки от стоимости единицы товара**, а затем выберите значение **Процент** в списке **FormatString** .</span><span class="sxs-lookup"><span data-stu-id="32a83-123">In the drop-down list at the top of the Properties window (right below the title bar), select the measure **Unit Price Discount Pct**, and then select **Percent** in the **FormatString** list.</span></span>  
  
8.  <span data-ttu-id="32a83-124">В окно свойств измените свойство **Name** для меры **процент скидки цены за единицу** на `Unit Price Discount Percentage` .</span><span class="sxs-lookup"><span data-stu-id="32a83-124">In the Properties window, change the **Name** property for the **Unit Price Discount Pct** measure to `Unit Price Discount Percentage`.</span></span>  
  
9. <span data-ttu-id="32a83-125">На панели **меры** щелкните **налоги AMT** и измените имя этой меры на `Tax Amount` .</span><span class="sxs-lookup"><span data-stu-id="32a83-125">In the **Measures** pane, click **Tax Amt** and change the name of this measure to `Tax Amount`.</span></span>  
  
10. <span data-ttu-id="32a83-126">В окне свойств нажмите значок **Автоматически скрыть** , чтобы скрыть окно свойств, а затем нажмите кнопку **Показывать дерево мер** на вкладке панели инструментов **Структура куба** .</span><span class="sxs-lookup"><span data-stu-id="32a83-126">In the Properties window, click the **Auto Hide** icon to hide the Properties window, and then click **Show Measures Tree** on the toolbar of the **Cube Structure** tab.</span></span>  
  
11. <span data-ttu-id="32a83-127">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="32a83-127">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="32a83-128">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="32a83-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="32a83-129">Изменение измерения «Заказчик»</span><span class="sxs-lookup"><span data-stu-id="32a83-129">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="32a83-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="32a83-130">See Also</span></span>  
 <span data-ttu-id="32a83-131">[Определение измерений базы данных](multidimensional-models/define-database-dimensions.md) </span><span class="sxs-lookup"><span data-stu-id="32a83-131">[Define Database Dimensions](multidimensional-models/define-database-dimensions.md) </span></span>  
 [<span data-ttu-id="32a83-132">Настройка свойств мер</span><span class="sxs-lookup"><span data-stu-id="32a83-132">Configure Measure Properties</span></span>](multidimensional-models/configure-measure-properties.md)  
  
  
