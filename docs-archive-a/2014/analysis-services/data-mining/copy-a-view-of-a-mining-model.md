---
title: Копирование представления модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clipboards [data mining]
- Mining Model Viewer [Analysis Services], clipboards
- copying mining models to clipboard
ms.assetid: 768372db-e5b4-4990-b459-03d854fd9a6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 36d4d372bd235cd1cc0c043ff98151091e242269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727486"
---
# <a name="copy-a-view-of-a-mining-model"></a><span data-ttu-id="867f0-102">Копирование представления модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="867f0-102">Copy a View of a Mining Model</span></span>
  <span data-ttu-id="867f0-103">Вкладка **Средство просмотра моделей интеллектуального анализа данных** в конструкторе интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] использует отдельное средство просмотра для каждого типа модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="867f0-103">The **Mining Model Viewer** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] uses a separate viewer for each type of mining model.</span></span> <span data-ttu-id="867f0-104">Некоторые средства просмотра имеют компоненты, из которых можно скопировать содержимое в буфер обмена, а затем вставить это содержимое в документ или в программу обработки изображений.</span><span class="sxs-lookup"><span data-stu-id="867f0-104">Several of the viewers have components from which you can copy the contents to the Clipboard, and from there paste the contents into a document or into image manipulation software.</span></span> <span data-ttu-id="867f0-105">Такой функциональностью обладают следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="867f0-105">The following components make this functionality available:</span></span>  
  
-   <span data-ttu-id="867f0-106">Диаграмма кластеров в средстве просмотра кластеров ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ) и средстве просмотра кластеризации последовательностей ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="867f0-106">Cluster Diagram in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="867f0-107">Дерево решений в средстве просмотра деревьев ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ) и средстве просмотра временных рядов ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="867f0-107">Decision Tree in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series Viewer</span></span>  
  
-   <span data-ttu-id="867f0-108">Преобразования состояний в средстве просмотра кластеризации последовательностей ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="867f0-108">State Transitions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="867f0-109">Сеть зависимостей в средстве просмотра правил взаимосвязи ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ), средстве просмотра упрощенного алгоритма Байеса ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ) и средстве просмотра деревьев ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="867f0-109">Dependency Network in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer, and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer</span></span>  
  
-   <span data-ttu-id="867f0-110">Содержимое модели интеллектуального анализа данных в области сведений узла средства просмотра деревьев содержимого общего вида ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="867f0-110">Mining model content, from the Node Details pane of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer</span></span>  
  
 <span data-ttu-id="867f0-111">Предусмотрена возможность скопировать все представление модели интеллектуального анализа данных или только ту ее часть, что представлена в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="867f0-111">You can copy the complete representation of the mining model, or just the part that is visible in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="867f0-112">При копировании модели с помощью средства просмотра новый объект модели не создается.</span><span class="sxs-lookup"><span data-stu-id="867f0-112">When you copy a model using the viewer, it does not create a new model object.</span></span> <span data-ttu-id="867f0-113">Для создания новой модели нужно использовать либо мастер, либо конструктор интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="867f0-113">To create a new model, you must use either the wizard, or the Data Mining Designer,.</span></span> <span data-ttu-id="867f0-114">Дополнительные сведения см. в разделе [Создание копии модели интеллектуального анализа данных](make-a-copy-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="867f0-114">For more information, see [Make a Copy of a Mining Model](make-a-copy-of-a-mining-model.md).</span></span>  
  
### <a name="to-copy-the-complete-model-to-the-clipboard"></a><span data-ttu-id="867f0-115">Копирование полной модели в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="867f0-115">To copy the complete model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="867f0-116">В списке **Модель интеллектуального анализа данных** на вкладке **Средство просмотра моделей интеллектуального анализа данных** выберите модель интеллектуального анализа данных, которую хотите посмотреть.</span><span class="sxs-lookup"><span data-stu-id="867f0-116">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="867f0-117">Перейдите на соответствующую вкладку, например **Сеть зависимостей** , и нажмите кнопку **Копировать весь граф** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="867f0-117">Select the appropriate tab, such as the **Dependency Network** tab, and then click **Copy Entire Graph** on the toolbar of that tab.</span></span>  
  
### <a name="to-copy-the-visible-piece-of-the-model-to-the-clipboard"></a><span data-ttu-id="867f0-118">Копирование видимой части модели в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="867f0-118">To copy the visible piece of the model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="867f0-119">В списке **Модель интеллектуального анализа данных** на вкладке **Средство просмотра моделей интеллектуального анализа данных** выберите модель интеллектуального анализа данных, которую хотите посмотреть.</span><span class="sxs-lookup"><span data-stu-id="867f0-119">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="867f0-120">Перейдите на соответствующую вкладку, например **Сеть зависимостей** , затем измените масштаб модели до требуемого уровня.</span><span class="sxs-lookup"><span data-stu-id="867f0-120">Select the appropriate tab, such as the **Dependency Network** tab, and then zoom in or out to view the model at the level that you want.</span></span>  
  
3.  <span data-ttu-id="867f0-121">Нажмите кнопку **Копировать представление графа** на панели инструментов выбранной вкладки.</span><span class="sxs-lookup"><span data-stu-id="867f0-121">Click **Copy Graph View** on the toolbar of the selected tab.</span></span>  
  
### <a name="to-copy-the-mining-model-content-to-the-clipboard"></a><span data-ttu-id="867f0-122">Копирование содержимого модели интеллектуального анализа данных в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="867f0-122">To copy the mining model content to the Clipboard</span></span>  
  
1.  <span data-ttu-id="867f0-123">В списке **Модель интеллектуального анализа данных** на вкладке **Средство просмотра моделей интеллектуального анализа данных** выберите модель интеллектуального анализа данных, которую хотите посмотреть.</span><span class="sxs-lookup"><span data-stu-id="867f0-123">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="867f0-124">Из раскрывающегося списка **Средство просмотра** выберите **Средство просмотра деревьев содержимого общего вида (Майкрософт)**.</span><span class="sxs-lookup"><span data-stu-id="867f0-124">From the **Viewer** drop-down list, select **Microsoft Generic Content Tree Viewer**.</span></span>  
  
3.  <span data-ttu-id="867f0-125">На панели **Заголовок узла (уникальный идентификатор)** щелкните узел.</span><span class="sxs-lookup"><span data-stu-id="867f0-125">In the **Node Caption (Unique ID)** pane, click a node.</span></span>  
  
4.  <span data-ttu-id="867f0-126">Щелкните правой кнопкой мыши панель **Сведения об узле** и выберите команду **Выделить все**.</span><span class="sxs-lookup"><span data-stu-id="867f0-126">Right-click the **Node Details** pane and then select **Select All**.</span></span>  
  
5.  <span data-ttu-id="867f0-127">Щелкните правой кнопкой мыши панель **Сведения об узле** повторно и выберите команду **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="867f0-127">Right-click the **Node Details** pane again and select **Copy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867f0-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="867f0-128">See Also</span></span>  
 [<span data-ttu-id="867f0-129">Задачи и инструкции средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="867f0-129">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
  
