---
title: окно просмотра значений
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Watch Window [Transact-SQL]
ms.assetid: 23f3baa4-14c2-4262-92f7-3f43fcfa0436
author: rothja
ms.author: jroth
ms.openlocfilehash: c2a3db9b095902fcb5620af91fb86d80f773d606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666479"
---
# <a name="watch-window"></a><span data-ttu-id="4b199-102">окно просмотра значений</span><span class="sxs-lookup"><span data-stu-id="4b199-102">Watch Window</span></span>
  <span data-ttu-id="4b199-103">В окне **Контрольные значения** отображается информация о выбранных выражениях.</span><span class="sxs-lookup"><span data-stu-id="4b199-103">The **Watch** window displays information about the expressions that you have selected.</span></span> <span data-ttu-id="4b199-104">Может быть открыто четыре окна контрольных значений: **Контрольные значения 1**, **Контрольные значения 2, Контрольные значения 3**и **Контрольные значения 4**.</span><span class="sxs-lookup"><span data-stu-id="4b199-104">There can be up to four watch windows: **Watch 1**, **Watch 2, Watch 3**, and **Watch 4**.</span></span> <span data-ttu-id="4b199-105">Выражения вычисляются в области текущего кадра стека вызова, который выбран в окне **Стек вызовов** .</span><span class="sxs-lookup"><span data-stu-id="4b199-105">The expressions are evaluated within the scope of the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="4b199-106">Чтобы иметь возможность контролировать значения переменных и выражений, необходимо находиться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="4b199-106">You must be in debug mode to watch variables and expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="4b199-107">Список задач</span><span class="sxs-lookup"><span data-stu-id="4b199-107">Task List</span></span>  
 <span data-ttu-id="4b199-108">**Доступ к окнам «Контрольные значения»**</span><span class="sxs-lookup"><span data-stu-id="4b199-108">**To access the Watch windows**</span></span>  
  
-   <span data-ttu-id="4b199-109">В меню **Отладка** выберите пункт **Окна**, затем пункт **Контрольные значения**и выберите пункт **Контрольные значения 1**, **Контрольные значения 2, Контрольные значения 3**или **Контрольные значения 4**.</span><span class="sxs-lookup"><span data-stu-id="4b199-109">On the **Debug** menu, click **Windows**, click **Watch**, and then click **Watch 1**, **Watch 2, Watch 3**, or **Watch 4**.</span></span>  
  
 <span data-ttu-id="4b199-110">**Изменение значения выражения**</span><span class="sxs-lookup"><span data-stu-id="4b199-110">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="4b199-111">Щелкните правой кнопкой мыши выражение и выберите команду **Изменить значение**.</span><span class="sxs-lookup"><span data-stu-id="4b199-111">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="4b199-112">Столбцы</span><span class="sxs-lookup"><span data-stu-id="4b199-112">Columns</span></span>  
 <span data-ttu-id="4b199-113">**Название**</span><span class="sxs-lookup"><span data-stu-id="4b199-113">**Name**</span></span>  
 <span data-ttu-id="4b199-114">Выражения, перечисляемые отладчиком [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b199-114">Are the expressions that are listed by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="4b199-115">Поддерживаются следующие выражения:</span><span class="sxs-lookup"><span data-stu-id="4b199-115">The following expressions are supported:</span></span>  
  
-   <span data-ttu-id="4b199-116">Переменные.</span><span class="sxs-lookup"><span data-stu-id="4b199-116">Variables.</span></span>  
  
-   <span data-ttu-id="4b199-117">Параметры.</span><span class="sxs-lookup"><span data-stu-id="4b199-117">Parameters.</span></span>  
  
-   <span data-ttu-id="4b199-118">Системные функции, имена которых начинаются с @@.</span><span class="sxs-lookup"><span data-stu-id="4b199-118">System functions whose name starts with @@.</span></span>  
  
-   <span data-ttu-id="4b199-119">Выражения, построенные путем применения операторов к одной или нескольким переменным, параметрам или системным функциям, например @IntegerCounter+1 или FirstName+LastName.</span><span class="sxs-lookup"><span data-stu-id="4b199-119">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
-   <span data-ttu-id="4b199-120">Инструкции Transact-SQL, возвращающие единственное значение, например SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="4b199-120">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
 <span data-ttu-id="4b199-121">**Value**</span><span class="sxs-lookup"><span data-stu-id="4b199-121">**Value**</span></span>  
 <span data-ttu-id="4b199-122">Отображается значение, возвращаемое после оценки отладчиком [!INCLUDE[tsql](../../includes/tsql-md.md)] выражения, указанного в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="4b199-122">Displays the value that is returned after the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger evaluates the expression specified in **Name**.</span></span>  
  
 <span data-ttu-id="4b199-123">Если длина выражения больше ширины столбца **Значение** , полное значение отображается в подсказке при перемещении указателя на ячейку **Значение** для этого выражения.</span><span class="sxs-lookup"><span data-stu-id="4b199-123">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="4b199-124">Значок лупы в ячейке **Значение** указывает, что доступен визуализатор отладчика [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b199-124">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="4b199-125">В этом списке можно указать **Визуализатор текста**, **Визуализатор XML**или **Визуализатор HTML**.</span><span class="sxs-lookup"><span data-stu-id="4b199-125">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="4b199-126">Чтобы выполнить запуск визуализатора отладчика, щелкните значок лупы.</span><span class="sxs-lookup"><span data-stu-id="4b199-126">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="4b199-127">В отладчике [!INCLUDE[tsql](../../includes/tsql-md.md)] откроется диалоговое окно, в котором данные будут отображены в формате, соответствующем типу этих данных.</span><span class="sxs-lookup"><span data-stu-id="4b199-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="4b199-128">**Тип**</span><span class="sxs-lookup"><span data-stu-id="4b199-128">**Type**</span></span>  
 <span data-ttu-id="4b199-129">Отображает тип данных выражения.</span><span class="sxs-lookup"><span data-stu-id="4b199-129">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b199-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b199-130">See Also</span></span>  
 <span data-ttu-id="4b199-131">[Отладчик Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="4b199-131">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="4b199-132">[Сведения отладчика Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="4b199-132">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="4b199-133">[окно локальных переменных](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="4b199-133">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="4b199-134">[Окно стека вызовов](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="4b199-134">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="4b199-135">[Диалоговое окно «Быстрая проверка»](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="4b199-135">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="4b199-136">Выражения (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4b199-136">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
