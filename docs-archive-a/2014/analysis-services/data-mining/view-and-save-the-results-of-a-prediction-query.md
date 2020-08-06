---
title: Просмотр и сохранение результатов прогнозирующего запроса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- viewing prediction query results
- displaying prediction query results
- Mining Model Prediction [Analysis Services], viewing results
ms.assetid: abba4d24-3619-44c1-8279-88f27ad627d3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6da4b515c4280969f665dba2cf5bee5281df0a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658534"
---
# <a name="view-and-save-the-results-of-a-prediction-query"></a><span data-ttu-id="cc34d-102">Просмотр и сохранение результатов прогнозирующего запроса</span><span class="sxs-lookup"><span data-stu-id="cc34d-102">View and Save the Results of a Prediction Query</span></span>
  <span data-ttu-id="cc34d-103">После определения запроса в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] с помощью конструктор запросов прогнозирования можно выполнить запрос и просмотреть результаты, переключившись на представление результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="cc34d-103">After you have defined a query in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using Prediction Query Builder, you can run the query and view the results by switching to the query result view.</span></span>  
  
 <span data-ttu-id="cc34d-104">Результаты прогнозирующего запроса можно сохранить в таблицу в любом источнике данных, определенном в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проекте.</span><span class="sxs-lookup"><span data-stu-id="cc34d-104">You can save the results of a prediction query to a table in any data source that is defined in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="cc34d-105">Можно либо создать новую таблицу, либо сохранить результаты запроса в существующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="cc34d-105">You can either create a new table or save the query results to an existing table.</span></span> <span data-ttu-id="cc34d-106">При сохранении результатов в существующую таблицу можно выбрать перезапись данных, хранящихся в таблице в текущий момент, в противном случае результаты будут добавлены к существующим данным в таблице.</span><span class="sxs-lookup"><span data-stu-id="cc34d-106">If you save the results to an existing table, you can choose to overwrite the data that is currently stored in the table; otherwise, the query results are appended to the existing data in the table.</span></span>  
  
### <a name="run-a-query-and-view-the-results"></a><span data-ttu-id="cc34d-107">Выполните запрос и просмотрите результаты</span><span class="sxs-lookup"><span data-stu-id="cc34d-107">Run a query and view the results</span></span>  
  
1.  <span data-ttu-id="cc34d-108">На панели инструментов вкладки **Прогнозирование моделей интеллектуального анализа** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]нажмите кнопку **Результат** .</span><span class="sxs-lookup"><span data-stu-id="cc34d-108">On the toolbar of the **Mining Model Prediction** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Result** .</span></span>  
  
     <span data-ttu-id="cc34d-109">Откроется окно результатов и выполнится запрос.</span><span class="sxs-lookup"><span data-stu-id="cc34d-109">The query results view opens and runs the query.</span></span> <span data-ttu-id="cc34d-110">Результаты отображаются в сетке в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="cc34d-110">The results are displayed in a grid in the viewer.</span></span>  
  
### <a name="save-the-results-of-a-prediction-query-to-a-table"></a><span data-ttu-id="cc34d-111">Cохраните результаты прогнозирующего запроса в таблицу</span><span class="sxs-lookup"><span data-stu-id="cc34d-111">Save the results of a prediction query to a table</span></span>  
  
1.  <span data-ttu-id="cc34d-112">На панели инструментов вкладки **Прогнозирование моделей интеллектуального анализа данных** в конструкторе интеллектуального анализа данных нажмите кнопку **Сохранить результат запроса**.</span><span class="sxs-lookup"><span data-stu-id="cc34d-112">On the toolbar of the **Mining Model Prediction** tab in Data Mining Designer, click **Save query result**.</span></span>  
  
     <span data-ttu-id="cc34d-113">Откроется диалоговое окно **Сохранение результата запроса интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="cc34d-113">The **Save Data Mining Query Result** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="cc34d-114">Выберите источник данных из списка **Источник данных** или нажмите кнопку **Создать** , чтобы создать новый источник данных.</span><span class="sxs-lookup"><span data-stu-id="cc34d-114">Select a data source from the **Data Source** list, or click **New** to create a new data source.</span></span>  
  
3.  <span data-ttu-id="cc34d-115">В поле **Имя таблицы** введите имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="cc34d-115">In the **Table Name** box, enter the name of the table.</span></span> <span data-ttu-id="cc34d-116">Если таблица уже существует, то установите флажок **Перезаписать при существовании** , чтобы заменить содержимое таблицы результатами запроса.</span><span class="sxs-lookup"><span data-stu-id="cc34d-116">If the table already exists, select **Overwrite if exists** to replace the contents of the table with the query results.</span></span> <span data-ttu-id="cc34d-117">Если не нужно перезаписывать содержимое таблицы, то не устанавливайте этот флажок.</span><span class="sxs-lookup"><span data-stu-id="cc34d-117">If you do not want to overwrite the contents of the table, do not select this check box.</span></span> <span data-ttu-id="cc34d-118">Результаты нового запроса будут добавлены к существующим данным в таблице.</span><span class="sxs-lookup"><span data-stu-id="cc34d-118">The new query results will be appended to the existing data in the table.</span></span>  
  
4.  <span data-ttu-id="cc34d-119">Выберите представление источника данных из списка **Добавить к представлению источника данных** , если необходимо добавить таблицу к представлению источника данных.</span><span class="sxs-lookup"><span data-stu-id="cc34d-119">Select a data source view from **Add to DSV** if you want to add the table to a data source view.</span></span>  
  
5.  <span data-ttu-id="cc34d-120">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc34d-120">Click **Save**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="cc34d-121">Если место назначения не поддерживает иерархические наборы строк, можно добавить в результаты ключевое слово FALTTENED для сохранения результатов в виде плоской таблицы.</span><span class="sxs-lookup"><span data-stu-id="cc34d-121">If the destination does not support hierarchical rowsets, you can add the FALTTENED keyword to the results to save as a flat table.</span></span>  
  
  
