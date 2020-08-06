---
title: Применение фиксированного плана запроса к структуре плана | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: bbf401f9-af7c-48e7-8a43-bf25e8af2fd7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 318955c4d0550e311873d8b4a6f79f72e04ac8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729386"
---
# <a name="apply-a-fixed-query-plan-to-a-plan-guide"></a><span data-ttu-id="70089-102">Применение фиксированного плана запроса к структуре плана</span><span class="sxs-lookup"><span data-stu-id="70089-102">Apply a Fixed Query Plan to a Plan Guide</span></span>
  <span data-ttu-id="70089-103">Можно применить фиксированный план запроса к руководству плана типов OBJECT или SQL.</span><span class="sxs-lookup"><span data-stu-id="70089-103">You can apply a fixed query plan to a plan guide of type OBJECT or SQL.</span></span> <span data-ttu-id="70089-104">Структуры планов, применяющие фиксированные планы запроса, удобно использовать в тех случаях, когда известно, что есть план выполнения, который работает с большей производительностью, чем выбранный оптимизатором для конкретного запроса.</span><span class="sxs-lookup"><span data-stu-id="70089-104">Plan guides that apply a fixed query plan are useful when you know about an existing execution plan that performs better than the one selected by the optimizer for a particular query.</span></span>  
  
 <span data-ttu-id="70089-105">В следующем примере создается структура плана для простой нерегламентированной инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="70089-105">The following example creates a plan guide for a simple ad hoc SQL statement.</span></span> <span data-ttu-id="70089-106">Требуемый план запроса для этого оператора представлен в структуре плана путем указания XML Showplan для запроса непосредственно в параметре `@hints` .</span><span class="sxs-lookup"><span data-stu-id="70089-106">The desired query plan for this statement is provided in the plan guide by specifying the XML Showplan for the query directly in the `@hints` parameter.</span></span> <span data-ttu-id="70089-107">В примере сначала выполняется инструкция SQL для создания плана в кэше планов.</span><span class="sxs-lookup"><span data-stu-id="70089-107">The example first executes the SQL statement to generate a plan in the plan cache.</span></span> <span data-ttu-id="70089-108">В этом примере допустим, что созданный план является желаемым планом и не требуется дополнительной настройки запросов.</span><span class="sxs-lookup"><span data-stu-id="70089-108">For the purposes of this example, it is assumed that the generated plan is the desired plan and no additional query tuning is required.</span></span> <span data-ttu-id="70089-109">Данные XML Showplan для запроса необходимо получить с помощью запроса к динамическим административным представлениям `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`и `sys.dm_exec_text_query_plan` и присвоить переменной `@xml_showplan` .</span><span class="sxs-lookup"><span data-stu-id="70089-109">The XML Showplan for the query is obtained by querying the `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`, and `sys.dm_exec_text_query_plan` dynamic management views and is assigned to the `@xml_showplan` variable.</span></span> <span data-ttu-id="70089-110">Переменная `@xml_showplan` затем передается оператору `sp_create_plan_guide` в параметре `@hints` .</span><span class="sxs-lookup"><span data-stu-id="70089-110">The `@xml_showplan` variable is then passed to the `sp_create_plan_guide` statement in the `@hints` parameter.</span></span> <span data-ttu-id="70089-111">Также можно создать структуру плана на основе плана запроса в кэше планов, используя хранимую процедуру [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="70089-111">Or, you can create a plan guide from a query plan in the plan cache by using the [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;  
GO  
DECLARE @xml_showplan nvarchar(max);  
SET @xml_showplan = (SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%');  
  
EXEC sp_create_plan_guide   
    @name = N'Guide1_from_XML_showplan',   
    @stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',   
    @type = N'SQL',  
    @module_or_batch = NULL,   
    @params = NULL,   
    @hints = @xml_showplan;  
GO  
```  
  
  
