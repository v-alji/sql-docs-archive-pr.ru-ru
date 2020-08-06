---
title: Архитектура интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 105f52e1-ad3b-4cd0-b67b-06dbb451c304
author: minewiskan
ms.author: owend
ms.openlocfilehash: a372972fd7fa39f7bcfd2e10abbc4fbf8f8c10aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667489"
---
# <a name="data-mining-architecture"></a><span data-ttu-id="77b30-102">Архитектора интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="77b30-102">Data Mining Architecture</span></span>
  <span data-ttu-id="77b30-103">В этом разделе описывается архитектура решений интеллектуального анализа данных, размещаемых на экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77b30-103">This section describes the architecture of data mining solutions that are hosted in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="77b30-104">В подразделах этого раздела описывается логическая и физическая архитектура экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , который поддерживает интеллектуальный анализ данных, а также приводятся сведения о клиентах, поставщиках и протоколах, которые используются для связи с серверами интеллектуального анализа данных и работы с объектами интеллектуального анализа как локально, так и удаленно.</span><span class="sxs-lookup"><span data-stu-id="77b30-104">The topics in this section describe the logical and physical architecture of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that supports data mining, and also provide information about the clients, providers, and protocols that can be used to communicate with data mining servers, and to work with data mining objects either locally or remotely.</span></span>  
  
 <span data-ttu-id="77b30-105">В целом интеллектуальный анализ данных SQL Server работает как служба в рамках экземпляра [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , работающего в многомерном режиме. Именно поэтому рекомендуется просмотреть следующие разделы электронной документации, в которых описывается работа, обслуживание и настройка многомерных решений [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77b30-105">In general, SQL Server Data Mining operates as a service that is provided as part of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance running in multidimensional mode; therefore, we recommend that you also review the following sections of Books Online that describe the operation, maintenance, and configuration of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] multidimensional solutions.</span></span>  
  
 [<span data-ttu-id="77b30-106">Обработка объектов многомерной модели</span><span class="sxs-lookup"><span data-stu-id="77b30-106">Multidimensional Model Object Processing</span></span>](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="77b30-107">Подключение к службам Analysis Services</span><span class="sxs-lookup"><span data-stu-id="77b30-107">Connect to Analysis Services</span></span>](../instances/connect-to-analysis-services.md)  
  
 [<span data-ttu-id="77b30-108">Место хранения базы данных</span><span class="sxs-lookup"><span data-stu-id="77b30-108">Database Storage Location</span></span>](../multidimensional-models/database-storage-location.md)  
  
 [<span data-ttu-id="77b30-109">Переключение базы данных служб Analysis Services между режимами ReadOnly и ReadWrite</span><span class="sxs-lookup"><span data-stu-id="77b30-109">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>](../multidimensional-models/switch-an-analysis-services-database-between-readonly-and-readwrite-modes.md)  
  
 <span data-ttu-id="77b30-110">Дополнительные сведения о реализации интеллектуального анализа данных в решении бизнес-аналитики см. в разделе «Руководства к решениям» в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="77b30-110">For more information about how you can implement data mining in your business intelligence solution, see the Solution Guides section of the MSDN Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77b30-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="77b30-111">In This Section</span></span>  
 [<span data-ttu-id="77b30-112">Логическая архитектура (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="77b30-112">Logical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](logical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="77b30-113">Физическая архитектура (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="77b30-113">Physical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](physical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="77b30-114">Службы интеллектуального анализа данных и источники данных</span><span class="sxs-lookup"><span data-stu-id="77b30-114">Data Mining Services and Data Sources</span></span>](data-mining-services-and-data-sources.md)  
  
 [<span data-ttu-id="77b30-115">Управление решениями и объектами интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="77b30-115">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
 [<span data-ttu-id="77b30-116">Общие сведения о безопасности (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="77b30-116">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="77b30-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="77b30-117">See Also</span></span>  
 <span data-ttu-id="77b30-118">[Программирование многомерной модели](../multidimensional-models/multidimensional-model-programming.md) </span><span class="sxs-lookup"><span data-stu-id="77b30-118">[Multidimensional Model Programming](../multidimensional-models/multidimensional-model-programming.md) </span></span>  
 [<span data-ttu-id="77b30-119">Программирование интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="77b30-119">Data Mining Programming</span></span>](../dev-guide/data-mining-programming.md)  
  
  
