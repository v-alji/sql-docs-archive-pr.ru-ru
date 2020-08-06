---
title: Источники данных в многомерных моделях | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- metadata [Analysis Services]
- Analysis Services objects, data sources
- storing data [Analysis Services], data sources
- data sources [Analysis Services], about data sources
- security [Analysis Services], data sources
- data sources [Analysis Services]
- storage [Analysis Services], data sources
ms.assetid: a16469d9-9d53-4e35-9982-fc06327a9d33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 41386c1c7abb0324aa17df24b3c427ca8cbb5615
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667446"
---
# <a name="data-sources-in-multidimensional-models"></a><span data-ttu-id="8b452-102">Источники данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="8b452-102">Data Sources in Multidimensional Models</span></span>
  <span data-ttu-id="8b452-103">Все данные, которые вы импортируете или загружаете в многомерную модель, происходят из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="8b452-103">All data that you import or load into a multidimensional model originates from an external data source.</span></span> <span data-ttu-id="8b452-104">Обычно исходные данные поступают из хранилища данных, разработанного для составления отчетов, однако они могут поступать из любой реляционной базы данных, которая обращается прямо или косвенно через посредника, например пакет [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8b452-104">Typically, source data is from a data warehouse designed for reporting purposes, but it could come from any relational database that is accessed directly or indirectly through an intermediary, such as an [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span>  
  
 <span data-ttu-id="8b452-105">Объект **источника данных** в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] задает прямое соединение с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="8b452-105">A **data source** object in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] specifies a direct connection to an external data source.</span></span> <span data-ttu-id="8b452-106">Помимо физического расположения, объект источника данных указывает строку соединения, поставщика данных, учетные данные и другие свойства, управляющие поведением соединения.</span><span class="sxs-lookup"><span data-stu-id="8b452-106">In addition to physical location, a data source object specifies the connection string, data provider, credentials, and other properties that control connection behavior.</span></span>  
  
 <span data-ttu-id="8b452-107">Сведения, предоставляемые объектом источника данных, используются при выполнении следующих операций.</span><span class="sxs-lookup"><span data-stu-id="8b452-107">Information provided by the data source object is used during the following operations:</span></span>  
  
-   <span data-ttu-id="8b452-108">Возврат сведений о схеме и других метаданных, используемых для генерирования представлений источников данных в модели.</span><span class="sxs-lookup"><span data-stu-id="8b452-108">Get schema information and other metadata used to generate data source views into a model.</span></span>  
  
-   <span data-ttu-id="8b452-109">Запрос или загрузка данных в модель во время обработки.</span><span class="sxs-lookup"><span data-stu-id="8b452-109">Query or load data into a model during processing.</span></span>  
  
-   <span data-ttu-id="8b452-110">Выполнение запросов к многомерным моделям или моделям интеллектуального анализа данных, использующим режим хранения ROLAP.</span><span class="sxs-lookup"><span data-stu-id="8b452-110">Run queries against multidimensional or data mining models that use ROLAP storage mode.</span></span>  
  
-   <span data-ttu-id="8b452-111">Считывание или запись удаленных секций.</span><span class="sxs-lookup"><span data-stu-id="8b452-111">Read or write to remote partitions.</span></span>  
  
-   <span data-ttu-id="8b452-112">Подключение к связанным объектам и синхронизация цели с источником.</span><span class="sxs-lookup"><span data-stu-id="8b452-112">Connect to linked objects, as well as synchronize from target to source.</span></span>  
  
-   <span data-ttu-id="8b452-113">Выполнение операций обратной записи для обновления данных таблицы фактов, которая хранится в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="8b452-113">Perform write back operations that update fact table data stored in a relational database.</span></span>  
  
 <span data-ttu-id="8b452-114">Если новая многомерная модель строится снизу вверх, следует начать с создания объекта источника данных, а затем использовать его для создания следующего объекта — **представления источников данных**.</span><span class="sxs-lookup"><span data-stu-id="8b452-114">When building a multidimensional model from the bottom up, you start by creating the data source object, and then use it to generate the next object, a **data source view**.</span></span> <span data-ttu-id="8b452-115">Представление источника данных — это уровень абстракции данных в модели.</span><span class="sxs-lookup"><span data-stu-id="8b452-115">A data source view is the data abstraction layer in the model.</span></span> <span data-ttu-id="8b452-116">Обычно оно создается после создания объекта источника данных на основе схемы исходной базы данных.</span><span class="sxs-lookup"><span data-stu-id="8b452-116">It is typically created after the data source object, using the schema of the source database as the basis.</span></span> <span data-ttu-id="8b452-117">Однако можно выбрать и другие способы создания модели, например, начать с кубов, измерений и создания наилучшей схемы для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="8b452-117">However, you can choose other ways to build a model, including starting with cubes and dimensions, and generating the schema that best supports your design.</span></span>  
  
 <span data-ttu-id="8b452-118">Каждой модели, независимо от способа создания, требуется хотя бы один объект источника данных, который задает соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="8b452-118">Regardless of how you build it, each model requires at least one data source object that specifies a connection to source data.</span></span> <span data-ttu-id="8b452-119">Можно создать несколько объектов источника данных в одной модели для использования данных из разных источников или изменять свойства соединения для конкретных объектов.</span><span class="sxs-lookup"><span data-stu-id="8b452-119">You can create multiple data source objects in a single model to use data from different sources or vary connection properties for specific objects.</span></span>  
  
 <span data-ttu-id="8b452-120">Управлять объектами источника данных можно независимо от других объектов в модели.</span><span class="sxs-lookup"><span data-stu-id="8b452-120">Data source objects can be managed independently of other objects in your model.</span></span> <span data-ttu-id="8b452-121">Свойства созданного источника данных можно позже изменить, а затем выполнить предварительную обработку модели для правильной выборки данных.</span><span class="sxs-lookup"><span data-stu-id="8b452-121">After you create a data source, you can change its properties later, and then preprocess the model to ensure the data is retrieved correctly.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="8b452-122">Связанные темы и задачи</span><span class="sxs-lookup"><span data-stu-id="8b452-122">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="8b452-123">Раздел</span><span class="sxs-lookup"><span data-stu-id="8b452-123">Topic</span></span>|<span data-ttu-id="8b452-124">Описание</span><span class="sxs-lookup"><span data-stu-id="8b452-124">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8b452-125">Поддерживаемые источники данных &#40;многомерные&#41;SSAS</span><span class="sxs-lookup"><span data-stu-id="8b452-125">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)|<span data-ttu-id="8b452-126">Описание типов источников данных, которые можно использовать в многомерной модели.</span><span class="sxs-lookup"><span data-stu-id="8b452-126">Describes the types of data sources that can be used in a multidimensional model.</span></span>|  
|[<span data-ttu-id="8b452-127">Создание источника данных (многомерные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="8b452-127">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](create-a-data-source-ssas-multidimensional.md)|<span data-ttu-id="8b452-128">Описывает добавление объекта источника данных в многомерную модель.</span><span class="sxs-lookup"><span data-stu-id="8b452-128">Explains how to add a data source object to a multidimensional model.</span></span>|  
|[<span data-ttu-id="8b452-129">Удаление источника данных в обозревателе решений (многомерные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="8b452-129">Delete a Data Source in Solution Explorer &#40;SSAS Multidimensional&#41;</span></span>](delete-a-data-source-in-solution-explorer-ssas-multidimensional.md)|<span data-ttu-id="8b452-130">Эта процедура позволяет удалить объект источника данных из многомерной модели.</span><span class="sxs-lookup"><span data-stu-id="8b452-130">Use this procedure to delete a data source object from a multidimensional model.</span></span>|  
|[<span data-ttu-id="8b452-131">Задание свойств источника данных (многомерные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="8b452-131">Set Data Source Properties &#40;SSAS Multidimensional&#41;</span></span>](set-data-source-properties-ssas-multidimensional.md)|<span data-ttu-id="8b452-132">Описывает каждое свойство и объясняет, как его задать.</span><span class="sxs-lookup"><span data-stu-id="8b452-132">Describes each property and explains how to set each one.</span></span>|  
|[<span data-ttu-id="8b452-133">Задание параметров олицетворения (службы SSAS — многомерные)</span><span class="sxs-lookup"><span data-stu-id="8b452-133">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](set-impersonation-options-ssas-multidimensional.md)|<span data-ttu-id="8b452-134">Объясняет настройку параметров в диалоговом окне «Сведения об олицетворении».</span><span class="sxs-lookup"><span data-stu-id="8b452-134">Explains how to configure options in the Impersonation Information dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b452-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b452-135">See Also</span></span>  
 <span data-ttu-id="8b452-136">[Объекты базы данных &#40;Analysis Services многомерных данных&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8b452-136">[Database Objects &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="8b452-137">[Логическая архитектура &#40;Analysis Services многомерных данных&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="8b452-137">[Logical Architecture &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span></span>  
 <span data-ttu-id="8b452-138">[Представления источников данных в многомерных моделях](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="8b452-138">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="8b452-139">Источники данных и привязки (многомерные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="8b452-139">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](data-sources-and-bindings-ssas-multidimensional.md)  
  
  
