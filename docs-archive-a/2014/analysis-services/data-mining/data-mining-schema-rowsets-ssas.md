---
title: Запросы к наборам строк схемы интеллектуального анализа данных (Analysis Services — интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- schema rowsets [Analysis Services], data mining
- data mining [Analysis Services], queries
- mining model content
- data mining [Analysis Services], schema rowsets
- schema rowsets [Analysis Services], retrieving
- data mining [Analysis Services], troubleshooting
ms.assetid: 442d8c29-07c7-45de-9a15-d556059f68d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60c802256454ee68d04392e685fa4acabf6c12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666896"
---
# <a name="querying-the-data-mining-schema-rowsets-analysis-services---data-mining"></a><span data-ttu-id="f2528-102">Запрос наборов строк схемы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="f2528-102">Querying the Data Mining Schema Rowsets (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="f2528-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]многие существующие наборы строк схемы интеллектуального анализа данных OLE DB доступны в виде набора системных таблиц, к которым можно выполнять запросы с помощью инструкций расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f2528-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], many of the existing OLE DB data mining schema rowsets are exposed as a set of system tables that you can query by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="f2528-104">Путем создания запросов к наборам строк схемы интеллектуального анализа данных можно определить доступные службы, получить последние сведения о состоянии моделей и структур и выяснить подробности о содержимом или параметрах модели.</span><span class="sxs-lookup"><span data-stu-id="f2528-104">By creating queries against the data mining schema rowset, you can identify the services that are available, get updates on the status of your models and structures, and find out details about the model content or parameters.</span></span> <span data-ttu-id="f2528-105">Описание наборов строк схемы интеллектуального анализа данных см. в разделе [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="f2528-105">For a description of the data mining schema rowsets, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2528-106">Кроме того, можно выполнить запрос к этому набору строк схемы интеллектуального анализа данных с помощью XMLA.</span><span class="sxs-lookup"><span data-stu-id="f2528-106">You can also query the data mining schema rowsets by using XMLA.</span></span> <span data-ttu-id="f2528-107">Дополнительные сведения о выполнении этого действия в среде SQL Server Management Studio см. в разделе [Создание запроса интеллектуального анализа данных с помощью XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="f2528-107">For more information about how to do this in SQL Server Management Studio, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="list-of-data-mining-schema-rowsets"></a><span data-ttu-id="f2528-108">Список наборов строк схемы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f2528-108">List of Data Mining Schema Rowsets</span></span>  
 <span data-ttu-id="f2528-109">В следующей таблице перечислены наборы строк схемы интеллектуального анализа данных, которые могут пригодиться при запросах и наблюдении.</span><span class="sxs-lookup"><span data-stu-id="f2528-109">The following table lists the data mining schema rowsets that may be useful for querying and monitoring.</span></span>  
  
|<span data-ttu-id="f2528-110">Имя набора строк</span><span class="sxs-lookup"><span data-stu-id="f2528-110">Rowset name</span></span>|<span data-ttu-id="f2528-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f2528-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f2528-112">DMSCHEMA_MINING_MODELS</span><span class="sxs-lookup"><span data-stu-id="f2528-112">DMSCHEMA_MINING_MODELS</span></span>|<span data-ttu-id="f2528-113">Выводит все модели интеллектуального анализа данных в текущем контексте.</span><span class="sxs-lookup"><span data-stu-id="f2528-113">Lists all mining models in the current context.</span></span><br /><br /> <span data-ttu-id="f2528-114">Включает такие сведения, как дата создания, параметры, использованные при создании модели, и размер обучающего набора.</span><span class="sxs-lookup"><span data-stu-id="f2528-114">Includes such information as the date created, parameters used to create the model, and the size of the training set.</span></span>|  
|<span data-ttu-id="f2528-115">DMSCHEMA_MINING_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="f2528-115">DMSCHEMA_MINING_COLUMNS</span></span>|<span data-ttu-id="f2528-116">Выводит все столбцы, использованные в моделях интеллектуального анализа данных в текущем контексте.</span><span class="sxs-lookup"><span data-stu-id="f2528-116">Lists all columns used in mining models in the current context.</span></span><br /><br /> <span data-ttu-id="f2528-117">Сведения: сопоставление с исходным столбцом структуры интеллектуального анализа данных, тип данных, точность и прогнозирующая функция, которые можно использовать со столбцом.</span><span class="sxs-lookup"><span data-stu-id="f2528-117">Information includes mapping to mining structure source column, data type, precision, and prediction functions that can be used with the column.</span></span>|  
|<span data-ttu-id="f2528-118">DMSCHEMA_MINING_STRUCTURES</span><span class="sxs-lookup"><span data-stu-id="f2528-118">DMSCHEMA_MINING_STRUCTURES</span></span>|<span data-ttu-id="f2528-119">Выводит всю структуру интеллектуального анализа данных в текущем контексте.</span><span class="sxs-lookup"><span data-stu-id="f2528-119">Lists all mining structure in the current context.</span></span><br /><br /> <span data-ttu-id="f2528-120">Сведения: данные о заполнении структуры, дата последней обработки структуры и определение набора контрольных данных для структуры, если они есть.</span><span class="sxs-lookup"><span data-stu-id="f2528-120">Information includes whether the structure is populated, the date the structure was last processed, and the definition of the holdout data set for the structure, if any.</span></span>|  
|<span data-ttu-id="f2528-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="f2528-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span></span>|<span data-ttu-id="f2528-122">Выводит все столбцы, использованные в структурах интеллектуального анализа в текущем контексте.</span><span class="sxs-lookup"><span data-stu-id="f2528-122">Lists all columns used in mining structures in the current context.</span></span><br /><br /> <span data-ttu-id="f2528-123">Сведения: тип содержимого и тип данных, допустимость значений NULL и наличие в столбце вложенных табличных данных.</span><span class="sxs-lookup"><span data-stu-id="f2528-123">Information includes content type and data type, nullability, and whether the column contains nested table data.</span></span>|  
|<span data-ttu-id="f2528-124">DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="f2528-124">DMSCHEMA_MINING_SERVICES</span></span>|<span data-ttu-id="f2528-125">Выводит все службы интеллектуального анализа или алгоритмы, доступные на указанном сервере.</span><span class="sxs-lookup"><span data-stu-id="f2528-125">Lists all mining services, or algorithms, that are available on the specified server.</span></span><br /><br /> <span data-ttu-id="f2528-126">Сведения: поддерживаемые флаги моделирования, типы ввода и поддерживаемые типы источника данных.</span><span class="sxs-lookup"><span data-stu-id="f2528-126">Information includes supported modeling flags, input types, and supported data source types.</span></span>|  
|<span data-ttu-id="f2528-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f2528-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span></span>|<span data-ttu-id="f2528-128">Выводит все параметры для служб интеллектуального анализа, доступные на текущем экземпляре.</span><span class="sxs-lookup"><span data-stu-id="f2528-128">Lists all parameters for the mining services that are available on the current instance.</span></span><br /><br /> <span data-ttu-id="f2528-129">Сведения: тип данных для каждого параметра, значения по умолчанию и верхний и нижний пределы.</span><span class="sxs-lookup"><span data-stu-id="f2528-129">Information includes the data type for each parameter, the default values, and the upper and lower limits.</span></span>|  
|<span data-ttu-id="f2528-130">DMSCHEMA_MODEL_CONTENT</span><span class="sxs-lookup"><span data-stu-id="f2528-130">DMSCHEMA_MODEL_CONTENT</span></span>|<span data-ttu-id="f2528-131">Возвращает содержимое модели, если модель обработана.</span><span class="sxs-lookup"><span data-stu-id="f2528-131">Returns the content of the model if the model has been processed.</span></span><br /><br /> <span data-ttu-id="f2528-132">Дополнительные сведения см. в разделе [Содержимое модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f2528-132">For more information, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>|  
|<span data-ttu-id="f2528-133">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="f2528-133">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="f2528-134">Выводит все базы данных (каталоги) в текущем экземпляре служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f2528-134">Lists all databases (catalogs) in the current instance of Analysis Services.</span></span>|  
|<span data-ttu-id="f2528-135">MDSCHEMA_INPUT_DATASOURCES</span><span class="sxs-lookup"><span data-stu-id="f2528-135">MDSCHEMA_INPUT_DATASOURCES</span></span>|<span data-ttu-id="f2528-136">Выводит все источники данных в текущем экземпляре служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f2528-136">Lists all data sources in the current instance of Analysis Services.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f2528-137">Список в таблице не является исчерпывающим. В нем показаны только наборы строк, наиболее важные для диагностики.</span><span class="sxs-lookup"><span data-stu-id="f2528-137">The list in the table is not comprehensive; it shows only those rowsets that may be of most interest for troubleshooting.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f2528-138">Примеры</span><span class="sxs-lookup"><span data-stu-id="f2528-138">Examples</span></span>  
 <span data-ttu-id="f2528-139">В следующем разделе даны некоторые примеры запросов к наборам строк схемы интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f2528-139">The following section provides some examples of queries against the data mining schema rowsets.</span></span>  
  
### <a name="example-1-list-data-mining-services"></a><span data-ttu-id="f2528-140">Пример 1. Перечисление служб интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f2528-140">Example 1: List Data Mining Services</span></span>  
 <span data-ttu-id="f2528-141">Следующий запрос возвращает список служб интеллектуального анализа, доступных на текущем сервере, что свидетельствует о том, что алгоритмы включены.</span><span class="sxs-lookup"><span data-stu-id="f2528-141">The following query returns a list of the mining services that are available on the current server, meaning the algorithms that are enabled.</span></span> <span data-ttu-id="f2528-142">Столбцы для каждой службы интеллектуального анализа содержат флаги моделирования и типы содержимого, которые может использовать каждый алгоритм; идентификатор GUID для каждой службы и любые пределы прогнозирования, назначенные для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="f2528-142">The columns provided for each mining service include the modeling flags and content types that can be used by each algorithm, the GUID for each service, and any prediction limits that may have been added for each service.</span></span>  
  
```  
SELECT *  
FROM $system.DMSCHEMA_MINING_SERVICES  
```  
  
### <a name="example-2-list-mining-model-parameters"></a><span data-ttu-id="f2528-143">Пример 2. Перечисление параметров модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f2528-143">Example 2: List Mining Model Parameters</span></span>  
 <span data-ttu-id="f2528-144">Следующий запрос возвращает параметры, которые использовались для создания конкретной модели интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="f2528-144">The following example returns the parameters that were used to create a specific mining model:</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
### <a name="example-3-list-all-rowsets"></a><span data-ttu-id="f2528-145">Пример 3. Перечисление всех наборов строк</span><span class="sxs-lookup"><span data-stu-id="f2528-145">Example 3: List All Rowsets</span></span>  
 <span data-ttu-id="f2528-146">Следующий пример возвращает полный список наборов строк, доступных на текущем сервере.</span><span class="sxs-lookup"><span data-stu-id="f2528-146">The following example returns a comprehensive list of the rowsets that are available on the current server:</span></span>  
  
```  
SELECT *   
FROM $system.DBSCHEMA_TABLES  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2528-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2528-147">See Also</span></span>  
 [<span data-ttu-id="f2528-148">Основные понятия устранения неполадок (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="f2528-148">Troubleshooting Concepts (Analysis Services - Data Mining)</span></span>](https://msdn.microsoft.com/library/cc645881.aspx)  
  
  
