---
title: Автоматическое соединение таблиц (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- joins [SQL Server], creating
- joins [SQL Server], automatic
ms.assetid: f152af82-bcb6-49ca-af19-48cdb7fc9ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: d05100f801d972759c1b5c105814f5cdbdccf84f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727761"
---
# <a name="join-tables-automatically-visual-database-tools"></a><span data-ttu-id="3be28-102">Автоматическое соединение таблиц (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="3be28-102">Join Tables Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="3be28-103">При добавлении двух или более таблиц в запрос [конструктор запросов и представлений](visual-database-tools.md) пытается определить, имеется ли между ними связь.</span><span class="sxs-lookup"><span data-stu-id="3be28-103">When you add two or more tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to determine if they are related.</span></span> <span data-ttu-id="3be28-104">Если это так, конструктор запросов и представлений автоматически помещает строки соединения между прямоугольниками, представляющими таблицы или объекты, структурированные в виде таблиц.</span><span class="sxs-lookup"><span data-stu-id="3be28-104">If they are, the Query and View Designer automatically puts join lines between the rectangles representing the tables or table-structured objects.</span></span>  
  
 <span data-ttu-id="3be28-105">Конструктор запросов и представлений определяет таблицы как соединенные, если:</span><span class="sxs-lookup"><span data-stu-id="3be28-105">The Query and View Designer will recognize tables as joined if:</span></span>  
  
-   <span data-ttu-id="3be28-106">В базе данных содержатся сведения, указывающая на связь между таблицами.</span><span class="sxs-lookup"><span data-stu-id="3be28-106">The database contains information that specifies that the tables are related.</span></span>  
  
-   <span data-ttu-id="3be28-107">Два столбца, по одному в каждой таблице, имеют одинаковые имена и принадлежат к одному и тому же типу данных.</span><span class="sxs-lookup"><span data-stu-id="3be28-107">If two columns, one in each table, have the same name and data type.</span></span> <span data-ttu-id="3be28-108">Такой столбец по крайней мере в одной таблице должен быть первичным ключом.</span><span class="sxs-lookup"><span data-stu-id="3be28-108">The column must be a primary key in at least one of the tables.</span></span> <span data-ttu-id="3be28-109">Например, при добавлении таблиц `employee` и `jobs` , если столбец `job_id` является первичным ключом в таблице `jobs` и в каждой таблице есть столбец с именем `job_id` , конструктор запросов и представлений автоматически соединит таблицы.</span><span class="sxs-lookup"><span data-stu-id="3be28-109">For example, if you add `employee` and `jobs` tables, if the `job_id` column is the primary key in the `jobs` table, and if each table has a column called `job_id` with the same data type, the Query and View Designer will automatically join the tables.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3be28-110">Конструктор запросов и представлений создаст только одно соединение на основе столбцов с одинаковым именем и типом данных.</span><span class="sxs-lookup"><span data-stu-id="3be28-110">The Query and View Designer will create only one join based on columns with the same name and data type.</span></span> <span data-ttu-id="3be28-111">Если возможно более одного соединения, конструктор запросов и представлений остановит работу после создания соединения на основе первого найденного им набора совпадающих столбцов.</span><span class="sxs-lookup"><span data-stu-id="3be28-111">If more than one join is possible, the Query and View Designer stops after creating a join based on the first set of matching columns that it finds.</span></span>  
  
-   <span data-ttu-id="3be28-112">Конструктор запросов и представлений определяет, что условие поиска (предложение WHERE) является фактически условием соединения.</span><span class="sxs-lookup"><span data-stu-id="3be28-112">The Query and View Designer detects that a search condition (a WHERE clause) is actually a join condition.</span></span> <span data-ttu-id="3be28-113">Например, после добавления таблиц `employee` и `jobs`создается условие поиска одинакового значения в столбце `job_id` обеих таблиц.</span><span class="sxs-lookup"><span data-stu-id="3be28-113">For example, you might add the tables `employee` and `jobs`, then create a search condition that searches for the same value in the `job_id` column of both tables.</span></span> <span data-ttu-id="3be28-114">В таком случае конструктор запросов и представлений определяет, что результатом условия поиска является соединение, а затем создает условие соединения на основе условия поиска.</span><span class="sxs-lookup"><span data-stu-id="3be28-114">When you do, the Query and View Designer detects that the search condition results in a join, and then creates a join condition based on the search condition.</span></span>  
  
 <span data-ttu-id="3be28-115">Если конструктор запросов и представлений создаст соединение, не подходящее к конкретному запросу, это соединение можно изменить или удалить.</span><span class="sxs-lookup"><span data-stu-id="3be28-115">If the Query and View Designer has created a join that is not suitable to your query, you can modify the join or remove it.</span></span> <span data-ttu-id="3be28-116">Дополнительные сведения см. в разделах [Изменение операторов соединения (визуальные инструменты для баз данных)](modify-join-operators-visual-database-tools.md) и [Удаление соединений (визуальные инструменты для баз данных)](remove-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3be28-116">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md) and [Remove Joins &#40;Visual Database Tools&#41;](remove-joins-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="3be28-117">Если конструктор запросов и представлений не выполнит автоматическое соединение таблиц в запросе, такое соединение можно создать вручную.</span><span class="sxs-lookup"><span data-stu-id="3be28-117">If the Query and View Designer does not automatically join the tables in your query, you can create a join yourself.</span></span> <span data-ttu-id="3be28-118">Дополнительные сведения см. в статье [Соединение таблиц вручную (визуальные инструменты для баз данных)](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3be28-118">For details, see [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be28-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="3be28-119">See Also</span></span>  
 <span data-ttu-id="3be28-120">[Как конструктор запросов и представлений представляет объединения &#40;визуальных инструментов для баз данных&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3be28-120">[How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;](how-the-query-and-view-designer-represents-joins-visual-database-tools.md) </span></span>  
 <span data-ttu-id="3be28-121">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3be28-121">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3be28-122">Запросы с соединениями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="3be28-122">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
