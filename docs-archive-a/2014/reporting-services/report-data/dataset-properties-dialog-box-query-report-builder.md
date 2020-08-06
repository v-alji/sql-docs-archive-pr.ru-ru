---
title: Диалоговое окно "Свойства набора данных" — "Запрос" (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10024"
ms.assetid: 75432318-0b00-4797-917c-0a2e74f9d951
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a3c9df366bc36302cc7faf22b6efb6c3d1017b5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751792"
---
# <a name="dataset-properties-dialog-box-query-report-builder"></a><span data-ttu-id="624fa-102">Диалоговое окно «Свойства набора данных» — «Запрос» (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="624fa-102">Dataset Properties Dialog Box, Query (Report Builder)</span></span>
  <span data-ttu-id="624fa-103">Выберите **Запрос** в диалоговом окне **Свойства набора данных** , чтобы выбрать общий набор данных на сервере отчетов или создать внедренный набор данных.</span><span class="sxs-lookup"><span data-stu-id="624fa-103">Select **Query** on the **Dataset Properties** dialog box to choose a shared dataset from a report server or to create an embedded dataset.</span></span> <span data-ttu-id="624fa-104">Для внедренного набора данных необходимо выбрать источник данных и создать запрос.</span><span class="sxs-lookup"><span data-stu-id="624fa-104">For an embedded dataset, you must choose a data source and build a query.</span></span>  
  
 <span data-ttu-id="624fa-105">Диалоговое окно **Свойства набора данных** содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="624fa-105">The **Dataset Properties** dialog box includes the following:</span></span>  
  
-   [<span data-ttu-id="624fa-106">Диалоговое окно "Свойства набора данных" — "Параметры" (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="624fa-106">Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;</span></span>](../dataset-properties-dialog-box-parameters-report-builder.md)  
  
-   [<span data-ttu-id="624fa-107">Диалоговое окно "Свойства набора данных" — "Поля" (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="624fa-107">Dataset Properties Dialog Box, Fields &#40;Report Builder&#41;</span></span>](../dataset-properties-dialog-box-fields-report-builder.md)  
  
-   [<span data-ttu-id="624fa-108">Диалоговое окно "Свойства набора данных" — "Настройки" (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="624fa-108">Dataset Properties Dialog Box, Options &#40;Report Builder&#41;</span></span>](dataset-properties-dialog-box-options-report-builder.md)  
  
-   [<span data-ttu-id="624fa-109">Диалоговое окно "Свойства набора данных" — "Фильтры" (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="624fa-109">Dataset Properties Dialog Box, Filters &#40;Report Builder&#41;</span></span>](../dataset-properties-dialog-box-filters-report-builder.md)  
  
 <span data-ttu-id="624fa-110">Дополнительные сведения см. в разделе [Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="624fa-110">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="624fa-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="624fa-111">Options</span></span>  
 <span data-ttu-id="624fa-112">**имя**;</span><span class="sxs-lookup"><span data-stu-id="624fa-112">**Name**</span></span>  
 <span data-ttu-id="624fa-113">Введите имя набора данных.</span><span class="sxs-lookup"><span data-stu-id="624fa-113">Type a name for the dataset.</span></span> <span data-ttu-id="624fa-114">Это имя не должно совпадать ни с одним именем области данных или группы в данном отчете.</span><span class="sxs-lookup"><span data-stu-id="624fa-114">The name cannot be the same as a name for any data region or group in the report.</span></span>  
  
 <span data-ttu-id="624fa-115">**Использовать общий набор данных**</span><span class="sxs-lookup"><span data-stu-id="624fa-115">**Use a shared dataset**</span></span>  
 <span data-ttu-id="624fa-116">Выберите этот параметр, чтобы использовать стандартный набор данных с сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="624fa-116">Select this option to use a predefined dataset from the report server.</span></span>  
  
 <span data-ttu-id="624fa-117">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="624fa-117">**Browse**</span></span>  
 <span data-ttu-id="624fa-118">Перейдите в папку на сервере отчетов или сайте SharePoint и выберите общий набор данных (RSD).</span><span class="sxs-lookup"><span data-stu-id="624fa-118">Browse to a folder on a report server or SharePoint site and select a shared dataset (.rsd).</span></span>  
  
 <span data-ttu-id="624fa-119">**Использовать в отчете внедренный набор данных**</span><span class="sxs-lookup"><span data-stu-id="624fa-119">**Use an embedded dataset in my report**</span></span>  
 <span data-ttu-id="624fa-120">Выберите этот параметр, чтобы создать набор данных, используемый только в данном отчете.</span><span class="sxs-lookup"><span data-stu-id="624fa-120">Select this option to create a dataset for use only by this report.</span></span>  
  
 <span data-ttu-id="624fa-121">**Источник данных**</span><span class="sxs-lookup"><span data-stu-id="624fa-121">**Data Source**</span></span>  
 <span data-ttu-id="624fa-122">Выберите источник данных, на котором основывается этот набор данных.</span><span class="sxs-lookup"><span data-stu-id="624fa-122">Select the data source on which to base the dataset.</span></span> <span data-ttu-id="624fa-123">Чтобы создать новый источник данных, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="624fa-123">To create a new data source, click **New**.</span></span>  
  
 <span data-ttu-id="624fa-124">**Тип запроса**</span><span class="sxs-lookup"><span data-stu-id="624fa-124">**Query type**</span></span>  
 <span data-ttu-id="624fa-125">Выберите тип команды или запрос для этого набора данных.</span><span class="sxs-lookup"><span data-stu-id="624fa-125">Select the type of command or query to use for the dataset.</span></span> <span data-ttu-id="624fa-126">Выберите **Текст** , чтобы запустить запрос и получить данные из базы данных.</span><span class="sxs-lookup"><span data-stu-id="624fa-126">Select **Text** to run a query to retrieve data from the database.</span></span> <span data-ttu-id="624fa-127">Выберите **Таблица** , чтобы выбрать все поля таблицы с помощью функции **TableDirect** в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="624fa-127">Select **Table** to use the **TableDirect** feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to select all the fields within a table.</span></span> <span data-ttu-id="624fa-128">Выберите **Хранимая процедура** , чтобы выполнить хранимую процедуру по имени.</span><span class="sxs-lookup"><span data-stu-id="624fa-128">Select **Stored Procedure** to run a stored procedure by name.</span></span> <span data-ttu-id="624fa-129">Поле**Текст** выбирается по умолчанию и используется для большинства запросов.</span><span class="sxs-lookup"><span data-stu-id="624fa-129">**Text** is selected by default and is used for most queries.</span></span> <span data-ttu-id="624fa-130">Чтобы изменить выбранный запрос к источнику данных, нажмите кнопку **Конструктор запросов**.</span><span class="sxs-lookup"><span data-stu-id="624fa-130">To edit the selected data source query, click **Query Designer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="624fa-131">Не все типы запросов поддерживаются всеми источниками данных.</span><span class="sxs-lookup"><span data-stu-id="624fa-131">Not all query types are supported by all data sources.</span></span> <span data-ttu-id="624fa-132">Например, тип **Таблица** поддерживается только источниками данных типа **OLE DB** и **ODBC**.</span><span class="sxs-lookup"><span data-stu-id="624fa-132">For example, **Table** is supported only by data source types **OLE DB** and **ODBC**.</span></span>  
  
 <span data-ttu-id="624fa-133">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="624fa-133">**Query**</span></span>  
 <span data-ttu-id="624fa-134">Появляется при выборе параметра типа команды **Текст** .</span><span class="sxs-lookup"><span data-stu-id="624fa-134">This option appears when you choose the **Text** command type option.</span></span> <span data-ttu-id="624fa-135">Введите запрос или импортируйте существующий запрос, нажав кнопку **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="624fa-135">Type a query or import a pre-existing query by clicking **Import**.</span></span> <span data-ttu-id="624fa-136">Нажмите кнопку **выражение** (*FX*), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="624fa-136">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="624fa-137">Если запрос был построен с помощью конструктора, текст запроса появляется в этом поле.</span><span class="sxs-lookup"><span data-stu-id="624fa-137">If you used a query designer to build a query, the text of the query appears in this box.</span></span>  
  
 <span data-ttu-id="624fa-138">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="624fa-138">**Table name**</span></span>  
 <span data-ttu-id="624fa-139">Введите имя таблицы, которая будет использоваться в качестве набора данных.</span><span class="sxs-lookup"><span data-stu-id="624fa-139">Enter the name of the table that you want to use as a dataset.</span></span> <span data-ttu-id="624fa-140">Этот параметр появляется при выборе параметра **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="624fa-140">This option appears when you select **Table**.</span></span>  
  
 <span data-ttu-id="624fa-141">**Выберите или введите имя хранимой процедуры**</span><span class="sxs-lookup"><span data-stu-id="624fa-141">**Select or enter stored procedure name**</span></span>  
 <span data-ttu-id="624fa-142">Выберите или введите имя хранимой процедуры, которую нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="624fa-142">Type or choose the name of the stored procedure that you want to use.</span></span> <span data-ttu-id="624fa-143">Нажмите кнопку **выражение** (*FX*), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="624fa-143">Click the **Expression** (*fx*) button to edit the expression.</span></span> <span data-ttu-id="624fa-144">Этот параметр появляется при выборе параметра типа команды «Хранимая процедура».</span><span class="sxs-lookup"><span data-stu-id="624fa-144">This option appears when you choose the Stored Procedure command type option.</span></span>  
  
 <span data-ttu-id="624fa-145">**Время ожидания (сек)**</span><span class="sxs-lookup"><span data-stu-id="624fa-145">**Time out (in seconds)**</span></span>  
 <span data-ttu-id="624fa-146">Введите количество секунд до истечения времени ожидания запроса. Значение по умолчанию — 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="624fa-146">Type the number of seconds until the query times out. The default is 30 seconds.</span></span> <span data-ttu-id="624fa-147">Значение параметра **Истечение времени ожидания** должно быть пустым или положительным числом.</span><span class="sxs-lookup"><span data-stu-id="624fa-147">The value for **Time out** must be empty or greater than zero.</span></span> <span data-ttu-id="624fa-148">Если значение не задано, время ожидания запроса не ограничивается.</span><span class="sxs-lookup"><span data-stu-id="624fa-148">If it is empty, the query does not time out.</span></span>  
  
 <span data-ttu-id="624fa-149">**Обновление полей**</span><span class="sxs-lookup"><span data-stu-id="624fa-149">**Refresh Fields**</span></span>  
 <span data-ttu-id="624fa-150">Выполните команду запроса, чтобы обновить список полей в диалоговом окне [Свойства набора данных — страница "Поля"](../dataset-properties-dialog-box-fields-report-builder.md) .</span><span class="sxs-lookup"><span data-stu-id="624fa-150">Run the query command to update the list of fields in the [Dataset Properties Dialog Box, Fields](../dataset-properties-dialog-box-fields-report-builder.md) page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="624fa-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="624fa-151">See Also</span></span>  
 <span data-ttu-id="624fa-152">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="624fa-152">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="624fa-153">[Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="624fa-153">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="624fa-154">Конструкторы запросов (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="624fa-154">Query Designers &#40;Report Builder&#41;</span></span>](../query-designers-report-builder.md)  
  
  
