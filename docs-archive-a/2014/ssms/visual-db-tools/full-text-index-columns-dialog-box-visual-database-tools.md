---
title: Диалоговое окно "Столбцы полнотекстовых индексов" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextcolumn
ms.assetid: a6f41c5c-d950-4d64-9e42-d062925917b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f1cd2c94739a13e1820d8c05b338abd91d8a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750428"
---
# <a name="full-text-index-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="16167-102">Диалоговое окно «Столбцы полнотекстовых индексов» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="16167-102">Full-Text Index Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="16167-103">В этом диалоговом окне приводится список столбцов, участвующих в полнотекстовом индексе для таблицы, открытой в конструкторе таблиц.</span><span class="sxs-lookup"><span data-stu-id="16167-103">This dialog box lists the columns participating in the full-text index for the table open in Table Designer.</span></span> <span data-ttu-id="16167-104">Чтобы открыть это диалоговое окно, щелкните правой кнопкой мыши таблицу в конструкторе таблиц, выберите **Полнотекстовой индекс** и в диалоговом окне **Полнотекстовой индекс** выберите индекс, который нужно просмотреть или отредактировать. После этого щелкните поле **Столбцы** в сетке справа и нажмите кнопку с многоточием ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="16167-104">To access this dialog box, right-click the table in Table Designer, choose **Full-Text Index**, and in the **Full-Text Index** dialog box, click the index with columns you want to view or edit, click the **Columns** field in the grid to the right, and click the ellipses (**...**).</span></span>  
  
## <a name="options"></a><span data-ttu-id="16167-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16167-105">Options</span></span>  
 <span data-ttu-id="16167-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="16167-106">**Column**</span></span>  
 <span data-ttu-id="16167-107">Показывает имена столбцов, участвующих в полнотекстовом индексе.</span><span class="sxs-lookup"><span data-stu-id="16167-107">Shows the names of columns participating in the full-text index.</span></span> <span data-ttu-id="16167-108">Для добавления столбца нажмите первую пустую ячейку, и выберите столбец из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="16167-108">To add a column, click in the first empty cell and choose a column from the drop-down list.</span></span> <span data-ttu-id="16167-109">Будут доступны только столбцы с данными, типом которых является либо текст, либо изображение.</span><span class="sxs-lookup"><span data-stu-id="16167-109">Only columns with either text-based or image data types will be accessible.</span></span>  
  
 <span data-ttu-id="16167-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="16167-110">**Data Type**</span></span>  
 <span data-ttu-id="16167-111">Показывает тип данных для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="16167-111">Shows the data type for each column.</span></span> <span data-ttu-id="16167-112">Это свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="16167-112">This is a read-only property.</span></span> <span data-ttu-id="16167-113">Для изменения типа данных откройте таблицу в конструкторе таблиц, щелкните кнопкой мыши столбец и измените тип данных на вкладке **Свойства столбца** .</span><span class="sxs-lookup"><span data-stu-id="16167-113">To change a data type, open the table in Table Designer, click the column, and edit the data type in the **Column Properties** tab.</span></span>  
  
 <span data-ttu-id="16167-114">**Типизировано по столбцам**</span><span class="sxs-lookup"><span data-stu-id="16167-114">**Typed by Column**</span></span>  
 <span data-ttu-id="16167-115">Применяется только к столбцам с типом данных `image`.</span><span class="sxs-lookup"><span data-stu-id="16167-115">Applies only to columns with the data type `image`.</span></span> <span data-ttu-id="16167-116">Отображает раскрывающийся список, по которому можно определить, какой еще столбец представляет тот же тип данных, что и данный столбец.</span><span class="sxs-lookup"><span data-stu-id="16167-116">Provides a drop-down list from which you can choose which of the other columns represent the data type of this column.</span></span> <span data-ttu-id="16167-117">Если тип данных этого столбца отличен от `image`, то значением будет «Нет».</span><span class="sxs-lookup"><span data-stu-id="16167-117">If this column is not of the `image` data type the value will be None.</span></span>  
  
 <span data-ttu-id="16167-118">Столбцы с типом данных `image` могут содержать файлы Microsoft Office (DOC, XLS и PPT), текстовые файлы (TXT) и HTML-файлы с расширением HTM, а установка значения типа данных для этого столбца в Image позволяет использовать полнотекстовый поиск для поиска содержимого этих файлов.</span><span class="sxs-lookup"><span data-stu-id="16167-118">Columns with the data type `image` can contain Microsoft Office files (.doc, .xls, and .ppt files), text files (.txt files), and HTML files (.htm files), and setting the data type of that column to image allows the full-text search to search the contents of the files.</span></span>  
  
 <span data-ttu-id="16167-119">**Язык**</span><span class="sxs-lookup"><span data-stu-id="16167-119">**Language**</span></span>  
 <span data-ttu-id="16167-120">Содержит список доступных языков.</span><span class="sxs-lookup"><span data-stu-id="16167-120">Lists available languages.</span></span> <span data-ttu-id="16167-121">Выберите из раскрывающего списка язык, соответствующий типу данных столбца.</span><span class="sxs-lookup"><span data-stu-id="16167-121">Choose the language from the drop-down list appropriate for your column data.</span></span> <span data-ttu-id="16167-122">Например, если язык операционной системы английский, но нужно индексировать столбец, содержащий немецкий текст, то выберите из раскрывающегося списка значение «Немецкий» для увеличения производительности индекса.</span><span class="sxs-lookup"><span data-stu-id="16167-122">For example, if you are using an English operating system, but you want to index a column that contains German text, choose German from the drop-down list to improve the index's performance.</span></span>  
  
 <span data-ttu-id="16167-123">**Статистическая семантика**</span><span class="sxs-lookup"><span data-stu-id="16167-123">**Statistical Semantics**</span></span>  
 <span data-ttu-id="16167-124">Укажите, следует ли включить статистическое семантическое индексирование для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="16167-124">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="16167-125">Дополнительные сведения см. в разделе [Семантический поиск (SQL Server)](../../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="16167-125">For more information, see [Semantic Search &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span></span>  
  
 <span data-ttu-id="16167-126">Если **Язык** выбран до выбора режима **Статистическая семантика**и выбранный язык не имеет связанной семантической модели языка, флажок **Статистическая семантика** будет недоступным.</span><span class="sxs-lookup"><span data-stu-id="16167-126">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="16167-127">Если режим **Статистическая семантика** выбран до выбора **Языка**, в раскрывающемся поле со списком будут доступны только языки, имеющие семантическую модель языка.</span><span class="sxs-lookup"><span data-stu-id="16167-127">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16167-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="16167-128">See Also</span></span>  
 [<span data-ttu-id="16167-129">Диалоговое окно "Полнотекстовый индекс" (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="16167-129">Full-Text Index Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
