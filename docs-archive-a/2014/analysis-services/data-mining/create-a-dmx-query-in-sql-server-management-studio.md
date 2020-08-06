---
title: Создание DMX-запроса в SQL Server Management Studio | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- templates [Analysis Services], queries
- SQL Server Management Studio [Analysis Services], DMX queries
- predictions [Analysis Services], DMX prediction queries
- predictions [DMX]
- prediction queries [DMX]
- queries [DMX], prediction queries
- mining models [Analysis Services], DMX
ms.assetid: 568ce40a-1f53-47eb-8c79-14347cdfde83
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20fc7a618f4977058203d8f35d235b543609dd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665676"
---
# <a name="create-a-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="e1b6e-102">Создание DMX-запроса в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1b6e-102">Create a DMX Query in SQL Server Management Studio</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e1b6e-103">предоставляет набор возможностей, упрощающих создание прогнозирующих запросов, запросов содержимого и запросов определения данных к моделям интеллектуального анализа данных и структурам интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-103">provides a set of features to help you create prediction queries, content queries, and data definition queries against mining models and mining structures.</span></span>  
  
-   <span data-ttu-id="e1b6e-104">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] и среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]доступен графический построитель прогнозирующих запросов, упрощающий написание прогнозирующих запросов и сопоставление наборов данных с моделью.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-104">The graphical Prediction Query Builder is available in both [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], to simplify the process of writing prediction queries and mapping data sets to a model.</span></span>  
  
-   <span data-ttu-id="e1b6e-105">Шаблоны запросов, находящиеся в обозревателе шаблонов, позволяют сразу приступить к созданию многих типов запросов расширений интеллектуального анализа данных, в том числе многих типов прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-105">The query templates provided in the Template Explorer jump-start the creation of many kinds of DMX queries, including many types of prediction queries.</span></span> <span data-ttu-id="e1b6e-106">Предоставляются шаблоны для запросов содержимого, запросов, использующих вложенные наборы данных, запросов, возвращающих варианты из структуры интеллектуального анализа данных, а также запросов определения данных.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-106">Templates are provided for content queries, queries used nested data sets, queries that return cases from the mining structure, and even data definition queries.</span></span>  
  
-   <span data-ttu-id="e1b6e-107">В обозревателе метаданных на панелях запросов многомерных выражений и запросов расширения интеллектуального анализа данных приводится список доступных моделей и структур, которые можно перетащить в построитель запросов, а также список функций расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-107">The Metadata Explorer in the MDX and DMX query panes provides a list of available models and structures that you can drag and drop into the query builder, as well as a list of DMX functions.</span></span> <span data-ttu-id="e1b6e-108">Это упрощает правильную передачу имен объектов без ввода с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-108">This feature makes it easy to get object names right, without typing.</span></span>  
  
 <span data-ttu-id="e1b6e-109">В этом разделе описывается построение DMX-запроса в обозревателе метаданных и в редакторе DMX-запросов.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-109">This topic describes how to build a DMX query by using the Metadata Explorer and the DMX query editor.</span></span>  
  
##  <a name="dmx-query-templates"></a><a name="BKMK_Templates"></a><span data-ttu-id="e1b6e-110">Шаблоны DMX-запросов</span><span class="sxs-lookup"><span data-stu-id="e1b6e-110">DMX Query Templates</span></span>  
 <span data-ttu-id="e1b6e-111">Шаблоны для создания основных запросов расширений интеллектуального анализа находятся в обозревателе шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-111">Templates for creating basic DMX queries are available in Template Explorer.</span></span> <span data-ttu-id="e1b6e-112">В папке **DMX** содержатся шаблоны интеллектуального анализа данных, которые подразделяются на следующие категории.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-112">The **DMX** folder contains data mining templates, which are divided into these categories:</span></span>  
  
-   <span data-ttu-id="e1b6e-113">**Содержимое модели**</span><span class="sxs-lookup"><span data-stu-id="e1b6e-113">**Model Content**</span></span>  
  
-   <span data-ttu-id="e1b6e-114">**Управление моделями**</span><span class="sxs-lookup"><span data-stu-id="e1b6e-114">**Model Management**</span></span>  
  
-   <span data-ttu-id="e1b6e-115">**Прогнозирующие запросы**</span><span class="sxs-lookup"><span data-stu-id="e1b6e-115">**Prediction Queries**</span></span>  
  
-   <span data-ttu-id="e1b6e-116">**Содержимое структуры**</span><span class="sxs-lookup"><span data-stu-id="e1b6e-116">**Structure Content**</span></span>  
  
 <span data-ttu-id="e1b6e-117">Также можно создавать пользовательские шаблоны для часто используемых запросов или команд.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-117">You can also create custom templates, for queries or commands that you run frequently.</span></span>  
  
## <a name="xmla-query-templates"></a><span data-ttu-id="e1b6e-118">Шаблоны XMLA-запросов</span><span class="sxs-lookup"><span data-stu-id="e1b6e-118">XMLA Query Templates</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="e1b6e-119">также предоставляют шаблоны для XMLA-запросов.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-119">also provides templates for XMLA queries.</span></span>  
  
 <span data-ttu-id="e1b6e-120">Типы запросов, выполняемые с помощью XML для аналитики и расширений интеллектуального анализа данных, в некоторой степени перекрываются.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-120">There is some overlap between the types of queries that you can perform by using XMLA and DMX.</span></span> <span data-ttu-id="e1b6e-121">Например, запросы к содержимому модели можно создавать с помощью расширений интеллектуального анализа данных или с помощью набора строк схемы интеллектуального анализа данных, однако иногда наборы строк схемы содержат данные, которые недоступны DMX-запросам содержимого.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-121">For example, you can create some model content queries by using either DMX or the data mining schema rowsets, but the schema rowsets sometimes contain information that is not exposed in DMX content queries.</span></span>  
  
 <span data-ttu-id="e1b6e-122">Кроме того, обработка операций в расширениях интеллектуального анализа данных и в XML для аналитики имеет ряд существенных различий.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-122">There are also some key differences in the way that operations are handled in DMX and in XMLA.</span></span> <span data-ttu-id="e1b6e-123">Так, в частности, XML для аналитики можно использовать в административных операциях, например для резервного копирования всей базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], однако если нужно создать резервную копию одной модели интеллектуального анализа данных, то в расширениях интеллектуального анализа данных поддерживается простая команда [EXPORT (DMX)](/sql/dmx/export-dmx), которая больше подходит для такой задачи.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-123">For example, you can use XMLA to perform administrative operations such as backup of an entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, but if you want to back up a single mining model, DMX provides a simple command, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx), that is better suited to that purpose.</span></span>  
  
##  <a name="build-and-run-a-dmx-query"></a><a name="BKMK_Building_Queries"></a><span data-ttu-id="e1b6e-124">Сборка и запуск DMX-запроса</span><span class="sxs-lookup"><span data-stu-id="e1b6e-124">Build and Run a DMX Query</span></span>  
  
#### <a name="open-a-new-dmx-query-window"></a><span data-ttu-id="e1b6e-125">Откройте окно создания DMX-запроса</span><span class="sxs-lookup"><span data-stu-id="e1b6e-125">Open a new DMX Query window</span></span>  
  
1.  <span data-ttu-id="e1b6e-126">Щелкните значок **Создать запрос** в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]и выберите пункт **Создать запрос расширений интеллектуального анализа данных сервера анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-126">Click **New Query** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then select **New Analysis Server DMX Query**.</span></span>  
  
2.  <span data-ttu-id="e1b6e-127">В открывшемся диалоговом окне **Подключиться к серверу** выберите экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , содержащий требуемые модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-127">When the **Connect to Server** dialog box appears, select the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining models you want to work with.</span></span>  
  
#### <a name="open-template-explorer"></a><span data-ttu-id="e1b6e-128">Откройте обозреватель шаблонов</span><span class="sxs-lookup"><span data-stu-id="e1b6e-128">Open Template Explorer</span></span>  
  
1.  <span data-ttu-id="e1b6e-129">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]выберите в меню **Вид** пункт **Обозреватель шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-129">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, select **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="e1b6e-130">Щелкните значок **Сервер анализа данных** , чтобы просмотреть представление в виде дерева шаблонов, применимых к службам [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1b6e-130">Click **Analysis Server** to see a tree view of the templates that apply to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
#### <a name="apply-a-template-to-build-a-query"></a><span data-ttu-id="e1b6e-131">Примените шаблон, чтобы построить запрос</span><span class="sxs-lookup"><span data-stu-id="e1b6e-131">Apply a template to build a query</span></span>  
  
-   <span data-ttu-id="e1b6e-132">Щелкните правой кнопкой мыши нужный тип запроса и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-132">Right-click the appropriate query type and select **Open**.</span></span>  
  
-   <span data-ttu-id="e1b6e-133">Также можно перетащить шаблон в редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-133">Or, drag the template into the query editor.</span></span>  
  
-   <span data-ttu-id="e1b6e-134">Можно ввести параметры для запроса, выбрав команду **Указать значения параметров шаблона**в меню **Запрос** .</span><span class="sxs-lookup"><span data-stu-id="e1b6e-134">You can also fill in the parameters for the query by using the option, **Specify Values for Parameters**, from the **Query** menu.</span></span>  
  
 <span data-ttu-id="e1b6e-135">Примеры создания отдельных типов запросов из шаблонов см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="e1b6e-135">For examples of how to create specific types of queries from templates, see the following topics:</span></span>  
  
 [<span data-ttu-id="e1b6e-136">создать одноэлементный прогнозирующий запрос из шаблона</span><span class="sxs-lookup"><span data-stu-id="e1b6e-136">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
  
 [<span data-ttu-id="e1b6e-137">Создание запроса содержимого к модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="e1b6e-137">Create a Content Query on a Mining Model</span></span>](create-a-content-query-on-a-mining-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="e1b6e-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1b6e-138">See Also</span></span>  
 <span data-ttu-id="e1b6e-139">[Интерфейсы запросов интеллектуального анализа данных](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e1b6e-139">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="e1b6e-140">Справочник по расширениям интеллектуального анализа данных (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="e1b6e-140">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
