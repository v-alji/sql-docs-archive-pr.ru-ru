---
title: Диалоговое окно «Определение сопоставления столбцов» (диаграмма точности интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.coltotablecolmapping.f1
ms.assetid: 68e9e2d2-173f-4363-a515-fc60bfee3af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ede835567f678f4152b3d1944f3c2c7160c6837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666784"
---
# <a name="specify-column-mapping-dialog-box-mining-accuracy-chart"></a><span data-ttu-id="6c0c9-102">Диалоговое окно «Указание сопоставления столбцов» (диаграмма точности интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="6c0c9-102">Specify Column Mapping Dialog Box (Mining Accuracy Chart)</span></span>
  <span data-ttu-id="6c0c9-103">Вкладка **Указание сопоставления столбцов** позволяет выбрать таблицы из внешнего источника данных и сопоставить столбцы с моделью интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-103">Use the **Specify Column Mapping** tab to select tables from an external data source and map the columns to a data mining model.</span></span> <span data-ttu-id="6c0c9-104">Затем с помощью внешних данных можно проверить точность модели интеллектуального анализа данных и представить результаты в диаграмме точности.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-104">You can then use the external data to test the accuracy of a mining model and displays the results in the accuracy chart.</span></span>  
  
 <span data-ttu-id="6c0c9-105">**Дополнительные сведения:** [Тестирование и проверка (интеллектуальный анализ данных)](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="6c0c9-105">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="6c0c9-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="6c0c9-106">Options</span></span>  
 <span data-ttu-id="6c0c9-107">**Структура интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="6c0c9-107">**Mining Structure**</span></span>  
 <span data-ttu-id="6c0c9-108">Показывает выбранную структуру интеллектуального анализа данных, в которых содержится модель, требующая проверки.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-108">Displays the selected mining structure that contains the model that you will test.</span></span>  
  
 <span data-ttu-id="6c0c9-109">**Выбор структуры**</span><span class="sxs-lookup"><span data-stu-id="6c0c9-109">**Select Structure**</span></span>  
 <span data-ttu-id="6c0c9-110">Нажмите, чтобы открыть диалоговое окно **Выбор структуры интеллектуального анализа данных** и выбрать другую структуру интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-110">Click to open the **Select Mining Structure** dialog box and select a different mining structure.</span></span>  
  
 <span data-ttu-id="6c0c9-111">**Выбор входных таблиц**</span><span class="sxs-lookup"><span data-stu-id="6c0c9-111">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="6c0c9-112">Показывает выбранные входные таблицы, используемые для формирования диаграммы точности прогнозов.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-112">Displays the selected input tables that are used to generate the lift chart.</span></span> <span data-ttu-id="6c0c9-113">Выберите таблицу, содержащую проверочные данные, которые будут использованы для проверки точности моделей.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-113">Select the table that contains the test data that you will use to test the accuracy of the models.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c0c9-114">Если панель не содержит никаких таблиц, нажмите кнопку **Выбрать таблицу вариантов** , чтобы добавить таблицы из представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-114">If the pane does not contain any tables, click **Select Case Table** to add tables from a data source view.</span></span>  
  
 <span data-ttu-id="6c0c9-115">**Удаление таблицы**</span><span class="sxs-lookup"><span data-stu-id="6c0c9-115">**Remove Table**</span></span>  
 <span data-ttu-id="6c0c9-116">Удаляет выбранную таблицу.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-116">Removes the selected table.</span></span> <span data-ttu-id="6c0c9-117">Эта кнопка отключена, если не было выбрано ни одной таблицы или если в списке **Выбор входных таблиц** не отображаются никакие таблицы.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-117">This button is disabled if a table has not been selected or if no tables are displayed in the **Select Input Tables** list.</span></span>  
  
 <span data-ttu-id="6c0c9-118">**Выбрать таблицу вариантов**</span><span class="sxs-lookup"><span data-stu-id="6c0c9-118">**Select Case Table**</span></span>  
 <span data-ttu-id="6c0c9-119">Нажмите, чтобы открыть диалоговое окно **Выбор таблицы** и выбрать представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-119">Click to open the **Select Table** dialog box and select a data source view.</span></span>  
  
 <span data-ttu-id="6c0c9-120">**Примечание.** Данная кнопка появляется, только если таблица вариантов не была выбрана.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-120">**Note** This button appears only if a case table has not been selected.</span></span> <span data-ttu-id="6c0c9-121">Чтобы включить кнопку и получить возможность выбрать другую таблицу вариантов, очистите список, выбрав все существующие таблицы и нажав кнопку **Удалить таблицу**.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-121">To enable the button so that you can select a different case table, clear the list by selecting all existing tables and then clicking **Remove Table**.</span></span>  
  
 <span data-ttu-id="6c0c9-122">**Выбор вложенной таблицы**</span><span class="sxs-lookup"><span data-stu-id="6c0c9-122">**Select Nested Table**</span></span>  
 <span data-ttu-id="6c0c9-123">Открывает диалоговое окно **Выбор таблицы** .</span><span class="sxs-lookup"><span data-stu-id="6c0c9-123">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="6c0c9-124">Данная кнопка появляется, только если была выбрана таблица вариантов.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-124">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="6c0c9-125">Если связанная структура интеллектуального анализа данных не содержит вложенной таблицы, данная кнопка отключена.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-125">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="6c0c9-126">**Изменить соединение**</span><span class="sxs-lookup"><span data-stu-id="6c0c9-126">**Modify Join**</span></span>  
 <span data-ttu-id="6c0c9-127">Открывает диалоговое окно **Определение вложенного соединения** .</span><span class="sxs-lookup"><span data-stu-id="6c0c9-127">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="6c0c9-128">Данная кнопка активна, только если выбрана вложенная таблица.</span><span class="sxs-lookup"><span data-stu-id="6c0c9-128">This button is active only if the nested table is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c0c9-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c0c9-129">See Also</span></span>  
 <span data-ttu-id="6c0c9-130">[Задачи тестирования и проверки и инструкции &#40;&#41;интеллектуального анализа данных](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6c0c9-130">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="6c0c9-131">Конструктор диаграмм точности интеллектуального анализа &#40;&#41;интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="6c0c9-131">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
