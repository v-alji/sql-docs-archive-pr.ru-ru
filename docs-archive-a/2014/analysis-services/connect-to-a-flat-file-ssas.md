---
title: Подключение к неструктурированному файлу (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connflatfile.f1
ms.assetid: a365991e-eded-4cd8-89c0-0daf6d658d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6bee3c8f7f4b255e6985e8d783365bc8a47599e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656738"
---
# <a name="connect-to-a-flat-file-ssas"></a><span data-ttu-id="5cd96-102">Подключение к неструктурированному файлу (SSAS)</span><span class="sxs-lookup"><span data-stu-id="5cd96-102">Connect to a Flat File (SSAS)</span></span>
  <span data-ttu-id="5cd96-103">Эта страница **мастера импорта таблиц** используется для соединения с неструктурированным файлом (TXT), файлом с разделителями в виде символов табуляции (TAB) или файлом с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="5cd96-103">This page of the **Table Import Wizard** enables you to connect to a flat file (.txt), tab-separated file (.tab), or a comma-separated file (.csv).</span></span> <span data-ttu-id="5cd96-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="5cd96-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="5cd96-105">Для соединения с неструктурированным файлом необходимо, чтобы на компьютере был установлен поставщик ACE.</span><span class="sxs-lookup"><span data-stu-id="5cd96-105">To connect to a flat file, you must have the ACE provider installed on your computer.</span></span> <span data-ttu-id="5cd96-106">Дополнительные сведения см. в разделе [Поддерживаемые источники данных (табличные службы SSAS)](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="5cd96-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cd96-107">При выборе файла на этой странице используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="5cd96-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="5cd96-108">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранного файла.</span><span class="sxs-lookup"><span data-stu-id="5cd96-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="5cd96-109">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5cd96-109">UI element list</span></span>  
 <span data-ttu-id="5cd96-110">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="5cd96-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="5cd96-111">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="5cd96-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="5cd96-112">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="5cd96-112">This is a required field.</span></span>  
  
 <span data-ttu-id="5cd96-113">**Путь к файлу**</span><span class="sxs-lookup"><span data-stu-id="5cd96-113">**File Path**</span></span>  
 <span data-ttu-id="5cd96-114">Укажите полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="5cd96-114">Specify a full path for the file.</span></span>  
  
 <span data-ttu-id="5cd96-115">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="5cd96-115">**Browse**</span></span>  
 <span data-ttu-id="5cd96-116">Перейдите в папку, в которой находится файл.</span><span class="sxs-lookup"><span data-stu-id="5cd96-116">Navigate to a location where a file is available.</span></span>  
  
 <span data-ttu-id="5cd96-117">**Разделитель столбцов**</span><span class="sxs-lookup"><span data-stu-id="5cd96-117">**Column Separator**</span></span>  
 <span data-ttu-id="5cd96-118">Выберите из списка разделитель столбцов.</span><span class="sxs-lookup"><span data-stu-id="5cd96-118">Select from a list of available column separators.</span></span> <span data-ttu-id="5cd96-119">Выберите разделитель, который вряд ли встретится в тексте.</span><span class="sxs-lookup"><span data-stu-id="5cd96-119">Choose a separator that is not likely to occur in the text.</span></span>  
  
|<span data-ttu-id="5cd96-120">Значение</span><span class="sxs-lookup"><span data-stu-id="5cd96-120">Value</span></span>|<span data-ttu-id="5cd96-121">Описание</span><span class="sxs-lookup"><span data-stu-id="5cd96-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5cd96-122">Табуляция (t)</span><span class="sxs-lookup"><span data-stu-id="5cd96-122">Tab (t)</span></span>|<span data-ttu-id="5cd96-123">Столбцы разделяются символом табуляции (t).</span><span class="sxs-lookup"><span data-stu-id="5cd96-123">Columns are separated by a tab (t).</span></span>|  
|<span data-ttu-id="5cd96-124">Запятая (,)</span><span class="sxs-lookup"><span data-stu-id="5cd96-124">Comma (,)</span></span>|<span data-ttu-id="5cd96-125">Столбцы разделяются символом запятой (,).</span><span class="sxs-lookup"><span data-stu-id="5cd96-125">Columns are separated by a comma (,).</span></span>|  
|<span data-ttu-id="5cd96-126">Точка с запятой (;)</span><span class="sxs-lookup"><span data-stu-id="5cd96-126">Semicolon (;)</span></span>|<span data-ttu-id="5cd96-127">Столбцы разделяются символом точки с запятой (;).</span><span class="sxs-lookup"><span data-stu-id="5cd96-127">Columns are separated by a semicolon (;).</span></span>|  
|<span data-ttu-id="5cd96-128">Пробел ( )</span><span class="sxs-lookup"><span data-stu-id="5cd96-128">Space ( )</span></span>|<span data-ttu-id="5cd96-129">Столбцы разделяются пробелом ( ).</span><span class="sxs-lookup"><span data-stu-id="5cd96-129">Columns are separated by a space ( ).</span></span>|  
|<span data-ttu-id="5cd96-130">Двоеточие (:)</span><span class="sxs-lookup"><span data-stu-id="5cd96-130">Colon (:)</span></span>|<span data-ttu-id="5cd96-131">Столбцы разделяются символом двоеточия (:).</span><span class="sxs-lookup"><span data-stu-id="5cd96-131">Columns are separated by a colon (:).</span></span>|  
|<span data-ttu-id="5cd96-132">Вертикальная черта (&#124;)</span><span class="sxs-lookup"><span data-stu-id="5cd96-132">Vertical Bar (&#124;)</span></span>|<span data-ttu-id="5cd96-133">Столбцы разделяются символом вертикальной черты (&#124;).</span><span class="sxs-lookup"><span data-stu-id="5cd96-133">Columns are separated by a vertical bar (&#124;).</span></span>|  
  
 <span data-ttu-id="5cd96-134">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="5cd96-134">**Advanced**</span></span>  
 <span data-ttu-id="5cd96-135">Укажите параметры кодировки и локали для неструктурированного файла.</span><span class="sxs-lookup"><span data-stu-id="5cd96-135">Specify the encoding and locale options for the flat file.</span></span>  
  
 <span data-ttu-id="5cd96-136">**Использовать первую строку для заголовков столбцов**</span><span class="sxs-lookup"><span data-stu-id="5cd96-136">**Use first row as column headers**</span></span>  
 <span data-ttu-id="5cd96-137">Укажите, следует ли использовать первую строку данных в качестве заголовков столбцов целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="5cd96-137">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="5cd96-138">**Предварительный просмотр данных**</span><span class="sxs-lookup"><span data-stu-id="5cd96-138">**Data preview**</span></span>  
 <span data-ttu-id="5cd96-139">Создать предварительный просмотр данных в выбранном файле и использовать следующие параметры для изменения импорта данных.</span><span class="sxs-lookup"><span data-stu-id="5cd96-139">Preview the data in the selected file, and use the following options to modify the data import.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cd96-140">В режиме предварительного просмотра отображаются только первые 50 строк файла.</span><span class="sxs-lookup"><span data-stu-id="5cd96-140">Only the first 50 rows in the file are displayed in this preview.</span></span>  
  
|<span data-ttu-id="5cd96-141">Параметр</span><span class="sxs-lookup"><span data-stu-id="5cd96-141">Option</span></span>|<span data-ttu-id="5cd96-142">Описание</span><span class="sxs-lookup"><span data-stu-id="5cd96-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5cd96-143">**Флажок в заголовке столбца**</span><span class="sxs-lookup"><span data-stu-id="5cd96-143">**Checkbox in the column header**</span></span>|<span data-ttu-id="5cd96-144">Установите флажок, чтобы включить столбец в импорт данных.</span><span class="sxs-lookup"><span data-stu-id="5cd96-144">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="5cd96-145">Снимите флажок, чтобы не импортировать столбец.</span><span class="sxs-lookup"><span data-stu-id="5cd96-145">Clear the checkbox to remove the column from the data import.</span></span>|  
|<span data-ttu-id="5cd96-146">**Стрелка вниз в заголовке столбца**</span><span class="sxs-lookup"><span data-stu-id="5cd96-146">**Down-arrow button in the column header**</span></span>|<span data-ttu-id="5cd96-147">Сортировка и фильтрация данных в столбце.</span><span class="sxs-lookup"><span data-stu-id="5cd96-147">Sort and filter data in the column.</span></span>|  
  
 <span data-ttu-id="5cd96-148">**Очистить фильтры строк**</span><span class="sxs-lookup"><span data-stu-id="5cd96-148">**Clear Row Filters**</span></span>  
 <span data-ttu-id="5cd96-149">Удалить все фильтры, примененные к данным в столбцах.</span><span class="sxs-lookup"><span data-stu-id="5cd96-149">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
