---
title: Диалоговое окно «Сохранение результата запроса интеллектуального анализа данных» (представление прогноза модели интеллектуального анализа) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dm.savedataminingqueryresult.f1
helpviewer_keywords:
- Save Data Mining Query Result dialog box
ms.assetid: 112fb527-7466-4fd4-9cf1-75596135648f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0838c90f0797a0db9c8a66cd8c5f877aaecdad0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656637"
---
# <a name="save-data-mining-query-result-dialog-box-mining-model-prediction-view"></a><span data-ttu-id="5f890-102">Диалоговое окно «Сохранение результатов запроса интеллектуального анализа данных» (представление прогноза модели интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="5f890-102">Save Data Mining Query Result Dialog Box (Mining Model Prediction View)</span></span>
  <span data-ttu-id="5f890-103">Диалоговое окно **Сохранение результата запроса интеллектуального анализа данных** позволяет сохранить результаты запроса интеллектуального анализа в новой таблице.</span><span class="sxs-lookup"><span data-stu-id="5f890-103">Use the **Save Data Mining Query Result** dialog box to save the results of a data mining query to a new table.</span></span>  
  
 <span data-ttu-id="5f890-104">Новая таблица будет создана в базе данных, которая определяется источником данных.</span><span class="sxs-lookup"><span data-stu-id="5f890-104">The new table will be created in the database defined by the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5f890-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="5f890-105">Options</span></span>  
 <span data-ttu-id="5f890-106">**Источник данных**</span><span class="sxs-lookup"><span data-stu-id="5f890-106">**Data Source**</span></span>  
 <span data-ttu-id="5f890-107">Выберите источник данных для текущего проекта.</span><span class="sxs-lookup"><span data-stu-id="5f890-107">Select a data source from the current project.</span></span> <span data-ttu-id="5f890-108">Если требуемый источник данных не существует, нажмите кнопку **Создать** , чтобы создать новый источник данных.</span><span class="sxs-lookup"><span data-stu-id="5f890-108">If the correct data source does not exist, click **New** to create a new data source.</span></span>  
  
 <span data-ttu-id="5f890-109">**Создать**</span><span class="sxs-lookup"><span data-stu-id="5f890-109">**New**</span></span>  
 <span data-ttu-id="5f890-110">Открывает **Мастер источников данных**.</span><span class="sxs-lookup"><span data-stu-id="5f890-110">Opens the **Data Source Wizard**.</span></span>  
  
 <span data-ttu-id="5f890-111">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="5f890-111">**Table Name**</span></span>  
 <span data-ttu-id="5f890-112">Введите имя новой таблицы.</span><span class="sxs-lookup"><span data-stu-id="5f890-112">Type a name for the new table.</span></span>  
  
 <span data-ttu-id="5f890-113">**Переписать, если существует**</span><span class="sxs-lookup"><span data-stu-id="5f890-113">**Overwrite if exists**</span></span>  
 <span data-ttu-id="5f890-114">Выберите этот параметр, если нужно перезаписать существующую таблицу с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="5f890-114">Select this option if you want to overwrite an existing table with the same name.</span></span>  
  
 <span data-ttu-id="5f890-115">Необходимо перезаписать существующую таблицу, если выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="5f890-115">Overwriting the existing table is required if any of the following is true:</span></span>  
  
-   <span data-ttu-id="5f890-116">Добавлены столбцы прогнозирующего запроса.</span><span class="sxs-lookup"><span data-stu-id="5f890-116">You added columns to the prediction query.</span></span>  
  
-   <span data-ttu-id="5f890-117">Изменены имена или типы данных любых столбцов в прогнозирующем запросе.</span><span class="sxs-lookup"><span data-stu-id="5f890-117">You changed the names or data types of any columns in the prediction query.</span></span>  
  
-   <span data-ttu-id="5f890-118">Выполнена инструкция ALTER для целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="5f890-118">You ran an ALTER statement on the destination table.</span></span>  
  
 <span data-ttu-id="5f890-119">Если несколько столбцов имеют одно и то же имя (например, несколько производных столбцов могут содержать столбец с именем по умолчанию **Выражение**), необходимо создать псевдоним для каждого столбца с повторяющимися именами.</span><span class="sxs-lookup"><span data-stu-id="5f890-119">If multiple columns have the same name (for example, several derived columns might have the default column name **Expression**), you must create an alias for each column with a duplicate name.</span></span> <span data-ttu-id="5f890-120">Если у столбцов нет уникальных имен, при попытке конструктора сохранить результаты в SQL Server возникнет ошибка, так как столбцы в таблице должны иметь уникальные имена.</span><span class="sxs-lookup"><span data-stu-id="5f890-120">If the columns do not have unique names, an error will be raised when the designer tries to save the results to SQL Server, because columns in a table must have unique names.</span></span>  
  
 <span data-ttu-id="5f890-121">**Добавить к представлению источника данных**</span><span class="sxs-lookup"><span data-stu-id="5f890-121">**Add to DSV**</span></span>  
 <span data-ttu-id="5f890-122">(Необязательно) Выберите представление источников данных в текущем проекте, если нужно добавить эту таблицу к существующему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="5f890-122">(Optional) Select a data source view contained in the project if you want to add the table to an existing data source.</span></span>  
  
 <span data-ttu-id="5f890-123">Этот параметр полезен, если необходимо, чтобы все связанные таблицы для модели, такие как обучающие данные, исходные данные и результаты запроса, были в одном источнике данных.</span><span class="sxs-lookup"><span data-stu-id="5f890-123">This option is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f890-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f890-124">See Also</span></span>  
 <span data-ttu-id="5f890-125">[Прогнозирование конструктор запросов &#40;интеллектуального анализа данных&#41;](prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="5f890-125">[Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md) </span></span>  
 <span data-ttu-id="5f890-126">[Интерфейсы запросов интеллектуального анализа данных](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="5f890-126">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="5f890-127">Справочник по расширениям интеллектуального анализа данных (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="5f890-127">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
