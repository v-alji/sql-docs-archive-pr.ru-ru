---
title: Иерархические данные (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [SQL Server], tables to support
- hierarchyid [Database Engine], concepts
- hierarchical tables [Database Engine]
- SqlHierarchyId
- hierarchyid [Database Engine]
- hierarchical queries [SQL Server], using hierarchyid data type
ms.assetid: 19aefa9a-fbc2-4b22-92cf-67b8bb01671c
author: rothja
ms.author: jroth
ms.openlocfilehash: 351a5a4aa6bc1655b8da5fced3e51385dd498bdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658713"
---
# <a name="hierarchical-data-sql-server"></a><span data-ttu-id="08a23-102">Иерархические данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08a23-102">Hierarchical Data (SQL Server)</span></span>
  <span data-ttu-id="08a23-103">Встроенный `hierarchyid` тип данных упрощает хранение и запрос иерархических данных.</span><span class="sxs-lookup"><span data-stu-id="08a23-103">The built-in `hierarchyid` data type makes it easier to store and query hierarchical data.</span></span> <span data-ttu-id="08a23-104">`hierarchyid`оптимизирован для представления деревьев, которые являются наиболее распространенным типом иерархических данных.</span><span class="sxs-lookup"><span data-stu-id="08a23-104">`hierarchyid` is optimized for representing trees, which are the most common type of hierarchical data.</span></span>  
  
 <span data-ttu-id="08a23-105">Иерархические данные представляют собой набор элементов данных, связанных между собой иерархическими связями.</span><span class="sxs-lookup"><span data-stu-id="08a23-105">Hierarchical data is defined as a set of data items that are related to each other by hierarchical relationships.</span></span> <span data-ttu-id="08a23-106">Иерархические связи — это связи, в которых один из элементов данных является родителем другого элемента.</span><span class="sxs-lookup"><span data-stu-id="08a23-106">Hierarchical relationships exist where one item of data is the parent of another item.</span></span> <span data-ttu-id="08a23-107">Примеры иерархических данных, которые обычно хранятся в базах данных, включают следующее.</span><span class="sxs-lookup"><span data-stu-id="08a23-107">Examples of the hierarchical data that is commonly stored in databases include the following:</span></span>  
  
-   <span data-ttu-id="08a23-108">Организационная структура</span><span class="sxs-lookup"><span data-stu-id="08a23-108">An organizational structure</span></span>  
  
-   <span data-ttu-id="08a23-109">Файловая система</span><span class="sxs-lookup"><span data-stu-id="08a23-109">A file system</span></span>  
  
-   <span data-ttu-id="08a23-110">группа задач в проекте;</span><span class="sxs-lookup"><span data-stu-id="08a23-110">A set of tasks in a project</span></span>  
  
-   <span data-ttu-id="08a23-111">Классификация языковых терминов</span><span class="sxs-lookup"><span data-stu-id="08a23-111">A taxonomy of language terms</span></span>  
  
-   <span data-ttu-id="08a23-112">Диаграмма связей между веб-страницами</span><span class="sxs-lookup"><span data-stu-id="08a23-112">A graph of links between Web pages</span></span>  
  
 <span data-ttu-id="08a23-113">Тип данных [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) используется для создания таблиц с иерархической структурой или для описания иерархической структуры данных, которые хранятся в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="08a23-113">Use [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) as a data type to create tables with a hierarchical structure, or to describe the hierarchical structure of data that is stored in another location.</span></span> <span data-ttu-id="08a23-114">Для запросов и управления иерархическими данными следует использовать [функции hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) в [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08a23-114">Use the [hierarchyid functions](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) in [!INCLUDE[tsql](../includes/tsql-md.md)] to query and manage hierarchical data.</span></span>  
  
##  <a name="key-properties-of-hierarchyid"></a><a name="keyprops"></a> <span data-ttu-id="08a23-115">Основные свойства типа hierarchyid</span><span class="sxs-lookup"><span data-stu-id="08a23-115">Key Properties of hierarchyid</span></span>  
 <span data-ttu-id="08a23-116">Значение типа данных `hierarchyid` представляет позицию в древовидной иерархии.</span><span class="sxs-lookup"><span data-stu-id="08a23-116">A value of the `hierarchyid` data type represents a position in a tree hierarchy.</span></span> <span data-ttu-id="08a23-117">Значения `hierarchyid` обладают следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="08a23-117">Values for `hierarchyid` have the following properties:</span></span>  
  
-   <span data-ttu-id="08a23-118">Исключительная компактность</span><span class="sxs-lookup"><span data-stu-id="08a23-118">Extremely compact</span></span>  
  
     <span data-ttu-id="08a23-119">Среднее число бит, необходимое для представления узла в древовидной структуре с *n* узлами, зависит от среднего количества потомков у узла.</span><span class="sxs-lookup"><span data-stu-id="08a23-119">The average number of bits that are required to represent a node in a tree with *n* nodes depends on the average fanout (the average number of children of a node).</span></span> <span data-ttu-id="08a23-120">Для структур с низкой степенью ветвления (0-7) объем занимаемой памяти равен примерно 6\*logA*n* бит, где A — среднее ветвление.</span><span class="sxs-lookup"><span data-stu-id="08a23-120">For small fanouts, (0-7) the size is about 6\*logA*n* bits, where A is the average fanout.</span></span> <span data-ttu-id="08a23-121">Для представления узла в иерархии организации, насчитывающей 100 000 человек со средним уровнем ветвления 6, необходимо около 38 бит.</span><span class="sxs-lookup"><span data-stu-id="08a23-121">A node in an organizational hierarchy of 100,000 people with an average fanout of 6 levels takes about 38 bits.</span></span> <span data-ttu-id="08a23-122">Эта величина округляется до 40 бит (5 байт), которые необходимы для хранения.</span><span class="sxs-lookup"><span data-stu-id="08a23-122">This is rounded up to 40 bits, or 5 bytes, for storage.</span></span>  
  
-   <span data-ttu-id="08a23-123">Сравнение проводится в порядке приоритета глубины</span><span class="sxs-lookup"><span data-stu-id="08a23-123">Comparison is in depth-first order</span></span>  
  
     <span data-ttu-id="08a23-124">Учитывая два `hierarchyid` значения **a** и **b**, **<b** означает, что перед b в первом прохождении дерева в глубину.</span><span class="sxs-lookup"><span data-stu-id="08a23-124">Given two `hierarchyid` values **a** and **b**, **a<b** means a comes before b in a depth-first traversal of the tree.</span></span> <span data-ttu-id="08a23-125">Индексы для типов данных `hierarchyid` располагаются в порядке приоритета глубины, и узлы, встречающиеся рядом при проходе по дереву с приоритетным направлением глубины, хранятся рядом друг с другом.</span><span class="sxs-lookup"><span data-stu-id="08a23-125">Indexes on `hierarchyid` data types are in depth-first order, and nodes close to each other in a depth-first traversal are stored near each other.</span></span> <span data-ttu-id="08a23-126">Например, потомки некоторой записи хранятся рядом с этой записью.</span><span class="sxs-lookup"><span data-stu-id="08a23-126">For example, the children of a record are stored adjacent to that record.</span></span>  
  
-   <span data-ttu-id="08a23-127">Поддержка произвольных вставок и удалений</span><span class="sxs-lookup"><span data-stu-id="08a23-127">Support for arbitrary insertions and deletions</span></span>  
  
     <span data-ttu-id="08a23-128">С помощью метода [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) можно в любой момент создать одноуровневый элемент, расположенный справа от заданного узла, слева от заданного узла или между любыми двумя другими одноуровневыми элементами.</span><span class="sxs-lookup"><span data-stu-id="08a23-128">By using the [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) method, it is always possible to generate a sibling to the right of any given node, to the left of any given node, or between any two siblings.</span></span> <span data-ttu-id="08a23-129">Свойство сравнения сохраняется, если произвольное число узлов вставляется в иерархию или удаляется из нее.</span><span class="sxs-lookup"><span data-stu-id="08a23-129">The comparison property is maintained when an arbitrary number of nodes is inserted or deleted from the hierarchy.</span></span> <span data-ttu-id="08a23-130">Большинство операций вставки и удаления сохраняют свойство компактности.</span><span class="sxs-lookup"><span data-stu-id="08a23-130">Most insertions and deletions preserve the compactness property.</span></span> <span data-ttu-id="08a23-131">Однако операции вставки между двумя узлами приводят к созданию значений hierarchyid, обладающих менее компактным представлением.</span><span class="sxs-lookup"><span data-stu-id="08a23-131">However, insertions between two nodes will produce hierarchyid values with a slightly less compact representation.</span></span>  
  
  
##  <a name="limitations-of-hierarchyid"></a><a name="limits"></a> <span data-ttu-id="08a23-132">Ограничения типа данных hierarchyid</span><span class="sxs-lookup"><span data-stu-id="08a23-132">Limitations of hierarchyid</span></span>  
 <span data-ttu-id="08a23-133">`hierarchyid`Тип данных имеет следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="08a23-133">The `hierarchyid` data type has the following limitations:</span></span>  
  
-   <span data-ttu-id="08a23-134">Столбец типа `hierarchyid` не принимает древовидную структуру автоматически.</span><span class="sxs-lookup"><span data-stu-id="08a23-134">A column of type `hierarchyid` does not automatically represent a tree.</span></span> <span data-ttu-id="08a23-135">Приложение должно создать и назначить значения `hierarchyid` таким образом, чтобы они отражали требуемые связи между строками.</span><span class="sxs-lookup"><span data-stu-id="08a23-135">It is up to the application to generate and assign `hierarchyid` values in such a way that the desired relationship between rows is reflected in the values.</span></span> <span data-ttu-id="08a23-136">Некоторые приложения могут содержать столбец типа `hierarchyid`, указывающий местоположение в иерархии, определенной в другой таблице.</span><span class="sxs-lookup"><span data-stu-id="08a23-136">Some applications might have a column of type `hierarchyid` that indicates the location in a hierarchy defined in another table.</span></span>  
  
-   <span data-ttu-id="08a23-137">Параллельными процессами создания и присвоения значений `hierarchyid` управляет само приложение.</span><span class="sxs-lookup"><span data-stu-id="08a23-137">It is up to the application to manage concurrency in generating and assigning `hierarchyid` values.</span></span> <span data-ttu-id="08a23-138">Нет никакой гарантии, что значения `hierarchyid` уникальны, если приложение не использует ограничение уникального ключа или не обеспечивает уникальность своей логикой.</span><span class="sxs-lookup"><span data-stu-id="08a23-138">There is no guarantee that `hierarchyid` values in a column are unique unless the application uses a unique key constraint or enforces uniqueness itself through its own logic.</span></span>  
  
-   <span data-ttu-id="08a23-139">Иерархические связи, представленные значениями типа `hierarchyid`, не обеспечиваются и не проверяются, как связи по внешнему ключу.</span><span class="sxs-lookup"><span data-stu-id="08a23-139">Hierarchical relationships represented by `hierarchyid` values are not enforced like a foreign key relationship.</span></span> <span data-ttu-id="08a23-140">Можно, а иногда и удобно иметь иерархическую связь, в которой у A есть потомок B и когда A удаляется, у B остается связь с несуществующей записью.</span><span class="sxs-lookup"><span data-stu-id="08a23-140">It is possible and sometimes appropriate to have a hierarchical relationship where A has a child B, and then A is deleted leaving B with a relationship to a nonexistent record.</span></span> <span data-ttu-id="08a23-141">Если это неприемлемо, приложение должно запросить потомков, прежде чем удалять родителей.</span><span class="sxs-lookup"><span data-stu-id="08a23-141">If this behavior is unacceptable, the application must query for descendants before deleting parents.</span></span>  
  
  
##  <a name="when-to-use-alternatives-to-hierarchyid"></a><a name="alternatives"></a> <span data-ttu-id="08a23-142">Использование других способов представления иерархических данных</span><span class="sxs-lookup"><span data-stu-id="08a23-142">When to Use Alternatives to hierarchyid</span></span>  
 <span data-ttu-id="08a23-143">Кроме типа `hierarchyid`, есть еще два способа представления иерархических данных:</span><span class="sxs-lookup"><span data-stu-id="08a23-143">Two alternatives to `hierarchyid` for representing hierarchical data are:</span></span>  
  
-   <span data-ttu-id="08a23-144">Родители-потомки</span><span class="sxs-lookup"><span data-stu-id="08a23-144">Parent/Child</span></span>  
  
-   <span data-ttu-id="08a23-145">XML</span><span class="sxs-lookup"><span data-stu-id="08a23-145">XML</span></span>  
  
 <span data-ttu-id="08a23-146">Использование типа `hierarchyid` дает больше возможностей.</span><span class="sxs-lookup"><span data-stu-id="08a23-146">`hierarchyid` is generally superior to these alternatives.</span></span> <span data-ttu-id="08a23-147">Однако есть ситуации (см. ниже), когда другие методы более эффективны.</span><span class="sxs-lookup"><span data-stu-id="08a23-147">However, there are specific situations detailed below where the alternatives are likely superior.</span></span>  
  
### <a name="parentchild"></a><span data-ttu-id="08a23-148">Родители-потомки</span><span class="sxs-lookup"><span data-stu-id="08a23-148">Parent/Child</span></span>  
 <span data-ttu-id="08a23-149">Если используется подход «родители-потомки», в каждой строке содержится ссылка на родительскую переменную.</span><span class="sxs-lookup"><span data-stu-id="08a23-149">When using the Parent/Child approach, each row contains a reference to the parent.</span></span> <span data-ttu-id="08a23-150">Следующая таблица определяет типичную таблицу для хранения строк в связи типа «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="08a23-150">The following table defines a typical table used to contain the parent and the child rows in a Parent/Child relationship:</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE TABLE ParentChildOrg  
   (  
    BusinessEntityID int PRIMARY KEY,  
    ManagerId int REFERENCES ParentChildOrg(BusinessEntityID),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
```  
  
 <span data-ttu-id="08a23-151">Сравнение подхода «родители-потомки» и `hierarchyid` для распространенных операций</span><span class="sxs-lookup"><span data-stu-id="08a23-151">Comparing Parent/Child and `hierarchyid` for Common Operations</span></span>  
  
-   <span data-ttu-id="08a23-152">Запросы по поддеревьям выполняются значительно быстрее, если используется тип `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="08a23-152">Subtree queries are significantly faster with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="08a23-153">Запросы по прямым потомкам обрабатываются немного медленнее, если используется тип `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="08a23-153">Direct descendant queries are slightly slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="08a23-154">Операции по перемещению узлов типа `hierarchyid`, не являющихся конечными, выполняются медленнее.</span><span class="sxs-lookup"><span data-stu-id="08a23-154">Moving non-leaf nodes is slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="08a23-155">Вставка неконечных узлов и вставка или перемещение конечных узлов имеют для типа данных `hierarchyid` одинаковую сложность.</span><span class="sxs-lookup"><span data-stu-id="08a23-155">Inserting non-leaf nodes and inserting or moving leaf nodes has the same complexity with `hierarchyid`.</span></span>  
  
 <span data-ttu-id="08a23-156">Метод «родители-потомки» может оказаться более эффективным в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="08a23-156">Parent/Child might be superior when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="08a23-157">Размер ключа очень важен.</span><span class="sxs-lookup"><span data-stu-id="08a23-157">The size of the key is critical.</span></span> <span data-ttu-id="08a23-158">При одинаковом количестве узлов значение типа `hierarchyid` занимает столько же или больше памяти, чем значение одного из целочисленных типов (`smallint`, `int`, `bigint`).</span><span class="sxs-lookup"><span data-stu-id="08a23-158">For the same number of nodes, a `hierarchyid` value is equal to or larger than an integer-family (`smallint`, `int`, `bigint`) value.</span></span> <span data-ttu-id="08a23-159">По этой причине можно использовать метод «родители-потомки», но только в редких случаях, так как тип `hierarchyid` обеспечивает более эффективное использование памяти при операциях ввода-вывода и требует меньше команд ЦП по сравнению со структурами типа «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="08a23-159">This is only a reason to use Parent/Child in rare cases, because `hierarchyid` has significantly better locality of I/O and CPU complexity than the common table expressions required when you are using a Parent/Child structure.</span></span>  
  
-   <span data-ttu-id="08a23-160">Запросы редко бывают обращены сразу к нескольким частям иерархии.</span><span class="sxs-lookup"><span data-stu-id="08a23-160">Queries rarely query across sections of the hierarchy.</span></span> <span data-ttu-id="08a23-161">Иными словами, запрос обычно касается только одной точки иерархической структуры.</span><span class="sxs-lookup"><span data-stu-id="08a23-161">In other words, queries usually address only a single point in the hierarchy.</span></span> <span data-ttu-id="08a23-162">В этих случаях хранение данных в одном месте не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="08a23-162">In these cases co-location is not important.</span></span> <span data-ttu-id="08a23-163">Например, метод «родители-потомки» предпочтителен в случае, если таблица организаций используется только для обработки заработной платы отдельных работников.</span><span class="sxs-lookup"><span data-stu-id="08a23-163">For example, Parent/Child is superior when the organization table is only used to process payroll for individual employees.</span></span>  
  
-   <span data-ttu-id="08a23-164">Структура неконечных поддеревьев часто меняется, и очень важна производительность.</span><span class="sxs-lookup"><span data-stu-id="08a23-164">Non-leaf subtrees move frequently and performance is very important.</span></span> <span data-ttu-id="08a23-165">В иерархической структуре «родители-потомки» изменение местоположения строки иерархии касается только одной строки.</span><span class="sxs-lookup"><span data-stu-id="08a23-165">In a parent/child representation changing the location of a row in a hierarchy affects a single row.</span></span> <span data-ttu-id="08a23-166">Изменение расположения строки в `hierarchyid` использовании влияет на *n* строк, где *n* — число узлов в перемещаемом поддереве.</span><span class="sxs-lookup"><span data-stu-id="08a23-166">Changing the location of a row in a `hierarchyid` usage affects *n* rows, where *n* is number of nodes in the sub-tree being moved.</span></span>  
  
     <span data-ttu-id="08a23-167">Если поддерево без конечных узлов необходимо часто перемещать и важна высокая производительность, но при этом большинство перемещений происходит на определенном уровне иерархии, рекомендуется разбить данные на две иерархические структуры: более высоких и более низких уровней.</span><span class="sxs-lookup"><span data-stu-id="08a23-167">If the non-leaf subtrees move frequently and performance is important, but most of the moves are at a well-defined level of the hierarchy, consider splitting the higher and lower levels into two hierarchies.</span></span> <span data-ttu-id="08a23-168">В этом случае все перемещения будут происходить на последнем уровне верхней иерархии.</span><span class="sxs-lookup"><span data-stu-id="08a23-168">This makes all moves into leaf-levels of the higher hierarchy.</span></span> <span data-ttu-id="08a23-169">Например, рассмотрим иерархию веб-сайтов, входящих в одну службу.</span><span class="sxs-lookup"><span data-stu-id="08a23-169">For instance, consider a hierarchy of Web sites hosted by a service.</span></span> <span data-ttu-id="08a23-170">Сайты содержат много страниц, имеющих иерархическую структуру.</span><span class="sxs-lookup"><span data-stu-id="08a23-170">Sites contain many pages arranged in a hierarchical manner.</span></span> <span data-ttu-id="08a23-171">Сайты службы могут перемещаться в другие места в иерархии сайтов, но реорганизация страниц происходит редко.</span><span class="sxs-lookup"><span data-stu-id="08a23-171">Hosted sites might be moved to other locations in the site hierarchy, but the subordinate pages are rarely re-arranged.</span></span> <span data-ttu-id="08a23-172">Это можно представить так:</span><span class="sxs-lookup"><span data-stu-id="08a23-172">This could be represented via:</span></span>  
  
    ```  
    CREATE TABLE HostedSites   
       (  
        SiteId hierarchyid, PageId hierarchyid  
       ) ;  
    GO  
    ```  
  
  
### <a name="xml"></a><span data-ttu-id="08a23-173">XML</span><span class="sxs-lookup"><span data-stu-id="08a23-173">XML</span></span>  
 <span data-ttu-id="08a23-174">XML-документ является деревом, поэтому один экземпляр типа данных XML может представлять всю структуру.</span><span class="sxs-lookup"><span data-stu-id="08a23-174">An XML document is a tree, and therefore a single XML data type instance can represent a complete hierarchy.</span></span> <span data-ttu-id="08a23-175">В [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] при создании XML-индекса `hierarchyid` значения используются внутренне для представления позиции в иерархии.</span><span class="sxs-lookup"><span data-stu-id="08a23-175">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when an XML index is created, `hierarchyid` values are used internally to represent the position in the hierarchy.</span></span>  
  
 <span data-ttu-id="08a23-176">Использование типа данных XML может быть выгодно в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="08a23-176">Using XML data type can be superior when all the following are true:</span></span>  
  
-   <span data-ttu-id="08a23-177">Всегда хранится и извлекается вся структура данных.</span><span class="sxs-lookup"><span data-stu-id="08a23-177">The complete hierarchy is always stored and retrieved.</span></span>  
  
-   <span data-ttu-id="08a23-178">Приложение обрабатывает данные в формате XML.</span><span class="sxs-lookup"><span data-stu-id="08a23-178">The data is consumed in XML format by the application.</span></span>  
  
-   <span data-ttu-id="08a23-179">Поиск с помощью предикатов происходит крайне редко, и производительность здесь не критична.</span><span class="sxs-lookup"><span data-stu-id="08a23-179">Predicate searches are extremely limited and not performance critical.</span></span>  
  
 <span data-ttu-id="08a23-180">Например, если приложение отслеживает работу многочисленных организаций, всегда хранит и извлекает всю организационную иерархию и не запрашивает подробные данные по отдельным организациям, таблица может иметь следующий вид.</span><span class="sxs-lookup"><span data-stu-id="08a23-180">For example, if an application tracks multiple organizations, always stores and retrieves the complete organizational hierarchy, and does not query into a single organization, a table of the following form might make sense:</span></span>  
  
```  
CREATE TABLE XMLOrg   
    (  
    Orgid int,  
    Orgdata xml  
    ) ;  
GO  
```  
  
  
##  <a name="indexing-strategies-for-hierarchical-data"></a><a name="indexing"></a> <span data-ttu-id="08a23-181">Ниже описаны подходы к индексированию иерархических данных:</span><span class="sxs-lookup"><span data-stu-id="08a23-181">Indexing Strategies for Hierarchical Data</span></span>  
 <span data-ttu-id="08a23-182">Есть два подхода к индексированию иерархических данных:</span><span class="sxs-lookup"><span data-stu-id="08a23-182">There are two strategies for indexing hierarchical data:</span></span>  
  
-   <span data-ttu-id="08a23-183">**В глубину**</span><span class="sxs-lookup"><span data-stu-id="08a23-183">**Depth-first**</span></span>  
  
     <span data-ttu-id="08a23-184">В индексе преимущественно в глубину строки поддерева хранятся рядом друг с другом.</span><span class="sxs-lookup"><span data-stu-id="08a23-184">A depth-first index stores the rows in a subtree near each other.</span></span> <span data-ttu-id="08a23-185">Например, записи всех сотрудников, в цепи подчиненности которых есть данный руководитель, хранятся рядом с записью руководителя.</span><span class="sxs-lookup"><span data-stu-id="08a23-185">For example, all employees that report through a manager are stored near their managers' record.</span></span>  
  
     <span data-ttu-id="08a23-186">В индексе преимущественно в глубину все узлы поддерева узла хранятся вместе.</span><span class="sxs-lookup"><span data-stu-id="08a23-186">In a depth-first index, all nodes in the subtree of a node are co-located.</span></span> <span data-ttu-id="08a23-187">Поэтому индекс преимущественно в глубину эффективен для обработки запросов по поддеревьям. Например, «найти все файлы в этой папке и ее подкаталогах».</span><span class="sxs-lookup"><span data-stu-id="08a23-187">Depth-first indexes are therefore efficient for answering queries about subtrees, such as "Find all files in this folder and its subfolders".</span></span>  
  
-   <span data-ttu-id="08a23-188">**В ширину**</span><span class="sxs-lookup"><span data-stu-id="08a23-188">**Breadth-first**</span></span>  
  
     <span data-ttu-id="08a23-189">Если используется индексирование в ширину, строки одного уровня иерархии хранятся вместе.</span><span class="sxs-lookup"><span data-stu-id="08a23-189">A breadth-first stores the rows each level of the hierarchy together.</span></span> <span data-ttu-id="08a23-190">Например, записи всех сотрудников, напрямую подчиненных одному и тому же руководителю, хранятся рядом друг с другом.</span><span class="sxs-lookup"><span data-stu-id="08a23-190">For example, the records of employees who directly report to the same manager are stored near each other.</span></span>  
  
     <span data-ttu-id="08a23-191">В индексе преимущественно в ширину все прямые потомки узла хранятся в одном месте.</span><span class="sxs-lookup"><span data-stu-id="08a23-191">In a breadth-first index all direct children of a node are co-located.</span></span> <span data-ttu-id="08a23-192">Поэтому индекс преимущественно в ширину эффективен для запросов по прямым потомкам. Например: «найти всех прямых подчиненных этого начальника».</span><span class="sxs-lookup"><span data-stu-id="08a23-192">Breadth-first indexes are therefore efficient for answering queries about immediate children, such as "Find all employees who report directly to this manager".</span></span>  
  
 <span data-ttu-id="08a23-193">Выбор стратегии индексирования (в глубину, в ширину или обе) и ключа кластеризации зависит от того, какие из вышеуказанных типов запросов обрабатываются чаще и какие операции более важны (SELECT или DML).</span><span class="sxs-lookup"><span data-stu-id="08a23-193">Whether to have depth-first, breadth-first, or both, and which to make the clustering key (if any), depends on the relative importance of the above types of queries, and the relative importance of SELECT vs. DML operations.</span></span> <span data-ttu-id="08a23-194">Пример использования стратегий индексирования см. в разделе [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="08a23-194">For a detailed example of indexing strategies, see [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
### <a name="creating-indexes"></a><span data-ttu-id="08a23-195">Создание индексов</span><span class="sxs-lookup"><span data-stu-id="08a23-195">Creating Indexes</span></span>  
 <span data-ttu-id="08a23-196">Для организации данных в ширину можно использовать метод GetLevel().</span><span class="sxs-lookup"><span data-stu-id="08a23-196">The GetLevel() method can be used to create a breadth first ordering.</span></span> <span data-ttu-id="08a23-197">В следующем примере создаются оба типа индекса: преимущественно в глубину и преимущественно в ширину.</span><span class="sxs-lookup"><span data-stu-id="08a23-197">In the following example, both breadth-first and depth-first indexes are created:</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;   
GO  
  
CREATE TABLE Organization  
   (  
    BusinessEntityID hierarchyid,  
    OrgLevel as BusinessEntityID.GetLevel(),   
    EmployeeName nvarchar(50) NOT NULL  
   ) ;  
GO  
  
CREATE CLUSTERED INDEX Org_Breadth_First   
ON Organization(OrgLevel,BusinessEntityID) ;  
GO  
  
CREATE UNIQUE INDEX Org_Depth_First   
ON Organization(BusinessEntityID) ;  
GO  
```  
  
  
## <a name="examples"></a><span data-ttu-id="08a23-198">Примеры</span><span class="sxs-lookup"><span data-stu-id="08a23-198">Examples</span></span>  
  
### <a name="simple-example"></a><span data-ttu-id="08a23-199">Простой пример</span><span class="sxs-lookup"><span data-stu-id="08a23-199">Simple Example</span></span>  
 <span data-ttu-id="08a23-200">Следующий пример намеренно упрощен, чтобы легче было приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="08a23-200">The following example is intentionally simplistic to help you get started.</span></span> <span data-ttu-id="08a23-201">Сначала создайте таблицу для хранения определенных географических данных.</span><span class="sxs-lookup"><span data-stu-id="08a23-201">First create a table to hold some geography data.</span></span>  
  
```  
CREATE TABLE SimpleDemo  
(Level hierarchyid NOT NULL,  
Location nvarchar(30) NOT NULL,  
LocationType nvarchar(9) NULL);  
```  
  
 <span data-ttu-id="08a23-202">Теперь введите данные для некоторых континентов, стран, штатов и городов.</span><span class="sxs-lookup"><span data-stu-id="08a23-202">Now insert data for some continents, countries, states, and cities.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES   
('/1/', 'Europe', 'Continent'),  
('/2/', 'South America', 'Continent'),  
('/1/1/', 'France', 'Country'),  
('/1/1/1/', 'Paris', 'City'),  
('/1/2/1/', 'Madrid', 'City'),  
('/1/2/', 'Spain', 'Country'),  
('/3/', 'Antarctica', 'Continent'),  
('/2/1/', 'Brazil', 'Country'),  
('/2/1/1/', 'Brasilia', 'City'),  
('/2/1/2/', 'Bahia', 'State'),  
('/2/1/2/1/', 'Salvador', 'City'),  
('/3/1/', 'McMurdo Station', 'City');  
```  
  
 <span data-ttu-id="08a23-203">Выберите данные, добавляя столбец, который преобразовывает данные уровня в текстовое значение, удобное для восприятия.</span><span class="sxs-lookup"><span data-stu-id="08a23-203">Select the data, adding a column that converts the Level data into a text value that is easy to understand.</span></span> <span data-ttu-id="08a23-204">Этот запрос также отсортирует результат по типу данных `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="08a23-204">This query also orders the result by the `hierarchyid` data type.</span></span>  
  
```  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], *   
FROM SimpleDemo ORDER BY Level;  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
Converted Level  Level     Location         LocationType  
/1/              0x58      Europe           Continent  
/1/1/            0x5AC0    France           Country  
/1/1/1/          0x5AD6    Paris            City  
/1/2/            0x5B40    Spain            Country  
/1/2/1/          0x5B56    Madrid           City  
/2/              0x68      South America    Continent  
/2/1/            0x6AC0    Brazil           Country  
/2/1/1/          0x6AD6    Brasilia         City  
/2/1/2/          0x6ADA    Bahia            State  
/2/1/2/1/        0x6ADAB0  Salvador         City  
/3/              0x78      Antarctica       Continent  
/3/1/            0x7AC0    McMurdo Station  City  
```  
  
 <span data-ttu-id="08a23-205">Обратите внимание, что иерархия имеет допустимую структуру, несмотря на отсутствие внутреннего согласования.</span><span class="sxs-lookup"><span data-stu-id="08a23-205">Notice that the hierarchy is has a valid structure, even though it is not internally consistent.</span></span> <span data-ttu-id="08a23-206">Байя — единственный штат.</span><span class="sxs-lookup"><span data-stu-id="08a23-206">Bahia is the only state.</span></span> <span data-ttu-id="08a23-207">Он отображается в иерархии как одноранговый по отношению к городу Бразилиа.</span><span class="sxs-lookup"><span data-stu-id="08a23-207">It appears in the hierarchy as a peer of the city Brasilia.</span></span> <span data-ttu-id="08a23-208">Аналогично полярная станция Макмердо не имеет родительской страны.</span><span class="sxs-lookup"><span data-stu-id="08a23-208">Similarly, McMurdo Station does not have a parent country.</span></span> <span data-ttu-id="08a23-209">Необходимо решить, подходит ли этот тип иерархии для использования.</span><span class="sxs-lookup"><span data-stu-id="08a23-209">Users must decide if this type of hierarchy is appropriate for their use.</span></span>  
  
 <span data-ttu-id="08a23-210">Добавьте еще одну строку и выберите результаты.</span><span class="sxs-lookup"><span data-stu-id="08a23-210">Add another row and select the results.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/1/3/1/', 'Kyoto', 'City'), ('/1/3/1/', 'London', 'City');  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], * FROM SimpleDemo ORDER BY Level;  
```  
  
 <span data-ttu-id="08a23-211">Это демонстрирует наличие других возможных проблем.</span><span class="sxs-lookup"><span data-stu-id="08a23-211">This demonstrates more possible problems.</span></span> <span data-ttu-id="08a23-212">Киото можно ввести в качестве уровня `/1/3/1/` даже при отсутствии родительского уровня `/1/3/`.</span><span class="sxs-lookup"><span data-stu-id="08a23-212">Kyoto can be inserted as level `/1/3/1/` even though there is no parent level `/1/3/`.</span></span> <span data-ttu-id="08a23-213">И Лондон и Киото имеют одинаковое значение свойства `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="08a23-213">And both London and Kyoto have the same value for the `hierarchyid`.</span></span> <span data-ttu-id="08a23-214">Опять-таки пользователи должны решить, подходит ли этот тип иерархии для использования, и заблокировать значения, недопустимые для использования.</span><span class="sxs-lookup"><span data-stu-id="08a23-214">Again, users must decide if this type of hierarchy is appropriate for their use, and block values that are invalid for their usage.</span></span>  
  
 <span data-ttu-id="08a23-215">Кроме того, в этой таблице не используется верхняя часть иерархии `'/'`.</span><span class="sxs-lookup"><span data-stu-id="08a23-215">Also, this table did not use the top of the hierarchy `'/'`.</span></span> <span data-ttu-id="08a23-216">Она была опущена, потому что общий родительский объект для всех континентов отсутствует.</span><span class="sxs-lookup"><span data-stu-id="08a23-216">It was omitted because there is no common parent of all the continents.</span></span> <span data-ttu-id="08a23-217">Его можно добавить путем добавления всей планеты.</span><span class="sxs-lookup"><span data-stu-id="08a23-217">You can add one by adding the whole planet.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/', 'Earth', 'Planet');  
```  
  
##  <a name="related-tasks"></a><a name="tasks"></a> <span data-ttu-id="08a23-218">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="08a23-218">Related Tasks</span></span>  
  
###  <a name="migrating-from-parentchild-to-hierarchyid"></a><a name="migrating"></a> <span data-ttu-id="08a23-219">Переход со структуры «родители-потомки» на тип hierarchyid</span><span class="sxs-lookup"><span data-stu-id="08a23-219">Migrating from Parent/Child to hierarchyid</span></span>  
 <span data-ttu-id="08a23-220">Большинство деревьев представлены методом «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="08a23-220">Most trees are represented using Parent/Child.</span></span> <span data-ttu-id="08a23-221">Для перехода со структуры «родители-потомки» на тип `hierarchyid` проще всего создать временный столбец или временную таблицу для хранения количества узлов на каждом уровне иерархии.</span><span class="sxs-lookup"><span data-stu-id="08a23-221">The easiest way to migrate from a Parent/Child structure to a table using `hierarchyid` is to use a temporary column or a temporary table to keep track of the number of nodes at each level of the hierarchy.</span></span> <span data-ttu-id="08a23-222">Пример преобразования таблицы с организацией "родители-потомки" см. в статье [Учебник. Использование типа данных hierarchyid](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md)(урок 1).</span><span class="sxs-lookup"><span data-stu-id="08a23-222">For an example of migrating a Parent/Child table, see lesson 1 of [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
###  <a name="managing-a-tree-using-hierarchyid"></a><a name="BKMK_ManagingTrees"></a> <span data-ttu-id="08a23-223">Управление древовидной структурой с помощью hierarchyid</span><span class="sxs-lookup"><span data-stu-id="08a23-223">Managing a Tree Using hierarchyid</span></span>  
 <span data-ttu-id="08a23-224">Хотя столбец `hierarchyid` не обязательно представляет дерево, приложение легко может обеспечить это.</span><span class="sxs-lookup"><span data-stu-id="08a23-224">Although a `hierarchyid` column does not necessarily represent a tree, an application can easily ensure that it does.</span></span>  
  
-   <span data-ttu-id="08a23-225">При формировании новых значений выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="08a23-225">When generating new values, do one of the following:</span></span>  
  
    -   <span data-ttu-id="08a23-226">Следите за последним номером потомка в строке родитель.</span><span class="sxs-lookup"><span data-stu-id="08a23-226">Keep track of the last child number in the parent row.</span></span>  
  
    -   <span data-ttu-id="08a23-227">Вычислите последнего потомка.</span><span class="sxs-lookup"><span data-stu-id="08a23-227">Compute the last child.</span></span> <span data-ttu-id="08a23-228">Для эффективного вычисления требуется наличие индекса по ширине.</span><span class="sxs-lookup"><span data-stu-id="08a23-228">Doing this efficiently requires a breadth-first index.</span></span>  
  
-   <span data-ttu-id="08a23-229">Обеспечьте уникальность, создав для столбца уникальный индекс, возможно, как часть ключа кластеризации.</span><span class="sxs-lookup"><span data-stu-id="08a23-229">Enforce uniqueness by creating a unique index on the column, perhaps as part of a clustering key.</span></span> <span data-ttu-id="08a23-230">Чтобы обеспечить уникальность вставляемых значений, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="08a23-230">To ensure that unique values are inserted, do one of the following:</span></span>  
  
    -   <span data-ttu-id="08a23-231">Определяйте нарушения уникальных ключей и проводите повторные попытки.</span><span class="sxs-lookup"><span data-stu-id="08a23-231">Detect unique key violation failures and retry.</span></span>  
  
    -   <span data-ttu-id="08a23-232">Определите уникальность каждого нового дочернего узла перед его вставкой с использованием сериализуемой транзакции.</span><span class="sxs-lookup"><span data-stu-id="08a23-232">Determine the uniqueness of each new child node, and insert it as part of a serializable transaction.</span></span>  
  
  
#### <a name="example-using-error-detection"></a><span data-ttu-id="08a23-233">Пример использования обнаружения ошибок</span><span class="sxs-lookup"><span data-stu-id="08a23-233">Example Using Error Detection</span></span>  
 <span data-ttu-id="08a23-234">В следующем примере образец кода вычисляет значение нового потомка **EmployeeId** , определяет любое нарушение ключа, а затем возвращается к маркеру **INS_EMP** для повторного вычисления значения новой строки **EmployeeId** :</span><span class="sxs-lookup"><span data-stu-id="08a23-234">In the following example, the sample code computes the new child **EmployeeId** value, and then detects any key violation and returns to **INS_EMP** marker to recompute the **EmployeeId** value for the new row:</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
CREATE TABLE Org_T1  
   (  
    EmployeeId hierarchyid PRIMARY KEY,  
    OrgLevel AS EmployeeId.GetLevel(),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
  
CREATE INDEX Org_BreadthFirst ON Org_T1(OrgLevel, EmployeeId)  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50) )   
AS  
BEGIN  
    DECLARE @last_child hierarchyid  
INS_EMP:   
    SELECT @last_child = MAX(EmployeeId) FROM Org_T1   
    WHERE EmployeeId.GetAncestor(1) = @mgrid  
INSERT Org_T1 (EmployeeId, EmployeeName)  
SELECT @mgrid.GetDescendant(@last_child, NULL), @EmpName   
-- On error, return to INS_EMP to recompute @last_child  
IF @@error <> 0 GOTO INS_EMP   
END ;  
GO  
```  
  
  
#### <a name="example-using-a-serializable-transaction"></a><span data-ttu-id="08a23-235">Пример использования сериализуемой транзакции</span><span class="sxs-lookup"><span data-stu-id="08a23-235">Example Using a Serializable Transaction</span></span>  
 <span data-ttu-id="08a23-236">Тип данных **Org_BreadthFirst** обеспечивает использование поиска по диапазону для определения значения **@last_child** .</span><span class="sxs-lookup"><span data-stu-id="08a23-236">The **Org_BreadthFirst** index ensures that determining **@last_child** uses a range seek.</span></span> <span data-ttu-id="08a23-237">В дополнение к другим вариантам ошибок, которые могут потребоваться для приложения, нарушение повторяющегося ключа после вставки означает попытку добавить нескольких сотрудников с одним и тем же идентификатором, поэтому **@last_child** их необходимо повторно вычислить.</span><span class="sxs-lookup"><span data-stu-id="08a23-237">In addition to other error cases an application might want to check, a duplicate key violation after the insert indicates an attempt to add multiple employees with the same id, and therefore **@last_child** must be recomputed.</span></span> <span data-ttu-id="08a23-238">Следующий код использует сериализуемую транзакцию и индекс по ширине для вычисления значения нового узла:</span><span class="sxs-lookup"><span data-stu-id="08a23-238">The following code uses a serializable transaction and a breadth-first index to compute the new node value:</span></span>  
  
```  
CREATE TABLE Org_T2  
    (  
    EmployeeId hierarchyid PRIMARY KEY,  
    LastChild hierarchyid,   
    EmployeeName nvarchar(50)   
    ) ;  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50))   
AS  
BEGIN  
DECLARE @last_child hierarchyid  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION   
  
UPDATE Org_T2   
SET @last_child = LastChild = EmployeeId.GetDescendant(LastChild,NULL)  
WHERE EmployeeId = @mgrid  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(@last_child, @EmpName)  
COMMIT  
END ;  
```  
  
 <span data-ttu-id="08a23-239">Следующий код заполняет таблицу тремя строками и возвращает результаты:</span><span class="sxs-lookup"><span data-stu-id="08a23-239">The following code populates the table with three rows and returns the results:</span></span>  
  
```  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(hierarchyid::GetRoot(), 'David') ;  
GO  
AddEmp 0x , 'Sariya'  
GO  
AddEmp 0x58 , 'Mary'  
GO  
SELECT * FROM Org_T2  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
EmployeeId LastChild EmployeeName  
---------- --------- ------------  
0x        0x58       David  
0x58      0x5AC0     Sariya  
0x5AC0    NULL       Mary  
```  
  
  
###  <a name="enforcing-a-tree"></a><a name="BKMK_EnforcingTrees"></a> <span data-ttu-id="08a23-240">Принудительное формирование древовидной структуры</span><span class="sxs-lookup"><span data-stu-id="08a23-240">Enforcing a tree</span></span>  
 <span data-ttu-id="08a23-241">Приведенный выше пример показывает, как можно использовать приложение для поддержания целостности дерева.</span><span class="sxs-lookup"><span data-stu-id="08a23-241">The above examples illustrate how an application can ensure that a tree is maintained.</span></span> <span data-ttu-id="08a23-242">Обеспечить целостность дерева с помощью ограничений можно, создав для вычисляемого столбца, который определяет родителя для каждого узла, ограничение внешнего ключа относительно идентификатора первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="08a23-242">To enforce a tree by using constraints, a computed column that defines the parent of each node can be created with a foreign key constraint back to the primary key id.</span></span>  
  
```  
CREATE TABLE Org_T3  
(  
   EmployeeId hierarchyid PRIMARY KEY,  
   ParentId AS EmployeeId.GetAncestor(1) PERSISTED    
      REFERENCES Org_T3(EmployeeId),  
   LastChild hierarchyid,   
   EmployeeName nvarchar(50)  
)  
GO  
```  
  
 <span data-ttu-id="08a23-243">Этот метод обеспечения взаимосвязи предпочтительней в случае, если прямой DML-доступ к таблице имеет код, который не в состоянии обеспечить целостность ее иерархического дерева.</span><span class="sxs-lookup"><span data-stu-id="08a23-243">This method of enforcing a relationship is preferred when code that is not trusted to maintain the hierarchical tree has direct DML access to the table.</span></span> <span data-ttu-id="08a23-244">Однако этот метод может снизить производительность, поскольку ограничение необходимо проверять при каждой DML-операции.</span><span class="sxs-lookup"><span data-stu-id="08a23-244">However this method might reduce performance because the constraint must be checked on every DML operation.</span></span>  
  
  
###  <a name="finding-ancestors-by-using-the-clr"></a><a name="findclr"></a> <span data-ttu-id="08a23-245">Поиск предков с помощью среды CLR</span><span class="sxs-lookup"><span data-stu-id="08a23-245">Finding Ancestors by Using the CLR</span></span>  
 <span data-ttu-id="08a23-246">Одной из частых операций, в которых участвуют два узла из иерархии, является нахождение ближайшего общего предка.</span><span class="sxs-lookup"><span data-stu-id="08a23-246">A common operation involving two nodes in a hierarchy is to find the lowest common ancestor.</span></span> <span data-ttu-id="08a23-247">Это может быть написано либо в [!INCLUDE[tsql](../includes/tsql-md.md)] , либо в среде CLR, так как `hierarchyid` тип доступен в обеих средах.</span><span class="sxs-lookup"><span data-stu-id="08a23-247">This can be written in either [!INCLUDE[tsql](../includes/tsql-md.md)] or CLR, because the `hierarchyid` type is available in both.</span></span> <span data-ttu-id="08a23-248">Рекомендуется использовать среду CLR, поскольку она обеспечивает большую производительность.</span><span class="sxs-lookup"><span data-stu-id="08a23-248">CLR is recommended because performance will be faster.</span></span>  
  
 <span data-ttu-id="08a23-249">Используйте следующий код CLR, чтобы найти список предков и ближайшего общего предка:</span><span class="sxs-lookup"><span data-stu-id="08a23-249">Use the following CLR code to list ancestors and to find the lowest common ancestor:</span></span>  
  
```  
using System;  
using System.Collections;  
using System.Text;  
using Microsoft.SqlServer.Server;  
using Microsoft.SqlServer.Types;  
  
public partial class HierarchyId_Operations  
{  
    [SqlFunction(FillRowMethodName = "FillRow_ListAncestors")]  
    public static IEnumerable ListAncestors(SqlHierarchyId h)  
    {  
        while (!h.IsNull)  
        {  
            yield return (h);  
            h = h.GetAncestor(1);  
        }  
    }  
    public static void FillRow_ListAncestors(Object obj, out SqlHierarchyId ancestor)  
    {  
        ancestor = (SqlHierarchyId)obj;  
    }  
  
    public static HierarchyId CommonAncestor(SqlHierarchyId h1, HierarchyId h2)  
    {  
        while (!h1.IsDescendant(h2))  
            h1 = h1.GetAncestor(1);  
  
        return h1;  
    }  
}  
```  
  
 <span data-ttu-id="08a23-250">Чтобы получить возможность использовать методы **ListAncestor** и **CommonAncestor** в следующих примерах [!INCLUDE[tsql](../includes/tsql-md.md)] , постройте библиотеки DLL и создайте сборку **HierarchyId_Operations** в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , выполнив код, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="08a23-250">To use the **ListAncestor** and **CommonAncestor** methods in the following [!INCLUDE[tsql](../includes/tsql-md.md)] examples, build the DLL and create the **HierarchyId_Operations** assembly in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by executing code similar to the following:</span></span>  
  
```  
CREATE ASSEMBLY HierarchyId_Operations   
FROM '<path to DLL>\ListAncestors.dll'  
GO  
```  
  
  
###  <a name="listing-ancestors"></a><a name="ancestors"></a> <span data-ttu-id="08a23-251">Перечисление предков</span><span class="sxs-lookup"><span data-stu-id="08a23-251">Listing Ancestors</span></span>  
 <span data-ttu-id="08a23-252">Создание списка предков узла — это распространенная операция, использующаяся, например, для демонстрации позиции в организации.</span><span class="sxs-lookup"><span data-stu-id="08a23-252">Creating a list of ancestors of a node is a common operation, for instance to show position in an organization.</span></span> <span data-ttu-id="08a23-253">Одним из способов ее реализации является применение возвращающей табличное значение функции, использующей класс **HierarchyId_Operations** , определенный выше:</span><span class="sxs-lookup"><span data-stu-id="08a23-253">One way of doing this is by using a table-valued-function using the **HierarchyId_Operations** class defined above:</span></span>  
  
 <span data-ttu-id="08a23-254">Использование среды [!INCLUDE[tsql](../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="08a23-254">Using [!INCLUDE[tsql](../includes/tsql-md.md)]:</span></span>  
  
```  
CREATE FUNCTION ListAncestors (@node hierarchyid)  
RETURNS TABLE (node hierarchyid)  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.ListAncestors  
GO  
```  
  
 <span data-ttu-id="08a23-255">Пример использования:</span><span class="sxs-lookup"><span data-stu-id="08a23-255">Example of usage:</span></span>  
  
```  
DECLARE @h hierarchyid  
SELECT @h = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- /1/1/5/2/  
  
SELECT LoginID, OrgNode.ToString() AS LogicalNode  
FROM HumanResources.EmployeeDemo AS ED  
JOIN ListAncestors(@h) AS A   
   ON ED.OrgNode = A.Node  
GO  
```  
  
  
###  <a name="finding-the-lowest-common-ancestor"></a><a name="lowestcommon"></a> <span data-ttu-id="08a23-256">Нахождение ближайшего общего предка</span><span class="sxs-lookup"><span data-stu-id="08a23-256">Finding the Lowest Common Ancestor</span></span>  
 <span data-ttu-id="08a23-257">С помощью класса **HierarchyId_Operations** , определенного выше, создайте следующую функцию [!INCLUDE[tsql](../includes/tsql-md.md)] для нахождения ближайшего общего предка, затрагивающую два узла в иерархии:</span><span class="sxs-lookup"><span data-stu-id="08a23-257">Using the **HierarchyId_Operations** class defined above, create the following [!INCLUDE[tsql](../includes/tsql-md.md)] function to find the lowest common ancestor involving two nodes in a hierarchy:</span></span>  
  
```  
CREATE FUNCTION CommonAncestor (@node1 hierarchyid, @node2 hierarchyid)  
RETURNS hierarchyid  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.CommonAncestor  
GO  
```  
  
 <span data-ttu-id="08a23-258">Пример использования:</span><span class="sxs-lookup"><span data-stu-id="08a23-258">Example of usage:</span></span>  
  
```  
DECLARE @h1 hierarchyid, @h2 hierarchyid  
  
SELECT @h1 = OrgNode   
FROM  HumanResources.EmployeeDemo   
WHERE LoginID = 'adventure-works\jossef0' -- Node is /1/1/3/  
  
SELECT @h2 = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- Node is /1/1/5/2/  
  
SELECT OrgNode.ToString() AS LogicalNode, LoginID   
FROM HumanResources.EmployeeDemo    
WHERE OrgNode = dbo.CommonAncestor(@h1, @h2) ;  
```  
  
 <span data-ttu-id="08a23-259">Результирующий узел — /1/1/</span><span class="sxs-lookup"><span data-stu-id="08a23-259">The resultant node is /1/1/</span></span>  
  
  
###  <a name="moving-subtrees"></a><a name="BKMK_MovingSubtrees"></a> <span data-ttu-id="08a23-260">Перемещение поддеревьев</span><span class="sxs-lookup"><span data-stu-id="08a23-260">Moving Subtrees</span></span>  
 <span data-ttu-id="08a23-261">Другой распространенной операцией является перемещение поддеревьев.</span><span class="sxs-lookup"><span data-stu-id="08a23-261">Another common operation is moving subtrees.</span></span> <span data-ttu-id="08a23-262">Приведенная ниже процедура принимает поддерево **@oldMgr** и делает его (включая **@oldMgr** ) поддеревом **@newMgr** .</span><span class="sxs-lookup"><span data-stu-id="08a23-262">The procedure below takes the subtree of **@oldMgr** and makes it (including **@oldMgr**) a subtree of **@newMgr**.</span></span>  
  
```  
CREATE PROCEDURE MoveOrg(@oldMgr nvarchar(256), @newMgr nvarchar(256) )  
AS  
BEGIN  
DECLARE @nold hierarchyid, @nnew hierarchyid  
SELECT @nold = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @oldMgr ;  
  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION  
SELECT @nnew = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @newMgr ;  
  
SELECT @nnew = @nnew.GetDescendant(max(OrgNode), NULL)   
FROM HumanResources.EmployeeDemo WHERE OrgNode.GetAncestor(1)=@nnew ;  
  
UPDATE HumanResources.EmployeeDemo    
SET OrgNode = OrgNode.GetReparentedValue(@nold, @nnew)  
WHERE OrgNode.IsDescendantOf(@nold) = 1 ;  
  
COMMIT TRANSACTION  
END ;  
GO  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="08a23-263">См. также:</span><span class="sxs-lookup"><span data-stu-id="08a23-263">See Also</span></span>  
 <span data-ttu-id="08a23-264">[Справочник по методам типа данных hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="08a23-264">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="08a23-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="08a23-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span></span>  
 [<span data-ttu-id="08a23-266">hierarchyid (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="08a23-266">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
