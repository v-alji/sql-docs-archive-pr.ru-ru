---
title: Просмотр моделей в Excel (SQL Server надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- browse models
- mining models, viewing
ms.assetid: a8cca1d7-602a-449a-875c-99da564965bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: c992f1f61112478a85276b6596da0137ccd5c9be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656809"
---
# <a name="browsing-models-in-excel-sql-server-data-mining-add-ins"></a><span data-ttu-id="da177-102">Просмотр моделей в Excel (надстройки интеллектуального анализа данных для SQL Server)</span><span class="sxs-lookup"><span data-stu-id="da177-102">Browsing Models in Excel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="da177-103">![Кнопка «Обзор моделей» на ленте «Интеллектуальный анализ данных»](media/dmc-browse.gif "Кнопка «Обзор моделей» на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="da177-103">![Browse Model button in Data Mining ribbon](media/dmc-browse.gif "Browse Model button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="da177-104">Визуальное исследование модели обычно является самым быстрым и простым способом понять правила и отношения, выявленные при помощи анализа.</span><span class="sxs-lookup"><span data-stu-id="da177-104">Visually exploring the model is usually the fastest and easiest way to get an understanding of the rules and relationships discovered by analysis.</span></span> <span data-ttu-id="da177-105">С помощью клиента интеллектуального анализа данных для Excel можно просмотреть временные модели, созданные во время текущего сеанса Excel и модели, хранящихся в экземпляре [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da177-105">By using the Data Mining Client for Excel, you can browse both temporary models created during the current Excel session, and models stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="da177-106">Чтобы просмотреть модель, следует выбрать модель и связанную с ней структуру из списка доступных моделей, при этом надстройка автоматически выберет средство просмотра, соответствующее алгоритму интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="da177-106">To browse a model, you select a model and its associated structure from a list of available models, and the add-in automatically picks the viewer that is appropriate for that data mining algorithm.</span></span> <span data-ttu-id="da177-107">Можно выполнить детализацию наиболее интересных тенденций, отфильтровать завершенную модель интеллектуального анализа данных и копировать графики и данные в Excel или в Visio.</span><span class="sxs-lookup"><span data-stu-id="da177-107">You can drill into the most interesting trends, filter the completed data mining model, and copy graphs and data to Excel or to Visio.</span></span>  
  
## <a name="using-the-browse-model-wizard"></a><span data-ttu-id="da177-108">Использование мастера выбора модели</span><span class="sxs-lookup"><span data-stu-id="da177-108">Using the Browse Model Wizard</span></span>  
  
1.  <span data-ttu-id="da177-109">Перейдите на вкладку **интеллектуальный анализ данных** .</span><span class="sxs-lookup"><span data-stu-id="da177-109">Click the **Data Mining** tab.</span></span>  
  
2.  <span data-ttu-id="da177-110">В группе **Использование модели** нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="da177-110">In the **Model Usage** group, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="da177-111">В диалоговом окне **Выбор модели** выберите модель интеллектуального анализа данных из списка и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da177-111">In the **Select Model** dialog box, choose a mining model from the list, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="da177-112">Мастер откроет окно **обзора** , которое подходит для выбранного типа модели.</span><span class="sxs-lookup"><span data-stu-id="da177-112">The wizard opens a **Browse** window that is appropriate for the type of model that you selected.</span></span>  
  
## <a name="list-of-data-mining-viewers"></a><span data-ttu-id="da177-113">Список средств просмотра интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="da177-113">List of Data Mining Viewers</span></span>  
 <span data-ttu-id="da177-114">В зависимости от алгоритма интеллектуального анализа данных, который использовался при создании модели, окно **Обзор** будет выглядеть немного иначе.</span><span class="sxs-lookup"><span data-stu-id="da177-114">Depending on the data mining algorithm that you used when you created the model, the **Browse** window will look a bit different.</span></span> <span data-ttu-id="da177-115">Оно может содержать диаграммы, улучшающие восприятие результатов, условные обозначения, которые содержат дополнительные сведения и элементы управления для взаимодействия с данными.</span><span class="sxs-lookup"><span data-stu-id="da177-115">It can include graphs to help interpret the results, legends that contain additional detail, and controls for interacting with the data.</span></span>  
  
 <span data-ttu-id="da177-116">Следующие разделы содержат руководство по применению каждого из средств просмотра, включая советы по анализу сложных диаграмм, а также по обработке результатов, их изменению и копированию.</span><span class="sxs-lookup"><span data-stu-id="da177-116">The following topics provide guidance in how to use each of the viewers, including tips on interpreting the complex graphs, and how to change, copy, or work with the results.</span></span>  
  
 [<span data-ttu-id="da177-117">Просмотр модели правил взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="da177-117">Browsing an Association Rules Model</span></span>](browsing-an-association-rules-model.md)  
  
 [<span data-ttu-id="da177-118">Просмотр модели кластеризации</span><span class="sxs-lookup"><span data-stu-id="da177-118">Browsing a Clustering Model</span></span>](browsing-a-clustering-model.md)  
  
 [<span data-ttu-id="da177-119">Просмотр модели дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="da177-119">Browsing a Decision Trees Model</span></span>](browsing-a-decision-trees-model.md)  
  
 [<span data-ttu-id="da177-120">Просмотр модели прогнозов</span><span class="sxs-lookup"><span data-stu-id="da177-120">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
 [<span data-ttu-id="da177-121">Обзор модели упрощенного алгоритма Байеса</span><span class="sxs-lookup"><span data-stu-id="da177-121">Browsing a Naive Bayes Model</span></span>](browsing-a-naive-bayes-model.md)  
  
 [<span data-ttu-id="da177-122">Просмотр модели нейронной сети</span><span class="sxs-lookup"><span data-stu-id="da177-122">Browsing a Neural Network Model</span></span>](browsing-a-neural-network-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="da177-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="da177-123">See Also</span></span>  
 <span data-ttu-id="da177-124">[Просмотр моделей интеллектуального анализа данных в Visio &#40;надстройки интеллектуального анализа данных&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="da177-124">[Viewing Data Mining Models in Visio &#40;Data Mining Add-ins&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="da177-125">Управление моделями &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="da177-125">Manage Models &#40;SQL Server Data Mining Add-ins&#41;</span></span>](manage-models-sql-server-data-mining-add-ins.md)  
  
  
