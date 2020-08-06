---
title: Измерения (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- OLAP objects [Analysis Services], dimensions
- dimensions [Analysis Services]
- Analysis Services objects, dimensions
ms.assetid: 2b114135-2572-4479-8c81-3ccf0cfeb9f7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e0e15d4f74c2c6cec06edaf692199e48534c7e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738951"
---
# <a name="dimensions-analysis-services---multidimensional-data"></a><span data-ttu-id="b7d0b-102">Измерения (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="b7d0b-102">Dimensions (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b7d0b-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] измерения являются фундаментальным компонентом кубов.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], dimensions are a fundamental component of cubes.</span></span> <span data-ttu-id="b7d0b-104">В измерениях данные привязаны к некоторой предметной области, например заказчики, магазины или служащие.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-104">Dimensions organize data with relation to an area of interest, such as customers, stores, or employees, to users.</span></span> <span data-ttu-id="b7d0b-105">В службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] измерения содержат атрибуты, которые соответствуют столбцам в таблицах измерения.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-105">Dimensions in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contain attributes that correspond to columns in dimension tables.</span></span> <span data-ttu-id="b7d0b-106">Эти атрибуты отображаются как иерархии атрибутов и могут быть организованы в пользовательские иерархии или определены как иерархии типа «родители-потомки» на основе столбцов базовой таблицы измерений.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-106">These attributes appear as attribute hierarchies and can be organized into user-defined hierarchies, or can be defined as parent-child hierarchies based on columns in the underlying dimension table.</span></span> <span data-ttu-id="b7d0b-107">Эти иерархии применяются для организации мер, которые содержатся в кубе.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-107">Hierarchies are used to organize measures that are contained in a cube.</span></span> <span data-ttu-id="b7d0b-108">Следующие подразделы содержат описание измерений, атрибутов и иерархий.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-108">The following topics provide an overview of dimensions, attributes, and hierarchies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7d0b-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="b7d0b-109">In This Section</span></span>  
  
|<span data-ttu-id="b7d0b-110">Раздел</span><span class="sxs-lookup"><span data-stu-id="b7d0b-110">Topic</span></span>|<span data-ttu-id="b7d0b-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b7d0b-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b7d0b-112">Введение в измерения (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="b7d0b-112">Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="b7d0b-113">Содержит обзор основных понятий, связанных с измерениями.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-113">Provides an overview of dimension concepts.</span></span>|  
|[<span data-ttu-id="b7d0b-114">Атрибуты и иерархии атрибутов</span><span class="sxs-lookup"><span data-stu-id="b7d0b-114">Attributes and Attribute Hierarchies</span></span>](attributes-and-attribute-hierarchies.md)|<span data-ttu-id="b7d0b-115">Содержит описание атрибутов и их иерархий.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-115">Describes attributes and attribute hierarchies.</span></span>|  
|[<span data-ttu-id="b7d0b-116">Пользовательские иерархии</span><span class="sxs-lookup"><span data-stu-id="b7d0b-116">User Hierarchies</span></span>](user-hierarchies.md)|<span data-ttu-id="b7d0b-117">Описывает пользовательские иерархии атрибутов.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-117">Describes user-defined hierarchies of attributes.</span></span>|  
|[<span data-ttu-id="b7d0b-118">Измерения, доступные для записи</span><span class="sxs-lookup"><span data-stu-id="b7d0b-118">Write-Enabled Dimensions</span></span>](write-enabled-dimensions.md)|<span data-ttu-id="b7d0b-119">Содержит описание измерений, доступных для записи.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-119">Describes write-enabled dimensions.</span></span>|  
|[<span data-ttu-id="b7d0b-120">Переводы измерений</span><span class="sxs-lookup"><span data-stu-id="b7d0b-120">Dimension Translations</span></span>](dimension-translations.md)|<span data-ttu-id="b7d0b-121">Описывает переводы метаданных измерений.</span><span class="sxs-lookup"><span data-stu-id="b7d0b-121">Describes translations of dimension meta data.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7d0b-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7d0b-122">See Also</span></span>  
 <span data-ttu-id="b7d0b-123">[Измерения в многомерных моделях](../multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b7d0b-123">[Dimensions in Multidimensional Models](../multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="b7d0b-124">Объекты куба &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="b7d0b-124">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
  
