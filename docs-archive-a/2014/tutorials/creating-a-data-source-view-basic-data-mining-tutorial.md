---
title: Создание представления источников данных (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1e68a88-0f82-415d-becc-78d180d4f845
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 4582845c905ef95601cbff2c810633f0cc901e3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658000"
---
# <a name="creating-a-data-source-view-basic-data-mining-tutorial"></a><span data-ttu-id="bd003-102">Создание представления источников данных (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="bd003-102">Creating a Data Source View (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="bd003-103">Представление источника данных основано на источнике данных, и в нем определяется подмножество данных, которые затем можно использовать в структурах интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="bd003-103">A data source view is built on a data source and defines a subset of the data, which you can then use in your mining structures.</span></span> <span data-ttu-id="bd003-104">Представление источника данных также можно использовать для добавления столбцов, создания вычисляемых столбцов и статистических выражений и добавления именованных представлений.</span><span class="sxs-lookup"><span data-stu-id="bd003-104">You can also use the data source view to add columns, create calculated columns and aggregates, and add named views.</span></span> <span data-ttu-id="bd003-105">Используя представления источников данных, можно выбирать данные, которые относятся к конкретному проекту, устанавливать связи между таблицами и менять структуру данных без изменения исходного источника данных.</span><span class="sxs-lookup"><span data-stu-id="bd003-105">By using data source views, you can select the data that relates to your project, establish relationships between tables, and modify the structure of the data, without modifying the original data source.</span></span> <span data-ttu-id="bd003-106">Дополнительные сведения см. в разделе [Представления источников данных в многомерных моделях](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span><span class="sxs-lookup"><span data-stu-id="bd003-106">For more information, see [Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span></span>  
  
### <a name="to-create-a-data-source-view"></a><span data-ttu-id="bd003-107">Создание представления источников данных</span><span class="sxs-lookup"><span data-stu-id="bd003-107">To create a data source view</span></span>  
  
1.  <span data-ttu-id="bd003-108">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **представления источников данных**и выберите пункт **создать представление источника данных**.</span><span class="sxs-lookup"><span data-stu-id="bd003-108">In **Solution Explorer**, right-click **Data Source Views**, and select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="bd003-109">На странице **Мастер представления источника данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bd003-109">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="bd003-110">На странице **Выбор источника данных** в разделе **реляционные источники данных**выберите источник данных Adventure Works DW 2012, созданный в последней задаче.</span><span class="sxs-lookup"><span data-stu-id="bd003-110">On the **Select a Data Source** page, under **Relational data sources**, select the Adventure Works DW 2012 data source that you created in the last task.</span></span> <span data-ttu-id="bd003-111">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bd003-111">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bd003-112">Если необходимо создать источник данных, щелкните правой кнопкой мыши элемент **Источники данных** и выберите команду **создать источник данных** , чтобы запустить мастер источников данных.</span><span class="sxs-lookup"><span data-stu-id="bd003-112">If you want to create a data source, right-click **Data Sources** and then click **New Data Source** to start the Data Source Wizard.</span></span>  
  
4.  <span data-ttu-id="bd003-113">На странице **Выбор таблиц и представлений** выберите следующие объекты, а затем щелкните стрелку вправо, чтобы включить их в новое представление источника данных:</span><span class="sxs-lookup"><span data-stu-id="bd003-113">On the **Select Tables and Views** page, select the following objects, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   <span data-ttu-id="bd003-114">**ProspectiveBuyer (dbo)** — таблица покупателей потенциальных велосипедов</span><span class="sxs-lookup"><span data-stu-id="bd003-114">**ProspectiveBuyer (dbo)** - table of prospective bike buyers</span></span>  
  
    -   <span data-ttu-id="bd003-115">**vTargetMail (dbo)** — Просмотр исторических данных о последних покупателях велосипедов</span><span class="sxs-lookup"><span data-stu-id="bd003-115">**vTargetMail (dbo)** - view of historical data about past bike buyers</span></span>  
  
5.  <span data-ttu-id="bd003-116">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bd003-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="bd003-117">На странице **Завершение работы мастера** по умолчанию представление источника данных называется Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="bd003-117">On the **Completing the Wizard** page, by default the data source view is named Adventure Works DW 2012.</span></span> <span data-ttu-id="bd003-118">Измените имя на `Targeted Mailing` , а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bd003-118">Change the name to `Targeted Mailing`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="bd003-119">Новое представление источника данных откроется на вкладке **Целевая рассылка. DSV [Design]** .</span><span class="sxs-lookup"><span data-stu-id="bd003-119">The new data source view opens in the **Targeted Mailing.dsv [Design]** tab.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="bd003-120">Предыдущая задача занятия</span><span class="sxs-lookup"><span data-stu-id="bd003-120">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="bd003-121">Учебник по созданию источника данных &#40;Basic Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="bd003-121">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="bd003-122">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="bd003-122">Next Lesson</span></span>  
 [<span data-ttu-id="bd003-123">Занятие 2. Создание структуры целевой рассылки &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="bd003-123">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="bd003-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd003-124">See Also</span></span>  
 [<span data-ttu-id="bd003-125">Определение представления источников данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="bd003-125">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/defining-a-data-source-view-analysis-services)  
  
  
