---
title: Алгоритмы интеллектуального анализа данных (SQL Server надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- segmentation
- data mining algorithms
- clustering [data mining]
- linear regression
- association [data mining]
- neural networks
- logistic regression
- regression
- sequence analysis
- decision tree [data mining]
- Naive Bayes
- time series [data mining]
ms.assetid: 3a1a62e4-9fb5-4cdb-a6c6-1b8b30d417ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3a73ce5a538756a740afd2db72d585fa54f03cae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667498"
---
# <a name="data-mining-algorithms-sql-server-data-mining-add-ins"></a><span data-ttu-id="3e474-102">Алгоритмы интеллектуального анализа данных (надстройки интеллектуального анализа данных SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3e474-102">Data Mining Algorithms (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="3e474-103">Надстройки интеллектуального анализа данных для Office поддерживают создание аналитических моделей с использованием следующих алгоритмов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="3e474-103">The Data Mining Add-ins for Office supports creation of analytical models using the following data mining algorithms.</span></span> <span data-ttu-id="3e474-104">Все алгоритмы основаны на широко известных методах машинного обучения и реализованы в Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="3e474-104">All algorithms are based on well-known machine learning methods and have been implemented by Microsoft Research.</span></span>  
  
## <a name="algorithms"></a><span data-ttu-id="3e474-105">Алгоритмы</span><span class="sxs-lookup"><span data-stu-id="3e474-105">Algorithms</span></span>  
  
|<span data-ttu-id="3e474-106">Метод машинного обучения</span><span class="sxs-lookup"><span data-stu-id="3e474-106">Machine learning method</span></span>|<span data-ttu-id="3e474-107">Принцип работы</span><span class="sxs-lookup"><span data-stu-id="3e474-107">How it works</span></span>|  
|-----------------------------|------------------|  
|<span data-ttu-id="3e474-108">Алгоритм правил взаимосвязей Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3e474-108">Microsoft Association Rules  algorithm</span></span>|<span data-ttu-id="3e474-109">Узнайте, какие продукты приобретены совместно или какие события произошли одновременно, и воспользуйтесь моделью для создания рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="3e474-109">Discover which products are purchased together or which events occur together, and use the model to create recommendations.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174916.aspx](https://msdn.microsoft.com/library/ms174916.aspx)|  
|<span data-ttu-id="3e474-110">Алгоритм кластеризации (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3e474-110">Microsoft Clustering algorithm</span></span>|<span data-ttu-id="3e474-111">Определяйте сегменты рынка, автоматически группируйте взаимосвязанных заказчиков или находите связи в данных для использования в дальнейшем интеллектуальном анализе.</span><span class="sxs-lookup"><span data-stu-id="3e474-111">Define market segments, automatically group related customers together, or find relationships in data to use in further mining.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174879.aspx](https://msdn.microsoft.com/library/ms174879.aspx)|  
|<span data-ttu-id="3e474-112">Алгоритм дерева принятия решений (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3e474-112">Microsoft Decision Trees algorithm</span></span>|<span data-ttu-id="3e474-113">Определяйте ранее неизвестные связи между различными элементами пользовательских данных для лучшего информационного обоснования своих решений или находите факторы, которые приводят к конкретным результатам.</span><span class="sxs-lookup"><span data-stu-id="3e474-113">Identify previously unknown relationships between various elements of your data to better inform your decisions, or find the factors that lead to specific outcomes.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
|<span data-ttu-id="3e474-114">Алгоритм линейной регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3e474-114">Microsoft Linear Regression algorithm</span></span>|<span data-ttu-id="3e474-115">Найдите математическую формулу, которая описывает факторы, влияющие на числовой результат.</span><span class="sxs-lookup"><span data-stu-id="3e474-115">Find a mathematical formula that describes factors that contribute to a numeric outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174824.aspx](https://msdn.microsoft.com/library/ms174824.aspx)|  
|<span data-ttu-id="3e474-116">Алгоритм логистической регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3e474-116">Microsoft Logistic Regression algorithm</span></span>|<span data-ttu-id="3e474-117">Идентифицируйте факторы, влияющие на двоичные результаты, и узнайте, как их использовать для воздействия на результаты.</span><span class="sxs-lookup"><span data-stu-id="3e474-117">Identify the factors that contribute to binary outcomes, and learn how to use those to affect results.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174828.aspx](https://msdn.microsoft.com/library/ms174828.aspx)|  
|<span data-ttu-id="3e474-118">Упрощенный алгоритм Байеса (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3e474-118">Microsoft Naïve Bayes algorithm</span></span>|<span data-ttu-id="3e474-119">Исследуйте связи в данных и находите среди них те, которые имеют наиболее тесную корреляцию с результатом.</span><span class="sxs-lookup"><span data-stu-id="3e474-119">Explore relationships in your data and find those mostly closely correlated with an outcome.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174806.aspx](https://msdn.microsoft.com/library/ms174806.aspx)|  
|<span data-ttu-id="3e474-120">Алгоритм нейронных сетей Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3e474-120">Microsoft Neural Networks algorithm</span></span>|<span data-ttu-id="3e474-121">Находите скрытые связи между несколькими входами и даже несколькими выходами.</span><span class="sxs-lookup"><span data-stu-id="3e474-121">Find hidden relationships among multiple inputs and even multiple outputs.</span></span> <span data-ttu-id="3e474-122">Используйте это для просмотра или для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="3e474-122">Use for exploration or for prediction.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174941.aspx](https://msdn.microsoft.com/library/ms174941.aspx)|  
|<span data-ttu-id="3e474-123">Алгоритм временных рядов (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3e474-123">Microsoft Time Series algorithm</span></span>|<span data-ttu-id="3e474-124">Используйте исторические данные для прогнозирования будущих значений.</span><span class="sxs-lookup"><span data-stu-id="3e474-124">Use historical data to forecast future values.</span></span><br /><br /> [https://msdn.microsoft.com/library/ms174923.aspx](https://msdn.microsoft.com/library/ms174923.aspx)|  
  
## <a name="advanced-options"></a><span data-ttu-id="3e474-125">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="3e474-125">Advanced Options</span></span>  
 <span data-ttu-id="3e474-126">При использовании клиента интеллектуального анализа данных для Excel можно создавать собственные структуры и модели интеллектуального анализа данных или тонко настраивать параметры алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="3e474-126">When you use the Data Mining Client for Excel, you have the option to create your own data mining structures and models, or to fine-tune the parameters of the algorithms.</span></span>  
  
 [<span data-ttu-id="3e474-127">Параметры алгоритма &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="3e474-127">Algorithm Parameters &#40;SQL Server Data Mining Add-ins&#41;</span></span>](algorithm-parameters-sql-server-data-mining-add-ins.md)  
  
 <span data-ttu-id="3e474-128">Предусмотрены два способа настройки модели с использованием следующих дополнительных параметров:</span><span class="sxs-lookup"><span data-stu-id="3e474-128">There are two ways to customize your models using these advanced options:</span></span>  
  
-   <span data-ttu-id="3e474-129">Используйте мастер **запросов интеллектуального анализа данных** для создания модели.</span><span class="sxs-lookup"><span data-stu-id="3e474-129">Use the **Data Mining Query** wizard to create your model.</span></span>  
  
-   <span data-ttu-id="3e474-130">В **клиенте интеллектуального анализа данных**после запуска мастера нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="3e474-130">In the **Data Mining Client**, after you start the wizard, click **Parameters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e474-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e474-131">See Also</span></span>  
 <span data-ttu-id="3e474-132">[&#40;запросов SQL Server надстройки интеллектуального анализа данных&#41;](query-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="3e474-132">[Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="3e474-133">Расширенное моделирование &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="3e474-133">Advanced Modeling &#40;Data Mining Add-ins for Excel&#41;</span></span>](advanced-modeling-data-mining-add-ins-for-excel.md)  
  
  
