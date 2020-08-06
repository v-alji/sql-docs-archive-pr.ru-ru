---
title: Источники данных из существующих объектов (мастер источников данных) (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourcewizard.specifyobject.f1
ms.assetid: e6ef6dea-9db8-45c4-8959-f9febd7caf7b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 621c938f4902c95dee1e2fcccb0f292597a565f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733282"
---
# <a name="data-sources-from-existing-objects-data-source-wizard-analysis-services"></a><span data-ttu-id="56483-102">Источники данных из существующих объектов (мастер источников данных) (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="56483-102">Data sources from existing objects (Data Source Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="56483-103">Используйте страницу **Источники данных из существующих объектов** для определения существующего источника данных или проекта, на котором будет основан новый источник данных.</span><span class="sxs-lookup"><span data-stu-id="56483-103">Use the **Data sources from existing objects** page to specify an existing data source or project on which to base the new data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="56483-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="56483-104">Options</span></span>  
 <span data-ttu-id="56483-105">**Создать источник данных, основанный на существующем источнике данных из вашего решения**</span><span class="sxs-lookup"><span data-stu-id="56483-105">**Create a data source based on an existing data source in your solution**</span></span>  
 <span data-ttu-id="56483-106">Выберите, если нужно создать новый источник данных на основе уже существующего источника данных в решении.</span><span class="sxs-lookup"><span data-stu-id="56483-106">Select to base the new data source on an existing data source in the solution.</span></span> <span data-ttu-id="56483-107">Когда создается, обновляется или развертывается проект, использующий новый источник данных, новый источник данных получает настройки источника данных, определенного выбором этого параметра.</span><span class="sxs-lookup"><span data-stu-id="56483-107">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires the settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="56483-108">**Источник данных**</span><span class="sxs-lookup"><span data-stu-id="56483-108">**Data source**</span></span>  
 <span data-ttu-id="56483-109">Из списка источников данных, сгруппированных по проектам, выберите источник данных, на основе которого нужно создать новый источник.</span><span class="sxs-lookup"><span data-stu-id="56483-109">Select a data source on which you want to base the new data source from the list of data sources, which is grouped by project.</span></span>  
  
 <span data-ttu-id="56483-110">**Создать источник данных на основе проекта служб Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="56483-110">**Create a data source based on an Analysis Services project**</span></span>  
 <span data-ttu-id="56483-111">Выберите, чтобы создать новый источник данных, ссылающийся на другой [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] проект в текущем решении.</span><span class="sxs-lookup"><span data-stu-id="56483-111">Select to create a new data source that references another [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in the current solution.</span></span> <span data-ttu-id="56483-112">Новый источник данных заимствует настройки из свойств `TargetServer` и `TargetDatabase` выбранного проекта.</span><span class="sxs-lookup"><span data-stu-id="56483-112">The new data source acquires settings from the `TargetServer` and `TargetDatabase` properties of the selected project.</span></span> <span data-ttu-id="56483-113">Когда создается, обновляется или развертывается проект, использующий новый источник данных, новый источник данных получает настройки источника данных, определенного выбором этого параметра.</span><span class="sxs-lookup"><span data-stu-id="56483-113">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="56483-114">**Проект**</span><span class="sxs-lookup"><span data-stu-id="56483-114">**Project**</span></span>  
 <span data-ttu-id="56483-115">Выберите проект, на который будет ссылаться новый источник данных.</span><span class="sxs-lookup"><span data-stu-id="56483-115">Select the project that you want to reference in the new data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56483-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="56483-116">See Also</span></span>  
 <span data-ttu-id="56483-117">[Справка F1 мастера источников данных &#40;Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="56483-117">[Data Source Wizard F1 Help &#40;Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span></span>  
 <span data-ttu-id="56483-118">[Источники данных в многомерных моделях](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="56483-118">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="56483-119">Поддерживаемые источники данных &#40;многомерные&#41;SSAS</span><span class="sxs-lookup"><span data-stu-id="56483-119">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
