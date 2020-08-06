---
title: Назначение обработки секции | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partitionprocessingdest.f1
helpviewer_keywords:
- partitions [Analysis Services], processing
- Partition Processing destination [Integration Services]
- destinations [Integration Services], Partition Processing
ms.assetid: 36c592ff-3f78-4a58-b496-31c1c8eee131
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d32306328f7a0575e55397d5209b4767d0cf1bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657186"
---
# <a name="partition-processing-destination"></a><span data-ttu-id="9599f-102">Назначение обработки секции</span><span class="sxs-lookup"><span data-stu-id="9599f-102">Partition Processing Destination</span></span>
  <span data-ttu-id="9599f-103">Назначение обработки секции производит загрузку и обработку секции служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9599f-103">The Partition Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] partition.</span></span> <span data-ttu-id="9599f-104">Дополнительные сведения о секциях см. в разделе [Секции (службы Analysis Services — многомерные данные)](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="9599f-104">For more information about partitions, see [Partitions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="9599f-105">Назначение обработки секции имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="9599f-105">The Partition Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="9599f-106">Параметры для выполнения добавочной обработки, полной обработки или обработки обновления.</span><span class="sxs-lookup"><span data-stu-id="9599f-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="9599f-107">Возможность установки конфигурации ошибки для указания, будет ли обработка пропускать ошибки или произведет остановку обработки после указанного количества ошибок.</span><span class="sxs-lookup"><span data-stu-id="9599f-107">Error configuration, to specify whether processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="9599f-108">Сопоставление входных столбцов и столбцов секционирования.</span><span class="sxs-lookup"><span data-stu-id="9599f-108">Mapping of input columns to partition columns.</span></span>  
  
 <span data-ttu-id="9599f-109">Дополнительные сведения об обработке объектов [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] см. в разделе [Настройка параметров обработки (службы Analysis Services)](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="9599f-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9599f-110">Описанные здесь задачи не применимы к табличным моделям служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9599f-110">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="9599f-111">Нельзя связать входные столбцы со столбцами секционирования для табличных моделей.</span><span class="sxs-lookup"><span data-stu-id="9599f-111">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="9599f-112">Вместо этого для обработки секции следует использовать задачу выполнения DDL [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9599f-112">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="configuration-of-the-partition-processing-destination"></a><span data-ttu-id="9599f-113">Настройка назначения «Обработка секций»</span><span class="sxs-lookup"><span data-stu-id="9599f-113">Configuration of the Partition Processing Destination</span></span>  
 <span data-ttu-id="9599f-114">Назначение обработки секций использует диспетчер соединений служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для соединения с проектом служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или экземпляром служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , который содержит кубы и секции, обрабатываемые назначением.</span><span class="sxs-lookup"><span data-stu-id="9599f-114">The Partition Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the cubes and partitions the destination processes.</span></span> <span data-ttu-id="9599f-115">Дополнительные сведения см. в статье [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9599f-115">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="9599f-116">Данное назначение имеет один вход.</span><span class="sxs-lookup"><span data-stu-id="9599f-116">This destination has one input.</span></span> <span data-ttu-id="9599f-117">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9599f-117">It does not support an error output.</span></span>  
  
 <span data-ttu-id="9599f-118">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="9599f-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="9599f-119">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор назначения обработки секций** , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9599f-119">For more information about the properties that you can set in the Partition Processing **Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="9599f-120">Редактор назначения "Обработка секций" (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="9599f-120">Partition Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../partition-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="9599f-121">Редактор назначения "Обработка секций" (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="9599f-121">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../partition-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="9599f-122">Редактор назначения "Обработка секций" (страница "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="9599f-122">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../partition-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="9599f-123">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="9599f-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="9599f-124">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9599f-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="9599f-125">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="9599f-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="9599f-126">Пользовательские свойства назначения «Обработка секций»</span><span class="sxs-lookup"><span data-stu-id="9599f-126">Partition Processing Destination Custom Properties</span></span>](partition-processing-destination-custom-properties.md)  
  
 <span data-ttu-id="9599f-127">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="9599f-127">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
