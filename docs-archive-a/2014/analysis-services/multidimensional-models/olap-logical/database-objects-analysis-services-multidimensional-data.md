---
title: Объекты базы данных (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], about objects
- SQL Server Analysis Services, objects
- Analysis Services objects, about Analysis Services objects
- SSAS, objects
- Analysis Services objects
- objects [Analysis Services]
ms.assetid: f76d869b-fc1d-4807-9f28-da09c7be382d
author: minewiskan
ms.author: owend
ms.openlocfilehash: d61e3213356146e1cf9e452e0b62e02c96bd4902
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752464"
---
# <a name="database-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="2ddfe-102">Объекты баз данных (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="2ddfe-102">Database Objects (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="2ddfe-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] Экземпляр содержит объекты и сборки базы данных для использования с оперативной аналитической обработкой (OLAP) и интеллектуальным анализом данных.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-103">A [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance contains database objects and assemblies for use with online analytical processing (OLAP) and data mining.</span></span>  
  
-   <span data-ttu-id="2ddfe-104">В базах данных содержатся объекты OLAP и интеллектуального анализа данных, такие как источники данных, представления источников данных, кубы, меры, группы мер, атрибуты, иерархии, структуры и модели интеллектуального анализа данных, а также роли.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-104">Databases contain OLAP and data mining objects, such as data sources, data source views, cubes, measures, measure groups, dimensions, attributes, hierarchies, mining structures, mining models and roles.</span></span>  
  
-   <span data-ttu-id="2ddfe-105">В сборках содержатся пользовательские функции, расширяющие функциональность внутренних функций, обеспечиваемых языками многомерных выражений и расширениями интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-105">Assemblies contain user-defined functions that extend the functionality of the intrinsic functions provided with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span>  
  
 <span data-ttu-id="2ddfe-106">Объект <xref:Microsoft.AnalysisServices.Database> представляет собой контейнер для всех объектов данных, которые требуются для проектов бизнес-аналитики (таких как кубы OLAP, измерения и структуры интеллектуального анализа данных), а также для поддерживающих их объектов (таких как <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account> и <xref:Microsoft.AnalysisServices.Role>).</span><span class="sxs-lookup"><span data-stu-id="2ddfe-106">The <xref:Microsoft.AnalysisServices.Database> object is the container for all data objects that are needed for a business intelligence project (such as OLAP cubes, dimensions, and data mining structures), and their supporting objects (such as <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account>, and <xref:Microsoft.AnalysisServices.Role>).</span></span>  
  
 <span data-ttu-id="2ddfe-107">Объект <xref:Microsoft.AnalysisServices.Database> предоставляет доступ ко всем объектам и атрибутам, которые включают следующее.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-107">A <xref:Microsoft.AnalysisServices.Database> object provides access to objects and attributes that include the following:</span></span>  
  
-   <span data-ttu-id="2ddfe-108">Все кубы, к которым может быть получен доступ, в виде коллекции.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-108">All cubes that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="2ddfe-109">Все измерения, к которым может быть получен доступ, в виде коллекции.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-109">All dimensions that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="2ddfe-110">Все структуры интеллектуального анализа данных, к которым может быть получен доступ, в виде коллекции.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-110">All mining structures that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="2ddfe-111">Все источники данных и представления источников данных, в виде двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-111">All data sources and data source views, as two collections.</span></span>  
  
-   <span data-ttu-id="2ddfe-112">Все роли и разрешения базы данных, в виде двух коллекций.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-112">All roles and database permissions, as two collections.</span></span>  
  
-   <span data-ttu-id="2ddfe-113">Значение параметра сортировки для базы данных.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-113">The collation value for the database.</span></span>  
  
-   <span data-ttu-id="2ddfe-114">Предполагаемый размер базы данных.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-114">The estimated size of the database.</span></span>  
  
-   <span data-ttu-id="2ddfe-115">Значение языка базы данных.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-115">The language value of the database.</span></span>  
  
-   <span data-ttu-id="2ddfe-116">Параметр, определяющий, является ли база данных видимой.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-116">The visible setting for the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ddfe-117">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2ddfe-117">In This Section</span></span>  
 <span data-ttu-id="2ddfe-118">В следующих подразделах описываются объекты, совместно используемые как OLAP, так и функциями интеллектуального анализа данных в службах [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ddfe-118">The following topics describe objects shared by both OLAP and data mining features in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="2ddfe-119">Раздел</span><span class="sxs-lookup"><span data-stu-id="2ddfe-119">Topic</span></span>|<span data-ttu-id="2ddfe-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2ddfe-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2ddfe-121">Источники данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="2ddfe-121">Data Sources in Multidimensional Models</span></span>](../data-sources-in-multidimensional-models.md)|<span data-ttu-id="2ddfe-122">Содержит описание источника данных в службах [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ddfe-122">Describes a data source in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="2ddfe-123">Представления источников данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="2ddfe-123">Data Source Views in Multidimensional Models</span></span>](../data-source-views-in-multidimensional-models.md)|<span data-ttu-id="2ddfe-124">Содержит описание моделей логических данных, основанных на одном или более источниках данных в службе[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ddfe-124">Describes a logical data model based on one or more data sources, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="2ddfe-125">Кубы в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="2ddfe-125">Cubes in Multidimensional Models</span></span>](../cubes-in-multidimensional-models.md)|<span data-ttu-id="2ddfe-126">Содержит описание кубов и объектов кубов, включая меры, группы мер, связи использования измерений, вычисления, ключевые показатели эффективности, действия, переводы, секции и перспективы.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-126">Describes cubes and cube objects, including measures, measure groups, dimension usage relationships, calculations, key performance indicators, actions, translations, partitions, and perspectives.</span></span>|  
|[<span data-ttu-id="2ddfe-127">Измерения (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="2ddfe-127">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="2ddfe-128">Содержит описание измерений и объектов измерений, включая атрибуты, связи атрибутов, иерархии, уровни и элементы.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-128">Describes dimensions and dimension objects, including attributes, attribute relationships, hierarchies, levels, and members.</span></span>|  
|[<span data-ttu-id="2ddfe-129">Структуры интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="2ddfe-129">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](../../data-mining/mining-structures-analysis-services-data-mining.md)|<span data-ttu-id="2ddfe-130">Содержит описание структур и объектов интеллектуального анализа данных, включая модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-130">Describes mining structures and mining objects, including mining models.</span></span>|  
|[<span data-ttu-id="2ddfe-131">Роли безопасности (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="2ddfe-131">Security Roles  &#40;Analysis Services - Multidimensional Data&#41;</span></span>](security-roles-analysis-services-multidimensional-data.md)|<span data-ttu-id="2ddfe-132">Содержит описание роли, механизма безопасности, используемого для управления доступом к объектам в службах [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ddfe-132">Describes a role, the security mechanism used to control access to objects in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="2ddfe-133">Управление сборками многомерной модели</span><span class="sxs-lookup"><span data-stu-id="2ddfe-133">Multidimensional Model Assemblies Management</span></span>](../multidimensional-model-assemblies-management.md)|<span data-ttu-id="2ddfe-134">Содержит описание сборки, коллекции пользовательских функций, используемой для расширения языков многомерных выражений и для расширений интеллектуального анализа данных в службах [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ddfe-134">Describes an assembly, a collection of user-defined functions used to extend the MDX and DMX languages, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ddfe-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ddfe-135">See Also</span></span>  
 <span data-ttu-id="2ddfe-136">[Поддерживаемые источники данных &#40;многомерные&#41;SSAS](../supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="2ddfe-136">[Data Sources Supported &#40;SSAS Multidimensional&#41;](../supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="2ddfe-137">[Решения многомерной модели &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="2ddfe-137">[Multidimensional Model Solutions &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span></span>  
 [<span data-ttu-id="2ddfe-138">Решения интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="2ddfe-138">Data Mining Solutions</span></span>](../../data-mining/data-mining-solutions.md)  
  
  
