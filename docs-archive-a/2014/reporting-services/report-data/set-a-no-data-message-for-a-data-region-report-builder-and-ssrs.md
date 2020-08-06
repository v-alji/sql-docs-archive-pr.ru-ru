---
title: Установка сообщения об отсутствии данных для области данных (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b194714-46f7-4f0e-9632-7f89d9600762
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9ed38ef14eb8f89753b4b3d7af3324ef0e88fa52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730189"
---
# <a name="set-a-no-data-message-for-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="57602-102">Установка сообщения об отсутствии данных для области данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="57602-102">Set a No Data Message for a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="57602-103">Чтобы задать текст, который будет отображаться в подготовленном к просмотру отчете в области данных, внутри которой данных нет, задайте свойство NoRowsMessage для таблицы, матрицы или области списка данных или свойство NoDataMessage для диаграммной области данных и NoDataText для цветовой шкалы для схемы.</span><span class="sxs-lookup"><span data-stu-id="57602-103">When you want to specify text to show in the rendered report in place of a data region that has no data, set the NoRowsMessage property for a table, matrix, or list data region, the NoDataMessage for a chart data region, and the NoDataText for the color scale for a map.</span></span> <span data-ttu-id="57602-104">Во время выполнения обработчик запросов производит запрос к каждому из наборов данных в отчете; такие запросы могут не вернуть результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="57602-104">At run time, the report processor runs the query for each dataset in a report and the dataset query may produce no result set.</span></span> <span data-ttu-id="57602-105">Если область данных привязана к пустому набору данных, то можно указать текст, который будет отображаться вместо пустой области данных.</span><span class="sxs-lookup"><span data-stu-id="57602-105">For a data region bound to an empty dataset, you can specify text to display instead of displaying an empty data region.</span></span> <span data-ttu-id="57602-106">Также свойство NoRowsMessage можно задать для вложенных отчетов; сообщение будет отображаться, если во время выполнения во вложенном отчете не будет заполненных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="57602-106">You can also set the NoRowsMessage property for a subreport when no datasets in the subreport have data at run time.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-norowsmessage-property-for-a-table-matrix-or-list"></a><span data-ttu-id="57602-107">Задание свойства NoRowsMessage для таблицы, матрицы или списка</span><span class="sxs-lookup"><span data-stu-id="57602-107">To set the NoRowsMessage property for a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="57602-108">В конструкторе щелкните область данных таблицы, матрицы или списка или вложенный отчет в области конструктора, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="57602-108">In Design view, click the table, matrix, or list data region or subreport on the design surface to select it.</span></span> <span data-ttu-id="57602-109">В панели свойств отображаются свойства выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="57602-109">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="57602-110">В области Свойства введите текст, который будет отображаться как сообщение в `NoRowsMessage` поле свойства.</span><span class="sxs-lookup"><span data-stu-id="57602-110">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="57602-111">Также можно выбрать пункт **Выражение** в раскрывающемся списке, чтобы открыть диалоговое окно **Выражение** и создать выражение.</span><span class="sxs-lookup"><span data-stu-id="57602-111">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatamessage-property-for-a-chart"></a><span data-ttu-id="57602-112">Задание свойства NoDataMessage для диаграммы</span><span class="sxs-lookup"><span data-stu-id="57602-112">To set the NoDataMessage property for a chart</span></span>  
  
1.  <span data-ttu-id="57602-113">В конструкторе щелкните диаграмму в области конструктора, чтобы выбрать ее.</span><span class="sxs-lookup"><span data-stu-id="57602-113">In Design view, click the chart on the design surface to select it.</span></span> <span data-ttu-id="57602-114">В панели свойств отображаются свойства выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="57602-114">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="57602-115">На панели Свойства разверните узел для `NoDataMessage` .</span><span class="sxs-lookup"><span data-stu-id="57602-115">In the Properties pane, expand the node for `NoDataMessage`.</span></span>  
  
3.  <span data-ttu-id="57602-116">В поле **Caption (заголовок**) введите текст, который должен отображаться как сообщение в `NoDataMessage` свойстве.</span><span class="sxs-lookup"><span data-stu-id="57602-116">In **Caption**, type the text that you want to display as a message in `NoDataMessage` property field.</span></span>  
  
     <span data-ttu-id="57602-117">Также можно выбрать пункт **Выражение** в раскрывающемся списке, чтобы открыть диалоговое окно **Выражение** и создать выражение.</span><span class="sxs-lookup"><span data-stu-id="57602-117">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-norowsmessage-for-a-subreport"></a><span data-ttu-id="57602-118">Назначение свойства NoRowsMessage для вложенного отчета</span><span class="sxs-lookup"><span data-stu-id="57602-118">To set the NoRowsMessage for a subreport</span></span>  
  
1.  <span data-ttu-id="57602-119">В конструкторе щелкните вложенный отчет в области конструктора, чтобы выбрать его.</span><span class="sxs-lookup"><span data-stu-id="57602-119">In Design view, click the subreport on the design surface to select it.</span></span> <span data-ttu-id="57602-120">В панели свойств отображаются свойства выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="57602-120">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="57602-121">В области Свойства введите текст, который будет отображаться как сообщение в `NoRowsMessage` поле свойства.</span><span class="sxs-lookup"><span data-stu-id="57602-121">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="57602-122">Также можно выбрать пункт **Выражение** в раскрывающемся списке, чтобы открыть диалоговое окно **Выражение** и создать выражение.</span><span class="sxs-lookup"><span data-stu-id="57602-122">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatatext-property-for-a-color-scale-for-a-map"></a><span data-ttu-id="57602-123">Назначение свойства NoDataText для цветовой шкалы для карты</span><span class="sxs-lookup"><span data-stu-id="57602-123">To set the NoDataText property for a color scale for a map</span></span>  
  
1.  <span data-ttu-id="57602-124">В конструкторе щелкните цветовую шкалу на карте, чтобы выбрать ее.</span><span class="sxs-lookup"><span data-stu-id="57602-124">In Design view, click the color scale on the map to select it.</span></span> <span data-ttu-id="57602-125">В панели свойств отображаются свойства выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="57602-125">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="57602-126">В области свойства в `NoDataText` введите текст, который должен отображаться как метка для цветов без значения данных.</span><span class="sxs-lookup"><span data-stu-id="57602-126">In the Properties pane, in `NoDataText`, type the text that you want to display as a label for colors with no data value.</span></span>  
  
     <span data-ttu-id="57602-127">Также можно выбрать пункт **Выражение** в раскрывающемся списке, чтобы открыть диалоговое окно **Выражение** и создать выражение.</span><span class="sxs-lookup"><span data-stu-id="57602-127">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57602-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="57602-128">See Also</span></span>  
 <span data-ttu-id="57602-129">[Вложенные отчеты (построитель отчетов и службы SSRS)](../report-design/subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="57602-129">[Subreports &#40;Report Builder and SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="57602-130">[Таблицы, матрицы и списки (построитель отчетов и службы SSRS)](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="57602-130">[Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="57602-131">[Диаграммы (построитель отчетов и службы SSRS)](../report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="57602-131">[Charts &#40;Report Builder and SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="57602-132">[Карты (построитель отчетов и службы SSRS)](../report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="57602-132">[Maps &#40;Report Builder and SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="57602-133">Вложенные отчеты (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="57602-133">Subreports &#40;Report Builder and SSRS&#41;</span></span>](../report-design/subreports-report-builder-and-ssrs.md)  
  
  
