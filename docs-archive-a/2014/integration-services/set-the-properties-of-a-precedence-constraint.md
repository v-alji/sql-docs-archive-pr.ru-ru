---
title: Задание свойств элемента управления очередностью | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Precedence Constraint Editor dialog box
- precedence constraints [Integration Services], properties
ms.assetid: d990f600-5c09-4cd5-8528-0a58d79dc9f2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 55b95bdb79d801156bef6198bc0f57accb5d9517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667791"
---
# <a name="set-the-properties-of-a-precedence-constraint"></a><span data-ttu-id="7e26d-102">Установка свойств управления очередностью</span><span class="sxs-lookup"><span data-stu-id="7e26d-102">Set the Properties of a Precedence Constraint</span></span>
  <span data-ttu-id="7e26d-103">Для установки свойств элементов управления очередностью можно использовать следующие средства.</span><span class="sxs-lookup"><span data-stu-id="7e26d-103">To set properties on precedence constraints, you can use one of these tools:</span></span>  
  
-   <span data-ttu-id="7e26d-104">Можно воспользоваться диалоговым окном **Редактор управления очередностью** .</span><span class="sxs-lookup"><span data-stu-id="7e26d-104">You can use the **Precedence Constraint Editor** dialog box.</span></span>  
  
-   <span data-ttu-id="7e26d-105">Можно использовать окно «Свойства».</span><span class="sxs-lookup"><span data-stu-id="7e26d-105">You can use the Properties window.</span></span> <span data-ttu-id="7e26d-106">Окно «Свойства» содержит свойства для настройки элементов управления очередностью, недоступные в диалоговом окне **Редактор управления очередностью** .</span><span class="sxs-lookup"><span data-stu-id="7e26d-106">The Properties window lists properties for configuring precedence constraints that are not available in the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="7e26d-107">В окне «Свойства» можно указать описание и имя управления очередностью и настроить заметку, которая будет отображена для управления очередностью в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="7e26d-107">In the Properties window, you can provide a description and name of the precedence constraint, and configure the annotation to display for the precedence constraint on the design surface.</span></span>  
  
 <span data-ttu-id="7e26d-108">Следующие процедуры описывают способы настройки свойств элементов управления очередностью с помощью этих средств.</span><span class="sxs-lookup"><span data-stu-id="7e26d-108">The following procedures describe how to set properties on precedence constraints by using each of these tools.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-precedence-constraint-editor"></a><span data-ttu-id="7e26d-109">Настройка свойств управления очередностью с помощью редактора управления очередностью</span><span class="sxs-lookup"><span data-stu-id="7e26d-109">To set the properties of a precedence constraint by using the Precedence Constraint Editor</span></span>  
  
1.  <span data-ttu-id="7e26d-110">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="7e26d-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="7e26d-111">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="7e26d-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="7e26d-112">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="7e26d-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="7e26d-113">Дважды щелкните объект управления очередностью.</span><span class="sxs-lookup"><span data-stu-id="7e26d-113">Double-click the precedence constraint.</span></span>  
  
     <span data-ttu-id="7e26d-114">Открывается **Редактор управления очередностью** .</span><span class="sxs-lookup"><span data-stu-id="7e26d-114">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="7e26d-115">В раскрывающемся списке **Операция оценки** выберите операцию оценки.</span><span class="sxs-lookup"><span data-stu-id="7e26d-115">In the **Evaluation operation** drop-down list, select an evaluation operation.</span></span>  
  
6.  <span data-ttu-id="7e26d-116">В раскрывающемся `Value` списке выберите результат выполнения приоритетного исполняемого объекта.</span><span class="sxs-lookup"><span data-stu-id="7e26d-116">In the `Value` drop-down list, select the execution result of the precedence executable.</span></span>  
  
7.  <span data-ttu-id="7e26d-117">Если в операции вычисления используется выражение, в `Expression` поле введите выражение и нажмите кнопку **проверить** , чтобы оценить выражение.</span><span class="sxs-lookup"><span data-stu-id="7e26d-117">If the evaluation operation uses an expression, in the `Expression` box, type an expression, and click **Test** to evaluate the expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e26d-118">В именах переменных учитывается регистр букв.</span><span class="sxs-lookup"><span data-stu-id="7e26d-118">Variable names are case-sensitive.</span></span>  
  
8.  <span data-ttu-id="7e26d-119">Если к исполняемому объекту с ограничением подключено несколько задач или контейнеров, выберите **логическое и** , чтобы указать, что результаты выполнения всех предшествующих исполняемых файлов должны иметь значение `true` .</span><span class="sxs-lookup"><span data-stu-id="7e26d-119">If multiple tasks or containers are connected to the constrained executable, select **Logical AND** to specify that the execution results of all preceding executables must evaluate to `true`.</span></span> <span data-ttu-id="7e26d-120">Выберите **логическое или** , чтобы указать, что только один результат выполнения должен иметь значение `true` .</span><span class="sxs-lookup"><span data-stu-id="7e26d-120">Select **Logical OR** to specify that only one execution result must evaluate to `true`.</span></span>  
  
9. <span data-ttu-id="7e26d-121">Нажмите кнопку **ОК** , чтобы закрыть **Редактор управления очередностью**.</span><span class="sxs-lookup"><span data-stu-id="7e26d-121">Click **OK** to close the **Precedence Constraint Editor**.</span></span>  
  
10. <span data-ttu-id="7e26d-122">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="7e26d-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-properties-window"></a><span data-ttu-id="7e26d-123">Настройка свойств управления очередностью с помощью редактора управления очередностью</span><span class="sxs-lookup"><span data-stu-id="7e26d-123">To set the properties of a precedence constraint by using the Properties window</span></span>  
  
1.  <span data-ttu-id="7e26d-124">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий пакет, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="7e26d-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to modify.</span></span>  
  
2.  <span data-ttu-id="7e26d-125">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="7e26d-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="7e26d-126">Перейдите на вкладку **поток управления** . В области конструктора на вкладке **поток управления** щелкните правой кнопкой мыши элемент Управление очередностью и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="7e26d-126">Click the **Control Flow** tab. On the design surface of the **Control Flow** tab, right-click the precedence constraint, and then click **Properties**.</span></span> <span data-ttu-id="7e26d-127">В окне «Свойства» измените значения свойств.</span><span class="sxs-lookup"><span data-stu-id="7e26d-127">In the Properties window, modify the property values.</span></span>  
  
4.  <span data-ttu-id="7e26d-128">В окне **Свойства** установите следующие свойства элементов управления очередностью, доступные для чтения-записи.</span><span class="sxs-lookup"><span data-stu-id="7e26d-128">In the **Properties** window, set the following read/write properties of precedence constraints:</span></span>  
  
    |<span data-ttu-id="7e26d-129">Свойство, доступное для чтения-записи</span><span class="sxs-lookup"><span data-stu-id="7e26d-129">Read/write property</span></span>|<span data-ttu-id="7e26d-130">Действие настройки</span><span class="sxs-lookup"><span data-stu-id="7e26d-130">Configuration action</span></span>|  
    |--------------------------|--------------------------|  
    |<span data-ttu-id="7e26d-131">Описание</span><span class="sxs-lookup"><span data-stu-id="7e26d-131">Description</span></span>|<span data-ttu-id="7e26d-132">Введите описание.</span><span class="sxs-lookup"><span data-stu-id="7e26d-132">Provide a description.</span></span>|  
    |<span data-ttu-id="7e26d-133">EvalOp</span><span class="sxs-lookup"><span data-stu-id="7e26d-133">EvalOp</span></span>|<span data-ttu-id="7e26d-134">Выберите операцию вычисления.</span><span class="sxs-lookup"><span data-stu-id="7e26d-134">Select an evaluation operation.</span></span> <span data-ttu-id="7e26d-135">Если `Expression` выбрана операция, **ExpressionAndConstant**или **ExpressionOrConstant** , можно указать выражение.</span><span class="sxs-lookup"><span data-stu-id="7e26d-135">If the `Expression`, **ExpressionAndConstant**, or **ExpressionOrConstant** operation is selected, you can specify an expression.</span></span>|  
    |<span data-ttu-id="7e26d-136">Выражение</span><span class="sxs-lookup"><span data-stu-id="7e26d-136">Expression</span></span>|<span data-ttu-id="7e26d-137">Если операция вычисления включает в себя выражение, введите выражение.</span><span class="sxs-lookup"><span data-stu-id="7e26d-137">If the evaluation operation includes and expression, provide an expression.</span></span> <span data-ttu-id="7e26d-138">Выражение должно иметь логическое значение.</span><span class="sxs-lookup"><span data-stu-id="7e26d-138">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="7e26d-139">Дополнительные сведения о языке выражений см. в разделе [Выражения служб Integration Services (SSIS)](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7e26d-139">For more information about the expression language, see [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>|  
    |<span data-ttu-id="7e26d-140">LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="7e26d-140">LogicalAnd</span></span>|<span data-ttu-id="7e26d-141">Задайте значение, `LogicalAnd` указывающее, вычисляется ли управление очередностью вместе с другими ограничениями очередностью, когда несколько исполняемых объектов предшествуют и связываются с исполняемым объектом с ограничением.</span><span class="sxs-lookup"><span data-stu-id="7e26d-141">Set `LogicalAnd` to specify whether the precedence constraint is evaluated in concert with other precedence constraints, when multiple executables precede and are linked to the constrained executable</span></span>|  
    |<span data-ttu-id="7e26d-142">Имя</span><span class="sxs-lookup"><span data-stu-id="7e26d-142">Name</span></span>|<span data-ttu-id="7e26d-143">Обновите имя элемента управления очередностью.</span><span class="sxs-lookup"><span data-stu-id="7e26d-143">Update the name of the precedence constraint.</span></span>|  
    |<span data-ttu-id="7e26d-144">ShowAnnotation</span><span class="sxs-lookup"><span data-stu-id="7e26d-144">ShowAnnotation</span></span>|<span data-ttu-id="7e26d-145">Укажите тип заметки, который должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="7e26d-145">Specify the type of annotation to use.</span></span> <span data-ttu-id="7e26d-146">Выберите значение **Never** , чтобы отключить заметки, **AsNeeded** , чтобы разрешить заметки по запросу, **ConstraintName** , чтобы автоматически вставлять заметки, используя значения свойства Name, **ConstraintDescription** , чтобы автоматически вставлять заметки, используя значения свойства Description, и **ConstraintOptions** , чтобы автоматически вставлять заметки, используя значения свойств Value и Expression.</span><span class="sxs-lookup"><span data-stu-id="7e26d-146">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **ConstraintName** to automatically annotate using the value of the Name property, **ConstraintDescription** to automatically annotate using the value of the Description property, and **ConstraintOptions** to automatically annotate using the values of the Value and Expression properties.</span></span>|  
    |<span data-ttu-id="7e26d-147">Значение</span><span class="sxs-lookup"><span data-stu-id="7e26d-147">Value</span></span>|<span data-ttu-id="7e26d-148">Если операция вычисления, указанная в свойстве EvalOP, содержит ограничение, выберите результат выполнения исполняемого объекта с ограничением.</span><span class="sxs-lookup"><span data-stu-id="7e26d-148">If the evaluation operation specified in the EvalOP property includes a constraint, select the execution result of the constraining executable.</span></span>|  
  
5.  <span data-ttu-id="7e26d-149">Закройте окно «Свойства».</span><span class="sxs-lookup"><span data-stu-id="7e26d-149">Close the Properties window.</span></span>  
  
6.  <span data-ttu-id="7e26d-150">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="7e26d-150">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e26d-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e26d-151">See Also</span></span>  
 <span data-ttu-id="7e26d-152">[Управление очередностью](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="7e26d-152">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="7e26d-153">[Подключение задач и контейнеров с помощью управления очередностью по умолчанию](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="7e26d-153">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="7e26d-154">[Установка значения управления очередностью с помощью контекстного меню](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="7e26d-154">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 [<span data-ttu-id="7e26d-155">Использование выражения в элементах управлении очередностью</span><span class="sxs-lookup"><span data-stu-id="7e26d-155">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
