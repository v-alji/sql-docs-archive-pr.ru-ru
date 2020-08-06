---
title: Свойства пути | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- paths [Integration Services], properties
ms.assetid: 89b1e347-9579-4f6b-af74-c6519ea08eea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ca263b866fb6d5d7ceb6352f708f387d79cad4f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655808"
---
# <a name="path-properties"></a><span data-ttu-id="647e8-102">Свойства пути</span><span class="sxs-lookup"><span data-stu-id="647e8-102">Path Properties</span></span>
  <span data-ttu-id="647e8-103">Объекты потока данных в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] объектной модели имеют общие свойства и пользовательские свойства на уровне компонента, входов и выходов, а также входных и выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="647e8-103">The data flow objects in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model have common properties and custom properties at the level of the component, inputs and outputs, and input columns and output columns.</span></span> <span data-ttu-id="647e8-104">Многие свойства имеют значения, доступные только для чтения и присваиваемые подсистемой обработки потока данных на этапе выполнения.</span><span class="sxs-lookup"><span data-stu-id="647e8-104">Many properties have read-only values that are assigned at run time by the data flow engine.</span></span>  
  
 <span data-ttu-id="647e8-105">Этот раздел содержит список и описание пользовательских свойств путей, соединяющих объекты потоков данных.</span><span class="sxs-lookup"><span data-stu-id="647e8-105">This topic lists and describes the custom properties of the paths that connect data flow objects.</span></span>  
  
## <a name="path-properties"></a><span data-ttu-id="647e8-106">Свойства пути</span><span class="sxs-lookup"><span data-stu-id="647e8-106">Path Properties</span></span>  
 <span data-ttu-id="647e8-107">В модели объектов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] путь, соединяющий компоненты потока данных, реализует интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="647e8-107">In the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model, a path that connects components in the data flow implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> interface.</span></span>  
  
 <span data-ttu-id="647e8-108">В следующей таблице показаны настраиваемые свойства путей в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="647e8-108">The following table describes the configurable properties of the paths in a data flow.</span></span> <span data-ttu-id="647e8-109">Подсистема обработки потока данных также назначает значения дополнительным, доступным только для чтения, свойствам, которые здесь не перечислены.</span><span class="sxs-lookup"><span data-stu-id="647e8-109">The data flow engine also assigns values to additional read-only properties that are not listed here.</span></span>  
  
|<span data-ttu-id="647e8-110">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="647e8-110">Property name</span></span>|<span data-ttu-id="647e8-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="647e8-111">Data Type</span></span>|<span data-ttu-id="647e8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="647e8-112">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="647e8-113">PathAnnotation</span><span class="sxs-lookup"><span data-stu-id="647e8-113">PathAnnotation</span></span>|<span data-ttu-id="647e8-114">Integer (перечисление)</span><span class="sxs-lookup"><span data-stu-id="647e8-114">Integer (enumeration)</span></span>|<span data-ttu-id="647e8-115">Значение показывает, следует ли отображать описание рядом с путем в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="647e8-115">A value that indicates whether an annotation should be displayed with the path on the designer surface.</span></span> <span data-ttu-id="647e8-116">Допустимые значения — `AsNeeded`, `SourceName`, `PathName` и `Never`.</span><span class="sxs-lookup"><span data-stu-id="647e8-116">The possible values are `AsNeeded`, `SourceName`, `PathName`, and `Never`.</span></span> <span data-ttu-id="647e8-117">Значение по умолчанию — `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="647e8-117">The default value is `AsNeeded`.</span></span>|  
|<span data-ttu-id="647e8-118">DestinationName</span><span class="sxs-lookup"><span data-stu-id="647e8-118">DestinationName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100>|<span data-ttu-id="647e8-119">Вход, связанный с путем.</span><span class="sxs-lookup"><span data-stu-id="647e8-119">The input associated with the path.</span></span>|  
|<span data-ttu-id="647e8-120">SourceName</span><span class="sxs-lookup"><span data-stu-id="647e8-120">SourceName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>|<span data-ttu-id="647e8-121">Выход, связанный с путем.</span><span class="sxs-lookup"><span data-stu-id="647e8-121">The output associated with the path.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="647e8-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="647e8-122">See Also</span></span>  
 <span data-ttu-id="647e8-123">[Пути служб Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="647e8-123">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="647e8-124">[Common Properties](../../2014/integration-services/common-properties.md) </span><span class="sxs-lookup"><span data-stu-id="647e8-124">[Common Properties](../../2014/integration-services/common-properties.md) </span></span>  
 <span data-ttu-id="647e8-125">[Пользовательские свойства преобразования](data-flow/transformations/transformation-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="647e8-125">[Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md) </span></span>  
 [<span data-ttu-id="647e8-126">Свойства потока данных, которые можно задавать с помощью выражений</span><span class="sxs-lookup"><span data-stu-id="647e8-126">Data Flow Properties that Can Be Set by Using Expressions</span></span>](../../2014/integration-services/data-flow-properties-that-can-be-set-by-using-expressions.md)  
  
  
