---
title: Параметры для запроса профиля распределения длины столбцов (задача "Профилирование данных") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 1a4de41f-f38d-40ea-ba1b-6c0ef67ea52a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c0ebb6f1e0a6df2c0e47311f7b8217c5ce6f2df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658950"
---
# <a name="column-length-distribution-profile-request-options-data-profiling-task"></a><span data-ttu-id="ed37f-102">Параметры запроса профиля распределения длины столбцов (задача «Профилирование данных»)</span><span class="sxs-lookup"><span data-stu-id="ed37f-102">Column Length Distribution Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="ed37f-103">При помощи панели **Свойства запроса** страницы **Запросы профиля** можно задать параметры для варианта **Запрос профиля распределения длины столбцов** , выбранного на панели запросов.</span><span class="sxs-lookup"><span data-stu-id="ed37f-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Length Distribution Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="ed37f-104">Профиль «Распределение длины столбцов» содержит все точные значения длины строковых значений в выбранном столбце и процент строк таблицы, соответствующий каждому значению длины.</span><span class="sxs-lookup"><span data-stu-id="ed37f-104">A Column Length Distribution profile reports all the distinct lengths of string values in the selected column and the percentage of rows in the table that each length represents.</span></span> <span data-ttu-id="ed37f-105">Этот профиль помогает выявлять такие проблемы данных, как недопустимые значения.</span><span class="sxs-lookup"><span data-stu-id="ed37f-105">This profile can help you identify problems in your data such as invalid values.</span></span> <span data-ttu-id="ed37f-106">Например, во время профилирования столбца с кодами штатов США, состоящими из двух символов, можно выявить значения длиной более двух символов.</span><span class="sxs-lookup"><span data-stu-id="ed37f-106">For example, you profile a column of two-character United States state codes and discover values longer than two characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed37f-107">В этом разделе описываются параметры, расположенные на странице **Запросы профиля** в **редакторе задачи «Профилирование данных»** .</span><span class="sxs-lookup"><span data-stu-id="ed37f-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="ed37f-108">Дополнительные сведения об этой странице редактора см. в разделе [Редактор задачи "Профилирование данных" (страница "Запросы профиля")](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="ed37f-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="ed37f-109">Дополнительные сведения об использовании задачи "Профилирование данных" см. в разделе [Установка задачи "Профилирование данных"](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="ed37f-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="ed37f-110">Дополнительные сведения об использовании средства просмотра профиля данных для анализа результатов задачи "Профилирование данных" см. в разделе [Средство просмотра профиля данных](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="ed37f-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="ed37f-111">Параметры области «Свойства запроса»</span><span class="sxs-lookup"><span data-stu-id="ed37f-111">Request Properties Options</span></span>  
 <span data-ttu-id="ed37f-112">Для варианта **Запрос профиля распределения длины столбцов**на панели **Свойства запроса** отображаются следующие группы параметров.</span><span class="sxs-lookup"><span data-stu-id="ed37f-112">For a **Column Length Distribution Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="ed37f-113">**Данные**, куда входят параметры **TableOrView** и **Column**</span><span class="sxs-lookup"><span data-stu-id="ed37f-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="ed37f-114">**Общие сведения**</span><span class="sxs-lookup"><span data-stu-id="ed37f-114">**General**</span></span>  
  
-   <span data-ttu-id="ed37f-115">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="ed37f-115">**Options**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="ed37f-116">Параметры данных</span><span class="sxs-lookup"><span data-stu-id="ed37f-116">Data Options</span></span>  
 <span data-ttu-id="ed37f-117">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="ed37f-117">**ConnectionManager**</span></span>  
 <span data-ttu-id="ed37f-118">Выберите существующий диспетчер подключений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] , использующий поставщик данных .NET для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) для подключения к базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которая содержит таблицу или представление для профилирования.</span><span class="sxs-lookup"><span data-stu-id="ed37f-118">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="ed37f-119">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="ed37f-119">**TableOrView**</span></span>  
 <span data-ttu-id="ed37f-120">Выберите существующую таблицу или представление, содержащие столбец для профилирования.</span><span class="sxs-lookup"><span data-stu-id="ed37f-120">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="ed37f-121">Дополнительные сведения см. в подразделе «Параметры TableorView» данного раздела.</span><span class="sxs-lookup"><span data-stu-id="ed37f-121">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="ed37f-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ed37f-122">**Column**</span></span>  
 <span data-ttu-id="ed37f-123">Выберите существующий столбец для профилирования.</span><span class="sxs-lookup"><span data-stu-id="ed37f-123">Select the existing column to be profiled.</span></span> <span data-ttu-id="ed37f-124">Выберите **(\*)** , чтобы выполнить профилирование всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="ed37f-124">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="ed37f-125">Дополнительные сведения см. в подразделе «Параметры столбца» данного раздела.</span><span class="sxs-lookup"><span data-stu-id="ed37f-125">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="ed37f-126">Параметры TableOrView</span><span class="sxs-lookup"><span data-stu-id="ed37f-126">TableOrView Options</span></span>  
 <span data-ttu-id="ed37f-127">**Схема**</span><span class="sxs-lookup"><span data-stu-id="ed37f-127">**Schema**</span></span>  
 <span data-ttu-id="ed37f-128">Указывает схему, которой принадлежит выбранная таблица.</span><span class="sxs-lookup"><span data-stu-id="ed37f-128">Specify the schema to which the selected table belongs.</span></span> <span data-ttu-id="ed37f-129">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ed37f-129">This option is read-only.</span></span>  
  
 <span data-ttu-id="ed37f-130">**Таблица**</span><span class="sxs-lookup"><span data-stu-id="ed37f-130">**Table**</span></span>  
 <span data-ttu-id="ed37f-131">Отображает имя выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="ed37f-131">Displays the name of the selected table.</span></span> <span data-ttu-id="ed37f-132">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ed37f-132">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="ed37f-133">Параметры столбца</span><span class="sxs-lookup"><span data-stu-id="ed37f-133">Column Options</span></span>  
 <span data-ttu-id="ed37f-134">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="ed37f-134">**IsWildCard**</span></span>  
 <span data-ttu-id="ed37f-135">Указывает, выбран ли подстановочный знак **(\*)** .</span><span class="sxs-lookup"><span data-stu-id="ed37f-135">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="ed37f-136">Этот параметр принимает значение **True**, если выбран подстановочный знак **(\*)** , означающий профилирование всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="ed37f-136">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="ed37f-137">Значение **False** показывает, что для профилирования выбран отдельный столбец.</span><span class="sxs-lookup"><span data-stu-id="ed37f-137">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="ed37f-138">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ed37f-138">This option is read-only.</span></span>  
  
 <span data-ttu-id="ed37f-139">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="ed37f-139">**ColumnName**</span></span>  
 <span data-ttu-id="ed37f-140">Отображает имя выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="ed37f-140">Displays the name of the selected column.</span></span> <span data-ttu-id="ed37f-141">Этот параметр пуст, если выбран подстановочный знак **(\*)** , означающий профилирование всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="ed37f-141">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="ed37f-142">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ed37f-142">This option is read-only.</span></span>  
  
 <span data-ttu-id="ed37f-143">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="ed37f-143">**StringCompareOptions**</span></span>  
 <span data-ttu-id="ed37f-144">Этот параметр не применяется к профилю «Распределение длины столбцов».</span><span class="sxs-lookup"><span data-stu-id="ed37f-144">This option does not apply to the Column Length Distribution Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="ed37f-145">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ed37f-145">General Options</span></span>  
 <span data-ttu-id="ed37f-146">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="ed37f-146">**RequestID**</span></span>  
 <span data-ttu-id="ed37f-147">Введите описательное имя для этого запроса профиля.</span><span class="sxs-lookup"><span data-stu-id="ed37f-147">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="ed37f-148">Обычно не нужно менять автоматически сформированное значение.</span><span class="sxs-lookup"><span data-stu-id="ed37f-148">Typically, you do not have to change the autogenerated value.</span></span>  
  
### <a name="options"></a><span data-ttu-id="ed37f-149">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed37f-149">Options</span></span>  
 <span data-ttu-id="ed37f-150">**IgnoreLeadingSpaces**</span><span class="sxs-lookup"><span data-stu-id="ed37f-150">**IgnoreLeadingSpaces**</span></span>  
 <span data-ttu-id="ed37f-151">Указывает, следует ли пропускать начальные пробелы при сравнении строковых значений.</span><span class="sxs-lookup"><span data-stu-id="ed37f-151">Indicate whether to ignore leading spaces when the profile compares string values.</span></span> <span data-ttu-id="ed37f-152">По умолчанию значение этого параметра равно **False**.</span><span class="sxs-lookup"><span data-stu-id="ed37f-152">The default value of this option is **False**.</span></span>  
  
 <span data-ttu-id="ed37f-153">**IgnoreTrailingSpaces**</span><span class="sxs-lookup"><span data-stu-id="ed37f-153">**IgnoreTrailingSpaces**</span></span>  
 <span data-ttu-id="ed37f-154">Указывает, следует ли пропускать конечные пробелы при сравнении строковых значений.</span><span class="sxs-lookup"><span data-stu-id="ed37f-154">Indicate whether to ignore trailing spaces when the profile compares string values.</span></span> <span data-ttu-id="ed37f-155">По умолчанию значение этого параметра равно **True**.</span><span class="sxs-lookup"><span data-stu-id="ed37f-155">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed37f-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed37f-156">See Also</span></span>  
 <span data-ttu-id="ed37f-157">[Редактор задачи "Профилирование данных" (страница "Общие")](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="ed37f-157">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="ed37f-158">Форма быстрого профиля одной таблицы (задача "Профилирование данных")</span><span class="sxs-lookup"><span data-stu-id="ed37f-158">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
