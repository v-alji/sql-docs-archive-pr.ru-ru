---
title: Создание запроса содержимого для модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: a0ce837a-89ed-46cf-9ce1-801ccb75fa04
author: minewiskan
ms.author: owend
ms.openlocfilehash: 26af1100d6ba80185c1cc4de18548df0e387824c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727481"
---
# <a name="create-a-content-query-on-a-mining-model"></a><span data-ttu-id="266e6-102">Создание запроса содержимого к модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="266e6-102">Create a Content Query on a Mining Model</span></span>
  <span data-ttu-id="266e6-103">Запрашивать содержимое модели интеллектуального анализа данных можно программным способом с помощью объектов AMO или XML/A, но легче создать запрос, используя расширения интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="266e6-103">You can query the mining model content programmatically by using AMO or XML/A, but it is easier to create queries by using DMX.</span></span> <span data-ttu-id="266e6-104">Также можно создавать запросы к наборам строк схемы интеллектуального анализа данных, устанавливая соединение с экземпляром [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и создавая запрос с помощью динамических административных представлений, предоставляемых службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="266e6-104">You can also create queries against the data mining schema rowsets by establishing a connection to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and creating a query using the DMVs provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="266e6-105">В следующих процедурах показаны создание запросов к модели интеллектуального анализа данных с помощью расширений интеллектуального анализа данных и способ запроса к наборам строк схемы интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="266e6-105">The following procedures demonstrate how to create queries against a mining model by using DMX, and how to query the data mining schema rowsets.</span></span>  
  
 <span data-ttu-id="266e6-106">Пример создания подобного запроса с использованием XML/A см. в разделе [Создание запроса интеллектуального анализа данных с помощью XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="266e6-106">For an example of how to create a similar query by using XML/A, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="querying-data-mining-model-content-by-using-dmx"></a><span data-ttu-id="266e6-107">Запрос содержимого модели интеллектуального анализа с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="266e6-107">Querying Data Mining Model Content by Using DMX</span></span>  
  
#### <a name="to-create-a-dmx-model-content-query"></a><span data-ttu-id="266e6-108">Создание DMX-запроса содержимого модели</span><span class="sxs-lookup"><span data-stu-id="266e6-108">To create a DMX model content query</span></span>  
  
1.  <span data-ttu-id="266e6-109">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Вид** выберите пункт **Обозреватель шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="266e6-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="266e6-110">На панели **Обозреватель шаблонов** щелкните значок куба, чтобы изменить список и отобразить шаблоны служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="266e6-110">In the **Template Explorer** pane, click the cube icon to change the list and display Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="266e6-111">В списке категорий шаблонов разверните **DMX**, затем **Содержимое модели**и дважды щелкните **Запрос содержимого**.</span><span class="sxs-lookup"><span data-stu-id="266e6-111">In the list of template categories, expand **DMX**, expand **Model Content**, and double-click **Content Query**.</span></span>  
  
4.  <span data-ttu-id="266e6-112">В диалоговом окне **Подключение к службам Analysis Services** выберите экземпляр, содержащий нужную модель интеллектуального анализа данных, и нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="266e6-112">In the **Connect to Analysis Services** dialog box, select the instance that contains the mining model you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="266e6-113">Шаблон **Запрос содержимого** откроется в соответствующем редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="266e6-113">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="266e6-114">На панели метаданных приводится список моделей, доступных в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="266e6-114">The metadata pane lists the models that are available in the current database.</span></span> <span data-ttu-id="266e6-115">Чтобы изменить базу данных, выберите другую базу данных в списке **Доступные базы данных** .</span><span class="sxs-lookup"><span data-stu-id="266e6-115">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
5.  <span data-ttu-id="266e6-116">Введите имя модели интеллектуального анализа данных в строке `FROM` [ *\<mining model, name, MyModel>* ] `.CONTENT` .</span><span class="sxs-lookup"><span data-stu-id="266e6-116">Enter the name of a mining model in the line, `FROM` [*\<mining model, name, MyModel>*]`.CONTENT`.</span></span> <span data-ttu-id="266e6-117">Если имя модели интеллектуального анализа данных содержит пробелы, его необходимо заключить в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="266e6-117">If the mining model name contains spaces, you must enclose the name in brackets.</span></span>  
  
     <span data-ttu-id="266e6-118">Можно не вводить имя, а выбрать модель интеллектуального анализа данных в **обозревателе объектов** и перетащить его в шаблон.</span><span class="sxs-lookup"><span data-stu-id="266e6-118">If you don't want to type the name, you can select a mining model in **Object Explorer** and drag it into the template.</span></span>  
  
6.  <span data-ttu-id="266e6-119">В строке `SELECT` *\<select list, expr list, \*>* Введите имена столбцов в наборе строк схемы содержимого модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="266e6-119">In the line, `SELECT`*\<select list, expr list, \*>*, type the names of columns in the mining model content schema rowset.</span></span>  
  
     <span data-ttu-id="266e6-120">Чтобы просмотреть список столбцов, которые можно возвратить в запросах содержимого модели интеллектуального анализа данных, см. раздел [Содержимое модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="266e6-120">To view a list of columns that you can return in mining model content queries, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
7.  <span data-ttu-id="266e6-121">При желании можно ввести условие в предложении шаблона WHERE, чтобы ограничить число возвращаемых строк.</span><span class="sxs-lookup"><span data-stu-id="266e6-121">Optionally, type a condition in the WHERE clause of the template to restrict the rows returned to specific nodes or values.</span></span>  
  
8.  <span data-ttu-id="266e6-122">Нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="266e6-122">Click **Execute**.</span></span>  
  
## <a name="querying-the-data-mining-schema-rowsets"></a><span data-ttu-id="266e6-123">Запрос набора строк схемы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="266e6-123">Querying the Data Mining Schema Rowsets</span></span>  
  
#### <a name="to-create-a-query-against-the-data-mining-schema-rowset"></a><span data-ttu-id="266e6-124">Создание запроса к набору строк схемы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="266e6-124">To create a query against the data mining schema rowset</span></span>  
  
1.  <span data-ttu-id="266e6-125">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]на панели инструментов **Создать запрос** щелкните **DMX-запрос служб Analysis Services**или **Запрос MDX служб Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="266e6-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **New Query** toolbar, click **Analysis Services DMX Query**, or **Analysis Services MDX query**.</span></span>  
  
2.  <span data-ttu-id="266e6-126">В диалоговом окне **Подключение к службам Analysis Services** выберите экземпляр, содержащий нужные объекты, и нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="266e6-126">In the **Connect to Analysis Services** dialog box, select the instance that contains the objects you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="266e6-127">Шаблон **Запрос содержимого** откроется в соответствующем редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="266e6-127">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="266e6-128">На панели метаданных приводится список объектов, доступных в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="266e6-128">The metadata pane lists the objects that are available in the current database.</span></span> <span data-ttu-id="266e6-129">Чтобы изменить базу данных, выберите другую базу данных в списке **Доступные базы данных** .</span><span class="sxs-lookup"><span data-stu-id="266e6-129">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
3.  <span data-ttu-id="266e6-130">В редакторе запросов введите следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="266e6-130">In the query editor, type the following:</span></span>  
  
     `SELECT *`  
  
     `FROM $system.DMSCHEMA_MINING_MODEL_CONTENT`  
  
     `WHERE MODEL_NAME = '<model name>'`  
  
4.  <span data-ttu-id="266e6-131">Нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="266e6-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="266e6-132">На панели «Результат» отобразится содержимое модели.</span><span class="sxs-lookup"><span data-stu-id="266e6-132">The Results pane displays the contents of the model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="266e6-133">Чтобы просмотреть список всех наборов строк схемы, которые можно запросить в текущем экземпляре, используется следующий запрос: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span><span class="sxs-lookup"><span data-stu-id="266e6-133">To view a list of all the schema rowsets that you can query on the current instance, use this query: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span></span> <span data-ttu-id="266e6-134">Список наборов строк схемы, относящихся к интеллектуальному анализу данных, см. в разделе [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="266e6-134">Or, for a list of schema rowsets specific to data mining, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="266e6-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="266e6-135">See Also</span></span>  
 <span data-ttu-id="266e6-136">[&#40;содержимого моделей интеллектуального анализа данных Analysis Services — интеллектуальный анализ&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="266e6-136">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="266e6-137">Data Mining Schema Rowsets</span><span class="sxs-lookup"><span data-stu-id="266e6-137">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
