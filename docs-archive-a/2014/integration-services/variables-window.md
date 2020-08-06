---
title: Окно "Переменные" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variables.f1
helpviewer_keywords:
- Variables Window dialog box
ms.assetid: f405e5ce-ef69-4c58-8c7d-a3d44dfe9ab0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffd6da67386291c14ebf588da9a1cf8f399214b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666116"
---
# <a name="variables-window"></a><span data-ttu-id="24a5a-102">Окно переменных</span><span class="sxs-lookup"><span data-stu-id="24a5a-102">Variables Window</span></span>
  <span data-ttu-id="24a5a-103">Окно **Переменные** используется для создания и изменения переменных, определяемых пользователем, и просмотра системных переменных.</span><span class="sxs-lookup"><span data-stu-id="24a5a-103">Use the **Variables** window to create and modify user-defined variables and view system variables.</span></span>  
  
 <span data-ttu-id="24a5a-104">По умолчанию окно **Переменные** располагается ниже области **Диспетчеры соединений** конструктора служб SSIS в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24a5a-104">By default, the **Variables** window is located below the **Connection Managers** area in the SSIS Designer, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="24a5a-105">Если окно **Переменные** не отображается, выберите пункт **Переменные** в меню **Службы SSIS**, чтобы отобразить его.</span><span class="sxs-lookup"><span data-stu-id="24a5a-105">If you don't see the **Variables** window, click **Variables** on the **SSIS** menu to display the window.</span></span>  
  
 <span data-ttu-id="24a5a-106">При необходимости окно **Переменные** можно открыть, назначив команде View.Variables нужное сочетание клавиш на странице **Клавиатура** диалогового окна **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="24a5a-106">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24a5a-107">Первым символом в значениях свойств `Name` и `Namespace` согласно стандарту Юникод 2.0 должна быть буква или символ подчеркивания (_).</span><span class="sxs-lookup"><span data-stu-id="24a5a-107">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="24a5a-108">Далее могут следовать буквы или цифры по определению стандарта Юникод 2.0 или символ подчеркивания (\_).</span><span class="sxs-lookup"><span data-stu-id="24a5a-108">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="options"></a><span data-ttu-id="24a5a-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="24a5a-109">Options</span></span>  
 <span data-ttu-id="24a5a-110">**Добавить переменную**</span><span class="sxs-lookup"><span data-stu-id="24a5a-110">**Add Variable**</span></span>  
 <span data-ttu-id="24a5a-111">Добавить переменную, определяемую пользователем.</span><span class="sxs-lookup"><span data-stu-id="24a5a-111">Add a user-defined variable.</span></span>  
  
 <span data-ttu-id="24a5a-112">**Переместить переменную**</span><span class="sxs-lookup"><span data-stu-id="24a5a-112">**Move Variable**</span></span>  
 <span data-ttu-id="24a5a-113">Выберите переменную из списка, а затем нажмите **Переместить переменную** , чтобы изменить область переменной.</span><span class="sxs-lookup"><span data-stu-id="24a5a-113">Click a variable in the list, and then click **Move Variable** to change the variable scope.</span></span> <span data-ttu-id="24a5a-114">В диалоговом окне **Выбор новой области** выберите пакет, контейнер, задачу или обработчик событий в пакете, чтобы изменить область переменной.</span><span class="sxs-lookup"><span data-stu-id="24a5a-114">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
 <span data-ttu-id="24a5a-115">Дополнительные сведения об области переменной см. в разделе [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="24a5a-115">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="24a5a-116">**Удалить переменную**</span><span class="sxs-lookup"><span data-stu-id="24a5a-116">**Delete Variable**</span></span>  
 <span data-ttu-id="24a5a-117">Выберите переменную из списка и щелкните **Удалить переменную**.</span><span class="sxs-lookup"><span data-stu-id="24a5a-117">Select a variable from the list, and then click **Delete Variable**.</span></span>  
  
 <span data-ttu-id="24a5a-118">**Параметры сетки**</span><span class="sxs-lookup"><span data-stu-id="24a5a-118">**Grid Options**</span></span>  
 <span data-ttu-id="24a5a-119">Нажмите, чтобы открыть диалоговое окно **Параметры сетки переменных** , в котором можно изменить выбор столбцов и применить фильтры к окну **Переменные** .</span><span class="sxs-lookup"><span data-stu-id="24a5a-119">Click to open the **Variable Grid Options** dialog box where you can change the column selection and apply filters to the **Variables** window.</span></span> <span data-ttu-id="24a5a-120">Дополнительные сведения см. в статье [Параметры сетки переменных](../../2014/integration-services/variable-grid-options.md).</span><span class="sxs-lookup"><span data-stu-id="24a5a-120">For more information, see [Variable Grid Options](../../2014/integration-services/variable-grid-options.md).</span></span>  
  
 `Name`  
 <span data-ttu-id="24a5a-121">Посмотреть имя переменной.</span><span class="sxs-lookup"><span data-stu-id="24a5a-121">View the variable name.</span></span> <span data-ttu-id="24a5a-122">Имена пользовательских переменных можно изменить.</span><span class="sxs-lookup"><span data-stu-id="24a5a-122">You can update the name for user-defined variables.</span></span>  
  
 <span data-ttu-id="24a5a-123">**Область**</span><span class="sxs-lookup"><span data-stu-id="24a5a-123">**Scope**</span></span>  
 <span data-ttu-id="24a5a-124">Посмотреть область переменной.</span><span class="sxs-lookup"><span data-stu-id="24a5a-124">View the scope of the variable.</span></span> <span data-ttu-id="24a5a-125">Областью переменной может быть весь пакет, а также контейнер или задача.</span><span class="sxs-lookup"><span data-stu-id="24a5a-125">A variable has either the scope of the entire package, or the scope of a container or task.</span></span> <span data-ttu-id="24a5a-126">Область переменной должна быть достаточной, чтобы переменная была видна любым другим задачам и компонентам, которые должны считывать или устанавливать ее значение.</span><span class="sxs-lookup"><span data-stu-id="24a5a-126">The scope of the variable must be sufficient so that the variable is visible to any other tasks or components that need to read or set its value.</span></span>  
  
 <span data-ttu-id="24a5a-127">Можно изменить область, щелкнув переменную и нажав **Переместить переменную** в окне **Переменные** .</span><span class="sxs-lookup"><span data-stu-id="24a5a-127">You can change the scope by clicking the variable and then clicking **Move Variable** in the **Variables** window.</span></span>  
  
 <span data-ttu-id="24a5a-128">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="24a5a-128">**Data Type**</span></span>  
 <span data-ttu-id="24a5a-129">Посмотреть тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="24a5a-129">View the data type of the variable.</span></span> <span data-ttu-id="24a5a-130">Для пользовательских переменных можно выбрать тип данных из списка.</span><span class="sxs-lookup"><span data-stu-id="24a5a-130">You can select a data type from the list for user-defined variables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24a5a-131">При присваивании выражения переменной тип данных нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="24a5a-131">If you assign an expression to the variable, you cannot change the data type.</span></span>  
  
 <span data-ttu-id="24a5a-132">**Значение**</span><span class="sxs-lookup"><span data-stu-id="24a5a-132">**Value**</span></span>  
 <span data-ttu-id="24a5a-133">Посмотреть значение переменной.</span><span class="sxs-lookup"><span data-stu-id="24a5a-133">View the variable value.</span></span> <span data-ttu-id="24a5a-134">Значение пользовательской переменной можно изменить.</span><span class="sxs-lookup"><span data-stu-id="24a5a-134">You can update the value for user-defined variables.</span></span> <span data-ttu-id="24a5a-135">Это значение может быть буквенным или представлять собой выражение, а значение может быть многостроковым.</span><span class="sxs-lookup"><span data-stu-id="24a5a-135">This value can be a literal or an expression, and the value can be a multi-line string.</span></span> <span data-ttu-id="24a5a-136">Чтобы назначить выражение переменной, нажмите кнопку троеточия рядом с столбцом **Выражение** в окне **Переменные** .</span><span class="sxs-lookup"><span data-stu-id="24a5a-136">To assign an expression to the variable, click the ellipse button that is next to the **Expression** column in the **Variables** window.</span></span>  
  
 `Namespace`  
 <span data-ttu-id="24a5a-137">Посмотреть имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="24a5a-137">View the namespace name.</span></span> <span data-ttu-id="24a5a-138">Пользовательские переменные изначально создаются в пространстве имен **User** , но имя пространства имен можно изменить в `Namespace` поле.</span><span class="sxs-lookup"><span data-stu-id="24a5a-138">User-defined variables are initially created in the **User** namespace, but you can change the namespace name in the `Namespace` field.</span></span> <span data-ttu-id="24a5a-139">Для вывода этого столбца щелкните **Параметры сетки**.</span><span class="sxs-lookup"><span data-stu-id="24a5a-139">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="24a5a-140">**Создать событие изменения**</span><span class="sxs-lookup"><span data-stu-id="24a5a-140">**Raise Change Event**</span></span>  
 <span data-ttu-id="24a5a-141">Указывает, будет ли активировано событие `OnVariableValueChanged` в случае изменения значения.</span><span class="sxs-lookup"><span data-stu-id="24a5a-141">Indicate whether to raise the `OnVariableValueChanged` event when a value changes.</span></span> <span data-ttu-id="24a5a-142">Значение пользовательской и системной переменной можно изменить.</span><span class="sxs-lookup"><span data-stu-id="24a5a-142">You can update the value for user-defined and system variables.</span></span> <span data-ttu-id="24a5a-143">По умолчанию окно **Переменные** не включает этот столбец.</span><span class="sxs-lookup"><span data-stu-id="24a5a-143">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="24a5a-144">Для вывода этого столбца щелкните **Параметры сетки**.</span><span class="sxs-lookup"><span data-stu-id="24a5a-144">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="24a5a-145">**Описание**</span><span class="sxs-lookup"><span data-stu-id="24a5a-145">**Description**</span></span>  
 <span data-ttu-id="24a5a-146">Просмотр описания переменной.</span><span class="sxs-lookup"><span data-stu-id="24a5a-146">View the variable description.</span></span> <span data-ttu-id="24a5a-147">Можно изменить описание для пользовательских переменных.</span><span class="sxs-lookup"><span data-stu-id="24a5a-147">You can change the description for user-defined variables.</span></span> <span data-ttu-id="24a5a-148">По умолчанию окно **Переменные** не включает этот столбец.</span><span class="sxs-lookup"><span data-stu-id="24a5a-148">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="24a5a-149">Для вывода этого столбца щелкните **Параметры сетки**.</span><span class="sxs-lookup"><span data-stu-id="24a5a-149">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="24a5a-150">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="24a5a-150">**Expression**</span></span>  
 <span data-ttu-id="24a5a-151">Просмотр выражения, присвоенного переменной.</span><span class="sxs-lookup"><span data-stu-id="24a5a-151">View the expression assigned to the variable.</span></span> <span data-ttu-id="24a5a-152">Чтобы присвоить выражение, нажмите кнопку троеточия.</span><span class="sxs-lookup"><span data-stu-id="24a5a-152">To assign an expression, click the ellipse button.</span></span>  
  
 <span data-ttu-id="24a5a-153">При присваивании выражения переменной рядом с переменной отображается специальный маркер значка.</span><span class="sxs-lookup"><span data-stu-id="24a5a-153">If you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="24a5a-154">Этот специальный маркер значка отображается также рядом с диспетчерами соединений и задачами, для которых заданы выражения.</span><span class="sxs-lookup"><span data-stu-id="24a5a-154">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a5a-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="24a5a-155">See Also</span></span>  
 <span data-ttu-id="24a5a-156">[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="24a5a-156">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="24a5a-157">[Использование переменных в пакетах](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="24a5a-157">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="24a5a-158">[Выражения&#41; Integration Services &#40;SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="24a5a-158">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="24a5a-159">Создание файлов дампа для выполнения пакетов</span><span class="sxs-lookup"><span data-stu-id="24a5a-159">Generating Dump Files for Package Execution</span></span>](troubleshooting/generating-dump-files-for-package-execution.md)  
  
  
