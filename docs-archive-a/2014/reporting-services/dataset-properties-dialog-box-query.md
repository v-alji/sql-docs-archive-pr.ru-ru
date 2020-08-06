---
title: Диалоговое окно "Свойства набора данных", запрос | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10160"
- sql12.rtp.rptdesigner.datasetproperties.query.f1
ms.assetid: 1fa34a4b-7de0-4e92-99fa-bc28a206773f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bffb14155d37e67333eb626747e1fcc54e618bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668659"
---
# <a name="dataset-properties-dialog-box-query"></a><span data-ttu-id="10420-102">Диалоговое окно «Свойства набора данных» — «Запрос»</span><span class="sxs-lookup"><span data-stu-id="10420-102">Dataset Properties Dialog Box, Query</span></span>
  <span data-ttu-id="10420-103">Перейдите на вкладку **Запрос** диалогового окна **Свойства набора данных** , чтобы выбрать источник данных и создать запрос.</span><span class="sxs-lookup"><span data-stu-id="10420-103">Select **Query** on the **Dataset Properties** dialog box to choose a data source and create a query.</span></span>  
  
 <span data-ttu-id="10420-104">Диалоговое окно **Свойства набора данных** содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="10420-104">The **Dataset Properties** dialog box includes the following:</span></span>  
  
-   [<span data-ttu-id="10420-105">Диалоговое окно "Свойства набора данных" — "Параметры"</span><span class="sxs-lookup"><span data-stu-id="10420-105">Dataset Properties Dialog Box, Parameters</span></span>](report-data/dataset-properties-dialog-box-parameters.md)  
  
-   [<span data-ttu-id="10420-106">Диалоговое окно «Свойства набора данных» — «Поля»</span><span class="sxs-lookup"><span data-stu-id="10420-106">Dataset Properties Dialog Box, Fields</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-fields.md)  
  
-   [<span data-ttu-id="10420-107">Диалоговое окно «Свойства набора данных» — «Настройки»</span><span class="sxs-lookup"><span data-stu-id="10420-107">Dataset Properties Dialog Box, Options</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-options.md)  
  
-   [<span data-ttu-id="10420-108">Диалоговое окно "Свойства набора данных" — "Фильтры"</span><span class="sxs-lookup"><span data-stu-id="10420-108">Dataset Properties Dialog Box, Filters</span></span>](report-data/dataset-properties-dialog-box-filters.md)  
  
## <a name="options"></a><span data-ttu-id="10420-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="10420-109">Options</span></span>  
 <span data-ttu-id="10420-110">**имя**;</span><span class="sxs-lookup"><span data-stu-id="10420-110">**Name**</span></span>  
 <span data-ttu-id="10420-111">Введите имя набора данных.</span><span class="sxs-lookup"><span data-stu-id="10420-111">Type a name for the dataset.</span></span> <span data-ttu-id="10420-112">Это имя не должно совпадать ни с одним именем области данных или группы в данном отчете.</span><span class="sxs-lookup"><span data-stu-id="10420-112">The name cannot be the same as a name for any data region or group in the report.</span></span>  
  
 <span data-ttu-id="10420-113">**Источник данных**</span><span class="sxs-lookup"><span data-stu-id="10420-113">**Data Source**</span></span>  
 <span data-ttu-id="10420-114">Выберите источник данных, на котором основывается этот набор данных.</span><span class="sxs-lookup"><span data-stu-id="10420-114">Select the data source on which to base the dataset.</span></span> <span data-ttu-id="10420-115">Чтобы создать новый источник данных, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="10420-115">To create a new data source, click **New**.</span></span>  
  
 <span data-ttu-id="10420-116">**Тип запроса**</span><span class="sxs-lookup"><span data-stu-id="10420-116">**Query type**</span></span>  
 <span data-ttu-id="10420-117">Выберите тип команды или запрос для этого набора данных.</span><span class="sxs-lookup"><span data-stu-id="10420-117">Select the type of command or query to use for the dataset.</span></span> <span data-ttu-id="10420-118">Выберите **Текст** , чтобы запустить запрос и получить данные из базы данных.</span><span class="sxs-lookup"><span data-stu-id="10420-118">Select **Text** to run a query to retrieve data from the database.</span></span> <span data-ttu-id="10420-119">Выберите **Таблица** , чтобы выбрать все поля таблицы с помощью функции **TableDirect** в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10420-119">Select **Table** to use the **TableDirect** feature of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to select all the fields within a table.</span></span> <span data-ttu-id="10420-120">Выберите **Хранимая процедура** , чтобы выполнить хранимую процедуру по имени.</span><span class="sxs-lookup"><span data-stu-id="10420-120">Select **Stored Procedure** to run a stored procedure by name.</span></span> <span data-ttu-id="10420-121">Поле**Текст** выбирается по умолчанию и используется для большинства запросов.</span><span class="sxs-lookup"><span data-stu-id="10420-121">**Text** is selected by default and is used for most queries.</span></span> <span data-ttu-id="10420-122">Чтобы изменить выбранный запрос к источнику данных, нажмите кнопку **Конструктор запросов**.</span><span class="sxs-lookup"><span data-stu-id="10420-122">To edit the selected data source query, click **Query Designer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10420-123">Не все типы запросов поддерживаются всеми источниками данных.</span><span class="sxs-lookup"><span data-stu-id="10420-123">Not all query types are supported by all data sources.</span></span> <span data-ttu-id="10420-124">Например, тип **Таблица** поддерживается только источниками данных типа **OLE DB** и **ODBC**.</span><span class="sxs-lookup"><span data-stu-id="10420-124">For example, **Table** is supported only by data source types **OLE DB** and **ODBC**.</span></span>  
  
 <span data-ttu-id="10420-125">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="10420-125">**Query**</span></span>  
 <span data-ttu-id="10420-126">Появляется при выборе параметра типа команды **Текст** .</span><span class="sxs-lookup"><span data-stu-id="10420-126">This option appears when you choose the **Text** command type option.</span></span> <span data-ttu-id="10420-127">Введите запрос или импортируйте существующий запрос, нажав кнопку **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="10420-127">Type a query or import a pre-existing query by clicking **Import**.</span></span> <span data-ttu-id="10420-128">Нажмите кнопку **выражение** (*FX*), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="10420-128">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10420-129">Если запрос был построен с помощью конструктора, текст запроса появляется в этом поле.</span><span class="sxs-lookup"><span data-stu-id="10420-129">If you used a query designer to build a query, the text of the query appears in this box.</span></span>  
  
 <span data-ttu-id="10420-130">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="10420-130">**Table name**</span></span>  
 <span data-ttu-id="10420-131">Введите имя таблицы, которая будет использоваться в качестве набора данных.</span><span class="sxs-lookup"><span data-stu-id="10420-131">Enter the name of the table that you want to use as a dataset.</span></span> <span data-ttu-id="10420-132">Этот параметр появляется при выборе параметра **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="10420-132">This option appears when you select **Table**.</span></span>  
  
 <span data-ttu-id="10420-133">**Выберите или введите имя хранимой процедуры**</span><span class="sxs-lookup"><span data-stu-id="10420-133">**Select or enter stored procedure name**</span></span>  
 <span data-ttu-id="10420-134">Выберите или введите имя хранимой процедуры, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="10420-134">Type or choose the name of the stored procedure that you want to use.</span></span> <span data-ttu-id="10420-135">Нажмите кнопку **выражение** (*FX*), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="10420-135">Click the **Expression** (*fx*) button to edit the expression.</span></span> <span data-ttu-id="10420-136">Этот параметр появляется при выборе параметра типа команды «Хранимая процедура».</span><span class="sxs-lookup"><span data-stu-id="10420-136">This option appears when you choose the Stored Procedure command type option.</span></span>  
  
 <span data-ttu-id="10420-137">**Время ожидания (сек)**</span><span class="sxs-lookup"><span data-stu-id="10420-137">**Time out (in seconds)**</span></span>  
 <span data-ttu-id="10420-138">Введите количество секунд до истечения времени ожидания запроса. Значение по умолчанию — 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="10420-138">Type the number of seconds until the query times out. The default is 30 seconds.</span></span> <span data-ttu-id="10420-139">Значение параметра **Истечение времени ожидания** должно быть пустым или положительным числом.</span><span class="sxs-lookup"><span data-stu-id="10420-139">The value for **Time out** must be empty or greater than zero.</span></span> <span data-ttu-id="10420-140">Если значение не задано, время ожидания запроса не ограничивается.</span><span class="sxs-lookup"><span data-stu-id="10420-140">If it is empty, the query does not time out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10420-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="10420-141">See Also</span></span>  
 <span data-ttu-id="10420-142">[Подключения к данным, источники данных и строки подключения в Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="10420-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="10420-143">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10420-143">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="10420-144">[Конструкторы запросов &#40;построитель отчетов&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="10420-144">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 [<span data-ttu-id="10420-145">Конструкторы запросов служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="10420-145">Reporting Services Query Designers</span></span>](../../2014/reporting-services/reporting-services-query-designers.md)  
  
  
