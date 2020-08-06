---
title: Создание именованных наборов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculations [Analysis Services], named sets
- named sets [Analysis Services]
- members [Analysis Services], named sets
ms.assetid: 03cf97a4-1a18-45f3-acb0-35123bd619be
author: minewiskan
ms.author: owend
ms.openlocfilehash: e92984102ceb8ad0ac049c15870e9f1efd6090fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728894"
---
# <a name="create-named-sets"></a><span data-ttu-id="0e1d4-102">Создание именованных наборов</span><span class="sxs-lookup"><span data-stu-id="0e1d4-102">Create Named Sets</span></span>
  <span data-ttu-id="0e1d4-103">Именованный набор — это набор элементов измерения или выражение набора, которые создаются для многократного использования, например в запросах на языке многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-103">A named set is a set of dimension members or a set expression that is created for reuse, for example in Multidimensional Expressions (MDX) queries.</span></span> <span data-ttu-id="0e1d4-104">Для создания именованных наборов может использоваться сочетание данных куба, арифметических операторов, чисел и функций.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-104">You can create named sets by combining cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="0e1d4-105">Например, можно создать именованный набор с именем Top Ten Factories, содержащий десять элементов измерения Factories с наибольшими значениями показателя Production.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-105">For example, you can create a named set called Top Ten Factories that contains the ten members of the Factories dimension that have the highest values for the Production measure.</span></span> <span data-ttu-id="0e1d4-106">Затем набор Top Ten Factories можно использовать в запросах конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-106">Top Ten Factories can then be used in queries by end users.</span></span> <span data-ttu-id="0e1d4-107">Например, конечный пользователь помещает набор Top Ten Factories на одну ось, а измерение меры, включая Production, — на другую ось.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-107">For example, an end user can place Top Ten Factories on one axis and the Measures dimension, including Production, on another axis.</span></span> <span data-ttu-id="0e1d4-108">Дополнительные сведения см. в разделах [Вычисления в многомерных моделях](calculations-in-multidimensional-models.md) и [Построение именованных наборов в многомерных выражениях](mdx/mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0e1d4-108">For more information, see [Calculations in Multidimensional Models](calculations-in-multidimensional-models.md), and [Building Named Sets in MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="0e1d4-109">Чтобы создать именованный набор, можно воспользоваться командой **Создать именованный набор** на вкладке **Вычисления** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-109">To create a named set, use the **New Named Set** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="0e1d4-110">Эта команда может быть вызвана из меню **Куб** на панели инструментов вкладки **Вычисления** .</span><span class="sxs-lookup"><span data-stu-id="0e1d4-110">This command can be invoked on the **Cube** menu on the **Calculations** tab toolbar.</span></span> <span data-ttu-id="0e1d4-111">Эта команда отображает форму для задания следующих параметров именованного набора.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-111">This command displays a form to specify the following options for the named set:</span></span>  
  
 <span data-ttu-id="0e1d4-112">**имя**;</span><span class="sxs-lookup"><span data-stu-id="0e1d4-112">**Name**</span></span>  
 <span data-ttu-id="0e1d4-113">Выберите имя именованного набора.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-113">Select the name of the named set.</span></span> <span data-ttu-id="0e1d4-114">Это имя отображается при просмотре куба конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-114">This name appears to end users when they browse the cube.</span></span>  
  
 <span data-ttu-id="0e1d4-115">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="0e1d4-115">**Expression**</span></span>  
 <span data-ttu-id="0e1d4-116">Укажите выражение, из которого получается именованный набор.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-116">Specify the expression that produces the named set.</span></span> <span data-ttu-id="0e1d4-117">Это выражение может быть записано на языке многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-117">This expression can be written in MDX.</span></span> <span data-ttu-id="0e1d4-118">Выражение может содержать любой из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="0e1d4-118">The expression can contain any of the following:</span></span>  
  
-   <span data-ttu-id="0e1d4-119">выражения данных, которые представляют компоненты куба, такие как измерения, уровни, меры и т. д.;</span><span class="sxs-lookup"><span data-stu-id="0e1d4-119">Data expressions that represent cube components such as dimensions, levels, measures, and so on.</span></span>  
  
-   <span data-ttu-id="0e1d4-120">арифметические операторы;</span><span class="sxs-lookup"><span data-stu-id="0e1d4-120">Arithmetic operators.</span></span>  
  
-   <span data-ttu-id="0e1d4-121">числа.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-121">Numbers.</span></span>  
  
-   <span data-ttu-id="0e1d4-122">функции.</span><span class="sxs-lookup"><span data-stu-id="0e1d4-122">Functions.</span></span>  
  
 <span data-ttu-id="0e1d4-123">Можно скопировать или перетащить компоненты куба с вкладки **Метаданные** панели **Средства вычисления** в поле **Выражение** панели **Редактор форм именованных наборов** .</span><span class="sxs-lookup"><span data-stu-id="0e1d4-123">You can copy or drag cube components from the **Metadata** tab of the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span> <span data-ttu-id="0e1d4-124">Можно скопировать или перетащить функции с вкладки **Функции** панели **Средства вычисления** в поле **Выражение** панели **Редактор форм именованных наборов** .</span><span class="sxs-lookup"><span data-stu-id="0e1d4-124">You can copy or drag functions from the **Functions** tab in the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0e1d4-125">Если выражение набора создается путем явного именования элементов в наборе, заключите список элементов в пару фигурных скобок ( {} ).</span><span class="sxs-lookup"><span data-stu-id="0e1d4-125">If you create the set expression by explicitly naming the members in the set, enclose the list of members in a pair of braces ({}).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1d4-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e1d4-126">See Also</span></span>  
 [<span data-ttu-id="0e1d4-127">Вычисления в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="0e1d4-127">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)  
  
  
