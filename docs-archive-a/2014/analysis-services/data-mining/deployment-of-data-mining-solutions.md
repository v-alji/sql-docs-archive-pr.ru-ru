---
title: Развертывание решений интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], deploying
- deploying [Analysis Services], production environments
- deploying [Analysis Services - data mining]
- solutions [Analysis Services], deploying
- models [Analysis Services], data mining
ms.assetid: d83effc7-437d-42e9-8ac3-b65f79e27043
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5764be2f7530add2fa4cb028b288be69598bb95c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667483"
---
# <a name="deployment-of-data-mining-solutions"></a><span data-ttu-id="757be-102">Развертывание решений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="757be-102">Deployment of Data Mining Solutions</span></span>
  <span data-ttu-id="757be-103">Последний шаг процесса интеллектуального анализа данных — это развертывание моделей в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="757be-103">The last step in the data mining process is to deploy the models to a production environment.</span></span> <span data-ttu-id="757be-104">Процесс развертывания важен, так как делает модели доступными пользователям для решения любой из следующих задач.</span><span class="sxs-lookup"><span data-stu-id="757be-104">Deployment is important because it makes the models available to users so that you can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="757be-105">Использование моделей для создания прогнозов и принятия бизнес-решений.</span><span class="sxs-lookup"><span data-stu-id="757be-105">Use the models to create predictions and make business decisions.</span></span> <span data-ttu-id="757be-106">Сведения о средствах, которые можно использовать для создания запросов, см. в разделе [интерфейсы запросов интеллектуального анализа данных](data-mining-query-tools.md).</span><span class="sxs-lookup"><span data-stu-id="757be-106">For information about the tools you can use to create queries, see [Data Mining Query Interfaces](data-mining-query-tools.md).</span></span>  
  
-   <span data-ttu-id="757be-107">Внедрение функций интеллектуального анализа данных непосредственно в приложение.</span><span class="sxs-lookup"><span data-stu-id="757be-107">Embed data mining functionality directly into an application.</span></span> <span data-ttu-id="757be-108">Можно включать объекты AMO или сборку, содержащую набор объектов, которые выбранное приложение может использовать для создания, изменения, обработки и удаления структур и моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="757be-108">You can include Analysis Management Objects (AMO) or an assembly that contains a set of objects that your application can use to create, alter, process, and delete mining structures and mining models.</span></span>  
  
-   <span data-ttu-id="757be-109">Создание отчетов, позволяющих пользователям запрашивать прогнозы, просматривать тенденции и сравнивать модели.</span><span class="sxs-lookup"><span data-stu-id="757be-109">Create reports that let users request predictions, view trends, or compare models.</span></span>  
  
 <span data-ttu-id="757be-110">В этом разделе подробно описаны параметры развертывания.</span><span class="sxs-lookup"><span data-stu-id="757be-110">This section provides detailed information about deployment options.</span></span>  
  
 [<span data-ttu-id="757be-111">Требования к развертыванию решений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="757be-111">Requirements for Deployment of Data Mining Solutions</span></span>](#bkmk_Reqs)  
  
 [<span data-ttu-id="757be-112">Развертывание решения с реляционными данными</span><span class="sxs-lookup"><span data-stu-id="757be-112">Deploying a Relational Solution</span></span>](#bkmk_RelationalSltn)  
  
 [<span data-ttu-id="757be-113">Развертывание решения с многомерными данными</span><span class="sxs-lookup"><span data-stu-id="757be-113">Deploying a Multidimensional Solution</span></span>](#bkmk_MDSltn)  
  
 [<span data-ttu-id="757be-114">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="757be-114">Related Resources</span></span>](#bkmk_Resources)  
  
## <a name="in-this-section"></a><span data-ttu-id="757be-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="757be-115">In This Section</span></span>  
 [<span data-ttu-id="757be-116">Развертывание решения интеллектуального анализа данных в предыдущих версиях SQL Server</span><span class="sxs-lookup"><span data-stu-id="757be-116">Deploy a Data Mining Solution to Previous Versions of SQL Server</span></span>](deploy-a-data-mining-solution-to-previous-versions-of-sql-server.md)  
  
 [<span data-ttu-id="757be-117">Экспорт и импорт объектов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="757be-117">Export and Import Data Mining Objects</span></span>](export-and-import-data-mining-objects.md)  
  
##  <a name="requirements-for-deployment-of-data-mining-solutions"></a><a name="bkmk_Reqs"></a><span data-ttu-id="757be-118">Требования к развертыванию решений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="757be-118">Requirements for Deployment of Data Mining Solutions</span></span>  
 <span data-ttu-id="757be-119">Экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], на котором развертывается решение, должен работать в режиме, поддерживающем многомерные объекты и объекты интеллектуального анализа данных, т. е. невозможно развернуть объекты интеллектуального анализа данных на экземпляре, который содержит данные табличных моделей или данные PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="757be-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="757be-120">Поэтому, если решение интеллектуального анализа данных создается в среде Visual Studio, обязательно используйте шаблон **Проект многомерных данных и интеллектуального анализа данных служб Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="757be-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="757be-121">Во время развертывания решения объекты, используемые для интеллектуального анализа данных, создаются на указанном экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] — в базе данных, имя которой совпадает с именем файла решения.</span><span class="sxs-lookup"><span data-stu-id="757be-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
###  <a name="deploying-a-relational-solution"></a><a name="bkmk_RelationalSltn"></a><span data-ttu-id="757be-122">Развертывание реляционного решения</span><span class="sxs-lookup"><span data-stu-id="757be-122">Deploying a Relational Solution</span></span>  
 <span data-ttu-id="757be-123">При развертывании решения интеллектуального анализа данных с реляционными данными объекты, используемые для интеллектуального анализа данных, создаются на указанном экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] — в базе данных, имя которой совпадает с именем файла решения.</span><span class="sxs-lookup"><span data-stu-id="757be-123">When you deploy a relational data mining solution, the required data mining objects are created within a new [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, and the objects are processed by default.</span></span> <span data-ttu-id="757be-124">Параметры обработки можно изменить с помощью свойства конфигурации **Параметр обработки**.</span><span class="sxs-lookup"><span data-stu-id="757be-124">You can change processing options by using the configuration property, **Processing Option**.</span></span> <span data-ttu-id="757be-125">Дополнительные сведения см. в разделах [Настройка свойств проекта служб Analysis Services (среда SSDT)](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md)создаются определенные объекты.</span><span class="sxs-lookup"><span data-stu-id="757be-125">For more information, see [Configure Analysis Services Project Properties &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span></span>  
  
 <span data-ttu-id="757be-126">По умолчанию каждый раз развертываются только дополнительные изменения.</span><span class="sxs-lookup"><span data-stu-id="757be-126">By default, only incremental changes are deployed each time.</span></span> <span data-ttu-id="757be-127">Иными словами, если изменена модель интеллектуального анализа данных, то при следующем развертывании проекта будет обновлена только эта модель.</span><span class="sxs-lookup"><span data-stu-id="757be-127">In other words, you can modify a mining model, and when you re-deploy the project, only that mining model would be updated.</span></span> <span data-ttu-id="757be-128">Однако, если клиентов много, редактирование базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] может привести к ошибкам.</span><span class="sxs-lookup"><span data-stu-id="757be-128">However, if you have multiple clients editing the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, this can lead to errors.</span></span> <span data-ttu-id="757be-129">Если требуется изменить режим развертывания по умолчанию таким образом, чтобы при развертывании решения обновлялась вся база данных, измените свойство **Режим развертывания**</span><span class="sxs-lookup"><span data-stu-id="757be-129">To change the default deployment mode so that the entire database is refreshed when you deploy the solution, change the **Deployment Mode** property</span></span>  
  
 <span data-ttu-id="757be-130">В решении интеллектуального анализа данных с реляционными данными должны развертываться только такие объекты, как определение источника данных, любые представления источников данных и все зависимые модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="757be-130">In a relational data mining solution, the only objects that must be deployed are the data source definition, any data source views that were used, the mining structures, and all dependent mining models.</span></span>  
  
###  <a name="deploying-a-multidimensional-solution"></a><a name="bkmk_MDSltn"></a><span data-ttu-id="757be-131">Развертывание многомерного решения</span><span class="sxs-lookup"><span data-stu-id="757be-131">Deploying a Multidimensional Solution</span></span>  
 <span data-ttu-id="757be-132">Если развертывается решение интеллектуального анализа данных с многомерными данными, это решение создает объекты интеллектуального анализа данных в той же базе данных, где находится исходный куб.</span><span class="sxs-lookup"><span data-stu-id="757be-132">When you deploy a multidimensional data mining solution, this solution creates your data mining objects within the same database as the source cube.</span></span>  
  
 <span data-ttu-id="757be-133">Поэтому во время обработки структуры или модели интеллектуального анализа данных необходимо обработать и исходный куб.</span><span class="sxs-lookup"><span data-stu-id="757be-133">When you process the mining structure or mining model, you must process the source cube as well.</span></span> <span data-ttu-id="757be-134">Поэтому развертывание решения, использующего модели интеллектуального анализа данных OLAP, может занять больше времени, чем развертывание решений с реляционными данными.</span><span class="sxs-lookup"><span data-stu-id="757be-134">For this reason, deploying a solution that uses OLAP mining models can take longer than relational data mining solutions.</span></span>  
  
 <span data-ttu-id="757be-135">Обычно объекты интеллектуального анализа данных используют те же источники данных и представления источников данных, которые используются в кубе.</span><span class="sxs-lookup"><span data-stu-id="757be-135">Typically data mining objects also use the same data sources and data source views that are used for the cube.</span></span> <span data-ttu-id="757be-136">Однако можно добавить источники данных и представления источников данных специально для интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="757be-136">However, you can add data sources and data source views that are targeted specifically to data mining.</span></span> <span data-ttu-id="757be-137">Например, обычно куб не содержит данных о потенциальных клиентах или внешних данных, которые не используются в многомерных объектах.</span><span class="sxs-lookup"><span data-stu-id="757be-137">For example, typically a cube would not contain data about prospective clients, or external data not used in the multidimensional objects.</span></span>  
  
##  <a name="related-resources"></a><a name="bkmk_Resources"></a><span data-ttu-id="757be-138">Связанные ресурсы</span><span class="sxs-lookup"><span data-stu-id="757be-138">Related Resources</span></span>  
 [<span data-ttu-id="757be-139">Перемещение объектов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="757be-139">Moving Data Mining Objects</span></span>](moving-data-mining-objects.md)  
  
 <span data-ttu-id="757be-140">Если модель основана только на реляционных данных, самым простым способом перемещения моделей является экспорт и импорт объектов с помощью инструкций DMX.</span><span class="sxs-lookup"><span data-stu-id="757be-140">If your model is based on relational data only, exporting and importing objects using DMX is the easiest way to move models.</span></span>  
  
 [<span data-ttu-id="757be-141">Перемещение базы данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="757be-141">Move an Analysis Services Database</span></span>](../multidimensional-models/move-an-analysis-services-database.md)  
  
 <span data-ttu-id="757be-142">Если модели используют куб в качестве источника данных, дополнительные сведения о перемещении моделей и соответствующих данных куба см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="757be-142">When models use a cube as a data source, refer to this topic for more information about how to move models and their supporting cube data.</span></span>  
  
 [<span data-ttu-id="757be-143">Развертывание проектов служб Analysis Services (среда SSDT)</span><span class="sxs-lookup"><span data-stu-id="757be-143">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](../multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
 <span data-ttu-id="757be-144">Содержит общие сведения о развертывании проектов служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и описывает свойства, которые можно задать как часть конфигурации проекта.</span><span class="sxs-lookup"><span data-stu-id="757be-144">Provides general information about deployment of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects, and describes the properties that you can set as part of the project configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757be-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="757be-145">See Also</span></span>  
 <span data-ttu-id="757be-146">[Обработка объектов многомерной модели](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="757be-146">[Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span></span>  
 <span data-ttu-id="757be-147">[Интерфейсы запросов интеллектуального анализа данных](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="757be-147">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="757be-148">Требования к обработке и связанные замечания (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="757be-148">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](processing-requirements-and-considerations-data-mining.md)  
  
  
