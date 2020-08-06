---
title: Редактор задачи "обработка Analysis Services" (страница "Analysis Services") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asprocessingtask.as.f1
helpviewer_keywords:
- Analysis Services Processing Task Editor
ms.assetid: 5612be78-57cf-4e4e-92cf-6bfa9f971040
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aabcfe286b40f58b429227654107d58e8a4ee837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657237"
---
# <a name="analysis-services-processing-task-editor-analysis-services-page"></a><span data-ttu-id="b8f2c-102">Редактор задачи «Обработка средствами Analysis Services» (страница «Средства Analysis Services»)</span><span class="sxs-lookup"><span data-stu-id="b8f2c-102">Analysis Services Processing Task Editor (Analysis Services Page)</span></span>
  <span data-ttu-id="b8f2c-103">Используйте страницу **Службы Analysis Services** диалогового окна **Редактор задачи «Обработка средствами Analysis Services»** для задания диспетчера соединений служб Analysis Services, выбора аналитических объектов для обработки, установки параметров обработки и действий при ошибках.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-103">Use the **Analysis Services** page of the **Analysis Services Processing Task Editor** dialog box to specify an Analysis Services connection manager, select the analytic objects to process, and set processing and error handling options.</span></span>  
  
 <span data-ttu-id="b8f2c-104">При обработке табличных моделей имейте в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-104">When processing tabular models, keep the following in mind:</span></span>  
  
1.  <span data-ttu-id="b8f2c-105">Невозможно выполнить анализ влияния на табличных моделях.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-105">You cannot perform impact analysis on tabular models.</span></span>  
  
2.  <span data-ttu-id="b8f2c-106">Не отображаются некоторые параметры обработки для табличного режима, такие как процесс дефрагментации и процесс повторного вычисления.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-106">Some processing options for tabular mode are not exposed, such as Process Defrag and Process Recalc.</span></span> <span data-ttu-id="b8f2c-107">Эти функции вы можете выполнить с помощью задачи «Выполнение инструкции DDL».</span><span class="sxs-lookup"><span data-stu-id="b8f2c-107">You can perform these functions by using the Execute DDL task.</span></span>  
  
3.  <span data-ttu-id="b8f2c-108">Некоторые предоставляемые параметры обработки, например индексы обработки, не подходят для табличных моделей, поэтому они не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-108">Some processing options provided, such as process indexes, are not appropriate for tabular models and should not be used.</span></span>  
  
4.  <span data-ttu-id="b8f2c-109">Параметры пакетов не учитываются в табличных моделях.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-109">Batch settings are ignored for tabular models.</span></span>  
  
 <span data-ttu-id="b8f2c-110">Дополнительные сведения об этой задаче см. в разделе [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="b8f2c-110">To learn about this task, see [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b8f2c-111">Варианты</span><span class="sxs-lookup"><span data-stu-id="b8f2c-111">Options</span></span>  
 <span data-ttu-id="b8f2c-112">**Диспетчер подключений Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-112">**Analysis Services connection manager**</span></span>  
 <span data-ttu-id="b8f2c-113">Выберите из списка существующий диспетчер подключений служб Analysis Services или нажмите кнопку **Создать** для его создания.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-113">Select an existing Analysis Services connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="b8f2c-114">**Создать**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-114">**New**</span></span>  
 <span data-ttu-id="b8f2c-115">Создайте новый диспетчер соединений служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-115">Create a new Analysis Services connection manager.</span></span>  
  
 <span data-ttu-id="b8f2c-116">**См. также:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Добавление диалогового окна "Диспетчер соединений со службами Analysis Services" в справочник по пользовательскому интерфейсу](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="b8f2c-116">**Related Topics:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span></span>  
  
 <span data-ttu-id="b8f2c-117">**Список объектов**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-117">**Object list**</span></span>  
 |<span data-ttu-id="b8f2c-118">Свойство</span><span class="sxs-lookup"><span data-stu-id="b8f2c-118">Property</span></span>|<span data-ttu-id="b8f2c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b8f2c-119">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="b8f2c-120">**Имени объекта**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-120">**Object Name**</span></span>|<span data-ttu-id="b8f2c-121">Позволяет отобразить список имен заданных объектов.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-121">Lists the specified object names.</span></span>|  
|<span data-ttu-id="b8f2c-122">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-122">**Type**</span></span>|<span data-ttu-id="b8f2c-123">Позволяет отобразить список типов заданных объектов.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-123">Lists the types of the specified objects.</span></span>|  
|<span data-ttu-id="b8f2c-124">**Параметры обработки**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-124">**Process Options**</span></span>|<span data-ttu-id="b8f2c-125">Выберите из списка параметр обработки.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-125">Select a processing option in the list.</span></span><br /><br /> <span data-ttu-id="b8f2c-126">**См. также**: [Обработка объектов многомерной модели](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span><span class="sxs-lookup"><span data-stu-id="b8f2c-126">**Related Topics**: [Multidimensional Model Object Processing](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span></span>|  
|<span data-ttu-id="b8f2c-127">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-127">**Settings**</span></span>|<span data-ttu-id="b8f2c-128">Позволяет отобразить список настроек обработки для заданных объектов.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-128">Lists processing settings for the specified objects.</span></span>|  
  
 <span data-ttu-id="b8f2c-129">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-129">**Add**</span></span>  
 <span data-ttu-id="b8f2c-130">Добавьте объект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в список.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-130">Add an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object to the list.</span></span>  
  
 <span data-ttu-id="b8f2c-131">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-131">**Remove**</span></span>  
 <span data-ttu-id="b8f2c-132">Выделите объект, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-132">Select an object, and then click **Delete**.</span></span>  
  
 <span data-ttu-id="b8f2c-133">**Анализ влияния**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-133">**Impact Analysis**</span></span>  
 <span data-ttu-id="b8f2c-134">Выполните анализ влияния на выбранный объект.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-134">Perform impact analysis on the selected object.</span></span>  
  
 <span data-ttu-id="b8f2c-135">**См. также:** [Диалоговое окно "Анализ влияния" (службы Analysis Services — многомерные данные)](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="b8f2c-135">**Related Topics:** [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
 <span data-ttu-id="b8f2c-136">**Сводка о настройках пакета**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-136">**Batch Settings Summary**</span></span>  
 |<span data-ttu-id="b8f2c-137">Свойство</span><span class="sxs-lookup"><span data-stu-id="b8f2c-137">Property</span></span>|<span data-ttu-id="b8f2c-138">Описание</span><span class="sxs-lookup"><span data-stu-id="b8f2c-138">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="b8f2c-139">**Порядок обработки**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-139">**Processing order**</span></span>|<span data-ttu-id="b8f2c-140">Позволяет задать, будут ли объекты обрабатываться последовательно или в составе пакета. При использовании параллельной обработки задает количество объектов для одновременной обработки.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-140">Specifies whether objects are processed sequentially or in a batch; if parallel processing is used, specifies the number of objects to process concurrently.</span></span>|  
|<span data-ttu-id="b8f2c-141">**Режим транзакции**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-141">**Transaction mode**</span></span>|<span data-ttu-id="b8f2c-142">Позволяет задать режим транзакции для последовательной обработки.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-142">Specifies the transaction mode for sequential processing.</span></span>|  
|<span data-ttu-id="b8f2c-143">**Ошибки измерения**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-143">**Dimension errors**</span></span>|<span data-ttu-id="b8f2c-144">Позволяет задать реакцию задачи на возникновение ошибок.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-144">Specifies the task behavior when errors occur.</span></span>|  
|<span data-ttu-id="b8f2c-145">**Путь к журналу ошибок ключа измерения**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-145">**Dimension key error log path**</span></span>|<span data-ttu-id="b8f2c-146">Позволяет задать путь к файлу журнала, в который записываются ошибки.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-146">Specifies the path of the file to which errors are logged.</span></span>|  
|<span data-ttu-id="b8f2c-147">**Обработать затронутые объекты**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-147">**Process affected objects**</span></span>|<span data-ttu-id="b8f2c-148">Позволяет указать, необходимо ли обрабатывать зависимые или затрагиваемые объекты.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-148">Indicates whether dependent or affected objects are also processed.</span></span>|  
  
 <span data-ttu-id="b8f2c-149">**Изменить параметры**</span><span class="sxs-lookup"><span data-stu-id="b8f2c-149">**Change Settings**</span></span>  
 <span data-ttu-id="b8f2c-150">Измените параметры обработки и действия при ошибках в ключах измерения.</span><span class="sxs-lookup"><span data-stu-id="b8f2c-150">Change the processing options and the handling of errors in dimension keys.</span></span>  
  
 <span data-ttu-id="b8f2c-151">**См. также:** [Диалоговое окно "Изменение настроек" (службы Analysis Services — многомерные данные)](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="b8f2c-151">**Related Topics:** [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f2c-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="b8f2c-152">See Also</span></span>  
 <span data-ttu-id="b8f2c-153">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b8f2c-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="b8f2c-154">[Редактор задачи "обработка Analysis Services" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="b8f2c-154">[Analysis Services Processing Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="b8f2c-155">Задача «Выполнение инструкции DDL служб Analysis Services»</span><span class="sxs-lookup"><span data-stu-id="b8f2c-155">Analysis Services Execute DDL Task</span></span>](control-flow/analysis-services-execute-ddl-task.md)  
  
  
