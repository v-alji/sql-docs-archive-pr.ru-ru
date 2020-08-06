---
title: Запрос интеллектуального анализа данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquery.f1
ms.assetid: 948e358a-6245-429f-82c7-4cedc5e048fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 657e4e173815fa25458e296f7eadb3d4d0696a02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665073"
---
# <a name="data-mining-query"></a><span data-ttu-id="7f8af-102">Запрос интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="7f8af-102">Data Mining Query</span></span>
  <span data-ttu-id="7f8af-103">Панель конструктора содержит построитель прогнозирующих запросов интеллектуального анализа данных, который можно использовать для построения прогнозирующих запросов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7f8af-103">The design pane contains the data mining prediction query builder, which you can use to build data mining prediction queries.</span></span> <span data-ttu-id="7f8af-104">Можно строить либо прогнозирующие запросы на основании входных таблиц, либо одноэлементные прогнозирующие запросы.</span><span class="sxs-lookup"><span data-stu-id="7f8af-104">You can design either prediction queries based on input tables, or singleton prediction queries.</span></span> <span data-ttu-id="7f8af-105">Переключитесь в просмотр результата, чтобы запустить запрос и просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="7f8af-105">Switch to the result view to run the query and view the results.</span></span> <span data-ttu-id="7f8af-106">Просмотр запроса отображает запрос расширения интеллектуального анализа данных, созданный построителем прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="7f8af-106">The query view displays the Data Mining Extensions (DMX) query created by the prediction query builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f8af-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f8af-107">Options</span></span>  
 <span data-ttu-id="7f8af-108">Кнопка переключения представлений</span><span class="sxs-lookup"><span data-stu-id="7f8af-108">Switch view button</span></span>  
 <span data-ttu-id="7f8af-109">Для переключения между панелями конструирования и запросов щелкните значок.</span><span class="sxs-lookup"><span data-stu-id="7f8af-109">Click an icon to switch between the design and query pane.</span></span> <span data-ttu-id="7f8af-110">По умолчанию открыта панель конструирования.</span><span class="sxs-lookup"><span data-stu-id="7f8af-110">By default, the design pane is open.</span></span>  
  
 <span data-ttu-id="7f8af-111">Для переключения на панель конструктора щелкните значок ![значок конструктора](../media/ssis-designicon.gif "Значок конструктора").</span><span class="sxs-lookup"><span data-stu-id="7f8af-111">To switch to the design pane, click the ![Design icon](../media/ssis-designicon.gif "Design icon") icon.</span></span>  
  
 <span data-ttu-id="7f8af-112">Для переключения на панель запросов щелкните значок ![значок SQL](../media/ssis-queryicon.gif "Значок SQL").</span><span class="sxs-lookup"><span data-stu-id="7f8af-112">To switch to the query pane, click the ![SQL icon](../media/ssis-queryicon.gif "SQL icon") icon.</span></span>  
  
 <span data-ttu-id="7f8af-113">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="7f8af-113">**Mining Model**</span></span>  
 <span data-ttu-id="7f8af-114">Отображает выбранную модель интеллектуального анализа данных, на основе которой будет производиться прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="7f8af-114">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="7f8af-115">**Выбрать модель**</span><span class="sxs-lookup"><span data-stu-id="7f8af-115">**Select Model**</span></span>  
 <span data-ttu-id="7f8af-116">Открывает диалоговое окно **Выбор модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="7f8af-116">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="7f8af-117">**Входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="7f8af-117">**Input Columns**</span></span>  
 <span data-ttu-id="7f8af-118">Отображает выбранные входные столбцы, используемые при формировании прогноза.</span><span class="sxs-lookup"><span data-stu-id="7f8af-118">Displays the selected input columns used to generate the predictions.</span></span>  
  
 <span data-ttu-id="7f8af-119">**Source**</span><span class="sxs-lookup"><span data-stu-id="7f8af-119">**Source**</span></span>  
 <span data-ttu-id="7f8af-120">Из раскрывающегося списка выберите источник, содержащий поле, которое надо использовать для столбца.</span><span class="sxs-lookup"><span data-stu-id="7f8af-120">Select the source containing the field that you will use for the column from the dropdown list.</span></span> <span data-ttu-id="7f8af-121">Можно использовать либо модель интеллектуального анализа данных, выбранную в таблице **Модель интеллектуального анализа данных** , входные таблицы, выбранные в таблице **Выбор входных таблиц** , либо функцию предсказания, либо пользовательское выражение.</span><span class="sxs-lookup"><span data-stu-id="7f8af-121">You can either use the mining model selected in the **Mining Model** table, the input table(s) selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="7f8af-122">В ячейку можно перетаскивать столбцы из таблиц, содержащих модели интеллектуального анализа данных, а также входные столбцы.</span><span class="sxs-lookup"><span data-stu-id="7f8af-122">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
 <span data-ttu-id="7f8af-123">**Поле**</span><span class="sxs-lookup"><span data-stu-id="7f8af-123">**Field**</span></span>  
 <span data-ttu-id="7f8af-124">Выберите столбец из списка столбцов, полученного из исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="7f8af-124">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="7f8af-125">Если в поле **Источник** была выбрана **Прогнозирующая функция**, данная ячейка будет содержать раскрывающийся список функций прогнозирования, доступных для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7f8af-125">If you selected **Prediction Function** in **Source**, this cell contains a drop-down list of the prediction functions available for the selected mining model.</span></span>  
  
 <span data-ttu-id="7f8af-126">**Псевдоним**</span><span class="sxs-lookup"><span data-stu-id="7f8af-126">**Alias**</span></span>  
 <span data-ttu-id="7f8af-127">Имя столбца, возвращаемое сервером.</span><span class="sxs-lookup"><span data-stu-id="7f8af-127">The name of the column returned by the server.</span></span>  
  
 <span data-ttu-id="7f8af-128">**Показать**</span><span class="sxs-lookup"><span data-stu-id="7f8af-128">**Show**</span></span>  
 <span data-ttu-id="7f8af-129">Выберите, чтобы возвратить столбец или только использовать столбец в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="7f8af-129">Select to return the column or to only use the column in the WHERE clause.</span></span>  
  
 <span data-ttu-id="7f8af-130">**Группирование**</span><span class="sxs-lookup"><span data-stu-id="7f8af-130">**Group**</span></span>  
 <span data-ttu-id="7f8af-131">Используйте со столбцом **И/ИЛИ** для группирования выражений.</span><span class="sxs-lookup"><span data-stu-id="7f8af-131">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="7f8af-132">Например (выражение1 ИЛИ выражение2) И выражение3.</span><span class="sxs-lookup"><span data-stu-id="7f8af-132">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="7f8af-133">**и/или**</span><span class="sxs-lookup"><span data-stu-id="7f8af-133">**And/Or**</span></span>  
 <span data-ttu-id="7f8af-134">Используйте для создания логического запроса.</span><span class="sxs-lookup"><span data-stu-id="7f8af-134">Use to create a logical query.</span></span> <span data-ttu-id="7f8af-135">Например (выражение1 ИЛИ выражение2) И выражение3.</span><span class="sxs-lookup"><span data-stu-id="7f8af-135">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="7f8af-136">**Критерий/Аргумент**</span><span class="sxs-lookup"><span data-stu-id="7f8af-136">**Criteria/Argument**</span></span>  
 <span data-ttu-id="7f8af-137">Задайте условие или пользовательское выражение, применимое к столбцу.</span><span class="sxs-lookup"><span data-stu-id="7f8af-137">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="7f8af-138">В ячейку можно перетаскивать столбцы из таблиц, содержащих модели интеллектуального анализа данных, а также входные столбцы.</span><span class="sxs-lookup"><span data-stu-id="7f8af-138">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f8af-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f8af-139">See Also</span></span>  
 <span data-ttu-id="7f8af-140">[Интерфейсы запросов интеллектуального анализа данных](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span><span class="sxs-lookup"><span data-stu-id="7f8af-140">[Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span></span>  
 [<span data-ttu-id="7f8af-141">Справочник по расширениям интеллектуального анализа данных (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="7f8af-141">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
