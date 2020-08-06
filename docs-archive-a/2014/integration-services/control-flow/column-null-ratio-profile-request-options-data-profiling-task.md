---
title: Параметры запроса профиля соотношения значений NULL в столбцах (задача "Профилирование данных") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 157ef8e4-fd23-4f81-8194-eebf74e9fd86
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e47c09a9a19eae4aed21c0c518430bc19a45648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658948"
---
# <a name="column-null-ratio-profile-request-options-data-profiling-task"></a><span data-ttu-id="17abf-102">Параметры запроса профиля соотношения значений NULL в столбцах (задача «Профилирование данных»)</span><span class="sxs-lookup"><span data-stu-id="17abf-102">Column Null Ratio Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="17abf-103">При помощи панели **Свойства запроса** страницы **Запросы профиля** можно задать параметры для варианта **Запрос соотношения значений NULL в столбцах** , выбранного на панели запросов.</span><span class="sxs-lookup"><span data-stu-id="17abf-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Null Ratio Request** selected in the requests pane.</span></span> <span data-ttu-id="17abf-104">Профиль «Соотношение значений NULL в столбцах» сообщает процент значений NULL в выбранном столбце.</span><span class="sxs-lookup"><span data-stu-id="17abf-104">A Column Null Ratio profile reports the percentage of null values in the selected column.</span></span> <span data-ttu-id="17abf-105">Этот профиль поможет выявить проблемы в данных, например появление непредвиденно высокого процента значений NULL в некотором столбце.</span><span class="sxs-lookup"><span data-stu-id="17abf-105">This profile can help you identify problems in your data such as an unexpectedly high ratio of null values in a column.</span></span> <span data-ttu-id="17abf-106">Например, с помощью профиля «Соотношение значений NULL в столбцах» можно профилировать столбец «Почтовый индекс» и обнаружить неприемлемо высокий процент отсутствующих почтовых индексов.</span><span class="sxs-lookup"><span data-stu-id="17abf-106">For example, a Column Null Ratio profile can profile a ZIP Code/Postal Code column and discover an unacceptably high percentage of missing postal codes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17abf-107">В этом разделе описываются параметры, расположенные на странице **Запросы профиля** в **редакторе задачи «Профилирование данных»** .</span><span class="sxs-lookup"><span data-stu-id="17abf-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="17abf-108">Дополнительные сведения об этой странице редактора см. в разделе [Редактор задачи "Профилирование данных" (страница "Запросы профиля")](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="17abf-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="17abf-109">Дополнительные сведения об использовании задачи "Профилирование данных" см. в разделе [Установка задачи "Профилирование данных"](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="17abf-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="17abf-110">Дополнительные сведения об использовании средства просмотра профиля данных для анализа результатов задачи "Профилирование данных" см. в разделе [Средство просмотра профиля данных](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="17abf-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="17abf-111">Параметры области «Свойства запроса»</span><span class="sxs-lookup"><span data-stu-id="17abf-111">Request Properties Options</span></span>  
 <span data-ttu-id="17abf-112">Для варианта **Запрос соотношения значений NULL в столбцах**на панели **Свойства запроса** отображаются следующие группы параметров.</span><span class="sxs-lookup"><span data-stu-id="17abf-112">For a **Column Null Ratio Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="17abf-113">**Данные**, куда входят параметры **TableOrView** и **Column**</span><span class="sxs-lookup"><span data-stu-id="17abf-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="17abf-114">**Общие сведения**</span><span class="sxs-lookup"><span data-stu-id="17abf-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="17abf-115">Параметры данных</span><span class="sxs-lookup"><span data-stu-id="17abf-115">Data Options</span></span>  
 <span data-ttu-id="17abf-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="17abf-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="17abf-117">Выберите существующий диспетчер подключений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] , использующий поставщик данных .NET для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) для подключения к базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которая содержит таблицу или представление для профилирования.</span><span class="sxs-lookup"><span data-stu-id="17abf-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the.NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="17abf-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="17abf-118">**TableOrView**</span></span>  
 <span data-ttu-id="17abf-119">Выберите существующую таблицу или представление, содержащие столбец для профилирования.</span><span class="sxs-lookup"><span data-stu-id="17abf-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="17abf-120">Дополнительные сведения см. в подразделе «Параметры TableorView» данного раздела.</span><span class="sxs-lookup"><span data-stu-id="17abf-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="17abf-121">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="17abf-121">**Column**</span></span>  
 <span data-ttu-id="17abf-122">Выберите существующий столбец для профилирования.</span><span class="sxs-lookup"><span data-stu-id="17abf-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="17abf-123">Выберите **(\*)** , чтобы выполнить профилирование всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="17abf-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="17abf-124">Дополнительные сведения см. в подразделе «Параметры столбца» данного раздела.</span><span class="sxs-lookup"><span data-stu-id="17abf-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="17abf-125">Параметры TableOrView</span><span class="sxs-lookup"><span data-stu-id="17abf-125">TableOrView Options</span></span>  
 <span data-ttu-id="17abf-126">**Схема**</span><span class="sxs-lookup"><span data-stu-id="17abf-126">**Schema**</span></span>  
 <span data-ttu-id="17abf-127">Указывает схему, которой принадлежит выбранная таблица.</span><span class="sxs-lookup"><span data-stu-id="17abf-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="17abf-128">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="17abf-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="17abf-129">**Таблица**</span><span class="sxs-lookup"><span data-stu-id="17abf-129">**Table**</span></span>  
 <span data-ttu-id="17abf-130">Отображает имя выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="17abf-130">Displays the name of the selected table.</span></span> <span data-ttu-id="17abf-131">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="17abf-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="17abf-132">Параметры столбца</span><span class="sxs-lookup"><span data-stu-id="17abf-132">Column Options</span></span>  
 <span data-ttu-id="17abf-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="17abf-133">**IsWildCard**</span></span>  
 <span data-ttu-id="17abf-134">Указывает, выбран ли подстановочный знак **(\*)** .</span><span class="sxs-lookup"><span data-stu-id="17abf-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="17abf-135">Этот параметр принимает значение **True**, если выбран подстановочный знак **(\*)** , означающий профилирование всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="17abf-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="17abf-136">Значение **False** показывает, что для профилирования выбран отдельный столбец.</span><span class="sxs-lookup"><span data-stu-id="17abf-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="17abf-137">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="17abf-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="17abf-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="17abf-138">**ColumnName**</span></span>  
 <span data-ttu-id="17abf-139">Отображает имя выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="17abf-139">Displays the name of the selected column.</span></span> <span data-ttu-id="17abf-140">Этот параметр пуст, если выбран подстановочный знак **(\*)** , означающий профилирование всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="17abf-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="17abf-141">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="17abf-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="17abf-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="17abf-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="17abf-143">Этот параметр не применяется к профилю «Соотношение значений NULL в столбцах».</span><span class="sxs-lookup"><span data-stu-id="17abf-143">This option does not apply to the Column Null Ratio Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="17abf-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="17abf-144">General Options</span></span>  
 <span data-ttu-id="17abf-145">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="17abf-145">**RequestID**</span></span>  
 <span data-ttu-id="17abf-146">Введите описательное имя для этого запроса профиля.</span><span class="sxs-lookup"><span data-stu-id="17abf-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="17abf-147">Обычно не нужно менять автоматически сформированное значение.</span><span class="sxs-lookup"><span data-stu-id="17abf-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17abf-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="17abf-148">See Also</span></span>  
 <span data-ttu-id="17abf-149">[Редактор задачи "Профилирование данных" (страница "Общие")](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="17abf-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="17abf-150">Форма быстрого профиля одной таблицы (задача "Профилирование данных")</span><span class="sxs-lookup"><span data-stu-id="17abf-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
