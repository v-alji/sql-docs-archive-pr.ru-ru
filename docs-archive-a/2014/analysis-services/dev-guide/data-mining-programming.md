---
title: Программирование интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- data mining [Analysis Services], developer's guide
ms.assetid: 9fd77b16-0b89-44ce-bcf1-7c04b62499da
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd4bd48b5914d5fda89f94c0a959e670ffec3321
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728930"
---
# <a name="data-mining-programming"></a><span data-ttu-id="3073f-102">Программирование интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="3073f-102">Data Mining Programming</span></span>
  <span data-ttu-id="3073f-103">Если встроенные инструменты и средства просмотра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не соответствуют требованиям, их можно расширить, создав собственные программные расширения служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3073f-103">If you find that the built-in tools and viewers in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="3073f-104">При таком подходе имеются два варианта.</span><span class="sxs-lookup"><span data-stu-id="3073f-104">In this approach, you have two options:</span></span>  
  
-   <span data-ttu-id="3073f-105">**XML для аналитики**</span><span class="sxs-lookup"><span data-stu-id="3073f-105">**XMLA**</span></span>  
  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="3073f-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)]поддерживает XML для аналитики (XMLA) в качестве протокола для связи с клиентскими приложениями.</span><span class="sxs-lookup"><span data-stu-id="3073f-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] supports XML for Analysis (XMLA) as a protocol for communication with client applications.</span></span> <span data-ttu-id="3073f-107">Службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] поддерживаются дополнительные команды, расширяющие спецификацию XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="3073f-107">Additional commands are supported by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that extend the XML for Analysis specification.</span></span>  
  
     <span data-ttu-id="3073f-108">Поскольку службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] используют XMLA для определения данных, управления данными и поддержки управления данными, можно создавать структуры интеллектуального анализа и модели интеллектуального анализа данных, используя визуальные средства среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], а затем расширяя объекты интеллектуального анализа данных, созданные с помощью скриптов DMX и ASSL.</span><span class="sxs-lookup"><span data-stu-id="3073f-108">Because [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses XMLA for data definition, data manipulation, and data control support, you can create mining structures and mining models by using the visual tools provided by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], and then extend the data mining objects that you have created by using Data Mining Extensions (DMX) and Analysis Services Scripting Language (ASSL) scripts.</span></span>  
  
     <span data-ttu-id="3073f-109">В скриптах XMLA можно создавать и полностью изменять объекты интеллектуального анализа данных, а также программно выполнять из приложений прогнозирующие запросы к моделям.</span><span class="sxs-lookup"><span data-stu-id="3073f-109">You can create and modify data mining objects entirely in XMLA scripts, and run prediction queries against the models programmatically from your own applications.</span></span>  
  
-   <span data-ttu-id="3073f-110">**Объекты AMO**</span><span class="sxs-lookup"><span data-stu-id="3073f-110">**Analysis Management Objects (AMO)**</span></span>  
  
     <span data-ttu-id="3073f-111">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] также обеспечивают полноценную платформу, позволяющую сторонним поставщикам интеллектуального анализа данных интегрировать в службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] объекты интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="3073f-111">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] also provides a complete framework that enables third-party data mining providers to integrate the data mining objects into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="3073f-112">Объекты AMO позволяют создавать структуры и модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="3073f-112">You can create mining structures and mining models by using AMO.</span></span> <span data-ttu-id="3073f-113">См. следующие примеры на CodePlex.</span><span class="sxs-lookup"><span data-stu-id="3073f-113">See the following samples in CodePlex:</span></span>  
  
    -   <span data-ttu-id="3073f-114">Браузер объектов AMO</span><span class="sxs-lookup"><span data-stu-id="3073f-114">AMO Browser</span></span>  
  
         <span data-ttu-id="3073f-115">Подключается к указанному вами экземпляру служб SSAS и перечисляет все объекты сервера и их свойства, включая структуру и модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="3073f-115">Connects to the SSAS instance you specify and lists all server objects and their properties, including mining structure and mining models.</span></span>  
  
    -   <span data-ttu-id="3073f-116">Простой образец объектов AMO</span><span class="sxs-lookup"><span data-stu-id="3073f-116">AMO Simple Sample</span></span>  
  
         <span data-ttu-id="3073f-117">В простом образце AS описывается программный доступ к большинству основных объектов, а также демонстрируется обзор метаданных и доступ к значениям из объектов.</span><span class="sxs-lookup"><span data-stu-id="3073f-117">The AS Simple Sample covers programmatic access to most major objects, and demonstrates metadata browsing, and access to the values in objects.</span></span>  
  
         <span data-ttu-id="3073f-118">В образце также показано создание и обработка структуры и модели интеллектуального анализа данных, а также обзор существующей модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="3073f-118">The sample also demonstrates how to create and process a data mining structure and model, as well as browse an existing data mining model.</span></span>  
  
-   <span data-ttu-id="3073f-119">**расширения интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="3073f-119">**DMX**</span></span>  
  
     <span data-ttu-id="3073f-120">С помощью расширений интеллектуального анализа данных можно инкапсулировать инструкции команд, прогнозирующие запросы и запросы метаданных и возвращать результаты в табличном формате при условии, что было создано соединение с сервером служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3073f-120">You can use DMX to encapsulate command statements, prediction queries, and metadata queries and return results in a tabular format, assuming you have created a connection to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3073f-121">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="3073f-121">In This Section</span></span>  
 [<span data-ttu-id="3073f-122">OLE DB для интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="3073f-122">OLE DB for Data Mining</span></span>](../../../2014/analysis-services/dev-guide/ole-db-for-data-mining.md)  
 <span data-ttu-id="3073f-123">Описание дополнений к спецификации для поддержки интеллектуального анализа данных и многомерных данных: новые наборы строк схемы и столбцы, язык расширений интеллектуального анализа данных для создания структур интеллектуального анализа и управления ими.</span><span class="sxs-lookup"><span data-stu-id="3073f-123">Describes additions to the specification to support data mining and multidimensional data: new schema rowsets and columns, Data Mining Extensions (DMX) language for creating and managing mining structures.</span></span>  
  
## <a name="related-reference"></a><span data-ttu-id="3073f-124">Связанные справочники</span><span class="sxs-lookup"><span data-stu-id="3073f-124">Related Reference</span></span>  
 [<span data-ttu-id="3073f-125">Разработка с использованием ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="3073f-125">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
 <span data-ttu-id="3073f-126">Знакомит с клиентом ADOMD.NET и программными объектами сервера.</span><span class="sxs-lookup"><span data-stu-id="3073f-126">Introduces ADOMD.NET client and server programming objects.</span></span>  
  
 [<span data-ttu-id="3073f-127">Разработка объектов управления аналитикой (объекты AMO)</span><span class="sxs-lookup"><span data-stu-id="3073f-127">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)  
 <span data-ttu-id="3073f-128">Представляет библиотеку программирования объектов AMO.</span><span class="sxs-lookup"><span data-stu-id="3073f-128">Introduces the AMO programming library.</span></span>  
  
 [<span data-ttu-id="3073f-129">Разработка на языке ASSL (язык ASSL)</span><span class="sxs-lookup"><span data-stu-id="3073f-129">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
 <span data-ttu-id="3073f-130">Знакомит с XML для аналитики (XMLA) и его расширениями.</span><span class="sxs-lookup"><span data-stu-id="3073f-130">Introduces XML for Analysis (XMLA) and its extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3073f-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="3073f-131">See Also</span></span>  
 <span data-ttu-id="3073f-132">[&#40;Analysis Services с руководством разработчика&#41;](../analysis-services-developer-documentation.md) </span><span class="sxs-lookup"><span data-stu-id="3073f-132">[Developer's Guide &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span></span>  
 [<span data-ttu-id="3073f-133">Справочник по расширениям интеллектуального анализа данных (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="3073f-133">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
