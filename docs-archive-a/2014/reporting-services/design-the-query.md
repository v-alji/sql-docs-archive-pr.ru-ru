---
title: Создать запрос | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735094"
---
# <a name="design-the-query"></a><span data-ttu-id="c7562-102">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="c7562-102">Design the Query</span></span>
  <span data-ttu-id="c7562-103">На этой странице мастера отчетов можно создать запрос: ввести его вручную, воспользоваться построителем запросов для интерактивного создания запроса или импортировать запрос из другого отчета.</span><span class="sxs-lookup"><span data-stu-id="c7562-103">Use this page of the Report Wizard to create a query by typing the query manually, by using Query Builder to interactively build a query, or by importing a query from another report.</span></span>  
  
 <span data-ttu-id="c7562-104">Какие именно запросы могут быть введены на этой странице, зависит от выбора типа источника данных на странице «Выбор источника данных» (на предыдущей странице мастера отчетов).</span><span class="sxs-lookup"><span data-stu-id="c7562-104">The data source type you chose on the Select the Data Source page, a previous page in the Report Wizard, determines the query you can enter on this page.</span></span> <span data-ttu-id="c7562-105">Например, если тип источника данных — [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , можно ввести [!INCLUDE[tsql](../includes/tsql-md.md)] инструкции или имена хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="c7562-105">For example, if the data source type is [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements or stored procedure names.</span></span> <span data-ttu-id="c7562-106">Если тип источника данных — [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , панель запросов отключается, и нельзя вводить запрос напрямую.</span><span class="sxs-lookup"><span data-stu-id="c7562-106">If the data source type is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], the Query pane is disabled and you cannot enter a query directly.</span></span> <span data-ttu-id="c7562-107">Задать запрос можно только при помощи построителя запросов.</span><span class="sxs-lookup"><span data-stu-id="c7562-107">You can specify the query by using Query Builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c7562-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="c7562-108">Options</span></span>  
 <span data-ttu-id="c7562-109">**Строка запроса**</span><span class="sxs-lookup"><span data-stu-id="c7562-109">**Query string**</span></span>  
 <span data-ttu-id="c7562-110">Введите запрос получения данных, которые будут использованы в отчете.</span><span class="sxs-lookup"><span data-stu-id="c7562-110">Type a query that retrieves the data you want to use in your report.</span></span>  
  
 <span data-ttu-id="c7562-111">**Построитель запросов**</span><span class="sxs-lookup"><span data-stu-id="c7562-111">**Query Builder**</span></span>  
 <span data-ttu-id="c7562-112">Нажмите кнопку **Построитель запросов** , чтобы открыть конструктор запросов применительно к источнику данных, либо импортировать запрос из другого отчета.</span><span class="sxs-lookup"><span data-stu-id="c7562-112">Click **Query Builder** to open a query designer for the data source, or to import a query from another report.</span></span>  
  
 <span data-ttu-id="c7562-113">Дополнительные сведения о конструкторах запросов см. в разделе [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span><span class="sxs-lookup"><span data-stu-id="c7562-113">For more information about query designers, see [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7562-114">Пример</span><span class="sxs-lookup"><span data-stu-id="c7562-114">Example</span></span>  
 <span data-ttu-id="c7562-115">Для типа источника данных **Microsoft SQL Server**следующий запрос получает список фамилий из [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] таблицы базы данных `Person` .</span><span class="sxs-lookup"><span data-stu-id="c7562-115">For the data source type **Microsoft SQL Server**, the following query retrieves a list of last names from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database `Person` table.</span></span>  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 <span data-ttu-id="c7562-116">Для типа источника данных **Microsoft SQL Server**следующий запрос выполняет [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] хранимую процедуру `uspGetEmployeeManagers` для сотрудника с идентификационным номером 1:</span><span class="sxs-lookup"><span data-stu-id="c7562-116">For the data source type **Microsoft SQL Server**, the following query runs the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] stored procedure `uspGetEmployeeManagers` for the employee with identification number 1:</span></span>  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7562-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7562-117">See Also</span></span>  
 <span data-ttu-id="c7562-118">[Справка мастера отчетов](../../2014/reporting-services/report-wizard-help.md) </span><span class="sxs-lookup"><span data-stu-id="c7562-118">[Report Wizard Help](../../2014/reporting-services/report-wizard-help.md) </span></span>  
 <span data-ttu-id="c7562-119">[Внедренные и общие наборы данных отчета &#40;построитель отчетов и службы SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c7562-119">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c7562-120">Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c7562-120">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
