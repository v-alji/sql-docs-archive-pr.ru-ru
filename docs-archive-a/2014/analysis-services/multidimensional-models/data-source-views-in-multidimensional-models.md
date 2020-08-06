---
title: Представления источников данных в многомерных моделях | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data source views [Analysis Services]
- data source views [Analysis Services], about data source views
- SQL Server Analysis Services, data source views
- data source views [Analysis Services], multiple
- Analysis Services, data source views
- multiple data source views
- SSAS, data source views
ms.assetid: 4c12376f-4fc2-492b-9a00-93eec34571ed
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1aef6b6d716ec71ac082ca8b7c042492c1712b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750308"
---
# <a name="data-source-views-in-multidimensional-models"></a><span data-ttu-id="63776-102">Представления источников данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="63776-102">Data Source Views in Multidimensional Models</span></span>
  <span data-ttu-id="63776-103">Представление источников данных представляет собой абстракцию реляционного источника данных, который становится основой кубов и измерений, создаваемых в многомерном проекте.</span><span class="sxs-lookup"><span data-stu-id="63776-103">A data source view (DSV) is an abstraction of a relational data source that becomes the basis of the cubes and dimensions you create in a multidimensional project.</span></span> <span data-ttu-id="63776-104">Представление источника данных позволяет управлять структурами данных, используемыми в проекте, и независимо работать с базовыми источниками данных (например, можно переименовать или объединить столбцы без непосредственного изменения исходного источника данных).</span><span class="sxs-lookup"><span data-stu-id="63776-104">The purpose of a DSV is to give you control over the data structures used in your project, and to work independently of the underlying data sources (for example, the ability to rename or concatenate columns without directly modifying the original data source).</span></span>  
  
 <span data-ttu-id="63776-105">Вы можете построить несколько представлений источников данных в проекте или в базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для одного или нескольких источников данных и сконструировать каждый из них для удовлетворения требований другого решения.</span><span class="sxs-lookup"><span data-stu-id="63776-105">You can build multiple data source views in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database on one or more data sources, and construct each one to satisfy the requirements for a different solution.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="63776-106">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="63776-106">Related Tasks</span></span>  
 [<span data-ttu-id="63776-107">Определение представления источников данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-107">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](defining-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-108">Добавление или удаление таблиц или представлений в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-108">Adding or Removing Tables or Views in a Data Source View &#40;Analysis Services&#41;</span></span>](adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-109">Изменение свойств в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-109">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-110">Определение логических связей в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-110">Define Logical Relationships in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-relationships-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-111">Определение логических первичных ключей в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-111">Define Logical Primary Keys in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-primary-keys-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-112">Определение именованных вычислений в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-112">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-113">Определение именованных запросов в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-113">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-114">Замена таблицы или именованного запроса в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-114">Replace a Table or a Named Query in a Data Source View &#40;Analysis Services&#41;</span></span>](replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-115">Работа с диаграммами в конструкторе представлений источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-115">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
 [<span data-ttu-id="63776-116">Просмотр данных в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-116">Explore Data in a Data Source View &#40;Analysis Services&#41;</span></span>](explore-data-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-117">Удаление представления источников данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-117">Delete a Data Source View &#40;Analysis Services&#41;</span></span>](delete-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="63776-118">Обновление схемы в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="63776-118">Refresh the Schema in a Data Source View &#40;Analysis Services&#41;</span></span>](refresh-the-schema-in-a-data-source-view-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="63776-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="63776-119">See Also</span></span>  
 <span data-ttu-id="63776-120">[Мастер формирования схем &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="63776-120">[Schema Generation Wizard &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span></span>  
 [<span data-ttu-id="63776-121">Поддерживаемые источники данных &#40;многомерные&#41;SSAS</span><span class="sxs-lookup"><span data-stu-id="63776-121">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
