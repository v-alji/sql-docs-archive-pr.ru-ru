---
title: Задание и настройка единиц измерения (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a15a96c3-7d2c-433e-a440-4ea051e967a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c01523dad9a96d2d45b96474d36873bac2484343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654799"
---
# <a name="set-and-configure-measurement-units-report-builder-and-ssrs"></a><span data-ttu-id="04128-102">Задание и настройка единиц измерения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="04128-102">Set and Configure Measurement Units (Report Builder and SSRS)</span></span>
  <span data-ttu-id="04128-103">Индикаторы могут иметь два вида единиц измерения: процентные и числовые.</span><span class="sxs-lookup"><span data-stu-id="04128-103">Indicators provide two measurement units: percentage and numeric.</span></span> <span data-ttu-id="04128-104">По умолчанию в качестве единиц измерения у индикаторов настроены процентные показатели.</span><span class="sxs-lookup"><span data-stu-id="04128-104">By default, indicators are configured to use percentages as the measurement unit.</span></span> <span data-ttu-id="04128-105">Таким образом, значения индикаторов, назначаемые для каждого значка в наборе индикаторов, определяются процентным диапазоном.</span><span class="sxs-lookup"><span data-stu-id="04128-105">This means that the indicator values assigned to each icon in the indicator set are determined by a percentage range.</span></span> <span data-ttu-id="04128-106">Диапазоны в процентах равномерно разделяются по значкам в наборе индикаторов.</span><span class="sxs-lookup"><span data-stu-id="04128-106">The percentage ranges are evenly divided across the icons in the indicator set.</span></span> <span data-ttu-id="04128-107">Каждый значок отображает состояние индикатора.</span><span class="sxs-lookup"><span data-stu-id="04128-107">Each icon represents an indicator state.</span></span> <span data-ttu-id="04128-108">Процентные показатели для каждого значка в наборе индикаторов можно изменять, задавая различные начальные и конечные процентные значения.</span><span class="sxs-lookup"><span data-stu-id="04128-108">You can change the percentages for each icon in the indicator set by specifying different start and end percentages.</span></span> <span data-ttu-id="04128-109">Индикаторы могут также автоматически определять минимальное и максимальное значения данных.</span><span class="sxs-lookup"><span data-stu-id="04128-109">Indicators also automatically detect the minimum and maximum values in the data.</span></span>  
  
 <span data-ttu-id="04128-110">В качестве единицы измерения можно выбрать и числовое значение.</span><span class="sxs-lookup"><span data-stu-id="04128-110">You can change the measurement unit to be a numeric value.</span></span> <span data-ttu-id="04128-111">В этом случае минимальное и максимальное значения не задаются. Вместо этого задаются только начальные и конечные значения для каждого значка, используемого индикатором.</span><span class="sxs-lookup"><span data-stu-id="04128-111">In this case, you do not specify minimum or maximum for the data; instead, you provide only the start and end values for each icon that the indicator uses.</span></span>  
  
 <span data-ttu-id="04128-112">Такие параметры, как единицы измерения, можно задать с помощью выражений.</span><span class="sxs-lookup"><span data-stu-id="04128-112">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="04128-113">Дополнительные сведения см. в разделе [Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="04128-113">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-use-the-numeric-state-measurement-unit"></a><span data-ttu-id="04128-114">Использование числовых единиц измерения</span><span class="sxs-lookup"><span data-stu-id="04128-114">To use the numeric state measurement unit</span></span>  
  
1.  <span data-ttu-id="04128-115">Щелкните правой кнопкой мыши индикатор, который необходимо изменить, и выберите **Свойства индикатора**.</span><span class="sxs-lookup"><span data-stu-id="04128-115">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="04128-116">Нажмите кнопку **Значения и состояния** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="04128-116">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="04128-117">В списке **Единица измерения состояний** щелкните **Числовая**.</span><span class="sxs-lookup"><span data-stu-id="04128-117">In the **States Measurement Unit** list, click **Numeric**.</span></span>  
  
     <span data-ttu-id="04128-118">Также можно нажать кнопку **Выражение** (*fx*), чтобы изменить выражение, которое задает значение параметра.</span><span class="sxs-lookup"><span data-stu-id="04128-118">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="04128-119">Для каждого значка в наборе индикаторов обновите значения в текстовых полях **Начало** и **Конец** .</span><span class="sxs-lookup"><span data-stu-id="04128-119">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="04128-120">Также можно нажать кнопку **Выражение** (*fx*), чтобы изменить выражение, которое задает значение параметров **Начало** и **Конец** .</span><span class="sxs-lookup"><span data-stu-id="04128-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04128-121">Значения в текстовых полях **Начало** и **Конец** должны быть числовыми.</span><span class="sxs-lookup"><span data-stu-id="04128-121">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-percentage-measurement-unit"></a><span data-ttu-id="04128-122">Использование процентных единиц измерения</span><span class="sxs-lookup"><span data-stu-id="04128-122">To use the percentage measurement unit</span></span>  
  
1.  <span data-ttu-id="04128-123">Щелкните правой кнопкой мыши индикатор, который необходимо изменить, и выберите **Свойства индикатора**.</span><span class="sxs-lookup"><span data-stu-id="04128-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="04128-124">Нажмите кнопку **Значения и состояния** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="04128-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="04128-125">В списке **Единица измерения состояний** щелкните **Процентная**.</span><span class="sxs-lookup"><span data-stu-id="04128-125">In the **States Measurement Unit** list, click **Percentage**.</span></span>  
  
     <span data-ttu-id="04128-126">Также можно нажать кнопку **Выражение** (*fx*), чтобы изменить выражение, которое задает значение параметра.</span><span class="sxs-lookup"><span data-stu-id="04128-126">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="04128-127">Измените параметры **Минимум** и **Максимум** , чтобы вместо автоматического обнаружения минимальных и максимальных значений данных, используемых индикатором, применялись конкретные значения (необязательно).</span><span class="sxs-lookup"><span data-stu-id="04128-127">Optionally, change the **Minimum** and **Maximum** options to use specific values instead of automatically detecting the minimum and maximum values of the data that the indicator uses.</span></span> <span data-ttu-id="04128-128">Значение **Минимум** должно быть меньше значения **Максимум**.</span><span class="sxs-lookup"><span data-stu-id="04128-128">The value of **Minimum** must be smaller than the value of **Maximum**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04128-129">Если минимальное и максимальное значения заданы явно, то индикатором используется заданный диапазон значений независимо от фактического минимального и максимального значения в данных.</span><span class="sxs-lookup"><span data-stu-id="04128-129">If you explicitly set minimum and maximum values, that value range is used by the indicator regardless of the actual the minimum and maximum values in the data.</span></span> <span data-ttu-id="04128-130">Таким образом, значения ниже минимума и выше максимума исключаются из оценки, с помощью которой определяется значок индикатора, отображаемый в отчете.</span><span class="sxs-lookup"><span data-stu-id="04128-130">This means that values lower than the minimum and higher than the maximum are excluded from the evaluation that determine what indictor icon to show in the report.</span></span>  
  
     <span data-ttu-id="04128-131">Также можно нажать кнопку **Выражение** (*fx*), чтобы изменить выражение, которое задает значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="04128-131">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the option.</span></span>  
  
5.  <span data-ttu-id="04128-132">Для каждого значка в наборе индикаторов обновите значения в текстовых полях **Начало** и **Конец** .</span><span class="sxs-lookup"><span data-stu-id="04128-132">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="04128-133">Также можно нажать кнопку **Выражение** (*fx*), чтобы изменить выражение, которое задает значение параметров **Начало** и **Конец** .</span><span class="sxs-lookup"><span data-stu-id="04128-133">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04128-134">Значения в текстовых полях **Начало** и **Конец** должны быть числовыми.</span><span class="sxs-lookup"><span data-stu-id="04128-134">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04128-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="04128-135">See Also</span></span>  
 [<span data-ttu-id="04128-136">Индикаторы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="04128-136">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
