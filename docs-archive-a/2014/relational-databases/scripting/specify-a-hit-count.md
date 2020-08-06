---
title: Настройка счетчика числа попаданий
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.breakpt.hitcount
helpviewer_keywords:
- Transact-SQL debugger, breakpoint hit count
ms.assetid: 24836939-94ed-4e57-aa85-5d6938d859e4
author: rothja
ms.author: jroth
ms.openlocfilehash: 34c75e990bce1ea5e64c0b45f7acbcaa52fc3c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666486"
---
# <a name="specify-a-hit-count"></a><span data-ttu-id="a4ef9-102">Настройка счетчика числа попаданий</span><span class="sxs-lookup"><span data-stu-id="a4ef9-102">Specify a Hit Count</span></span>
  <span data-ttu-id="a4ef9-103">Счетчик числа попаданий точки останова увеличивается отладчиком [!INCLUDE[tsql](../../includes/tsql-md.md)] каждый раз при достижении точки останова.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-103">A breakpoint hit count is a counter that is incremented by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger each time the breakpoint is reached.</span></span> <span data-ttu-id="a4ef9-104">Если достигнуто указанное число попаданий или удовлетворяется любое из указанных условий для точки останова, то отладчик выполняет действие, заданное для точки останова.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-104">If the specified hit count is reached and any specified breakpoint condition is satisfied, the debugger performs the action specified for the breakpoint.</span></span>  
  
## <a name="hit-count-considerations"></a><span data-ttu-id="a4ef9-105">Соображения в отношении счетчика числа попаданий</span><span class="sxs-lookup"><span data-stu-id="a4ef9-105">Hit Count Considerations</span></span>  
 <span data-ttu-id="a4ef9-106">По умолчанию выполнение прерывается каждый раз, когда достигается точка останова.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-106">By default, execution breaks every time a breakpoint is hit.</span></span> <span data-ttu-id="a4ef9-107">Можно выбрать один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="a4ef9-107">You can choose between the following options:</span></span>  
  
-   <span data-ttu-id="a4ef9-108">Останавливать всегда (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a4ef9-108">Break always (the default).</span></span>  
  
-   <span data-ttu-id="a4ef9-109">Останавливать, если счетчик равен определенному значению.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-109">Break when the hit count equals a specified value.</span></span>  
  
-   <span data-ttu-id="a4ef9-110">Останавливать, если счетчик равен кратному числу заданного значения.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-110">Break when the hit count equals a multiple of a specified value.</span></span>  
  
-   <span data-ttu-id="a4ef9-111">Останавливать, если счетчик превышает заданное значение или равен ему.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-111">Break when the hit count is greater than or equal to a specified value.</span></span>  
  
 <span data-ttu-id="a4ef9-112">Счетчики числа попаданий точек останова увеличиваются в рамках сеанса отладки.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-112">Breakpoint hit counts are incremented within the scope of a debugging session.</span></span> <span data-ttu-id="a4ef9-113">Все счетчики числа попаданий обнуляются в начале каждого сеанса отладки.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-113">All hit counts are set to zero at the start of each debugging session.</span></span>  
  
 <span data-ttu-id="a4ef9-114">Если необходимо отслеживать, сколько раз достигается точка останова, без выполнения остановки, задайте очень большое значение счетчика числа попаданий, чтобы точка останова никогда не была достигнута.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-114">If you want to track how many times a breakpoint is hit without having the breakpoint break execution, specify a hit count with a very high value so the breakpoint never breaks.</span></span>  
  
 <span data-ttu-id="a4ef9-115">Действие для точки останова по умолчанию — прекращение выполнения, если достигнуто число попаданий и удовлетворяется условие для точки останова.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-115">The default action for a breakpoint is to break execution when both the hit count and breakpoint condition have been satisfied.</span></span> <span data-ttu-id="a4ef9-116">Сведения об указании других действий см. в разделе [Задание действия в точке останова](specify-a-breakpoint-action.md).</span><span class="sxs-lookup"><span data-stu-id="a4ef9-116">For information about specifying other actions, see [Specify a Breakpoint Action](specify-a-breakpoint-action.md).</span></span>  
  
#### <a name="to-specify-a-hit-count"></a><span data-ttu-id="a4ef9-117">Настройка счетчика числа попаданий</span><span class="sxs-lookup"><span data-stu-id="a4ef9-117">To Specify a Hit Count</span></span>  
  
1.  <span data-ttu-id="a4ef9-118">В окне редактора щелкните глиф точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Число попаданий** .</span><span class="sxs-lookup"><span data-stu-id="a4ef9-118">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="a4ef9-119">-или-</span><span class="sxs-lookup"><span data-stu-id="a4ef9-119">-or-</span></span>  
  
     <span data-ttu-id="a4ef9-120">В окне **Точки останова** щелкните глиф точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Число попаданий** .</span><span class="sxs-lookup"><span data-stu-id="a4ef9-120">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="a4ef9-121">В диалоговом окне **Счетчик числа попаданий точки останова** выберите нужное поведение в поле **При попадании в точку останова** .</span><span class="sxs-lookup"><span data-stu-id="a4ef9-121">In the **Breakpoint Hit Count** dialog box, select the behavior you want from the **When the breakpoint is hit** box.</span></span>  
  
     <span data-ttu-id="a4ef9-122">При выборе параметров, отличных от **Останавливать всегда**, с правой стороны от списка появится текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-122">If you choose any setting other than **Break Always**, a text box appears to the right of the list.</span></span> <span data-ttu-id="a4ef9-123">Введите целое число в текстовое поле, чтобы задать нужное количество попаданий.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-123">Enter an integer in the text box to specify the hit count you want.</span></span>  
  
3.  <span data-ttu-id="a4ef9-124">Нажмите кнопку **ОК** , чтобы внести изменения, либо кнопку **Отмена** , чтобы выйти без их применения.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-124">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
#### <a name="to-view-or-reset-the-current-hit-count"></a><span data-ttu-id="a4ef9-125">Просмотр или сброс текущего счетчика числа попаданий</span><span class="sxs-lookup"><span data-stu-id="a4ef9-125">To View or Reset the Current Hit Count</span></span>  
  
1.  <span data-ttu-id="a4ef9-126">В окне редактора щелкните глиф точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Число попаданий** .</span><span class="sxs-lookup"><span data-stu-id="a4ef9-126">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="a4ef9-127">-или-</span><span class="sxs-lookup"><span data-stu-id="a4ef9-127">-or-</span></span>  
  
     <span data-ttu-id="a4ef9-128">В окне **Точки останова** щелкните глиф точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Число попаданий** .</span><span class="sxs-lookup"><span data-stu-id="a4ef9-128">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="a4ef9-129">В диалоговом окне **Счетчик точек останова** пункт **Текущее число попаданий** отображается сразу над кнопкой **Сброс** .</span><span class="sxs-lookup"><span data-stu-id="a4ef9-129">In the **Breakpoint Hit Count** dialog box, the **Current hit count:** is displayed just above the **Reset** button.</span></span>  
  
3.  <span data-ttu-id="a4ef9-130">Нажмите кнопку **Сброс** , если нужно обнулить текущий счетчик числа попаданий.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-130">Click **Reset** if you want to set the current hit count to zero.</span></span>  
  
4.  <span data-ttu-id="a4ef9-131">Нажмите кнопку **ОК** или **Отмена** для выхода из диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="a4ef9-131">Click **OK** or **Cancel** to exit the dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ef9-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4ef9-132">See Also</span></span>  
 [<span data-ttu-id="a4ef9-133">Задание условия точки останова</span><span class="sxs-lookup"><span data-stu-id="a4ef9-133">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)  
  
  
