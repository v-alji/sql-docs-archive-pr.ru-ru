---
title: Конструктор запросов (мастер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.dataview.vdtquerydesigner.f1
- sql12.rtp.rptwizard.querybuilder.f1
helpviewer_keywords:
- Query Builder [Reporting Services]
ms.assetid: 1b0904ea-28c1-448e-b56c-c0fdfbc8b222
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 34369bc72fadae75afbc93eb03c0e40509dd27a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654882"
---
# <a name="query-builder-report-wizard"></a><span data-ttu-id="859db-102">Построитель запросов (мастер отчетов)</span><span class="sxs-lookup"><span data-stu-id="859db-102">Query Builder (Report Wizard)</span></span>
  <span data-ttu-id="859db-103">Построитель запросов позволяет определить запрос для получения результирующего набора для отчета.</span><span class="sxs-lookup"><span data-stu-id="859db-103">Use the Query Builder to specify a query that retrieves a result set to use in a report.</span></span> <span data-ttu-id="859db-104">Можно выбрать один из следующих двух построителей запросов.</span><span class="sxs-lookup"><span data-stu-id="859db-104">You can choose between two query builders:</span></span>  
  
-   <span data-ttu-id="859db-105">Текстовый построитель запросов (по умолчанию), предоставляет простую рабочую область для ввода запроса и просмотра его результатов.</span><span class="sxs-lookup"><span data-stu-id="859db-105">The text-based query builder (default) provides a simple workspace for specifying a query and viewing the results.</span></span> <span data-ttu-id="859db-106">Можно указать несколько инструкций, запросов или команд языка [!INCLUDE[tsql](../includes/tsql-md.md)] для создания собственных модулей обработки данных, а также указать запросы, заданные как выражения.</span><span class="sxs-lookup"><span data-stu-id="859db-106">You can specify multiple [!INCLUDE[tsql](../includes/tsql-md.md)] statements, query or command syntax for custom data processing extensions, and queries that are specified as expressions.</span></span> <span data-ttu-id="859db-107">Поскольку обычный построитель запросов предварительную обработку запроса не выполняет и может быть адаптирован под любой синтаксис, он является конструктором запросов по умолчанию в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="859db-107">Because the generic query builder does not preprocess the query and can accommodate any kind of query syntax, it is the default query builder tool for Report Designer.</span></span>  
  
-   <span data-ttu-id="859db-108">Графический построитель запросов предоставляет более наглядную визуальную оболочку.</span><span class="sxs-lookup"><span data-stu-id="859db-108">The graphical query builder provides a richer visual experience.</span></span> <span data-ttu-id="859db-109">Он используется в среде [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] и других компонентах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="859db-109">It is used in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] and in other parts of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="859db-110">Этим построителем запросов можно пользоваться в том случае, когда не создаются выражения или многокомпонентные инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="859db-110">You can use the graphical query builder if you are not creating expressions or multi-part SQL statements.</span></span>  
  
     <span data-ttu-id="859db-111">Чтобы переключиться в графический построитель запросов, нажмите кнопку **Редактировать как текст** в верхнем левом углу диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="859db-111">To switch to the graphical query builder, toggle the **Edit As Text** button in the top left corner of the window.</span></span>  
  
 <span data-ttu-id="859db-112">Можно также импортировать запрос из другого отчета.</span><span class="sxs-lookup"><span data-stu-id="859db-112">You can also import a query from another report.</span></span>  
  
## <a name="query-builder-options"></a><span data-ttu-id="859db-113">Параметры построителя запросов</span><span class="sxs-lookup"><span data-stu-id="859db-113">Query Builder Options</span></span>  
 <span data-ttu-id="859db-114">**Редактировать как текст**</span><span class="sxs-lookup"><span data-stu-id="859db-114">**Edit As Text**</span></span>  
 <span data-ttu-id="859db-115">Переключает между текстовым и графическим конструктором запросов (при условии, что запрос поддерживается обоими конструкторами).</span><span class="sxs-lookup"><span data-stu-id="859db-115">Toggles between the text-based and graphical query designers, if both will work for the query.</span></span>  
  
 <span data-ttu-id="859db-116">**Импорт**</span><span class="sxs-lookup"><span data-stu-id="859db-116">**Import**</span></span>  
 <span data-ttu-id="859db-117">Открывает диалоговое окно **Импорт запроса** и отображает RDL и SQL-файлы для всех имеющихся отчетов.</span><span class="sxs-lookup"><span data-stu-id="859db-117">Opens the **Import Query** dialog box and displays .rdl and .sql files for any available report.</span></span> <span data-ttu-id="859db-118">Запрос можно либо использовать «как есть», либо изменить его в построителе запросов.</span><span class="sxs-lookup"><span data-stu-id="859db-118">You can use the imported query as it is, or you can modify it in the query builder.</span></span>  
  
 <span data-ttu-id="859db-119">**! (Выполнить)**</span><span class="sxs-lookup"><span data-stu-id="859db-119">**! (Run)**</span></span>  
 <span data-ttu-id="859db-120">Выполняет запрос и возвращает результирующий набор, если запрос не содержит ошибок.</span><span class="sxs-lookup"><span data-stu-id="859db-120">Runs the query and returns a result set if the query is valid.</span></span> <span data-ttu-id="859db-121">Обратите внимание, что нельзя выполнить запрос, если он является выражением.</span><span class="sxs-lookup"><span data-stu-id="859db-121">Note that you cannot execute the query if it is an expression.</span></span> <span data-ttu-id="859db-122">Чтобы проверить запрос на основе выражения, необходимо выполнить предварительный просмотр отчета.</span><span class="sxs-lookup"><span data-stu-id="859db-122">To verify an expression-based query, you must preview the report.</span></span>  
  
 <span data-ttu-id="859db-123">**Тип команды**</span><span class="sxs-lookup"><span data-stu-id="859db-123">**Command type**</span></span>  
 <span data-ttu-id="859db-124">Определяет текст, хранимую процедуру или непосредственно таблицу.</span><span class="sxs-lookup"><span data-stu-id="859db-124">Specifies text, stored procedure, or table direct.</span></span> <span data-ttu-id="859db-125">Доступность типов команд зависит от заданного модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="859db-125">Availability of a command type depends on the data processing extension you specified.</span></span>  
  
 <span data-ttu-id="859db-126">**Панель запросов**</span><span class="sxs-lookup"><span data-stu-id="859db-126">**Query pane**</span></span>  
 <span data-ttu-id="859db-127">Введите запрос.</span><span class="sxs-lookup"><span data-stu-id="859db-127">Type the query.</span></span>  
  
 <span data-ttu-id="859db-128">**Панель результатов**</span><span class="sxs-lookup"><span data-stu-id="859db-128">**Result pane**</span></span>  
 <span data-ttu-id="859db-129">Показывает результирующий набор данного запроса.</span><span class="sxs-lookup"><span data-stu-id="859db-129">Shows the result set returned from the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859db-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="859db-130">See Also</span></span>  
 <span data-ttu-id="859db-131">[Внедренные и общие наборы данных отчета &#40;построитель отчетов и службы SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="859db-131">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="859db-132">Справка мастера отчетов</span><span class="sxs-lookup"><span data-stu-id="859db-132">Report Wizard Help</span></span>](../../2014/reporting-services/report-wizard-help.md)  
  
  
