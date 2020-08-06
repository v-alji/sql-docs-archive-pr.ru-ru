---
title: Указание механизма параметризации запросов с помощью структур плана | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- TEMPLATE plan guide
- PARAMETERIZATION FORCED option
- PARAMETERIZATION option
- PARAMETERIZATION SIMPLE option
- parameterization [SQL Server]
- overriding parameterization behavior
- plan guides [SQL Server], parameterization
- parameterized queries [SQL Server]
ms.assetid: f0f738ff-2819-4675-a8c8-1eb6c210a7e6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f595b9f0e0a6d7bceffc5cb283c60b6f40e025b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668822"
---
# <a name="specify-query-parameterization-behavior-by-using-plan-guides"></a><span data-ttu-id="86bce-102">Указание механизма параметризации запросов с помощью структур плана</span><span class="sxs-lookup"><span data-stu-id="86bce-102">Specify Query Parameterization Behavior by Using Plan Guides</span></span>
  <span data-ttu-id="86bce-103">Если для параметра базы данных PARAMETERIZATION установлено значение SIMPLE, оптимизатор запросов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может выбрать параметризацию запросов.</span><span class="sxs-lookup"><span data-stu-id="86bce-103">When the PARAMETERIZATION database option is set to SIMPLE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer may choose to parameterize the queries.</span></span> <span data-ttu-id="86bce-104">Это значит, что все литеральные значения, содержащиеся в запросе, заменяются параметрами.</span><span class="sxs-lookup"><span data-stu-id="86bce-104">This means that any literal values that are contained in a query are substituted with parameters.</span></span> <span data-ttu-id="86bce-105">Этот процесс называется простой параметризацией.</span><span class="sxs-lookup"><span data-stu-id="86bce-105">This process is referred to as simple parameterization.</span></span> <span data-ttu-id="86bce-106">При применении простой (SIMPLE) параметризации невозможно контролировать, какие запросы параметризуются, а какие нет.</span><span class="sxs-lookup"><span data-stu-id="86bce-106">When SIMPLE parameterization is in effect, you cannot control which queries are parameterized and which queries are not.</span></span> <span data-ttu-id="86bce-107">Однако можно параметризовать все запросы в базе данных, присвоив параметру базы данных PARAMETERIZATION значение FORCED.</span><span class="sxs-lookup"><span data-stu-id="86bce-107">However, you can specify that all queries in a database be parameterized by setting the PARAMETERIZATION database option to FORCED.</span></span> <span data-ttu-id="86bce-108">Этот процесс называется принудительной параметризацией.</span><span class="sxs-lookup"><span data-stu-id="86bce-108">This process is referred to as forced parameterization.</span></span>  
  
 <span data-ttu-id="86bce-109">Механизм параметризации в базе данных можно переопределить с помощью структур планов следующим путем.</span><span class="sxs-lookup"><span data-stu-id="86bce-109">You can override the parameterization behavior of a database by using plan guides in the following ways:</span></span>  
  
-   <span data-ttu-id="86bce-110">Если значение параметра базы данных PARAMETERIZATION равно SIMPLE, можно указать, чтобы попытки принудительной параметризации выполнялись в определенном классе запросов.</span><span class="sxs-lookup"><span data-stu-id="86bce-110">When the PARAMETERIZATION database option is set to SIMPLE, you can specify that forced parameterization is attempted on a certain class of queries.</span></span> <span data-ttu-id="86bce-111">Это можно сделать путем создания структуры плана TEMPLATE для параметризованной формы запроса и задания указания запроса PARAMETERIZATION FORCED с помощью хранимой процедуры [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="86bce-111">You do this by creating a TEMPLATE plan guide on the parameterized form of the query, and specifying the PARAMETERIZATION FORCED query hint in the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure.</span></span> <span data-ttu-id="86bce-112">Такая разновидность структуры плана представляет собой способ включения принудительной параметризации только для определенного класса запросов, а не для всех.</span><span class="sxs-lookup"><span data-stu-id="86bce-112">You can consider this kind of plan guide as a way to enable forced parameterization only on a certain class of queries, instead of all queries.</span></span>  
  
-   <span data-ttu-id="86bce-113">Если значение параметра базы данных PARAMETERIZATION равно FORCED, можно указать, чтобы для определенного класса запросов выполнялись только попытки простой параметризации вместо принудительной.</span><span class="sxs-lookup"><span data-stu-id="86bce-113">When the PARAMETERIZATION database option is set to FORCED, you can specify that for a certain class of queries, only simple parameterization is attempted, not forced parameterization.</span></span> <span data-ttu-id="86bce-114">Это можно сделать путем создания структуры плана TEMPLATE для формы запроса с принудительной параметризацией и задания указания запроса PARAMETERIZATION SIMPLE с помощью хранимой процедуры **sp_create_plan_guide**.</span><span class="sxs-lookup"><span data-stu-id="86bce-114">You do this by creating a TEMPLATE plan guide on the force-parameterized form of the query, and specifying the PARAMETERIZATION SIMPLE query hint in **sp_create_plan_guide**.</span></span>  
  
 <span data-ttu-id="86bce-115">Рассмотрим следующий запрос к базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="86bce-115">Consider the following query on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT pi.ProductID, SUM(pi.Quantity) AS Total  
FROM Production.ProductModel AS pm   
    INNER JOIN Production.ProductInventory AS pi   
        ON pm.ProductModelID = pi.ProductID   
WHERE pi.ProductID = 101   
GROUP BY pi.ProductID, pi.Quantity HAVING SUM(pi.Quantity) > 50;  
```  
  
 <span data-ttu-id="86bce-116">Администратор базы данных решил не включать принудительную параметризацию для всех запросов к базе данных.</span><span class="sxs-lookup"><span data-stu-id="86bce-116">As a database administrator, you have determined that you do not want to enable forced parameterization on all queries in the database.</span></span> <span data-ttu-id="86bce-117">Однако необходимо избегать затрат на компиляцию для всех запросов, синтаксически эквивалентных предыдущему и различающихся только литеральными значениями констант.</span><span class="sxs-lookup"><span data-stu-id="86bce-117">However, you do want to avoid compilation costs on all queries that are syntactically equivalent to the previous query, but differ only in their constant literal values.</span></span> <span data-ttu-id="86bce-118">Иными словами, необходимо реализовать параметризацию запроса таким образом, чтобы план для данного вида запроса использовался повторно.</span><span class="sxs-lookup"><span data-stu-id="86bce-118">In other words, you want the query to be parameterized so that a query plan for this kind of query is reused.</span></span> <span data-ttu-id="86bce-119">В этом случае нужно выполнить следующее.</span><span class="sxs-lookup"><span data-stu-id="86bce-119">In this case, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="86bce-120">Получить параметризованную форму запроса.</span><span class="sxs-lookup"><span data-stu-id="86bce-120">Retrieve the parameterized form of the query.</span></span> <span data-ttu-id="86bce-121">Единственным безопасным путем получения этого значения для последующего использования в процедуре **sp_create_plan_guide** является использование системной хранимой процедуры [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="86bce-121">The only safe way to obtain this value for use in **sp_create_plan_guide** is by using the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span>  
  
2.  <span data-ttu-id="86bce-122">Создать структуру плана для параметризованной формы запроса, задав указание запроса PARAMETERIZATION FORCED.</span><span class="sxs-lookup"><span data-stu-id="86bce-122">Create the plan guide on the parameterized form of the query, specifying the PARAMETERIZATION FORCED query hint.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="86bce-123">В ходе параметризации запроса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] присваивает параметрам, заменяющим литеральные значения, определенный тип данных в зависимости от значения и размера литерала.</span><span class="sxs-lookup"><span data-stu-id="86bce-123">As part of parameterizing a query, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns a data type to the parameters that replace the literal values, depending on the value and size of the literal.</span></span> <span data-ttu-id="86bce-124">Тот же процесс выполняется со значениями константных литералов, передаваемых в **@stmt** выходной параметр **sp_get_query_template**.</span><span class="sxs-lookup"><span data-stu-id="86bce-124">The same process occurs to the value of the constant literals passed to the **@stmt** output parameter of **sp_get_query_template**.</span></span> <span data-ttu-id="86bce-125">Так как тип данных, указанный в **@params** аргументе **sp_create_plan_guide** , должен соответствовать значению запроса, заданному в параметре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , может потребоваться создать более одной структуры плана, чтобы охватить полный диапазон возможных значений параметров для запроса.</span><span class="sxs-lookup"><span data-stu-id="86bce-125">Because the data type specified in the **@params** argument of **sp_create_plan_guide** must match that of the query as it is parameterized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you may have to create more than one plan guide to cover the complete range of possible parameter values for the query.</span></span>  
  
 <span data-ttu-id="86bce-126">Следующий скрипт можно использовать как для получения параметризированного запроса, так и для дальнейшего создания по нему структуры плана:</span><span class="sxs-lookup"><span data-stu-id="86bce-126">The following script can be used both to obtain the parameterized query and then create a plan guide on it:</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT pi.ProductID, SUM(pi.Quantity) AS Total   
      FROM Production.ProductModel AS pm   
      INNER JOIN Production.ProductInventory AS pi ON pm.ProductModelID = pi.ProductID   
      WHERE pi.ProductID = 101   
      GROUP BY pi.ProductID, pi.Quantity   
      HAVING sum(pi.Quantity) > 50',  
    @stmt OUTPUT,   
    @params OUTPUT;  
EXEC sp_create_plan_guide   
    N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="86bce-127">Подобным образом в базе данных, в которой уже включена принудительная параметризация, можно гарантировать, что указанный в качестве примера запрос и другие синтаксически ему эквивалентные, в которых различаются только литеральные значения констант, будут параметризованы согласно правилам простой параметризации.</span><span class="sxs-lookup"><span data-stu-id="86bce-127">Similarly, in a database in which forced parameterization is already enabled, you can make sure that the sample query, and others that are syntactically equivalent, except for their constant literal values, are parameterized according to the rules of simple parameterization.</span></span> <span data-ttu-id="86bce-128">Для этого следует указать PARAMETERIZATION SIMPLE вместо PARAMETERIZATION FORCED в предложении OPTION.</span><span class="sxs-lookup"><span data-stu-id="86bce-128">To do this, specify PARAMETERIZATION SIMPLE instead of PARAMETERIZATION FORCED in the OPTION clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86bce-129">С помощью структур плана TEMPLATE осуществляется сопоставление инструкций с запросами, поступающими в пакетах, каждый из которых состоит только из одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="86bce-129">TEMPLATE plan guides match statements to queries submitted in batches that consist of a single statement only.</span></span> <span data-ttu-id="86bce-130">Инструкции, находящиеся в пакетах с несколькими инструкциями, не подлежат сопоставлению со структурами планов TEMPLATE.</span><span class="sxs-lookup"><span data-stu-id="86bce-130">Statements inside multistatement batches are not eligible to be matched by TEMPLATE plan guides.</span></span>  
  
  
