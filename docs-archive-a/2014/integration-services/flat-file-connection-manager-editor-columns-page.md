---
title: Редактор диспетчера соединений с неструктурированными файлами (страница «Столбцы») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.columns.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 40ce7537-abd0-4973-97fd-6ccb90fddfa0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6ce579f73922d2eaa2c48e98a98f52cd5836f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655867"
---
# <a name="flat-file-connection-manager-editor-columns-page"></a><span data-ttu-id="023a2-102">Редактор диспетчера соединений с неструктурированными файлами (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="023a2-102">Flat File Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="023a2-103">Страница **Столбцы** диалогового окна **Редактор диспетчера соединений с неструктурированными файлами** используется для задания данных о строках и столбцах и для предварительного просмотра файла.</span><span class="sxs-lookup"><span data-stu-id="023a2-103">Use the **Columns** page of the **Flat File Connection Manager Editor** dialog box to specify the row and column information, and to preview the file.</span></span>  
  
 <span data-ttu-id="023a2-104">Дополнительные сведения о диспетчере соединений с неструктурированными файлами см. в разделе [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="023a2-104">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="023a2-105">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="023a2-105">Static Options</span></span>  
 <span data-ttu-id="023a2-106">**Имя диспетчера подключений**</span><span class="sxs-lookup"><span data-stu-id="023a2-106">**Connection manager name**</span></span>  
 <span data-ttu-id="023a2-107">Укажите уникальное имя для соединения с неструктурированным файлом в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="023a2-107">Provide a unique name for the Flat File connection in the workflow.</span></span> <span data-ttu-id="023a2-108">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="023a2-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="023a2-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="023a2-109">**Description**</span></span>  
 <span data-ttu-id="023a2-110">Опишите соединение.</span><span class="sxs-lookup"><span data-stu-id="023a2-110">Describe the connection.</span></span> <span data-ttu-id="023a2-111">Рекомендуется описать цель соединения, чтобы пакеты самодокументировались и их проще было обслуживать.</span><span class="sxs-lookup"><span data-stu-id="023a2-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="023a2-112">Динамические параметры формата неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="023a2-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="023a2-113">Формат = Разделитель</span><span class="sxs-lookup"><span data-stu-id="023a2-113">Format = Delimited</span></span>  
 <span data-ttu-id="023a2-114">**Разделитель строк**</span><span class="sxs-lookup"><span data-stu-id="023a2-114">**Row delimiter**</span></span>  
 <span data-ttu-id="023a2-115">Выберите из списка доступных разделителей строк или введите текст разделителя.</span><span class="sxs-lookup"><span data-stu-id="023a2-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="023a2-116">Значение</span><span class="sxs-lookup"><span data-stu-id="023a2-116">Value</span></span>|<span data-ttu-id="023a2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="023a2-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="023a2-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="023a2-118">**{CR}{LF}**</span></span>|<span data-ttu-id="023a2-119">Строки разделяются сочетанием символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="023a2-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="023a2-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="023a2-120">**{CR}**</span></span>|<span data-ttu-id="023a2-121">Строки разделяются символом возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="023a2-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="023a2-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="023a2-122">**{LF}**</span></span>|<span data-ttu-id="023a2-123">Строки разделяются символом перевода строки.</span><span class="sxs-lookup"><span data-stu-id="023a2-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="023a2-124">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="023a2-124">**Semicolon {;}**</span></span>|<span data-ttu-id="023a2-125">Строки разделяются точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="023a2-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="023a2-126">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="023a2-126">**Colon {:}**</span></span>|<span data-ttu-id="023a2-127">Строки разделяются двоеточием.</span><span class="sxs-lookup"><span data-stu-id="023a2-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="023a2-128">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="023a2-128">**Comma {,}**</span></span>|<span data-ttu-id="023a2-129">Строки разделяются запятой.</span><span class="sxs-lookup"><span data-stu-id="023a2-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="023a2-130">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="023a2-130">**Tab {t}**</span></span>|<span data-ttu-id="023a2-131">Строки разделяются символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="023a2-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="023a2-132">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="023a2-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="023a2-133">Строки разделяются вертикальной чертой.</span><span class="sxs-lookup"><span data-stu-id="023a2-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="023a2-134">**Разделитель столбцов**</span><span class="sxs-lookup"><span data-stu-id="023a2-134">**Column delimiter**</span></span>  
 <span data-ttu-id="023a2-135">Выберите из списка доступных разделителей столбцов или введите текст разделителя.</span><span class="sxs-lookup"><span data-stu-id="023a2-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="023a2-136">Значение</span><span class="sxs-lookup"><span data-stu-id="023a2-136">Value</span></span>|<span data-ttu-id="023a2-137">Описание</span><span class="sxs-lookup"><span data-stu-id="023a2-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="023a2-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="023a2-138">**{CR}{LF}**</span></span>|<span data-ttu-id="023a2-139">Столбцы разделяются парой символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="023a2-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="023a2-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="023a2-140">**{CR}**</span></span>|<span data-ttu-id="023a2-141">Столбцы разделяются символом возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="023a2-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="023a2-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="023a2-142">**{LF}**</span></span>|<span data-ttu-id="023a2-143">Столбцы разделяются символом перевода строки.</span><span class="sxs-lookup"><span data-stu-id="023a2-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="023a2-144">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="023a2-144">**Semicolon {;}**</span></span>|<span data-ttu-id="023a2-145">Столбцы разделяются символом точки с запятой.</span><span class="sxs-lookup"><span data-stu-id="023a2-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="023a2-146">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="023a2-146">**Colon {:}**</span></span>|<span data-ttu-id="023a2-147">Столбцы разделяются символом двоеточия.</span><span class="sxs-lookup"><span data-stu-id="023a2-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="023a2-148">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="023a2-148">**Comma {,}**</span></span>|<span data-ttu-id="023a2-149">Столбцы разделяются символом запятой.</span><span class="sxs-lookup"><span data-stu-id="023a2-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="023a2-150">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="023a2-150">**Tab {t}**</span></span>|<span data-ttu-id="023a2-151">Столбцы разделяются символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="023a2-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="023a2-152">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="023a2-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="023a2-153">Столбцы разделяются символом вертикальной черты.</span><span class="sxs-lookup"><span data-stu-id="023a2-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="023a2-154">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="023a2-154">**Refresh**</span></span>  
 <span data-ttu-id="023a2-155">Просмотрите результаты изменения разделителей, нажав кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="023a2-155">View the effect of changing the delimiters to skip by clicking **Refresh**.</span></span> <span data-ttu-id="023a2-156">Эта кнопка становится видимой только после изменения других параметров соединения.</span><span class="sxs-lookup"><span data-stu-id="023a2-156">This button only becomes visible after you have changed other connection options.</span></span>  
  
 <span data-ttu-id="023a2-157">**Предварительный просмотр строк**</span><span class="sxs-lookup"><span data-stu-id="023a2-157">**Preview rows**</span></span>  
 <span data-ttu-id="023a2-158">Просмотр образца данных в неструктурированном файле, разделенном на столбцы и строки с помощью выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="023a2-158">View sample data in the flat file, divided into columns and rows by using the options selected.</span></span>  
  
 <span data-ttu-id="023a2-159">**Сбросить столбцы**</span><span class="sxs-lookup"><span data-stu-id="023a2-159">**Reset Columns**</span></span>  
 <span data-ttu-id="023a2-160">При нажатии кнопки **Сбросить столбцы**удаляются все столбцы, кроме исходных.</span><span class="sxs-lookup"><span data-stu-id="023a2-160">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="023a2-161">Формат = Фиксированная ширина</span><span class="sxs-lookup"><span data-stu-id="023a2-161">Format = Fixed Width</span></span>  
 <span data-ttu-id="023a2-162">**Шрифт**</span><span class="sxs-lookup"><span data-stu-id="023a2-162">**Font**</span></span>  
 <span data-ttu-id="023a2-163">Выбор шрифта для предварительного просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="023a2-163">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="023a2-164">**Столбцы источника данных**</span><span class="sxs-lookup"><span data-stu-id="023a2-164">**Source data columns**</span></span>  
 <span data-ttu-id="023a2-165">Настройте ширину строк, перемещая красный вертикальный маркер, а также ширину столбцов, щелкнув линейку в верхней части окна предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="023a2-165">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="023a2-166">**Ширина строки**</span><span class="sxs-lookup"><span data-stu-id="023a2-166">**Row width**</span></span>  
 <span data-ttu-id="023a2-167">Задайте длину строки перед добавлением разделителей для отдельных столбцов.</span><span class="sxs-lookup"><span data-stu-id="023a2-167">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="023a2-168">Или переместите красный вертикальный маркер в окне предварительного просмотра, чтобы отметить конец строки.</span><span class="sxs-lookup"><span data-stu-id="023a2-168">Or, drag the vertical red line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="023a2-169">Значение ширины строки автоматически обновляется.</span><span class="sxs-lookup"><span data-stu-id="023a2-169">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="023a2-170">**Сбросить столбцы**</span><span class="sxs-lookup"><span data-stu-id="023a2-170">**Reset Columns**</span></span>  
 <span data-ttu-id="023a2-171">При нажатии кнопки **Сбросить столбцы**удаляются все столбцы, кроме исходных.</span><span class="sxs-lookup"><span data-stu-id="023a2-171">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="023a2-172">Формат = Выравнивание по левому краю</span><span class="sxs-lookup"><span data-stu-id="023a2-172">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="023a2-173">В файлах с текстом без выравнивания вправо каждый столбец имеет фиксированную ширину, за исключением последнего столбца.</span><span class="sxs-lookup"><span data-stu-id="023a2-173">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="023a2-174">Он отделяется разделителем строк.</span><span class="sxs-lookup"><span data-stu-id="023a2-174">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="023a2-175">**Шрифт**</span><span class="sxs-lookup"><span data-stu-id="023a2-175">**Font**</span></span>  
 <span data-ttu-id="023a2-176">Выбор шрифта для предварительного просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="023a2-176">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="023a2-177">**Столбцы источника данных**</span><span class="sxs-lookup"><span data-stu-id="023a2-177">**Source data columns**</span></span>  
 <span data-ttu-id="023a2-178">Настройте ширину строк, перемещая красный вертикальный маркер, а также ширину столбцов, щелкнув линейку в верхней части окна предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="023a2-178">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="023a2-179">**Разделитель строк**</span><span class="sxs-lookup"><span data-stu-id="023a2-179">**Row delimiter**</span></span>  
 <span data-ttu-id="023a2-180">Выберите из списка доступных разделителей строк или введите текст разделителя.</span><span class="sxs-lookup"><span data-stu-id="023a2-180">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="023a2-181">Значение</span><span class="sxs-lookup"><span data-stu-id="023a2-181">Value</span></span>|<span data-ttu-id="023a2-182">Описание</span><span class="sxs-lookup"><span data-stu-id="023a2-182">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="023a2-183">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="023a2-183">**{CR}{LF}**</span></span>|<span data-ttu-id="023a2-184">Строки разделяются сочетанием символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="023a2-184">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="023a2-185">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="023a2-185">**{CR}**</span></span>|<span data-ttu-id="023a2-186">Строки разделяются символом возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="023a2-186">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="023a2-187">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="023a2-187">**{LF}**</span></span>|<span data-ttu-id="023a2-188">Строки разделяются символом перевода строки.</span><span class="sxs-lookup"><span data-stu-id="023a2-188">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="023a2-189">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="023a2-189">**Semicolon {;}**</span></span>|<span data-ttu-id="023a2-190">Строки разделяются точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="023a2-190">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="023a2-191">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="023a2-191">**Colon {:}**</span></span>|<span data-ttu-id="023a2-192">Строки разделяются двоеточием.</span><span class="sxs-lookup"><span data-stu-id="023a2-192">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="023a2-193">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="023a2-193">**Comma {,}**</span></span>|<span data-ttu-id="023a2-194">Строки разделяются запятой.</span><span class="sxs-lookup"><span data-stu-id="023a2-194">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="023a2-195">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="023a2-195">**Tab {t}**</span></span>|<span data-ttu-id="023a2-196">Строки разделяются символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="023a2-196">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="023a2-197">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="023a2-197">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="023a2-198">Строки разделяются вертикальной чертой.</span><span class="sxs-lookup"><span data-stu-id="023a2-198">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="023a2-199">**Сбросить столбцы**</span><span class="sxs-lookup"><span data-stu-id="023a2-199">**Reset Columns**</span></span>  
 <span data-ttu-id="023a2-200">При нажатии кнопки **Сбросить столбцы**удаляются все столбцы, кроме исходных.</span><span class="sxs-lookup"><span data-stu-id="023a2-200">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023a2-201">См. также:</span><span class="sxs-lookup"><span data-stu-id="023a2-201">See Also</span></span>  
 <span data-ttu-id="023a2-202">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="023a2-202">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="023a2-203">[Редактор диспетчера соединений с неструктурированными файлами &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="023a2-203">[Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="023a2-204">[Редактор диспетчера соединений с неструктурированными файлами &#40;страница "Дополнительно"&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="023a2-204">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="023a2-205">Редактор диспетчера подключений с неструктурированными файлами (страница "Предварительный просмотр")</span><span class="sxs-lookup"><span data-stu-id="023a2-205">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
