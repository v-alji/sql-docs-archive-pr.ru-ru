---
title: Создание структуры плана для параметризованных запросов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- parameterized queries, plan guides for
- plan guides [SQL Server], parameterized queries
ms.assetid: b532ae16-66e7-4641-9bc8-b0d805853477
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 565610826f704274724ea05d821205a5b3391060
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668830"
---
# <a name="create-a-plan-guide-for-parameterized-queries"></a><span data-ttu-id="5ca95-102">Создание руководства плана для параметризованных запросов</span><span class="sxs-lookup"><span data-stu-id="5ca95-102">Create a Plan Guide for Parameterized Queries</span></span>
  <span data-ttu-id="5ca95-103">Структура плана TEMPLATE соответствует изолированным инструкциям с параметрами.</span><span class="sxs-lookup"><span data-stu-id="5ca95-103">A TEMPLATE plan guide matches stand-alone queries that parameterize to a specified form.</span></span>  
  
 <span data-ttu-id="5ca95-104">В приведенном ниже примере создается структура плана, которой сопоставляется запрос заданной параметризованной формы и которое вынуждает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] параметризовать поступающие запросы.</span><span class="sxs-lookup"><span data-stu-id="5ca95-104">The following example creates a plan guide that matches any query that parameterizes to a specified form, and directs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to force parameterization of the query.</span></span> <span data-ttu-id="5ca95-105">Два приведенных ниже запроса являются синтаксическими эквивалентами, однако различаются своими значениями постоянных литералов.</span><span class="sxs-lookup"><span data-stu-id="5ca95-105">The following two queries are syntactically equivalent, but differ only in their constant literal values.</span></span>  
  
```  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45639;  
  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45640;  
```  
  
 <span data-ttu-id="5ca95-106">Ниже представлена структура плана для параметризованного запроса.</span><span class="sxs-lookup"><span data-stu-id="5ca95-106">Here is the plan guide on the parameterized form of the query:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'TemplateGuide1',  
    @stmt = N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
              INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
                  ON h.SalesOrderID = d.SalesOrderID  
              WHERE h.SalesOrderID = @0',  
    @type = N'TEMPLATE',  
    @module_or_batch = NULL,  
    @params = N'@0 int',  
    @hints = N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="5ca95-107">В предыдущем примере значение параметра `@stmt` является параметризованной формой запроса.</span><span class="sxs-lookup"><span data-stu-id="5ca95-107">In the previous example, the value for the `@stmt` parameter is the parameterized form of the query.</span></span> <span data-ttu-id="5ca95-108">Единственным надежным способом выяснения указанного значения для использования в процедуре sp_create_plan_guide является использование системной хранимой процедуры [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5ca95-108">The only reliable way to obtain this value for use in sp_create_plan_guide is to use the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span> <span data-ttu-id="5ca95-109">Следующий скрипт можно использовать как для получения параметризированного запроса, так и для дальнейшего создания по нему структуры плана:</span><span class="sxs-lookup"><span data-stu-id="5ca95-109">The following script can be used both to obtain the parameterized query and then create a plan guide on it.</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
      INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
          ON h.SalesOrderID = d.SalesOrderID  
      WHERE h.SalesOrderID = 45639;',  
    @stmt OUTPUT,   
    @params OUTPUT  
EXEC sp_create_plan_guide N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5ca95-110">Значения постоянных литералов аргумента `@stmt` , передаваемого в процедуру `sp_get_query_template` , определяют тип данных для аргумента, заменяющего указанные литералы.</span><span class="sxs-lookup"><span data-stu-id="5ca95-110">The value of the constant literals in the `@stmt` parameter passed to `sp_get_query_template` might affect the data type that is chosen for the parameter that replaces the literal.</span></span> <span data-ttu-id="5ca95-111">Это влияет на совпадение структур планов.</span><span class="sxs-lookup"><span data-stu-id="5ca95-111">This will affect plan guide matching.</span></span> <span data-ttu-id="5ca95-112">Возможно, придется создать несколько структур плана для обработки различных диапазонов значений аргумента.</span><span class="sxs-lookup"><span data-stu-id="5ca95-112">You may have to create more than one plan guide to handle different parameter value ranges.</span></span>  
  
 <span data-ttu-id="5ca95-113">Структуры планов TEMPLATE также можно использовать совместно со структурами планов SQL.</span><span class="sxs-lookup"><span data-stu-id="5ca95-113">You can also use TEMPLATE plan guides together with SQL plan guides.</span></span> <span data-ttu-id="5ca95-114">Например, можно создать структуру плана TEMPLATE, чтобы убедиться, что класс запросов будет параметризован.</span><span class="sxs-lookup"><span data-stu-id="5ca95-114">For example, you can create a TEMPLATE plan guide to make sure that a class of queries is parameterized.</span></span> <span data-ttu-id="5ca95-115">Затем можно создать руководство плана SQL для параметризованной формы запроса.</span><span class="sxs-lookup"><span data-stu-id="5ca95-115">You can then create an SQL plan guide on the parameterized form of that query.</span></span>  
  
  
