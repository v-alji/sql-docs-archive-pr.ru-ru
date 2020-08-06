---
title: Использование приложения SQL Server Profiler для создания и проверки структур плана | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- checking plan guides
- plan guides [SQL Server], testing
- plan guides [SQL Server], SQL Server Profiler
- matching queries to plan guides [SQL Server]
- testing plan guides
- SQL Server Profiler, plan guides
- plan guides [SQL Server], creating
- capturing query text [SQL Server]
- verifying plan guides
- Profiler [SQL Server Profiler], plan guides
- query-to-plan guide matching [SQL Server]
ms.assetid: 7018dbf0-1a1a-411a-88af-327bedf9cfbd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 543905343d74c9fbabe5f671d9021657ea5f76b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732593"
---
# <a name="use-sql-server-profiler-to-create-and-test-plan-guides"></a><span data-ttu-id="9aa95-102">Использование приложения SQL Server Profiler для создания и проверки руководств планов</span><span class="sxs-lookup"><span data-stu-id="9aa95-102">Use SQL Server Profiler to Create and Test Plan Guides</span></span>
  <span data-ttu-id="9aa95-103">При создании структуры плана приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] может применяться для извлечения точного текста запроса, который может использоваться в аргументе *statement_text* хранимой процедуры **sp_create_plan_guide** .</span><span class="sxs-lookup"><span data-stu-id="9aa95-103">When you are creating a plan guide, you can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to capture the exact query text for use in the *statement_text* argument of the **sp_create_plan_guide** stored procedure.</span></span> <span data-ttu-id="9aa95-104">Тем самым гарантируется, что во время компиляции структура плана будет соответствовать запросу.</span><span class="sxs-lookup"><span data-stu-id="9aa95-104">This helps make sure that the plan guide will be matched to the query at compile time.</span></span> <span data-ttu-id="9aa95-105">После создания структуры плана приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] может также использоваться для проверки того, что структура плана действительно соответствует запросу.</span><span class="sxs-lookup"><span data-stu-id="9aa95-105">After the plan guide is created, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can also be used to test that the plan guide is, in fact, being matched to the query.</span></span> <span data-ttu-id="9aa95-106">Обычно проверка структуры плана приложением [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] нужна, чтобы убедиться в том, что запрос соответствует структуре плана.</span><span class="sxs-lookup"><span data-stu-id="9aa95-106">Generally, you should test plan guides by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to verify that your query is being matched to your plan guide.</span></span>  
  
## <a name="capturing-query-text-by-using-sql-server-profiler"></a><span data-ttu-id="9aa95-107">Извлечение текста запроса при помощи приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="9aa95-107">Capturing Query Text by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="9aa95-108">Если выполняется запрос и при помощи приложения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] извлекается текст точно в том виде, в котором он был представлен [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], можно создать структуру плана типа SQL или TEMPLATE, которое будет точно соответствовать тексту запроса.</span><span class="sxs-lookup"><span data-stu-id="9aa95-108">If you run a query and capture the text exactly as it was submitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can create a plan guide of type SQL or TEMPLATE that will match the query text exactly.</span></span> <span data-ttu-id="9aa95-109">Благодаря этому структура плана может использоваться оптимизатором запросов.</span><span class="sxs-lookup"><span data-stu-id="9aa95-109">This makes sure that the plan guide is used by the query optimizer.</span></span>  
  
 <span data-ttu-id="9aa95-110">Рассмотрим следующий запрос, представленный приложением в виде изолированного пакета:</span><span class="sxs-lookup"><span data-stu-id="9aa95-110">Consider the following query that is submitted by an application as a stand-alone batch:</span></span>  
  
```  
SELECT COUNT(*) AS c  
FROM Sales.SalesOrderHeader AS h  
INNER JOIN Sales.SalesOrderDetail AS d  
  ON h.SalesOrderID = d.SalesOrderID  
WHERE h.OrderDate BETWEEN '20000101' and '20050101';  
```  
  
 <span data-ttu-id="9aa95-111">Предположим, необходимо, чтобы запрос был выполнен при помощи операции соединения слиянием, но SHOWPLAN указывает на то, что запрос не использует соединение слиянием.</span><span class="sxs-lookup"><span data-stu-id="9aa95-111">Suppose you want this query to execute using a merge join operation, but SHOWPLAN indicates that the query is not using a merge join.</span></span> <span data-ttu-id="9aa95-112">Запрос нельзя изменить непосредственно в приложении, поэтому создается структура плана, определяющая, что указание запроса MERGE JOIN должно быть присоединено к запросу во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="9aa95-112">You cannot change the query directly in the application, so instead you create a plan guide to specify that the MERGE JOIN query hint be appended to the query at compile time.</span></span>  
  
 <span data-ttu-id="9aa95-113">Для извлечения текста запроса точно в том виде, в каком его получает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="9aa95-113">To capture the text of the query exactly as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] receives it, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9aa95-114">Запустите трассировку в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , выбрав тип события **SQL:BatchStarting** .</span><span class="sxs-lookup"><span data-stu-id="9aa95-114">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making sure that the **SQL:BatchStarting** event type is selected.</span></span>  
  
2.  <span data-ttu-id="9aa95-115">Позвольте приложению выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="9aa95-115">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="9aa95-116">Приостановите трассировку приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9aa95-116">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="9aa95-117">Щелкните событие **SQL:BatchStarting** , соответствующее запросу.</span><span class="sxs-lookup"><span data-stu-id="9aa95-117">Click the **SQL:BatchStarting** event that corresponds to the query.</span></span>  
  
5.  <span data-ttu-id="9aa95-118">Щелкните событие правой кнопкой мыши и выберите **Извлечь данные события**.</span><span class="sxs-lookup"><span data-stu-id="9aa95-118">Right-click and select **Extract Event Data**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9aa95-119">Не предпринимайте попыток скопировать текст пакета, выделяя его из нижней панели окна трассировки профайлера.</span><span class="sxs-lookup"><span data-stu-id="9aa95-119">Do not try to copy the batch text by selecting it from the lower pane of the Profiler trace window.</span></span> <span data-ttu-id="9aa95-120">Это может привести к несоответствию структуры плана исходному пакету.</span><span class="sxs-lookup"><span data-stu-id="9aa95-120">This might cause the plan guide that you create to not match the original batch.</span></span>  
  
6.  <span data-ttu-id="9aa95-121">Сохраните данные события в файле.</span><span class="sxs-lookup"><span data-stu-id="9aa95-121">Save the event data to a file.</span></span> <span data-ttu-id="9aa95-122">Это и будет текст пакета.</span><span class="sxs-lookup"><span data-stu-id="9aa95-122">This is the batch text.</span></span>  
  
7.  <span data-ttu-id="9aa95-123">Откройте в блокноте файл текста пакета и скопируйте текст в буфер копирования и вставки.</span><span class="sxs-lookup"><span data-stu-id="9aa95-123">Open the batch text file in Notepad and copy the text to the copy and paste buffer.</span></span>  
  
8.  <span data-ttu-id="9aa95-124">Создайте структуру плана и вставьте скопированный текст внутри кавычек (**''**), заданных для аргумента **@stmt** .</span><span class="sxs-lookup"><span data-stu-id="9aa95-124">Create the plan guide and paste the copied text inside the quotation marks (**''**) specified for the **@stmt** argument.</span></span> <span data-ttu-id="9aa95-125">Необходимо экранировать любые одинарные кавычки в **@stmt** аргументе, поставив перед ними еще одну одинарную кавычку.</span><span class="sxs-lookup"><span data-stu-id="9aa95-125">You must escape any single quotation marks in the **@stmt** argument by preceding them with another single quotation mark.</span></span> <span data-ttu-id="9aa95-126">Следите за тем, чтобы при вставке одинарных кавычек не были вставлены или удалены другие символы.</span><span class="sxs-lookup"><span data-stu-id="9aa95-126">Be careful not to add or remove any other characters when you insert these single quotation marks.</span></span> <span data-ttu-id="9aa95-127">Например, литерал даты **'** 20000101 **'** должен быть указан в следующем формате: **''** 20000101 **''** .</span><span class="sxs-lookup"><span data-stu-id="9aa95-127">For example, the date literal **'** 20000101 **'** must be delimited as **''** 20000101 **''**.</span></span>  
  
 <span data-ttu-id="9aa95-128">Далее приводится структура плана:</span><span class="sxs-lookup"><span data-stu-id="9aa95-128">Here is the plan guide:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'MyGuide1',  
    @stmt = N'<paste the text copied from the batch text file here>',  
    @type = N'SQL',  
    @module_or_batch = NULL,  
    @params = NULL,  
    @hints = N'OPTION (MERGE JOIN)';  
```  
  
## <a name="testing-plan-guides-by-using-sql-server-profiler"></a><span data-ttu-id="9aa95-129">Проверка структур планов при помощи приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="9aa95-129">Testing Plan Guides by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="9aa95-130">Чтобы убедиться в том, что структура плана соответствует запросу, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="9aa95-130">To verify that a plan guide is being matched to a query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9aa95-131">Запустите трассировку в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , выбрав тип события **Showplan XML** (находится в узле **Производительность** ).</span><span class="sxs-lookup"><span data-stu-id="9aa95-131">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making certain that the **Showplan XML** event type is selected (located under the **Performance** node).</span></span>  
  
2.  <span data-ttu-id="9aa95-132">Позвольте приложению выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="9aa95-132">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="9aa95-133">Приостановите трассировку приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9aa95-133">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="9aa95-134">Найдите событие **Showplan XML** для соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="9aa95-134">Find the **Showplan XML** event for the affected query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9aa95-135">Событие **XML-код инструкции Showplan компиляции запроса** использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="9aa95-135">The **Showplan XML for Query Compile** event cannot be used.</span></span> <span data-ttu-id="9aa95-136">**PlanGuideDB** не существует в этом событии.</span><span class="sxs-lookup"><span data-stu-id="9aa95-136">**PlanGuideDB** does not exist in that event.</span></span>  
  
5.  <span data-ttu-id="9aa95-137">Если структура плана имеет тип OBJECT или SQL, убедитесь, что событие **Showplan XML** содержит атрибуты **PlanGuideDB** и **PlanGuideName** для структуры плана, которая, как ожидается, соответствует запросу.</span><span class="sxs-lookup"><span data-stu-id="9aa95-137">If the plan guide is of type OBJECT or SQL, verify that the **Showplan XML** event contains the **PlanGuideDB** and **PlanGuideName** attributes for the plan guide that you expected to match the query.</span></span> <span data-ttu-id="9aa95-138">Если структура плана имеет тип TEMPLATE, убедитесь, что событие **Showplan XML** содержит атрибуты **TemplatePlanGuideDB** и **TemplatePlanGuideName** для ожидаемой структуры плана.</span><span class="sxs-lookup"><span data-stu-id="9aa95-138">Or, in the case of a TEMPLATE plan guide, verify that the **Showplan XML** event contains the **TemplatePlanGuideDB** and **TemplatePlanGuideName** attributes for the expected plan guide.</span></span> <span data-ttu-id="9aa95-139">Тем самым производится проверка работы структуры плана.</span><span class="sxs-lookup"><span data-stu-id="9aa95-139">This verifies that the plan guide is working.</span></span> <span data-ttu-id="9aa95-140">Эти атрибуты содержатся в элементе **\<StmtSimple>** плана.</span><span class="sxs-lookup"><span data-stu-id="9aa95-140">These attributes are contained under the **\<StmtSimple>** element of the plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa95-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="9aa95-141">See Also</span></span>  
 [<span data-ttu-id="9aa95-142">sp_create_plan_guide (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9aa95-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)  
  
  
