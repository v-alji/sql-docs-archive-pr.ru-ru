---
title: Диалоговое окно «Изменение свойств таблицы» (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.edittablepropdb.f1
ms.assetid: 8d913e83-7246-44cc-8fc7-31729023c0d8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6664d244f5f653610b37bd628abdb2263e015c0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667458"
---
# <a name="edit-table-properties-dialog-box-ssas"></a><span data-ttu-id="03d8e-102">Диалоговое окно «Изменение свойств таблицы» (SSAS)</span><span class="sxs-lookup"><span data-stu-id="03d8e-102">Edit Table Properties Dialog Box (SSAS)</span></span>
  <span data-ttu-id="03d8e-103">В диалоговом окне **Изменение свойств таблицы** можно просмотреть и изменить свойства таблиц, импортированных в конструктор моделей с помощью мастера импорта таблиц.</span><span class="sxs-lookup"><span data-stu-id="03d8e-103">The **Edit Table Properties** dialog box enables you to view and modify the properties of tables that are imported into the model designer by using the Table Import Wizard.</span></span> <span data-ttu-id="03d8e-104">Чтобы открыть это диалоговое окно, выберите таблицу в конструкторе моделей, а затем выберите пункт **Свойства таблицы** в меню **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="03d8e-104">To access this dialog box, in the model designer, select a table, then click the **Table** menu, and then click **Table Properties**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="03d8e-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="03d8e-105">UI element list</span></span>  
 <span data-ttu-id="03d8e-106">Параметры в этом диалоговом окне различаются в зависимости от способа импорта данных — путем выбора таблиц из списка или с помощью SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="03d8e-106">The options for this dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span>  
  
## <a name="table-preview-mode"></a><span data-ttu-id="03d8e-107">Режим просмотра таблицы</span><span class="sxs-lookup"><span data-stu-id="03d8e-107">Table Preview Mode</span></span>  
 <span data-ttu-id="03d8e-108">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="03d8e-108">**Table name**</span></span>  
 <span data-ttu-id="03d8e-109">Отображает имя таблицы данных в модели.</span><span class="sxs-lookup"><span data-stu-id="03d8e-109">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03d8e-110">Здесь нельзя изменить имя.</span><span class="sxs-lookup"><span data-stu-id="03d8e-110">You cannot edit the name here.</span></span> <span data-ttu-id="03d8e-111">Чтобы изменить имя таблицы, щелкните правой кнопкой мыши вкладку таблицы в нижней части конструктора моделей.</span><span class="sxs-lookup"><span data-stu-id="03d8e-111">However, you can change the name of the table by right-clicking the table tab at the bottom of the model designer.</span></span>  
  
 <span data-ttu-id="03d8e-112">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="03d8e-112">**Connection name**</span></span>  
 <span data-ttu-id="03d8e-113">Выводит имя используемого в данный момент соединения.</span><span class="sxs-lookup"><span data-stu-id="03d8e-113">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="03d8e-114">**Имя источника**</span><span class="sxs-lookup"><span data-stu-id="03d8e-114">**Source name**</span></span>  
 <span data-ttu-id="03d8e-115">Отображение или изменение таблицы, из которой получены данные.</span><span class="sxs-lookup"><span data-stu-id="03d8e-115">Display or change the table from which the data is obtained.</span></span>  
  
 <span data-ttu-id="03d8e-116">Если заменить источник на таблицу, столбцы которой отличаются от столбцов текущей таблицы, то выводится сообщение с предупреждением об отличающихся столбцах.</span><span class="sxs-lookup"><span data-stu-id="03d8e-116">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="03d8e-117">Затем необходимо выбрать столбцы, которые нужно поместить в текущую таблицу, и нажать кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="03d8e-117">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="03d8e-118">Можно заменить таблицу целиком, установив флажок слева от таблицы.</span><span class="sxs-lookup"><span data-stu-id="03d8e-118">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03d8e-119">Замена источника данных для таблицы фактически означает замену содержимого текущей таблицы на содержимое новой исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="03d8e-119">When you change the data source of a table, you essentially replace the contents of the current table with the contents of the new source table.</span></span>  
  
 <span data-ttu-id="03d8e-120">**Имена столбцов из**</span><span class="sxs-lookup"><span data-stu-id="03d8e-120">**Column names from**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="03d8e-121">**Source**</span><span class="sxs-lookup"><span data-stu-id="03d8e-121">**Source**</span></span>|<span data-ttu-id="03d8e-122">Выберите этот параметр, чтобы заменить текущие имена столбцов именами столбцов из выбранной исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="03d8e-122">Select this option to replace the current column names with the column names from the selected source table.</span></span>|  
|<span data-ttu-id="03d8e-123">**Модель**</span><span class="sxs-lookup"><span data-stu-id="03d8e-123">**Model**</span></span>|<span data-ttu-id="03d8e-124">Выберите этот параметр, чтобы использовать текущие имена столбцов, заданные в модели.</span><span class="sxs-lookup"><span data-stu-id="03d8e-124">Select this option to use the current column names as they exist in the model.</span></span>|  
  
 <span data-ttu-id="03d8e-125">**Просмотр обновления**</span><span class="sxs-lookup"><span data-stu-id="03d8e-125">**Refresh preview**</span></span>  
 <span data-ttu-id="03d8e-126">Нажмите, чтобы просмотреть столбцы данных в выбранной исходной таблице.</span><span class="sxs-lookup"><span data-stu-id="03d8e-126">Click to view the columns of data in the currently selected source table.</span></span>  
  
 <span data-ttu-id="03d8e-127">**Переключиться в**</span><span class="sxs-lookup"><span data-stu-id="03d8e-127">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="03d8e-128">**Просмотр таблицы**</span><span class="sxs-lookup"><span data-stu-id="03d8e-128">**Table preview**</span></span>|<span data-ttu-id="03d8e-129">Выберите этот параметр, чтобы просмотреть выбранную таблицу и ограниченное количество строк данных.</span><span class="sxs-lookup"><span data-stu-id="03d8e-129">Select this option to preview the selected table and a limited number of rows of data.</span></span>|  
|<span data-ttu-id="03d8e-130">**Редактор запросов**</span><span class="sxs-lookup"><span data-stu-id="03d8e-130">**Query editor**</span></span>|<span data-ttu-id="03d8e-131">Выберите этот параметр, чтобы просмотреть запрос к выбранному источнику данных.</span><span class="sxs-lookup"><span data-stu-id="03d8e-131">Select this option to view the query against the selected data source.</span></span> <span data-ttu-id="03d8e-132">Этот параметр доступен не для всех источников данных.</span><span class="sxs-lookup"><span data-stu-id="03d8e-132">This option is not available for all data sources.</span></span>|  
  
 <span data-ttu-id="03d8e-133">**Флажок в заголовке столбца**</span><span class="sxs-lookup"><span data-stu-id="03d8e-133">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="03d8e-134">Установите флажок, чтобы включить столбец в импорт данных.</span><span class="sxs-lookup"><span data-stu-id="03d8e-134">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="03d8e-135">Снимите флажок, чтобы не импортировать столбец.</span><span class="sxs-lookup"><span data-stu-id="03d8e-135">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="03d8e-136">**Стрелка вниз в заголовке столбца**</span><span class="sxs-lookup"><span data-stu-id="03d8e-136">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="03d8e-137">Фильтровать данные в столбце.</span><span class="sxs-lookup"><span data-stu-id="03d8e-137">Filter data in the column.</span></span>  
  
 <span data-ttu-id="03d8e-138">**Очистить фильтры строк**</span><span class="sxs-lookup"><span data-stu-id="03d8e-138">**Clear row filters**</span></span>  
 <span data-ttu-id="03d8e-139">Щелкните, чтобы удалить примененные фильтры.</span><span class="sxs-lookup"><span data-stu-id="03d8e-139">Click to remove any filters that have been applied.</span></span>  
  
 <span data-ttu-id="03d8e-140">**OK**</span><span class="sxs-lookup"><span data-stu-id="03d8e-140">**OK**</span></span>  
 <span data-ttu-id="03d8e-141">Нажмите, чтобы применить все выполненные изменения, включая замену столбцов.</span><span class="sxs-lookup"><span data-stu-id="03d8e-141">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="query-design-mode"></a><span data-ttu-id="03d8e-142">Режим конструктора запросов</span><span class="sxs-lookup"><span data-stu-id="03d8e-142">Query Design Mode</span></span>  
 <span data-ttu-id="03d8e-143">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="03d8e-143">**Table name**</span></span>  
 <span data-ttu-id="03d8e-144">Отображает имя таблицы данных в модели.</span><span class="sxs-lookup"><span data-stu-id="03d8e-144">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03d8e-145">Здесь нельзя изменить имя. Чтобы изменить имя таблицы, щелкните правой кнопкой мыши вкладку таблицы в нижней части конструктора.</span><span class="sxs-lookup"><span data-stu-id="03d8e-145">You cannot edit the name here; however, you can change the name of the table by right-clicking the table tab at the bottom of the designer.</span></span>  
  
 <span data-ttu-id="03d8e-146">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="03d8e-146">**Connection name**</span></span>  
 <span data-ttu-id="03d8e-147">Выводит имя используемого в данный момент соединения.</span><span class="sxs-lookup"><span data-stu-id="03d8e-147">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="03d8e-148">**Переключиться в**</span><span class="sxs-lookup"><span data-stu-id="03d8e-148">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="03d8e-149">**Просмотр таблицы**</span><span class="sxs-lookup"><span data-stu-id="03d8e-149">**Table preview**</span></span>|<span data-ttu-id="03d8e-150">Выберите этот параметр, чтобы просмотреть выбранную таблицу и несколько строк данных.</span><span class="sxs-lookup"><span data-stu-id="03d8e-150">Select this option to preview the selected table and a few rows of data.</span></span>|  
|<span data-ttu-id="03d8e-151">**Редактор запросов**</span><span class="sxs-lookup"><span data-stu-id="03d8e-151">**Query editor**</span></span>|<span data-ttu-id="03d8e-152">Выберите этот параметр, чтобы просмотреть запрос, который будет выполнен по отношению к выбранному источнику данных.</span><span class="sxs-lookup"><span data-stu-id="03d8e-152">Select this option to view the query that will be issued against the selected data source.</span></span>|  
  
 <span data-ttu-id="03d8e-153">**Инструкция SQL**</span><span class="sxs-lookup"><span data-stu-id="03d8e-153">**Sql statement**</span></span>  
 <span data-ttu-id="03d8e-154">Выводит инструкцию SQL, которая выполняется в текущем источнике данных для получения строк.</span><span class="sxs-lookup"><span data-stu-id="03d8e-154">Displays the SQL statement that is issued against the current data source to retrieve rows.</span></span> <span data-ttu-id="03d8e-155">По умолчанию возвращаются все строки, но можно получить подмножество строк, создав фильтр или вручную изменив инструкцию SQL.</span><span class="sxs-lookup"><span data-stu-id="03d8e-155">By default, all rows are retrieved, but you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="03d8e-156">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="03d8e-156">**Validate**</span></span>  
 <span data-ttu-id="03d8e-157">Нажмите, чтобы проверить синтаксис инструкции для выбранного источника данных и поставщика.</span><span class="sxs-lookup"><span data-stu-id="03d8e-157">Click to verify that the statement is syntactically correct for the selected data source and provider.</span></span>  
  
 <span data-ttu-id="03d8e-158">**Оформление**</span><span class="sxs-lookup"><span data-stu-id="03d8e-158">**Design**</span></span>  
 <span data-ttu-id="03d8e-159">Нажмите, чтобы открыть графический конструктор запросов и построить инструкцию запроса.</span><span class="sxs-lookup"><span data-stu-id="03d8e-159">Click to open a visual query designer and build a query statement.</span></span> <span data-ttu-id="03d8e-160">Для получения дополнительных сведений об использовании конструктора нажмите клавишу F1 в окне конструктора.</span><span class="sxs-lookup"><span data-stu-id="03d8e-160">For information about how to use the designer, press F1 from the designer.</span></span>  
  
 <span data-ttu-id="03d8e-161">**OK**</span><span class="sxs-lookup"><span data-stu-id="03d8e-161">**OK**</span></span>  
 <span data-ttu-id="03d8e-162">Нажмите, чтобы применить все выполненные изменения, включая замену столбцов.</span><span class="sxs-lookup"><span data-stu-id="03d8e-162">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d8e-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="03d8e-163">See Also</span></span>  
 [<span data-ttu-id="03d8e-164">Таблицы и столбцы (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="03d8e-164">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tabular-models/tables-and-columns-ssas-tabular.md)  
  
  
