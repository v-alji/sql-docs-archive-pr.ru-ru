---
title: Редактор преобразования "Статистическая обработка" (вкладка "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.aggregationtransformation.advanced.f1
helpviewer_keywords:
- Aggregate Transformation Editor
ms.assetid: 186a9736-2554-40a0-9cb2-877a8db5fde8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb3742a83f363f74004a5aac0eefc589ee2a5be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657244"
---
# <a name="aggregate-transformation-editor-advanced-tab"></a><span data-ttu-id="a2c9a-102">Редактор преобразований «Статистическая обработка» (вкладка «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="a2c9a-102">Aggregate Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="a2c9a-103">Вкладка **Дополнительно** диалогового окна **Редактор преобразования «Статистическая обработка»** позволяет задавать свойства компонентов, указывать агрегатные функции и задавать свойства входных и выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-103">Use the **Advanced** tab of the **Aggregate Transformation Editor** dialog box to set component properties, specify aggregations, and set properties of input and output columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2c9a-104">Если параметры числа ключей, масштаба ключей, числа различающихся ключей и масштаба различающихся ключей определены на вкладке **Дополнительно** , они действуют на уровне компонентов; если они определены в расширенном режиме просмотра вкладки **Агрегаты** — на уровне вывода; а если они определены в списке столбцов внизу на вкладке **Агрегаты** — на уровне столбцов.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-104">The options for key count, key scale, distinct key count, and distinct key scale apply at the component level when specified on the **Advanced** tab, at the output level when specified in the advanced display of the **Aggregations** tab, and at the column level when specified in the column list at the bottom of the **Aggregations** tab.</span></span>  
>   
>  <span data-ttu-id="a2c9a-105">В преобразовании «Статистическая обработка» свойства **Ключи** и **Порядок числа ключей** ссылаются на ожидаемое число групп, являющихся результатом операции **Группировать по** .</span><span class="sxs-lookup"><span data-stu-id="a2c9a-105">In the Aggregate transformation, **Keys** and **Keys scale** refer to the number of groups that are expected to result from a **Group by** operation.</span></span> <span data-ttu-id="a2c9a-106">Свойства**Количество различных ключей** и **Порядок числа различных ключей** ссылаются на ожидаемое число различающихся значений, являющихся результатом операции **Подсчет различных объектов** .</span><span class="sxs-lookup"><span data-stu-id="a2c9a-106">**Count distinct keys** and **Count distinct scale** refer to the number of distinct values that are expected to result from a **Distinct count** operation.</span></span>  
  
 <span data-ttu-id="a2c9a-107">Дополнительные сведения о преобразовании «Статистическая обработка» см. в разделе [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a2c9a-107">To learn more about the Aggregate transformation, see [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a2c9a-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="a2c9a-108">Options</span></span>  
 <span data-ttu-id="a2c9a-109">**Порядок числа ключей**</span><span class="sxs-lookup"><span data-stu-id="a2c9a-109">**Keys scale**</span></span>  
 <span data-ttu-id="a2c9a-110">Дополнительно можно указать примерное число ключей, ожидаемых статистической функцией.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-110">Optionally specify the approximate number of keys that the aggregation expects.</span></span> <span data-ttu-id="a2c9a-111">Преобразование использует эти сведения для оптимизации исходного размера своего кэша.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-111">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="a2c9a-112">По умолчанию значение этого параметра **Не указано**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-112">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="a2c9a-113">Если указаны и **Порядок числа ключей** , и **Число ключей** , то **Число ключей** имеет более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-113">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
|<span data-ttu-id="a2c9a-114">Значение</span><span class="sxs-lookup"><span data-stu-id="a2c9a-114">Value</span></span>|<span data-ttu-id="a2c9a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a2c9a-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a2c9a-116">Не указан</span><span class="sxs-lookup"><span data-stu-id="a2c9a-116">Unspecified</span></span>|<span data-ttu-id="a2c9a-117">Свойство **Порядок числа ключей** не используется.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-117">The **Keys scale** property is not used.</span></span>|  
|<span data-ttu-id="a2c9a-118">Низкий</span><span class="sxs-lookup"><span data-stu-id="a2c9a-118">Low</span></span>|<span data-ttu-id="a2c9a-119">Агрегат может записывать около 500 000 ключей.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-119">Aggregation can write approximately 500,000 keys.</span></span>|  
|<span data-ttu-id="a2c9a-120">Средний</span><span class="sxs-lookup"><span data-stu-id="a2c9a-120">Medium</span></span>|<span data-ttu-id="a2c9a-121">Агрегат может записывать около 5 000 000 ключей.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-121">Aggregation can write approximately 5,000,000 keys.</span></span>|  
|<span data-ttu-id="a2c9a-122">Высокий</span><span class="sxs-lookup"><span data-stu-id="a2c9a-122">High</span></span>|<span data-ttu-id="a2c9a-123">Агрегат может записывать более 25 000 000 ключей.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-123">Aggregation can write more than 25,000,000 keys.</span></span>|  
  
 <span data-ttu-id="a2c9a-124">**Число ключей**</span><span class="sxs-lookup"><span data-stu-id="a2c9a-124">**Number of keys**</span></span>  
 <span data-ttu-id="a2c9a-125">Также можно указать точное число ключей, ожидаемых после статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-125">Optionally specify the exact number of keys that the aggregation expects.</span></span> <span data-ttu-id="a2c9a-126">Преобразование использует эти сведения для оптимизации исходного размера своего кэша.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-126">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="a2c9a-127">Если указаны и **Порядок числа ключей** , и **Число ключей** , то **Число ключей** имеет более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-127">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
 <span data-ttu-id="a2c9a-128">**Порядок числа различных ключей**</span><span class="sxs-lookup"><span data-stu-id="a2c9a-128">**Count distinct scale**</span></span>  
 <span data-ttu-id="a2c9a-129">Дополнительно можно указать приблизительное количество различающихся значений, которое может записывать агрегат.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-129">Optionally specify the approximate number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="a2c9a-130">По умолчанию значение этого параметра **Не указано**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-130">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="a2c9a-131">Если указаны и параметр **Порядок числа различных ключей** , и параметр **Количество различных ключей** , то параметр **Количество различных ключей** имеет более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-131">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
|<span data-ttu-id="a2c9a-132">Значение</span><span class="sxs-lookup"><span data-stu-id="a2c9a-132">Value</span></span>|<span data-ttu-id="a2c9a-133">Описание</span><span class="sxs-lookup"><span data-stu-id="a2c9a-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a2c9a-134">Не указан</span><span class="sxs-lookup"><span data-stu-id="a2c9a-134">Unspecified</span></span>|<span data-ttu-id="a2c9a-135">Свойство CountDistinctScale не используется.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-135">The CountDistinctScale property is not used.</span></span>|  
|<span data-ttu-id="a2c9a-136">Низкий</span><span class="sxs-lookup"><span data-stu-id="a2c9a-136">Low</span></span>|<span data-ttu-id="a2c9a-137">Статистическая функция может записывать примерно 500 000 уникальных ключей.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-137">Aggregation can write approximately 500,000 distinct values.</span></span>|  
|<span data-ttu-id="a2c9a-138">Средний</span><span class="sxs-lookup"><span data-stu-id="a2c9a-138">Medium</span></span>|<span data-ttu-id="a2c9a-139">Агрегат может записывать примерно 5 000 000 различных значений.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-139">Aggregation can write approximately 5,000,000 distinct values.</span></span>|  
|<span data-ttu-id="a2c9a-140">Высокий</span><span class="sxs-lookup"><span data-stu-id="a2c9a-140">High</span></span>|<span data-ttu-id="a2c9a-141">Агрегат может записывать более 25 000 000 различающихся ключей.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-141">Aggregation can write more than 25,000,000 distinct values.</span></span>|  
  
 <span data-ttu-id="a2c9a-142">**Количество различных ключей**</span><span class="sxs-lookup"><span data-stu-id="a2c9a-142">**Count distinct keys**</span></span>  
 <span data-ttu-id="a2c9a-143">При необходимости можно указать точное количество различающихся значений, которое может записывать агрегат.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-143">Optionally specify the exact number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="a2c9a-144">Если указаны и параметр **Порядок числа различных ключей** , и параметр **Количество различных ключей** , то параметр **Количество различных ключей** имеет более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-144">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
 <span data-ttu-id="a2c9a-145">**Коэффициент автоматического расширения**</span><span class="sxs-lookup"><span data-stu-id="a2c9a-145">**Auto extend factor**</span></span>  
 <span data-ttu-id="a2c9a-146">Значение от 1 до 100 указывает процент, на который может увеличиваться объем памяти при статистической обработке.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-146">Use a value between 1 and 100 to specify the percentage by which memory can be extended during the aggregation.</span></span> <span data-ttu-id="a2c9a-147">По умолчанию значение этого параметра — **25%**.</span><span class="sxs-lookup"><span data-stu-id="a2c9a-147">By default, the value of this option is **25%**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c9a-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2c9a-148">See Also</span></span>  
 <span data-ttu-id="a2c9a-149">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a2c9a-149">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a2c9a-150">[Редактор преобразования "Статистическая обработка" &#40;вкладка "агрегаты"&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span><span class="sxs-lookup"><span data-stu-id="a2c9a-150">[Aggregate Transformation Editor &#40;Aggregations Tab&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span></span>  
 [<span data-ttu-id="a2c9a-151">Статистическая обработка значений в наборе данных с помощью преобразования «Агрегатная обработка»</span><span class="sxs-lookup"><span data-stu-id="a2c9a-151">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>](data-flow/transformations/aggregate-values-in-a-dataset-by-using-the-aggregate-transformation.md)  
  
  
