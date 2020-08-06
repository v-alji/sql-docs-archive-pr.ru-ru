---
title: Окно "Список ошибок"
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- error list window
- SQL Server Management Studio [SQL Server], error list window
ms.assetid: fae6327d-e268-44ae-a474-4a8f8f843129
author: rothja
ms.author: jroth
ms.openlocfilehash: 00455c339344b7b38a48500c49d139aa52df6116
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668224"
---
# <a name="error-list-window-management-studio"></a><span data-ttu-id="d75ec-102">Окно «Список ошибок» (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d75ec-102">Error List Window (Management Studio)</span></span>
  <span data-ttu-id="d75ec-103">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Список ошибок**среды** отображает синтаксические и семантические ошибки, полученные из кода IntelliSense в редакторе запросов [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d75ec-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Error List** displays the syntax and semantic errors that are generated from the IntelliSense code in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="features-of-the-error-list"></a><span data-ttu-id="d75ec-104">Функции списка ошибок</span><span class="sxs-lookup"><span data-stu-id="d75ec-104">Features of the Error List</span></span>  
 <span data-ttu-id="d75ec-105">**Список ошибок** обеспечивает следующую функциональность.</span><span class="sxs-lookup"><span data-stu-id="d75ec-105">The **Error List** provides the following functionality:</span></span>  
  
-   <span data-ttu-id="d75ec-106">В процессе изменения скриптов **Список ошибок** отображает ошибки и предупреждения, формируемые технологией IntelliSense в редакторе запросов [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d75ec-106">As you edit scripts, the **Error List** displays the errors and warnings produced by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="d75ec-107">Можно дважды щелкнуть на любом сообщении об ошибке на вкладке для файла скрипта, который формирует ошибку, и перейти к месту нахождения ошибки.</span><span class="sxs-lookup"><span data-stu-id="d75ec-107">You can double-click any error message entry to focus on the tab for the script file that generated the error, and move to the error location.</span></span>  
  
-   <span data-ttu-id="d75ec-108">Можно фильтровать отображаемые элементы и столбцы данных, которые будут показаны в каждом элементе.</span><span class="sxs-lookup"><span data-stu-id="d75ec-108">You can filter which entries you want to display, and which columns of information you want appear for each entry.</span></span>  
  
-   <span data-ttu-id="d75ec-109">После устранения ошибки ошибочный элемент удаляется из **Списка ошибок**.</span><span class="sxs-lookup"><span data-stu-id="d75ec-109">After you fix an error, the error entry is removed from the **Error List**.</span></span>  
  
-   <span data-ttu-id="d75ec-110">После того как вкладка для файла скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] будет закрыта, ошибки для этого файла удаляются из **Списка ошибок**.</span><span class="sxs-lookup"><span data-stu-id="d75ec-110">When you close the tab for a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file, the errors for that file are removed from the **Error List**.</span></span>  
  
## <a name="working-with-the-error-list"></a><span data-ttu-id="d75ec-111">Работа со списком ошибок</span><span class="sxs-lookup"><span data-stu-id="d75ec-111">Working with the Error List</span></span>  
 <span data-ttu-id="d75ec-112">Для показа **Списка ошибок**сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="d75ec-112">To display the **Error List**, do one of the following:</span></span>  
  
-   <span data-ttu-id="d75ec-113">В меню **Вид** выберите пункт **Список ошибок**.</span><span class="sxs-lookup"><span data-stu-id="d75ec-113">On the **View** menu, click **Error List**.</span></span>  
  
-   <span data-ttu-id="d75ec-114">Нажмите клавиши CTRL+\\, CTRL+E.</span><span class="sxs-lookup"><span data-stu-id="d75ec-114">Enter the keyboard shortcut CTRL+\\, CTRL+E.</span></span>  
  
 <span data-ttu-id="d75ec-115">Открыв **Список ошибок**, можно настроить представление, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d75ec-115">After you open the **Error List**, you can customize your view by performing the following actions:</span></span>  
  
-   <span data-ttu-id="d75ec-116">Для сортировки списка выберите любой заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="d75ec-116">To sort the list, click any column header.</span></span> <span data-ttu-id="d75ec-117">Для повторной сортировки по дополнительному столбцу нажмите и удерживайте клавишу SHIFT, а затем выберите другой заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="d75ec-117">To sort again by an additional column, press and hold the SHIFT key, and then click another column header.</span></span>  
  
-   <span data-ttu-id="d75ec-118">Чтобы выбрать отображаемые и скрываемые столбцы, выберите команду **Показать столбцы** из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="d75ec-118">To select which columns are displayed and which are hidden, select **Show Columns** from the shortcut menu.</span></span>  
  
-   <span data-ttu-id="d75ec-119">Чтобы изменить порядок, в котором отображаются столбцы, перетащите любой заголовок столбца влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="d75ec-119">To change the order in which columns are displayed, drag any column header to the left or right.</span></span>  
  
 <span data-ttu-id="d75ec-120">**Список ошибок** не содержит ссылок на дополнительные сведения о конкретных ошибках.</span><span class="sxs-lookup"><span data-stu-id="d75ec-120">The **Error List** does not link to additional information about specific errors.</span></span>  
  
## <a name="transact-sql-errors-in-management-studio"></a><span data-ttu-id="d75ec-121">Ошибки Transact-SQL в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="d75ec-121">Transact-SQL Errors in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="d75ec-122">отображает ошибки скриптов [!INCLUDE[tsql](../../includes/tsql-md.md)] в следующих местах.</span><span class="sxs-lookup"><span data-stu-id="d75ec-122">displays errors for [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in the following locations:</span></span>  
  
-   <span data-ttu-id="d75ec-123">**Список ошибок** отображает все синтаксические и семантические ошибки, обнаруженные технологией IntelliSense в редакторе [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d75ec-123">The **Error List** contains all syntax and semantic errors found by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor.</span></span> <span data-ttu-id="d75ec-124">Этот список ошибок динамически обновляется по мере изменения скриптов [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d75ec-124">This list of errors is dynamically updated as you edit [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="d75ec-125">В список входят все ошибки, обнаруженные редактором в каждом скрипте [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d75ec-125">The list includes all errors that the editor has found in each [!INCLUDE[tsql](../../includes/tsql-md.md)] script.</span></span> <span data-ttu-id="d75ec-126">Редактор не прекращает разбор файла после обнаружения ошибок в скрипте.</span><span class="sxs-lookup"><span data-stu-id="d75ec-126">The editor does not stop parsing a file after encountering errors in a script.</span></span> <span data-ttu-id="d75ec-127">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]технология IntelliSense в редакторе [!INCLUDE[ssDE](../../includes/ssde-md.md)] не поддерживает все синтаксические элементы [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d75ec-127">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="d75ec-128">**Список ошибок** содержит только ошибки синтаксиса [!INCLUDE[tsql](../../includes/tsql-md.md)] , поддерживаемого технологией IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="d75ec-128">The **Error List** contains only errors from the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax that is supported by IntelliSense.</span></span>  
  
-   <span data-ttu-id="d75ec-129">Вкладка **Сообщения** в нижней части окна редактора запросов [!INCLUDE[ssDE](../../includes/ssde-md.md)] отображает все ошибки и сообщения, возвращаемые компонентом [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] при выполнении скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d75ec-129">The **Messages** tab at the bottom of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window displays all errors and messages that are returned by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] when a [!INCLUDE[tsql](../../includes/tsql-md.md)] script is executed.</span></span> <span data-ttu-id="d75ec-130">Список не изменяется до тех пор, пока скрипт не будет выполнен повторно.</span><span class="sxs-lookup"><span data-stu-id="d75ec-130">This list does not change until you execute the script again.</span></span> <span data-ttu-id="d75ec-131">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] прекращает разбор пакета после того, как обнаруживает одну или две ошибки компиляции, поэтому на вкладке **Сообщения** могут быть перечислены не все ошибки в скрипте.</span><span class="sxs-lookup"><span data-stu-id="d75ec-131">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stops parsing a batch after it finds one or two compile errors; therefore, the **Messages** tab might not list all errors in a script.</span></span>  
  
 <span data-ttu-id="d75ec-132">Иногда ошибки приводятся в обоих местах.</span><span class="sxs-lookup"><span data-stu-id="d75ec-132">Sometimes errors are listed in both locations.</span></span> <span data-ttu-id="d75ec-133">Например, файл скрипта может содержать синтаксическую ошибку, которая приводится в **Списке ошибок**.</span><span class="sxs-lookup"><span data-stu-id="d75ec-133">For example, a script file might have a syntax error that is listed in the **Error List**.</span></span> <span data-ttu-id="d75ec-134">Если выполнить скрипт, прежде чем будет исправлена ошибка, средство синтаксического анализа компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] может обнаружить такое же состояние и показать такое же сообщение об ошибке на вкладке **Сообщения** .</span><span class="sxs-lookup"><span data-stu-id="d75ec-134">If you execute the script before you correct the error, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] parser can detect the same condition and return another copy of the error message in the **Messages** tab.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d75ec-135">**Список ошибок** содержит только ошибки из редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] . В него не включаются ошибки из редакторов многомерных выражений, расширений интеллектуального анализа данных и XML/A.</span><span class="sxs-lookup"><span data-stu-id="d75ec-135">The **Error List** only displays errors from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor; it does not display errors from the MDX, DMX, or XML/A Editors.</span></span> <span data-ttu-id="d75ec-136">Все ошибки многомерных выражений, расширений интеллектуального анализа данных и XML/A выводятся на вкладке **Сообщения** в соответствующих редакторах.</span><span class="sxs-lookup"><span data-stu-id="d75ec-136">All MDX, DMX, and XML/A errors are displayed in the **Messages** tab in those editors.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d75ec-137">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d75ec-137">UI element list</span></span>  
 <span data-ttu-id="d75ec-138">Если **Список ошибок** открыт, сведения отображаются в следующих столбцах.</span><span class="sxs-lookup"><span data-stu-id="d75ec-138">When the **Error List** is open, the information is displayed in the following columns:</span></span>  
  
 <span data-ttu-id="d75ec-139">**Порядок по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="d75ec-139">**Default Order**</span></span>  
 <span data-ttu-id="d75ec-140">Отображает целочисленное значение, которое указывает порядковый номер создания элемента.</span><span class="sxs-lookup"><span data-stu-id="d75ec-140">Displays an integer that indicates the order in which an entry was generated.</span></span>  
  
 <span data-ttu-id="d75ec-141">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d75ec-141">**Description**</span></span>  
 <span data-ttu-id="d75ec-142">Отображает текст элемента ошибки.</span><span class="sxs-lookup"><span data-stu-id="d75ec-142">Displays the text of the error entry.</span></span> <span data-ttu-id="d75ec-143">Длинные описания переносятся на дополнительные строки.</span><span class="sxs-lookup"><span data-stu-id="d75ec-143">Lengthy descriptions wrap onto additional lines.</span></span>  
  
 <span data-ttu-id="d75ec-144">**Файл**</span><span class="sxs-lookup"><span data-stu-id="d75ec-144">**File**</span></span>  
 <span data-ttu-id="d75ec-145">Отображает имя файла скрипта, сформировавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="d75ec-145">Displays the name of the script file that generated the error.</span></span>  
  
 <span data-ttu-id="d75ec-146">**Линия**</span><span class="sxs-lookup"><span data-stu-id="d75ec-146">**Line**</span></span>  
 <span data-ttu-id="d75ec-147">Отображает целочисленное значение, которое указывает строку кода, в котором содержится ошибка.</span><span class="sxs-lookup"><span data-stu-id="d75ec-147">Displays an integer that indicates which line of the code includes the error.</span></span>  
  
 <span data-ttu-id="d75ec-148">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d75ec-148">**Column**</span></span>  
 <span data-ttu-id="d75ec-149">Отображает целочисленное значение, которое указывает положение ошибки в строке кода.</span><span class="sxs-lookup"><span data-stu-id="d75ec-149">Displays an integer that indicates the position of the error in the line of code.</span></span>  
  
 <span data-ttu-id="d75ec-150">**Проект**</span><span class="sxs-lookup"><span data-stu-id="d75ec-150">**Project**</span></span>  
 <span data-ttu-id="d75ec-151">Отображает имя проекта, в который входит файл скрипта.</span><span class="sxs-lookup"><span data-stu-id="d75ec-151">Displays the name of the project that includes the script file.</span></span>  
