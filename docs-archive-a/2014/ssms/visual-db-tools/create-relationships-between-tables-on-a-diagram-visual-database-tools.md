---
title: Создание связей между таблицами на диаграмме (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- diagrams [SQL Server], designing
ms.assetid: 28e9630c-dff4-46cc-bb0e-fe77998b6ac2
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7d627a37f84dcb66b2129bb9c7dbc5890ccd46c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749576"
---
# <a name="create-relationships-between-tables-on-a-diagram-visual-database-tools"></a><span data-ttu-id="18ed4-102">Создание связи между таблицами на диаграмме (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="18ed4-102">Create Relationships Between Tables on a Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="18ed4-103">Можно создавать связи между столбцами разных таблиц в конструкторе диаграмм, перетаскивая столбцы между таблицами.</span><span class="sxs-lookup"><span data-stu-id="18ed4-103">You can create relationships between columns in different tables in the Diagram Designer by dragging columns between tables.</span></span>  
  
### <a name="to-create-a-relationship-graphically"></a><span data-ttu-id="18ed4-104">Графическое создание связи</span><span class="sxs-lookup"><span data-stu-id="18ed4-104">To create a relationship graphically</span></span>  
  
1.  <span data-ttu-id="18ed4-105">В конструкторе баз данных щелкните селектор строк для одного или более столбцов базы данных, которые необходимо связать со столбцом в другой таблице.</span><span class="sxs-lookup"><span data-stu-id="18ed4-105">In Database Designer, click the row selector for one or more database columns that you want to relate to a column in another table.</span></span>  
  
2.  <span data-ttu-id="18ed4-106">Перетащите выбранные столбцы в связанную таблицу.</span><span class="sxs-lookup"><span data-stu-id="18ed4-106">Drag the selected column(s) to the related table.</span></span>  
  
3.  <span data-ttu-id="18ed4-107">Отображаются два диалоговых окна: **Связь по внешнему ключу** и **Таблицы и столбцы**, второе отображается на переднем плане.</span><span class="sxs-lookup"><span data-stu-id="18ed4-107">Two dialog boxes appear: **Foreign Key Relationship** and **Tables and Columns**, with the latter appearing in the foreground.</span></span>  
  
4.  <span data-ttu-id="18ed4-108">**Имя связи** устанавливается системой в формате FK_*локальная_таблица*_\*таблица_внешнего_ключа\*.</span><span class="sxs-lookup"><span data-stu-id="18ed4-108">**Relationship name** has a system-provided name in the format FK_*localtable*_*foreigntable*.</span></span> <span data-ttu-id="18ed4-109">Можно изменить это значение.</span><span class="sxs-lookup"><span data-stu-id="18ed4-109">You may change this value.</span></span>  
  
5.  <span data-ttu-id="18ed4-110">Убедитесь, что **Таблица первичного ключа** правильно задает таблицу.</span><span class="sxs-lookup"><span data-stu-id="18ed4-110">Verify that **Primary key table** specifies the correct table.</span></span>  
  
6.  <span data-ttu-id="18ed4-111">Сетка содержит локальные столбцы и соответствующие им внешние столбцы.</span><span class="sxs-lookup"><span data-stu-id="18ed4-111">The grid lists the local columns and their matching foreign columns.</span></span> <span data-ttu-id="18ed4-112">Можно добавить или удалить столбцы таблицы, либо изменить сопоставления.</span><span class="sxs-lookup"><span data-stu-id="18ed4-112">You can add or remove table columns or change mappings.</span></span>  
  
7.  <span data-ttu-id="18ed4-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="18ed4-113">Choose **OK**.</span></span>  
  
     <span data-ttu-id="18ed4-114">Открывается диалоговое окно **Связь по внешнему ключу** .</span><span class="sxs-lookup"><span data-stu-id="18ed4-114">The **Foreign Key Relationship** dialog box appears.</span></span> <span data-ttu-id="18ed4-115">**Выбранная связь** отображает созданную связь.</span><span class="sxs-lookup"><span data-stu-id="18ed4-115">**Selected Relationship** shows the relationship you have created.</span></span>  
  
8.  <span data-ttu-id="18ed4-116">Измените свойства связи в сетке.</span><span class="sxs-lookup"><span data-stu-id="18ed4-116">Change properties for the relationship in the grid.</span></span>  
  
9. <span data-ttu-id="18ed4-117">Нажмите кнопку **OК** , чтобы создать связь.</span><span class="sxs-lookup"><span data-stu-id="18ed4-117">Choose **OK** to create the relationship.</span></span>  
  
     <span data-ttu-id="18ed4-118">Конструктор баз данных отображает связь между выбранными столбцами.</span><span class="sxs-lookup"><span data-stu-id="18ed4-118">Database Designer shows a relationship between the columns you chose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ed4-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="18ed4-119">See Also</span></span>  
 <span data-ttu-id="18ed4-120">[Диалоговое окно "таблицы и столбцы" &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="18ed4-120">[Tables and Columns Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="18ed4-121">[Ограничения UNIQUE и проверочные ограничения](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="18ed4-121">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="18ed4-122">Работа с таблицами в диаграммах базы данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="18ed4-122">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
