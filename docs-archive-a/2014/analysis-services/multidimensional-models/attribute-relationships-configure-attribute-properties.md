---
title: Настройка свойств связи атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- flexible relationships (Analysis Services)
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
- properties [Analysis Services], attribute relationships
- rigid relationships (Analysis Services)
ms.assetid: fce511af-66d7-42fc-bb3a-6c516f16b10e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 241fa2af16377fd2cacf657ec6f99c5ca4bd0c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655426"
---
# <a name="configure-attribute-relationship-properties"></a><span data-ttu-id="1339e-102">Настройка свойств связи атрибута</span><span class="sxs-lookup"><span data-stu-id="1339e-102">Configure Attribute Relationship Properties</span></span>
  <span data-ttu-id="1339e-103">В следующей таблице приведен список и описание свойств связи атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1339e-103">The following table lists and describes the properties of an attribute relationship.</span></span>  
  
|<span data-ttu-id="1339e-104">Свойство</span><span class="sxs-lookup"><span data-stu-id="1339e-104">Property</span></span>|<span data-ttu-id="1339e-105">Описание</span><span class="sxs-lookup"><span data-stu-id="1339e-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1339e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1339e-106">Attribute</span></span>|<span data-ttu-id="1339e-107">Содержит имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="1339e-107">Contains the name of the attribute.</span></span>|  
|<span data-ttu-id="1339e-108">Кратность</span><span class="sxs-lookup"><span data-stu-id="1339e-108">Cardinality</span></span>|<span data-ttu-id="1339e-109">Указывает количество элементов связи.</span><span class="sxs-lookup"><span data-stu-id="1339e-109">Indicates the cardinality of the relationship.</span></span> <span data-ttu-id="1339e-110">Значением является Many для связи типа «многие к одному» или One для связи «один к одному».</span><span class="sxs-lookup"><span data-stu-id="1339e-110">Values are Many, for a many to one relationship, or One, for a one to one relationship.</span></span> <span data-ttu-id="1339e-111">Значение по умолчанию — Many.</span><span class="sxs-lookup"><span data-stu-id="1339e-111">Default value is Many.</span></span> <span data-ttu-id="1339e-112">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] свойство кратности не оказывает никакого влияния — его использование зарезервировано для будущей реализации.</span><span class="sxs-lookup"><span data-stu-id="1339e-112">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the cardinality property has no effect - its use is reserved for a future implementation.</span></span>|  
|<span data-ttu-id="1339e-113">Имя</span><span class="sxs-lookup"><span data-stu-id="1339e-113">Name</span></span>|<span data-ttu-id="1339e-114">Содержит понятное имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="1339e-114">Contains the friendly name of the attribute.</span></span>|  
|<span data-ttu-id="1339e-115">RelationshipType</span><span class="sxs-lookup"><span data-stu-id="1339e-115">RelationshipType</span></span>|<span data-ttu-id="1339e-116">Указывает на изменение связей элементов со временем.</span><span class="sxs-lookup"><span data-stu-id="1339e-116">Indicates whether member relationships change over time.</span></span> <span data-ttu-id="1339e-117">Значением является Rigid, означающее, что связи между элементами со временем остаются неизменными, или Flexible, означающее, что связи между элементами со временем изменяются.</span><span class="sxs-lookup"><span data-stu-id="1339e-117">Values are Rigid, which means that relationships between members do not change over time, or Flexible, which means that relationships between members change over time.</span></span> <span data-ttu-id="1339e-118">Значение по умолчанию — Flexible.</span><span class="sxs-lookup"><span data-stu-id="1339e-118">Default is Flexible.</span></span> <span data-ttu-id="1339e-119">Если связь определена как гибкая, то агрегаты не сбрасываются, а после добавочного обновления выполняется их повторное вычисление (они не будут удаляться, если добавляются только новые элементы).</span><span class="sxs-lookup"><span data-stu-id="1339e-119">If you define a relationship as flexible, aggregations are dropped and recomputed as part of an incremental update (they will not be dropped if only new members are added).</span></span> <span data-ttu-id="1339e-120">Если связь определена как жесткая, агрегаты в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] сохраняются при добавочном обновлении измерения.</span><span class="sxs-lookup"><span data-stu-id="1339e-120">If you define a relationship as rigid, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retains aggregations when the dimension is incrementally updated.</span></span> <span data-ttu-id="1339e-121">Если же связь, определенная как жесткая, все-таки изменилась, то службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] во время добавочной обработки выдадут сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1339e-121">If a relationship that is defined as rigid actually changes, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generates an error during incremental processing.</span></span> <span data-ttu-id="1339e-122">Указание подходящих связей и свойств связей повышает производительность запросов и производительность обработки.</span><span class="sxs-lookup"><span data-stu-id="1339e-122">Specifying the appropriate relationships and relationship properties increases query and processing performance.</span></span>|  
|<span data-ttu-id="1339e-123">Видимый</span><span class="sxs-lookup"><span data-stu-id="1339e-123">Visible</span></span>|<span data-ttu-id="1339e-124">Определяет видимость связи атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1339e-124">Determines the visibility of the attribute relationship.</span></span> <span data-ttu-id="1339e-125">Значениями являются True или False.</span><span class="sxs-lookup"><span data-stu-id="1339e-125">Values are True or False.</span></span> <span data-ttu-id="1339e-126">Значение по умолчанию — True.</span><span class="sxs-lookup"><span data-stu-id="1339e-126">Default is True.</span></span>|  
  
  
