---
title: Логическая архитектура (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, architecture
- logical architecture [Analysis Services Multidimensional Data]
ms.assetid: 1b9cae0a-8990-4194-af5f-a1ea5f2aff06
author: minewiskan
ms.author: owend
ms.openlocfilehash: d93361fb14bc6544ffa7376439c2da0c8e06c3fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666818"
---
# <a name="logical-architecture-analysis-services---multidimensional-data"></a><span data-ttu-id="d988b-102">Логическая архитектура (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="d988b-102">Logical Architecture (Analysis Services - Multidimensional Data)</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="d988b-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] использует как серверные, так и клиентские компоненты для предоставления функциональных возможностей OLAP и интеллектуального анализа данных для приложений бизнес-аналитики:</span><span class="sxs-lookup"><span data-stu-id="d988b-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses both server and client components to supply online analytical processing (OLAP) and data mining functionality for business intelligence applications:</span></span>  
  
-   <span data-ttu-id="d988b-104">Серверный компонент служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] реализован в виде службы Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="d988b-104">The server component of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] is implemented as a Microsoft Windows service.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="d988b-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]поддерживает несколько экземпляров на одном компьютере, при этом каждый экземпляр [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] реализуется как отдельный экземпляр службы Windows.</span><span class="sxs-lookup"><span data-stu-id="d988b-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] supports multiple instances on the same computer, with each instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implemented as a separate instance of the Windows service.</span></span>  
  
-   <span data-ttu-id="d988b-106">Клиенты обмениваются данными со службами [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] с помощью общедоступного стандарта XML для аналитики (XMLA), который представляет собой протокол на базе SOAP для выполнения команд и получения ответов и предоставляется в виде веб-службы.</span><span class="sxs-lookup"><span data-stu-id="d988b-106">Clients communicate with [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] using the public standard XML for Analysis (XMLA), a SOAP-based protocol for issuing commands and receiving responses, exposed as a Web service.</span></span> <span data-ttu-id="d988b-107">Клиентские модели объектов также предоставляются через XML для аналитики, и доступ к ним производится через управляемый поставщик, например ADOMD.NET, или через собственный поставщик данных OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d988b-107">Client object models are also provided over XMLA, and can be accessed either by using a managed provider, such as ADOMD.NET, or a native OLE DB provider.</span></span>  
  
-   <span data-ttu-id="d988b-108">Команды запроса могут выдаваться с помощью следующих языков: SQL; МНОГОМЕРные выражения, язык запросов отраслевого стандарта для анализа; или расширения интеллектуального анализа данных (DMX) — язык запросов отраслевого стандарта, ориентированный на интеллектуальный анализ данных.</span><span class="sxs-lookup"><span data-stu-id="d988b-108">Query commands can be issued using the following languages: SQL; Multidimensional Expressions (MDX), an industry standard query language for analysis; or Data Mining Extensions (DMX), an industry standard query language oriented toward data mining.</span></span> <span data-ttu-id="d988b-109">Язык сценариев служб Analysis Services (ASSL) также может использоваться для управления объектами базы данных служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d988b-109">Analysis Services Scripting Language (ASSL) can also be used to manage [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database objects.</span></span>  
  
 <span data-ttu-id="d988b-110">Также службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] поддерживают ядро локального куба, которое позволяет приложениям на отключенных клиентах просматривать локально хранимые многомерные данные.</span><span class="sxs-lookup"><span data-stu-id="d988b-110">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] also supports a local cube engine that enables applications on disconnected clients to browse locally stored multidimensional data.</span></span> <span data-ttu-id="d988b-111">Дополнительные сведения см. в статье [требования к архитектуре клиента для разработки Analysis Services](../olap-physical/client-architecture-requirements-for-analysis-services-development.md) .</span><span class="sxs-lookup"><span data-stu-id="d988b-111">For more information, see [Client Architecture Requirements for Analysis Services Development](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d988b-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d988b-112">In This Section</span></span>  
 <span data-ttu-id="d988b-113">**Обзор логической архитектуры**</span><span class="sxs-lookup"><span data-stu-id="d988b-113">**Logical Architecture Overview**</span></span>  
 [<span data-ttu-id="d988b-114">Общие сведения об логической архитектуре &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d988b-114">Logical Architecture Overview &#40;Analysis Services - Multidimensional Data&#41;</span></span>](logical-architecture-overview-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="d988b-115">**Объекты сервера**</span><span class="sxs-lookup"><span data-stu-id="d988b-115">**Server Objects**</span></span>  
 [<span data-ttu-id="d988b-116">Серверные объекты &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d988b-116">Server Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](server-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="d988b-117">**Объекты базы данных**</span><span class="sxs-lookup"><span data-stu-id="d988b-117">**Database Objects**</span></span>  
 [<span data-ttu-id="d988b-118">Объекты баз данных (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="d988b-118">Database Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](database-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="d988b-119">**Объекты измерений**</span><span class="sxs-lookup"><span data-stu-id="d988b-119">**Dimension Objects**</span></span>  
 [<span data-ttu-id="d988b-120">Объекты измерения &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d988b-120">Dimension Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimension-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="d988b-121">**Объекты куба**</span><span class="sxs-lookup"><span data-stu-id="d988b-121">**Cube Objects**</span></span>  
 [<span data-ttu-id="d988b-122">Объекты куба &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d988b-122">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="d988b-123">**Безопасность доступа пользователей**</span><span class="sxs-lookup"><span data-stu-id="d988b-123">**User Access Security**</span></span>  
 [<span data-ttu-id="d988b-124">Архитектура безопасности доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="d988b-124">User Access Security Architecture</span></span>](understanding-microsoft-olap-logical-architecture.md)  
  
## <a name="see-also"></a><span data-ttu-id="d988b-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d988b-125">See Also</span></span>  
 <span data-ttu-id="d988b-126">[Основные сведения об архитектуре Microsoft OLAP](../olap-physical/understanding-microsoft-olap-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d988b-126">[Understanding Microsoft OLAP Architecture](../olap-physical/understanding-microsoft-olap-architecture.md) </span></span>  
 [<span data-ttu-id="d988b-127">Физическая архитектура (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="d988b-127">Physical Architecture &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../olap-physical/understanding-microsoft-olap-physical-architecture.md)  
  
  
