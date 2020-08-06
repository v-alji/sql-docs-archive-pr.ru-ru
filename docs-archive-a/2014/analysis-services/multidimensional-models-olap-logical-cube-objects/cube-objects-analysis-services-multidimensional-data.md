---
title: Объекты Cube (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], objects
ms.assetid: 5cee362e-3f95-4467-bc6c-29b1518ecbf3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0e6dfb75be696ab26893e668b99dc36c7340f86c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665160"
---
# <a name="cube-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="06f59-102">Объекты куба (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="06f59-102">Cube Objects (Analysis Services - Multidimensional Data)</span></span>
    
## <a name="introducing-cube-objects"></a><span data-ttu-id="06f59-103">Знакомство с объектами куба</span><span class="sxs-lookup"><span data-stu-id="06f59-103">Introducing Cube Objects</span></span>  
 <span data-ttu-id="06f59-104">Простой <xref:Microsoft.AnalysisServices.Cube> объект состоит из следующих основных сведений, измерений и групп мер.</span><span class="sxs-lookup"><span data-stu-id="06f59-104">A simple <xref:Microsoft.AnalysisServices.Cube> object is composed of: basic information, dimensions, and measure groups.</span></span> <span data-ttu-id="06f59-105">Основная информация включает имя куба по умолчанию, меру куба, источник данных, режим хранения и др.</span><span class="sxs-lookup"><span data-stu-id="06f59-105">Basic information includes the name of the cube, the default measure of the cube, the data source, the storage mode, and others.</span></span>  
  
 <span data-ttu-id="06f59-106">Коллекция Dimensions содержит фактический набор измерений из коллекции измерений базы данных, используемых в данном кубе.</span><span class="sxs-lookup"><span data-stu-id="06f59-106">The Dimensions collection contains the actual set of dimensions used in the cube from the database dimensions colection.</span></span> <span data-ttu-id="06f59-107">Все измерения должны быть определены в коллекции измерений базы данных, прежде чем на них можно будет ссылаться в кубе.</span><span class="sxs-lookup"><span data-stu-id="06f59-107">All dimensions have to be defined in the dimensions collection of the database before being referenced in the cube.</span></span> <span data-ttu-id="06f59-108">Закрытые измерения недоступны в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="06f59-108">Private dimensions are not available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="06f59-109">Группы мер — это множество мер в кубе.</span><span class="sxs-lookup"><span data-stu-id="06f59-109">Measure groups are sets of measures in the cube.</span></span> <span data-ttu-id="06f59-110">Группа мер представляет собой коллекцию мер, которые имеют общее представление источника данных и общее множество измерений.</span><span class="sxs-lookup"><span data-stu-id="06f59-110">A measure group is a collection of measures that have a common data source view and a common set of dimensions.</span></span> <span data-ttu-id="06f59-111">Группа мер — это единица обработки мер; группы мер могут обрабатываться отдельно, а затем просматриваться.</span><span class="sxs-lookup"><span data-stu-id="06f59-111">A measure group is the unit of process for measures; measure groups can be processed individually and then browsed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06f59-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="06f59-112">In this section</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="06f59-113">Раздел</span><span class="sxs-lookup"><span data-stu-id="06f59-113">Topic</span></span>||  
|[<span data-ttu-id="06f59-114">Действия (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="06f59-114">Actions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models/actions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="06f59-115">Aggregations and Aggregation Designs</span><span class="sxs-lookup"><span data-stu-id="06f59-115">Aggregations and Aggregation Designs</span></span>](aggregations-and-aggregation-designs.md)||  
|[<span data-ttu-id="06f59-116">Вычисления</span><span class="sxs-lookup"><span data-stu-id="06f59-116">Calculations</span></span>](calculations.md)||  
|[<span data-ttu-id="06f59-117">Ячейки куба &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="06f59-117">Cube Cells &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-cells-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="06f59-118">Свойства куба</span><span class="sxs-lookup"><span data-stu-id="06f59-118">Cube Properties</span></span>](cube-properties-multidimensional-model-programming.md)||  
|[<span data-ttu-id="06f59-119">Хранилище Куба &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="06f59-119">Cube Storage &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-storage-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="06f59-120">Переводы куба</span><span class="sxs-lookup"><span data-stu-id="06f59-120">Cube Translations</span></span>](cube-translations.md)||  
|[<span data-ttu-id="06f59-121">Связи измерений</span><span class="sxs-lookup"><span data-stu-id="06f59-121">Dimension Relationships</span></span>](dimension-relationships.md)||  
|[<span data-ttu-id="06f59-122">Ключевые показатели эффективности в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="06f59-122">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](../multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)||  
|[<span data-ttu-id="06f59-123">Меры и их группы</span><span class="sxs-lookup"><span data-stu-id="06f59-123">Measures and Measure Groups</span></span>](../multidimensional-models/measures-and-measure-groups.md)||  
|[<span data-ttu-id="06f59-124">Секции (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="06f59-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partitions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="06f59-125">Перспективы</span><span class="sxs-lookup"><span data-stu-id="06f59-125">Perspectives</span></span>](perspectives.md)||  
  
  
