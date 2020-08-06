---
title: Как конструктор запросов и представлений представляет объединения (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL pane [Visual Database Tools]
- joins [SQL Server], Query and View Designer
- Diagram pane [Visual Database Tools]
ms.assetid: 20a99dcb-83bd-4aa6-9139-92e2e5ba4887
author: stevestein
ms.author: sstein
ms.openlocfilehash: 55fdea533436f9fa7c2a902667b3166085c27e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665197"
---
# <a name="how-the-query-and-view-designer-represents-joins-visual-database-tools"></a><span data-ttu-id="00f0a-102">Как конструктор запросов и представлений представляет соединения (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="00f0a-102">How the Query and View Designer Represents Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="00f0a-103">При соединении таблиц [конструктор запросов и представлений](visual-database-tools.md) представляет соединение графически на [панели диаграммы](diagram-pane-visual-database-tools.md) и в виде синтаксиса языка SQL на [панели SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="00f0a-103">If tables are joined, the [Query and View Designer](visual-database-tools.md) represents the join graphically in the [Diagram pane](diagram-pane-visual-database-tools.md) and by using SQL syntax in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="diagram-pane"></a><span data-ttu-id="00f0a-104">панели диаграммы</span><span class="sxs-lookup"><span data-stu-id="00f0a-104">Diagram Pane</span></span>  
 <span data-ttu-id="00f0a-105">На панели диаграмм конструктор запросов и представлений отображает строку соединения данных столбцов, включенных в соединение.</span><span class="sxs-lookup"><span data-stu-id="00f0a-105">In the Diagram pane the Query and View Designer displays a join line between the data columns involved in the join.</span></span> <span data-ttu-id="00f0a-106">Конструктор запросов и представлений отображает одну строку соединения для каждого условия соединения.</span><span class="sxs-lookup"><span data-stu-id="00f0a-106">The Query and View Designer displays one join line for each join condition.</span></span> <span data-ttu-id="00f0a-107">Например, на следующей иллюстрации показана строка соединения для двух соединяемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="00f0a-107">For example, the following illustration shows a join line between two tables that are joined:</span></span>  
  
 <span data-ttu-id="00f0a-108">![Линия соединения показывает связь между двумя таблицами](../../database-engine/media//dv3wbig.gif "Линия соединения показывает связь между двумя таблицами")</span><span class="sxs-lookup"><span data-stu-id="00f0a-108">![Join line shows relationship between two tables](../../database-engine/media//dv3wbig.gif "Join line shows relationship between two tables")</span></span>  
  
 <span data-ttu-id="00f0a-109">Если таблицы соединяются с использованием более чем одного условия соединения, то в конструкторе запросов и представлений отображается несколько строк соединения, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="00f0a-109">If tables are joined using more than one join condition, the Query and View Designer displays multiple join lines, as in the following example:</span></span>  
  
 <span data-ttu-id="00f0a-110">![Таблицы, соединенные по нескольким условиям](../../database-engine/media//dv3w9n1.gif "Таблицы, соединенные по нескольким условиям")</span><span class="sxs-lookup"><span data-stu-id="00f0a-110">![Tables joined using more than one join condition](../../database-engine/media//dv3w9n1.gif "Tables joined using more than one join condition")</span></span>  
  
 <span data-ttu-id="00f0a-111">Если соединяемые столбцы данных не отображаются (например прямоугольник, представляющий таблицу или объект с табличной структурой, свернут, или в соединении содержится выражение), то строка соединения помещается в строку заголовка прямоугольника, представляющего таблицу или объект с табличной структурой.</span><span class="sxs-lookup"><span data-stu-id="00f0a-111">If the joined data columns are not displayed (for example, the rectangle representing the table or table-structured object is minimized or the join involves an expression), the Query and View Designer places the join line at the title bar of the rectangle representing the table or table-structured object.</span></span>  
  
 <span data-ttu-id="00f0a-112">Форма значка в середине строки соединения показывает, как соединяются таблицы или объекты с табличной структурой.</span><span class="sxs-lookup"><span data-stu-id="00f0a-112">The shape of the icon in the middle of the join line indicates how the tables or table-structured objects are joined.</span></span> <span data-ttu-id="00f0a-113">Если в предложении соединения используется оператор, отличный от оператора сравнения равно (=), то данный оператор отображается в значке строки соединения.</span><span class="sxs-lookup"><span data-stu-id="00f0a-113">If the join clause uses an operator other than equal (=), the operator appears in the join line icon.</span></span> <span data-ttu-id="00f0a-114">В следующей таблице перечислены значки, которые появляются в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="00f0a-114">The following table lists the icons that appear in the join line.</span></span>  
  
|<span data-ttu-id="00f0a-115">**Значок строки соединения**</span><span class="sxs-lookup"><span data-stu-id="00f0a-115">**Join line icon**</span></span>|<span data-ttu-id="00f0a-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="00f0a-116">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="00f0a-117">![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbih.gif "Значок визуальных инструментов для баз данных")</span><span class="sxs-lookup"><span data-stu-id="00f0a-117">![Visual Database Tools icon](../../database-engine/media//dv3wbih.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="00f0a-118">Внутреннее соединение (создается с использованием знака равенства)</span><span class="sxs-lookup"><span data-stu-id="00f0a-118">Inner join (created using an equal sign).</span></span>|  
|<span data-ttu-id="00f0a-119">![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbii.gif "Значок визуальных инструментов для баз данных")</span><span class="sxs-lookup"><span data-stu-id="00f0a-119">![Visual Database Tools icon](../../database-engine/media//dv3wbii.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="00f0a-120">Внутреннее соединение, основанное на операторе «больше».</span><span class="sxs-lookup"><span data-stu-id="00f0a-120">Inner join based on the "greater than" operator.</span></span>|  
|<span data-ttu-id="00f0a-121">![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbij.gif "Значок визуальных инструментов для баз данных")</span><span class="sxs-lookup"><span data-stu-id="00f0a-121">![Visual Database Tools icon](../../database-engine/media//dv3wbij.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="00f0a-122">Внешнее соединение, в котором участвуют все строки отображаемой слева таблицы, даже если они не имеют соответствий в связанной с ней таблице.</span><span class="sxs-lookup"><span data-stu-id="00f0a-122">Outer join in which all rows from the table represented on the left will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="00f0a-123">![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbik.gif "Значок визуальных инструментов для баз данных")</span><span class="sxs-lookup"><span data-stu-id="00f0a-123">![Visual Database Tools icon](../../database-engine/media//dv3wbik.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="00f0a-124">Внешнее соединение, в котором участвуют все строки отображаемой справа таблицы, даже если они не имеют соответствий в связанной с ней таблице.</span><span class="sxs-lookup"><span data-stu-id="00f0a-124">Outer join in which all rows from the table represented on the right will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="00f0a-125">![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbil.gif "Значок визуальных инструментов для баз данных")</span><span class="sxs-lookup"><span data-stu-id="00f0a-125">![Visual Database Tools icon](../../database-engine/media//dv3wbil.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="00f0a-126">Полное внешнее соединение, включающее все строки из соединяемых таблиц (даже те строки таблиц, для которых нет соответствующих строк в другой соединяемой таблице).</span><span class="sxs-lookup"><span data-stu-id="00f0a-126">Full outer join in which all rows from both tables will be included, even if they do not have matches in the related table.</span></span>|  
  
 <span data-ttu-id="00f0a-127">Символ в конце строки соединения указывает тип соединения.</span><span class="sxs-lookup"><span data-stu-id="00f0a-127">The symbols on the ends of the join line indicate the type of join.</span></span> <span data-ttu-id="00f0a-128">В следующей таблице перечислены типы соединений и значков, которые появляются в конце строки соединения.</span><span class="sxs-lookup"><span data-stu-id="00f0a-128">The following table lists the types of joins and the icons displayed on the ends of the join line.</span></span>  
  
|<span data-ttu-id="00f0a-129">**Значок в конце строки соединения**</span><span class="sxs-lookup"><span data-stu-id="00f0a-129">**Icon on ends of join line**</span></span>|<span data-ttu-id="00f0a-130">**Тип соединения**</span><span class="sxs-lookup"><span data-stu-id="00f0a-130">**Type of join**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="00f0a-131">![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbim.gif "Значок визуальных инструментов для баз данных")</span><span class="sxs-lookup"><span data-stu-id="00f0a-131">![Visual Database Tools icon](../../database-engine/media//dv3wbim.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="00f0a-132">Соединение «один к одному»</span><span class="sxs-lookup"><span data-stu-id="00f0a-132">One-to-one join.</span></span>|  
|<span data-ttu-id="00f0a-133">![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbin.gif "Значок визуальных инструментов для баз данных")</span><span class="sxs-lookup"><span data-stu-id="00f0a-133">![Visual Database Tools icon](../../database-engine/media//dv3wbin.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="00f0a-134">Соединение «один ко многим»</span><span class="sxs-lookup"><span data-stu-id="00f0a-134">One-to-many join.</span></span>|  
|<span data-ttu-id="00f0a-135">![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbio.gif "Значок визуальных инструментов для баз данных")</span><span class="sxs-lookup"><span data-stu-id="00f0a-135">![Visual Database Tools icon](../../database-engine/media//dv3wbio.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="00f0a-136">Конструктор запросов и представлений не может определить тип соединения.</span><span class="sxs-lookup"><span data-stu-id="00f0a-136">Query and View Designer cannot determine the join type.</span></span> <span data-ttu-id="00f0a-137">Такая ситуация часто возникает при создании соединения вручную.</span><span class="sxs-lookup"><span data-stu-id="00f0a-137">This situation occurs most often when you have created a join manually.</span></span>|  
  
## <a name="sql-pane"></a><span data-ttu-id="00f0a-138">панели SQL</span><span class="sxs-lookup"><span data-stu-id="00f0a-138">SQL Pane</span></span>  
 <span data-ttu-id="00f0a-139">В инструкции SQL соединение может быть выражено несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="00f0a-139">A join can be expressed in a number of ways in an SQL statement.</span></span> <span data-ttu-id="00f0a-140">Точный синтаксис зависит от используемой базы данных и от того, как определено соединение.</span><span class="sxs-lookup"><span data-stu-id="00f0a-140">The exact syntax depends on the database you are using and on how you have defined the join.</span></span>  
  
 <span data-ttu-id="00f0a-141">Параметры синтаксиса для соединения таблиц включают:</span><span class="sxs-lookup"><span data-stu-id="00f0a-141">Syntax options for joining tables include:</span></span>  
  
-   <span data-ttu-id="00f0a-142">**Квалификатор JOIN для предложения FROM**.</span><span class="sxs-lookup"><span data-stu-id="00f0a-142">**JOIN qualifier for the FROM clause**.</span></span>   <span data-ttu-id="00f0a-143">Ключевые слова INNER и OUTER определяют тип соединения.</span><span class="sxs-lookup"><span data-stu-id="00f0a-143">The keywords INNER and OUTER specify the join type.</span></span> <span data-ttu-id="00f0a-144">Такой синтаксис относится к стандарту ANSI SQL-92.</span><span class="sxs-lookup"><span data-stu-id="00f0a-144">This syntax is standard for ANSI 92 SQL.</span></span>  
  
     <span data-ttu-id="00f0a-145">Например, при соединении таблиц `publishers` и `pub_info` на основе столбца `pub_id` в каждой таблице результирующая инструкция SQL может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="00f0a-145">For example, if you join the `publishers` and `pub_info` tables based on the `pub_id` column in each table, the resulting SQL statement might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM publishers INNER JOIN pub_info ON  
       publishers.pub_id = pub_info.pub_id  
    ```  
  
     <span data-ttu-id="00f0a-146">При создании внешнего соединения вместо слова INNER появляются слова LEFT OUTER или RIGHT OUTER.</span><span class="sxs-lookup"><span data-stu-id="00f0a-146">If you create an outer join, the words LEFT OUTER or RIGHT OUTER appear in place of the word INNER.</span></span>  
  
-   <span data-ttu-id="00f0a-147">**Предложение WHERE сравнивает столбцы обеих таблиц**.</span><span class="sxs-lookup"><span data-stu-id="00f0a-147">**WHERE clause compares columns in both tables**.</span></span>   <span data-ttu-id="00f0a-148">Предложение WHERE появляется тогда, когда база данных не поддерживает синтаксис JOIN (или если WHERE введено вручную).</span><span class="sxs-lookup"><span data-stu-id="00f0a-148">A WHERE clause appears if the database does not support the JOIN syntax (or if you entered it yourself).</span></span> <span data-ttu-id="00f0a-149">Если используется предложение WHERE для создания соединения, то названия обеих таблиц появляются в предложении FROM.</span><span class="sxs-lookup"><span data-stu-id="00f0a-149">If the join is created in the WHERE clause, both table names appear in the FROM clause.</span></span>  
  
     <span data-ttu-id="00f0a-150">Например, следующая инструкция соединяет таблицы `publishers` и `pub_info` .</span><span class="sxs-lookup"><span data-stu-id="00f0a-150">For example, the following statement joins the `publishers` and `pub_info` tables.</span></span>  
  
    ```  
    SELECT *  
    FROM publishers, pub_info  
    WHERE publishers.pub_id = pub_info.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="00f0a-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="00f0a-151">See Also</span></span>  
 <span data-ttu-id="00f0a-152">[Запрос с помощью соединений &#40;визуальных инструментов для баз данных&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="00f0a-152">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="00f0a-153">Диалоговое окно "Соединение" (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="00f0a-153">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
