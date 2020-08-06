---
title: Соединение таблиц по нескольким столбцам (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiple column joins
- joins [SQL Server], multiple columns
ms.assetid: 56a158bc-a42a-4b78-baad-4721d2d22cd3
author: stevestein
ms.author: sstein
ms.openlocfilehash: dda52fe27b2034242c8cbf458dd010240c792146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664641"
---
# <a name="join-tables-on-multiple-columns-visual-database-tools"></a><span data-ttu-id="2de67-102">Соединение таблиц по нескольким столбцам (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="2de67-102">Join Tables on Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="2de67-103">Таблицы можно соединять по нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="2de67-103">You can join tables with multiple columns.</span></span> <span data-ttu-id="2de67-104">То есть можно создать запрос, который будет сопоставлять строки из двух таблиц, только если они удовлетворяют нескольким условиям.</span><span class="sxs-lookup"><span data-stu-id="2de67-104">That is, you can create a query that matches rows from the two tables only if they satisfy multiple conditions.</span></span> <span data-ttu-id="2de67-105">Если база данных содержит связь, которая сопоставляет несколько столбцов с внешними ключами в одной таблице первичному ключу из нескольких столбцов в другой, эту связь можно использовать для соединения по нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="2de67-105">If the database contains a relationship matching multiple foreign-key columns in one table to a multicolumn primary key in the other table, you can use this relationship to create a multicolumn join.</span></span> <span data-ttu-id="2de67-106">Дополнительные сведения см. в статье [Автоматическое соединение таблиц (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2de67-106">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="2de67-107">Даже если база данных не содержит связь с несколькими внешними ключами, соединение можно создать вручную.</span><span class="sxs-lookup"><span data-stu-id="2de67-107">Even if the database contains no multi-column foreign-key relationship, you can create the join manually.</span></span>  
  
### <a name="to-manually-create-a-multicolumn-join"></a><span data-ttu-id="2de67-108">Самостоятельное создание соединения по нескольким столбцам</span><span class="sxs-lookup"><span data-stu-id="2de67-108">To manually create a multicolumn join</span></span>  
  
1.  <span data-ttu-id="2de67-109">Добавьте на [панель диаграммы](diagram-pane-visual-database-tools.md) таблицы, которые нужно соединить.</span><span class="sxs-lookup"><span data-stu-id="2de67-109">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the tables you want to join.</span></span>  
  
2.  <span data-ttu-id="2de67-110">Перетащите имя первого столбца соединения из окна первой таблицы на соответствующий столбец в окне второй таблицы.</span><span class="sxs-lookup"><span data-stu-id="2de67-110">Drag the name of the first join column in the first table window and drop it onto the related column in the second table window.</span></span> <span data-ttu-id="2de67-111">Соединение нельзя основывать на столбцах типа text, ntext или image.</span><span class="sxs-lookup"><span data-stu-id="2de67-111">You cannot base a join on text, ntext, or image columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2de67-112">Обычно столбцы соединения должны быть одного типа данных (или совместимых типов).</span><span class="sxs-lookup"><span data-stu-id="2de67-112">In general, the join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="2de67-113">Например, если столбец соединения в первой таблице содержит дату, его нужно связать со столбцом второй таблицы, также содержащем дату.</span><span class="sxs-lookup"><span data-stu-id="2de67-113">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="2de67-114">С другой стороны, если первый столбец соединения содержит целые числа, связываемый с ним столбец также должен относиться к целочисленному типу данных, однако размер у него может быть другим.</span><span class="sxs-lookup"><span data-stu-id="2de67-114">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="2de67-115">Однако могут быть случаи, когда благодаря неявному преобразованию типов можно соединить внешне несовместимые столбцы.</span><span class="sxs-lookup"><span data-stu-id="2de67-115">However, there may be cases where implicit data type conversions can join seemingly incompatible columns will work.</span></span>  
    >   
    >  <span data-ttu-id="2de67-116">[Конструктор запросов и представлений](query-and-view-designer-tools-visual-database-tools.md) не будет проверять типы данных соединяемых столбцов, но при выполнении запроса база данных отобразит ошибку, если типы данных несовместимы.</span><span class="sxs-lookup"><span data-stu-id="2de67-116">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="2de67-117">Перетащите имя второго столбца соединения из окна первой таблицы на соответствующий столбец в окне второй таблицы.</span><span class="sxs-lookup"><span data-stu-id="2de67-117">Drag the name of the second join column in the first table window and drop it onto the related column in the second table window.</span></span>  
  
4.  <span data-ttu-id="2de67-118">Повторите шаг 3 для всех пар соединяемых столбцов в таблицах.</span><span class="sxs-lookup"><span data-stu-id="2de67-118">Repeat step 3 for each additional pair of join columns in the two tables.</span></span>  
  
5.  <span data-ttu-id="2de67-119">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="2de67-119">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de67-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="2de67-120">See Also</span></span>  
 [<span data-ttu-id="2de67-121">Запросы с соединениями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="2de67-121">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
