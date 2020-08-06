---
title: Основные сведения об архитектуре Microsoft OLAP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- multidimensional data [Analysis Services], about multidimensional data
ms.assetid: a2eaaee8-7b06-48af-ba44-e21a3678c4c4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1abbbbd7c2f7caa99407bbcd17ace07deac5dfeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665628"
---
# <a name="understanding-microsoft-olap-architecture"></a><span data-ttu-id="ede17-102">Основные сведения об архитектуре Microsoft OLAP</span><span class="sxs-lookup"><span data-stu-id="ede17-102">Understanding Microsoft OLAP Architecture</span></span>
  <span data-ttu-id="ede17-103">Изучите указанные ниже разделы, чтобы лучше понять работу многомерных баз данных служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] и запланировать способ реализации многомерных баз данных в своем решении бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="ede17-103">Use these topics to better understand [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] multidimensional databases and plan how to implement multidimensional databases in your business intelligence solution.</span></span>  
  
 <span data-ttu-id="ede17-104">![Маленький значок папки с файлами](../../../integration-services/media/filefolder-small.gif "Маленький значок папки") **логическая архитектура**</span><span class="sxs-lookup"><span data-stu-id="ede17-104">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **Logical Architecture**</span></span>  
 [<span data-ttu-id="ede17-105">Серверные объекты &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede17-105">Server Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../olap-logical/server-objects-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="ede17-106">Объекты измерения &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede17-106">Dimension Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimension-objects-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="ede17-107">Объекты куба &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede17-107">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="ede17-108">Другие...</span><span class="sxs-lookup"><span data-stu-id="ede17-108">More...</span></span>](../olap-logical/understanding-microsoft-olap-logical-architecture.md)  
  
 <span data-ttu-id="ede17-109">![Маленький значок папки с файлами](../../../integration-services/media/filefolder-small.gif "Маленький значок папки") **физическая архитектура**</span><span class="sxs-lookup"><span data-stu-id="ede17-109">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **Physical Architecture**</span></span>  
 [<span data-ttu-id="ede17-110">Серверные компоненты ядра OLAP</span><span class="sxs-lookup"><span data-stu-id="ede17-110">OLAP Engine Server Components</span></span>](olap-engine-server-components.md)  
  
 [<span data-ttu-id="ede17-111">Локальные Кубы &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ede17-111">Local Cubes &#40;Analysis Services - Multidimensional Data&#41;</span></span>](local-cubes-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="ede17-112">Другие...</span><span class="sxs-lookup"><span data-stu-id="ede17-112">More...</span></span>](understanding-microsoft-olap-physical-architecture.md)  
  
 <span data-ttu-id="ede17-113">![Маленький значок папки с файлами](../../../integration-services/media/filefolder-small.gif "Маленький значок папки") **Архитектура программирования**</span><span class="sxs-lookup"><span data-stu-id="ede17-113">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **Programming Architecture**</span></span>  
 [<span data-ttu-id="ede17-114">Разработка объектов управления аналитикой (объекты AMO)</span><span class="sxs-lookup"><span data-stu-id="ede17-114">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)  
  
 [<span data-ttu-id="ede17-115">Разработка на языке ASSL (язык ASSL)</span><span class="sxs-lookup"><span data-stu-id="ede17-115">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
  
 [<span data-ttu-id="ede17-116">Разработка с использованием ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="ede17-116">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
  
 <span data-ttu-id="ede17-117">![Маленький значок папки с файлами](../../../integration-services/media/filefolder-small.gif "Маленький значок папки") **вопросы международного** использования</span><span class="sxs-lookup"><span data-stu-id="ede17-117">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **International Considerations**</span></span>  
 [<span data-ttu-id="ede17-118">Сценарии глобализации для многомерных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ede17-118">Globalization scenarios for Analysis Services Multiidimensional</span></span>](../../globalization-scenarios-for-analysis-services-multiidimensional.md)  
  
## <a name="see-also"></a><span data-ttu-id="ede17-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="ede17-119">See Also</span></span>  
 [<span data-ttu-id="ede17-120">Технический справочник &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="ede17-120">Technical Reference &#40;SSAS&#41;</span></span>](../../powershell/technical-reference-ssas.md)  
  
  
