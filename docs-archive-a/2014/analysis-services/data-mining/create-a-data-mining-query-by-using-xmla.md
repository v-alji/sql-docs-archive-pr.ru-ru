---
title: Создание запроса интеллектуального анализа данных с помощью XMLA | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 8f6b6008-006c-4792-9bd1-64c30dc3fd41
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0e85b17db0781671fab0874706f12fdac95b30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667968"
---
# <a name="create-a-data-mining-query-by-using-xmla"></a><span data-ttu-id="ce8c4-102">Создание запроса интеллектуального анализа данных с помощью XMLA</span><span class="sxs-lookup"><span data-stu-id="ce8c4-102">Create a Data Mining Query by Using XMLA</span></span>
  <span data-ttu-id="ce8c4-103">С помощью объектов AMO, инструкций DMX и языка XML/A можно создавать разнообразные запросы к объектам интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-103">You can create a variety of queries against data mining objects by using AMO, DMX, or XML/A.</span></span>  
  
 <span data-ttu-id="ce8c4-104">Язык XML необходим для связи между службами Analysis Services и всеми клиентами.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-104">XML is used for communication between the Analysis Services server and all clients.</span></span> <span data-ttu-id="ce8c4-105">Поэтому, хотя обычно гораздо проще создавать запросы к содержимому с помощью расширений интеллектуального анализа данных, запросы можно также создавать либо с помощью инструкций DISCOVER и COMMAND языка XML/A, либо с использованием клиента, поддерживающего протокол SOAP, либо создав запрос XML/A в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce8c4-105">Therefore, although it is generally much easier to create content queries by using DMX, you can write queries by using the DISCOVER and COMMAND statements in XML/A, either by using a client that supports the SOAP protocol, or by creating an XML/A query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ce8c4-106">В данном разделе объясняется, как использовать шаблоны XML/A, доступные в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , для создания запроса к содержимому модели интеллектуального анализа данных, хранящейся на текущем сервере.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-106">This topic explains how to use the XML/A templates that are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a model content query against a mining model stored on the current server.</span></span>  
  
## <a name="querying-data-mining-schema-rowsets-by-using-xmla"></a><span data-ttu-id="ce8c4-107">Создание запроса к набору строк схемы интеллектуального анализа данных с помощью XML/A</span><span class="sxs-lookup"><span data-stu-id="ce8c4-107">Querying Data Mining Schema Rowsets by Using XML/A</span></span>  
  
#### <a name="to-open-an-xmla-template"></a><span data-ttu-id="ce8c4-108">Открытие шаблона XML/A</span><span class="sxs-lookup"><span data-stu-id="ce8c4-108">To open an XML/A template</span></span>  
  
1.  <span data-ttu-id="ce8c4-109">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Вид** выберите пункт **Обозреватель шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="ce8c4-110">Щелкните значок куба, чтобы открыть шаблоны служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-110">Click the cube icon to open the list of Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="ce8c4-111">В списке категорий шаблонов раскройте пункт **XMLA**, разверните узел **Наборы строк схемы**и дважды щелкните **Выявление наборов строк схемы** , чтобы открыть шаблон в соответствующем редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-111">In the list of template categories, expand **XMLA**, expand **Schema Rowsets**, and double-click **Discover Schema Rowsets** to open the template in the appropriate code editor.</span></span>  
  
4.  <span data-ttu-id="ce8c4-112">В диалоговом окне **Подключиться к службам Analysis Services** введите сведения о соединении и нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-112">In the **Connect to Analysis Services** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="ce8c4-113">Откроется новое окно редактора запросов, отображающее содержимое шаблона **Выявление наборов строк схемы**</span><span class="sxs-lookup"><span data-stu-id="ce8c4-113">A new query editor window opens, populated with the **Discover Schema Rowsets** template.</span></span>  
  
#### <a name="to-discover-column-names-from-the-mining-model-content-schema-rowset"></a><span data-ttu-id="ce8c4-114">Получение имен столбцов для набора строк схемы MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="ce8c4-114">To discover column names from the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="ce8c4-115">В открытом шаблоне **Выявление наборов строк схемы** щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-115">With the **Discover Schema Rowsets** template open, click **Execute**.</span></span>  
  
     <span data-ttu-id="ce8c4-116">На панели **Результаты** будет выведен список наборов строк схемы, содержащий имена наборов строк и столбцы наборов строк для всех наборов строк, доступных в данном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-116">A list of schema rowsets is returned in the **Results** pane that contains the rowset names and rowset columns for all rowsets available on the current instance.</span></span>  
  
2.  <span data-ttu-id="ce8c4-117">На панели **запрос** поместите курсор после **\<Restriction List>** и нажмите клавишу ВВОД, чтобы добавить новую строку.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-117">In the **Query** pane, place the cursor after **\<Restriction List>** and press ENTER to add a new line.</span></span>  
  
3.  <span data-ttu-id="ce8c4-118">Поместите курсор на пустую строку и введите \*\* \<SchemaName> DMSCHEMA_MINING_MODEL_CONTENT \</SchemaName> \*\*</span><span class="sxs-lookup"><span data-stu-id="ce8c4-118">Place the cursor on the blank line and type **\<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT\</SchemaName>**</span></span>  
  
     <span data-ttu-id="ce8c4-119">Весь раздел ограничений теперь должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-119">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT</SchemaName>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
4.  <span data-ttu-id="ce8c4-120">Нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-120">Click **Execute**.</span></span>  
  
     <span data-ttu-id="ce8c4-121">На панели **Результаты** отображается список имен столбцов для указанного набора строк схемы.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-121">The **Results** pane shows a list of column names for the specified schema rowset.</span></span>  
  
#### <a name="to-create-a-content-query-using-the-mining-model-content-schema-rowset"></a><span data-ttu-id="ce8c4-122">Создание запроса к содержимому с использованием набора строк схемы MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="ce8c4-122">To create a content query using the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="ce8c4-123">В шаблоне **Выявление наборов строк схемы** измените тип запроса, изменив текст внутри тегов типа запроса.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-123">In the **Discover Schema Rowsets** template, change the request type by replacing the text inside the request type tags.</span></span>  
  
     <span data-ttu-id="ce8c4-124">Вместо</span><span class="sxs-lookup"><span data-stu-id="ce8c4-124">Replace this line:</span></span>  
  
     `<RequestType>DISCOVER_SCHEMA_ROWSETS</RequestType>`  
  
     <span data-ttu-id="ce8c4-125">следующей строкой:</span><span class="sxs-lookup"><span data-stu-id="ce8c4-125">with the following line:</span></span>  
  
     <span data-ttu-id="ce8c4-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span><span class="sxs-lookup"><span data-stu-id="ce8c4-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span></span>  
  
2.  <span data-ttu-id="ce8c4-127">Измените список ограничений, чтобы задать имя модели интеллектуального анализа данных, добавив новое условие к списку ограничений.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-127">Change the restriction list to specify a mining model by name, by adding a new condition to the restriction lists.</span></span>  
  
3.  <span data-ttu-id="ce8c4-128">В шаблоне поместите курсор после элемента `<Restriction List>` и нажмите клавишу ВВОД, чтобы добавить новую строку.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-128">In the template, place the cursor after `<Restriction List>` and press ENTER to add a new line.</span></span>  
  
4.  <span data-ttu-id="ce8c4-129">Поместите курсор в пустую строку и введите **<MODEL_NAME>Имя моей модели</MODEL_NAME>**</span><span class="sxs-lookup"><span data-stu-id="ce8c4-129">Place the cursor on the blank line and type **<MODEL_NAME>My model name</MODEL_NAME>**</span></span>  
  
     <span data-ttu-id="ce8c4-130">Весь раздел ограничений теперь должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-130">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<MODEL_NAME>My model name</MODEL_NAME>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
5.  <span data-ttu-id="ce8c4-131">Нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="ce8c4-132">На панели результатов выводится определение схемы и значения для заданной модели.</span><span class="sxs-lookup"><span data-stu-id="ce8c4-132">The Results pane displays the schema definition, together with the values for the specified model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce8c4-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce8c4-133">See Also</span></span>  
 <span data-ttu-id="ce8c4-134">[&#40;содержимого моделей интеллектуального анализа данных Analysis Services — интеллектуальный анализ&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ce8c4-134">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="ce8c4-135">Data Mining Schema Rowsets</span><span class="sxs-lookup"><span data-stu-id="ce8c4-135">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
