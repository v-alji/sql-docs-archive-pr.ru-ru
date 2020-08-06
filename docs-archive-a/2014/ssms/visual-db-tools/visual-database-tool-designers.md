---
title: Конструкторы визуальных инструментов для баз данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- data sources [SQL Server]
- View Designer
- Visual Database Tools [SQL Server]
- Database Diagram Designer
- Query Designer [SQL Server]
- design tools [Visual Database Tools]
- Table Designer
- Visual Database Tools [SQL Server], designers
- Properties window [Visual Database Tools]
ms.assetid: bd0ca68e-6f69-42dd-bcb5-ce511673769c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6a307a0a82aa02e7197189ca6cfc9ba70a3fea33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656137"
---
# <a name="visual-database-tool-designers"></a><span data-ttu-id="e1395-102">Конструкторы визуальных инструментов для баз данных</span><span class="sxs-lookup"><span data-stu-id="e1395-102">Visual Database Tool Designers</span></span>
  <span data-ttu-id="e1395-103">Визуальные инструменты для баз данных представляют собой сочетание средств проектирования, которые можно использовать для работы с источниками данных.</span><span class="sxs-lookup"><span data-stu-id="e1395-103">The Visual Database Tools are a combination of design tools you can use to work with a data source.</span></span> <span data-ttu-id="e1395-104">С их помощью можно создавать запросы, конструировать и менять структуру базы данных и обновлять данные.</span><span class="sxs-lookup"><span data-stu-id="e1395-104">You can use them to create queries, design or modify a database structure, or update data.</span></span> <span data-ttu-id="e1395-105">В число этих средств входят конструктор диаграмм баз данных, конструктор таблиц и конструктор запросов и представлений.</span><span class="sxs-lookup"><span data-stu-id="e1395-105">The tools are Database Diagram Designer, Table Designer, and Query and View Designer.</span></span>  
  
## <a name="properties-window"></a><span data-ttu-id="e1395-106">Окно «Свойства»</span><span class="sxs-lookup"><span data-stu-id="e1395-106">Properties Window</span></span>  
 <span data-ttu-id="e1395-107">Аналогичное окно доступно не только в визуальных инструментах для баз данных, но именно здесь можно вносить многие изменения.</span><span class="sxs-lookup"><span data-stu-id="e1395-107">The properties window is not specific to Visual Database Tools, but it is where many modifications can be made.</span></span> <span data-ttu-id="e1395-108">В этом окне показаны свойства текущего выбранного элемента (например, таблицы), которые можно изменять (все, начиная от имени свойства и заканчивая параметрами сортировки столбца).</span><span class="sxs-lookup"><span data-stu-id="e1395-108">It shows the properties for the item currently selected (like a table) and allows you to edit those properties (everything from the properties name to the collation of a column).</span></span> <span data-ttu-id="e1395-109">Некоторые свойства можно просматривать в окне «Свойства», но менять их нужно другими средствами.</span><span class="sxs-lookup"><span data-stu-id="e1395-109">Some properties can be seen in the properties window but must be modified in a different tool.</span></span>  
  
## <a name="database-diagram-designer"></a><span data-ttu-id="e1395-110">конструктор диаграмм баз данных</span><span class="sxs-lookup"><span data-stu-id="e1395-110">Database Diagram Designer</span></span>  
 <span data-ttu-id="e1395-111">Конструктор диаграмм баз данных открывает окно, где можно визуально создавать и изменять таблицы и связи в базе данных, а также просматривать их.</span><span class="sxs-lookup"><span data-stu-id="e1395-111">Database Diagram Designer provides a window where you can visually create, edit, and show the tables and relationships in a database.</span></span>  
  
 <span data-ttu-id="e1395-112">Чтобы открыть конструктор диаграмм баз данных, откройте уже существующую диаграмму или в обозревателе объектов щелкните правой кнопкой мыши узел "База данных" и в раскрывающемся списке выберите **Создать диаграмму базы данных** .</span><span class="sxs-lookup"><span data-stu-id="e1395-112">To display Database Diagram Designer, open an existing diagram or right-click the Database node in Object Explorer and choose **New Database Diagram** from the drop-down menu.</span></span>  
  
 <span data-ttu-id="e1395-113">После открытия конструктора в главном меню появится меню **Диаграмма базы данных** .</span><span class="sxs-lookup"><span data-stu-id="e1395-113">Once the designer is open, the **Database Diagram** menu appears in the main menu.</span></span> <span data-ttu-id="e1395-114">Это меню является точкой доступа к специальным возможностям конструктора.</span><span class="sxs-lookup"><span data-stu-id="e1395-114">This menu is the access point to the designer's special features.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1395-115">Конструктор работает с базами данных Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e1395-115">This designer works with Microsoft SQL Server databases.</span></span>  
>   
>  <span data-ttu-id="e1395-116">Данная версия визуальных инструментов для баз данных не поддерживает Microsoft SQL Server версии 7 и более ранние версии.</span><span class="sxs-lookup"><span data-stu-id="e1395-116">This version of Visual Database Tools does not support Microsoft SQL Server version 7 and earlier.</span></span>  
  
## <a name="table-designer"></a><span data-ttu-id="e1395-117">конструктор таблиц</span><span class="sxs-lookup"><span data-stu-id="e1395-117">Table Designer</span></span>  
 <span data-ttu-id="e1395-118">Конструктор таблиц — визуальное средство проектирования и визуализации отдельных таблиц базы данных Microsoft SQL Server, к которой подключен пользователь.</span><span class="sxs-lookup"><span data-stu-id="e1395-118">Table Designer is a visual tool allowing you to design and visualize a single table in a Microsoft SQL Server database to which you are connected.</span></span>  
  
 <span data-ttu-id="e1395-119">Окно конструктора делится на две панели.</span><span class="sxs-lookup"><span data-stu-id="e1395-119">Table Designer has two panes.</span></span> <span data-ttu-id="e1395-120">В верхней области показана таблица, в каждой строке которой описывается один столбец таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="e1395-120">The upper area shows a grid; each row of the grid describes one database column.</span></span> <span data-ttu-id="e1395-121">Для каждого столбца отображаются его главные атрибуты: имя столбца, тип данных и допустимость значения NULL.</span><span class="sxs-lookup"><span data-stu-id="e1395-121">For each database column, the grid displays its fundamental attributes: column name, data type, and nulls-allowed setting.</span></span>  
  
 <span data-ttu-id="e1395-122">В нижней области конструктора таблиц на вкладке «Свойства столбца» отображаются дополнительные атрибуты любого выбранного в верхней таблице столбца.</span><span class="sxs-lookup"><span data-stu-id="e1395-122">The lower area of Table Designer, the Column Properties tab, shows additional attributes for whichever column is highlighted in the upper area.</span></span>  
  
 <span data-ttu-id="e1395-123">Щелкнув правой кнопкой мыши в таблице конструктора можно получить доступ к диалоговым окнам, в которых можно создавать и менять связи, ограничения, индексы и ключи таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="e1395-123">From Table Designer, you can also right-click in the grid section to access dialog boxes through which you can create and modify relationships, constraints, indexes, and keys for the table.</span></span>  
  
 <span data-ttu-id="e1395-124">Чтобы открыть конструктор таблиц, откройте уже существующую таблицу или щелкните правой кнопкой мыши узел **Таблицы** в обозревателе объектов и в раскрывающемся списке выберите **Добавить новую таблицу** .</span><span class="sxs-lookup"><span data-stu-id="e1395-124">To display Table Designer, open an existing table, or right-click the **Tables** node in Object Explorer, and choose **Add New Table** from the drop-down menu.</span></span>  
  
 <span data-ttu-id="e1395-125">После открытия конструктора в главном меню появится меню «Конструктор таблиц».</span><span class="sxs-lookup"><span data-stu-id="e1395-125">Once the designer is open, the Table Designer menu appears in the main menu.</span></span> <span data-ttu-id="e1395-126">Это меню является точкой доступа к специальным возможностям конструктора.</span><span class="sxs-lookup"><span data-stu-id="e1395-126">This menu is the access point to the designer's special features.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1395-127">Конструктор работает с базами данных Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e1395-127">This designer works with Microsoft SQL Server databases.</span></span>  
>   
>  <span data-ttu-id="e1395-128">Данная версия визуальных инструментов для баз данных не поддерживает Microsoft SQL Server версии 7 и более ранние версии.</span><span class="sxs-lookup"><span data-stu-id="e1395-128">This version of Visual Database Tools does not support Microsoft SQL Server version 7 and earlier.</span></span>  
  
## <a name="query-and-view-designer"></a><span data-ttu-id="e1395-129">конструктор запросов и представлений</span><span class="sxs-lookup"><span data-stu-id="e1395-129">Query and View Designer</span></span>  
 <span data-ttu-id="e1395-130">Конструктор запросов и представлений фактически представляет собой два средства, работающих схожим образом.</span><span class="sxs-lookup"><span data-stu-id="e1395-130">Query and View designer is actually two tools that work in very similar ways.</span></span> <span data-ttu-id="e1395-131">К некоторым из их основных отличий относится следующее.</span><span class="sxs-lookup"><span data-stu-id="e1395-131">Some of the major differences are:</span></span>  
  
-   <span data-ttu-id="e1395-132">Представления сохраняются в базе данных, а запросы сохраняются в проекте базы данных среды Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e1395-132">Views are saved with the database while a query is saved with a Visual Studio database project.</span></span>  
  
-   <span data-ttu-id="e1395-133">Конструктор запросов работает практически с любыми источниками данных, а конструктор представлений поддерживает только SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e1395-133">Query Designer works with nearly any data source, where View Designer works only with SQL Server.</span></span>  
  
-   <span data-ttu-id="e1395-134">Конструктор запросов позволяет проектировать инструкции языка манипулирования данными SELECT, INSERT, UPDATE и DELETE, а представления могут содержать только инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="e1395-134">Query Designer allows you to design SELECT, INSERT, UPDATE and DELETE DML statements, while views can only contain SELECT statements.</span></span>  
  
### <a name="view-designer"></a><span data-ttu-id="e1395-135">Конструктор представлений</span><span class="sxs-lookup"><span data-stu-id="e1395-135">View Designer</span></span>  
 <span data-ttu-id="e1395-136">Конструктор представлений позволяет проектировать и наглядно отображать существующие представления или создавать новые в базе данных Microsoft SQL Server, к которой подключен пользователь.</span><span class="sxs-lookup"><span data-stu-id="e1395-136">View Designer allows you to design and visualize an existing view or create a new one in a Microsoft SQL Server database to which you are connected.</span></span>  
  
 <span data-ttu-id="e1395-137">Окно конструктора содержит четыре панели: панель диаграмм, панель критериев, панель «SQL» и панель результатов.</span><span class="sxs-lookup"><span data-stu-id="e1395-137">View Designer has four panes: the Diagram pane, the Criteria pane, the SQL pane, and the Results pane.</span></span> <span data-ttu-id="e1395-138">Дополнительные сведения о каждой из этих панелей см. в разделе [Инструменты конструктора запросов и представлений (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e1395-138">For more detailed information on each of these panes, see [Query and View Designer Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="e1395-139">Чтобы открыть конструктор представлений, откройте уже существующее представление или щелкните правой кнопкой мыши узел **Представление** в обозревателе объектов и в раскрывающемся списке выберите **Добавить новое представление**.</span><span class="sxs-lookup"><span data-stu-id="e1395-139">To display View Designer, open an existing view or right-click the **View** node in Object Explorer and choose **Add New View** from the drop-down menu.</span></span>  
  
 <span data-ttu-id="e1395-140">После открытия конструктора в главном меню появится меню **Конструктор запросов** .</span><span class="sxs-lookup"><span data-stu-id="e1395-140">Once the designer is open, the **Query Designer** menu appears in the main menu.</span></span> <span data-ttu-id="e1395-141">Это меню является точкой доступа к специальным возможностям конструктора.</span><span class="sxs-lookup"><span data-stu-id="e1395-141">This menu is the access point to the designer's special features.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1395-142">Конструктор работает с базами данных Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e1395-142">This designer works with Microsoft SQL Server databases.</span></span>  
>   
>  <span data-ttu-id="e1395-143">Данная версия визуальных инструментов для баз данных не поддерживает Microsoft SQL Server версии 7 и более ранние версии.</span><span class="sxs-lookup"><span data-stu-id="e1395-143">This version of Visual Database Tools does not support Microsoft SQL Server version 7 and earlier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1395-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1395-144">See Also</span></span>  
 <span data-ttu-id="e1395-145">[Проектирование диаграмм баз данных &#40;визуальных инструментов для баз данных&#41;](design-database-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e1395-145">[Design Database Diagrams &#40;Visual Database Tools&#41;](design-database-diagrams-visual-database-tools.md) </span></span>  
 <span data-ttu-id="e1395-146">[Разработка таблиц &#40;визуальных инструментов для баз данных&#41;](design-tables-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e1395-146">[Design Tables &#40;Visual Database Tools&#41;](design-tables-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e1395-147">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e1395-147">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
