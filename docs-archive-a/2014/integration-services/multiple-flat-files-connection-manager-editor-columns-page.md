---
title: Редактор диспетчера соединений с несколькими неструктурированными файлами (страница "столбцы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.columns.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: ad0cb668-0df2-4d4e-9a20-d20692a0b67a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a7f4936f0722754b414076820eda7dcf2dc8dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655809"
---
# <a name="multiple-flat-files-connection-manager-editor-columns-page"></a><span data-ttu-id="6e584-102">Редактор диспетчера соединения с несколькими неструктурированными файлами (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="6e584-102">Multiple Flat Files Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="6e584-103">Для задания сведений о строках и столбцах, а также для предварительного просмотра первого выбранного файла используется узел **Столбцы** диалогового окна **Редактор диспетчера соединений с несколькими неструктурированными файлами** .</span><span class="sxs-lookup"><span data-stu-id="6e584-103">Use the **Columns** node of the **Multiple Flat Files Connection Manager Editor** dialog box to specify the row and column information, and to preview the first selected file.</span></span>  
  
 <span data-ttu-id="6e584-104">Дополнительные сведения о диспетчере соединений с несколькими неструктурированными файлами см. в разделе [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6e584-104">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="6e584-105">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="6e584-105">Static Options</span></span>  
 <span data-ttu-id="6e584-106">**Имя диспетчера подключений**</span><span class="sxs-lookup"><span data-stu-id="6e584-106">**Connection manager name**</span></span>  
 <span data-ttu-id="6e584-107">Задайте уникальное имя для соединения с несколькими неструктурированными файлами в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="6e584-107">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="6e584-108">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e584-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="6e584-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6e584-109">**Description**</span></span>  
 <span data-ttu-id="6e584-110">Опишите соединение.</span><span class="sxs-lookup"><span data-stu-id="6e584-110">Describe the connection.</span></span> <span data-ttu-id="6e584-111">Рекомендуется описать цель соединения, чтобы пакеты самодокументировались и их проще было обслуживать.</span><span class="sxs-lookup"><span data-stu-id="6e584-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="6e584-112">Динамические параметры формата неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="6e584-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="6e584-113">Формат = Разделитель</span><span class="sxs-lookup"><span data-stu-id="6e584-113">Format = Delimited</span></span>  
 <span data-ttu-id="6e584-114">**Разделитель строк**</span><span class="sxs-lookup"><span data-stu-id="6e584-114">**Row delimiter**</span></span>  
 <span data-ttu-id="6e584-115">Выберите из списка доступных разделителей строк или введите текст разделителя.</span><span class="sxs-lookup"><span data-stu-id="6e584-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="6e584-116">Значение</span><span class="sxs-lookup"><span data-stu-id="6e584-116">Value</span></span>|<span data-ttu-id="6e584-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6e584-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e584-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="6e584-118">**{CR}{LF}**</span></span>|<span data-ttu-id="6e584-119">Строки разделяются сочетанием символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="6e584-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="6e584-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="6e584-120">**{CR}**</span></span>|<span data-ttu-id="6e584-121">Строки разделяются символом возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="6e584-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="6e584-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="6e584-122">**{LF}**</span></span>|<span data-ttu-id="6e584-123">Строки разделяются символом перевода строки.</span><span class="sxs-lookup"><span data-stu-id="6e584-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="6e584-124">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="6e584-124">**Semicolon {;}**</span></span>|<span data-ttu-id="6e584-125">Строки разделяются точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="6e584-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="6e584-126">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="6e584-126">**Colon {:}**</span></span>|<span data-ttu-id="6e584-127">Строки разделяются двоеточием.</span><span class="sxs-lookup"><span data-stu-id="6e584-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="6e584-128">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="6e584-128">**Comma {,}**</span></span>|<span data-ttu-id="6e584-129">Строки разделяются запятой.</span><span class="sxs-lookup"><span data-stu-id="6e584-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="6e584-130">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="6e584-130">**Tab {t}**</span></span>|<span data-ttu-id="6e584-131">Строки разделяются символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="6e584-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="6e584-132">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="6e584-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="6e584-133">Строки разделяются вертикальной чертой.</span><span class="sxs-lookup"><span data-stu-id="6e584-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="6e584-134">**Разделитель столбцов**</span><span class="sxs-lookup"><span data-stu-id="6e584-134">**Column delimiter**</span></span>  
 <span data-ttu-id="6e584-135">Выберите из списка доступных разделителей столбцов или введите текст разделителя.</span><span class="sxs-lookup"><span data-stu-id="6e584-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="6e584-136">Значение</span><span class="sxs-lookup"><span data-stu-id="6e584-136">Value</span></span>|<span data-ttu-id="6e584-137">Описание</span><span class="sxs-lookup"><span data-stu-id="6e584-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e584-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="6e584-138">**{CR}{LF}**</span></span>|<span data-ttu-id="6e584-139">Столбцы разделяются парой символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="6e584-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="6e584-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="6e584-140">**{CR}**</span></span>|<span data-ttu-id="6e584-141">Столбцы разделяются символом возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="6e584-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="6e584-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="6e584-142">**{LF}**</span></span>|<span data-ttu-id="6e584-143">Столбцы разделяются символом перевода строки.</span><span class="sxs-lookup"><span data-stu-id="6e584-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="6e584-144">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="6e584-144">**Semicolon {;}**</span></span>|<span data-ttu-id="6e584-145">Столбцы разделяются символом точки с запятой.</span><span class="sxs-lookup"><span data-stu-id="6e584-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="6e584-146">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="6e584-146">**Colon {:}**</span></span>|<span data-ttu-id="6e584-147">Столбцы разделяются символом двоеточия.</span><span class="sxs-lookup"><span data-stu-id="6e584-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="6e584-148">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="6e584-148">**Comma {,}**</span></span>|<span data-ttu-id="6e584-149">Столбцы разделяются символом запятой.</span><span class="sxs-lookup"><span data-stu-id="6e584-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="6e584-150">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="6e584-150">**Tab {t}**</span></span>|<span data-ttu-id="6e584-151">Столбцы разделяются символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="6e584-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="6e584-152">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="6e584-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="6e584-153">Столбцы разделяются символом вертикальной черты.</span><span class="sxs-lookup"><span data-stu-id="6e584-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="6e584-154">**Сбросить столбцы**</span><span class="sxs-lookup"><span data-stu-id="6e584-154">**Reset Columns**</span></span>  
 <span data-ttu-id="6e584-155">При нажатии кнопки **Сбросить столбцы**удаляются все столбцы, кроме исходных.</span><span class="sxs-lookup"><span data-stu-id="6e584-155">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="6e584-156">Формат = Фиксированная ширина</span><span class="sxs-lookup"><span data-stu-id="6e584-156">Format = Fixed Width</span></span>  
 <span data-ttu-id="6e584-157">**Шрифт**</span><span class="sxs-lookup"><span data-stu-id="6e584-157">**Font**</span></span>  
 <span data-ttu-id="6e584-158">Выбор шрифта для предварительного просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="6e584-158">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="6e584-159">**Столбцы источника данных**</span><span class="sxs-lookup"><span data-stu-id="6e584-159">**Source data columns**</span></span>  
 <span data-ttu-id="6e584-160">Настройте ширину строк, перемещая вертикальный маркер, а также ширину столбцов, щелкнув линейку в верхней части окна предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="6e584-160">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="6e584-161">**Ширина строки**</span><span class="sxs-lookup"><span data-stu-id="6e584-161">**Row width**</span></span>  
 <span data-ttu-id="6e584-162">Задайте длину строки перед добавлением разделителей для отдельных столбцов.</span><span class="sxs-lookup"><span data-stu-id="6e584-162">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="6e584-163">Либо перетащите вертикальную линию в окне предварительного просмотра, чтобы отметить конец строки.</span><span class="sxs-lookup"><span data-stu-id="6e584-163">Or, drag the vertical line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="6e584-164">Значение ширины строки автоматически обновляется.</span><span class="sxs-lookup"><span data-stu-id="6e584-164">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="6e584-165">**Сбросить столбцы**</span><span class="sxs-lookup"><span data-stu-id="6e584-165">**Reset Columns**</span></span>  
 <span data-ttu-id="6e584-166">При нажатии кнопки **Сбросить столбцы**удаляются все столбцы, кроме исходных.</span><span class="sxs-lookup"><span data-stu-id="6e584-166">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="6e584-167">Формат = Выравнивание по левому краю</span><span class="sxs-lookup"><span data-stu-id="6e584-167">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e584-168">В файлах с текстом без выключки вправо каждый столбец имеет фиксированную ширину, за исключением последнего столбца.</span><span class="sxs-lookup"><span data-stu-id="6e584-168">Ragged right files are those in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="6e584-169">Он отделяется разделителем строк.</span><span class="sxs-lookup"><span data-stu-id="6e584-169">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="6e584-170">**Шрифт**</span><span class="sxs-lookup"><span data-stu-id="6e584-170">**Font**</span></span>  
 <span data-ttu-id="6e584-171">Выбор шрифта для предварительного просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="6e584-171">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="6e584-172">**Столбцы источника данных**</span><span class="sxs-lookup"><span data-stu-id="6e584-172">**Source data columns**</span></span>  
 <span data-ttu-id="6e584-173">Настройте ширину строк, перемещая вертикальный маркер, а также ширину столбцов, щелкнув линейку в верхней части окна предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="6e584-173">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="6e584-174">**Разделитель строк**</span><span class="sxs-lookup"><span data-stu-id="6e584-174">**Row delimiter**</span></span>  
 <span data-ttu-id="6e584-175">Выберите из списка доступных разделителей строк или введите текст разделителя.</span><span class="sxs-lookup"><span data-stu-id="6e584-175">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="6e584-176">Значение</span><span class="sxs-lookup"><span data-stu-id="6e584-176">Value</span></span>|<span data-ttu-id="6e584-177">Описание</span><span class="sxs-lookup"><span data-stu-id="6e584-177">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e584-178">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="6e584-178">**{CR}{LF}**</span></span>|<span data-ttu-id="6e584-179">Строки разделяются сочетанием символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="6e584-179">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="6e584-180">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="6e584-180">**{CR}**</span></span>|<span data-ttu-id="6e584-181">Строки разделяются символом возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="6e584-181">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="6e584-182">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="6e584-182">**{LF}**</span></span>|<span data-ttu-id="6e584-183">Строки разделяются символом перевода строки.</span><span class="sxs-lookup"><span data-stu-id="6e584-183">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="6e584-184">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="6e584-184">**Semicolon {;}**</span></span>|<span data-ttu-id="6e584-185">Строки разделяются точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="6e584-185">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="6e584-186">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="6e584-186">**Colon {:}**</span></span>|<span data-ttu-id="6e584-187">Строки разделяются двоеточием.</span><span class="sxs-lookup"><span data-stu-id="6e584-187">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="6e584-188">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="6e584-188">**Comma {,}**</span></span>|<span data-ttu-id="6e584-189">Строки разделяются запятой.</span><span class="sxs-lookup"><span data-stu-id="6e584-189">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="6e584-190">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="6e584-190">**Tab {t}**</span></span>|<span data-ttu-id="6e584-191">Строки разделяются символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="6e584-191">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="6e584-192">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="6e584-192">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="6e584-193">Строки разделяются вертикальной чертой.</span><span class="sxs-lookup"><span data-stu-id="6e584-193">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="6e584-194">**Сбросить столбцы**</span><span class="sxs-lookup"><span data-stu-id="6e584-194">**Reset Columns**</span></span>  
 <span data-ttu-id="6e584-195">При нажатии кнопки **Сбросить столбцы**удаляются все столбцы, кроме исходных.</span><span class="sxs-lookup"><span data-stu-id="6e584-195">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e584-196">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e584-196">See Also</span></span>  
 <span data-ttu-id="6e584-197">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6e584-197">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6e584-198">[Редактор диспетчера соединений с несколькими неструктурированными файлами &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="6e584-198">[Multiple Flat Files Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="6e584-199">[Редактор диспетчера соединений с несколькими неструктурированными файлами &#40;страница "Дополнительно"&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="6e584-199">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="6e584-200">Редактор диспетчера подключений с несколькими неструктурированными файлами (страница "Предварительный просмотр")</span><span class="sxs-lookup"><span data-stu-id="6e584-200">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
