---
title: Создание запросов на удаление (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- row removal [SQL Server], Delete query
- Delete query
- queries [SQL Server], types
- removing rows
- removing data
- data deletions [SQL Server]
- deleting rows
- deleting data
ms.assetid: 0db3af43-1ec4-48c8-b769-2bb9c76d3434
author: stevestein
ms.author: sstein
ms.openlocfilehash: a76c3aaef623365e419f40f3058308f6217d75d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668546"
---
# <a name="create-delete-queries-visual-database-tools"></a><span data-ttu-id="a21b0-102">Создание запросов на удаление (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="a21b0-102">Create Delete Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="a21b0-103">С помощью запроса на удаление можно удалить все строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="a21b0-103">You can delete all rows in a table by using a Delete query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a21b0-104">При удалении всех строк из таблицы данные в ней очищаются, но сама таблица не удаляется.</span><span class="sxs-lookup"><span data-stu-id="a21b0-104">Deleting all rows from a table clears the data in the table but does not delete the table itself.</span></span> <span data-ttu-id="a21b0-105">Чтобы удалить таблицу из базы данных, щелкните правой кнопкой мыши в обозревателе объектов, а затем выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a21b0-105">To delete a table from a database, right-click the table in Object Explorer and click **Delete**.</span></span>  
  
 <span data-ttu-id="a21b0-106">При создании запроса на удаление панель критериев изменится, отображая параметры, доступные при удалении строк.</span><span class="sxs-lookup"><span data-stu-id="a21b0-106">When you create a Delete query, the Criteria pane changes to reflect the options available for deleting rows.</span></span> <span data-ttu-id="a21b0-107">Так как в запросе на удаление данные не отображаются, столбцы «Вывод», «Сортировать по», «Порядок сортировки» удаляются.</span><span class="sxs-lookup"><span data-stu-id="a21b0-107">Because you do not display data in a Delete query, the Output, Sort By, and Sort Order columns are removed.</span></span> <span data-ttu-id="a21b0-108">Кроме того, флажки напротив имен столбцов в прямоугольнике, представляющем таблицу или возвращающий табличное значение объект, удаляются, так как отдельные столбцы для удаления указать невозможно.</span><span class="sxs-lookup"><span data-stu-id="a21b0-108">In addition, the check boxes next to the column names in the rectangle representing the table or table-valued object are removed because you cannot specify individual columns to delete.</span></span>  
  
 <span data-ttu-id="a21b0-109">Если конструктор запросов и представлений не может удалить одну или более строк, ни одна из них не удаляется, а пользователь получает сообщение с уведомлением о строках, содержащих данные, которые невозможно удалить из базы.</span><span class="sxs-lookup"><span data-stu-id="a21b0-109">If the Query and View Designer can't delete one or more of the rows none of them will be deleted and you will receive a message telling you which row(s) contain information that can't be deleted from the database.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a21b0-110">Действие по выполнению запроса на удаление отменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="a21b0-110">You cannot undo the action of executing a Delete query.</span></span> <span data-ttu-id="a21b0-111">В качестве предупредительной меры перед выполнением запроса на удаление рекомендуется создать резервную копию данных.</span><span class="sxs-lookup"><span data-stu-id="a21b0-111">As a precaution, back up your data before executing a Delete query.</span></span>  
  
### <a name="to-create-a-delete-query"></a><span data-ttu-id="a21b0-112">Создание запроса на удаление</span><span class="sxs-lookup"><span data-stu-id="a21b0-112">To create a Delete query</span></span>  
  
1.  <span data-ttu-id="a21b0-113">Добавьте на панели диаграмм таблицу, в которой необходимо удалить строки.</span><span class="sxs-lookup"><span data-stu-id="a21b0-113">Add the table to delete rows from to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="a21b0-114">В меню **Конструктор запросов** наведите указатель на пункт **Тип изменения**, а затем выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a21b0-114">From the **Query Designer** menu, point to **Change Type**, and then click **Delete**.</span></span> <span data-ttu-id="a21b0-115">**Примечание** . Если на панели "Диаграмма" при запуске запроса на удаление отображается более одной таблицы, конструктор запросов и представлений отобразит [диалоговое окно "Удаление таблицы"](visual-database-tools.md) для запроса имени таблицы, из которой необходимо удалить строки.</span><span class="sxs-lookup"><span data-stu-id="a21b0-115">**Note** If more than one table is displayed in the Diagram pane when you start the Delete query, the Query and View Designer displays the [Delete Table Dialog Box](visual-database-tools.md) to prompt you for the name of the table to delete rows from.</span></span>  
  
 <span data-ttu-id="a21b0-116">При выполнении запроса на удаление в [панели результатов](results-pane-visual-database-tools.md)не выводятся никакие результаты.</span><span class="sxs-lookup"><span data-stu-id="a21b0-116">When you execute the Delete query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="a21b0-117">Вместо этого отображается сообщение о том, сколько строк было удалено.</span><span class="sxs-lookup"><span data-stu-id="a21b0-117">Instead, a message appears indicating how many rows were deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a21b0-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="a21b0-118">See Also</span></span>  
 <span data-ttu-id="a21b0-119">[Поддерживаемые типы запросов &#40;визуальных инструментов для баз данных&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a21b0-119">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a21b0-120">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="a21b0-120">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
