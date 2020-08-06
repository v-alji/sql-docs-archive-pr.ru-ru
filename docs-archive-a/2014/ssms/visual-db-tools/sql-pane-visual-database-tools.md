---
title: Панель SQL (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Query Designer [SQL Server], SQL pane
- View Designer, SQL pane
- SQL pane [Visual Database Tools]
ms.assetid: dbabab18-0614-415b-a2ef-9bcd0d320d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a87ec1d5517852fefb152e0ec7b3165fa32988b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727718"
---
# <a name="sql-pane-visual-database-tools"></a><span data-ttu-id="b72df-102">Панель SQL (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="b72df-102">SQL Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="b72df-103">Панель SQL можно использовать для создания собственных инструкций SQL; можно также создать инструкцию на панели критериев или панели диаграмм, и на панели SQL будут созданы инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="b72df-103">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="b72df-104">После того как запрос построен, панель SQL его автоматически обновляет и меняет его формат для удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="b72df-104">As you build your query, the SQL pane automatically updates and reformats for easy readability.</span></span>  
  
 <span data-ttu-id="b72df-105">Чтобы открыть панель SQL, сначала откройте конструктор запросов и представлений (с объектом базы данных, выбранным в обозревателе серверов в меню **База данных** , выберите пункт **Создать запрос**).</span><span class="sxs-lookup"><span data-stu-id="b72df-105">To open the SQL pane, first open Query and View Designer (with a database object selected in Server Explorer, from the **Database** menu, click **New Query**).</span></span> <span data-ttu-id="b72df-106">Затем в меню **Конструктор запросов** укажите пункт **Панель** и щелкните элемент **SQL**.</span><span class="sxs-lookup"><span data-stu-id="b72df-106">Then from the **Query Designer** menu point to **Pane** and click **SQL**.</span></span>  
  
 <span data-ttu-id="b72df-107">На панели SQL можно:</span><span class="sxs-lookup"><span data-stu-id="b72df-107">In the SQL pane you can:</span></span>  
  
-   <span data-ttu-id="b72df-108">создать новые запросы с помощью ввода инструкций SQL;</span><span class="sxs-lookup"><span data-stu-id="b72df-108">Create new queries by entering SQL statements.</span></span>  
  
-   <span data-ttu-id="b72df-109">изменить инструкцию SQL, созданную конструктором запросов и представлений, на основании собственных параметров на панелях диаграмм и критериев;</span><span class="sxs-lookup"><span data-stu-id="b72df-109">Modify the SQL statement created by the Query and View Designer based on settings you make in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="b72df-110">ввести инструкции, которые пользуются преимуществами функций, характерных для использующейся базы данных.</span><span class="sxs-lookup"><span data-stu-id="b72df-110">Enter statements that take advantage of features specific to the database you are using.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b72df-111">Убедитесь, что известны правила идентификации объектов в использующейся базе данных.</span><span class="sxs-lookup"><span data-stu-id="b72df-111">Be sure you know the rules for identifying database objects in the database you are using.</span></span> <span data-ttu-id="b72df-112">Подробные сведения см. в документации по системе управления базой данных.</span><span class="sxs-lookup"><span data-stu-id="b72df-112">For details, see the documentation for your database management system.</span></span>  
  
## <a name="statements-in-the-sql-pane"></a><span data-ttu-id="b72df-113">Инструкции на панели SQL</span><span class="sxs-lookup"><span data-stu-id="b72df-113">Statements in the SQL Pane</span></span>  
 <span data-ttu-id="b72df-114">Текущий запрос можно редактировать непосредственно на панели SQL.</span><span class="sxs-lookup"><span data-stu-id="b72df-114">You can edit the current query directly in the SQL pane.</span></span> <span data-ttu-id="b72df-115">При переходе на другую панель конструктор запросов и представлений автоматически форматирует инструкцию и затем изменяет панели диаграмм и критериев для соответствия этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="b72df-115">When you move to another pane, the Query and View Designer automatically formats your statement, and then changes the Diagram and Criteria panes to match your statement.</span></span>  
  
 <span data-ttu-id="b72df-116">Если инструкция не может быть представлена на панелях диаграмм и критериев, учитывая, что эти панели видимы, конструктор запросов и представлений выводит ошибку и предлагает два выхода:</span><span class="sxs-lookup"><span data-stu-id="b72df-116">If your statement cannot be represented in the Diagram and Criteria panes, and if those panes are visible, Query and View Designer displays an error and then offers you two choices:</span></span>  
  
-   <span data-ttu-id="b72df-117">не учитывать невозможность представления инструкции на панелях диаграмм и критериев;</span><span class="sxs-lookup"><span data-stu-id="b72df-117">Ignore that the statement can not be represented in the Diagram and Criteria panes.</span></span>  
  
-   <span data-ttu-id="b72df-118">отменить изменения, которые не могут быть представлены, и восстановить до недавней версии инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="b72df-118">Undo the change that can not be represented and revert to the most recent version of the SQL statement.</span></span>  
  
 <span data-ttu-id="b72df-119">Если не учитывается невозможность представления инструкции на панелях диаграмм и критериев, конструктор запросов и представлений затемняет другие панели, чтобы показать, что они больше не отражают содержимое панели SQL.</span><span class="sxs-lookup"><span data-stu-id="b72df-119">If you choose to ignore that the statement can not be represented in the Diagram and Criteria panes, the Query and View Designer dims the other panes to indicate that they no longer reflect the contents of the SQL pane.</span></span>  
  
 <span data-ttu-id="b72df-120">Можно продолжить изменение и выполнение инструкции, также как и других инструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="b72df-120">You can continue to edit the statement and execute it as you would any SQL statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b72df-121">Если была введена инструкция SQL, но потом были внесены изменения в запрос, с изменением панелей диаграмм и критериев, конструктор запросов и представлений перестроит и заново отобразит инструкцию SQL.</span><span class="sxs-lookup"><span data-stu-id="b72df-121">If you enter an SQL statement, but then make further changes to the query by changing the Diagram and Criteria panes, the Query and View Designer rebuilds and redisplays the SQL statement.</span></span> <span data-ttu-id="b72df-122">В некоторых случаях это приводит к тому, что инструкция SQL строится отлично от той, которая была введена изначально (хотя результат получится одинаковый).</span><span class="sxs-lookup"><span data-stu-id="b72df-122">In some cases, this action results in an SQL statement that is constructed differently from the one you originally entered (though it will always yield the same results).</span></span> <span data-ttu-id="b72df-123">Эта разница особенно возможна, если ведется работа с условиями поиска, содержащими несколько предложений, связанных AND и OR.</span><span class="sxs-lookup"><span data-stu-id="b72df-123">This difference is particularly likely when you are working with search conditions that involve several clauses linked with AND and OR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b72df-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="b72df-124">See Also</span></span>  
 <span data-ttu-id="b72df-125">[Создание запросов &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b72df-125">[Create Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="b72df-126">[Выполнение запросов &#40;визуальных инструментов для баз данных&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b72df-126">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="b72df-127">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b72df-127">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="b72df-128">[Панель диаграмм &#40;визуальные инструменты для баз данных&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b72df-128">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="b72df-129">[Панель критериев &#40;визуальных инструментов для баз данных&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b72df-129">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b72df-130">Панель результатов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="b72df-130">Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
