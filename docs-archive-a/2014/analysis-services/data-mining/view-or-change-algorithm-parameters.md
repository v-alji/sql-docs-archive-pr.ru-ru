---
title: Просмотр или изменение параметров алгоритма | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- algorithms [data mining]
- mining models [Analysis Services], algorithms
ms.assetid: 151b899b-c27a-4a09-bcf5-5c9f0ec24168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30719cd50e0c473cf2aab5d9689d27dff4f26343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658533"
---
# <a name="view-or-change-algorithm-parameters"></a><span data-ttu-id="11457-102">Просмотр или изменение параметров алгоритма</span><span class="sxs-lookup"><span data-stu-id="11457-102">View or Change Algorithm Parameters</span></span>
  <span data-ttu-id="11457-103">Параметры алгоритма, используемого для построения моделей интеллектуального анализа данных, можно изменить для оптимизации результатов модели.</span><span class="sxs-lookup"><span data-stu-id="11457-103">You can change the parameters provided with the algorithms that you use to build data mining models to customize the results of the model.</span></span>  
  
 <span data-ttu-id="11457-104">Параметры алгоритма, предоставляемые в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , изменяют гораздо больше, чем просто свойства модели: они могут использоваться для фундаментального изменения способа обработки, группировки и отображения данных.</span><span class="sxs-lookup"><span data-stu-id="11457-104">The algorithm parameters provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] change much more than just properties on the model: they can be used to fundamentally alter the way that data is processed, grouped, and displayed.</span></span> <span data-ttu-id="11457-105">Например, параметры алгоритма можно использовать для выполнения следующих операций.</span><span class="sxs-lookup"><span data-stu-id="11457-105">For example, you can use algorithm parameters to do the following:</span></span>  
  
-   <span data-ttu-id="11457-106">Изменение метода анализа, например метода кластеризации.</span><span class="sxs-lookup"><span data-stu-id="11457-106">Change the method of analysis, such as the clustering method.</span></span>  
  
-   <span data-ttu-id="11457-107">Управление выбором компонентов.</span><span class="sxs-lookup"><span data-stu-id="11457-107">Control feature selection behavior.</span></span>  
  
-   <span data-ttu-id="11457-108">Указание размера наборов элементов или вероятности правил.</span><span class="sxs-lookup"><span data-stu-id="11457-108">Specify the size of itemsets or the probability of rules.</span></span>  
  
-   <span data-ttu-id="11457-109">Управление разветвлением и глубиной деревьев точности.</span><span class="sxs-lookup"><span data-stu-id="11457-109">Control branching and depth of decision trees.</span></span>  
  
-   <span data-ttu-id="11457-110">Указание начального значения или размера внутренней перегрузки во время создания модели.</span><span class="sxs-lookup"><span data-stu-id="11457-110">Specify a seed value or the size of the internal holdout set used for model creation.</span></span>  
  
 <span data-ttu-id="11457-111">Параметры сильно отличаются для каждого из алгоритмов. Список параметров, которые можно задать для каждого алгоритма, см. в технических справочниках в этом разделе: [Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="11457-111">The parameters provided for each algorithm vary greatly; for a list of the parameters that you can set for each algorithm, see the technical reference topics in this section: [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="change-an-algorithm-parameter"></a><span data-ttu-id="11457-112">Изменение параметров алгоритма</span><span class="sxs-lookup"><span data-stu-id="11457-112">Change an algorithm parameter</span></span>  
  
1.  <span data-ttu-id="11457-113">На вкладке **Модели интеллектуального анализа данных** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]щелкните правой кнопкой мыши тип алгоритма модели интеллектуального анализа, для которого необходимо настроить алгоритм, и выберите **Задать параметры алгоритма**.</span><span class="sxs-lookup"><span data-stu-id="11457-113">On the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the algorithm type of the mining model for which you want to tune the algorithm, and select **Set Algorithm Parameters**.</span></span>  
  
     <span data-ttu-id="11457-114">Откроется диалоговое окно **Параметры алгоритма** .</span><span class="sxs-lookup"><span data-stu-id="11457-114">The **Algorithm Parameters** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="11457-115">В столбце **Значение** задайте новое значение для алгоритма, который необходимо модифицировать.</span><span class="sxs-lookup"><span data-stu-id="11457-115">In the **Value** column, set a new value for the algorithm that you want to change.</span></span>  
  
     <span data-ttu-id="11457-116">Если значение в столбце **Значение** не введено, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] используют значение параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11457-116">If you do not enter a value in the **Value** column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses the default parameter value.</span></span> <span data-ttu-id="11457-117">В столбце **Диапазон** указаны допустимые для ввода значения.</span><span class="sxs-lookup"><span data-stu-id="11457-117">The **Range** column describes the possible values that you can enter.</span></span>  
  
3.  <span data-ttu-id="11457-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="11457-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="11457-119">Параметру алгоритма присваивается новое значение.</span><span class="sxs-lookup"><span data-stu-id="11457-119">The algorithm parameter is set with the new value.</span></span> <span data-ttu-id="11457-120">Изменение параметра не отразится на модели интеллектуального анализа данных до ее повторной обработки.</span><span class="sxs-lookup"><span data-stu-id="11457-120">The parameter change will not be reflected in the mining model until you reprocess the model.</span></span>  
  
### <a name="view-the-parameters-used-in-an-existing-model"></a><span data-ttu-id="11457-121">Просмотр параметров существующей модели</span><span class="sxs-lookup"><span data-stu-id="11457-121">View the parameters used in an existing model</span></span>  
  
1.  <span data-ttu-id="11457-122">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте окно DMX-запросов.</span><span class="sxs-lookup"><span data-stu-id="11457-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window.</span></span>  
  
2.  <span data-ttu-id="11457-123">Введите примерно следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="11457-123">Type a query like this one:</span></span>  
  
    ```  
    select MINING_PARAMETERS   
    from $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = '<model name>'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="11457-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="11457-124">See Also</span></span>  
 [<span data-ttu-id="11457-125">Задачи и инструкции по модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="11457-125">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
