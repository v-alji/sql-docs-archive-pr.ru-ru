---
title: Развертывание и масштабирование моделей интеллектуального анализа (надстройки интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- manage
ms.assetid: 4c617375-6b01-4a71-9680-de0cbf2cff05
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd2839144d4d1667da09830aaabd1ec3f17a9c21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666268"
---
# <a name="deploying-and-scaling-mining-models-data-mining-add-ins-for-excel"></a><span data-ttu-id="5c74c-102">Развертывание и масштабирование моделей интеллектуального анализа данных (надстройки интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="5c74c-102">Deploying and Scaling Mining Models (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="5c74c-103">Средства в группе " **Использование модели** " и " **Управление** " позволяют управлять существующими моделями интеллектуального анализа данных и просматривать их.</span><span class="sxs-lookup"><span data-stu-id="5c74c-103">The tools in the **Model Usage** and **Management** group are provided to help you manage and browse existing mining models.</span></span> <span data-ttu-id="5c74c-104">Эти средства можно использовать для просмотра любых моделей, хранящихся в экземпляре [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , а не только тех, которые были созданы с помощью надстроек.</span><span class="sxs-lookup"><span data-stu-id="5c74c-104">You can use these tools to view any models that are stored on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], not just those created using the add-ins.</span></span>  
  
 <span data-ttu-id="5c74c-105">При наличии необходимых разрешений можно удалять, изменять, переименовывать или обрабатывать существующие модели и структуры интеллектуального анализа данных, не выходя из Excel.</span><span class="sxs-lookup"><span data-stu-id="5c74c-105">If you have the necessary permissions, you can delete, modify, rename, or process existing mining models and structures without leaving Excel.</span></span>  
  
## <a name="model-usage-toolbar"></a><span data-ttu-id="5c74c-106">Панель инструментов использования модели</span><span class="sxs-lookup"><span data-stu-id="5c74c-106">Model Usage Toolbar</span></span>  
  
### <a name="browse"></a><span data-ttu-id="5c74c-107">Просмотреть</span><span class="sxs-lookup"><span data-stu-id="5c74c-107">Browse</span></span>  
 <span data-ttu-id="5c74c-108">Используйте мастер **обзора** для выбора существующей модели интеллектуального анализа данных, а затем просмотрите и изучите модель в средстве просмотра, содержащем несколько графиков и средств.</span><span class="sxs-lookup"><span data-stu-id="5c74c-108">Use the **Browse** wizard to select an existing data mining model, and then view and explore the model in a viewer that contains multiple graphs and tools.</span></span>  
  
 <span data-ttu-id="5c74c-109">Дополнительные сведения см. [в разделе Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="5c74c-109">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="document-model"></a><span data-ttu-id="5c74c-110">Документирование модели</span><span class="sxs-lookup"><span data-stu-id="5c74c-110">Document Model</span></span>  
 <span data-ttu-id="5c74c-111">Нажмите кнопку **модель документа** , чтобы запустить мастер, который создает отчет о структурах интеллектуального анализа данных и созданных моделях интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5c74c-111">Click **Document Model** to start a wizard that creates a report of the mining structures and mining models that you have created.</span></span> <span data-ttu-id="5c74c-112">Можно создавать простые или расширенные отчеты.</span><span class="sxs-lookup"><span data-stu-id="5c74c-112">You can create basic or advanced reports.</span></span> <span data-ttu-id="5c74c-113">Отчеты включают метаданные столбцов и модели, поэтому они полезны для документирования работы и отслеживания изменений в моделях.</span><span class="sxs-lookup"><span data-stu-id="5c74c-113">The reports include column and model metadata, so are useful for documenting your work and tracking changes in models.</span></span>  
  
 <span data-ttu-id="5c74c-114">Дополнительные сведения см. в разделе [документирование моделей интеллектуального анализа данных &#40;надстройки интеллектуального анализа для Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5c74c-114">For more information, see [Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span></span>  
  
### <a name="query"></a><span data-ttu-id="5c74c-115">Запрос</span><span class="sxs-lookup"><span data-stu-id="5c74c-115">Query</span></span>  
 <span data-ttu-id="5c74c-116">Нажмите кнопку **запрос** , чтобы запустить мастер **запросов** .</span><span class="sxs-lookup"><span data-stu-id="5c74c-116">Click **Query** to start the **Query** wizard.</span></span> <span data-ttu-id="5c74c-117">Мастер интерактивно просматривает процесс создания прогнозирующего запроса к существующей модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5c74c-117">The wizard interactively walks you through the process of creating a prediction query against an existing data mining model.</span></span>  
  
 <span data-ttu-id="5c74c-118">Для дальнейшей настройки запроса или построения запросов, не входящих в мастер, просто нажмите кнопку **Дополнительно** , чтобы запустить **Расширенный редактор запроса интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="5c74c-118">To further customize the query, or build queries not included in the wizard, just click the **Advanced** button to start the **Data Mining Query Advanced Editor**.</span></span>  
  
 <span data-ttu-id="5c74c-119">Дополнительные сведения см. в разделе [Query &#40;SQL Server надстроек интеллектуального анализа данных&#41;](query-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="5c74c-119">For more information, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="data-mining-advanced-query-editor"></a><span data-ttu-id="5c74c-120">Расширенный редактор запросов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="5c74c-120">Data Mining Advanced Query Editor</span></span>  
 <span data-ttu-id="5c74c-121">В этом редакторе можно использовать шаблоны расширений интеллектуального анализа данных, чтобы быстро запустить запрос, а затем изменить входные данные, выходные данные, алгоритмы и параметры, чтобы создать пользовательскую модель интеллектуального анализа данных, структуру интеллектуального анализа данных или прогнозирующий запрос.</span><span class="sxs-lookup"><span data-stu-id="5c74c-121">In this editor, you can use Data Mining Extensions (DMX) templates to jumpstart a query, and then modify the inputs, outputs, algorithms, and parameters to create a custom mining model, mining structure, or prediction query.</span></span>  
  
 <span data-ttu-id="5c74c-122">Дополнительные сведения см. в разделе [Расширенный редактор запросов интеллектуального анализа данных](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5c74c-122">For more information, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="management"></a><span data-ttu-id="5c74c-123">Управление</span><span class="sxs-lookup"><span data-stu-id="5c74c-123">Management</span></span>  
 <span data-ttu-id="5c74c-124">Используйте мастер **управления моделями** для просмотра существующих моделей в текущем соединении.</span><span class="sxs-lookup"><span data-stu-id="5c74c-124">Use the **Manage Models** wizard to view existing models on the current connection.</span></span> <span data-ttu-id="5c74c-125">Также можно удалять, переименовывать, обрабатывать, импортировать и экспортировать модели и структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5c74c-125">You can also delete, rename, process, or import and export mining models and structures.</span></span>  
  
 <span data-ttu-id="5c74c-126">Дополнительные сведения см. в разделе [Управление моделями &#40;SQL Server надстройки интеллектуального анализа данных&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="5c74c-126">For more information, see [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c74c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c74c-127">See Also</span></span>  
 <span data-ttu-id="5c74c-128">[Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="5c74c-128">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="5c74c-129">Проверка моделей и использование моделей для прогнозирования &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5c74c-129">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
