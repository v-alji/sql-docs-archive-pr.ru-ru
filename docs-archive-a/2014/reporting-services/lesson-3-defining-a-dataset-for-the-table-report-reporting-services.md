---
title: Занятие 3. Определение набора данных для табличного отчета (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ee93dfcb-8f52-4d63-b4f6-0d38e00fd350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 33fe48a60db2e7d15d205a4bff6205347f95c61c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657570"
---
# <a name="lesson-3-defining-a-dataset-for-the-table-report-reporting-services"></a><span data-ttu-id="314b7-102">Занятие 3. Определение набора данных для табличного отчета (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="314b7-102">Lesson 3: Defining a Dataset for the Table Report (Reporting Services)</span></span>
  <span data-ttu-id="314b7-103">После определения источника данных необходимо определить набор данных.</span><span class="sxs-lookup"><span data-stu-id="314b7-103">After you define the data source, you need to define a dataset.</span></span> <span data-ttu-id="314b7-104">В службах [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]данные, используемые в отчетах, содержатся в *наборе данных*.</span><span class="sxs-lookup"><span data-stu-id="314b7-104">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], data that you use in reports is contained in a *dataset*.</span></span> <span data-ttu-id="314b7-105">Набор данных содержит указатель на источник данных и запрос, используемый в отчете, а также вычисляемые поля и переменные.</span><span class="sxs-lookup"><span data-stu-id="314b7-105">A dataset includes a pointer to a data source and a query to be used by the report, as well as calculated fields and variables.</span></span>  
  
 <span data-ttu-id="314b7-106">Чтобы создать запрос, можно использовать «Конструктор запросов».</span><span class="sxs-lookup"><span data-stu-id="314b7-106">You can use the query designer in Report Designer to design the query.</span></span> <span data-ttu-id="314b7-107">В этом учебнике будет создан запрос, извлекающий сведения о заказах на продажу из [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] базы данных **2008** .</span><span class="sxs-lookup"><span data-stu-id="314b7-107">For this tutorial, you will create a query that retrieves sales order information from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]**2008** database.</span></span>  
  
### <a name="to-define-a-transact-sql-query-for-report-data"></a><span data-ttu-id="314b7-108">Определение запроса Transact-SQL для данных отчета</span><span class="sxs-lookup"><span data-stu-id="314b7-108">To define a Transact-SQL query for report data</span></span>  
  
1.  <span data-ttu-id="314b7-109">В области **данных отчета** нажмите кнопку **создать**, а затем выберите **набор данных...**. Откроется диалоговое окно **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="314b7-109">In the **Report Data** pane, click **New**, and then click **Dataset...**. The **Dataset Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="314b7-110">В поле **Имя** введите **AdventureWorksDataset**.</span><span class="sxs-lookup"><span data-stu-id="314b7-110">In the **Name** box, type **AdventureWorksDataset**.</span></span>  
  
3.  <span data-ttu-id="314b7-111">Выберите **Использовать набор данных, внедренный в отчет**.</span><span class="sxs-lookup"><span data-stu-id="314b7-111">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="314b7-112">Убедитесь, что имя источника данных, AdventureWorks2012, находится в текстовом поле **источник данных** , а **тип запроса** — **Text**.</span><span class="sxs-lookup"><span data-stu-id="314b7-112">Make sure the name of your data source, AdventureWorks2012, is in the **Data source** text box, and that the **Query type** is **Text**.</span></span>  
  
5.  <span data-ttu-id="314b7-113">Введите или скопируйте и вставьте приведенный ниже запрос Transact-SQL в поле **Запрос** .</span><span class="sxs-lookup"><span data-stu-id="314b7-113">Type, or copy and paste, the following Transact-SQL query into the **Query** box.</span></span>  
  
    ```  
    SELECT   
       soh.OrderDate AS [Date],   
       soh.SalesOrderNumber AS [Order],   
       pps.Name AS Subcat, pp.Name as Product,    
       SUM(sd.OrderQty) AS Qty,  
       SUM(sd.LineTotal) AS LineTotal  
    FROM Sales.SalesPerson sp   
       INNER JOIN Sales.SalesOrderHeader AS soh   
          ON sp.BusinessEntityID = soh.SalesPersonID  
       INNER JOIN Sales.SalesOrderDetail AS sd   
          ON sd.SalesOrderID = soh.SalesOrderID  
       INNER JOIN Production.Product AS pp   
          ON sd.ProductID = pp.ProductID  
       INNER JOIN Production.ProductSubcategory AS pps   
          ON pp.ProductSubcategoryID = pps.ProductSubcategoryID  
       INNER JOIN Production.ProductCategory AS ppc   
          ON ppc.ProductCategoryID = pps.ProductCategoryID  
    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name,   
       soh.SalesPersonID  
    HAVING ppc.Name = 'Clothing'  
    ```  
  
6.  <span data-ttu-id="314b7-114">Нажмите кнопку **Конструктор запросов** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="314b7-114">(Optional) Click the **Query Designer** button.</span></span> <span data-ttu-id="314b7-115">В текстовом конструкторе запросов будет отображен запрос.</span><span class="sxs-lookup"><span data-stu-id="314b7-115">The query is displayed in the text-based query designer.</span></span> <span data-ttu-id="314b7-116">Вы можете переключиться к графическому конструктору запросов, нажав кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="314b7-116">You can toggle to the graphical query designer by clicking **Edit As Text**.</span></span> <span data-ttu-id="314b7-117">Просмотрите результаты запроса, нажав кнопку выполнить **(!)** на панели инструментов конструктора запросов.</span><span class="sxs-lookup"><span data-stu-id="314b7-117">View the results of the query by clicking the run **(!)** button on the query designer toolbar.</span></span>  
  
     <span data-ttu-id="314b7-118">Будут показаны данные из шести полей четырех различных таблиц из базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="314b7-118">You see the data from six fields from four different tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="314b7-119">В запросе используется возможность псевдонимов языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="314b7-119">The query makes use of Transact-SQL functionality such as aliases.</span></span> <span data-ttu-id="314b7-120">Например, таблица SalesOrderHeader называется soh.</span><span class="sxs-lookup"><span data-stu-id="314b7-120">For example, the SalesOrderHeader table is called soh.</span></span>  
  
     <span data-ttu-id="314b7-121">Нажмите кнопку **ОК** для выхода из конструктора запросов.</span><span class="sxs-lookup"><span data-stu-id="314b7-121">Click **OK** to exit the query designer.</span></span>  
  
7.  <span data-ttu-id="314b7-122">Нажмите кнопку **ОК** для выхода из диалогового окна **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="314b7-122">Click **OK** to exit the **Dataset Properties** dialog box.</span></span>  
  
     <span data-ttu-id="314b7-123">Поля и набор данных **AdventureWorksDataset** появятся в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="314b7-123">Your **AdventureWorksDataset** dataset and fields appear in the Report Data pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="314b7-124">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="314b7-124">Next Task</span></span>  
 <span data-ttu-id="314b7-125">Определен запрос, получающий данные для отчета.</span><span class="sxs-lookup"><span data-stu-id="314b7-125">You have successfully specified a query that retrieves data for your report.</span></span> <span data-ttu-id="314b7-126">Далее предстоит создать макет отчета.</span><span class="sxs-lookup"><span data-stu-id="314b7-126">Next, you will create the report layout.</span></span> <span data-ttu-id="314b7-127">См. [Занятие 4. Добавление таблицы в отчет (службы Reporting Services)](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="314b7-127">See [Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="314b7-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="314b7-128">See Also</span></span>  
 <span data-ttu-id="314b7-129">[Средства проектирования запросов в конструктор отчетов SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="314b7-129">[Query Design Tools in Report Designer SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span></span>  
 <span data-ttu-id="314b7-130">[Тип подключения SQL Server &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="314b7-130">[SQL Server Connection Type &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="314b7-131">Руководство. Составление инструкций Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="314b7-131">Tutorial: Writing Transact-SQL Statements</span></span>](../t-sql/tutorial-writing-transact-sql-statements.md)  
  
  
