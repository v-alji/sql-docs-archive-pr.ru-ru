---
title: Фильтры соединения | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server replication], join
- publications [SQL Server replication], join filters
- merge replication join filters [SQL Server replication]
- join filters
ms.assetid: dd78fd8f-56e3-4582-9abd-6bc25c91e075
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b97e7d7b53e6a3fdb242d1272e013bbd45f0ed17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654204"
---
# <a name="join-filters"></a><span data-ttu-id="4e6f7-102">фильтры соединения</span><span class="sxs-lookup"><span data-stu-id="4e6f7-102">Join Filters</span></span>
  <span data-ttu-id="4e6f7-103">Фильтр соединения позволяет фильтровать таблицу на основе фильтрации связанной таблицы в публикации.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-103">A join filter allows a table to be filtered based on how a related table in the publication is filtered.</span></span> <span data-ttu-id="4e6f7-104">Родительская таблица, как правило, фильтруется параметризованным фильтром. Затем определяется один или несколько фильтров соединения практически таким же способом, что и соединение таблиц.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-104">Typically a parent table is filtered using a parameterized filter; then one or more join filters are defined in much the same way that you define a join between tables.</span></span> <span data-ttu-id="4e6f7-105">Фильтры соединения расширяют параметризованные фильтры таким образом, чтобы данные в связанных таблицах реплицировались только в том случае, если они соответствуют предложению фильтра соединения.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-105">The join filters extend the parameterized filter so that the data in the related tables is only replicated if it matches the join filter clause.</span></span>  
  
 <span data-ttu-id="4e6f7-106">Фильтры соединений, как правило, следуют связям «первичный-внешний ключ», определенным для таблиц, к которым они применяются, но не ограничиваются только этими связями.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-106">Join filters typically follow the primary key/foreign key relationships defined for the tables to which they are applied, but they are not limited strictly to primary key/foreign key relationships.</span></span> <span data-ttu-id="4e6f7-107">Фильтр соединения может быть основан на любой логике, которая сравнивает связанные данные в двух таблицах.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-107">The join filter can be based on any logic that compares related data in two tables.</span></span>  
  
 <span data-ttu-id="4e6f7-108">Обратите внимание на следующие таблицы в образце базы данных [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] , связанные связью «первичный-внешний ключ»:</span><span class="sxs-lookup"><span data-stu-id="4e6f7-108">Consider the following tables in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database, which are related through primary key to foreign key relationships:</span></span>  
  
-   <span data-ttu-id="4e6f7-109">**HumanResources.Employee**</span><span class="sxs-lookup"><span data-stu-id="4e6f7-109">**HumanResources.Employee**</span></span>  
  
-   <span data-ttu-id="4e6f7-110">**Sales.SalesOrderHeader**</span><span class="sxs-lookup"><span data-stu-id="4e6f7-110">**Sales.SalesOrderHeader**</span></span>  
  
-   <span data-ttu-id="4e6f7-111">**Sales.SalesOrderDetail**</span><span class="sxs-lookup"><span data-stu-id="4e6f7-111">**Sales.SalesOrderDetail**</span></span>  
  
 <span data-ttu-id="4e6f7-112">Эти таблицы могли бы использоваться в приложении для поддержки перемещающихся между регионами продавцов, но они должны фильтроваться таким образом, чтобы каждый менеджер продаж из таблицы **HumanResources.Employee** получал лишь те данные, которые относятся к заказам его клиентов.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-112">These tables could be used in an application to support a mobile sales force, but they must be filtered so that each sales person in the **HumanResources.Employee** table receives only the data relevant to their customers' orders.</span></span>  
  
 <span data-ttu-id="4e6f7-113">Прежде всего необходимо определить параметризованный фильтр в родительской таблице, в данном примере — таблице **HumanResources.Employee.** .</span><span class="sxs-lookup"><span data-stu-id="4e6f7-113">The first step is to define a parameterized filter on the parent table, which in this example is the **HumanResources.Employee** table.</span></span> <span data-ttu-id="4e6f7-114">Эта таблица включает столбец **LoginID**, содержащий имя входа каждого сотрудника в виде *domain\login*.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-114">This table includes the column **LoginID**, which contains the login for each employee in the form *domain\login*.</span></span> <span data-ttu-id="4e6f7-115">Для фильтрации таблицы, при которой каждый работник будет видеть только данные, связанные с ним, укажите следующее предложение параметризованного фильтра:</span><span class="sxs-lookup"><span data-stu-id="4e6f7-115">To filter this table so that each employee receives only the data related to them, specify a parameterized filter clause of:</span></span>  
  
```  
LoginID = SUSER_SNAME()  
```  
  
 <span data-ttu-id="4e6f7-116">Благодаря этому фильтру подписка каждого сотрудника будет содержать только те данные из таблицы **HumanResources.Employee** , которые относятся к этому сотруднику (в этом случае — в одной строке).</span><span class="sxs-lookup"><span data-stu-id="4e6f7-116">This filter ensures that each employee's subscription only contains data from the **HumanResources.Employee** table that is relevant to that employee (which in this case is a single row).</span></span> <span data-ttu-id="4e6f7-117">Дополнительные сведения см. в разделе [Параметризованные фильтры строк](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="4e6f7-117">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 <span data-ttu-id="4e6f7-118">Следующим этапом является расширение этого фильтра на все связанные таблицы, используя синтаксис, подобный тому, который использовался для указания соединения таблиц.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-118">The next step is to extend this filter to each of the related tables, using syntax similar to that used to specify a join between two tables.</span></span> <span data-ttu-id="4e6f7-119">Первое предложение фильтра соединения:</span><span class="sxs-lookup"><span data-stu-id="4e6f7-119">The first join filter clause is:</span></span>  
  
```  
Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
```  
  
 <span data-ttu-id="4e6f7-120">Это предложение обеспечивает включение в подписку только тех сведений о заказах, которые относятся к каждому менеджеру по продажам.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-120">This ensures the subscription contains only the order data relevant to each sales person.</span></span> <span data-ttu-id="4e6f7-121">Второе предложение фильтра соединения:</span><span class="sxs-lookup"><span data-stu-id="4e6f7-121">The second join filter clause is:</span></span>  
  
```  
SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
```  
  
 <span data-ttu-id="4e6f7-122">Это предложение обеспечивает включение в подписку только подробных данных о заказах, которые относятся к каждому менеджеру по продажам.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-122">This ensures the subscription contains only the detail data related to the order data for each sales person.</span></span> <span data-ttu-id="4e6f7-123">В данном примере показывается соединение отдельной таблицы в каждой точке; кроме того, в каждой точке можно соединить и несколько таблиц.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-123">This example shows a single table being joined at each point; it is also possible to join more than one table at each point.</span></span>  
  
 <span data-ttu-id="4e6f7-124">Фильтры соединения можно добавлять по одному в мастере создания публикаций и диалоговом окне **Свойства публикации** , или же их можно добавить программно.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-124">Join filters can be added one at a time through the New Publication Wizard and the **Publication Properties** dialog box, or they can be added programmatically.</span></span> <span data-ttu-id="4e6f7-125">Кроме того, их можно автоматически формировать с помощью мастера создания публикаций: укажите фильтр строк для таблицы, и фильтры соединения будут применены ко всем связанным таблицам.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-125">They can also be generated automatically through the New Publication Wizard: you specify a row filter for a table and join filters are applied to all related tables.</span></span> <span data-ttu-id="4e6f7-126">Дополнительные сведения см. в статьях [Определение и изменение фильтра соединения между статьями публикации слиянием](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Автоматическое формирование набора фильтров соединения между статьями публикации слиянием (среда SQL Server Management Studio)](../publish/automatically-generate-join-filters-between-merge-articles.md) и [Определение статьи](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="4e6f7-126">For more information, see [Define and Modify a Join Filter Between Merge Articles](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Automatically Generate a Set of Join Filters Between Merge Articles &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md), and [Define an Article](../publish/define-an-article.md).</span></span>  
  
## <a name="optimizing-join-filter-performance"></a><span data-ttu-id="4e6f7-127">Оптимизация производительности фильтра соединения</span><span class="sxs-lookup"><span data-stu-id="4e6f7-127">Optimizing Join Filter Performance</span></span>  
 <span data-ttu-id="4e6f7-128">Чтобы оптимизировать производительность фильтра соединения, необходимо придерживаться следующих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-128">Join filter performance can be optimized by following these guidelines:</span></span>  
  
-   <span data-ttu-id="4e6f7-129">Ограничьте число таблиц, входящих в иерархию фильтра соединения.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-129">Limit the number of tables in the join filter hierarchy.</span></span>  
  
     <span data-ttu-id="4e6f7-130">Фильтры соединений могут включать неограниченное количество таблиц, однако фильтры с большим количеством таблиц могут в значительной степени повлиять на производительность во время процесса слияния.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-130">Join Filters can involve an unlimited number of tables, but filters with a large number of tables can significantly impact performance during merge processing.</span></span> <span data-ttu-id="4e6f7-131">При создании фильтров соединения из пяти и более таблиц рассмотрите другие решения: не фильтруйте маленькие таблицы, таблицы, которые не изменяются или служат в основном таблицами подстановки.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-131">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="4e6f7-132">Используйте фильтры соединения только между теми таблицами, которые должны быть секционированы среди подписок.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-132">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="4e6f7-133">Для параметра **join unique key** установите значение **True** (где необходимо).</span><span class="sxs-lookup"><span data-stu-id="4e6f7-133">Set the **join unique key** option to **True** where appropriate.</span></span>  
  
     <span data-ttu-id="4e6f7-134">Для процесса слияния предлагается специальная оптимизация производительности, если соединяемый столбец в родительской таблице уникален.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-134">The merge process has special performance optimizations available if the joined column in the parent is unique.</span></span> <span data-ttu-id="4e6f7-135">Если условие соединения основано на уникальном столбце, задайте для фильтра соединения параметр **join unique key** .</span><span class="sxs-lookup"><span data-stu-id="4e6f7-135">If the join condition is based on a unique column, set the **join unique key** option for the join filter.</span></span> <span data-ttu-id="4e6f7-136">Сведения о настройке этого параметра см. в разделах руководства, перечисленных в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-136">For information about setting this option, see the how-to topics listed in the previous section.</span></span>  
  
-   <span data-ttu-id="4e6f7-137">Убедитесь, что столбцы, указанные в фильтрах соединений, имеют индексы.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-137">Ensure that the columns referenced in join filters are indexed.</span></span>  
  
     <span data-ttu-id="4e6f7-138">Если столбцы, указанные в фильтре, имеют индексы, репликация может более эффективно обработать фильтры.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-138">If the columns referenced in the filter are indexed, replication can process the filters more efficiently.</span></span>  
  
-   <span data-ttu-id="4e6f7-139">Не создавайте фильтры строк, которые имитируют фильтры соединения.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-139">Do not create row filters that mimic join filters.</span></span>  
  
     <span data-ttu-id="4e6f7-140">Можно создавать фильтры строк, имитирующие фильтры соединения, используя вложенный запрос в предложении WHERE, например:</span><span class="sxs-lookup"><span data-stu-id="4e6f7-140">It is possible to create row filters that mimic join filters by using a subquery in a WHERE clause, such as:</span></span>  
  
    ```  
    WHERE Customer.SalesPersonID IN (SELECT EmployeeID FROM Employee WHERE LoginID = SUSER_SNAME())   
    ```  
  
     <span data-ttu-id="4e6f7-141">Настоятельно рекомендуется такую логику выражать в фильтре соединения, а не во вложенном запросе.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-141">It is strongly recommended that all such logic be expressed in a join filter rather than a subquery.</span></span> <span data-ttu-id="4e6f7-142">Если приложение требует, чтобы фильтр строк использовал вложенный запрос, убедитесь, что вложенный запрос обращается только к поисковым данным, которые не изменяются.</span><span class="sxs-lookup"><span data-stu-id="4e6f7-142">If your application requires a row filter to use a subsquery, ensure that the subquery only references lookup data that does not change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e6f7-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e6f7-143">See Also</span></span>  
 <span data-ttu-id="4e6f7-144">[Фильтрация опубликованных данных для репликации слиянием](filter-published-data-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="4e6f7-144">[Filter Published Data for Merge Replication](filter-published-data-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="4e6f7-145">Параметризованные фильтры строк</span><span class="sxs-lookup"><span data-stu-id="4e6f7-145">Parameterized Row Filters</span></span>](parameterized-filters-parameterized-row-filters.md)  
  
  
