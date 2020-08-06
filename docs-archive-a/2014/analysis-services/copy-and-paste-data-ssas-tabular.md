---
title: Копирование и вставка данных (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.pastepreviewdb.f1
ms.assetid: 2f8d8b3d-810b-4c31-98f2-341015e13da8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30df733377f3cb6f7583d380fbb8e92a0ea69e88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656709"
---
# <a name="copy-and-paste-data-ssas-tabular"></a><span data-ttu-id="c9bf7-102">Копирование и вставка данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="c9bf7-102">Copy and Paste Data (SSAS Tabular)</span></span>
  <span data-ttu-id="c9bf7-103">Табличные данные можно скопировать из внешнего приложения и вставить в новую или существующую таблицу в конструкторе моделей.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-103">You can copy table data from external applications and paste it into a new or existing table in the model designer.</span></span> <span data-ttu-id="c9bf7-104">Данные, вставляемые из буфера обмена, должны иметь формат HTML, например, как и данные, копируемые из Excel или Word.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-104">The data that you paste from the Clipboard must be in HTML format, for example, data that is copied from Excel or Word.</span></span> <span data-ttu-id="c9bf7-105">Конструктор моделей автоматически обнаруживает и применяет типы данных для вставляемых данных.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-105">The model designer will automatically detect and apply data types to the pasted data.</span></span> <span data-ttu-id="c9bf7-106">Также можно изменить тип данных или формат отображения столбца вручную.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-106">You can also manually modify the data type or display formatting of a column.</span></span>  
  
 <span data-ttu-id="c9bf7-107">В отличие от соединения с источником данных, вставленные таблицы не имеют свойства «Имя соединения» или «Источник данных».</span><span class="sxs-lookup"><span data-stu-id="c9bf7-107">Unlike tables with a data source connection, pasted tables do not have a Connection Name or Source Data property.</span></span> <span data-ttu-id="c9bf7-108">Вставленные данные сохраняются в файле Model.bim.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-108">Pasted data is persisted in the Model.bim file.</span></span> <span data-ttu-id="c9bf7-109">При сохранении проекта или файла Model.bim вставленные данные также будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-109">When the project or Model.bim file is saved, the pasted data is also saved.</span></span>  
  
 <span data-ttu-id="c9bf7-110">При развертывании модели вставленные данные также будут развернуты вместе с ней вне зависимости от того, обрабатывается ли модель во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-110">When a model is deployed, pasted data will also be deployed with it regardless if the model is processed with the deployment.</span></span>  
  
 <span data-ttu-id="c9bf7-111">Разделы данной темы:</span><span class="sxs-lookup"><span data-stu-id="c9bf7-111">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="c9bf7-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c9bf7-112">Prerequisites</span></span>](#bkmk_prerequisites)  
  
-   [<span data-ttu-id="c9bf7-113">Вставить данные</span><span class="sxs-lookup"><span data-stu-id="c9bf7-113">Paste Data</span></span>](#bkmk_paste_data)  
  
-   [<span data-ttu-id="c9bf7-114">Диалоговое окно «Просмотр вставки»</span><span class="sxs-lookup"><span data-stu-id="c9bf7-114">Paste Preview Dialog Box</span></span>](#bkmk_paste_preview)  
  
##  <a name="prerequisites"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="c9bf7-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c9bf7-115">Prerequisites</span></span>  
 <span data-ttu-id="c9bf7-116">Существует несколько ограничений для вставки данных.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-116">There are some restrictions when pasting data:</span></span>  
  
-   <span data-ttu-id="c9bf7-117">Вставленные таблицы не могут содержать более 10 000 строк.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-117">Pasted tables cannot have more than 10,000 rows.</span></span>  
  
-   <span data-ttu-id="c9bf7-118">Вставленные таблицы не подлежат секционированию.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-118">Pasted tables cannot be partitioned.</span></span>  
  
-   <span data-ttu-id="c9bf7-119">Вставленные таблицы не поддерживаются в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-119">Pasted tables are not supported in DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="c9bf7-120">Варианты **Добавить из буфера** и **Вставка с заменой** доступны только во время работы с таблицей, изначально созданной путем вставки данных из буфера.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-120">The **Paste Append** and **Paste Replace** options are only available when working with a table that was initially created by pasting data from the Clipboard.</span></span> <span data-ttu-id="c9bf7-121">Команды **Добавить из буфера** и **Вставить с заменой** не позволяют добавлять данные в таблицу импортированных данных из другого источника данных.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-121">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data from another type of data source.</span></span>  
  
-   <span data-ttu-id="c9bf7-122">Если используется команда **Добавить из буфера** или **Вставить с заменой**, новые данные должны содержать ровно столько же столбцов, сколько исходные.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-122">When you use **Paste Append** or **Paste Replace**, the new data must contain exactly the same number of columns as the original data.</span></span> <span data-ttu-id="c9bf7-123">Предпочтительно также, чтобы столбцы вставляемых или добавляемых данных имели те же или совместимые типы данных, что и столбцы в целевой таблице.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-123">Preferably, the columns of data that you paste or append should also be of the same or compatible data type as those in the destination table.</span></span> <span data-ttu-id="c9bf7-124">В некоторых случаях вы можете использовать другой тип данных, но это может привести к **несоответствию типов** .</span><span class="sxs-lookup"><span data-stu-id="c9bf7-124">In some cases you can use a different data type, but a **Type mismatch** error may be displayed.</span></span>  
  
##  <a name="paste-data"></a><a name="bkmk_paste_data"></a> <span data-ttu-id="c9bf7-125">Вставить данные</span><span class="sxs-lookup"><span data-stu-id="c9bf7-125">Paste Data</span></span>  
  
#### <a name="to-paste-data-into-the-designer"></a><span data-ttu-id="c9bf7-126">Вставка данных в конструктор</span><span class="sxs-lookup"><span data-stu-id="c9bf7-126">To paste data into the designer</span></span>  
  
-   <span data-ttu-id="c9bf7-127">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте меню **Правка** и выберите один из следующих пунктов:</span><span class="sxs-lookup"><span data-stu-id="c9bf7-127">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Edit** menu, and then clicke of the following:</span></span>  
  
    -   <span data-ttu-id="c9bf7-128">Нажмите кнопку **Вставить** , чтобы вставить содержимое буфера обмена в новую таблицу.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-128">Click **Paste** to paste the contents of the Clipboard into a new table.</span></span>  
  
    -   <span data-ttu-id="c9bf7-129">Нажмите кнопку **Добавить из буфера** , чтобы вставить содержимое буфера обмена в качестве дополнительных строк в выбранную таблицу.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-129">Click **Paste Append** to paste the contents of the Clipboard as additional rows into the selected table.</span></span> <span data-ttu-id="c9bf7-130">Новые строки будут добавлены в конец таблицы.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-130">The new rows will be added to the end of the table.</span></span>  
  
    -   <span data-ttu-id="c9bf7-131">Нажмите кнопку **Вставить с заменой** , чтобы заменить выбранную таблицу содержимым из буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-131">Click **Paste Replace** to replace the selected table with the contents of the Clipboard.</span></span> <span data-ttu-id="c9bf7-132">Все существующие имена заголовков столбцов останутся в таблице, при этом все связи будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-132">All existing column header names will remain in the table, and relationships are preserved.</span></span>  
  
##  <a name="paste-preview-dialog-box"></a><a name="bkmk_paste_preview"></a><span data-ttu-id="c9bf7-133">Диалоговое окно «Просмотр вставки»</span><span class="sxs-lookup"><span data-stu-id="c9bf7-133">Paste Preview Dialog Box</span></span>  
 <span data-ttu-id="c9bf7-134">В диалоговом окне **Просмотр вставки** можно просмотреть данные, которые копируются в окно конструктора, и убедиться, что данные копируются правильно.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-134">The **Paste Preview** dialog box enables you to see a preview of data that is copied into the designer window and to ensure that the data is copied correctly.</span></span> <span data-ttu-id="c9bf7-135">Чтобы открыть это диалоговое окно, скопируйте табличные данные в формате HTML в буфер обмена, а затем в конструкторе в меню **Правка** выберите команду **Вставить**, **Добавить из буфера**или **Вставить с заменой**.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-135">To access this dialog box, copy table-based data in the HTML format to the clipboard, and then in the designer, click on the **Edit** menu, and then click **Paste**, **Paste Append**, or **Paste Replace**.</span></span> <span data-ttu-id="c9bf7-136">Кнопки **Добавить из буфера** и **Вставить с заменой** доступны только во время добавления или замены данных в таблице, которая создана путем копирования и вставки данных из буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-136">The **Paste Append** and **Paste Replace** options are only available when you add or replace data in a table that was created by copying and pasting from the Clipboard.</span></span> <span data-ttu-id="c9bf7-137">Команды **Добавить из буфера** и **Вставить с заменой** не позволяют добавлять данные в таблицу импортированных данных.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-137">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data.</span></span>  
  
 <span data-ttu-id="c9bf7-138">Параметры в этом диалоговом окне различаются в зависимости от типа операции — вставка данных в новую таблицу, вставка данных в существующую таблицу с заменой существующих данных или добавление данных в существующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-138">The options for this dialog box are different depending on whether you paste data into a completely new table, paste data into an existing table and then replace the existing data with the new data, or whether you append data to an existing table.</span></span>  
  
### <a name="paste-to-new-table"></a><span data-ttu-id="c9bf7-139">Вставка в новую таблицу</span><span class="sxs-lookup"><span data-stu-id="c9bf7-139">Paste to New Table</span></span>  
 <span data-ttu-id="c9bf7-140">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="c9bf7-140">**Table name**</span></span>  
 <span data-ttu-id="c9bf7-141">Укажите имя таблицы, создаваемой в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-141">Specify the name of the table that will be created in the designer.</span></span>  
  
 <span data-ttu-id="c9bf7-142">**Данные для вставки**</span><span class="sxs-lookup"><span data-stu-id="c9bf7-142">**Data to be pasted**</span></span>  
 <span data-ttu-id="c9bf7-143">Показывает образец содержимого буфера обмена, которое будет добавлено в целевую таблицу.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-143">Shows a sample of the Clipboard contents that will be added to the destination table.</span></span>  
  
### <a name="paste-append"></a><span data-ttu-id="c9bf7-144">Добавить из буфера</span><span class="sxs-lookup"><span data-stu-id="c9bf7-144">Paste Append</span></span>  
 <span data-ttu-id="c9bf7-145">**Существующие данные в таблице**</span><span class="sxs-lookup"><span data-stu-id="c9bf7-145">**Existing data in the table**</span></span>  
 <span data-ttu-id="c9bf7-146">Показывает образец существующих данных в таблице, чтобы проверить столбцы, типы данных и т. д.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-146">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="c9bf7-147">**Данные для вставки**</span><span class="sxs-lookup"><span data-stu-id="c9bf7-147">**Data to be pasted**</span></span>  
 <span data-ttu-id="c9bf7-148">Показывает образец содержимого буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-148">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="c9bf7-149">Существующие данные будут добавлены в эти данные.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-149">The existing data will be appended by this data.</span></span>  
  
### <a name="paste-replace"></a><span data-ttu-id="c9bf7-150">Вставка с заменой</span><span class="sxs-lookup"><span data-stu-id="c9bf7-150">Paste Replace</span></span>  
 <span data-ttu-id="c9bf7-151">**Существующие данные в таблице**</span><span class="sxs-lookup"><span data-stu-id="c9bf7-151">**Existing data in the table**</span></span>  
 <span data-ttu-id="c9bf7-152">Показывает образец существующих данных в таблице, чтобы проверить столбцы, типы данных и т. д.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-152">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="c9bf7-153">**Данные для вставки**</span><span class="sxs-lookup"><span data-stu-id="c9bf7-153">**Data to be pasted**</span></span>  
 <span data-ttu-id="c9bf7-154">Показывает образец содержимого буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-154">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="c9bf7-155">Существующие данные будут удалены из целевой таблицы, и будут вставлены новые строки.</span><span class="sxs-lookup"><span data-stu-id="c9bf7-155">The existing data in the destination table will be deleted and the new rows will be inserted into the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bf7-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9bf7-156">See Also</span></span>  
 <span data-ttu-id="c9bf7-157">[Импорт данных &#40;табличные&#41;SSAS](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c9bf7-157">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="c9bf7-158">[Поддерживаемые источники данных &#40;табличные&#41;SSAS](tabular-models/data-sources-supported-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c9bf7-158">[Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c9bf7-159">Выбор типа данных столбца (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="c9bf7-159">Set the Data Type of a Column &#40;SSAS Tabular&#41;</span></span>](tabular-models/set-the-data-type-of-a-column-ssas-tabular.md)  
  
  
