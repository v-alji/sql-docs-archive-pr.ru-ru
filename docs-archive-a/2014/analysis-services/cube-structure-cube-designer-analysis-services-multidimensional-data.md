---
title: Структура куба (конструктор кубов) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.cubebuilderview.f1
ms.assetid: 00f0b605-5352-4b42-84f5-bd6c3e42d3d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 857dd87c1d638a29adfa11c7de5a4d9f2d006314
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666905"
---
# <a name="cube-structure-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="eb33f-102">Структура куба (конструктор кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="eb33f-102">Cube Structure (Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="eb33f-103">Вкладка **Структура куба** в **Конструкторе кубов** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] служит для создания и изменения групп мер и самих мер, добавления измерений куба и отображения объектов, включенных в куб, из соответствующего представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="eb33f-103">Use the **Cube Structure** tab in **Cube Designer** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create and modify measure groups and measures, add cube dimensions, and display the objects included in the cube from the associated data source view.</span></span>  
  
 <span data-ttu-id="eb33f-104">Вкладка **Структура куба** содержит следующие панели.</span><span class="sxs-lookup"><span data-stu-id="eb33f-104">The **Cube Structure** tab contains the following panes:</span></span>  
  
## <a name="panes"></a><span data-ttu-id="eb33f-105">Панели</span><span class="sxs-lookup"><span data-stu-id="eb33f-105">Panes</span></span>  
  
|<span data-ttu-id="eb33f-106">Панель</span><span class="sxs-lookup"><span data-stu-id="eb33f-106">Pane</span></span>|<span data-ttu-id="eb33f-107">Определение</span><span class="sxs-lookup"><span data-stu-id="eb33f-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="eb33f-108">**Панель инструментов**</span><span class="sxs-lookup"><span data-stu-id="eb33f-108">**Toolbar**</span></span>|<span data-ttu-id="eb33f-109">Используйте панель инструментов для выполнения общих действий на этой вкладке. Дополнительные сведения об этой панели см. в разделе [панель инструментов &#40;вкладка Структура куба, конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="eb33f-109">Use the toolbar to perform common actions in this tab. For more information about this pane, see [Toolbar &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md).</span></span>|  
|<span data-ttu-id="eb33f-110">**Мерам**</span><span class="sxs-lookup"><span data-stu-id="eb33f-110">**Measures**</span></span>|<span data-ttu-id="eb33f-111">панель **Меры** позволяет создавать и изменять группы мер и сами меры для выбранного куба.</span><span class="sxs-lookup"><span data-stu-id="eb33f-111">Use the **Measures** pane to create and modify measure groups and measures for the selected cube.</span></span> <span data-ttu-id="eb33f-112">Дополнительные сведения об этой панели см. в разделе [Меры (вкладка "Структура куба", конструктор кубов) (службы Analysis Services — многомерные данные)](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="eb33f-112">For more information about this pane, see [Measures &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md).</span></span>|  
|<span data-ttu-id="eb33f-113">**Измерения**</span><span class="sxs-lookup"><span data-stu-id="eb33f-113">**Dimensions**</span></span>|<span data-ttu-id="eb33f-114">Панель **Измерения** позволяет включать и изменять измерения для выбранного куба.</span><span class="sxs-lookup"><span data-stu-id="eb33f-114">Use the **Dimensions** pane to include and modify cube dimensions for the selected cube.</span></span> <span data-ttu-id="eb33f-115">Дополнительные сведения об этой панели см. в разделе [Измерения (вкладка "Структура куба", конструктор кубов) (службы Analysis Services — многомерные данные)](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="eb33f-115">For more information about this pane, see [Dimensions &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md).</span></span>|  
|<span data-ttu-id="eb33f-116">**Представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="eb33f-116">**Data Source View**</span></span>|<span data-ttu-id="eb33f-117">Панель **Представление источника данных** позволяет просматривать и изменять представление источника данных, связанное с выбранным кубом.</span><span class="sxs-lookup"><span data-stu-id="eb33f-117">Use the **Data Source View** pane to view and edit the data source view associated with the selected cube.</span></span> <span data-ttu-id="eb33f-118">Дополнительные сведения об этой панели см. в разделе [Представление источника данных (вкладка "Структура куба", конструктор кубов) (службы Analysis Services — многомерные данные)](data-source-view-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="eb33f-118">For more information about this pane, see [Data Source View &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-cube-designer-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb33f-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb33f-119">See Also</span></span>  
 <span data-ttu-id="eb33f-120">[Логическая архитектура &#40;Analysis Services многомерных данных&#41;](multidimensional-models/olap-logical/understanding-microsoft-olap-logical-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="eb33f-120">[Logical Architecture &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/olap-logical/understanding-microsoft-olap-logical-architecture.md) </span></span>  
 <span data-ttu-id="eb33f-121">[Кубы в многомерных моделях](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="eb33f-121">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="eb33f-122">[Настройка свойств мер](multidimensional-models/configure-measure-properties.md) </span><span class="sxs-lookup"><span data-stu-id="eb33f-122">[Configure Measure Properties](multidimensional-models/configure-measure-properties.md) </span></span>  
 <span data-ttu-id="eb33f-123">[Измерения &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="eb33f-123">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="eb33f-124">[Представления источников данных в многомерных моделях](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="eb33f-124">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="eb33f-125">Конструктор кубов &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="eb33f-125">Cube Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-designer-analysis-services-multidimensional-data.md)  
  
  
