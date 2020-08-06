---
title: Запрос (SQL Server надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [data mining]
- Data Mining Query Advanced Editor
- query builder [data mining]
- DMX
ms.assetid: 16af4a6f-18d4-496a-a304-7a13aa32ee76
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90794aae8a3d664d47ab251ffdd954f22d48f992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738921"
---
# <a name="query-sql-server-data-mining-add-ins"></a><span data-ttu-id="fe9c3-102">Запрос (надстройки интеллектуального анализа данных SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fe9c3-102">Query (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="fe9c3-103">![Кнопка «Модель запроса» на ленте «Интеллектуальный анализ данных»](media/dmc-query.gif "Кнопка «Модель запроса» на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="fe9c3-103">![Query Model button, Data Mining ribbon](media/dmc-query.gif "Query Model button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="fe9c3-104">С помощью мастера **Запрос** выполняется взаимодействие с существующими моделями интеллектуального анализа данных для создания прогнозов на основе данных таблицы Excel, диапазона Excel или другого источника данных.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-104">The **Query** wizard helps you interact with existing mining models to make predictions based on data in an Excel table, an Excel range, or another data source.</span></span> <span data-ttu-id="fe9c3-105">Процесс применения новых данных к существующей модели для прогнозирования трендов называется *прогнозирующим запросом*.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-105">The process of applying new data to an existing model to predict trends is called a *prediction query*.</span></span>  
  
 <span data-ttu-id="fe9c3-106">Мастер **запросов** также предоставляет расширенный редактор для создания или изменения моделей интеллектуального анализа данных, создания пользовательских запросов или работы со структурами, не поддерживаемыми в других средствах, например со вложенными наборами данных.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-106">The **Query** wizard also provides an advanced editor for creating or modifying data mining models, for generating custom queries, or for working with structures not supported in the other tools, such as nested datasets.</span></span>  
  
-   <span data-ttu-id="fe9c3-107">Используйте текстовый редактор для ввода или вставки инструкций расширений интеллектуального анализа данных, созданных в других местах.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-107">Use the text editor to type or paste in the Data Mining Extensions (DMX) statements you've created elsewhere.</span></span>  
  
-   <span data-ttu-id="fe9c3-108">Используйте интерактивный построитель запросов для построения пользовательских инструкции расширений интеллектуального анализа данных с помощью шаблонов и диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-108">Use the interactive Query Builder to compose a custom DMX statement with the help of templates and dialog boxes.</span></span>  
  
-   <span data-ttu-id="fe9c3-109">Можно создавать пользовательские инструкции расширений интеллектуального анализа данных для управления или резервного копирования моделей или структур интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-109">Create DMX statements to manage or back up mining models and structures.</span></span>  
  
## <a name="using-the-query-wizard"></a><span data-ttu-id="fe9c3-110">Использование мастера запросов</span><span class="sxs-lookup"><span data-stu-id="fe9c3-110">Using the Query Wizard</span></span>  
  
1.  <span data-ttu-id="fe9c3-111">Вначале необходимо определить источник данных, который будет использоваться в качестве входного.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-111">First, you must specify a source for the data to use as input.</span></span> <span data-ttu-id="fe9c3-112">Можно использовать данные в существующей таблице или диапазоне Excel, либо указать инструкцию SQL для получения данных.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-112">You can use data in an existing Excel table or range, or you can specify a SQL statement to retrieve the data.</span></span>  
  
2.  <span data-ttu-id="fe9c3-113">Затем мастер выводит список моделей интеллектуального анализа данных на сервере, с которым установлено соединение.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-113">Next, the wizard presents a list of data mining models on the server to which you are connected.</span></span> <span data-ttu-id="fe9c3-114">Если известно, какая модель необходима, и пользователь знаком с интеллектуальным анализом данных, можно также нажать кнопку **Дополнительно** , чтобы открыть **Расширенный редактор запросов интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-114">If you know the model you want and are familiar with data mining, you can also click **Advanced** to open the **Data Mining Advanced Query Editor**.</span></span>  
  
3.  <span data-ttu-id="fe9c3-115">В зависимости от выбранного типа модели, необходимо указать столбец, содержащий данные, подлежащие оценке, и определить сопоставления между столбцами входных данных и столбцами модели.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-115">Depending on the type of model that you choose, you must specify the column that contains the data to be evaluated, and define mappings between the input data columns and the model columns.</span></span> <span data-ttu-id="fe9c3-116">В зависимости от выбранного алгоритма, можно настроить другие свойства модели.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-116">Depending on the algorithm you choose, you can set other properties on the model.</span></span>  
  
4.  <span data-ttu-id="fe9c3-117">В конце своей работы мастер также предоставляет возможность выбрать один или более прогнозов и позволяет указать назначение для хранения результатов.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-117">Finally, the wizard also gives you the ability to choose one or more predictions, and specify a destination in which to store the results.</span></span>  
  
 <span data-ttu-id="fe9c3-118">В любое время можно нажать кнопку **Дополнительно** , чтобы переключиться в **Расширенный редактор запросов интеллектуального анализа данных**, позволяющий управлять каждой частью инструкции DMX.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-118">At any time, you can click **Advanced** to switch to the **Data Mining Advanced Query Editor**, which gives you more control over each part of the DMX statement.</span></span> <span data-ttu-id="fe9c3-119">Дополнительные сведения об использовании расширенных средств редактирования запросов см. в разделе [Расширенный редактор запросов интеллектуального анализа данных](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="fe9c3-119">For more information about how to use the advanced query editing tools, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="fe9c3-120">Требования</span><span class="sxs-lookup"><span data-stu-id="fe9c3-120">Requirements</span></span>  
 <span data-ttu-id="fe9c3-121">Чтобы использовать **мастер запросов** , необходимо установить соединение с экземпляром служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe9c3-121">To use the **Query** wizard, you must be connected to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="fe9c3-122">Кроме того, сервер должен содержать по меньшей мере одну модель интеллектуального анализа данных соответствующего типа.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-122">Moreover, the server must contain at least one data mining model of an appropriate type.</span></span> <span data-ttu-id="fe9c3-123">Если нет доступной модели интеллектуального анализа данных, ее можно создать с помощью мастеров клиента интеллектуального анализа данных для Excel.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-123">If no mining models are available, you can create one by using the wizards provided in the Data Mining Client for Excel.</span></span> <span data-ttu-id="fe9c3-124">Сведения о создании нового режима интеллектуального анализа с помощью мастера см. в разделе [Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="fe9c3-124">For information about how to create a new mining mode by using a wizard, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe9c3-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe9c3-125">See Also</span></span>  
 <span data-ttu-id="fe9c3-126">[Развертывание и масштабирование моделей интеллектуального анализа &#40;надстройки интеллектуального анализа данных для Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="fe9c3-126">[Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="fe9c3-127">Клиент интеллектуального анализа данных для Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="fe9c3-127">Data Mining Client for Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](data-mining-client-for-excel-sql-server-data-mining-add-ins.md)  
  
  
