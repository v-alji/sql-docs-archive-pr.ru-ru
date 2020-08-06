---
title: Параметры запроса профиля статистики столбцов (задача "Профилирование данных") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 87205984-507a-49f3-b27c-36a0075c234d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce5c062a12e38d147f3cef95ea09b4c80f7c256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658945"
---
# <a name="column-statistics-profile-request-options-data-profiling-task"></a><span data-ttu-id="e84cf-102">Параметры запроса профиля статистики столбцов (задача «Профилирование данных»)</span><span class="sxs-lookup"><span data-stu-id="e84cf-102">Column Statistics Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="e84cf-103">Для установки параметров режима **Запрос профиля статистики столбцов** , выделенного на панели запросов, используется панель **Свойства запроса** страницы **Запросы профиля** .</span><span class="sxs-lookup"><span data-stu-id="e84cf-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Statistics Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="e84cf-104">Профиль статистики столбцов описывает статистические показатели, такие как минимальное, максимальное, среднее и стандартное отклонение для числовых столбцов, а также минимальное и максимальное отклонение для столбцов типа `datetime`.</span><span class="sxs-lookup"><span data-stu-id="e84cf-104">A Column Statistics profile reports statistics such as minimum, maximum, average, and standard deviation for numeric columns, and minimum and maximum for `datetime` columns.</span></span> <span data-ttu-id="e84cf-105">Этот профиль поможет выявить проблемы в данных, например наличие недопустимых дат.</span><span class="sxs-lookup"><span data-stu-id="e84cf-105">This profile can help you identify problems in your data such as invalid dates.</span></span> <span data-ttu-id="e84cf-106">Например, во время профилирования столбца исторических дат обнаружена самая поздняя дата, расположенная в будущем.</span><span class="sxs-lookup"><span data-stu-id="e84cf-106">For example, you profile a column of historical dates and discover a maximum date that is in the future.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e84cf-107">В этом разделе описываются параметры, расположенные на странице **Запросы профиля** в **редакторе задачи «Профилирование данных»** .</span><span class="sxs-lookup"><span data-stu-id="e84cf-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="e84cf-108">Дополнительные сведения об этой странице редактора см. в разделе [Редактор задачи "Профилирование данных" (страница "Запросы профиля")](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="e84cf-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="e84cf-109">Дополнительные сведения об использовании задачи "Профилирование данных" см. в разделе [Установка задачи "Профилирование данных"](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="e84cf-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="e84cf-110">Дополнительные сведения об использовании средства просмотра профиля данных для анализа результатов задачи "Профилирование данных" см. в разделе [Средство просмотра профиля данных](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="e84cf-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="e84cf-111">Параметры области «Свойства запроса»</span><span class="sxs-lookup"><span data-stu-id="e84cf-111">Request Properties Options</span></span>  
 <span data-ttu-id="e84cf-112">Для варианта **Запрос профиля статистики столбцов**в панели **Свойства запроса** отображаются следующие группы параметров:</span><span class="sxs-lookup"><span data-stu-id="e84cf-112">For a **Column Statistics Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="e84cf-113">**Данные**, куда входят параметры **TableOrView** и **Column**</span><span class="sxs-lookup"><span data-stu-id="e84cf-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="e84cf-114">**Общие сведения**</span><span class="sxs-lookup"><span data-stu-id="e84cf-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="e84cf-115">Параметры данных</span><span class="sxs-lookup"><span data-stu-id="e84cf-115">Data Options</span></span>  
 <span data-ttu-id="e84cf-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="e84cf-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="e84cf-117">Выберите существующий диспетчер подключений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] , использующий поставщик данных .NET для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) для подключения к базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которая содержит таблицу или представление для профилирования.</span><span class="sxs-lookup"><span data-stu-id="e84cf-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="e84cf-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="e84cf-118">**TableOrView**</span></span>  
 <span data-ttu-id="e84cf-119">Выберите существующую таблицу или представление, содержащие столбец для профилирования.</span><span class="sxs-lookup"><span data-stu-id="e84cf-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="e84cf-120">Дополнительные сведения см. в подразделе «Параметры TableorView» данного раздела.</span><span class="sxs-lookup"><span data-stu-id="e84cf-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="e84cf-121">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e84cf-121">**Column**</span></span>  
 <span data-ttu-id="e84cf-122">Выберите существующий столбец для профилирования.</span><span class="sxs-lookup"><span data-stu-id="e84cf-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="e84cf-123">Выберите **(\*)** , чтобы выполнить профилирование всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="e84cf-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="e84cf-124">Дополнительные сведения см. в подразделе «Параметры столбца» данного раздела.</span><span class="sxs-lookup"><span data-stu-id="e84cf-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="e84cf-125">Параметры TableOrView</span><span class="sxs-lookup"><span data-stu-id="e84cf-125">TableOrView Options</span></span>  
 <span data-ttu-id="e84cf-126">**Схема**</span><span class="sxs-lookup"><span data-stu-id="e84cf-126">**Schema**</span></span>  
 <span data-ttu-id="e84cf-127">Указывает схему, которой принадлежит выбранная таблица.</span><span class="sxs-lookup"><span data-stu-id="e84cf-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="e84cf-128">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e84cf-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="e84cf-129">**Таблица**</span><span class="sxs-lookup"><span data-stu-id="e84cf-129">**Table**</span></span>  
 <span data-ttu-id="e84cf-130">Отображает имя выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="e84cf-130">Displays the name of the selected table.</span></span> <span data-ttu-id="e84cf-131">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e84cf-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="e84cf-132">Параметры столбца</span><span class="sxs-lookup"><span data-stu-id="e84cf-132">Column Options</span></span>  
 <span data-ttu-id="e84cf-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="e84cf-133">**IsWildCard**</span></span>  
 <span data-ttu-id="e84cf-134">Указывает, выбран ли подстановочный знак **(\*)** .</span><span class="sxs-lookup"><span data-stu-id="e84cf-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="e84cf-135">Этот параметр принимает значение **True**, если выбран подстановочный знак **(\*)** , означающий профилирование всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="e84cf-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="e84cf-136">Значение **False** показывает, что для профилирования выбран отдельный столбец.</span><span class="sxs-lookup"><span data-stu-id="e84cf-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="e84cf-137">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e84cf-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="e84cf-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="e84cf-138">**ColumnName**</span></span>  
 <span data-ttu-id="e84cf-139">Отображает имя выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="e84cf-139">Displays the name of the selected column.</span></span> <span data-ttu-id="e84cf-140">Этот параметр пуст, если выбран подстановочный знак **(\*)** , означающий профилирование всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="e84cf-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="e84cf-141">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e84cf-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="e84cf-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="e84cf-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="e84cf-143">Этот параметр не применяется к профилю статистики столбцов.</span><span class="sxs-lookup"><span data-stu-id="e84cf-143">This option does not apply to the Column Statistics Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="e84cf-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e84cf-144">General Options</span></span>  
 <span data-ttu-id="e84cf-145">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="e84cf-145">**RequestID**</span></span>  
 <span data-ttu-id="e84cf-146">Введите описательное имя для этого запроса профиля.</span><span class="sxs-lookup"><span data-stu-id="e84cf-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="e84cf-147">Обычно не нужно менять автоматически сформированное значение.</span><span class="sxs-lookup"><span data-stu-id="e84cf-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84cf-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="e84cf-148">See Also</span></span>  
 <span data-ttu-id="e84cf-149">[Редактор задачи "Профилирование данных" (страница "Общие")](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e84cf-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="e84cf-150">Форма быстрого профиля одной таблицы (задача "Профилирование данных")</span><span class="sxs-lookup"><span data-stu-id="e84cf-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
