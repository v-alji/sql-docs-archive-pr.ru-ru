---
title: Шаблоны расширений интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a577e52-821d-4bd3-ba35-075a6be285c9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79c8615933baf4fa3d80974daae91b4d1c7fa101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667471"
---
# <a name="dmx-templates"></a><span data-ttu-id="0b23e-102">Шаблоны расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-102">DMX Templates</span></span>
  <span data-ttu-id="0b23e-103">Шаблоны интеллектуального анализа данных позволяют быстро создавать сложные запросы.</span><span class="sxs-lookup"><span data-stu-id="0b23e-103">The data mining templates help you quickly build sophisticated queries.</span></span> <span data-ttu-id="0b23e-104">Хотя общий синтаксис для DMX-запросов хорошую описан в документации, использование шаблонов облегчает построение запросов, так как можно просто щелкать и указывать аргументы и источники данных.</span><span class="sxs-lookup"><span data-stu-id="0b23e-104">Although the general syntax for DMX queries is well documented, using the templates makes it easier to build queries by clicking and pointing to arguments and data sources.</span></span>  
  
## <a name="using-the-templates"></a><span data-ttu-id="0b23e-105">Использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="0b23e-105">Using the Templates</span></span>  
  
1.  <span data-ttu-id="0b23e-106">В окне клиента интеллектуального анализа данных для Excel выберите **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="0b23e-106">In the Data Mining Client for Excel, click **Query**.</span></span>  
  
2.  <span data-ttu-id="0b23e-107">На **начальной** странице мастера нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b23e-107">On the wizard **Start** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="0b23e-108">На странице **Выбор модели**нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="0b23e-108">On the page, **Select Model**, click **Advanced**.</span></span>  
  
     <span data-ttu-id="0b23e-109">**Совет.** Если планируется создание прогнозирующего запроса для модели, можно сначала выбрать модель, а затем нажать кнопку **Дополнительно**, чтобы указать в шаблоне имя модели.</span><span class="sxs-lookup"><span data-stu-id="0b23e-109">**Tip:** If you are going to create a prediction query on a model, you can select the model first, and then click **Advanced**, to prepopulate the template with the model name.</span></span>  
  
4.  <span data-ttu-id="0b23e-110">В **расширенном редакторе запросов интеллектуального анализа данных**щелкните **Шаблоны расширения интеллектуального анализа данных**и выберите шаблон.</span><span class="sxs-lookup"><span data-stu-id="0b23e-110">In the **Data Mining Advanced Query Editor**, click **DMX Templates**, and select a template.</span></span>  
  
5.  <span data-ttu-id="0b23e-111">Нажмите клавишу ВВОД, чтобы загрузить шаблон на панель DMX-запроса.</span><span class="sxs-lookup"><span data-stu-id="0b23e-111">Press ENTER to load the template into the DMX Query pane.</span></span>  
  
6.  <span data-ttu-id="0b23e-112">Продолжайте щелкать по ссылкам в шаблоне. Когда появляется диалоговое окно, выберите соответствующие выходные данные, модель или параметр.</span><span class="sxs-lookup"><span data-stu-id="0b23e-112">Continue clicking the links in the template, and as the dialog box appears, select an appropriate output, model, or parameter.</span></span>  
  
     <span data-ttu-id="0b23e-113">Для прогнозирующих запросов сначала выберите входной набор данных, а затем сопоставьте столбцы.</span><span class="sxs-lookup"><span data-stu-id="0b23e-113">For prediction queries, choose the input dataset first, and then map the columns.</span></span>  
  
7.  <span data-ttu-id="0b23e-114">Щелкните **Изменить запрос** , чтобы перейти в представление текстового редактора и вручную изменить запрос.</span><span class="sxs-lookup"><span data-stu-id="0b23e-114">Click **Edit Query** to switch to text editor view and manually change the query.</span></span>  
  
     <span data-ttu-id="0b23e-115">Помните, что при переключении представлений во время работы в редакторе запросов любые параметры, заданные в текущем представлении, будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="0b23e-115">Be aware, however, that if you switch views when working in the query editor, any information that you had in the previous view will be cleared.</span></span> <span data-ttu-id="0b23e-116">Перед переключением представления сохраните изменения, скопировав и вставив инструкции расширений интеллектуального анализа данных в отдельный файл.</span><span class="sxs-lookup"><span data-stu-id="0b23e-116">Before changing views, save your work by copying and pasting the DMX statements to a separate file.</span></span>  
  
8.  <span data-ttu-id="0b23e-117">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0b23e-117">Click **Finish**.</span></span> <span data-ttu-id="0b23e-118">В диалоговом окне **Выбор назначения** укажите место сохранения результатов.</span><span class="sxs-lookup"><span data-stu-id="0b23e-118">In the **Choose Destination** dialog  box, specify where you want the result saved.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="0b23e-119">В случае успешного выполнения инструкция DMX, отправленная на сервер, также сохраняется в окне **Трассировка** .</span><span class="sxs-lookup"><span data-stu-id="0b23e-119">If you executed a statement successfully, the DMX statement that you sent to the server is also recorded in the **Trace** window.</span></span> <span data-ttu-id="0b23e-120">Дополнительные сведения об использовании функции трассировки см. в разделе [трассировка &#40;клиент интеллектуального анализа данных для Excel&#41;](trace-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="0b23e-120">For more information about how to use the Trace feature, see [Trace &#40;Data Mining Client for Excel&#41;](trace-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="0b23e-121">Дополнительные сведения об использовании расширенного редактора запросов интеллектуального анализа данных см. в разделе [Query &#40;SQL Server надстройки интеллектуального анализа данных&#41;](query-sql-server-data-mining-add-ins.md) и [Расширенный редактор запросов интеллектуального анализа данных](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="0b23e-121">For more information about how to use the Data Mining Advanced Query Editor, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) and [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="list-of-dmx-templates"></a><span data-ttu-id="0b23e-122">Список шаблонов расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-122">List of DMX Templates</span></span>  
 <span data-ttu-id="0b23e-123">В клиенте интеллектуального анализа данных для Excel есть следующие шаблоны расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="0b23e-123">The following DMX templates are included in the Data Mining Client for Excel.</span></span>  
  
 <span data-ttu-id="0b23e-124">**Прогнозирование**</span><span class="sxs-lookup"><span data-stu-id="0b23e-124">**Prediction**</span></span>  
  
 <span data-ttu-id="0b23e-125">Эти шаблоны позволяют создавать сложные прогнозирующие запросы, включая запросы, которые не поддерживаются мастером надстроек, например запросы, где используются вложенные таблицы или внешние источники данных.</span><span class="sxs-lookup"><span data-stu-id="0b23e-125">Use these templates to create advanced prediction queries, including queries not supported by the wizards in the add-ins, such as queries that use nested tables or external data sources.</span></span>  
  
-   <span data-ttu-id="0b23e-126">Отфильтрованные прогнозы</span><span class="sxs-lookup"><span data-stu-id="0b23e-126">Filtered predictions</span></span>  
  
-   <span data-ttu-id="0b23e-127">Отфильтрованные вложенные прогнозы</span><span class="sxs-lookup"><span data-stu-id="0b23e-127">Filtered nested predictions</span></span>  
  
-   <span data-ttu-id="0b23e-128">Вложенные прогнозы</span><span class="sxs-lookup"><span data-stu-id="0b23e-128">Nested predictions</span></span>  
  
-   <span data-ttu-id="0b23e-129">Одноэлементные прогнозы</span><span class="sxs-lookup"><span data-stu-id="0b23e-129">Singleton predictions</span></span>  
  
-   <span data-ttu-id="0b23e-130">Стандартные прогнозы</span><span class="sxs-lookup"><span data-stu-id="0b23e-130">Standard predictions</span></span>  
  
-   <span data-ttu-id="0b23e-131">Прогнозы временных рядов</span><span class="sxs-lookup"><span data-stu-id="0b23e-131">Time series predictions</span></span>  
  
-   <span data-ttu-id="0b23e-132">Прогнозирующий запрос TOP</span><span class="sxs-lookup"><span data-stu-id="0b23e-132">TOP prediction query</span></span>  
  
-   <span data-ttu-id="0b23e-133">Прогнозирующий запрос TOP для вложенной таблицы</span><span class="sxs-lookup"><span data-stu-id="0b23e-133">TOP prediction query on nested table</span></span>  
  
 <span data-ttu-id="0b23e-134">**Создание**</span><span class="sxs-lookup"><span data-stu-id="0b23e-134">**Create**</span></span>  
  
 <span data-ttu-id="0b23e-135">Эти шаблоны позволяют создавать пользовательские модели или структуры данных.</span><span class="sxs-lookup"><span data-stu-id="0b23e-135">Use these templates to build custom models or data structures.</span></span> <span data-ttu-id="0b23e-136">Вы не ограничены моделями, поддерживаемыми мастерами. Вы можете использовать любой алгоритм интеллектуального анализа данных, поддерживаемый экземпляром [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , к которому вы подключены, включая алгоритмы подключаемых модулей.</span><span class="sxs-lookup"><span data-stu-id="0b23e-136">You are not limited to the models supported by the wizards - you can use any data mining algorithm supported by the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you are connected to, including plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="0b23e-137">Модель интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-137">Mining model</span></span>  
  
-   <span data-ttu-id="0b23e-138">Структура интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-138">Mining structure</span></span>  
  
-   <span data-ttu-id="0b23e-139">Структура интеллектуального анализа данных с контрольными данными</span><span class="sxs-lookup"><span data-stu-id="0b23e-139">Mining structure with holdout</span></span>  
  
-   <span data-ttu-id="0b23e-140">Временная модель</span><span class="sxs-lookup"><span data-stu-id="0b23e-140">Temporary model</span></span>  
  
-   <span data-ttu-id="0b23e-141">Временная структура</span><span class="sxs-lookup"><span data-stu-id="0b23e-141">Temporary structure</span></span>  
  
 <span data-ttu-id="0b23e-142">**Свойства модели**</span><span class="sxs-lookup"><span data-stu-id="0b23e-142">**Model Properties**</span></span>  
  
 <span data-ttu-id="0b23e-143">Эти шаблоны позволяют создавать запросы, которые получают метаданные модели и обучающий набор.</span><span class="sxs-lookup"><span data-stu-id="0b23e-143">Use these templates to create queries that get metadata about the model and the training set.</span></span> <span data-ttu-id="0b23e-144">Можно также получить данные из содержимого модели или статистический профиль обучающих данных.</span><span class="sxs-lookup"><span data-stu-id="0b23e-144">You can also retrieve details from the model content, or get a statistical profile of the training data.</span></span>  
  
-   <span data-ttu-id="0b23e-145">Содержимое модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-145">Mining model content</span></span>  
  
-   <span data-ttu-id="0b23e-146">Минимальное и максимальное значения столбца</span><span class="sxs-lookup"><span data-stu-id="0b23e-146">Minimum and maximum column values</span></span>  
  
-   <span data-ttu-id="0b23e-147">Проверочные или обучающие варианты структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-147">Mining structure test/training cases</span></span>  
  
-   <span data-ttu-id="0b23e-148">Значения дискретных столбцов</span><span class="sxs-lookup"><span data-stu-id="0b23e-148">Discrete column values</span></span>  
  
 <span data-ttu-id="0b23e-149">**Управление**</span><span class="sxs-lookup"><span data-stu-id="0b23e-149">**Management**</span></span>  
  
 <span data-ttu-id="0b23e-150">Эти шаблоны позволяют выполнять любую задачу управления, поддерживаемую расширениями интеллектуального анализа данных, включая импорт и экспорт моделей, удаление и очистку моделей или структур данных.</span><span class="sxs-lookup"><span data-stu-id="0b23e-150">Use these templates to perform any management task supported by DMX, which includes importing and exporting models, deleting models, and clearing models or data structures.</span></span>  
  
-   <span data-ttu-id="0b23e-151">Очистка модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-151">Clear mining model</span></span>  
  
-   <span data-ttu-id="0b23e-152">Очистка структуры и модели</span><span class="sxs-lookup"><span data-stu-id="0b23e-152">Clear structure and models</span></span>  
  
-   <span data-ttu-id="0b23e-153">Очистка структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-153">Clear mining structure</span></span>  
  
-   <span data-ttu-id="0b23e-154">Удаление модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-154">Delete mining model</span></span>  
  
-   <span data-ttu-id="0b23e-155">Удаление структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-155">Delete mining structure</span></span>  
  
-   <span data-ttu-id="0b23e-156">Переименование модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-156">Rename mining model</span></span>  
  
-   <span data-ttu-id="0b23e-157">Переименование структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-157">Rename mining structure</span></span>  
  
-   <span data-ttu-id="0b23e-158">Обучение модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-158">Train mining model</span></span>  
  
-   <span data-ttu-id="0b23e-159">Обучение вложенной структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-159">Train nested mining structure</span></span>  
  
-   <span data-ttu-id="0b23e-160">Обучение структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-160">Train mining structure</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="0b23e-161">Требования</span><span class="sxs-lookup"><span data-stu-id="0b23e-161">Requirements</span></span>  
 <span data-ttu-id="0b23e-162">В зависимости от используемого шаблона могут потребоваться административные разрешения, чтобы получить доступ к серверу служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="0b23e-162">Depending on which template you are using, you might need administrative permissions to access the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b23e-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b23e-163">See Also</span></span>  
 [<span data-ttu-id="0b23e-164">Создание модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="0b23e-164">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
