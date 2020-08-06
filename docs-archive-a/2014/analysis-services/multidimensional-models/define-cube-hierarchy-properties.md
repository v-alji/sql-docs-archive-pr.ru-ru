---
title: Определение свойств иерархии куба | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], multilevel
- hierarchies [Analysis Services], cubes
ms.assetid: 819d0a4e-7815-4332-a605-b07ca2ade6ac
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8903a49754357aad9cf24ee63fffa45fbf120e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728889"
---
# <a name="define-cube-hierarchy-properties"></a><span data-ttu-id="54562-102">Определение свойств иерархии куба</span><span class="sxs-lookup"><span data-stu-id="54562-102">Define Cube Hierarchy Properties</span></span>
  <span data-ttu-id="54562-103">Свойства иерархии куба позволяют указывать уникальные настройки многоуровневых иерархий в измерениях куба на основе одного измерения базы данных.</span><span class="sxs-lookup"><span data-stu-id="54562-103">Cube hierarchy properties enable you to specify unique settings for user-defined hierarchies in cube dimensions based on the same database dimension.</span></span> <span data-ttu-id="54562-104">В следующей таблице описаны свойства иерархии куба.</span><span class="sxs-lookup"><span data-stu-id="54562-104">The following table describes the properties of a cube hierarchy.</span></span>  
  
|<span data-ttu-id="54562-105">Свойство</span><span class="sxs-lookup"><span data-stu-id="54562-105">Property</span></span>|<span data-ttu-id="54562-106">Описание</span><span class="sxs-lookup"><span data-stu-id="54562-106">Description</span></span>|  
|--------------|-----------------|  
|`Enabled`|<span data-ttu-id="54562-107">Указывает, включена ли иерархия для измерения куба.</span><span class="sxs-lookup"><span data-stu-id="54562-107">Determines whether the hierarchy is enabled for the cube dimension.</span></span>|  
|`HierarchyID`|<span data-ttu-id="54562-108">Содержит уникальный идентификатор (ID) иерархии.</span><span class="sxs-lookup"><span data-stu-id="54562-108">Contains the unique identifier (ID) of the hierarchy.</span></span>|  
|`OptimizedState`|<span data-ttu-id="54562-109">Определяет уровень оптимизации, применяемый к иерархии.</span><span class="sxs-lookup"><span data-stu-id="54562-109">Determines the level of optimization that is applied to the hierarchy.</span></span> <span data-ttu-id="54562-110">Это свойство может иметь следующие значения:</span><span class="sxs-lookup"><span data-stu-id="54562-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="54562-111">`FullyOptimized`: экземпляр создает индексы иерархии для улучшения производительности запросов.</span><span class="sxs-lookup"><span data-stu-id="54562-111">`FullyOptimized`: The instance builds indexes for the hierarchy to improve query performance.</span></span> <span data-ttu-id="54562-112">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="54562-112">This is the default value.</span></span><br /><br /> <span data-ttu-id="54562-113">`NotOptimized`: экземпляр не создает дополнительные индексы.</span><span class="sxs-lookup"><span data-stu-id="54562-113">`NotOptimized`: The instance does not build additional indexes.</span></span>|  
|`Visible`|<span data-ttu-id="54562-114">Определяет видимость иерархии кубов.</span><span class="sxs-lookup"><span data-stu-id="54562-114">Determines the visibility of the cube hierarchy.</span></span> <span data-ttu-id="54562-115">Значение по умолчанию — `True`.</span><span class="sxs-lookup"><span data-stu-id="54562-115">The default value is `True`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54562-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="54562-116">See Also</span></span>  
 [<span data-ttu-id="54562-117">Пользовательские иерархии</span><span class="sxs-lookup"><span data-stu-id="54562-117">User Hierarchies</span></span>](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md)  
  
  
