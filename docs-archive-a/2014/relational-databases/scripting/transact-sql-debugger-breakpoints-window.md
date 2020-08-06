---
title: Окно точек останова
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Breakpoints Window [Transact-SQL]
ms.assetid: bad88d10-fdd5-4d3d-b5ea-a4f063847485
author: rothja
ms.author: jroth
ms.openlocfilehash: 077d501e581ed5baaac45cc6bbbb34e0040730e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667012"
---
# <a name="breakpoints-window"></a><span data-ttu-id="0eea7-102">Окно точек останова</span><span class="sxs-lookup"><span data-stu-id="0eea7-102">Breakpoints Window</span></span>
  <span data-ttu-id="0eea7-103">В окне **Точки останова** перечисляются все точки останова, которые заданы в текущем редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0eea7-103">The **Breakpoints** window lists all the breakpoints that are set in the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="0eea7-104">Чтобы управлять точками останова, используйте панель инструментов в окне **Точки останова** .</span><span class="sxs-lookup"><span data-stu-id="0eea7-104">To manage the breakpoints, use the toolbar in the **Breakpoints** window.</span></span> <span data-ttu-id="0eea7-105">Точки останова представляют собой точки кода, где выполнение в режиме отладке приостанавливается, чтобы можно было просматривать отладочные данные.</span><span class="sxs-lookup"><span data-stu-id="0eea7-105">Breakpoints are locations in the code where execution pauses in debug mode so that you can view debugging data.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="0eea7-106">Список задач</span><span class="sxs-lookup"><span data-stu-id="0eea7-106">Task List</span></span>  
 <span data-ttu-id="0eea7-107">**Доступ к окну «Точки останова»**</span><span class="sxs-lookup"><span data-stu-id="0eea7-107">**To access the Breakpoints window**</span></span>  
  
-   <span data-ttu-id="0eea7-108">В меню **Отладка** выберите пункт **Окна**, а затем **Точки останова**.</span><span class="sxs-lookup"><span data-stu-id="0eea7-108">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
## <a name="breakpoints-window-columns"></a><span data-ttu-id="0eea7-109">Столбцы окна «Точки останова»</span><span class="sxs-lookup"><span data-stu-id="0eea7-109">Breakpoints Window Columns</span></span>  
 <span data-ttu-id="0eea7-110">По умолчанию в окне **Точки останова** перечислены следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="0eea7-110">By default, the **Breakpoints** window lists the following columns.</span></span>  
  
 <span data-ttu-id="0eea7-111">**Название**</span><span class="sxs-lookup"><span data-stu-id="0eea7-111">**Name**</span></span>  
 <span data-ttu-id="0eea7-112">Отображается имя точки останова.</span><span class="sxs-lookup"><span data-stu-id="0eea7-112">Displays the name of the breakpoint.</span></span> <span data-ttu-id="0eea7-113">Имена точек останова предоставляются отладчиком.</span><span class="sxs-lookup"><span data-stu-id="0eea7-113">Breakpoint names are provided by the debugger.</span></span> <span data-ttu-id="0eea7-114">Это имя включает имя окна редактора запросов компонента Database Engine, которое содержит точку останова, и номер строки в редакторе запросов, на которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="0eea7-114">This name includes the name of Database Engine Query Editor window that contains the breakpoint, and the line number in the Query Editor on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="0eea7-115">**Condition**</span><span class="sxs-lookup"><span data-stu-id="0eea7-115">**Condition**</span></span>  
 <span data-ttu-id="0eea7-116">Отображает **(нет условия)** .</span><span class="sxs-lookup"><span data-stu-id="0eea7-116">Displays **(no condition)**.</span></span> <span data-ttu-id="0eea7-117">Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] не поддерживает задание условий точки останова.</span><span class="sxs-lookup"><span data-stu-id="0eea7-117">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint conditions.</span></span>  
  
 <span data-ttu-id="0eea7-118">**Число попаданий**</span><span class="sxs-lookup"><span data-stu-id="0eea7-118">**Hit Count**</span></span>  
 <span data-ttu-id="0eea7-119">Отображает**всегда выполнять останов**.</span><span class="sxs-lookup"><span data-stu-id="0eea7-119">Displays**breaks always**.</span></span>  
  
 <span data-ttu-id="0eea7-120">Можно добавлять и удалять следующие столбцы, выбирая их в списке **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="0eea7-120">You can add and remove the following columns by selecting them on the **Columns** list.</span></span>  
  
 <span data-ttu-id="0eea7-121">**Filter**</span><span class="sxs-lookup"><span data-stu-id="0eea7-121">**Filter**</span></span>  
 <span data-ttu-id="0eea7-122">Отображает **(нет)** .</span><span class="sxs-lookup"><span data-stu-id="0eea7-122">Displays **(none)**.</span></span> <span data-ttu-id="0eea7-123">Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] не поддерживает задание фильтров для точек останова.</span><span class="sxs-lookup"><span data-stu-id="0eea7-123">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint filters.</span></span>  
  
 <span data-ttu-id="0eea7-124">**При попадании**</span><span class="sxs-lookup"><span data-stu-id="0eea7-124">**When Hit**</span></span>  
 <span data-ttu-id="0eea7-125">Отображает **Останов**.</span><span class="sxs-lookup"><span data-stu-id="0eea7-125">Displays **Break**.</span></span>  
  
 <span data-ttu-id="0eea7-126">**Язык**</span><span class="sxs-lookup"><span data-stu-id="0eea7-126">**Language**</span></span>  
 <span data-ttu-id="0eea7-127">Для языка **отображается значение** Transact-SQL [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0eea7-127">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0eea7-128">**Компонент**</span><span class="sxs-lookup"><span data-stu-id="0eea7-128">**Function**</span></span>  
 <span data-ttu-id="0eea7-129">Отображается номер строки, на которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="0eea7-129">Displays the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="0eea7-130">**Файл**</span><span class="sxs-lookup"><span data-stu-id="0eea7-130">**File**</span></span>  
 <span data-ttu-id="0eea7-131">Отображается имя исходного файла, который содержит точку останова, и номер строки, на которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="0eea7-131">Displays the name of the source file that contains the breakpoint, and the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="0eea7-132">**Адрес**</span><span class="sxs-lookup"><span data-stu-id="0eea7-132">**Address**</span></span>  
 <span data-ttu-id="0eea7-133">Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] не поддерживает эту функцию.</span><span class="sxs-lookup"><span data-stu-id="0eea7-133">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="0eea7-134">**Процесс**</span><span class="sxs-lookup"><span data-stu-id="0eea7-134">**Process**</span></span>  
 <span data-ttu-id="0eea7-135">Отображает **[SQL]** , указывая, что это — процесс компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0eea7-135">Displays **[SQL]** to indicate that this is a [!INCLUDE[ssDE](../../includes/ssde-md.md)] process.</span></span> <span data-ttu-id="0eea7-136">Затем следует имя экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , в котором выполняется код.</span><span class="sxs-lookup"><span data-stu-id="0eea7-136">This is followed by the name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the code executes.</span></span>  
  
## <a name="breakpoints-window-toolbar"></a><span data-ttu-id="0eea7-137">Панель инструментов окна «Точки останова»</span><span class="sxs-lookup"><span data-stu-id="0eea7-137">Breakpoints Window Toolbar</span></span>  
 <span data-ttu-id="0eea7-138">Если в текущем окне редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] имеются активные точки останова, то в окне **Точки останова** отображается панель инструментов, с помощью которой можно управлять точками останова.</span><span class="sxs-lookup"><span data-stu-id="0eea7-138">When the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window has active breakpoints, the **Breakpoints** window displays a toolbar that can be used to manage the breakpoints.</span></span>  
  
 <span data-ttu-id="0eea7-139">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="0eea7-139">**Delete**</span></span>  
 <span data-ttu-id="0eea7-140">Удаляет выбранную точку останова.</span><span class="sxs-lookup"><span data-stu-id="0eea7-140">Deletes the selected breakpoint.</span></span>  
  
 <span data-ttu-id="0eea7-141">**Удалить все точки останова**</span><span class="sxs-lookup"><span data-stu-id="0eea7-141">**Delete All Breakpoints**</span></span>  
 <span data-ttu-id="0eea7-142">Удаляет все точки останова, которые показаны в окне **Точки останова** .</span><span class="sxs-lookup"><span data-stu-id="0eea7-142">Deletes all breakpoints that are displayed in the **Breakpoints** window.</span></span>  
  
 <span data-ttu-id="0eea7-143">**Отключить все точки останова**</span><span class="sxs-lookup"><span data-stu-id="0eea7-143">**Disable All Breakpoints**</span></span>  
 <span data-ttu-id="0eea7-144">Отключает все точки останова, чтобы они больше не останавливали выполнение кода, но точки останова сохраняются.</span><span class="sxs-lookup"><span data-stu-id="0eea7-144">Disables all breakpoints so that they no longer stop code execution; however, the breakpoints remain.</span></span> <span data-ttu-id="0eea7-145">После отключения всех точек останова эта кнопка становится кнопкой **Включить все точки останова**.</span><span class="sxs-lookup"><span data-stu-id="0eea7-145">When all the breakpoints are disabled, this button becomes **Enable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="0eea7-146">**Включить все точки останова**</span><span class="sxs-lookup"><span data-stu-id="0eea7-146">**Enable All Breakpoints**</span></span>  
 <span data-ttu-id="0eea7-147">Включает все точки останова, чтобы они останавливали выполнение кода.</span><span class="sxs-lookup"><span data-stu-id="0eea7-147">Enables all breakpoints so that they stop code execution.</span></span> <span data-ttu-id="0eea7-148">После включения всех точек останова эта кнопка становится кнопкой **Отключить все точки останова**.</span><span class="sxs-lookup"><span data-stu-id="0eea7-148">When all breakpoints are enabled, this button becomes **Disable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="0eea7-149">**К исходному коду**</span><span class="sxs-lookup"><span data-stu-id="0eea7-149">**Go To Source Code**</span></span>  
 <span data-ttu-id="0eea7-150">Помещает курсор на строку в редакторе запросов, которая содержит выбранную точку останова.</span><span class="sxs-lookup"><span data-stu-id="0eea7-150">Positions the cursor on the line in the Query Editor that contains the selected breakpoint.</span></span>  
  
 <span data-ttu-id="0eea7-151">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="0eea7-151">**Columns**</span></span>  
 <span data-ttu-id="0eea7-152">Содержит список всех столбцов, которые могут быть показаны в окне **Точки останова** .</span><span class="sxs-lookup"><span data-stu-id="0eea7-152">Lists all the columns that can be displayed in the **Breakpoints** window.</span></span> <span data-ttu-id="0eea7-153">Флажками обозначены показанные столбцы.</span><span class="sxs-lookup"><span data-stu-id="0eea7-153">A check box indicates the columns that are displayed.</span></span> <span data-ttu-id="0eea7-154">Чтобы добавить или удалить столбец в окне **Точки останова** , выберите этот столбец в списке.</span><span class="sxs-lookup"><span data-stu-id="0eea7-154">To add or remove a column in the **Breakpoints** window, select the column on the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eea7-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="0eea7-155">See Also</span></span>  
 [<span data-ttu-id="0eea7-156">Отладчик Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0eea7-156">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
