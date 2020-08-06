---
title: Пошаговая отладка кода Transact-SQL
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, debugging code
- Transact-SQL debugger, step over
- Transact-SQL debugger, step out
- Transact-SQL debugger, step into
ms.assetid: e09079b8-c4c9-42b4-821b-4ce81a98a086
author: rothja
ms.author: jroth
ms.openlocfilehash: 48cb307130c65729640864a26bdf1dfaf344b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667021"
---
# <a name="step-through-transact-sql-code"></a><span data-ttu-id="cd564-102">Пошаговая отладка кода Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd564-102">Step Through Transact-SQL Code</span></span>
  <span data-ttu-id="cd564-103">Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] позволяет выбирать инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , которые будут выполняться в окне редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd564-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger enables you to control which [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are run in a [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span> <span data-ttu-id="cd564-104">Отладчик можно останавливать на отдельных инструкциях, а затем просматривать состояние элементов кода в этой точке.</span><span class="sxs-lookup"><span data-stu-id="cd564-104">You can pause the debugger on individual statements and then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="cd564-105">Точки останова</span><span class="sxs-lookup"><span data-stu-id="cd564-105">Breakpoints</span></span>  
 <span data-ttu-id="cd564-106">Точка останова указывает отладчику приостановку выполнения на определенной инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd564-106">A breakpoint signals the debugger to pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="cd564-107">Дополнительные сведения о точках останова см. в разделе «Использование точек останова Transact-SQL».</span><span class="sxs-lookup"><span data-stu-id="cd564-107">For more information about breakpoints, see Using Transact-SQL Breakpoints.</span></span>  
  
## <a name="controlling-statement-execution"></a><span data-ttu-id="cd564-108">Управление выполнением инструкций</span><span class="sxs-lookup"><span data-stu-id="cd564-108">Controlling Statement Execution</span></span>  
 <span data-ttu-id="cd564-109">В отладчике [!INCLUDE[tsql](../../includes/tsql-md.md)] можно указать следующие параметры для выполнения из текущей инструкции в коде [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd564-109">In the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can specify the following options for executing from the current statement in [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
-   <span data-ttu-id="cd564-110">Выполнить код до следующей точки останова.</span><span class="sxs-lookup"><span data-stu-id="cd564-110">Run to the next breakpoint.</span></span>  
  
-   <span data-ttu-id="cd564-111">Перейти в следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="cd564-111">Step into the next statement.</span></span>  
  
     <span data-ttu-id="cd564-112">Если следующая инструкция вызывает хранимую процедуру, функцию или триггер [!INCLUDE[tsql](../../includes/tsql-md.md)] , отладчик открывает новое окно редактора запросов, содержащее код этого модуля.</span><span class="sxs-lookup"><span data-stu-id="cd564-112">If the next statement invokes a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, function, or trigger, the debugger displays a new Query Editor window that contains the code of the module.</span></span> <span data-ttu-id="cd564-113">Это окно находится в режиме отладки, а выполнение приостанавливается на первой инструкции модуля.</span><span class="sxs-lookup"><span data-stu-id="cd564-113">The window is in debug mode, and execution pauses on the first statement in the module.</span></span> <span data-ttu-id="cd564-114">Затем можно просмотреть код модуля, например, установив точки останова или выполнив код пошагово.</span><span class="sxs-lookup"><span data-stu-id="cd564-114">You can then move through the module code, for example, by setting breakpoints or stepping through the code.</span></span>  
  
-   <span data-ttu-id="cd564-115">Перейти к следующей инструкции.</span><span class="sxs-lookup"><span data-stu-id="cd564-115">Step over the next statement.</span></span>  
  
     <span data-ttu-id="cd564-116">Выполняется следующая инструкция.</span><span class="sxs-lookup"><span data-stu-id="cd564-116">The next statement is executed.</span></span> <span data-ttu-id="cd564-117">Однако если эта инструкция вызывает хранимую процедуру, функцию или триггер, то код модуля выполняется полностью, а результаты возвращаются вызвавшему его коду.</span><span class="sxs-lookup"><span data-stu-id="cd564-117">However, if the statement invokes a stored procedure, function, or trigger, the module code runs until it finishes, and the results are returned to the calling code.</span></span> <span data-ttu-id="cd564-118">Если есть уверенность, что в хранимой процедуре ошибок нет, то ее можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="cd564-118">If you are sure there are no errors in a stored procedure, you can step over it.</span></span> <span data-ttu-id="cd564-119">Выполнение приостанавливается на инструкции, которая следует за вызовом хранимой процедуры, функции или триггера.</span><span class="sxs-lookup"><span data-stu-id="cd564-119">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="cd564-120">Выйти из хранимой процедуры, функции или триггера.</span><span class="sxs-lookup"><span data-stu-id="cd564-120">Step out of a stored procedure, function, or trigger.</span></span>  
  
     <span data-ttu-id="cd564-121">Выполнение приостанавливается на инструкции, которая следует за вызовом хранимой процедуры, функции или триггера.</span><span class="sxs-lookup"><span data-stu-id="cd564-121">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="cd564-122">Выполнить от текущего места до текущего места расположения указателя, пропускать все точки останова.</span><span class="sxs-lookup"><span data-stu-id="cd564-122">Run from the current location to the current location of the pointer, and ignore all breakpoints.</span></span>  
  
 <span data-ttu-id="cd564-123">В следующей таблице приведены различные способы управления выполнением инструкций в отладчике [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd564-123">The following table lists the various ways in which you can control how statements execute in the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span>  
  
|<span data-ttu-id="cd564-124">Действие</span><span class="sxs-lookup"><span data-stu-id="cd564-124">Action</span></span>|<span data-ttu-id="cd564-125">Процедура</span><span class="sxs-lookup"><span data-stu-id="cd564-125">Procedure</span></span>|  
|------------|---------------|  
|<span data-ttu-id="cd564-126">Выполнить все инструкции от текущей инструкции до следующей точки останова</span><span class="sxs-lookup"><span data-stu-id="cd564-126">Run all statements from the current statement to the next breakpoint</span></span>|<span data-ttu-id="cd564-127">В меню **Отладка** выберите команду **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="cd564-127">On the **Debug** menu, click **Continue**.</span></span><br /><br /> <span data-ttu-id="cd564-128">На панели инструментов " **Отладка** " нажмите кнопку **продолжить** .</span><span class="sxs-lookup"><span data-stu-id="cd564-128">On the **Debug** toolbar, click the **Continue** button.</span></span>|  
|<span data-ttu-id="cd564-129">Перейти в следующую инструкцию или модуль</span><span class="sxs-lookup"><span data-stu-id="cd564-129">Step into the next statement or module</span></span>|<span data-ttu-id="cd564-130">В меню **Отладка** выберите пункт **Шаг с заходом**.</span><span class="sxs-lookup"><span data-stu-id="cd564-130">On the **Debug** menu, click **Step Into**.</span></span><br /><br /> <span data-ttu-id="cd564-131">На панели инструментов **Отладка** нажмите кнопку **Шаг с заходом** .</span><span class="sxs-lookup"><span data-stu-id="cd564-131">On the **Debug** toolbar, click the **Step Into** button.</span></span><br /><br /> <span data-ttu-id="cd564-132">Нажмите клавишу F11.</span><span class="sxs-lookup"><span data-stu-id="cd564-132">Press F11.</span></span>|  
|<span data-ttu-id="cd564-133">Перейти через следующую инструкцию или модуль</span><span class="sxs-lookup"><span data-stu-id="cd564-133">Step over the next statement or module</span></span>|<span data-ttu-id="cd564-134">В меню **Отладка** выберите команду **Шаг с обходом**.</span><span class="sxs-lookup"><span data-stu-id="cd564-134">On the **Debug** menu, click **Step Over**.</span></span><br /><br /> <span data-ttu-id="cd564-135">На панели инструментов **Отладка** нажмите кнопку **Шаг с обходом** .</span><span class="sxs-lookup"><span data-stu-id="cd564-135">On the **Debug** toolbar, click the **Step Over** button.</span></span><br /><br /> <span data-ttu-id="cd564-136">Нажмите клавишу F10.</span><span class="sxs-lookup"><span data-stu-id="cd564-136">Press F10.</span></span>|  
|<span data-ttu-id="cd564-137">Выйти из модуля</span><span class="sxs-lookup"><span data-stu-id="cd564-137">Step out of a module</span></span>|<span data-ttu-id="cd564-138">В меню **Отладка** выберите пункт **Шаг с выходом**.</span><span class="sxs-lookup"><span data-stu-id="cd564-138">On the **Debug** menu, click **Step Out**.</span></span><br /><br /> <span data-ttu-id="cd564-139">На панели инструментов **Отладка** нажмите кнопку **Шаг с выходом** .</span><span class="sxs-lookup"><span data-stu-id="cd564-139">On the **Debug** toolbar, click the **Step Out** button.</span></span><br /><br /> <span data-ttu-id="cd564-140">Нажмите сочетание клавиш SHIFT+F11.</span><span class="sxs-lookup"><span data-stu-id="cd564-140">Press SHIFT+F11.</span></span>|  
|<span data-ttu-id="cd564-141">Выполнить до текущего положения курсора</span><span class="sxs-lookup"><span data-stu-id="cd564-141">Run to the current cursor location</span></span>|<span data-ttu-id="cd564-142">Щелкните правой кнопкой мыши в окне редактора запросов и выберите команду **Выполнить до курсора**.</span><span class="sxs-lookup"><span data-stu-id="cd564-142">Right-click in the Query Editor window, and then click **Run To Cursor**.</span></span><br /><br /> <span data-ttu-id="cd564-143">Нажмите сочетание клавиш CTRL+F10.</span><span class="sxs-lookup"><span data-stu-id="cd564-143">Press CTRL+F10.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd564-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd564-144">See Also</span></span>  
 [<span data-ttu-id="cd564-145">Сведения отладчика Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd564-145">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
