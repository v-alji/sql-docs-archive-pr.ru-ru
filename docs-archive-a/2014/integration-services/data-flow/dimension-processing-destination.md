---
title: Назначение "Обработка измерений" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimensionprocessingdest.f1
helpviewer_keywords:
- Dimension Processing destination
- loading dimensions
- destinations [Integration Services], Dimension Processing
- dimensions [Analysis Services], processing
ms.assetid: 4c49bb95-7259-42f4-a785-bb6aaf5f8566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61cde87ac4fa5fcb1352491d787674447dd404b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657206"
---
# <a name="dimension-processing-destination"></a><span data-ttu-id="9155a-102">назначение «Обработка измерений»</span><span class="sxs-lookup"><span data-stu-id="9155a-102">Dimension Processing Destination</span></span>
  <span data-ttu-id="9155a-103">Назначение "Обработка измерений" загружает и обрабатывает измерение служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9155a-103">The Dimension Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimension.</span></span> <span data-ttu-id="9155a-104">Дополнительные сведения об измерениях см. в разделе [Измерения (службы Analysis Services — многомерные данные)](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="9155a-104">For more information about dimensions, see [Dimensions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="9155a-105">Назначение «Обработка измерений» включает следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="9155a-105">The Dimension Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="9155a-106">Параметры для выполнения добавочной обработки, полной обработки или обработки обновления.</span><span class="sxs-lookup"><span data-stu-id="9155a-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="9155a-107">Конфигурация ошибок, определяющая, пропускает ли ошибки обработка измерений или останавливается после определенного числа ошибок.</span><span class="sxs-lookup"><span data-stu-id="9155a-107">Error configuration, to specify whether dimension processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="9155a-108">Сопоставление входных столбцов со столбцами в таблицах измерения.</span><span class="sxs-lookup"><span data-stu-id="9155a-108">Mapping of input columns to columns in dimension tables.</span></span>  
  
 <span data-ttu-id="9155a-109">Дополнительные сведения об обработке объектов [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] см. в разделе [Настройка параметров обработки (службы Analysis Services)](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="9155a-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
## <a name="configuration-of-the-dimension-processing-destination"></a><span data-ttu-id="9155a-110">Настройка назначения «Обработка измерения»</span><span class="sxs-lookup"><span data-stu-id="9155a-110">Configuration of the Dimension Processing Destination</span></span>  
 <span data-ttu-id="9155a-111">Назначение «Обработка измерений» использует диспетчер соединений служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , чтобы подключиться к проекту служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или экземпляру служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , содержащему измерения, обрабатываемые назначением.</span><span class="sxs-lookup"><span data-stu-id="9155a-111">The Dimension Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the dimensions the destination processes.</span></span> <span data-ttu-id="9155a-112">Дополнительные сведения см. в статье [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9155a-112">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="9155a-113">Данное назначение имеет один вход.</span><span class="sxs-lookup"><span data-stu-id="9155a-113">This destination has one input.</span></span> <span data-ttu-id="9155a-114">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9155a-114">It does not support an error output.</span></span>  
  
 <span data-ttu-id="9155a-115">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="9155a-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="9155a-116">Дополнительные сведения о свойствах, которые можно настроить при помощи диалогового окна **Редактор назначения обработки измерений** , см. в одном из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="9155a-116">For more information about the properties that you can set in the **Dimension Processing Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="9155a-117">Редактор назначения "Обработка измерения" (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="9155a-117">Dimension Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../dimension-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="9155a-118">Редактор назначения "Обработка измерения" (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="9155a-118">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../dimension-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="9155a-119">Редактор назначения "Обработка измерения" (страница "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="9155a-119">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../dimension-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="9155a-120">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="9155a-120">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="9155a-121">Дополнительные сведения о свойствах, которые можно задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="9155a-121">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="9155a-122">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="9155a-122">Common Properties</span></span>](../common-properties.md)  
  
 <span data-ttu-id="9155a-123">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="9155a-123">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9155a-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="9155a-124">See Also</span></span>  
 <span data-ttu-id="9155a-125">[Поток данных](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="9155a-125">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="9155a-126">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="9155a-126">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
