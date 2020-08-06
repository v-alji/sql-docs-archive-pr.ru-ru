---
title: Свойства модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- data mining [Analysis Services], properties
- columns [data mining], properties
- Data Mining Designer
- properties [data mining]
ms.assetid: c5194619-8b31-42be-a95f-585711462945
author: minewiskan
ms.author: owend
ms.openlocfilehash: fb086f4a978ca96de8e6fc99f889f718247629af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666873"
---
# <a name="mining-model-properties"></a><span data-ttu-id="625cd-102">Свойства модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="625cd-102">Mining Model Properties</span></span>
  <span data-ttu-id="625cd-103">Модели интеллектуального анализа данных имеют следующие типы свойств.</span><span class="sxs-lookup"><span data-stu-id="625cd-103">Mining models have the following kinds of properties:</span></span>  
  
-   <span data-ttu-id="625cd-104">Свойства, которые наследуются от структуры интеллектуального анализа данных и определяют тип данных и содержимого, используемые моделью.</span><span class="sxs-lookup"><span data-stu-id="625cd-104">Properties that are inherited from the mining structure that define the data type and content type of the data used by the model;</span></span>  
  
-   <span data-ttu-id="625cd-105">Свойства, связанные с алгоритмом, который используется для создания модели интеллектуального анализа данных, включая любые пользовательские параметры.</span><span class="sxs-lookup"><span data-stu-id="625cd-105">Properties that are related to the algorithm used to create the mining model, including any customer parameters;</span></span>  
  
-   <span data-ttu-id="625cd-106">Свойства, определяющие фильтр для модели, который используется для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="625cd-106">Properties that define a filter on the model used to train the model.</span></span>  
  
 <span data-ttu-id="625cd-107">Свойства модели интеллектуального анализа данных первоначально задаются при создании модели, но большинство свойств можно позже изменить, включая параметры алгоритма, фильтры и свойства использования столбцов.</span><span class="sxs-lookup"><span data-stu-id="625cd-107">The properties of a mining model are initially defined when you create the model; however, you can alter most properties later, including the algorithm parameters, filters, and column usage properties.</span></span> <span data-ttu-id="625cd-108">Изменить свойства можно на вкладке **Модели интеллектуального анализа данных** конструктора интеллектуального анализа данных, а также с помощью AMO или XMLA.</span><span class="sxs-lookup"><span data-stu-id="625cd-108">You change properties by using the **Mining Models** tab of Data Mining Designer, or by using AMO or XMLA.</span></span>  
  
 <span data-ttu-id="625cd-109">После изменения любого свойства модели необходимо повторно обработать модель с учетом изменений.</span><span class="sxs-lookup"><span data-stu-id="625cd-109">Whenever you change any property of a model, you must reprocess the model for the changes to be reflected in the model.</span></span> <span data-ttu-id="625cd-110">Повторная обработка необходима даже в том случае, если изменение затрагивает только метаданные, например при добавлении псевдонима столбца или описания.</span><span class="sxs-lookup"><span data-stu-id="625cd-110">Reprocessing is required even if the change only involves metadata, such as adding a column alias or description.</span></span>  
  
## <a name="properties-of-models"></a><span data-ttu-id="625cd-111">Свойства моделей</span><span class="sxs-lookup"><span data-stu-id="625cd-111">Properties of Models</span></span>  
 <span data-ttu-id="625cd-112">В этой таблице описываются свойства, связанные с моделями интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-112">The following table describes the properties that are specific to mining models.</span></span> <span data-ttu-id="625cd-113">Кроме того, есть свойства, связанные с отдельными столбцами модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-113">Additionally, there are properties that you can set on individual columns in the mining</span></span>  
  
|<span data-ttu-id="625cd-114">Свойство</span><span class="sxs-lookup"><span data-stu-id="625cd-114">Property</span></span>|<span data-ttu-id="625cd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="625cd-115">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="625cd-116">**Алгоритм**</span><span class="sxs-lookup"><span data-stu-id="625cd-116">**Algorithm**</span></span>|<span data-ttu-id="625cd-117">Устанавливает тип алгоритма для модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-117">Sets the algorithm type for the mining model.</span></span>|  
|<span data-ttu-id="625cd-118">**AlgorithmParameters**</span><span class="sxs-lookup"><span data-stu-id="625cd-118">**AlgorithmParameters**</span></span>|<span data-ttu-id="625cd-119">Устанавливает значения параметров алгоритма, доступных для каждого типа алгоритма.</span><span class="sxs-lookup"><span data-stu-id="625cd-119">Sets values for algorithm parameters that are available for each algorithm type.</span></span>|  
|<span data-ttu-id="625cd-120">**Filter**</span><span class="sxs-lookup"><span data-stu-id="625cd-120">**Filter**</span></span>|<span data-ttu-id="625cd-121">Задает фильтр, который применяется к данным, используемым для обучения и проверки модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-121">Sets a filter that is applied to the data that is used for training and testing the mining model.</span></span> <span data-ttu-id="625cd-122">Определение фильтра хранится вместе с моделью и может использоваться по указанию пользователя при создании запросов прогноза или проверке правильности модели.</span><span class="sxs-lookup"><span data-stu-id="625cd-122">The filter definition is stored with the model and can be used optionally when you create prediction queries, or when you test the accuracy of the model.</span></span><br /><br /> <span data-ttu-id="625cd-123">При обучении модели фильтр модели становится обязательным.</span><span class="sxs-lookup"><span data-stu-id="625cd-123">The model filter is not optional when training the model.</span></span>|  
|<span data-ttu-id="625cd-124">**имя**;</span><span class="sxs-lookup"><span data-stu-id="625cd-124">**Name**</span></span>|<span data-ttu-id="625cd-125">Устанавливает имя модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-125">Sets the name of the mining model.</span></span>|  
|<span data-ttu-id="625cd-126">**AllowDrillThrough**</span><span class="sxs-lookup"><span data-stu-id="625cd-126">**AllowDrillThrough**</span></span>|<span data-ttu-id="625cd-127">Указывает, включена ли детализация в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-127">Specifies whether drill through is enabled on the mining model.</span></span>|  
  
## <a name="properties-of-model-columns"></a><span data-ttu-id="625cd-128">Свойства столбцов модели</span><span class="sxs-lookup"><span data-stu-id="625cd-128">Properties of Model Columns</span></span>  
 <span data-ttu-id="625cd-129">Для каждого столбца в модели интеллектуального анализа данных можно установить следующие свойства, относящиеся к интеллектуальному анализу данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-129">You can set the following data mining-specific properties for each column in a mining model.</span></span> <span data-ttu-id="625cd-130">Значения этих свойств можно установить различными для каждой модели интеллектуального анализа данных в структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-130">You can set these properties to a different value for each mining model in a mining structure.</span></span>  
  
|<span data-ttu-id="625cd-131">Свойство</span><span class="sxs-lookup"><span data-stu-id="625cd-131">Property</span></span>|<span data-ttu-id="625cd-132">Описание</span><span class="sxs-lookup"><span data-stu-id="625cd-132">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="625cd-133">**Описание**</span><span class="sxs-lookup"><span data-stu-id="625cd-133">**Description**</span></span>|<span data-ttu-id="625cd-134">Описывает назначение столбца интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="625cd-134">Describes the purpose of the mining column.</span></span>|  
|<span data-ttu-id="625cd-135">**имя**;</span><span class="sxs-lookup"><span data-stu-id="625cd-135">**Name**</span></span>|<span data-ttu-id="625cd-136">Устанавливает имя столбца модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-136">Sets the name of the mining model column.</span></span> <span data-ttu-id="625cd-137">Можно ввести новое имя, чтобы предоставить псевдоним для столбца модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-137">You can type a new name, to provide an alias for the mining model column.</span></span>|  
|<span data-ttu-id="625cd-138">**ModelingFlags**</span><span class="sxs-lookup"><span data-stu-id="625cd-138">**ModelingFlags**</span></span>|<span data-ttu-id="625cd-139">Устанавливает любые флаги, относящиеся к алгоритму, для столбца.</span><span class="sxs-lookup"><span data-stu-id="625cd-139">Sets any algorithm-specific flags for the column.</span></span>|  
|<span data-ttu-id="625cd-140">**SourceColumnID**</span><span class="sxs-lookup"><span data-stu-id="625cd-140">**SourceColumnID**</span></span>|<span data-ttu-id="625cd-141">Указывает имя столбца структуры интеллектуального анализа данных, на котором основан столбец модели.</span><span class="sxs-lookup"><span data-stu-id="625cd-141">Indicates the name of the mining structure column on which the model column is based.</span></span><br /><br /> <span data-ttu-id="625cd-142">Это свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="625cd-142">This property is read-only.</span></span>|  
|<span data-ttu-id="625cd-143">**Использование**</span><span class="sxs-lookup"><span data-stu-id="625cd-143">**Usage**</span></span>|<span data-ttu-id="625cd-144">Устанавливает, как столбец будет использоваться моделью интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="625cd-144">Sets how the column will be used by the mining model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="625cd-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="625cd-145">See Also</span></span>  
 <span data-ttu-id="625cd-146">[Столбцы модели интеллектуального анализа данных](mining-model-columns.md) </span><span class="sxs-lookup"><span data-stu-id="625cd-146">[Mining Model Columns](mining-model-columns.md) </span></span>  
 <span data-ttu-id="625cd-147">[Структуры интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="625cd-147">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="625cd-148">[Задачи и инструкции по модели интеллектуального анализа данных](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="625cd-148">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="625cd-149">[Изменение свойств модели интеллектуального анализа данных](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="625cd-149">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="625cd-150">[Средства интеллектуального анализа данных](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="625cd-150">[Data Mining Tools](data-mining-tools.md) </span></span>  
 <span data-ttu-id="625cd-151">[Создание реляционной структуры интеллектуального анализа данных](create-a-relational-mining-structure.md) </span><span class="sxs-lookup"><span data-stu-id="625cd-151">[Create a Relational Mining Structure](create-a-relational-mining-structure.md) </span></span>  
 [<span data-ttu-id="625cd-152">создать псевдоним для столбца модели</span><span class="sxs-lookup"><span data-stu-id="625cd-152">Create an Alias for a Model Column</span></span>](create-an-alias-for-a-model-column.md)  
  
  
