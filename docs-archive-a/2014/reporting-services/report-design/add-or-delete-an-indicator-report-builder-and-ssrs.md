---
title: Добавление или удаление индикатора (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8b1aac1-53ef-47a4-afc0-8fa866c6c480
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 186ed4f5b6cf7cb239dc7c33a11089c11bccae14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735042"
---
# <a name="add-or-delete-an-indicator-report-builder-and-ssrs"></a><span data-ttu-id="05f53-102">Добавление или удаление индикатора (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="05f53-102">Add or Delete an Indicator (Report Builder and SSRS)</span></span>
  <span data-ttu-id="05f53-103">Индикаторы — это минимальные датчики, обеспечивающие возможность быстрого определения состояния одиночного значения данных.</span><span class="sxs-lookup"><span data-stu-id="05f53-103">Indicators are minimal gauges that convey the state of a single data value at a glance.</span></span> <span data-ttu-id="05f53-104">Дополнительные сведения см. в разделе [Индикаторы (построитель отчетов и службы SSRS)](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05f53-104">For more information about them, see [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="05f53-105">Индикаторы обычно размещаются в ячейках таблицы или матрицы, но можно использовать сами индикаторы, параллельно с датчиками или внедренные в датчиках.</span><span class="sxs-lookup"><span data-stu-id="05f53-105">Indicators are commonly placed in cells in a table or matrix, but you can also use indicators by themselves, side-by-side with gauges, or embedded in gauges.</span></span>  
  
 <span data-ttu-id="05f53-106">При первом добавлении индикатора он по умолчанию настраивается для использования процентных единиц измерения.</span><span class="sxs-lookup"><span data-stu-id="05f53-106">When you first add an indicator, it is by default configured to use percentages as measurement units.</span></span> <span data-ttu-id="05f53-107">Процентные диапазоны равномерно распределяются между элементами набора индикаторов, а область значений, отображаемых индикатором, является для индикатора родительским элементом, таким как таблица или матрица.</span><span class="sxs-lookup"><span data-stu-id="05f53-107">The percentage ranges are evenly distributed across members of the indicator set, and the scope of values shown by the indicator is the parent of the indicator such as a table or matrix.</span></span>  
  
 <span data-ttu-id="05f53-108">Можно обновить значения и состояния индикаторов.</span><span class="sxs-lookup"><span data-stu-id="05f53-108">You can update the values and states of indicators.</span></span> <span data-ttu-id="05f53-109">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="05f53-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="05f53-110">Изменение значков индикаторов и наборов индикаторов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="05f53-110">Change Indicator Icons and Indicator Sets &#40;Report Builder and SSRS&#41;</span></span>](change-indicator-icons-and-indicator-sets-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="05f53-111">Задание и настройка единиц измерения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="05f53-111">Set and Configure Measurement Units &#40;Report Builder and SSRS&#41;</span></span>](set-and-configure-measurement-units-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="05f53-112">Задание области действия синхронизации (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="05f53-112">Set Synchronization Scope &#40;Report Builder and SSRS&#41;</span></span>](set-synchronization-scope-report-builder-and-ssrs.md)  
  
 <span data-ttu-id="05f53-113">Поскольку индикатор располагается внутри панели датчиков, необходимо выбрать вместо панели индикатор при необходимости настройки индикатора с помощью диалогового окна **Свойства индикатора** или панели **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="05f53-113">Because an indicator is positioned inside the gauge panel, you need to select the indicator instead of the panel when you want to configure the indicator by using the **Indicators Properties** dialog box or the **Properties** pane.</span></span> <span data-ttu-id="05f53-114">На следующем рисунке отображается выбранный индикатор на панели датчиков.</span><span class="sxs-lookup"><span data-stu-id="05f53-114">The following picture shows a selected indicator in its gauge panel.</span></span>  
  
 <span data-ttu-id="05f53-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span><span class="sxs-lookup"><span data-stu-id="05f53-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05f53-116">В зависимости от ширины столбца и длины значений данных, текст в ячейках таблицы или матрицы может переноситься по словам на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="05f53-116">Depending on column width and the length of data values, the text in table or matrix cells might wrap and display text on multiple lines.</span></span> <span data-ttu-id="05f53-117">В этом случае значок индикатора может растянуться и изменить форму.</span><span class="sxs-lookup"><span data-stu-id="05f53-117">When this occurs, the indicator icon might be stretched and change shape.</span></span> <span data-ttu-id="05f53-118">В результате значок индикатора воспринимается хуже.</span><span class="sxs-lookup"><span data-stu-id="05f53-118">This can make the indicator icon less readable.</span></span> <span data-ttu-id="05f53-119">Во избежание растяжений значка разместите индикатор внутри прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="05f53-119">Place the indicator inside a rectangle to ensure that the icon is never stretched.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="05f53-120">Добавление индикатора в таблицу или матрицу</span><span class="sxs-lookup"><span data-stu-id="05f53-120">To add an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="05f53-121">Откройте существующий отчет или создайте новый отчет, содержащий таблицу и матрицу с данными, которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="05f53-121">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="05f53-122">Дополнительные сведения см. в разделах [Таблицы (построитель отчетов и службы SSRS)](tables-report-builder-and-ssrs.md) и [Матрицы (построитель отчетов и службы SSRS)](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05f53-122">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="05f53-123">Вставьте столбец в таблицу или матрицу.</span><span class="sxs-lookup"><span data-stu-id="05f53-123">Insert a column in your table or matrix.</span></span> <span data-ttu-id="05f53-124">Дополнительные сведения см. в разделе [Вставка или удаление столбца (построитель отчетов и службы SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05f53-124">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="05f53-125">При необходимости на вкладке **Вставка** нажмите кнопку **Прямоугольник**, а затем щелкните ячейку в новом столбце.</span><span class="sxs-lookup"><span data-stu-id="05f53-125">Optionally, on the **Insert** tab, click **Rectangle**, and then click a cell in the new column.</span></span>  
  
4.  <span data-ttu-id="05f53-126">На вкладке **Вставка** нажмите кнопку **Индикатор**, а затем щелкните ячейку в новом столбце.</span><span class="sxs-lookup"><span data-stu-id="05f53-126">On the **Insert** tab, click **Indicator**, and then click a cell in the new column.</span></span>  
  
     <span data-ttu-id="05f53-127">Если в ячейку был добавлен прямоугольник, щелкните эту ячейку.</span><span class="sxs-lookup"><span data-stu-id="05f53-127">If you added a rectangle to a cell, click that cell.</span></span>  
  
5.  <span data-ttu-id="05f53-128">В диалоговом окне **Выбор стиля индикатора** в левой панели выберите тип нужного индикатора, а затем выберите набор индикаторов.</span><span class="sxs-lookup"><span data-stu-id="05f53-128">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
6.  <span data-ttu-id="05f53-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="05f53-129">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="05f53-130">Щелкните индикатор.</span><span class="sxs-lookup"><span data-stu-id="05f53-130">Click the indicator.</span></span> <span data-ttu-id="05f53-131">Откроется панель **Данные датчика** .</span><span class="sxs-lookup"><span data-stu-id="05f53-131">The **Gauge Data** pane opens.</span></span>  
  
8.  <span data-ttu-id="05f53-132">В области **Значения** в раскрывающемся списке **(Не указано)** выберите поле, значения которого необходимо отобразить в качестве индикатора.</span><span class="sxs-lookup"><span data-stu-id="05f53-132">In the **Values** area, in the **(Unspecified)** drop-down list, click the field whose values you want to display as an indicator.</span></span>  
  
     <span data-ttu-id="05f53-133">Индикатор настроен для использования значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05f53-133">The indicator is configured to use default values.</span></span> <span data-ttu-id="05f53-134">По умолчанию индикаторы настроены для использования в качестве единиц измерения процентных соотношений, диапазоны процентного соотношения равномерно распределяются между элементами индикатора, а для значений, указываемых индикатором, используется область ближайшей группы.</span><span class="sxs-lookup"><span data-stu-id="05f53-134">By default, indicators are configured use percentages as measurement units and the percentage ranges are evenly distributed across the members of the indicator and the value that the indicator conveys uses the scope of the nearest group.</span></span>  
  
### <a name="to-delete-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="05f53-135">Удаление индикатора из таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="05f53-135">To delete an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="05f53-136">Щелкните индикатор правой кнопкой мыши и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="05f53-136">Right-click the indicator to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="05f53-137">Индикатор должен быть расположен на панели датчиков, содержащей другие индикаторы или датчики.</span><span class="sxs-lookup"><span data-stu-id="05f53-137">An indicator might be positioned inside a gauge panel that contains other indicators or gauges.</span></span> <span data-ttu-id="05f53-138">Если панель датчиков содержит несколько элементов, убедитесь, что для их удаления выбран индикатор, а не панель датчиков.</span><span class="sxs-lookup"><span data-stu-id="05f53-138">If the gauge panels contain multiple items, be sure to click the indicator to delete it, not the gauge panel.</span></span> <span data-ttu-id="05f53-139">Если нажать и удалить панель датчиков, то будут удалены панели датчиков и все элементы в них.</span><span class="sxs-lookup"><span data-stu-id="05f53-139">If you click and then delete the gauge panel, the gauge panels and all the items in it are deleted.</span></span>  
  
2.  <span data-ttu-id="05f53-140">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="05f53-140">Click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05f53-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="05f53-141">See Also</span></span>  
 [<span data-ttu-id="05f53-142">Индикаторы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="05f53-142">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
