---
title: Соединение таблиц вручную (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- manual joins [SQL Server]
- joins [SQL Server], manual
- joins [SQL Server], creating
ms.assetid: 9c785356-646b-4c87-82d4-25efd6051d9d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83f7615be3f5f18164dd3ca0f62ef6cbd9167be3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727762"
---
# <a name="join-tables-manually-visual-database-tools"></a><span data-ttu-id="46086-102">Соединение таблицы вручную (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="46086-102">Join Tables Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="46086-103">При добавлении двух (и более) таблиц к запросу [Конструктор запросов и представлений](visual-database-tools.md) пытается соединить таблицы, основываясь на общих данных или на сведениях о связи между этими таблицами, хранящихся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="46086-103">When you add two (or more) tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to join them based on common data or on information stored in the database about how tables are related.</span></span> <span data-ttu-id="46086-104">Дополнительные сведения см. в статье [Автоматическое соединение таблиц (визуальные инструменты для баз данных)](join-tables-automatically-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="46086-104">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span></span> <span data-ttu-id="46086-105">Однако если конструктор запросов и представлений не соединил таблицы автоматически или если нужно создать дополнительные условия соединения таблиц, можно соединить таблицы вручную.</span><span class="sxs-lookup"><span data-stu-id="46086-105">However, if the Query and View Designer has not joined the tables automatically, or if you want to create additional join conditions between tables, you can join tables manually.</span></span>  
  
 <span data-ttu-id="46086-106">Соединения можно создавать на основании сравнения двух любых столбцов, а не только столбцов, содержащих одинаковые данные.</span><span class="sxs-lookup"><span data-stu-id="46086-106">You can create joins based on comparisons between any two columns, not just columns that contain the same information.</span></span> <span data-ttu-id="46086-107">Например, если база данных содержит две таблицы, `titles` и `roysched`, можно сравнить значения в столбце `ytd_sales` таблицы `titles` со значениями в столбцах `lorange` и `hirange` в таблице `roysched` .</span><span class="sxs-lookup"><span data-stu-id="46086-107">For example, if your database contains two tables, `titles` and `roysched`, you can compare values in the `ytd_sales` column of the `titles` table against the `lorange` and `hirange` columns in the `roysched` table.</span></span> <span data-ttu-id="46086-108">Создание этого соединения позволит найти заголовки, для которых сведения о продажах за текущий год находятся в пределах между низким и высоким диапазоном лицензионных платежей.</span><span class="sxs-lookup"><span data-stu-id="46086-108">Creating this join would allow you to find titles for which the year-to-date sales falls between the low and high ranges for the royalty payments.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="46086-109">Соединения работают быстрее, если столбцы, входящие в условие соединения, были проиндексированы.</span><span class="sxs-lookup"><span data-stu-id="46086-109">Joins work fastest if the columns in the join condition have been indexed.</span></span> <span data-ttu-id="46086-110">В некоторых случаях соединение неиндексированных столбцов может привести к медленной работе запроса.</span><span class="sxs-lookup"><span data-stu-id="46086-110">In some cases, joining on unindexed columns can result in a slow query.</span></span>  
  
### <a name="to-manually-join-tables-or-table-structured-objects"></a><span data-ttu-id="46086-111">Соединение таблиц или табличных объектов вручную</span><span class="sxs-lookup"><span data-stu-id="46086-111">To manually join tables or table-structured objects</span></span>  
  
1.  <span data-ttu-id="46086-112">Добавьте на [панель диаграммы](diagram-pane-visual-database-tools.md) объекты, которые нужно соединить.</span><span class="sxs-lookup"><span data-stu-id="46086-112">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the objects you want to join.</span></span>  
  
2.  <span data-ttu-id="46086-113">Захватите имя соединяемого столбца первой таблицы или табличного объекта и перетащите его к соответствующему столбцу второй таблицы или табличного объекта.</span><span class="sxs-lookup"><span data-stu-id="46086-113">Drag the name of the join column in the first table or table-structured object and drop it onto the related column in the second table or table-structured object.</span></span> <span data-ttu-id="46086-114">Соединение не может быть основано на столбцах типа `text`, `ntext` или `mage`.</span><span class="sxs-lookup"><span data-stu-id="46086-114">You cannot base a join on `text`, `ntext`, or i`mage` columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="46086-115">Столбцы соединения должны иметь одинаковые (или совместимые) типы данных.</span><span class="sxs-lookup"><span data-stu-id="46086-115">The join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="46086-116">Например, если столбец соединения в первой таблице содержит дату, его нужно связать со столбцом второй таблицы, также содержащем дату.</span><span class="sxs-lookup"><span data-stu-id="46086-116">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="46086-117">С другой стороны, если первый столбец соединения содержит целые числа, связываемый с ним столбец также должен относиться к целочисленному типу данных, однако размер у него может быть другим.</span><span class="sxs-lookup"><span data-stu-id="46086-117">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="46086-118">Конструктор запросов и представлений не будет проверять типы данных соединяемых столбцов, но при выполнении запроса база данных отобразит ошибку, если типы данных несовместимы.</span><span class="sxs-lookup"><span data-stu-id="46086-118">The Query and View Designer will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="46086-119">Если необходимо, измените оператор соединения; по умолчанию оператором является знак равенства (=).</span><span class="sxs-lookup"><span data-stu-id="46086-119">If necessary, change the join operator; by default, the operator is an equal sign (=).</span></span> <span data-ttu-id="46086-120">Дополнительные сведения см. в разделе [Изменение операторов соединения (визуальные инструменты для баз данных)](modify-join-operators-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="46086-120">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="46086-121">Конструктор запросов и представлений добавляет предложение INNER JOIN к инструкции SQL на [панели SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="46086-121">The Query and View Designer adds an INNER JOIN clause to the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="46086-122">Тип внешнего соединения можно изменить.</span><span class="sxs-lookup"><span data-stu-id="46086-122">You can change the type to an outer join.</span></span> <span data-ttu-id="46086-123">Дополнительные сведения см. в разделе [Создание внешних соединений (визуальные инструменты для баз данных)](create-outer-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="46086-123">For details see [Create Outer Joins &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46086-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="46086-124">See Also</span></span>  
 [<span data-ttu-id="46086-125">Запросы с соединениями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="46086-125">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
