---
title: Открытие конструктора запросов и представлений (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- opening View Designer
- View Designer, opening
- Query Designer [SQL Server], opening
- opening Query Designer
ms.assetid: b473f258-d53c-41c0-9ad9-528a2ff141f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a36a0a9f014759269517a5774167f84c19b0b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664639"
---
# <a name="open-the-query-and-view-designer-visual-database-tools"></a><span data-ttu-id="8cf9f-102">Открытие конструктора запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="8cf9f-102">Open the Query and View Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="8cf9f-103">Конструктор запросов и представлений открывается при открытии определения представления, показе результатов запроса или представления, при создании или открытии запроса.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-103">The Query and View Designer opens when you open the definition of a view, show the results for a query or view, or create or open a query.</span></span> <span data-ttu-id="8cf9f-104">Он состоит из четырех отдельных панелей.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-104">It consists of four separate panes:</span></span>  
  
-   <span data-ttu-id="8cf9f-105">Панель диаграмм представляет в графическом виде таблицы или возвращающие табличное значение объекты, выбранные из подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-105">The Diagram pane presents a graphic display of the tables or table-valued objects you have selected from the data connection.</span></span> <span data-ttu-id="8cf9f-106">Отображаются также все связи соединений между ними.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-106">It also shows any join relationships among them.</span></span>  
  
-   <span data-ttu-id="8cf9f-107">Вводя значения в табличную сетку, на панели критериев можно указывать параметры запроса, например: какие из столбцов данных следует отображать, как упорядочивать результаты, какие строки выделить.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-107">The Criteria pane allows you to specify query options - such as which data columns to display, how to order the results, and what rows to select - by entering your choices into a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="8cf9f-108">Панель SQL можно использовать для создания собственных инструкций SQL; можно также создать инструкцию на панели критериев или панели диаграмм, и на панели SQL будут созданы инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-108">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="8cf9f-109">После построения запрос автоматически обновляется и переформатируется на панели SQL, становясь удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-109">As you build your query, the SQL pane automatically updates and reformats to be easily read.</span></span>  
  
-   <span data-ttu-id="8cf9f-110">Панель результатов показывает результаты выполнения самого последнего запроса Select</span><span class="sxs-lookup"><span data-stu-id="8cf9f-110">The Results pane shows the results of the most recently executed Select query.</span></span> <span data-ttu-id="8cf9f-111">(результаты запросов других типов отображаются в окнах сообщений).</span><span class="sxs-lookup"><span data-stu-id="8cf9f-111">(The results of other query types are displayed in message boxes.)</span></span>  
  
-   <span data-ttu-id="8cf9f-112">Эти панели полезны для работы с запросами и представлениями.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-112">These panes are useful for working with both queries and views.</span></span>  
  
-   <span data-ttu-id="8cf9f-113">При открытии представления или запроса одновременно открываются некоторые или все панели.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-113">When you open a view or query some or all of the panes open with it.</span></span> <span data-ttu-id="8cf9f-114">Какая именно панель открывается, зависит от настроек в диалоговом окне **Параметры** и от текущей системы управления базами данных.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-114">Which ones open depend on the settings in the **Options** dialog box and what database management system you're connected to.</span></span> <span data-ttu-id="8cf9f-115">По умолчанию, открываются все четыре панели.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-115">The default is that all four open.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-a-view"></a><span data-ttu-id="8cf9f-116">Открытие конструктора запросов и представлений для представления</span><span class="sxs-lookup"><span data-stu-id="8cf9f-116">To open the Query and View Designer for a view</span></span>  
  
1.  <span data-ttu-id="8cf9f-117">В обозревателе объектов щелкните правой кнопкой мыши нужное представление и выберите команду **Конструктор** или **Открыть представление**.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-117">In Object Explorer, right-click the view you want to open and click **Design** or **Open View**.</span></span>  
  
     <span data-ttu-id="8cf9f-118">При выборе команды **Конструктор**панели конструктора запросов и представлений открываются с учетом параметров, заданных в диалоговом окне **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="8cf9f-118">If you chose **Design**, the Query and View Designer panes open as dictated by the options selected in the **Options** dialog box.</span></span> <span data-ttu-id="8cf9f-119">При выборе пункта меню **Открыть представление**по умолчанию открывается только панель результатов.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-119">If you chose **Open View**, only the Results pane opens by default.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-an-existing-query"></a><span data-ttu-id="8cf9f-120">Открытие конструктора запросов и представлений для существующего запроса</span><span class="sxs-lookup"><span data-stu-id="8cf9f-120">To open the Query and View Designer for an existing query</span></span>  
  
1.  <span data-ttu-id="8cf9f-121">В обозревателе решений разверните папку **Запросы** .</span><span class="sxs-lookup"><span data-stu-id="8cf9f-121">In Solution Explorer, expand the **Queries** folder.</span></span>  
  
2.  <span data-ttu-id="8cf9f-122">Дважды щелкните мышью открываемый запрос.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-122">Double-click the query you want to open.</span></span>  
  
3.  <span data-ttu-id="8cf9f-123">Выделите инструкции запроса, щелкните правой кнопкой мыши выделенную область и выберите команду **Создать запрос в редакторе**.</span><span class="sxs-lookup"><span data-stu-id="8cf9f-123">Highlight the query statement(s), right-click the highlighted area and click **Design Query in Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf9f-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="8cf9f-124">See Also</span></span>  
 <span data-ttu-id="8cf9f-125">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8cf9f-125">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="8cf9f-126">Инструменты конструктора запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="8cf9f-126">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](query-and-view-designer-tools-visual-database-tools.md)  
  
  
