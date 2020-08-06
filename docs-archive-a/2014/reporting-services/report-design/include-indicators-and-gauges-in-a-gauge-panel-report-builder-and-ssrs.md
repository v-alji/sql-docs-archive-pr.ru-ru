---
title: Добавление индикаторов и датчиков на панель датчиков (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dff9b67-b483-4c51-a822-6dbe706a6840
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b1107745f54cd94abd7507a3e9b5a706ca5402de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739368"
---
# <a name="include-indicators-and-gauges-in-a-gauge-panel-report-builder-and-ssrs"></a><span data-ttu-id="cba02-102">Добавление индикаторов и датчиков на панель датчиков (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="cba02-102">Include Indicators and Gauges in a Gauge Panel (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cba02-103">Панель датчиков — это контейнер верхнего уровня, который содержит один или несколько датчиков и индикаторов.</span><span class="sxs-lookup"><span data-stu-id="cba02-103">The gauge panel is the top-level container that holds one or more gauges and indicators.</span></span> <span data-ttu-id="cba02-104">Индикаторы могут быть встроены в датчики или помещены рядом с ними на панели датчиков.</span><span class="sxs-lookup"><span data-stu-id="cba02-104">Indicators can be embedded in gauges or placed next to them in the gauge panel.</span></span>  
  
 <span data-ttu-id="cba02-105">Если индикатор и датчик являются смежными на панели датчиков и показывают данные из разных полей, то может потребоваться добавить метки, чтобы было ясно, какие данные представлены датчиком и индикатором.</span><span class="sxs-lookup"><span data-stu-id="cba02-105">If the indicator and gauge are adjacent in the gauge panel and show data from different fields, you might want to add labels to make it clear what data the gauge and indicator convey.</span></span>  
  
 <span data-ttu-id="cba02-106">Параметры датчика и индикатора могут быть заданы с помощью выражений.</span><span class="sxs-lookup"><span data-stu-id="cba02-106">Gauge and indicator options can be set by using expressions.</span></span> <span data-ttu-id="cba02-107">Дополнительные сведения см. в разделе [Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cba02-107">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-indicator-in-a-gauge"></a><span data-ttu-id="cba02-108">Внедрение индикатора в датчик</span><span class="sxs-lookup"><span data-stu-id="cba02-108">To embed an indicator in a gauge</span></span>  
  
1.  <span data-ttu-id="cba02-109">Откройте существующий отчет или создайте новый отчет, содержащий таблицу и матрицу с данными, которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="cba02-109">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="cba02-110">Дополнительные сведения см. в разделах [Таблицы (построитель отчетов и службы SSRS)](tables-report-builder-and-ssrs.md) и [Матрицы (построитель отчетов и службы SSRS)](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cba02-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="cba02-111">Вставьте столбец в таблицу или матрицу.</span><span class="sxs-lookup"><span data-stu-id="cba02-111">Insert a column in your table or matrix.</span></span> <span data-ttu-id="cba02-112">Дополнительные сведения см. в разделе [Вставка или удаление столбца (построитель отчетов и службы SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cba02-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="cba02-113">На вкладке **Вставить** в группе **Области данных** нажмите **Датчик**, затем щелкните ячейку в новом столбце.</span><span class="sxs-lookup"><span data-stu-id="cba02-113">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then, and then click a cell in the new column.</span></span> <span data-ttu-id="cba02-114">Откроется диалоговое окно **Выбор типа датчика** .</span><span class="sxs-lookup"><span data-stu-id="cba02-114">The **Select Gauge Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="cba02-115">Нажмите **Радиальный**.</span><span class="sxs-lookup"><span data-stu-id="cba02-115">Click **Radial**.</span></span> <span data-ttu-id="cba02-116">Будет выбран первый радиальный датчик.</span><span class="sxs-lookup"><span data-stu-id="cba02-116">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="cba02-117">Щелкните датчик.</span><span class="sxs-lookup"><span data-stu-id="cba02-117">Click the gauge.</span></span> <span data-ttu-id="cba02-118">Откроется панель **Данные датчика** .</span><span class="sxs-lookup"><span data-stu-id="cba02-118">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="cba02-119">В области **Значения** в раскрывающемся списке **(Не указано)** выберите поле, значения которого необходимо отобразить в датчике.</span><span class="sxs-lookup"><span data-stu-id="cba02-119">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="cba02-120">Можно также перетащить нужное поле из набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="cba02-120">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="cba02-121">Правой кнопкой мыши щелкните датчик, **Добавить индикатор**, а затем **Дочерний**.</span><span class="sxs-lookup"><span data-stu-id="cba02-121">Right-click the gauge, click **Add Indicator**, and then click **Child**.</span></span> <span data-ttu-id="cba02-122">Откроется диалоговое окно **Выбор стиля индикатора** .</span><span class="sxs-lookup"><span data-stu-id="cba02-122">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="cba02-123">В диалоговом окне **Выбор стиля индикатора** в левой панели выберите тип нужного индикатора, а затем выберите набор индикаторов.</span><span class="sxs-lookup"><span data-stu-id="cba02-123">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="cba02-124">Щелкните индикатор.</span><span class="sxs-lookup"><span data-stu-id="cba02-124">Click the indicator.</span></span> <span data-ttu-id="cba02-125">Откроется панель **Данные датчика** .</span><span class="sxs-lookup"><span data-stu-id="cba02-125">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="cba02-126">В области **Значения** в раскрывающемся списке **(Не указано)** выберите поле, значения которого необходимо отобразить в качестве индикатора.</span><span class="sxs-lookup"><span data-stu-id="cba02-126">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="cba02-127">Можно также перетащить нужное поле из набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="cba02-127">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="cba02-128">Это поле может быть таким же или иным по сравнению с тем, которое используется в датчике.</span><span class="sxs-lookup"><span data-stu-id="cba02-128">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-show-an-indicator-and-gauge-side-by-side"></a><span data-ttu-id="cba02-129">Отображение индикатора и датчика рядом друг с другом</span><span class="sxs-lookup"><span data-stu-id="cba02-129">To show an indicator and gauge side by side</span></span>  
  
1.  <span data-ttu-id="cba02-130">Откройте существующий отчет или создайте новый отчет, содержащий таблицу и матрицу с данными, которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="cba02-130">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="cba02-131">Дополнительные сведения см. в разделах [Таблицы (построитель отчетов и службы SSRS)](tables-report-builder-and-ssrs.md) и [Матрицы (построитель отчетов и службы SSRS)](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cba02-131">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="cba02-132">Вставьте столбец в таблицу или матрицу.</span><span class="sxs-lookup"><span data-stu-id="cba02-132">Insert a column in your table or matrix.</span></span> <span data-ttu-id="cba02-133">Дополнительные сведения см. в разделе [Вставка или удаление столбца (построитель отчетов и службы SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cba02-133">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="cba02-134">На вкладке **Вставить** в группе **Области данных** нажмите **Датчик**, затем щелкните ячейку во вставленном столбце.</span><span class="sxs-lookup"><span data-stu-id="cba02-134">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click a cell in the column you inserted.</span></span> <span data-ttu-id="cba02-135">Откроется диалоговое окно **Выбор типа датчика** .</span><span class="sxs-lookup"><span data-stu-id="cba02-135">The **Select Gauge Type** dialog appears.</span></span>  
  
4.  <span data-ttu-id="cba02-136">Нажмите **Радиальный**.</span><span class="sxs-lookup"><span data-stu-id="cba02-136">Click **Radial**.</span></span> <span data-ttu-id="cba02-137">Будет выбран первый радиальный датчик.</span><span class="sxs-lookup"><span data-stu-id="cba02-137">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="cba02-138">Щелкните датчик.</span><span class="sxs-lookup"><span data-stu-id="cba02-138">Click the gauge.</span></span> <span data-ttu-id="cba02-139">Откроется панель **Данные датчика** .</span><span class="sxs-lookup"><span data-stu-id="cba02-139">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="cba02-140">В области **Значения** в раскрывающемся списке **(Не указано)** выберите поле, значения которого необходимо отобразить в датчике.</span><span class="sxs-lookup"><span data-stu-id="cba02-140">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="cba02-141">Можно также перетащить нужное поле из набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="cba02-141">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="cba02-142">Правой кнопкой мыши щелкните датчик, **Добавить индикатор**, затем **Смежный**.</span><span class="sxs-lookup"><span data-stu-id="cba02-142">Right-click the gauge, click **Add Indicator**, and then click **Adjacent**.</span></span> <span data-ttu-id="cba02-143">Откроется диалоговое окно **Выбор стиля индикатора** .</span><span class="sxs-lookup"><span data-stu-id="cba02-143">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="cba02-144">В диалоговом окне **Выбор стиля индикатора** в левой панели выберите тип нужного индикатора, а затем выберите набор индикаторов.</span><span class="sxs-lookup"><span data-stu-id="cba02-144">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="cba02-145">Щелкните индикатор.</span><span class="sxs-lookup"><span data-stu-id="cba02-145">Click the indicator.</span></span> <span data-ttu-id="cba02-146">Откроется панель **Данные датчика** .</span><span class="sxs-lookup"><span data-stu-id="cba02-146">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="cba02-147">В области **Значения** в раскрывающемся списке **(Не указано)** выберите поле, значения которого необходимо отобразить в качестве индикатора.</span><span class="sxs-lookup"><span data-stu-id="cba02-147">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="cba02-148">Можно также перетащить нужное поле из набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="cba02-148">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="cba02-149">Это поле может быть таким же или иным по сравнению с тем, которое используется в датчике.</span><span class="sxs-lookup"><span data-stu-id="cba02-149">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
14. <span data-ttu-id="cba02-150">Щелкните правой кнопкой мыши панель датчиков и выберите **Добавить метку**.</span><span class="sxs-lookup"><span data-stu-id="cba02-150">Right-click the gauge panel and click **Add Label**.</span></span> <span data-ttu-id="cba02-151">Метка добавится на панель датчиков.</span><span class="sxs-lookup"><span data-stu-id="cba02-151">A label is added to the gauge panel.</span></span> <span data-ttu-id="cba02-152">Повторите это действие еще раз.</span><span class="sxs-lookup"><span data-stu-id="cba02-152">Repeat one more time.</span></span>  
  
     <span data-ttu-id="cba02-153">На панели датчиков появятся две метки.</span><span class="sxs-lookup"><span data-stu-id="cba02-153">The gauge panel has two labels.</span></span>  
  
15. <span data-ttu-id="cba02-154">Перетащите каждую метку в местоположение рядом с датчиком или индикатором.</span><span class="sxs-lookup"><span data-stu-id="cba02-154">Drag each label to a location near the gauge or indicator.</span></span>  
  
16. <span data-ttu-id="cba02-155">Щелкните правой кнопкой метку рядом с датчиком, выберите пункт **Свойства метки**и введите требуемый текст в поле **Текст** .</span><span class="sxs-lookup"><span data-stu-id="cba02-155">Right-click the label near the gauge, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
17. <span data-ttu-id="cba02-156">Щелкните правой кнопкой метку рядом с индикатором, выберите пункт **Свойства метки**и введите требуемый текст в поле **Текст** .</span><span class="sxs-lookup"><span data-stu-id="cba02-156">Right-click the label near the indicator, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
18. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cba02-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="cba02-157">See Also</span></span>  
 [<span data-ttu-id="cba02-158">Индикаторы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="cba02-158">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
