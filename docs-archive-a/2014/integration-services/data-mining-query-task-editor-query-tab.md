---
title: Редактор задачи «Запрос интеллектуального анализа данных» (вкладка «запрос») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.query.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 72b1755d-d226-46c5-b862-0c9333196a10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6005c92d0d48850461c01353ddf94c61140d0f2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738519"
---
# <a name="data-mining-query-task-editor-query-tab"></a><span data-ttu-id="e522a-102">Редактор задачи «Запрос интеллектуального анализа данных» (вкладка «Запрос»)</span><span class="sxs-lookup"><span data-stu-id="e522a-102">Data Mining Query Task Editor (Query Tab)</span></span>
  <span data-ttu-id="e522a-103">Используйте вкладку **Запрос** диалогового окна **Задача «Запрос интеллектуального анализа данных»** , чтобы создать запросы прогноза, основанные на модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e522a-103">Use the **Query** tab of the **Data Mining Query Task** dialog box to create prediction queries based on a mining model.</span></span> <span data-ttu-id="e522a-104">В этом диалоговом окне также можно привязать параметры и результирующие наборы к переменным.</span><span class="sxs-lookup"><span data-stu-id="e522a-104">In this dialog box you can also bind parameters and result sets to variables.</span></span>  
  
 <span data-ttu-id="e522a-105">Сведения об интеллектуальном анализе данных в пакетах см. в разделах [Задача "Запрос интеллектуального анализа данных"](control-flow/data-mining-query-task.md) и [Решения для интеллектуального анализа данных](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="e522a-105">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="e522a-106">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e522a-106">General Options</span></span>  
 <span data-ttu-id="e522a-107">**имя**;</span><span class="sxs-lookup"><span data-stu-id="e522a-107">**Name**</span></span>  
 <span data-ttu-id="e522a-108">Задайте уникальное имя для задачи «Запрос интеллектуального анализа данных».</span><span class="sxs-lookup"><span data-stu-id="e522a-108">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="e522a-109">Это имя используется в качестве метки для значка задачи.</span><span class="sxs-lookup"><span data-stu-id="e522a-109">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e522a-110">Имена задач в пределах пакета должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="e522a-110">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="e522a-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e522a-111">**Description**</span></span>  
 <span data-ttu-id="e522a-112">Введите описание задачи «Запрос интеллектуального анализа данных».</span><span class="sxs-lookup"><span data-stu-id="e522a-112">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="build-query-tab-options"></a><span data-ttu-id="e522a-113">Параметры вкладки «Построение запроса»</span><span class="sxs-lookup"><span data-stu-id="e522a-113">Build Query Tab Options</span></span>  
 <span data-ttu-id="e522a-114">**Запрос интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="e522a-114">**Data mining query**</span></span>  
 <span data-ttu-id="e522a-115">Введите запрос интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e522a-115">Type a data mining query.</span></span>  
  
 <span data-ttu-id="e522a-116">**См. также:**  [Справочник по расширениям интеллектуального анализа данных (расширения интеллектуального анализа данных)](/sql/dmx/data-mining-extensions-dmx-reference)</span><span class="sxs-lookup"><span data-stu-id="e522a-116">**Related Topics:**  [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference)</span></span>  
  
 <span data-ttu-id="e522a-117">**Создать новый запрос**</span><span class="sxs-lookup"><span data-stu-id="e522a-117">**Build New Query**</span></span>  
 <span data-ttu-id="e522a-118">Создать запрос интеллектуального анализа данных, используя графическое средство.</span><span class="sxs-lookup"><span data-stu-id="e522a-118">Create the data mining query using a graphical tool.</span></span>  
  
 <span data-ttu-id="e522a-119">**См. также:** [Data Mining Query](control-flow/data-mining-query.md)</span><span class="sxs-lookup"><span data-stu-id="e522a-119">**Related Topics:** [Data Mining Query](control-flow/data-mining-query.md)</span></span>  
  
## <a name="parameter-mapping-tab-options"></a><span data-ttu-id="e522a-120">Параметры вкладки «Сопоставление параметров»</span><span class="sxs-lookup"><span data-stu-id="e522a-120">Parameter Mapping Tab Options</span></span>  
 <span data-ttu-id="e522a-121">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="e522a-121">**Parameter Name**</span></span>  
 <span data-ttu-id="e522a-122">При необходимости обновите имя параметра.</span><span class="sxs-lookup"><span data-stu-id="e522a-122">Optionally, update the parameter name.</span></span> <span data-ttu-id="e522a-123">Сопоставьте параметр с переменной, выбрав переменную из списка **Имя переменной** .</span><span class="sxs-lookup"><span data-stu-id="e522a-123">Map the parameter to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="e522a-124">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="e522a-124">**Variable Name**</span></span>  
 <span data-ttu-id="e522a-125">Выберите переменную из списка, чтобы сопоставить ее с параметром.</span><span class="sxs-lookup"><span data-stu-id="e522a-125">Select a variable in the list to map it to the parameter.</span></span>  
  
 <span data-ttu-id="e522a-126">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="e522a-126">**Add**</span></span>  
 <span data-ttu-id="e522a-127">Добавить параметр к списку.</span><span class="sxs-lookup"><span data-stu-id="e522a-127">Add to a parameter to the list.</span></span>  
  
 <span data-ttu-id="e522a-128">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="e522a-128">**Remove**</span></span>  
 <span data-ttu-id="e522a-129">Выберите параметр, а затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e522a-129">Select a parameter, and then click **Remove**.</span></span>  
  
## <a name="result-set-tab-options"></a><span data-ttu-id="e522a-130">Параметры вкладки «Результирующий набор»</span><span class="sxs-lookup"><span data-stu-id="e522a-130">Result Set Tab Options</span></span>  
 <span data-ttu-id="e522a-131">**Имя результата**</span><span class="sxs-lookup"><span data-stu-id="e522a-131">**Result Name**</span></span>  
 <span data-ttu-id="e522a-132">При необходимости обновите имя результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="e522a-132">Optionally, update the result set name.</span></span> <span data-ttu-id="e522a-133">Сопоставьте результат с переменной, выбрав переменную из списка **Имя переменной** .</span><span class="sxs-lookup"><span data-stu-id="e522a-133">Map the result to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="e522a-134">После добавления результата нажатием кнопки **Добавить**укажите уникальное имя для результата.</span><span class="sxs-lookup"><span data-stu-id="e522a-134">After you have added a result by clicking **Add**, provide a unique name for the result.</span></span>  
  
 <span data-ttu-id="e522a-135">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="e522a-135">**Variable Name**</span></span>  
 <span data-ttu-id="e522a-136">Выберите переменную из списка, чтобы сопоставить ее с результирующим набором.</span><span class="sxs-lookup"><span data-stu-id="e522a-136">Select a variable in the list to map it to the result set.</span></span>  
  
 <span data-ttu-id="e522a-137">**Тип результата**</span><span class="sxs-lookup"><span data-stu-id="e522a-137">**Result Type**</span></span>  
 <span data-ttu-id="e522a-138">Укажите, должна ли возвращаться одиночная строка или полный результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="e522a-138">Indicate whether to return a single row or a full result set.</span></span>  
  
 <span data-ttu-id="e522a-139">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="e522a-139">**Add**</span></span>  
 <span data-ttu-id="e522a-140">Добавить результирующий набор к списку.</span><span class="sxs-lookup"><span data-stu-id="e522a-140">Add a result set to the list.</span></span>  
  
 <span data-ttu-id="e522a-141">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="e522a-141">**Remove**</span></span>  
 <span data-ttu-id="e522a-142">Выберите результат, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e522a-142">Select a result, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e522a-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="e522a-143">See Also</span></span>  
 <span data-ttu-id="e522a-144">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e522a-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e522a-145">[Редактор задачи «Запрос интеллектуального анализа данных» &#40;вкладку «модель интеллектуального анализа»&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="e522a-145">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="e522a-146">[Редактор задачи "запрос интеллектуального анализа данных" &#40;вкладка "выходные данные"&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span><span class="sxs-lookup"><span data-stu-id="e522a-146">[Data Mining Query Task Editor &#40;Output Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span></span>  
 [<span data-ttu-id="e522a-147">Конструктора моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="e522a-147">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
