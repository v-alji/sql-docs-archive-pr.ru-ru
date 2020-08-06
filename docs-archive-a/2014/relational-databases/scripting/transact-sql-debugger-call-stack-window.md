---
title: Окно стека вызовов
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Call Stack Window [Transact-SQL]
ms.assetid: ddb0b19c-87cd-4883-bcb8-ec09ffb30369
author: rothja
ms.author: jroth
ms.openlocfilehash: b4b72e484ade696be81ebac8ea4eed9be295edf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667673"
---
# <a name="call-stack-window"></a><span data-ttu-id="7f3b4-102">Окно стека вызовов</span><span class="sxs-lookup"><span data-stu-id="7f3b4-102">Call Stack Window</span></span>
  <span data-ttu-id="7f3b4-103">В окне **Стек вызовов** отображаются модули в стеке вызова, а также типы данных и значения всех параметров, передаваемых в модули.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-103">The **Call Stack** window displays the modules on the call stack, and the data types and values of any parameters that are passed to the modules.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="7f3b4-104">включают в себя хранимые процедуры, функции и триггеры.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-104">modules include stored procedures, functions, and triggers.</span></span> <span data-ttu-id="7f3b4-105">Чтобы отобразить стек вызова, необходимо находиться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-105">To display the call stack, you must be in debug mode.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="7f3b4-106">Список задач</span><span class="sxs-lookup"><span data-stu-id="7f3b4-106">Task List</span></span>  
 <span data-ttu-id="7f3b4-107">**Доступ к окну «Стек вызовов»**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-107">**To access the Call Stack window**</span></span>  
  
-   <span data-ttu-id="7f3b4-108">В меню **Отладка** укажите **Окна**и выберите пункт **Стек вызовов**.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-108">On the **Debug** menu, click **Windows**, and then click **Call Stack**.</span></span>  
  
 <span data-ttu-id="7f3b4-109">**Изменение текущего кадра стека в стеке вызова**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-109">**To change the current Call Stack frame**</span></span>  
  
 <span data-ttu-id="7f3b4-110">Можно использовать любую из следующих процедур, чтобы сделать один из кадров стека текущим.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-110">You can use either of the following procedures to make a stack frame the current frame:</span></span>  
  
-   <span data-ttu-id="7f3b4-111">Щелкните правой кнопкой мыши кадр стека и выберите команду **Перейти к кадру**.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-111">Right-click the stack frame, and then click **Switch To Frame**.</span></span>  
  
-   <span data-ttu-id="7f3b4-112">Дважды щелкните кадр стека.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-112">Double-click the stack frame.</span></span>  
  
 <span data-ttu-id="7f3b4-113">**Просмотр источника кадра, отличного от текущего кадра**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-113">**To view the source of a frame other than the current frame**</span></span>  
  
-   <span data-ttu-id="7f3b4-114">Щелкните правой кнопкой мыши кадр стека и выберите команду **К исходному коду**.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-114">Right-click the stack frame, and then click **Go To Source Code**.</span></span>  
  
## <a name="stack-frames"></a><span data-ttu-id="7f3b4-115">Кадры стека</span><span class="sxs-lookup"><span data-stu-id="7f3b4-115">Stack Frames</span></span>  
 <span data-ttu-id="7f3b4-116">Каждая строка в окне **Стек вызовов** называется кадром стека и представляет либо вызов модуля из файла скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] , либо вызов одного модуля из другого модуля.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-116">Each row in the **Call Stack** window is called a stack frame and represents either a call from a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file to a module or a call from one module to another.</span></span> <span data-ttu-id="7f3b4-117">Нижний кадр стека на экране показывает ту строку в окне редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , в которой был сделан первый вызов в стеке.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-117">The bottom stack frame in the display indicates the line in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window that made the first call into the stack.</span></span> <span data-ttu-id="7f3b4-118">Верхняя строка указывает строку, на которой отладчик приостановил выполнение, и обозначается желтой стрелкой в левом поле окна.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-118">The top row indicates the line on which the debugger paused execution, and is identified by a yellow arrow in the left margin of the window.</span></span> <span data-ttu-id="7f3b4-119">Каждая промежуточная строка указывает модуль и номер строки исходного кода, в котором произошел вызов следующего, вышестоящего кадра стека.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-119">Each intermediate row indicates the module and the line number of the source code that called the next higher stack frame.</span></span>  
  
 <span data-ttu-id="7f3b4-120">Все выражения в окнах **Локальные значения**, **Контрольные значения**и **Быстрая проверка** вычисляются на основе текущего кадра стека.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-120">All expressions in the **Locals**, **Watch**, and **QuickWatch** windows are evaluated based on the current stack frame.</span></span> <span data-ttu-id="7f3b4-121">В окне «Редактор запросов» отображается код текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-121">The Query Editor window displays the code for the current frame.</span></span> <span data-ttu-id="7f3b4-122">По умолчанию текущим кадром стека является кадр, в котором отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] приостановил выполнение.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-122">By default, the current stack frame is the frame in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger paused execution.</span></span> <span data-ttu-id="7f3b4-123">После перехода от текущего кадра стека к другому кадру выражения в окнах **Локальные переменные**, **Контрольные значения**и **Быстрая проверка** повторно вычисляются в контексте нового кадра и в окне редактора запросов отображается исходный код нового кадра.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-123">When you change the current stack frame to another frame, the expressions in the **Locals**, **Watch**, and **QuickWatch** windows are reevaluated in the context of the new frame, and the source code of the new frame is displayed in the Query Editor window.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="7f3b4-124">Столбцы</span><span class="sxs-lookup"><span data-stu-id="7f3b4-124">Columns</span></span>  
 <span data-ttu-id="7f3b4-125">**Название**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-125">**Name**</span></span>  
 <span data-ttu-id="7f3b4-126">Отображается информация о модуле в стеке вызова.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-126">Displays information about a module on the call stack.</span></span>  
  
 <span data-ttu-id="7f3b4-127">В нижней строке в стеке вызова в поле **Имя** указано окно источника редактора запросов и номер строки первого вызова в стеке.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-127">For the bottom row in the call stack, **Name** lists the Query Editor source window and line number of the first call into the stack.</span></span> <span data-ttu-id="7f3b4-128">В других строках поле **Имя** имеет формат **Модуль(Экземпляр.База_данных)(Список_параметров) Номер_строки**.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-128">For the other rows, **Name** has the format **Module(Instance.Database)(ParmList) LineNumber**.</span></span>  
  
 <span data-ttu-id="7f3b4-129">**Модуль**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-129">**Module**</span></span>  
 <span data-ttu-id="7f3b4-130">Представляет собой имя хранимой процедуры, функции или хранимой процедуры, вызвавшей следующий кадр.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-130">Is the name of the stored procedure, function, or stored procedure that called to the next frame.</span></span>  
  
 <span data-ttu-id="7f3b4-131">**Экземпляр.База_данных**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-131">**Instance.Database**</span></span>  
 <span data-ttu-id="7f3b4-132">Указывает экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и базу данных, в которой содержится модуль.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-132">Is the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the database that is holding the module.</span></span>  
  
 <span data-ttu-id="7f3b4-133">**Список_параметров**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-133">**ParmList**</span></span>  
 <span data-ttu-id="7f3b4-134">Указывает тип данных, имя и значение каждого параметра, переданного во время вызова в модуль.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-134">Indicates the data type, name, and value for each parameter that is passed in during the call to the module.</span></span>  
  
 <span data-ttu-id="7f3b4-135">**LineNumber**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-135">**LineNumber**</span></span>  
 <span data-ttu-id="7f3b4-136">Для всех строк, кроме верхней строки, значение **Номер_строки** указывает, в какой строке модуля вызван этот кадр.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-136">For all rows except the top row, **LineNumber** indicates which line in the module called to the frame.</span></span> <span data-ttu-id="7f3b4-137">Для верхней строки значение **Номер_строки** указывает строку, которая в настоящее время находится в фокусе в отладчике.</span><span class="sxs-lookup"><span data-stu-id="7f3b4-137">For the top row, **LineNumber** indicates the line on which the debugger is currently focused.</span></span>  
  
 <span data-ttu-id="7f3b4-138">**Язык**</span><span class="sxs-lookup"><span data-stu-id="7f3b4-138">**Language**</span></span>  
 <span data-ttu-id="7f3b4-139">Для языка **отображается значение** Transact-SQL [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3b4-139">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f3b4-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f3b4-140">See Also</span></span>  
 <span data-ttu-id="7f3b4-141">[Отладчик Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="7f3b4-141">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="7f3b4-142">[Сведения отладчика Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="7f3b4-142">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 [<span data-ttu-id="7f3b4-143">Пошаговая отладка кода Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7f3b4-143">Step Through Transact-SQL Code</span></span>](step-through-transact-sql-code.md)  
