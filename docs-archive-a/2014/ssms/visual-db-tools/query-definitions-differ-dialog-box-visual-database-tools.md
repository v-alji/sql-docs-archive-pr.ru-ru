---
title: Диалоговое окно "Определения запроса различаются" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69639
- vdtsql.chm:69640
- vdt.dlgbox.querydefinitionsdiffer
ms.assetid: 90383473-2922-40e5-9682-3850849aa856
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9a39d5d6b739fa4ab1a96ea95b513ecb7f6682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735821"
---
# <a name="query-definitions-differ-dialog-box-visual-database-tools"></a><span data-ttu-id="12b58-102">Диалоговое окно «Определения запроса различаются» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="12b58-102">Query Definitions Differ Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="12b58-103">Это диалоговое окно уведомляет о том, что данный запрос не может быть графически представлен на панелях «Диаграмма» и «Критерии» и его можно редактировать только на панели SQL.</span><span class="sxs-lookup"><span data-stu-id="12b58-103">This dialog box notifies you that your query cannot be represented graphically in the Diagram and Criteria panes, and that you can edit your query only in the SQL pane.</span></span>  
  
 <span data-ttu-id="12b58-104">Это диалоговое окно может появляться при вводе или редактировании инструкции SQL на панели SQL, при переходе на другую панель, при подтверждении запроса или при попытке выполнить запрос в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="12b58-104">This dialog box may appear when you enter or edit an SQL statement in the SQL pane; you then move to another pane, verify the query, or attempt to execute the query; and one of the following conditions applies:</span></span>  
  
-   <span data-ttu-id="12b58-105">Инструкция SQL неполная или содержит одну или несколько синтаксических ошибок.</span><span class="sxs-lookup"><span data-stu-id="12b58-105">The SQL statement is incomplete or contains one or more syntax errors.</span></span>  
  
-   <span data-ttu-id="12b58-106">Инструкция SQL допустима, но не поддерживается в графических панелях (например запрос объединения).</span><span class="sxs-lookup"><span data-stu-id="12b58-106">The SQL statement is valid but is not supported in the graphical panes (for example, a Union query).</span></span>  
  
-   <span data-ttu-id="12b58-107">Инструкция SQL допустима, но содержит синтаксические выражения, применимые только к используемому подключению к данным.</span><span class="sxs-lookup"><span data-stu-id="12b58-107">The SQL statement is valid but contains syntax specific to the data connection you are using.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="12b58-108">Проверить допустимость инструкции можно с помощью кнопки **Проверить инструкцию SQL** на панели инструментов **Запрос** .</span><span class="sxs-lookup"><span data-stu-id="12b58-108">You can check whether a statement is valid using the **Verify SQL Statement** button on the **Query** toolbar.</span></span>  
  
 <span data-ttu-id="12b58-109">Диалоговое окно выводит сообщение о том, что инструкция SQL не может быть представлена и запрашивает о дальнейших действиях.</span><span class="sxs-lookup"><span data-stu-id="12b58-109">The dialog box displays a message with the reason that the SQL statement cannot be represented, and then asks how you want to proceed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12b58-110">Диалоговое окно **Определения запроса различаются** не появляется, если скрыты панели "Диаграмма" и "Критерии".</span><span class="sxs-lookup"><span data-stu-id="12b58-110">The **Query Definitions Differ** dialog box does not appear if you have hidden the Diagram and Criteria panes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="12b58-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="12b58-111">Options</span></span>  
 <span data-ttu-id="12b58-112">**Кнопка «Пропустить»**</span><span class="sxs-lookup"><span data-stu-id="12b58-112">**Ignore Button**</span></span>  
 <span data-ttu-id="12b58-113">Нажмите эту кнопку, чтобы указать, что нужно принять инструкцию SQL, редактировать ее дальше или выполнить ее.</span><span class="sxs-lookup"><span data-stu-id="12b58-113">Choose this button to specify that you want to accept the SQL statement, either to edit it further or to execute it.</span></span> <span data-ttu-id="12b58-114">Если инструкция принимается, панели «Диаграмма» и «Критерии» становятся недоступными для выбора, указывая на то, что их представление не соответствует инструкции в области SQL.</span><span class="sxs-lookup"><span data-stu-id="12b58-114">If you accept the statement, the Diagram and Criteria panes appear dimmed to indicate that they do not represent the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="12b58-115">**Кнопка «Отмена»**</span><span class="sxs-lookup"><span data-stu-id="12b58-115">**Undo Button**</span></span>  
 <span data-ttu-id="12b58-116">Нажмите эту кнопку, чтобы отказаться от изменений, произведенных на панели SQL.</span><span class="sxs-lookup"><span data-stu-id="12b58-116">Choose this button to discard your changes to the SQL pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12b58-117">Если инструкция верна, но не поддерживается графически конструктором запросов и представлений, ее можно выполнить даже в том случае, если она не представлена на панелях «Диаграмма» и «Критерии».</span><span class="sxs-lookup"><span data-stu-id="12b58-117">If the statement is correct but not supported graphically by the Query and View Designer, you can execute it even though it cannot be represented in the Diagram and Criteria panes.</span></span> <span data-ttu-id="12b58-118">Например, если вводится запрос соединения, инструкция может быть выполнена, но не будет представлена на других панелях.</span><span class="sxs-lookup"><span data-stu-id="12b58-118">For example, if you enter a Union query, the statement can be executed but not represented in the other panes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b58-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="12b58-119">See Also</span></span>  
 [<span data-ttu-id="12b58-120">Инструменты конструктора запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="12b58-120">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
