---
title: Задание цветов диаграммы с помощью палитры (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d95efc22-5a32-43d4-9bd2-12753e7fd395
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7db137ed87b0c84e43577dcf2936a6287abd8e36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663961"
---
# <a name="define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs"></a><span data-ttu-id="3b5e1-102">Задание цветов диаграммы с помощью палитры (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3b5e1-102">Define Colors on a Chart Using a Palette (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3b5e1-103">Цветовую палитру диаграммы можно изменить, выбрав существующую палитру или определив свою.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-103">You can change the color palette for a chart by selecting a pre-defined palette or defining a custom palette.</span></span> <span data-ttu-id="3b5e1-104">Пользовательские палитры зависят для конкретного отчета.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-104">Custom palettes are report-specific.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-colors-on-the-chart-using-a-built-in-color-palette"></a><span data-ttu-id="3b5e1-105">Изменение цветов диаграммы с помощью встроенной цветовой палитры</span><span class="sxs-lookup"><span data-stu-id="3b5e1-105">To change the colors on the chart using a built-in color palette</span></span>  
  
1.  <span data-ttu-id="3b5e1-106">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="3b5e1-106">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="3b5e1-107">Щелкните диаграмму в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-107">On the design surface, click the chart.</span></span> <span data-ttu-id="3b5e1-108">На панели «Свойства» отображаются свойства объекта диаграммы.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-108">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
     <span data-ttu-id="3b5e1-109">В раскрывающемся списке в верхней части панели свойств появляется имя объекта (по умолчанию —**Диаграмма1** ).</span><span class="sxs-lookup"><span data-stu-id="3b5e1-109">The object name (**Chart1** by default) appears in the drop-down list at the top of the Properties pane.</span></span>  
  
3.  <span data-ttu-id="3b5e1-110">На вкладке **Диаграмма** в свойстве Palette выберите из раскрывающегося списка новую палитру.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-110">In the **Chart** section, for the Palette property, select a new palette from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3b5e1-111">Изменить цвета или их порядок во встроенной палитре нельзя.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-111">You cannot change the colors or order in a pre-defined palette.</span></span>  
  
### <a name="to-define-your-own-colors-on-the-chart-using-a-custom-color-palette"></a><span data-ttu-id="3b5e1-112">Определение пользовательских цветов диаграммы с помощью пользовательской цветовой палитры</span><span class="sxs-lookup"><span data-stu-id="3b5e1-112">To define your own colors on the chart using a custom color palette</span></span>  
  
1.  <span data-ttu-id="3b5e1-113">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="3b5e1-113">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="3b5e1-114">Щелкните диаграмму в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-114">On the design surface, click the chart.</span></span> <span data-ttu-id="3b5e1-115">На панели «Свойства» отображаются свойства объекта диаграммы.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-115">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="3b5e1-116">В разделе **Диаграмма** для `Palette` Свойства выберите **Пользовательская**.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-116">In the **Chart** section, for the `Palette` property, select **Custom**.</span></span>  
  
4.  <span data-ttu-id="3b5e1-117">В области свойства CustomPaletteColors нажмите кнопку изменения коллекции ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="3b5e1-117">In the CustomPaletteColors property, click the Edit Collection (**...**) button.</span></span> <span data-ttu-id="3b5e1-118">Будет открыто окно **Редактор коллекции ReportColorExpression** .</span><span class="sxs-lookup"><span data-stu-id="3b5e1-118">The **ReportColorExpression Collection Editor** opens.</span></span>  
  
5.  <span data-ttu-id="3b5e1-119">Чтобы добавить цвет, нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="3b5e1-119">Click **Add** to add a color.</span></span> <span data-ttu-id="3b5e1-120">Выберите цвет из раскрывающегося списка или выберите выражение и укажите шестнадцатеричное значение конкретного цвета — например, ff6600 для оранжевого цвета.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-120">Select a color from the drop-down list or select Expression and specify a hex value for a specific color, such as ff6600 for "Orange".</span></span>  
  
     <span data-ttu-id="3b5e1-121">Дополнительные сведения о шестнадцатеричных значениях см. в разделе [Таблица цветов](https://go.microsoft.com/fwlink/?linkid=9258) в MSDN.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-121">For more information about hex values, see [Color Table](https://go.microsoft.com/fwlink/?linkid=9258) on MSDN.</span></span>  
  
6.  <span data-ttu-id="3b5e1-122">Нажмите кнопку **Добавить** , чтобы добавить в палитру еще один цвет.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-122">Click **Add** to add more colors to the palette.</span></span>  
  
7.  <span data-ttu-id="3b5e1-123">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-123">When you are done, click **OK**.</span></span>  
  
 <span data-ttu-id="3b5e1-124">В пользовательской палитре можно менять порядок цветов, чтобы изменить цвета разных рядов диаграммы.</span><span class="sxs-lookup"><span data-stu-id="3b5e1-124">If you are using a custom palette, you can change the order of the colors to change the color of different series in the chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b5e1-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b5e1-125">See Also</span></span>  
 <span data-ttu-id="3b5e1-126">[Форматирование цветов для рядов на диаграмме (построитель отчетов и службы SSRS)](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b5e1-126">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3b5e1-127">[Диаграммы (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b5e1-127">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3b5e1-128">Указание согласованных цветов для нескольких фигурных диаграмм (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3b5e1-128">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
