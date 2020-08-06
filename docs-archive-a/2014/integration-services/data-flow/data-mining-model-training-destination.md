---
title: Назначение "Обучение модели интеллектуального анализа данных" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingmodeltrainingdest.f1
helpviewer_keywords:
- destinations [Integration Services], Data Mining Model Training
- Data Mining Model Training destination
- mining models [Analysis Services], training
- training mining models
ms.assetid: 6bc8cbe2-46af-4f7b-93d6-86779313c9d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e101a7e374f16b12b3a5aa30a49dbecd2632f06f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665049"
---
# <a name="data-mining-model-training-destination"></a><span data-ttu-id="e184f-102">целевой объект «Обучение модели интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="e184f-102">Data Mining Model Training Destination</span></span>
  <span data-ttu-id="e184f-103">Целевой объект «Обучение модели интеллектуального анализа данных» обучает модели анализа данных, пропуская данные, которые получает целевой объект, через алгоритмы модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e184f-103">The Data Mining Model Training destination trains data mining models by passing the data that the destination receives through the data mining model algorithms.</span></span> <span data-ttu-id="e184f-104">Несколько моделей интеллектуального анализа данных могут быть обучены одним целевым объектом, если модели построены на одной и той же структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e184f-104">Multiple data mining models can be trained by one destination if the models are built on the same data mining structure.</span></span> <span data-ttu-id="e184f-105">Дополнительные сведения см. в разделах [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) и [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span><span class="sxs-lookup"><span data-stu-id="e184f-105">For more information, see [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) and [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span></span>  
  
## <a name="configuration-of-the-data-mining-model-training-destination"></a><span data-ttu-id="e184f-106">Настройка назначения «Обучение модели интеллектуального анализа данных».</span><span class="sxs-lookup"><span data-stu-id="e184f-106">Configuration of the Data Mining Model Training Destination</span></span>  
 <span data-ttu-id="e184f-107">Если столбец уровня вариантов в целевой структуре и модели построены на структуре, содержимое которой типа KEY TIME или KEY SEQUENCE, входные данные должны быть отсортированы по этой колонке.</span><span class="sxs-lookup"><span data-stu-id="e184f-107">If a case level column of the target structure and the models built on the structure has the content type KEY TIME or KEY SEQUENCE, the input data must be sorted on that column.</span></span> <span data-ttu-id="e184f-108">Например, модели, созданные с использованием алгоритма временных рядов (Майкрософт), используют тип содержимого KEY TIME.</span><span class="sxs-lookup"><span data-stu-id="e184f-108">For example, models built using the Microsoft Time Series algorithm use the content type KEY TIME.</span></span> <span data-ttu-id="e184f-109">Если входные данные не отсортированы, то обработка модели может завершиться неудачно.</span><span class="sxs-lookup"><span data-stu-id="e184f-109">If input data is not sorted, the processing of the model may fail.</span></span> <span data-ttu-id="e184f-110">Если данные требуется отсортировать, можно в потоке данных предварительно использовать преобразование «Сортировка» для их сортировки.</span><span class="sxs-lookup"><span data-stu-id="e184f-110">If the data requires sorting, you can use a Sort transformation earlier in the data flow to sort the data.</span></span> <span data-ttu-id="e184f-111">Это требование не относится к столбцам с типом содержимого KEY.</span><span class="sxs-lookup"><span data-stu-id="e184f-111">This requirement does not apply to columns with the KEY content type.</span></span> <span data-ttu-id="e184f-112">Дополнительные сведения см. в разделе [Типы содержимого (интеллектуальный анализ данных)](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) и [Преобразование "Сортировка"](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="e184f-112">For more information, see [Content Types &#40;Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) and [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e184f-113">Входные данные целевого объекта «Обучение модели интеллектуального анализа данных» должны быть отсортированы.</span><span class="sxs-lookup"><span data-stu-id="e184f-113">The input to the Data Mining Model training destination must be sorted.</span></span> <span data-ttu-id="e184f-114">Чтобы отсортировать данные, следует включить целевой объект «Сортировка» в поток данных к назначению «Обучение модели интеллектуального анализа данных».</span><span class="sxs-lookup"><span data-stu-id="e184f-114">To sort the data, you can include a Sort destination upstream from the Data Mining Model Training destination in the data flow.</span></span> <span data-ttu-id="e184f-115">Дополнительные сведения см. в разделе [Sort Transformation](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="e184f-115">For more information, see [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
 <span data-ttu-id="e184f-116">Этот целевой объект имеет один вход и ни одного выхода.</span><span class="sxs-lookup"><span data-stu-id="e184f-116">This destination has one input and no output.</span></span>  
  
 <span data-ttu-id="e184f-117">Назначение "Обучение модели интеллектуального анализа данных" использует диспетчер соединений служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для подключения к проекту служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или экземпляру служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], содержащему структуру интеллектуального анализа данных и модели интеллектуального анализа, которые обучаются с помощью назначения.</span><span class="sxs-lookup"><span data-stu-id="e184f-117">The Data Mining Model Training destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models that the destination trains.</span></span> <span data-ttu-id="e184f-118">Дополнительные сведения см. в статье [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e184f-118">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e184f-119">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="e184f-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e184f-120">Дополнительные сведения о свойствах, которые могут быть заданы в диалоговом окне **Редактор сценариев обучения моделей интеллектуального анализа данных** , см. в одном из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="e184f-120">For more information about the properties that you can set in the **Data Mining Model Training Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e184f-121">Редактор обучения модели интеллектуального анализа данных (вкладка "Соединение")</span><span class="sxs-lookup"><span data-stu-id="e184f-121">Data Mining Model Training Editor &#40;Connection Tab&#41;</span></span>](../data-mining-model-training-editor-connection-tab.md)  
  
-   [<span data-ttu-id="e184f-122">Редактор обучения модели интеллектуального анализа данных (вкладка "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="e184f-122">Data Mining Model Training Editor &#40;Columns Tab&#41;</span></span>](../data-mining-model-training-editor-columns-tab.md)  
  
 <span data-ttu-id="e184f-123">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="e184f-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="e184f-124">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="e184f-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e184f-125">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="e184f-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="e184f-126">Пользовательские свойства назначения «Обучение модели интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="e184f-126">Data Mining Model Training Destination Custom Properties</span></span>](data-mining-model-training-destination-custom-properties.md)  
  
 <span data-ttu-id="e184f-127">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="e184f-127">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
