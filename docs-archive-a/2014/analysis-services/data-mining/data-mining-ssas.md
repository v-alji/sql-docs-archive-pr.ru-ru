---
title: Интеллектуальный анализ данных (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
ms.assetid: b1c912da-72f6-4d96-89c8-55a2c4f19e88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7044ee397d457f7924d0db99dbec6659f969f104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666893"
---
# <a name="data-mining-ssas"></a><span data-ttu-id="60785-102">Интеллектуальный анализ данных (службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="60785-102">Data Mining (SSAS)</span></span>
  <span data-ttu-id="60785-103">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] — это интегрированная платформа для решений, в которых реализован интеллектуальный анализ данных.</span><span class="sxs-lookup"><span data-stu-id="60785-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides an integrated platform for solutions that incorporate data mining.</span></span> <span data-ttu-id="60785-104">Для создания решений интеллектуального анализа данных с прогнозирующим анализом могут быть использованы либо реляционные данные, либо данные в кубе.</span><span class="sxs-lookup"><span data-stu-id="60785-104">You can use either relational or cube data to create business intelligence solutions with predictive analytics.</span></span>  
  
## <a name="benefits-of-data-mining"></a><span data-ttu-id="60785-105">Преимущества интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="60785-105">Benefits of Data Mining</span></span>  
 <span data-ttu-id="60785-106">В интеллектуальном анализе данных с помощью хорошо исследованных статистических принципов в данных выделяются закономерности, которые помогают принимать обоснованные решения по сложным проблемам.</span><span class="sxs-lookup"><span data-stu-id="60785-106">Data mining uses well-researched statistical principles to discover patterns in your data, helping you make intelligent decisions about complex problems.</span></span> <span data-ttu-id="60785-107">Применив алгоритмы интеллектуального анализа данных [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] к своим данным, вы сможете прогнозировать тенденции, выделять закономерности, создавать правила и рекомендации, анализировать последовательность событий в сложных наборах данных и обнаруживать новые зависимости.</span><span class="sxs-lookup"><span data-stu-id="60785-107">By applying the data mining algorithms in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to your data, you can forecast trends, identify patterns, create rules and recommendations, analyze the sequence of events in complex data sets, and gain new insights.</span></span>  
  
 <span data-ttu-id="60785-108">Средства интеллектуального анализа данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]имеют широкие возможности, легко доступны и интегрированы со средствами, которые многие пользователи предпочитают применять для анализа и составления отчетов.</span><span class="sxs-lookup"><span data-stu-id="60785-108">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], data mining is powerful, accessible, and integrated with the tools that many people prefer to use for analysis and reporting.</span></span> <span data-ttu-id="60785-109">По ссылкам в этом разделе можно получить общие сведения, относящиеся к интеллектуальному анализу данных. Рекомендуется ознакомиться с ними перед началом работы.</span><span class="sxs-lookup"><span data-stu-id="60785-109">See the links in this section to get the broad background about data mining that you need to get started.</span></span>  
  
## <a name="key-data-mining-features"></a><span data-ttu-id="60785-110">Ключевые функции интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="60785-110">Key Data Mining Features</span></span>  
 <span data-ttu-id="60785-111">SQL Server предоставляет следующие функции по поддержке встроенных решений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="60785-111">SQL Server provides the following features in support of integrated data mining solutions:</span></span>  
  
-   <span data-ttu-id="60785-112">Несколько источников данных: для интеллектуального анализа данных не требуется создание хранилища данных или куба OLAP.</span><span class="sxs-lookup"><span data-stu-id="60785-112">Multiple data sources: You do not have to create a data warehouse or an OLAP cube to do data mining.</span></span> <span data-ttu-id="60785-113">Можно пользоваться табличными данными от внешних поставщиков, из электронных таблиц и даже текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="60785-113">You can use tabular data from external providers, spreadsheets, and even text files.</span></span> <span data-ttu-id="60785-114">Также легко доступен интеллектуальный анализ кубов OLAP, созданных в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60785-114">You can also easily mine OLAP cubes created in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="60785-115">При этом невозможно использовать данные из выполняющейся в памяти базы данных.</span><span class="sxs-lookup"><span data-stu-id="60785-115">However, you cannot use data from an in-memory database.</span></span>  
  
-   <span data-ttu-id="60785-116">Встроенная очистка данных, управление данными и ETL: в службах Data Quality Services предусмотрены мощные средства для профилирования и очистки данных.</span><span class="sxs-lookup"><span data-stu-id="60785-116">Integrated data cleansing, data management, and ETL: Data Quality Services provides advanced tools for profiling and cleansing data.</span></span> <span data-ttu-id="60785-117">Службы Integration Services могут быть использованы в построении процессов ETL для очистки данных, а также для создания, обработки, обучения и обновления моделей.</span><span class="sxs-lookup"><span data-stu-id="60785-117">Integration Services can be used to build ETL processes for cleaning data, and also for building, processing, training, and updating models.</span></span>  
  
-   <span data-ttu-id="60785-118">Несколько настраиваемых алгоритмов: в дополнение к кластеризации, нейронным сетям и деревьям принятия решений платформа поддерживает разработку собственных пользовательских подключаемых алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="60785-118">Multiple customizable algorithms: In addition to providing algorithms such as clustering, neural networks, and decisions trees, the platform supports development of your own custom plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="60785-119">Инфраструктура проверки моделей: проверять модели и наборы данных теперь можно с помощью таких важных статистических средств, как перекрестная проверка, матрицы классификации, диаграммы точности прогнозов и точечные диаграммы.</span><span class="sxs-lookup"><span data-stu-id="60785-119">Model testing infrastructure: Test your models and data sets using important statistical tools as cross-validation, classification matrices, lift charts, and scatter plots.</span></span> <span data-ttu-id="60785-120">Простое создание проверочных и обучающих наборов и управление ими.</span><span class="sxs-lookup"><span data-stu-id="60785-120">Easily create and manage testing and training sets.</span></span>  
  
-   <span data-ttu-id="60785-121">Запросы и детализация: создание прогнозирующих запросов, получение закономерностей и статистики моделей, а также детализация данных вариантов.</span><span class="sxs-lookup"><span data-stu-id="60785-121">Querying and drillthrough: Create prediction queries, retrieve model patterns and statistics, and drill through to case data.</span></span>  
  
-   <span data-ttu-id="60785-122">Клиентские средства: в дополнение к средам разработки и проектирования, входящим в состав SQL Server, появились надстройки интеллектуального анализа данных для Excel в решении таких задач, как создание и просмотр моделей, а также выполнение запросов к ним.</span><span class="sxs-lookup"><span data-stu-id="60785-122">Client tools: In addition to the development and design studios provided by SQL Server, you can use the Data Mining Add-ins for Excel to create, query, and browse models.</span></span> <span data-ttu-id="60785-123">Кроме того, можно создавать пользовательские клиенты, в том числе веб-службы.</span><span class="sxs-lookup"><span data-stu-id="60785-123">Or, create custom clients, including Web services.</span></span>  
  
-   <span data-ttu-id="60785-124">Поддержка языка сценариев и управляемые API-интерфейсы: все объекты интеллектуального анализа данных являются полностью программируемыми.</span><span class="sxs-lookup"><span data-stu-id="60785-124">Scripting language support and managed API: All data mining objects are fully programmable.</span></span> <span data-ttu-id="60785-125">Сценарии через MDX, XMLA или расширения PowerShell для служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60785-125">Scripting is possible through MDX, XMLA, or the PowerShell extensions for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="60785-126">С помощью языка расширения интеллектуального анализа данных (DMX) можно быстро создавать запросы и сценарии.</span><span class="sxs-lookup"><span data-stu-id="60785-126">Use the Data Mining Extensions (DMX) language for fast querying and scripting.</span></span>  
  
-   <span data-ttu-id="60785-127">Защита и развертывание: обеспечивает безопасность на основе ролей через [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], в том числе раздельные разрешения для детализации на моделирование и структурирование данных.</span><span class="sxs-lookup"><span data-stu-id="60785-127">Security and deployment: Provides role-based security through [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], including separate permissions for drillthrough to model and structure data.</span></span> <span data-ttu-id="60785-128">Простота развертывания моделей на других серверах, которая предоставляет пользователям доступ к закономерностям и прогнозированию</span><span class="sxs-lookup"><span data-stu-id="60785-128">Easy deployment of models to other servers, so that users can access the patterns or perform predictions</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60785-129">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="60785-129">In This Section</span></span>  
 <span data-ttu-id="60785-130">В подразделах этого раздела описаны основные возможности интеллектуального анализа данных SQL Server и связанные с ним задачи.</span><span class="sxs-lookup"><span data-stu-id="60785-130">The topics in this section introduce the principal features of SQL Server Data Mining and related tasks.</span></span>  
  
-   [<span data-ttu-id="60785-131">Основные понятия интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="60785-131">Data Mining Concepts</span></span>](data-mining-concepts.md)  
  
-   [<span data-ttu-id="60785-132">Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="60785-132">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="60785-133">Структуры интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="60785-133">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="60785-134">Модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="60785-134">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="60785-135">Тестирование и проверка (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="60785-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
-   [<span data-ttu-id="60785-136">Запросы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="60785-136">Data Mining Queries</span></span>](data-mining-queries.md)  
  
-   [<span data-ttu-id="60785-137">Решения интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="60785-137">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
-   [<span data-ttu-id="60785-138">Средства интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="60785-138">Data Mining Tools</span></span>](data-mining-tools.md)  
  
-   [<span data-ttu-id="60785-139">Архитектора интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="60785-139">Data Mining Architecture</span></span>](data-mining-architecture.md)  
  
-   [<span data-ttu-id="60785-140">Общие сведения о безопасности (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="60785-140">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
  
