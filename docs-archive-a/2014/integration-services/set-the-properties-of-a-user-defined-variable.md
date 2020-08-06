---
title: Задание свойств определяемой пользователем переменной | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- modifying variables
- variables [Integration Services], properties
ms.assetid: f98ddbec-f668-4dba-a768-44ac3ae0536f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf53be469e3d377f7efb379f78e85e31b26767b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751275"
---
# <a name="set-the-properties-of-a-user-defined-variable"></a><span data-ttu-id="cfcb8-102">Установка свойств определяемой пользователем переменной</span><span class="sxs-lookup"><span data-stu-id="cfcb8-102">Set the Properties of a User-Defined Variable</span></span>
  <span data-ttu-id="cfcb8-103">Чтобы задать свойства определяемой пользователем переменной в службах [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], можно использовать один из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-103">To set the properties of a user-defined variable in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], you can use one of the following features:</span></span>  
  
-   <span data-ttu-id="cfcb8-104">Окно «Переменные».</span><span class="sxs-lookup"><span data-stu-id="cfcb8-104">Variables window.</span></span>  
  
-   <span data-ttu-id="cfcb8-105">Окно «Свойства».</span><span class="sxs-lookup"><span data-stu-id="cfcb8-105">Properties window.</span></span> <span data-ttu-id="cfcb8-106">В окне **Свойства** указаны свойства для настройки переменных, недоступные в окне **Переменные** : Description, EvaluateAsExpression, Expression, ReadOnly, ValueType и IncludeInDebugDump.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-106">The **Properties** window lists properties for configuring variables that are not available in the **Variables** window: Description, EvaluateAsExpression, Expression, ReadOnly, ValueType, and IncludeInDebugDump.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfcb8-107">Службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] предоставляют также набор системных переменных, свойства которых нельзя обновить, за исключением свойства RaiseChangedEvent.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-107">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] also provides a set of system variables whose properties cannot be updated, with the exception of the RaiseChangedEvent property.</span></span>  
  
 <span data-ttu-id="cfcb8-108">**Задание выражений в переменных**</span><span class="sxs-lookup"><span data-stu-id="cfcb8-108">**Setting Expressions on Variables**</span></span>  
  
 <span data-ttu-id="cfcb8-109">При использовании окна **Свойства** для задания выражений на определяемой пользователем переменной:</span><span class="sxs-lookup"><span data-stu-id="cfcb8-109">When you use the **Properties** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="cfcb8-110">Значение переменной можно задать с помощью свойства Value или Expression.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-110">The value of a variable can be set by the Value or the Expression property.</span></span> <span data-ttu-id="cfcb8-111">По умолчанию свойство EvaluateAsExpression имеет значение `False` , а значение переменной задается свойством Value.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-111">By default, the EvaluateAsExpression property is set to `False` and the value of the variable is set by the Value property.</span></span> <span data-ttu-id="cfcb8-112">Чтобы использовать выражение для задания значения, необходимо сначала установить EvaluateAsExpression в значение `True` , а затем указать выражение в свойстве Expression.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-112">To use an expression to set the value, you must first set EvaluateAsExpression to `True`, and then provide an expression in the Expression property.</span></span> <span data-ttu-id="cfcb8-113">Свойство Value автоматически устанавливается в значение результата выражения.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-113">The Value property is automatically set to the evaluation result of the expression.</span></span>  
  
-   <span data-ttu-id="cfcb8-114">Свойство ValueType содержит тип данных значения свойства Value.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-114">The ValueType property contains the data type of the value in the Value property.</span></span> <span data-ttu-id="cfcb8-115">Если свойство Value задается с помощью выражения, свойство ValueType автоматически обновляется типом данных, совместимым с результатом вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-115">When Value is set by an expression, ValueType is automatically updated to a data type that is compatible with the evaluation result of the expression.</span></span> <span data-ttu-id="cfcb8-116">Например, если значение содержит 0, а свойство ValueType содержит **Int32** , а затем для параметра expression задано значение GETDATE (), то value содержит текущую дату и время, а ValueType имеет значение `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="cfcb8-116">For example, if Value contains 0 and ValueType property contains **Int32** and you then set Expression to GETDATE(), Value contains the current date and time and ValueType is set to `DateTime`.</span></span>  
  
-   <span data-ttu-id="cfcb8-117">Окно **Свойства** для переменной предоставляет доступ к диалоговому окну **Построитель выражений** .</span><span class="sxs-lookup"><span data-stu-id="cfcb8-117">The **Properties** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="cfcb8-118">Это средство можно использовать для построения, проверки и вычисления выражений.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-118">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="cfcb8-119">Дополнительные сведения см. в разделах [Построитель выражений](expressions/expression-builder.md) и [Выражения служб Integration Services (SSIS)](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cfcb8-119">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="cfcb8-120">При использовании окна **Переменные** для задания выражений на определяемой пользователем переменной:</span><span class="sxs-lookup"><span data-stu-id="cfcb8-120">When you use the **Variables** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="cfcb8-121">Чтобы использовать выражение для задания значения переменной, сначала убедитесь, что тип данных Variable совместим с результатом вычисления выражения, а затем укажите выражение в `Expression` столбце окна **переменные** .</span><span class="sxs-lookup"><span data-stu-id="cfcb8-121">To use an expression to set the variable value, first confirm that the variable data type is compatible with the evaluation result of the expression and then provide an expression in the `Expression` column of the **Variables** window.</span></span> <span data-ttu-id="cfcb8-122">Свойство EvaluateAsExpression в окне **Свойства** автоматически устанавливается в значение `True` .</span><span class="sxs-lookup"><span data-stu-id="cfcb8-122">The EvaluateAsExpression property in the **Properties** window is automatically set to `True`.</span></span>  
  
-   <span data-ttu-id="cfcb8-123">При присваивании выражения переменной рядом с переменной отображается специальный маркер значка.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-123">When you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="cfcb8-124">Этот специальный маркер значка отображается также рядом с диспетчерами соединений и задачами, для которых заданы выражения.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-124">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
-   <span data-ttu-id="cfcb8-125">Окно **Переменные** для переменной предоставляет доступ к диалоговому окну **Построитель выражений** .</span><span class="sxs-lookup"><span data-stu-id="cfcb8-125">The **Variables** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="cfcb8-126">Это средство можно использовать для построения, проверки и вычисления выражений.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-126">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="cfcb8-127">Дополнительные сведения см. в разделах [Построитель выражений](expressions/expression-builder.md) и [Выражения служб Integration Services (SSIS)](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cfcb8-127">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="cfcb8-128">Если в окне **переменные** и **свойства** присвоить выражение переменной и параметру `EvaluateAsExpression` присвоено значение `True` , то изменить тип данных переменной нельзя.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-128">In both the **Variables** and **Properties** window, if you assign an expression to the variable, and `EvaluateAsExpression` is set to `True`, you cannot change the variable data type.</span></span>  
  
 <span data-ttu-id="cfcb8-129">**Задание свойств пространства имен и имени**</span><span class="sxs-lookup"><span data-stu-id="cfcb8-129">**Setting the Namespace and Name Properties**</span></span>  
  
 <span data-ttu-id="cfcb8-130">Первым символом в значениях свойств `Name` и `Namespace` согласно стандарту Юникод 2.0 должна быть буква или символ подчеркивания (_).</span><span class="sxs-lookup"><span data-stu-id="cfcb8-130">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="cfcb8-131">Далее могут следовать буквы или цифры по определению стандарта Юникод 2.0 или символ подчеркивания (\_).</span><span class="sxs-lookup"><span data-stu-id="cfcb8-131">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="using-the-variables-window-to-set-properties"></a><span data-ttu-id="cfcb8-132">Использование окна «Переменные» для задания значений свойств</span><span class="sxs-lookup"><span data-stu-id="cfcb8-132">Using the Variables Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-variables-window"></a><span data-ttu-id="cfcb8-133">Задание свойств переменной с помощью окна «Переменные»</span><span class="sxs-lookup"><span data-stu-id="cfcb8-133">To set the properties of a variable by using the Variables window</span></span>  
  
1.  <span data-ttu-id="cfcb8-134">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-134">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="cfcb8-135">В окне обозревателя решений щелкните пакет правой кнопкой мыши для его открытия.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-135">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="cfcb8-136">В меню **Службы SSIS** щелкните **Переменные**.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-136">On the **SSIS** menu, click **Variables**.</span></span>  
  
     <span data-ttu-id="cfcb8-137">При необходимости окно **Переменные** можно открыть, назначив команде View.Variables нужное сочетание клавиш на странице **Клавиатура** диалогового окна **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="cfcb8-137">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="cfcb8-138">При желании в окне **Переменные** выберите **Параметры сетки**, а затем выберите столбцы для отображения в окне **Переменные** и выберите фильтры для списка переменных.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-138">Optionally, in the **Variables** window click **Grid Options**, and then select the columns to appear in the **Variables** window and select the filters to apply to the list of variables.</span></span>  
  
5.  <span data-ttu-id="cfcb8-139">Выберите переменную из списка, а затем обновите значения в `Name` **типах данных**,, `Value` `Namespace` ,, **Создайте событие изменения**, **Описание** и `Expression` столбцы.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-139">Select the variable in the list, and then update values in the `Name`, **Data Type**, `Value`, `Namespace`, **Raise Change Event**, **Description,** and `Expression` columns.</span></span>  
  
6.  <span data-ttu-id="cfcb8-140">Выберите переменную из списка, а затем нажмите **Переместить переменную** для изменения области.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-140">Select the variable in the list, and then click **Move Variable** to change the scope.</span></span>  
  
7.  <span data-ttu-id="cfcb8-141">Чтобы сохранить измененный пакет, в меню **Файл** выберите команду **Сохранить выбранные элементы**.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-141">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="using-the-properties-window-to-set-properties"></a><span data-ttu-id="cfcb8-142">Использование окна «Свойства» для задания значений свойств</span><span class="sxs-lookup"><span data-stu-id="cfcb8-142">Using the Properties Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-properties-window"></a><span data-ttu-id="cfcb8-143">Задание свойств переменной с помощью окна «Свойства»</span><span class="sxs-lookup"><span data-stu-id="cfcb8-143">To set the properties of a variable by using the Properties window</span></span>  
  
1.  <span data-ttu-id="cfcb8-144">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-144">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="cfcb8-145">В окне обозревателя решений щелкните пакет правой кнопкой мыши для его открытия.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-145">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="cfcb8-146">В меню **Просмотр** выберите пункт **Окно свойств**.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-146">On the **View** menu, click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="cfcb8-147">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] перейдите на вкладку **Обозреватель пакетов** и разверните узел пакета.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-147">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Package Explorer** tab and expand the Package node.</span></span>  
  
5.  <span data-ttu-id="cfcb8-148">Чтобы изменить переменные в области пакета, разверните узел «Переменные» или разворачивайте узлы «Обработчики событий» или «Исполняемые объекты», пока не обнаружите узел «Переменные» с переменной, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-148">To modify variables with package scope, expand the Variables node; otherwise, expand the Event Handlers or Executables nodes until you locate the Variables node that contains the variable that you want to modify.</span></span>  
  
6.  <span data-ttu-id="cfcb8-149">Щелкните переменную, свойства которой необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-149">Click the variable whose properties you want to modify.</span></span>  
  
7.  <span data-ttu-id="cfcb8-150">В окне **Свойства** обновите свойства переменной для чтения/записи.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-150">In the **Properties** window, update the read/write variable properties.</span></span> <span data-ttu-id="cfcb8-151">Для переменных, определяемых пользователем, некоторые свойства отображаются только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-151">Some properties are read/read only for user-defined variables.</span></span>  
  
     <span data-ttu-id="cfcb8-152">Дополнительные сведения о свойствах см. в разделе [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="cfcb8-152">For more information about the properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
8.  <span data-ttu-id="cfcb8-153">Чтобы сохранить измененный пакет, в меню **Файл** выберите команду **Сохранить выбранные элементы**.</span><span class="sxs-lookup"><span data-stu-id="cfcb8-153">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfcb8-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfcb8-154">See Also</span></span>  
 <span data-ttu-id="cfcb8-155">[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="cfcb8-155">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="cfcb8-156">[Использование переменных в пакетах](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="cfcb8-156">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="cfcb8-157">Добавление, удаление и изменение области определяемой пользователем переменной в пакете</span><span class="sxs-lookup"><span data-stu-id="cfcb8-157">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
