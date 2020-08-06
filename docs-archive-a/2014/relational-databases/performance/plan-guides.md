---
title: Структуры планов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- TEMPLATE plan guide
- SQL plan guides
- OPTIMIZE FOR query hint
- RECOMPILE query hint
- OBJECT plan guide
- plan guides [SQL Server], about plan guides
- OPTION clause
- plan guides [SQL Server]
- USE PLAN query hint
ms.assetid: bfc97632-c14c-4768-9dc5-a9c512f6b2bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c97682163313a56acb8521174fa8d4012a69b529
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666005"
---
# <a name="plan-guides"></a><span data-ttu-id="6742a-102">Руководства планов</span><span class="sxs-lookup"><span data-stu-id="6742a-102">Plan Guides</span></span>
  <span data-ttu-id="6742a-103">Структуры планов позволяют оптимизировать производительность запросов, если невозможно или нежелательно непосредственно изменять текст фактически имеющегося запроса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6742a-103">Plan guides let you optimize the performance of queries when you cannot or do not want to directly change the text of the actual query in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="6742a-104">Структуры планов влияют на оптимизацию запросов путем присоединения к ним указаний запроса или постоянного плана запроса.</span><span class="sxs-lookup"><span data-stu-id="6742a-104">Plan guides influence the optimization of queries by attaching query hints or a fixed query plan to them.</span></span> <span data-ttu-id="6742a-105">Структуры планов полезны, когда небольшое подмножество запросов в приложении базы данных стороннего разработчика выполняются не так, как ожидается.</span><span class="sxs-lookup"><span data-stu-id="6742a-105">Plan guides can be useful when a small subset of queries in a database application provided by a third-party vendor are not performing as expected.</span></span> <span data-ttu-id="6742a-106">В структуре плана задается инструкция Transact-SQL, которую нужно оптимизировать, и либо предложение OPTION, содержащее указания запросов, либо конкретный план запроса, с помощью которого планируется оптимизировать запрос.</span><span class="sxs-lookup"><span data-stu-id="6742a-106">In the plan guide, you specify the Transact-SQL statement that you want optimized and either an OPTION clause that contains the query hints you want to use or a specific query plan you want to use to optimize the query.</span></span> <span data-ttu-id="6742a-107">При выполнении запроса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сопоставляет инструкцию Transact-SQL со структурой плана и присоединяет предложение OPTION к запросу во время выполнения или использует указанный план запроса.</span><span class="sxs-lookup"><span data-stu-id="6742a-107">When the query executes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] matches the Transact-SQL statement to the plan guide and attaches the OPTION clause to the query at run time or uses the specified query plan.</span></span>  
  
 <span data-ttu-id="6742a-108">Общее число структур планов, которые можно создать, ограничивается только доступными системными ресурсами.</span><span class="sxs-lookup"><span data-stu-id="6742a-108">The total number of plan guides you can create is limited only by available system resources.</span></span> <span data-ttu-id="6742a-109">Тем не менее использование структур планов должно быть ограничено критически важными запросами, затрагиваемыми в целях улучшения или стабилизации производительности.</span><span class="sxs-lookup"><span data-stu-id="6742a-109">Nevertheless, plan guides should be limited to mission-critical queries that are targeted for improved or stabilized performance.</span></span> <span data-ttu-id="6742a-110">Структуры планов не следует использовать для основной массы запросов развернутого приложения.</span><span class="sxs-lookup"><span data-stu-id="6742a-110">Plan guides should not be used to influence most of the query load of a deployed application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6742a-111">Структуру планов можно использовать не во всех выпусках [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6742a-111">Plan guides cannot be used in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6742a-112">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="6742a-112">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="6742a-113">Структуры планов видны в любом выпуске.</span><span class="sxs-lookup"><span data-stu-id="6742a-113">Plan guides are visible in any edition.</span></span> <span data-ttu-id="6742a-114">Можно также присоединить базу данных, содержащую структуры планов, к любой версии.</span><span class="sxs-lookup"><span data-stu-id="6742a-114">You can also attach a database that contains plan guides to any edition.</span></span> <span data-ttu-id="6742a-115">Структуры планов остаются нетронутыми при восстановлении или присоединении базы данных к обновленной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6742a-115">Plan guides remain intact when you restore or attach a database to an upgraded version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="types-of-plan-guides"></a><span data-ttu-id="6742a-116">Типы структур планов</span><span class="sxs-lookup"><span data-stu-id="6742a-116">Types of Plan Guides</span></span>  
 <span data-ttu-id="6742a-117">Могут быть созданы структуры планов следующих типов.</span><span class="sxs-lookup"><span data-stu-id="6742a-117">The following types of plan guides can be created.</span></span>  
  
 <span data-ttu-id="6742a-118">OBJECT, руководство плана</span><span class="sxs-lookup"><span data-stu-id="6742a-118">OBJECT plan guide</span></span>  
 <span data-ttu-id="6742a-119">Структура плана OBJECT соответствует запросам, выполняемым в контексте хранимых процедур языка [!INCLUDE[tsql](../../includes/tsql-md.md)] , определяемых пользователем скалярных функций, определяемых пользователем функций с несколькими инструкциями, возвращающих табличные значения, и триггеров DML.</span><span class="sxs-lookup"><span data-stu-id="6742a-119">An OBJECT plan guide matches queries that execute in the context of [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, scalar user-defined functions, multi-statement table-valued user-defined functions, and DML triggers.</span></span>  
  
 <span data-ttu-id="6742a-120">Предположим, что следующая хранимая процедура, которая принимает параметр `@Country`_`region` , находится в приложении базы данных, развертываемом применительно к базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="6742a-120">Suppose the following stored procedure, which takes the `@Country`_`region` parameter, is in a database application that is deployed against the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
CREATE PROCEDURE Sales.GetSalesOrderByCountry (@Country_region nvarchar(60))  
AS  
BEGIN  
    SELECT *  
    FROM Sales.SalesOrderHeader AS h, Sales.Customer AS c,   
        Sales.SalesTerritory AS t  
    WHERE h.CustomerID = c.CustomerID  
        AND c.TerritoryID = t.TerritoryID  
        AND CountryRegionCode = @Country_region  
END;  
```  
  
 <span data-ttu-id="6742a-121">Предполагается, что эта хранимая процедура скомпилирована и оптимизирована для значения `@Country`_`region = N'AU'` (Австралия).</span><span class="sxs-lookup"><span data-stu-id="6742a-121">Assume that this stored procedure has been compiled and optimized for `@Country`_`region = N'AU'` (Australia).</span></span> <span data-ttu-id="6742a-122">Но из Австралии поступает относительно небольшое количество заказов на продажу, поэтому производительность снижается, если запрос выполняется с использованием значений параметров, относящихся к тем странам, где имеется большее количество заказов на продажу.</span><span class="sxs-lookup"><span data-stu-id="6742a-122">However, because there are relatively few sales orders that originate from Australia, performance decreases when the query executes using parameter values of countries with more sales orders.</span></span> <span data-ttu-id="6742a-123">Так как страна, из которой поступает больше всего заказов на продажу, — США, план запроса, сформированный для значения `@Country`\_`region = N'US'` , вероятно, обеспечит лучшую производительность для всех возможных значений параметра `@Country`\_`region` .</span><span class="sxs-lookup"><span data-stu-id="6742a-123">Because the most sales orders originate in the United States, a query plan that is generated for `@Country`\_`region = N'US'` would likely perform better for all possible values of the `@Country`\_`region` parameter.</span></span>  
  
 <span data-ttu-id="6742a-124">Чтобы решить эту проблему, измените хранимую процедуру и добавьте указание `OPTIMIZE FOR` в запрос.</span><span class="sxs-lookup"><span data-stu-id="6742a-124">You could address this problem by modifying the stored procedure to add the `OPTIMIZE FOR` query hint to the query.</span></span> <span data-ttu-id="6742a-125">Однако так как хранимая процедура находится в развернутом приложении, напрямую менять код приложения нельзя.</span><span class="sxs-lookup"><span data-stu-id="6742a-125">However, because the stored procedure is in a deployed application, you cannot directly modify the application code.</span></span> <span data-ttu-id="6742a-126">Вместо этого можно создать следующую структуру плана в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6742a-126">Instead, you can create the following plan guide in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
sp_create_plan_guide   
@name = N'Guide1',  
@stmt = N'SELECT *FROM Sales.SalesOrderHeader AS h,  
        Sales.Customer AS c,  
        Sales.SalesTerritory AS t  
        WHERE h.CustomerID = c.CustomerID   
            AND c.TerritoryID = t.TerritoryID  
            AND CountryRegionCode = @Country_region',  
@type = N'OBJECT',  
@module_or_batch = N'Sales.GetSalesOrderByCountry',  
@params = NULL,  
@hints = N'OPTION (OPTIMIZE FOR (@Country_region = N''US''))';  
```  
  
 <span data-ttu-id="6742a-127">При выполнении запроса, указанного в инструкции `sp_create_plan_guide` , этот запрос изменяется до оптимизации: в него добавляется предложение `OPTIMIZE FOR (@Country = N''US'')` .</span><span class="sxs-lookup"><span data-stu-id="6742a-127">When the query specified in the `sp_create_plan_guide` statement executes, the query is modified before optimization to include the `OPTIMIZE FOR (@Country = N''US'')` clause.</span></span>  
  
 <span data-ttu-id="6742a-128">Структура плана SQL</span><span class="sxs-lookup"><span data-stu-id="6742a-128">SQL plan guide</span></span>  
 <span data-ttu-id="6742a-129">Структура плана SQL соответствует запросам, выполняющимся в контексте изолированных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] и пакетов, не входящих ни в один объект базы данных.</span><span class="sxs-lookup"><span data-stu-id="6742a-129">An SQL plan guide matches queries that execute in the context of stand-alone [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and batches that are not part of a database object.</span></span> <span data-ttu-id="6742a-130">Структуры планов SQL также можно использовать для соответствия запросам с параметрами.</span><span class="sxs-lookup"><span data-stu-id="6742a-130">SQL-based plan guides can also be used to match queries that parameterize to a specified form.</span></span> <span data-ttu-id="6742a-131">Структуры планов SQL применяются к изолированным инструкциям [!INCLUDE[tsql](../../includes/tsql-md.md)] и пакетам.</span><span class="sxs-lookup"><span data-stu-id="6742a-131">SQL plan guides apply to stand-alone [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and batches.</span></span> <span data-ttu-id="6742a-132">Часто эти инструкции передаются приложением с помощью хранимой процедуры [sp_executesql](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6742a-132">Frequently, these statements are submitted by an application by using the [sp_executesql](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql) system stored procedure.</span></span> <span data-ttu-id="6742a-133">Например, рассмотрим следующий изолированный пакет:</span><span class="sxs-lookup"><span data-stu-id="6742a-133">For example, consider the following stand-alone batch:</span></span>  
  
```  
SELECT TOP 1 * FROM Sales.SalesOrderHeader ORDER BY OrderDate DESC;  
```  
  
 <span data-ttu-id="6742a-134">Чтобы избежать создания параллельного плана выполнения для этого запроса, создайте приведенную ниже структуру плана и присвойте указанию запроса `MAXDOP` значение `1` в параметре `@hints` .</span><span class="sxs-lookup"><span data-stu-id="6742a-134">To prevent a parallel execution plan from being generated on this query, create the following plan guide and set the `MAXDOP` query hint to `1` in the `@hints` parameter.</span></span>  
  
```  
sp_create_plan_guide   
@name = N'Guide2',   
@stmt = N'SELECT TOP 1 * FROM Sales.SalesOrderHeader ORDER BY OrderDate DESC',  
@type = N'SQL',  
@module_or_batch = NULL,   
@params = NULL,   
@hints = N'OPTION (MAXDOP 1)';  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6742a-135">Значения, передаваемые для аргументов `@module_or_batch` и `@params` инструкции `sp_create_plan guide` , должны соответствовать тексту настоящего запроса.</span><span class="sxs-lookup"><span data-stu-id="6742a-135">The values that are supplied for the `@module_or_batch` and `@params` arguments of the `sp_create_plan guide` statement must match the corresponding text submitted in the actual query.</span></span> <span data-ttu-id="6742a-136">Дополнительные сведения см. в разделах [sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) и [Использование приложения SQL Server Profiler для создания и проверки руководств планов](plan-guides.md).</span><span class="sxs-lookup"><span data-stu-id="6742a-136">For more information, see [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) and [Use SQL Server Profiler to Create and Test Plan Guides](plan-guides.md).</span></span>  
  
 <span data-ttu-id="6742a-137">Кроме того, структуры планов SQL можно создавать для запросов с той же параметризованной формой, если значением параметра базы данных PARAMETERIZATION является SET или FORCED либо если создана структура плана TEMPLATE, определяющая, что класс запросов должен быть параметризован.</span><span class="sxs-lookup"><span data-stu-id="6742a-137">SQL plan guides can also be created on queries that parameterize to the same form when the PARAMETERIZATION database option is SET to FORCED, or when a TEMPLATE plan guide is created specifying that a parameterized class of queries.</span></span>  
  
 <span data-ttu-id="6742a-138">TEMPLATE, структура плана</span><span class="sxs-lookup"><span data-stu-id="6742a-138">TEMPLATE plan guide</span></span>  
 <span data-ttu-id="6742a-139">Структура плана TEMPLATE соответствует изолированным инструкциям с параметрами.</span><span class="sxs-lookup"><span data-stu-id="6742a-139">A TEMPLATE plan guide matches stand-alone queries that parameterize to a specified form.</span></span> <span data-ttu-id="6742a-140">Эти структуры планов используются для замещения текущего параметра PARAMETERIZATION инструкции SET базы данных для класса запросов.</span><span class="sxs-lookup"><span data-stu-id="6742a-140">These plan guides are used to override the current PARAMETERIZATION database SET option of a database for a class of queries.</span></span>  
  
 <span data-ttu-id="6742a-141">Структуры планов TEMPLATE создаются в одной из следующих ситуаций.</span><span class="sxs-lookup"><span data-stu-id="6742a-141">You can create a TEMPLATE plan guide in either of the following situations:</span></span>  
  
-   <span data-ttu-id="6742a-142">Параметр базы данных PARAMETERIZATION инструкции SET хранит значение FORCED, но есть запросы, которые желательно скомпилировать в соответствии с правилами простой параметризации.</span><span class="sxs-lookup"><span data-stu-id="6742a-142">The PARAMETERIZATION database option is SET to FORCED, but there are queries you want compiled according to the rules of simple parameterization.</span></span>  
  
-   <span data-ttu-id="6742a-143">Параметр базы данных PARAMETERIZATION задается с помощью инструкции SET равным SIMPLE (настройка по умолчанию), но желательно произвести попытку принудительной параметризации определенного класса запросов.</span><span class="sxs-lookup"><span data-stu-id="6742a-143">The PARAMETERIZATION database option is SET to SIMPLE (the default setting), but you want forced parameterization to be tried on a class of queries.</span></span>  
  
## <a name="plan-guide-matching-requirements"></a><span data-ttu-id="6742a-144">Требования по соответствию для структур планов</span><span class="sxs-lookup"><span data-stu-id="6742a-144">Plan Guide Matching Requirements</span></span>  
 <span data-ttu-id="6742a-145">Структуры планов действительны в области видимости базы данных, в которой они создаются.</span><span class="sxs-lookup"><span data-stu-id="6742a-145">Plan guides are scoped to the database in which they are created.</span></span> <span data-ttu-id="6742a-146">Поэтому с запросом могут быть согласованы только структуры планов, находящиеся в базе данных, которая является текущей при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="6742a-146">Therefore, only plan guides that are in the database that is current when a query executes can be matched to the query.</span></span> <span data-ttu-id="6742a-147">Например, если [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] является текущей базой данных и выполняется нижеследующий запрос:</span><span class="sxs-lookup"><span data-stu-id="6742a-147">For example, if [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] is the current database and the following query executes:</span></span>  
  
 `SELECT FirstName, LastName FROM Person.Person;`  
  
 <span data-ttu-id="6742a-148">Только руководства планов в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] подлежат сопоставлению с этим запросом.</span><span class="sxs-lookup"><span data-stu-id="6742a-148">Only plan guides in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database are eligible to be matched to this query.</span></span> <span data-ttu-id="6742a-149">Но если [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] является текущей базой данных и выполняются нижеследующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="6742a-149">However, if [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] is the current database and the following statements are run:</span></span>  
  
 `USE DB1;`  
  
 `SELECT FirstName, LastName FROM Person.Person;`  
  
 <span data-ttu-id="6742a-150">Для согласования с запросом применимы только структуры планов в `DB1` , поскольку запрос выполняется в контексте `DB1`.</span><span class="sxs-lookup"><span data-stu-id="6742a-150">Only plan guides in `DB1` are eligible to be matched to the query because the query is executing in the context of `DB1`.</span></span>  
  
 <span data-ttu-id="6742a-151">В структурах плана, основанных на SQL или TEMPLATE, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] посимвольно сравнивает значения аргументов @module_or_batch и @params, переданных в запросе.</span><span class="sxs-lookup"><span data-stu-id="6742a-151">For SQL- or TEMPLATE-based plan guides, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] matches the values for the @module_or_batch and @params arguments to a query by comparing the two values character by character.</span></span> <span data-ttu-id="6742a-152">Это означает, что необходимо предоставить текст точно в том же виде, в каком [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] получит его в действительном пакете.</span><span class="sxs-lookup"><span data-stu-id="6742a-152">This means you must provide the text exactly as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] receives it in the actual batch.</span></span>  
  
 <span data-ttu-id="6742a-153">Если @type = 'SQL' и @module_or_batch имеет значение NULL, параметр @module_or_batch получает значение @stmt. Из этого следует, что значение для *statement_text* должно быть предоставлено в идентичном формате, символ к символу, так как оно передается в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6742a-153">When @type = 'SQL' and @module_or_batch is set to NULL, the value of @module_or_batch is set to the value of @stmt. This means that the value for *statement_text* must be provided in the identical format, character-for-character, as it is submitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6742a-154">Для упрощения соответствия формата внутренние преобразования не выполняются.</span><span class="sxs-lookup"><span data-stu-id="6742a-154">No internal conversion is performed to facilitate this match.</span></span>  
  
 <span data-ttu-id="6742a-155">Если к инструкции могут быть применены и обычная структура плана (SQL или OBJECT), и структура плана TEMPLATE, то используется только обычная структура плана.</span><span class="sxs-lookup"><span data-stu-id="6742a-155">When both a regular (SQL or OBJECT) plan guide and a TEMPLATE plan guide can apply to a statement, only the regular plan guide will be used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6742a-156">Пакет, содержащий инструкцию, для которой необходимо создать структуру плана, не может содержать инструкцию USE *database* .</span><span class="sxs-lookup"><span data-stu-id="6742a-156">The batch that contains the statement on which you want to create a plan guide cannot contain a USE *database* statement.</span></span>  
  
## <a name="plan-guide-effect-on-the-plan-cache"></a><span data-ttu-id="6742a-157">Влияние структуры плана на кэш планов</span><span class="sxs-lookup"><span data-stu-id="6742a-157">Plan Guide Effect on the Plan Cache</span></span>  
 <span data-ttu-id="6742a-158">Создание структуры плана в модуле стирает план запроса для этого модуля из кэша планов.</span><span class="sxs-lookup"><span data-stu-id="6742a-158">Creating a plan guide on a module removes the query plan for that module from the plan cache.</span></span> <span data-ttu-id="6742a-159">Создание структуры плана типа OBJECT или SQL в потоке стирает план запроса для потока, который имеет такое же значение хеш-функции.</span><span class="sxs-lookup"><span data-stu-id="6742a-159">Creating a plan guide of type OBJECT or SQL on a batch removes the query plan for a batch that has the same hash value.</span></span> <span data-ttu-id="6742a-160">Создание структуры плана типа TEMPLATE стирает все потоки с одним оператором из кэша планов через базу данных.</span><span class="sxs-lookup"><span data-stu-id="6742a-160">Creating a plan guide of type TEMPLATE removes all single-statement batches from the plan cache within that database.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6742a-161">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="6742a-161">Related Tasks</span></span>  
  
|<span data-ttu-id="6742a-162">Задача</span><span class="sxs-lookup"><span data-stu-id="6742a-162">Task</span></span>|<span data-ttu-id="6742a-163">Раздел</span><span class="sxs-lookup"><span data-stu-id="6742a-163">Topic</span></span>|  
|----------|-----------|  
|<span data-ttu-id="6742a-164">Описано, как создать структуру плана.</span><span class="sxs-lookup"><span data-stu-id="6742a-164">Describes how to create a plan guide.</span></span>|[<span data-ttu-id="6742a-165">Создание структуры плана</span><span class="sxs-lookup"><span data-stu-id="6742a-165">Create a New Plan Guide</span></span>](create-a-new-plan-guide.md)|  
|<span data-ttu-id="6742a-166">Описано, как создать структуру плана для параметризованных запросов.</span><span class="sxs-lookup"><span data-stu-id="6742a-166">Describes how to create a plan guide for parameterized queries.</span></span>|[<span data-ttu-id="6742a-167">Создание структуры плана для параметризованных запросов</span><span class="sxs-lookup"><span data-stu-id="6742a-167">Create a Plan Guide for Parameterized Queries</span></span>](create-a-plan-guide-for-parameterized-queries.md)|  
|<span data-ttu-id="6742a-168">Описано, как управлять режимом параметризации запроса с использованием структур планов.</span><span class="sxs-lookup"><span data-stu-id="6742a-168">Describes how to control query parameterization behavior by using plan guides.</span></span>|[<span data-ttu-id="6742a-169">Указание механизма параметризации запросов с помощью структур плана</span><span class="sxs-lookup"><span data-stu-id="6742a-169">Specify Query Parameterization Behavior by Using Plan Guides</span></span>](specify-query-parameterization-behavior-by-using-plan-guides.md)|  
|<span data-ttu-id="6742a-170">Описано, как включить постоянный план запроса в структуру плана.</span><span class="sxs-lookup"><span data-stu-id="6742a-170">Describes how to include a fixed query plan in a plan guide.</span></span>|[<span data-ttu-id="6742a-171">Применение фиксированного плана запроса к структуре плана</span><span class="sxs-lookup"><span data-stu-id="6742a-171">Apply a Fixed Query Plan to a Plan Guide</span></span>](apply-a-fixed-query-plan-to-a-plan-guide.md)|  
|<span data-ttu-id="6742a-172">Описано, как задать указания запросов в структуре плана.</span><span class="sxs-lookup"><span data-stu-id="6742a-172">Describes how to specify query hints in a plan guide.</span></span>|[<span data-ttu-id="6742a-173">Присоединение указаний запросов к структуре плана</span><span class="sxs-lookup"><span data-stu-id="6742a-173">Attach Query Hints to a Plan Guide</span></span>](attach-query-hints-to-a-plan-guide.md)|  
|<span data-ttu-id="6742a-174">Описано, как просматривать свойства структуры плана.</span><span class="sxs-lookup"><span data-stu-id="6742a-174">Describes how to view plan guide properties.</span></span>|[<span data-ttu-id="6742a-175">Просмотр свойств структуры плана</span><span class="sxs-lookup"><span data-stu-id="6742a-175">View Plan Guide Properties</span></span>](view-plan-guide-properties.md)|  
|<span data-ttu-id="6742a-176">Описано, как использовать профилировщик SQL Server для создания и проверки структур планов.</span><span class="sxs-lookup"><span data-stu-id="6742a-176">Describes how to use SQL Server Profiler to create and test plan guides.</span></span>|[<span data-ttu-id="6742a-177">Использование приложения SQL Server Profiler для создания и проверки структур плана</span><span class="sxs-lookup"><span data-stu-id="6742a-177">Use SQL Server Profiler to Create and Test Plan Guides</span></span>](plan-guides.md)|  
|<span data-ttu-id="6742a-178">Описано, как проверять структуры планов.</span><span class="sxs-lookup"><span data-stu-id="6742a-178">Describes how to validate plan guides.</span></span>|[<span data-ttu-id="6742a-179">Проверка структур плана после обновления</span><span class="sxs-lookup"><span data-stu-id="6742a-179">Validate Plan Guides After Upgrade</span></span>](validate-plan-guides-after-upgrade.md)|  
  
## <a name="see-also"></a><span data-ttu-id="6742a-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="6742a-180">See Also</span></span>  
 <span data-ttu-id="6742a-181">[sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6742a-181">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="6742a-182">[sp_create_plan_guide_from_handle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6742a-182">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span></span>  
 <span data-ttu-id="6742a-183">[sp_control_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6742a-183">[sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="6742a-184">[sys.plan_guides (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6742a-184">[sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql) </span></span>  
 [<span data-ttu-id="6742a-185">sys.fn_validate_plan_guide (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6742a-185">sys.fn_validate_plan_guide &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql)  
  
  
