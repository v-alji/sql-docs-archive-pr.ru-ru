---
title: Указание размера индикатора с помощью выражения (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab0b86f1-4882-4258-a2b6-c612faecfa4b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b450abb957329b8dbaa4f7f0e4c963c5f63f06b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654776"
---
# <a name="specify-the-size-of-an-indicator-using-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="a2be7-102">Указание размера индикатора с помощью выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a2be7-102">Specify the Size of an Indicator Using an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a2be7-103">Помимо цвета, направления и формы, для изменения визуального представления индикатора можно использовать его размер.</span><span class="sxs-lookup"><span data-stu-id="a2be7-103">In addition to color, direction, and shape, you can use size to maximize the visual impact of indicators.</span></span>  
  
 <span data-ttu-id="a2be7-104">У индикатора есть коллекция состояний индикатора IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="a2be7-104">An indicator has a collection of indicator states named IndicatorStates.</span></span> <span data-ttu-id="a2be7-105">Коллекция IndicatorStates обычно имеет несколько состояний.</span><span class="sxs-lookup"><span data-stu-id="a2be7-105">The IndicatorStates collection typically have multiple states.</span></span> <span data-ttu-id="a2be7-106">Каждое состояние является частью коллекции и представляется значком.</span><span class="sxs-lookup"><span data-stu-id="a2be7-106">Each state is a member of the collection and is represented by an icon.</span></span> <span data-ttu-id="a2be7-107">Вместе состояния представляют собой коллекцию IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="a2be7-107">Together the states constitute the IndicatorsStates collection.</span></span>  
  
 <span data-ttu-id="a2be7-108">Для динамической настройки размера значков надо задать свойства элементов коллекции IndicatorStates на панели "Свойства" в построителе отчетов.</span><span class="sxs-lookup"><span data-stu-id="a2be7-108">To dynamically configure the sizes of icons, you set properties of members of the IndicatorsStates collection in the Properties pane of Report Builder.</span></span> <span data-ttu-id="a2be7-109">Если панель **Свойства** не отображается, перейдите на вкладку **Вид** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a2be7-109">If the **Properties** pane is not visible, click the **View** tab and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2be7-110">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]окно **Свойства** используется для установки свойств элемента.</span><span class="sxs-lookup"><span data-stu-id="a2be7-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you use the **Properties** window to set the member properties.</span></span> <span data-ttu-id="a2be7-111">Если окно **Свойства** не открыто, нажмите клавишу F4.</span><span class="sxs-lookup"><span data-stu-id="a2be7-111">If the **Properties** window is not open, press the F4 key.</span></span>  
  
 <span data-ttu-id="a2be7-112">Панель **Свойства** предоставляет доступ к свойствам коллекции IndicatorStates индикатора.</span><span class="sxs-lookup"><span data-stu-id="a2be7-112">The **Properties** pane provides access to the properties of the IndicatorStates collection of an indicator.</span></span> <span data-ttu-id="a2be7-113">Разные размеры значков задаются установкой свойства ScaleFactor коллекции IndicatorStates с помощью выражения.</span><span class="sxs-lookup"><span data-stu-id="a2be7-113">You configure the icons to be different sizes by setting the ScaleFactor property of the IndicatorStates collection members using an expression.</span></span> <span data-ttu-id="a2be7-114">Дополнительные сведения см. в разделе [Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a2be7-114">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="a2be7-115">Выражение, используемое для этой процедуры, также применяется для создания отчетов с разными размерами индикаторов, как показано в разделе [Индикаторы (построитель отчетов и службы SSRS)](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a2be7-115">The expression used in this procedure was also used to generate the report with different sizes of indicators, shown in [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-the-indicator-icon-size-using-an-expression"></a><span data-ttu-id="a2be7-116">Указание размера значка индикатора с помощью выражения</span><span class="sxs-lookup"><span data-stu-id="a2be7-116">To specify the indicator icon size using an expression</span></span>  
  
1.  <span data-ttu-id="a2be7-117">Щелкните индикатор, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="a2be7-117">Click the indicator you want to change.</span></span>  
  
2.  <span data-ttu-id="a2be7-118">На панели "Свойства" найдите свойство IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="a2be7-118">In the Properties pane, locate the IndicatorStates property.</span></span>  
  
     <span data-ttu-id="a2be7-119">Если панель "Свойства" организована по категориям, свойство IndicatorStates будет находиться в категории **Состояния** .</span><span class="sxs-lookup"><span data-stu-id="a2be7-119">If the Properties pane is organized by category, you will find IndicatorStates in the **States** category.</span></span>  
  
3.  <span data-ttu-id="a2be7-120">Нажмите кнопку с многоточием **(...)** рядом со свойством IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="a2be7-120">Click the ellipsis **(...)** button next to IndicatorStates.</span></span> <span data-ttu-id="a2be7-121">Откроется диалоговое окно **Редактор коллекции состояний индикатора** .</span><span class="sxs-lookup"><span data-stu-id="a2be7-121">The **IndicatorState Collection Editor** dialog box opens.</span></span>  
  
     <span data-ttu-id="a2be7-122">Выберите все элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="a2be7-122">Select all members of the collection.</span></span>  
  
4.  <span data-ttu-id="a2be7-123">В списке **Выбор нескольких свойств** щелкните стрелку вниз рядом со свойством ScaleFactor и выберите **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="a2be7-123">In the **Multi-Select Properties** list, click the down arrow next to ScaleFactor and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="a2be7-124">В диалоговом окне **Выражение** введите выражение.</span><span class="sxs-lookup"><span data-stu-id="a2be7-124">In the **Expression** dialog box write the expression.</span></span>  
  
     <span data-ttu-id="a2be7-125">В следующем образце выражения размер значка изменяется в зависимости от значения поля **Продажи за год на дату** .</span><span class="sxs-lookup"><span data-stu-id="a2be7-125">The following sample expression makes the icon a different size based on the value of the **SalesYTD** field.</span></span>  
  
     `=IIF(Fields!SalesYTD.value = 0,0,Fields!SalesYTD.value/Max(Fields!SalesYTD.value,"Indicator"))`  
  
     <span data-ttu-id="a2be7-126">Дополнительные сведения см. в разделе [Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a2be7-126">For more information, see [Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a2be7-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2be7-127">See Also</span></span>  
 [<span data-ttu-id="a2be7-128">Индикаторы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a2be7-128">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
