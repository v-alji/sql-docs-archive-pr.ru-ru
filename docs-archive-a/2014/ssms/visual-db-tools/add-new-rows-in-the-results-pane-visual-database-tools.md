---
title: Добавление строк на панели результатов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- inserting rows
- Query Designer [SQL Server], Results pane
- Results pane
- adding rows
- row additions [SQL Server], Results pane
ms.assetid: 59891c84-3f54-4ab9-8b86-72c59627b480
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3137da106279e09305261c6c7cb7fd06d254b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657477"
---
# <a name="add-new-rows-in-the-results-pane-visual-database-tools"></a><span data-ttu-id="37fef-102">Добавление новых строк на панель результатов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="37fef-102">Add New Rows in the Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="37fef-103">Новые данные можно добавлять, вводя их или копируя из другой программы, например из блокнота или приложения Excel.</span><span class="sxs-lookup"><span data-stu-id="37fef-103">You can add new data either by typing it in or by pasting it from another program such as Notepad or Excel.</span></span> <span data-ttu-id="37fef-104">Чтобы можно было вставить строку, в ней должно быть ровно то же число столбцов тех же типов, что и в таблице, куда производится вставка.</span><span class="sxs-lookup"><span data-stu-id="37fef-104">A row to be pasted must have exactly the same number and types of columns as the table into which you are pasting.</span></span> <span data-ttu-id="37fef-105">За раз на панель результатов можно вставить несколько строк.</span><span class="sxs-lookup"><span data-stu-id="37fef-105">You can paste multiple rows into the Results pane at once.</span></span>  
  
 <span data-ttu-id="37fef-106">Сведения о вводе данных см. в разделе [Правила обновления результатов (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="37fef-106">For information about how to enter data see [Rules for Updating Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-add-a-new-data-row"></a><span data-ttu-id="37fef-107">Добавление новой строки данных</span><span class="sxs-lookup"><span data-stu-id="37fef-107">To add a new data row</span></span>  
  
1.  <span data-ttu-id="37fef-108">Перейдите в нижнюю часть панели результатов, где есть пустая строка, в которую можно добавить новые данные.</span><span class="sxs-lookup"><span data-stu-id="37fef-108">Navigate to the bottom of the Results pane, where a blank row is available for adding a new data row.</span></span>  
  
     <span data-ttu-id="37fef-109">Начальным значением всех столбцов будет *NULL*.</span><span class="sxs-lookup"><span data-stu-id="37fef-109">The initial values for all columns will be *NULL*.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="37fef-110">Чтобы перейти сразу к первой пустой строке, воспользуйтесь панелью навигации в нижней части области результатов.</span><span class="sxs-lookup"><span data-stu-id="37fef-110">To go directly to the first empty row use the navigation bar at the bottom of the Results pane.</span></span>  
  
2.  <span data-ttu-id="37fef-111">Если копируются строки из буфера обмена, выберите новую строку, нажав на кнопку слева от нее.</span><span class="sxs-lookup"><span data-stu-id="37fef-111">If you are pasting rows from the Clipboard, select the new row by clicking the button to its left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37fef-112">Если хотя бы одна вставляемая строка не может быть сохранена в базе данных, будет получено сообщение, в котором будет сказано, какие строки не удается сохранить.</span><span class="sxs-lookup"><span data-stu-id="37fef-112">If one or more of the rows you're pasting can't be committed to the database you will receive a message telling you which row(s) couldn't be committed.</span></span>  
  
3.  <span data-ttu-id="37fef-113">Введите данные в новую строку.</span><span class="sxs-lookup"><span data-stu-id="37fef-113">Enter the data for the new row.</span></span> <span data-ttu-id="37fef-114">При копировании выберите **Вставка** из меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="37fef-114">If you are pasting, choose **Paste** from the **Edit** menu.</span></span>  
  
4.  <span data-ttu-id="37fef-115">Дайте строке зафиксироваться в базе данных.</span><span class="sxs-lookup"><span data-stu-id="37fef-115">Leave that row to commit it to the database.</span></span>  
  
 <span data-ttu-id="37fef-116">Если при сохранении строки произойдет ошибка, конструктор запросов и представлений отобразит соответствующее сообщение, а затем осуществит возврат к редактируемой строке.</span><span class="sxs-lookup"><span data-stu-id="37fef-116">If an error occurs when you save the row the Query and View Designer displays a message and then returns you to the row you were editing.</span></span> <span data-ttu-id="37fef-117">Можно выполнить следующее.</span><span class="sxs-lookup"><span data-stu-id="37fef-117">You can then:</span></span>  
  
-   <span data-ttu-id="37fef-118">Решить проблему, отредактировав строку.</span><span class="sxs-lookup"><span data-stu-id="37fef-118">Resolve the error by making further edits in the row.</span></span>  
  
-   <span data-ttu-id="37fef-119">Отменить правку, нажав клавишу ESC.</span><span class="sxs-lookup"><span data-stu-id="37fef-119">Cancel the edit by pressing ESC.</span></span> <span data-ttu-id="37fef-120">При нажатии клавиши ESC, если курсор находится в изменяемой ячейке, изменения в этой ячейке будут отменены.</span><span class="sxs-lookup"><span data-stu-id="37fef-120">If you press ESC while in a cell that you changed, the changes for that cell are canceled.</span></span> <span data-ttu-id="37fef-121">При нажатии клавиши ESC, если курсор находится в неизменяемой ячейке, будут отменены изменения во всей строке.</span><span class="sxs-lookup"><span data-stu-id="37fef-121">If you press ESC while in a cell you have not changed, the changes for the entire row are canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37fef-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="37fef-122">See Also</span></span>  
 <span data-ttu-id="37fef-123">[Работа с данными в области результатов &#40;визуальных инструментов для баз данных&#41;](results-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="37fef-123">[Work with Data in the Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="37fef-124">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="37fef-124">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
