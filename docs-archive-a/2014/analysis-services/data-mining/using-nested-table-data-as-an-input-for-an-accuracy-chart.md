---
title: Использование данных вложенной таблицы в качестве входных для диаграммы точности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], nested tables
- Mining Accuracy Chart [Analysis Services], input tables
- nested tables
- adding nested tables
ms.assetid: 162e0686-ada3-4dd3-9151-9589926e6613
author: minewiskan
ms.author: owend
ms.openlocfilehash: 97d5bbd75d09b1a9e4276c4723ad6986dbabf9e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654590"
---
# <a name="using-nested-table-data-as-an-input-for-an-accuracy-chart"></a><span data-ttu-id="5ec56-102">Использование данных вложенной таблицы в качестве входных для диаграммы точности</span><span class="sxs-lookup"><span data-stu-id="5ec56-102">Using Nested Table Data as an Input for an Accuracy Chart</span></span>
  <span data-ttu-id="5ec56-103">Если при проверке точности модели интеллектуального анализа данных на внешних данных модель интеллектуального анализа содержит вложенные таблицы, то внешние данные также должны содержать таблицу вариантов и связанную с ней вложенную таблицу.</span><span class="sxs-lookup"><span data-stu-id="5ec56-103">When you test the accuracy of a mining model by using external data, if the mining model contains nested tables, the external data must also contain a case table and an associated nested table.</span></span>  
  
 <span data-ttu-id="5ec56-104">В этом разделе описана работа с вложенными таблицами, используемыми для проверки моделей, сопоставление вложенных таблиц и таблиц вариантов в режиме и во внешних данных, а также применение фильтра к вложенной таблице.</span><span class="sxs-lookup"><span data-stu-id="5ec56-104">This topic describes how to work with nested tables used for model testing, how to map nested and case tables in the mode and in the external data, and how to apply a filter to a nested table.</span></span>  
  
 <span data-ttu-id="5ec56-105">Следующие советы могут помочь при работе с вложенными таблицами.</span><span class="sxs-lookup"><span data-stu-id="5ec56-105">When working with nested tables, keep in mind these tips:</span></span>  
  
-   <span data-ttu-id="5ec56-106">При выборе параметра **Использовать проверочные варианты модели интеллектуального анализа данных** или **Использовать проверочные варианты структуры интеллектуального анализа данных**задавать таблицу вариантов или вложенную таблицу необязательно.</span><span class="sxs-lookup"><span data-stu-id="5ec56-106">If you select the option **Use mining model test cases** or **Use mining structure test cases**, you do not need to specify a case table or nested table.</span></span> <span data-ttu-id="5ec56-107">Если выбран один из этих параметров, определение проверочных данных хранится в структуре интеллектуального анализа данных и проверочные данные выбираются автоматически при создании диаграммы точности.</span><span class="sxs-lookup"><span data-stu-id="5ec56-107">With those options, the definition of the test data is stored in the mining structure and the test data is automatically selected when you create the accuracy chart.</span></span>  
  
-   <span data-ttu-id="5ec56-108">Если в источнике данных уже существует связь между вариантом и вложенной таблицей, то столбцы в структуре интеллектуального анализа данных автоматически сопоставляются со столбцами, имеющими то же имя во входной таблице.</span><span class="sxs-lookup"><span data-stu-id="5ec56-108">If a relationship already exists between the case and nested table in the data source, the columns in the mining structure are automatically mapped to the columns that have the same name in the input table.</span></span>  
  
-   <span data-ttu-id="5ec56-109">Вложенную таблицу нельзя добавить до тех пор, пока не задана таблица вариантов.</span><span class="sxs-lookup"><span data-stu-id="5ec56-109">You cannot select a nested table until you have specified the case table.</span></span> <span data-ttu-id="5ec56-110">Кроме того, вложенную таблицу нельзя добавить в качестве входных данных до тех пор, пока модель интеллектуального анализа данных использует таблицу вариантов и вложенную таблицу.</span><span class="sxs-lookup"><span data-stu-id="5ec56-110">Also, you cannot specify a nested table as an input unless the mining model also uses a case table and nested table structure.</span></span>  
  
### <a name="use-a-nested-table-as-input-to-an-accuracy-chart"></a><span data-ttu-id="5ec56-111">Использование вложенной таблицы в качестве входных данных для диаграммы точности</span><span class="sxs-lookup"><span data-stu-id="5ec56-111">Use a nested table as input to an accuracy chart</span></span>  
  
1.  <span data-ttu-id="5ec56-112">Дважды щелкните структуру интеллектуального анализа данных, чтобы открыть ее в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5ec56-112">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="5ec56-113">Перейдите на вкладку **Диаграмма точности интеллектуального анализа** , а затем на вкладку **Выбор входных данных** .</span><span class="sxs-lookup"><span data-stu-id="5ec56-113">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="5ec56-114">Выберите параметр **Задать другой набор данных**в области **Выбор набора данных для диаграммы точности**.</span><span class="sxs-lookup"><span data-stu-id="5ec56-114">In **Select data set to be used for accuracy chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="5ec56-115">Нажмите кнопку обзора **(...)** , чтобы выбрать внешний набор данных из списка представлений источников данных на текущем сервере.</span><span class="sxs-lookup"><span data-stu-id="5ec56-115">Click the browse button **(...)** to choose the external data set from a list of data source views on the current server.</span></span>  
  
5.  <span data-ttu-id="5ec56-116">Щелкните **Выбор таблицы вариантов**.</span><span class="sxs-lookup"><span data-stu-id="5ec56-116">Click **Select Case Table**.</span></span> <span data-ttu-id="5ec56-117">В диалоговом окне **Выбор таблицы** выберите из представления источников данных таблицу, содержащую данные варианта, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5ec56-117">In the **Select Table** dialog box, choose the table from the data source view that contains the case data, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="5ec56-118">Щелкните **Выбор вложенной таблицы**.</span><span class="sxs-lookup"><span data-stu-id="5ec56-118">Click **Select Nested Table**.</span></span> <span data-ttu-id="5ec56-119">В диалоговом окне **Выбор таблицы** выберите таблицу, которая содержит вложенные данные, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5ec56-119">In the **Select Table** dialog box, select the table that contains the nested data, and then click **OK**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="5ec56-120">Если необходимо изменить связь между вложенной таблицей и таблицей вариантов, нажмите кнопку **Изменить соединение** , после чего откроется диалоговое окно **Создание связи** .</span><span class="sxs-lookup"><span data-stu-id="5ec56-120">If you need to modify the relationship between the nested table and the case table, click **Modify Join** to open the **Create Relationship** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec56-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ec56-121">See Also</span></span>  
 <span data-ttu-id="5ec56-122">[Выбор и сопоставьте данные тестирования модели](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="5ec56-122">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="5ec56-123">Применение фильтров к данным проверки модели</span><span class="sxs-lookup"><span data-stu-id="5ec56-123">Apply Filters to Model Testing Data</span></span>](apply-filters-to-model-testing-data.md)  
  
  
