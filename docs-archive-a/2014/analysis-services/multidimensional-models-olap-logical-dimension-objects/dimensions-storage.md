---
title: Хранилище измерений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], storage
- storing data [Analysis Services]
- storage [Analysis Services], dimensions
- relational OLAP
- multidimensional OLAP
- MOLAP
- storing data [Analysis Services], dimensions
- ROLAP
ms.assetid: 8d74b932-2174-4e1f-8414-636455880b6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa68ebcfa8f4136bcd4a131842c852665ee9851
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728913"
---
# <a name="dimension-storage"></a><span data-ttu-id="86bab-102">Хранение измерений</span><span class="sxs-lookup"><span data-stu-id="86bab-102">Dimension Storage</span></span>
  <span data-ttu-id="86bab-103">Измерения в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] поддерживают два режима хранения:</span><span class="sxs-lookup"><span data-stu-id="86bab-103">Dimensions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support two storage modes:</span></span>  
  
-   <span data-ttu-id="86bab-104">Реляционный OLAP (ROLAP)</span><span class="sxs-lookup"><span data-stu-id="86bab-104">Relational OLAP (ROLAP)</span></span>  
  
-   <span data-ttu-id="86bab-105">Многомерный OLAP (MOLAP)</span><span class="sxs-lookup"><span data-stu-id="86bab-105">Multidimensional OLAP (MOLAP)</span></span>  
  
 <span data-ttu-id="86bab-106">Режим хранения определяет место и форму данных измерения.</span><span class="sxs-lookup"><span data-stu-id="86bab-106">The storage mode determines the location and form of a dimension's data.</span></span> <span data-ttu-id="86bab-107">MOLAP — режим хранения измерений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="86bab-107">MOLAP is the default storage mode for dimensions.</span></span> <span data-ttu-id="86bab-108">**См. также:**[режимы хранения секций и обработка](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span><span class="sxs-lookup"><span data-stu-id="86bab-108">**Related topics:**[Partition Storage Modes and Processing](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span></span>  
  
## <a name="molap"></a><span data-ttu-id="86bab-109">MOLAP</span><span class="sxs-lookup"><span data-stu-id="86bab-109">MOLAP</span></span>  
 <span data-ttu-id="86bab-110">Данные для измерения в режиме MOLAP хранятся в многомерной структуре в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86bab-110">Data for a dimension that uses MOLAP is stored in a multidimensional structure in the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="86bab-111">Эта многомерная структура создается и заполняется при обработке измерения.</span><span class="sxs-lookup"><span data-stu-id="86bab-111">This multidimensional structure is created and populated when the dimension is processed.</span></span> <span data-ttu-id="86bab-112">Измерения MOLAP обеспечивают более высокую производительность, чем измерения ROLAP.</span><span class="sxs-lookup"><span data-stu-id="86bab-112">MOLAP dimensions provide better query performance than ROLAP dimensions.</span></span>  
  
## <a name="rolap"></a><span data-ttu-id="86bab-113">ROLAP</span><span class="sxs-lookup"><span data-stu-id="86bab-113">ROLAP</span></span>  
 <span data-ttu-id="86bab-114">Данные для измерения, использующего режим ROLAP, фактически хранятся в таблицах, используемых для определения измерения.</span><span class="sxs-lookup"><span data-stu-id="86bab-114">Data for a dimension that uses ROLAP is actually stored in the tables used to define the dimension.</span></span> <span data-ttu-id="86bab-115">Режим хранения ROLAP можно использовать для крупных измерений без дублирования больших объемов данных, однако, это приведет к потере производительности запроса.</span><span class="sxs-lookup"><span data-stu-id="86bab-115">The ROLAP storage mode can be used to support large dimensions without duplicating large amounts of data, but at the expense of query performance.</span></span> <span data-ttu-id="86bab-116">Измерения основаны непосредственно на таблицах в представлении источника данных, используемого для определения измерения, поэтому режим хранения ROLAP также может поддерживать OLAP реального времени.</span><span class="sxs-lookup"><span data-stu-id="86bab-116">Because the dimension relies directly on the tables in the data source view used to define the dimension, the ROLAP storage mode also supports real-time OLAP.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="86bab-117">Если измерение использует режим хранения ROLAP и при этом входит в состав куба, использующего режим хранения MOLAP, все изменения схемы в исходной таблице должны сопровождаться немедленной обработкой куба.</span><span class="sxs-lookup"><span data-stu-id="86bab-117">If a dimension uses the ROLAP storage mode and the dimension is included in a cube that uses MOLAP storage, any schema changes to its source table must be followed by immediate processing of the cube.</span></span> <span data-ttu-id="86bab-118">В противном случае может возникнуть несогласованность результатов при запросах к кубу.</span><span class="sxs-lookup"><span data-stu-id="86bab-118">Failure to do this may result in inconsistent results when querying the cube.</span></span> <span data-ttu-id="86bab-119">**См**. также[в статье Автоматизация Analysis Services административных задач с помощью служб SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="86bab-119">**Related topic:**[Automate Analysis Services Administrative Tasks with SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86bab-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="86bab-120">See Also</span></span>  
 [<span data-ttu-id="86bab-121">Режимы хранения и обработка секции</span><span class="sxs-lookup"><span data-stu-id="86bab-121">Partition Storage Modes and Processing</span></span>](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
  
