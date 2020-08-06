---
title: Панель запросов (представление прогноза модели интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.query.f1
ms.assetid: fdeec72e-d0bd-4453-9eaa-46436e4d6edc
author: minewiskan
ms.author: owend
ms.openlocfilehash: e17a27190891ea9e00be21d5013d0767d61ac148
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657960"
---
# <a name="query-pane-mining-model-prediction-view"></a><span data-ttu-id="89cc8-102">Панель запросов (представление прогноза модели интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="89cc8-102">Query Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="89cc8-103">Панель **Запрос** отображает инструкции выражений интеллектуального анализа данных, созданные в построителе прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="89cc8-103">The **Query** pane displays the Data Mining Expressions (DMX) statements created by Prediction Query Builder.</span></span> <span data-ttu-id="89cc8-104">Можно изменить инструкции и затем нажать кнопку **Переключиться в режим просмотра результата запроса** для возврата результатов.</span><span class="sxs-lookup"><span data-stu-id="89cc8-104">You can modify the statements and then click the **Switch to query result view** button to return the results.</span></span> <span data-ttu-id="89cc8-105">Если переключиться обратно на представление **Проект** , то любые произведенные изменения инструкций будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="89cc8-105">If you switch back to the **Design** view, any changes you made to the statement will be lost.</span></span>  
  
 <span data-ttu-id="89cc8-106">**Дополнительные сведения:** [Инструкции управления данными расширений интеллектуального анализа данных](/sql/dmx/dmx-statements-data-manipulation), [Создание DMX-запроса в среде SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="89cc8-106">**For More Information:** [Data Mining Extensions &#40;DMX&#41; Data Manipulation Statements](/sql/dmx/dmx-statements-data-manipulation), [Create a DMX Query in SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="89cc8-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="89cc8-107">Options</span></span>  
 <span data-ttu-id="89cc8-108">**Переключиться в режим просмотра результата запроса**</span><span class="sxs-lookup"><span data-stu-id="89cc8-108">**Switch to query result view**</span></span>  
 <span data-ttu-id="89cc8-109">Для переключения между панелями щелкните **Проект**, **Запрос**и **Результат** .</span><span class="sxs-lookup"><span data-stu-id="89cc8-109">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="89cc8-110">При переключении на панель **Результат** происходит выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="89cc8-110">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="89cc8-111">**Сохранить результат запроса**</span><span class="sxs-lookup"><span data-stu-id="89cc8-111">**Save the query result**</span></span>  
 <span data-ttu-id="89cc8-112">Открывает диалоговое окно **Сохранение результата запроса интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="89cc8-112">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="89cc8-113">**Одноэлементный запрос**</span><span class="sxs-lookup"><span data-stu-id="89cc8-113">**Singleton query**</span></span>  
 <span data-ttu-id="89cc8-114">Позволяет создать одноэлементный запрос, в котором входные данные будут вводиться прямо в запрос вместо предоставления ссылок на таблицу входных значений.</span><span class="sxs-lookup"><span data-stu-id="89cc8-114">Lets you create a singleton query, in which you provide the input data directly in your query instead of providing a reference to a table of input values.</span></span> <span data-ttu-id="89cc8-115">Таблица **Выбор входных таблиц** заменяется таблицей **Ввод одноэлементного запроса** .</span><span class="sxs-lookup"><span data-stu-id="89cc8-115">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span> <span data-ttu-id="89cc8-116">Текущий прогнозирующий запрос будет потерян при переключении в режим одноэлементного запроса.</span><span class="sxs-lookup"><span data-stu-id="89cc8-116">The current prediction query will be lost if you switch to a singleton query.</span></span>  
  
 <span data-ttu-id="89cc8-117">**Обновить результаты запроса**</span><span class="sxs-lookup"><span data-stu-id="89cc8-117">**Refresh query results**</span></span>  
 <span data-ttu-id="89cc8-118">Обработать заново прогнозирующий запрос.</span><span class="sxs-lookup"><span data-stu-id="89cc8-118">Reprocesses the prediction query.</span></span> <span data-ttu-id="89cc8-119">Это возможно только на панели **Результат** .</span><span class="sxs-lookup"><span data-stu-id="89cc8-119">This is enabled only in the **Result** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89cc8-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="89cc8-120">See Also</span></span>  
 <span data-ttu-id="89cc8-121">[Интерфейсы запросов интеллектуального анализа данных](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="89cc8-121">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 <span data-ttu-id="89cc8-122">[Расширения интеллектуального анализа данных &#40;Справочник по инструкции DMX&#41;](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="89cc8-122">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 [<span data-ttu-id="89cc8-123">Построитель прогнозирующих запросов (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="89cc8-123">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
