---
title: Контейнер "Цикл по элементам" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.forloopcontainerdetails.f1
helpviewer_keywords:
- repeating control flow
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: 44cf7355-992b-4bbf-a28c-bfb012de06f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a6c864779237fdbf4dd249f87b7c06655293c047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654459"
---
# <a name="for-loop-container"></a><span data-ttu-id="ede5f-102">Контейнер «цикл по элементам»</span><span class="sxs-lookup"><span data-stu-id="ede5f-102">For Loop Container</span></span>
  <span data-ttu-id="ede5f-103">Контейнер «цикл по элементам» определяет повторяющийся поток управления в пакете.</span><span class="sxs-lookup"><span data-stu-id="ede5f-103">The For Loop container defines a repeating control flow in a package.</span></span> <span data-ttu-id="ede5f-104">Управление циклом аналогично структуре цикла **For** в языках программирования.</span><span class="sxs-lookup"><span data-stu-id="ede5f-104">The loop implementation is similar to the **For** looping structure in programming languages.</span></span> <span data-ttu-id="ede5f-105">В ходе каждого повтора цикла контейнер «цикл по элементам» вычисляет выражение и повторяет рабочий процесс до тех пор, пока результатом выражения не станет `False`.</span><span class="sxs-lookup"><span data-stu-id="ede5f-105">In each repeat of the loop, the For Loop container evaluates an expression and repeats its workflow until the expression evaluates to `False`.</span></span>  
  
 <span data-ttu-id="ede5f-106">Контейнер "цикл по элементам" использует следующие элементы для определения цикла:</span><span class="sxs-lookup"><span data-stu-id="ede5f-106">The For Loop container usesthe following elements to define the loop:</span></span>  
  
-   <span data-ttu-id="ede5f-107">дополнительное выражение инициализации, в котором присваиваются значения счетчикам цикла;</span><span class="sxs-lookup"><span data-stu-id="ede5f-107">An optional initialization expression that assigns values to the loop counters.</span></span>  
  
-   <span data-ttu-id="ede5f-108">выражение вычисления, содержащее выражение, которое используется для проверки необходимости продолжения или остановки цикла;</span><span class="sxs-lookup"><span data-stu-id="ede5f-108">An evaluation expression that contains the expression used to test whether the loop should stop or continue.</span></span>  
  
-   <span data-ttu-id="ede5f-109">дополнительное выражение итерации, которое увеличивает или уменьшает счетчик цикла.</span><span class="sxs-lookup"><span data-stu-id="ede5f-109">An optional iteration expression that increments or decrements the loop counter.</span></span>  
  
 <span data-ttu-id="ede5f-110">На следующей диаграмме показан контейнер «цикл по элементам» с задачей «Отправка почты».</span><span class="sxs-lookup"><span data-stu-id="ede5f-110">The following diagram shows a For Loop container with a Send Mail task.</span></span> <span data-ttu-id="ede5f-111">Если выражение инициализации равно `@Counter = 0`, выражение вычисления равно `@Counter < 4`, а выражение итерации равно `@Counter = @Counter + 1`, то цикл повторяется четыре раза, после чего отправляет четыре электронных сообщения.</span><span class="sxs-lookup"><span data-stu-id="ede5f-111">If the initialization expression is `@Counter = 0`, the evaluation expression is `@Counter < 4`, and the iteration expression is `@Counter = @Counter + 1`, the loop repeats four times and sends four e-mail messages.</span></span>  
  
 <span data-ttu-id="ede5f-112">![Контейнер цикла For, повторяющий задачу четыре раза](../media/ssis-forloop.gif "Контейнер цикла For, повторяющий задачу четыре раза")</span><span class="sxs-lookup"><span data-stu-id="ede5f-112">![A For Loop container repeats a task four times](../media/ssis-forloop.gif "A For Loop container repeats a task four times")</span></span>  
  
 <span data-ttu-id="ede5f-113">Выражения должны являться допустимыми выражениями служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ede5f-113">The expressions must be valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions.</span></span>  
  
 <span data-ttu-id="ede5f-114">Для создания выражений инициализации и присваивания можно использовать оператор присваивания (=).</span><span class="sxs-lookup"><span data-stu-id="ede5f-114">To create the initialization and assignment expressions, you can use the assignment operator (=).</span></span> <span data-ttu-id="ede5f-115">Этот оператор не поддерживается грамматикой выражений служб Integration Services и может быть использован в контейнере «цикл по элементам» только в выражениях инициализации и присваивания.</span><span class="sxs-lookup"><span data-stu-id="ede5f-115">This operator is not otherwise supported by the Integration Services expression grammar and can only be used by the initialization and assignment expression types in the For Loop container.</span></span> <span data-ttu-id="ede5f-116">Любое выражение, использующее оператор присваивания, должно содержать выражение синтаксиса `@Var = <expression>`, где **Var** является переменной выполнения, а \<expression> — это выражение, соответствующее правилам синтаксиса выражения [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ede5f-116">Any expression that uses the assignment operator must have the syntax `@Var = <expression>`, where **Var** is a run-time variable and \<expression> is an expression that follows the rules of the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="ede5f-117">Выражение может содержать переменные, литералы и другие операторы и функции, которые поддерживаются грамматикой выражений служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="ede5f-117">The expression can include the variables, literals, and any operators and functions that the SSIS expression grammar supports.</span></span> <span data-ttu-id="ede5f-118">Выражение должно возвращать тип данных, который может быть приведен к типу данных переменной.</span><span class="sxs-lookup"><span data-stu-id="ede5f-118">The expression must evaluate to a data type that can be cast to the data type of the variable.</span></span>  
  
 <span data-ttu-id="ede5f-119">Контейнер «цикл по элементам» может содержать только одно выражение вычисления.</span><span class="sxs-lookup"><span data-stu-id="ede5f-119">A For Loop container can have only one evaluation expression.</span></span> <span data-ttu-id="ede5f-120">Это означает, что контейнер «цикл по элементам» выполняет все элементы потока управления одинаковое количество раз.</span><span class="sxs-lookup"><span data-stu-id="ede5f-120">This means that the For Loop container runs all its control flow elements the same number of times.</span></span> <span data-ttu-id="ede5f-121">Ввиду того, что контейнер «цикл по элементам» может включать другие контейнеры «цикл по элементам», в пакетах можно создавать вложенные циклы и сложные циклы выполнения.</span><span class="sxs-lookup"><span data-stu-id="ede5f-121">Because the For Loop container can include other For Loop containers, you can build nested loops and implement complex looping in packages.</span></span>  
  
 <span data-ttu-id="ede5f-122">Можно устанавливать свойство транзакции для контейнера «цикл по элементам», чтобы определить транзакцию для вложенного набора пакета потока управления.</span><span class="sxs-lookup"><span data-stu-id="ede5f-122">You can set a transaction property on the For Loop container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="ede5f-123">Таким образом, возможно выполнение транзакции на более детальном уровне.</span><span class="sxs-lookup"><span data-stu-id="ede5f-123">In this way, you can manage transactions at a more granular level.</span></span> <span data-ttu-id="ede5f-124">Например, если контейнер «цикл по элементам» несколько раз повторяет выполнение потока управления для обновления данных, можно настроить «цикл по элементам» и его поток управления с использованием транзакции, чтобы в случае неполного обновления данных обновление вообще не было произведено.</span><span class="sxs-lookup"><span data-stu-id="ede5f-124">For example, if a For Loop container repeats a control flow that updates data in a table multiple times, you can configure the For Loop and its control flow to use a transaction to ensure that if not all data is updated successfully, no data is updated.</span></span> <span data-ttu-id="ede5f-125">Дополнительные сведения см. в разделе [Транзакции служб Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="ede5f-125">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-for-loop-container"></a><span data-ttu-id="ede5f-126">Настройка контейнера «цикл по элементам»</span><span class="sxs-lookup"><span data-stu-id="ede5f-126">Configuration of the For Loop Container</span></span>  
 <span data-ttu-id="ede5f-127">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="ede5f-127">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ede5f-128">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ede5f-128">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ede5f-129">Редактор циклов по элементам</span><span class="sxs-lookup"><span data-stu-id="ede5f-129">For Loop Editor</span></span>](../for-loop-editor.md)  
  
-   [<span data-ttu-id="ede5f-130">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="ede5f-130">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="ede5f-131">Дополнительные сведения о задании этих свойств программными средствами см. в документации по классу **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** в руководстве для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="ede5f-131">For more information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ede5f-132">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="ede5f-132">Related Tasks</span></span>  
 <span data-ttu-id="ede5f-133">Сведения о настройке контейнера «цикл по элементам» см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ede5f-133">For information about how to configure a For Loop Container, see the following topics.</span></span>  
  
-   [<span data-ttu-id="ede5f-134">Настройка контейнера «цикл по элементам»</span><span class="sxs-lookup"><span data-stu-id="ede5f-134">Configure a For Loop Container</span></span>](for-loop-container.md)  
  
-   [<span data-ttu-id="ede5f-135">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="ede5f-135">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="ede5f-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="ede5f-136">See Also</span></span>  
 <span data-ttu-id="ede5f-137">[Поток управления](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="ede5f-137">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="ede5f-138">Выражения служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="ede5f-138">Integration Services &#40;SSIS&#41; Expressions</span></span>](../expressions/integration-services-ssis-expressions.md)  
  
  
