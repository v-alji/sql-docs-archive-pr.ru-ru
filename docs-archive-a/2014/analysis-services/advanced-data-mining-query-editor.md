---
title: Расширенный редактор запросов интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 27e7fc46-689d-43a4-9647-1c27d182bdd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2aadf4df75b1ccf6001ad8e97d589ce5666f56ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656953"
---
# <a name="advanced-data-mining-query-editor"></a><span data-ttu-id="80143-102">Расширенный редактор запросов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="80143-102">Advanced Data Mining Query Editor</span></span>
  <span data-ttu-id="80143-103">**Расширенный редактор запросов интеллектуального анализа данных** — это средство, помогающее создавать пользовательские модели и запросы.</span><span class="sxs-lookup"><span data-stu-id="80143-103">The **Data Mining Query Advanced Editor** is a tool to help you build custom models and queries.</span></span>  
  
 <span data-ttu-id="80143-104">Редактор предоставляет набор шаблонов с интерактивными ссылками.</span><span class="sxs-lookup"><span data-stu-id="80143-104">The editor provides a set of templates with clickable links.</span></span> <span data-ttu-id="80143-105">Достаточно щелкнуть ссылку и выбрать объекты или значения с помощью диалогового окна, чтобы создавать сложные инструкции расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="80143-105">Just click each link, and use the dialog boxes to select objects or values and build complex Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="80143-106">Можно переключиться на текстовый редактор, чтобы изменить инструкцию интеллектуального анализа данных вручную.</span><span class="sxs-lookup"><span data-stu-id="80143-106">You can switch the view to text editing model to modify the DMX statement manually.</span></span>  
  
 <span data-ttu-id="80143-107">Чтобы перейти к **Расширенный редактор запросов интеллектуального анализа данных**, щелкните **запрос** , а затем нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="80143-107">To get to the **Data Mining Query Advanced Editor**, click **Query** and then click **Advanced**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="80143-108">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="80143-108">UI element list</span></span>  
 <span data-ttu-id="80143-109">**Панель «DMX-запрос»**</span><span class="sxs-lookup"><span data-stu-id="80143-109">**DMX Query pane**</span></span>  
 <span data-ttu-id="80143-110">Здесь можно просмотреть текущую DMX-инструкцию.</span><span class="sxs-lookup"><span data-stu-id="80143-110">Here you can see the current DMX statement.</span></span>  
  
 <span data-ttu-id="80143-111">Щелкните правой кнопкой мыши панель, чтобы скопировать текущую инструкцию расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="80143-111">Right-click in the pane to copy the current DMX statement.</span></span>  
  
 <span data-ttu-id="80143-112">Можно щелкнуть любую выделенную часть инструкции, чтобы получить параметры, относящиеся к этому предложению.</span><span class="sxs-lookup"><span data-stu-id="80143-112">You can click any highlighted part of the statement to get options specific to that clause.</span></span> <span data-ttu-id="80143-113">Например, чтобы удалить, добавить или изменить выходные данные, щелкните ссылку правой кнопкой мыши **\<Output>** .</span><span class="sxs-lookup"><span data-stu-id="80143-113">For example, to delete, add, or edit an output, right-click the **\<Output>** link.</span></span>  
  
 <span data-ttu-id="80143-114">**Изменить запрос/Построитель запросов**</span><span class="sxs-lookup"><span data-stu-id="80143-114">**Edit Query/Query Builder**</span></span>  
 <span data-ttu-id="80143-115">Используйте эту кнопку для переключения редактора между текстовым редактором, в котором можно непосредственно писать инструкции DMX. и **конструктор запросов**, которые помогают создать инструкцию DMX.</span><span class="sxs-lookup"><span data-stu-id="80143-115">Use this button to switch the editor between a text editor, where you can write DMX statements directly; and the **Query Builder**, which helps you build a DMX statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80143-116">**Предупреждение:** При переключении представлений перед выполнением запроса появляется сообщение о том, что некоторые изменения могут быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="80143-116">**Warning:** If you switch views before the query has been run, a message appears stating that you might lose some changes.</span></span> <span data-ttu-id="80143-117">Если инструкция DMX допустима, во многих случаях **конструктор запросов** может успешно преобразовать эти изменения.</span><span class="sxs-lookup"><span data-stu-id="80143-117">If the DMX statement is valid, in many cases the **Query Builder** might successfully convert these changes.</span></span> <span data-ttu-id="80143-118">Однако, если создана достаточно сложная DMX-инструкция, следует сохранить работу, прежде чем переключать представления.</span><span class="sxs-lookup"><span data-stu-id="80143-118">However, if you have built a particularly complex DMX statement, you should definitely save your work before switching views.</span></span>  
  
 <span data-ttu-id="80143-119">**Шаблоны расширений интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="80143-119">**DMX Templates**</span></span>  
 <span data-ttu-id="80143-120">Щелкните и выберите из списка шаблонов, содержащих примеры расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="80143-120">Click and select from a list of templates that contain DMX examples.</span></span> <span data-ttu-id="80143-121">Есть шаблоны практически для любого типа модели или прогнозирующего запроса, которые могут понадобиться, включая запросы, которые используют вложенные таблицы, и DMX-инструкции для управления моделями.</span><span class="sxs-lookup"><span data-stu-id="80143-121">The templates provide just about every type of model or prediction query that you might need, including queries that use nested tables, and DMX statements to manage models.</span></span> <span data-ttu-id="80143-122">Даже для тех, у кого есть хорошие навыки работы с расширениями интеллектуального анализа данных, шаблоны помогут сэкономить время, позволяя избежать ошибок синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="80143-122">Even if you know some DMX, the templates can save you time by getting the syntax right.</span></span>  
  
 <span data-ttu-id="80143-123">**Выбор модели**</span><span class="sxs-lookup"><span data-stu-id="80143-123">**Choose Model**</span></span>  
 <span data-ttu-id="80143-124">Щелкните, чтобы просмотреть список доступных моделей интеллектуального анализа данных для текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="80143-124">Click to view a list of data mining models available on the current connection.</span></span>  
  
 <span data-ttu-id="80143-125">Можно также отобразить список доступных моделей, щелкнув имя модели в инструкции DMX на панели **DMX-запрос** .</span><span class="sxs-lookup"><span data-stu-id="80143-125">You can also display a list of available models by clicking on the model name in the DMX statement in the **DMX Query** pane.</span></span> <span data-ttu-id="80143-126">Имя модели обычно выделено красным.</span><span class="sxs-lookup"><span data-stu-id="80143-126">The model name is typically highlighted in red.</span></span>  
  
 <span data-ttu-id="80143-127">**Выбор входных данных**</span><span class="sxs-lookup"><span data-stu-id="80143-127">**Select Input**</span></span>  
 <span data-ttu-id="80143-128">Щелкните, чтобы выбрать данные, которые будут входными в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="80143-128">Click to choose the data to use as input to the mining model.</span></span> <span data-ttu-id="80143-129">Если источник данных не указан, можно также щелкнуть **\<Input>** ссылку, выделенную красным цветом на панели **DMX-запрос** .</span><span class="sxs-lookup"><span data-stu-id="80143-129">If no data source has been specified, you can also click the **\<Input>** link, which is highlighted in red in the **DMX Query** pane.</span></span>  
  
 <span data-ttu-id="80143-130">Выберите \*\* \@ InputRowset\*\* из раскрывающегося списка, чтобы открыть диалоговое окно **Замена InputRowset** и изменить существующие входные данные.</span><span class="sxs-lookup"><span data-stu-id="80143-130">Select **\@InputRowset** from the dropdown list to open the **Replace InputRowset** dialog box and modify an existing input.</span></span>  
  
 <span data-ttu-id="80143-131">Выберите **Добавить входные** данные, чтобы открыть диалоговое окно **Добавление ввода** и указать новый источник данных.</span><span class="sxs-lookup"><span data-stu-id="80143-131">Select **Add Input** to open the **Add Input** dialog box and specify a new data source.</span></span>  
  
 <span data-ttu-id="80143-132">Можно также изменить существующие входные данные, щелкнув ссылку \*\* \@ InputRowset\*\* , выделенную красным цветом на панели DMX-запрос.</span><span class="sxs-lookup"><span data-stu-id="80143-132">You can also modify an existing input by clicking the **\@InputRowset** link, which is highlighted in red in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="80143-133">**Столбцы карт**</span><span class="sxs-lookup"><span data-stu-id="80143-133">**Map Columns**</span></span>  
 <span data-ttu-id="80143-134">Выберите столбцы из модели интеллектуального анализа данных и сопоставьте их со столбцами из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="80143-134">Select columns from the mining model and then map them to columns in the external data source.</span></span>  
  
 <span data-ttu-id="80143-135">Можно также щелкнуть выделенную **\<Mapping>** ссылку на панели DMX-запрос.</span><span class="sxs-lookup"><span data-stu-id="80143-135">You can also click the highlighted **\<Mapping>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="80143-136">**Добавление выходных данных**</span><span class="sxs-lookup"><span data-stu-id="80143-136">**Add Output**</span></span>  
 <span data-ttu-id="80143-137">Щелкните, чтобы выбрать столбцы, которые будут выдаваться в рамках прогнозирующего запроса.</span><span class="sxs-lookup"><span data-stu-id="80143-137">Click to choose the columns that should be output as part of a prediction query.</span></span>  
  
 <span data-ttu-id="80143-138">Можно также щелкнуть выделенную **\<Add Output>** ссылку на панели DMX-запрос.</span><span class="sxs-lookup"><span data-stu-id="80143-138">You can also click the highlighted **\<Add Output>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="80143-139">**Столбцы модели**</span><span class="sxs-lookup"><span data-stu-id="80143-139">**Model Columns**</span></span>  
 <span data-ttu-id="80143-140">Отображается список столбцов выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="80143-140">Lists the columns in the selected mining model.</span></span> <span data-ttu-id="80143-141">Значок ромба рядом с именем столбца указывает на то, что этот столбец является прогнозируемым столбцом.</span><span class="sxs-lookup"><span data-stu-id="80143-141">A diamond mark next to the column name indicates that the column is a predictable column.</span></span>  
  
 <span data-ttu-id="80143-142">**Входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="80143-142">**Input Columns**</span></span>  
 <span data-ttu-id="80143-143">Отображаются столбцы внешнего источника данных, добавленные в качестве входа.</span><span class="sxs-lookup"><span data-stu-id="80143-143">Lists the columns from the external data source that have been added as inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80143-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="80143-144">See Also</span></span>  
 [<span data-ttu-id="80143-145">&#40;запросов SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="80143-145">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
  
