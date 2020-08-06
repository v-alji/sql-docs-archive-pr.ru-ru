---
title: окно локальных переменных
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Locals Window [Transact-SQL]
ms.assetid: 59bea640-7823-4b4d-832c-f384d83cca2f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f8f62eb69a50d7543af41dddb9c62c842d17151
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668221"
---
# <a name="locals-window"></a><span data-ttu-id="eb810-102">Окно локальных значений</span><span class="sxs-lookup"><span data-stu-id="eb810-102">Locals Window</span></span>
  <span data-ttu-id="eb810-103">В окне **Локальные переменные** отображаются сведения о локальных выражениях в текущей области отладчика [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb810-103">The **Locals** window displays information about the local expressions in the current scope of the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="eb810-104">Областью является текущий кадр стека вызова, выбранный в окне **Стек вызовов** .</span><span class="sxs-lookup"><span data-stu-id="eb810-104">The scope is set to the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="eb810-105">Чтобы иметь возможность просматривать локальные выражения, необходимо находиться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="eb810-105">You must be in debug mode to display the local expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="eb810-106">Список задач</span><span class="sxs-lookup"><span data-stu-id="eb810-106">Task List</span></span>  
 <span data-ttu-id="eb810-107">**Доступ к окну «Локальные переменные»**</span><span class="sxs-lookup"><span data-stu-id="eb810-107">**To access the Locals window**</span></span>  
  
-   <span data-ttu-id="eb810-108">В меню **Отладка** выберите пункт **Окна**, а затем пункт **Локальные переменные**.</span><span class="sxs-lookup"><span data-stu-id="eb810-108">On the **Debug** menu, click **Windows**, and then click **Locals**.</span></span>  
  
 <span data-ttu-id="eb810-109">**Изменение значения выражения**</span><span class="sxs-lookup"><span data-stu-id="eb810-109">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="eb810-110">Щелкните правой кнопкой мыши выражение и выберите команду **Изменить значение**.</span><span class="sxs-lookup"><span data-stu-id="eb810-110">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="eb810-111">Столбцы</span><span class="sxs-lookup"><span data-stu-id="eb810-111">Columns</span></span>  
 <span data-ttu-id="eb810-112">**Название**</span><span class="sxs-lookup"><span data-stu-id="eb810-112">**Name**</span></span>  
 <span data-ttu-id="eb810-113">Имя локального выражения.</span><span class="sxs-lookup"><span data-stu-id="eb810-113">Is the name of the local expression.</span></span> <span data-ttu-id="eb810-114">В отладчике [!INCLUDE[tsql](../../includes/tsql-md.md)] перечисляются переменные, параметры и системные функции, имена которых начинаются с @@.</span><span class="sxs-lookup"><span data-stu-id="eb810-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger lists variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="eb810-115">**Value**</span><span class="sxs-lookup"><span data-stu-id="eb810-115">**Value**</span></span>  
 <span data-ttu-id="eb810-116">Отображается значение, которое в настоящее время присвоено локальному выражению.</span><span class="sxs-lookup"><span data-stu-id="eb810-116">Displays the value that is currently assigned to the local expression.</span></span> <span data-ttu-id="eb810-117">Этот столбец остается пустым, если выражению не присвоено значение.</span><span class="sxs-lookup"><span data-stu-id="eb810-117">This column is blank when no value has been assigned to the expression.</span></span>  
  
 <span data-ttu-id="eb810-118">Если длина выражения больше ширины столбца **Значение** , полное значение отображается в подсказке при перемещении указателя на ячейку **Значение** для этого выражения.</span><span class="sxs-lookup"><span data-stu-id="eb810-118">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="eb810-119">Значок лупы в ячейке **Значение** указывает, что доступен визуализатор отладчика [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb810-119">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="eb810-120">В этом списке можно указать **Визуализатор текста**, **Визуализатор XML**или **Визуализатор HTML**.</span><span class="sxs-lookup"><span data-stu-id="eb810-120">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="eb810-121">Чтобы выполнить запуск визуализатора отладчика, щелкните значок лупы.</span><span class="sxs-lookup"><span data-stu-id="eb810-121">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="eb810-122">В отладчике [!INCLUDE[tsql](../../includes/tsql-md.md)] откроется диалоговое окно, в котором данные будут отображены в формате, соответствующем типу этих данных.</span><span class="sxs-lookup"><span data-stu-id="eb810-122">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="eb810-123">**Тип**</span><span class="sxs-lookup"><span data-stu-id="eb810-123">**Type**</span></span>  
 <span data-ttu-id="eb810-124">Отображает тип данных выражения.</span><span class="sxs-lookup"><span data-stu-id="eb810-124">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb810-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb810-125">See Also</span></span>  
 <span data-ttu-id="eb810-126">[Отладчик Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="eb810-126">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="eb810-127">[Сведения отладчика Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="eb810-127">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="eb810-128">[окно просмотра значений](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="eb810-128">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="eb810-129">[Окно стека вызовов](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="eb810-129">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="eb810-130">[Диалоговое окно «Быстрая проверка»](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="eb810-130">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="eb810-131">Выражения (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eb810-131">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
