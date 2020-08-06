---
title: Запрос параметров, используемых для создания модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: ce7719e0-6127-4d9c-a753-0e0a3db065e1
author: minewiskan
ms.author: owend
ms.openlocfilehash: a3802a0d70579f613accbe6abd310da909751b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733326"
---
# <a name="query-the-parameters-used-to-create-a-mining-model"></a><span data-ttu-id="bd5ba-102">запросить параметры, используемые для создания модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="bd5ba-102">Query the Parameters Used to Create a Mining Model</span></span>
  <span data-ttu-id="bd5ba-103">На составление модели интеллектуального анализа данных влияют не только обучающие варианты, но и параметры, заданные при создании модели.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-103">The composition of a mining model is affected not only by the training cases, but by the parameters that were set when the model was created.</span></span> <span data-ttu-id="bd5ba-104">Поэтому может быть полезно извлечь значения параметров существующей модели, чтобы лучше разобраться в ее поведении.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-104">Therefore, you might find it useful to retrieve the parameter settings of an existing model to better understand the behavior of the model.</span></span> <span data-ttu-id="bd5ba-105">Получение параметров также может быть полезным при создании документации по конкретной версии модели.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-105">Retrieving parameters is also useful when documenting a particular version of that model.</span></span>  
  
 <span data-ttu-id="bd5ba-106">Для получения параметров, которые использовались при создании модели, нужно создать запрос к одному из наборов строк схемы модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-106">To find the parameters that were used when the model was created, you create a query against one of the mining model schema rowsets.</span></span> <span data-ttu-id="bd5ba-107">В службах [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)]эти наборы строк схемы доступны как набор системных представлений, к которым легко осуществлять запросы с помощью синтаксиса языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-107">In [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], these schema rowsets are exposed as a set of system views that you can query easily by using Transact-SQL syntax.</span></span> <span data-ttu-id="bd5ba-108">В данной процедуре описывается создание запроса, возвращающего параметры, которые использовались для создания указанной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-108">This procedure describes how to create a query that returns the parameters that were used to create the specified mining model.</span></span>  
  
### <a name="to-open-a-query-window-for-a-schema-rowset-query"></a><span data-ttu-id="bd5ba-109">Открытие окна «Запрос» для запроса к набору строк схемы</span><span class="sxs-lookup"><span data-stu-id="bd5ba-109">To open a Query window for a schema rowset query</span></span>  
  
1.  <span data-ttu-id="bd5ba-110">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , содержащий модель, к которой создается запрос.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the model you want to query.</span></span>  
  
2.  <span data-ttu-id="bd5ba-111">Щелкните правой кнопкой мыши имя экземпляра, выберите **Создать запрос**, а затем **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-111">Right-click the instance name, select **New Query**, and then select **DMX**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bd5ba-112"> Можно также создать запрос к модели интеллектуального анализа данных с помощью шаблона **Многомерное выражение**</span><span class="sxs-lookup"><span data-stu-id="bd5ba-112">You can also create a query against a data mining model by using the **MDX** template.</span></span>  
  
3.  <span data-ttu-id="bd5ba-113">Если в экземпляре содержится несколько баз данных, выберите в списке **Доступные базы данных** на панели инструментов базу данных, содержащую модель, к которой нужно создать запрос.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-113">If the instance contains multiple databases, select the database that contains the model you want to query from the **Available Databases** list in the toolbar.</span></span>  
  
### <a name="to-return-model-parameters-for-an-existing-mining-model"></a><span data-ttu-id="bd5ba-114">Возврат параметров существующей модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="bd5ba-114">To return model parameters for an existing mining model</span></span>  
  
1.  <span data-ttu-id="bd5ba-115">На панели DMX-запросов введите или вставьте следующий текст.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-115">In the DMX query pane, type or paste the following text:</span></span>  
  
    ```  
    SELECT MINING_PARAMETERS  
    FROM $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = ''  
    ```  
  
2.  <span data-ttu-id="bd5ba-116">Выберите в обозревателе объектов нужную модель интеллектуального анализа данных и перетащите ее на панель DMX-запросов, чтобы она оказалась заключенной в одиночные кавычки.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-116">In Object Explorer, select the mining model you want, and then drag it into the DMX Query pane, between the single quotation marks.</span></span>  
  
3.  <span data-ttu-id="bd5ba-117">Нажмите клавишу F5 или кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-117">Press F5, or click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd5ba-118">Пример</span><span class="sxs-lookup"><span data-stu-id="bd5ba-118">Example</span></span>  
 <span data-ttu-id="bd5ba-119">Следующий программный код возвращает список параметров, которые использовались в учебнике [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md)при создании модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-119">The following code returns a list of the parameters that were used to create the mining model that you build in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="bd5ba-120">В число этих параметров входят все значения по умолчанию, используемые службами интеллектуального анализа данных и предоставляемые поставщиками на сервере.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-120">These parameters include the explicit values for any defaults used by the mining services available from providers on the server.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
 <span data-ttu-id="bd5ba-121">Данный пример кода возвращает для модели кластеризации следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="bd5ba-121">The code example returns the following parameters for the clustering model:</span></span>  
  
 <span data-ttu-id="bd5ba-122">Результаты eExample:</span><span class="sxs-lookup"><span data-stu-id="bd5ba-122">eExample Results:</span></span>  
  
 <span data-ttu-id="bd5ba-123">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd5ba-123">MINING_PARAMETERS</span></span>  
  
 <span data-ttu-id="bd5ba-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span><span class="sxs-lookup"><span data-stu-id="bd5ba-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5ba-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd5ba-125">See Also</span></span>  
 <span data-ttu-id="bd5ba-126">[Задачи и инструкции по запросам интеллектуального анализа данных](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="bd5ba-126">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="bd5ba-127">Запросы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="bd5ba-127">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
