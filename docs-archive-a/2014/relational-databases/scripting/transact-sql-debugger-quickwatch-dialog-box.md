---
title: Диалоговое окно «Быстрая проверка»
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.quickwatch
helpviewer_keywords:
- QuickWatch Dialog [Transact-SQL]
ms.assetid: d6bbb373-1452-41f2-bdc5-86ae689c3dc0
author: rothja
ms.author: jroth
ms.openlocfilehash: 48e4bda558b75bec0c81815c90feff9d6500a803
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668219"
---
# <a name="quickwatch-dialog-box"></a><span data-ttu-id="6dd45-102">Диалоговое окно «Быстрая проверка»</span><span class="sxs-lookup"><span data-stu-id="6dd45-102">QuickWatch Dialog Box</span></span>
  <span data-ttu-id="6dd45-103">Используйте диалоговое окно **Быстрая проверка** , чтобы быстро просмотреть тип данных и значение одного из выражений [!INCLUDE[tsql](../../includes/tsql-md.md)] , такого как переменная или параметр, при отладке кода [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6dd45-103">Use the **QuickWatch** dialog box to quickly view the data type and value of one [!INCLUDE[tsql](../../includes/tsql-md.md)] expression, such as a variable or parameter, when you are debugging [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="6dd45-104">Чтобы просмотреть несколько выражений, можно также добавить выражение в окне **Контрольные значения** .</span><span class="sxs-lookup"><span data-stu-id="6dd45-104">To watch multiple expressions, you can also add the expression to a **Watch** window.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="6dd45-105">Список задач</span><span class="sxs-lookup"><span data-stu-id="6dd45-105">Task List</span></span>  
 <span data-ttu-id="6dd45-106">**Доступ к диалоговому окну «Быстрая проверка»**</span><span class="sxs-lookup"><span data-stu-id="6dd45-106">**To access the QuickWatch dialog box**</span></span>  
  
-   <span data-ttu-id="6dd45-107">В меню **Отладка** выберите пункт **Быстрая проверка**.</span><span class="sxs-lookup"><span data-stu-id="6dd45-107">On the **Debug** menu, click **QuickWatch**.</span></span>  
  
 <span data-ttu-id="6dd45-108">**Просмотр информации о выражении**</span><span class="sxs-lookup"><span data-stu-id="6dd45-108">**To view the information about an expression**</span></span>  
  
1.  <span data-ttu-id="6dd45-109">В списке **Выражение** введите или выберите необходимое выражение.</span><span class="sxs-lookup"><span data-stu-id="6dd45-109">In the **Expression** list box, type or select the expression that you want.</span></span> <span data-ttu-id="6dd45-110">Поддерживаются следующие выражения [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="6dd45-110">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] expressions are supported:</span></span>  
  
    -   <span data-ttu-id="6dd45-111">Переменные.</span><span class="sxs-lookup"><span data-stu-id="6dd45-111">Variables.</span></span>  
  
    -   <span data-ttu-id="6dd45-112">Параметры.</span><span class="sxs-lookup"><span data-stu-id="6dd45-112">Parameters.</span></span>  
  
    -   <span data-ttu-id="6dd45-113">Системные функции, имена которых начинаются с @@.</span><span class="sxs-lookup"><span data-stu-id="6dd45-113">System functions whose name starts with @@.</span></span>  
  
    -   <span data-ttu-id="6dd45-114">Выражения, построенные путем применения операторов к одной или нескольким переменным, параметрам или системным функциям, например @IntegerCounter+1 или FirstName+LastName.</span><span class="sxs-lookup"><span data-stu-id="6dd45-114">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
    -   <span data-ttu-id="6dd45-115">Инструкции Transact-SQL, возвращающие единственное значение, например SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="6dd45-115">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
2.  <span data-ttu-id="6dd45-116">Нажмите кнопку **Пересчет**.</span><span class="sxs-lookup"><span data-stu-id="6dd45-116">Click **Reevaluate**.</span></span>  
  
 <span data-ttu-id="6dd45-117">**Добавление выражения быстрого просмотра в окно «Просмотр значений»**</span><span class="sxs-lookup"><span data-stu-id="6dd45-117">**To add the QuickWatch expression to a Watch window**</span></span>  
  
-   <span data-ttu-id="6dd45-118">Нажмите кнопку **Добавить контрольное значение**.</span><span class="sxs-lookup"><span data-stu-id="6dd45-118">Click **Add Watch**.</span></span>  
  
 <span data-ttu-id="6dd45-119">**Изменение значения выражения быстрой проверки**</span><span class="sxs-lookup"><span data-stu-id="6dd45-119">**To change the value of the QuickWatch expression**</span></span>  
  
-   <span data-ttu-id="6dd45-120">Щелкните правой кнопкой мыши выражение и выберите команду **Изменить значение**.</span><span class="sxs-lookup"><span data-stu-id="6dd45-120">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6dd45-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="6dd45-121">Options</span></span>  
 <span data-ttu-id="6dd45-122">**Список выражений**</span><span class="sxs-lookup"><span data-stu-id="6dd45-122">**Expression list**</span></span>  
 <span data-ttu-id="6dd45-123">Отображается выражение, выбранное в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="6dd45-123">Displays the currently selected expression.</span></span> <span data-ttu-id="6dd45-124">Раскрывающийся список содержит набор выражений, которые можно выбрать для отображения.</span><span class="sxs-lookup"><span data-stu-id="6dd45-124">The drop-down list contains a set of expressions that you can select to display.</span></span> <span data-ttu-id="6dd45-125">В списке содержатся выражения, доступные в пределах кадра стека, выбранного в настоящее время в окне **Стек вызова** .</span><span class="sxs-lookup"><span data-stu-id="6dd45-125">The expressions in the list are those available in the scope of the stack frame that is currently selected in the **Call Stack** window.</span></span> <span data-ttu-id="6dd45-126">Чтобы отобразить другое выражение, введите выражение или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="6dd45-126">To display a different expression, either enter the expression or select it from list.</span></span> <span data-ttu-id="6dd45-127">Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] поддерживает следующие выражения: переменные, параметры и системные функции, которые имеют имена, начинающиеся с @@.</span><span class="sxs-lookup"><span data-stu-id="6dd45-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports the following expressions: variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="6dd45-128">**Сетка значений**</span><span class="sxs-lookup"><span data-stu-id="6dd45-128">**Value grid**</span></span>  
 <span data-ttu-id="6dd45-129">Отображаются свойства выражения, которое просматривается в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="6dd45-129">Displays the properties of the expression that is currently being watched.</span></span>  
  
 <span data-ttu-id="6dd45-130">**Название**</span><span class="sxs-lookup"><span data-stu-id="6dd45-130">**Name**</span></span>  
 <span data-ttu-id="6dd45-131">Является просматриваемым выражением [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6dd45-131">Is the [!INCLUDE[tsql](../../includes/tsql-md.md)] expression being watched.</span></span>  
  
 <span data-ttu-id="6dd45-132">**Value**</span><span class="sxs-lookup"><span data-stu-id="6dd45-132">**Value**</span></span>  
 <span data-ttu-id="6dd45-133">Отображается значение, которое в настоящее время присвоено выражению.</span><span class="sxs-lookup"><span data-stu-id="6dd45-133">Displays the value that is currently assigned to the expression.</span></span> <span data-ttu-id="6dd45-134">Если в настоящее время выражение не имеет значения, отображается пустое поле.</span><span class="sxs-lookup"><span data-stu-id="6dd45-134">A blank is displayed when the expression currently has no value.</span></span>  
  
 <span data-ttu-id="6dd45-135">Если длина выражения больше ширины столбца **Значение** , полное значение отображается в подсказке при перемещении указателя на ячейку **Значение** для этого выражения.</span><span class="sxs-lookup"><span data-stu-id="6dd45-135">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="6dd45-136">Значок лупы в ячейке **Значение** указывает, что доступен визуализатор отладчика [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6dd45-136">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="6dd45-137">В этом списке можно указать **Визуализатор текста**, **Визуализатор XML**или **Визуализатор HTML**.</span><span class="sxs-lookup"><span data-stu-id="6dd45-137">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="6dd45-138">Чтобы выполнить запуск визуализатора отладчика, щелкните значок лупы.</span><span class="sxs-lookup"><span data-stu-id="6dd45-138">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="6dd45-139">В отладчике [!INCLUDE[tsql](../../includes/tsql-md.md)] откроется диалоговое окно, в котором данные будут отображены в формате, соответствующем типу этих данных.</span><span class="sxs-lookup"><span data-stu-id="6dd45-139">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="6dd45-140">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6dd45-140">**Type**</span></span>  
 <span data-ttu-id="6dd45-141">Отображает тип данных выражения.</span><span class="sxs-lookup"><span data-stu-id="6dd45-141">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd45-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="6dd45-142">See Also</span></span>  
 <span data-ttu-id="6dd45-143">[Отладчик Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="6dd45-143">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="6dd45-144">[Сведения отладчика Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="6dd45-144">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="6dd45-145">[окно просмотра значений](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="6dd45-145">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="6dd45-146">[окно локальных переменных](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="6dd45-146">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="6dd45-147">[Окно стека вызовов](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="6dd45-147">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 [<span data-ttu-id="6dd45-148">Выражения (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6dd45-148">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
  
  
