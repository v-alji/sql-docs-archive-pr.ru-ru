---
title: Редактор диспетчера соединений с несколькими неструктурированными файлами (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.general.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: 00129d43-2772-413b-bdf8-ac5de81cf4a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f30a422794723f216d30e05f0750fb1e974e0920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736527"
---
# <a name="multiple-flat-files-connection-manager-editor-general-page"></a><span data-ttu-id="047f1-102">Редактор диспетчера соединений с несколькими неструктурированными файлами (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="047f1-102">Multiple Flat Files Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="047f1-103">С помощью страницы **Общие** диалогового окна **Редактор диспетчера соединения с несколькими неструктурированными файлами** можно выбрать группу файлов с одинаковым форматом данных и указать их формат данных.</span><span class="sxs-lookup"><span data-stu-id="047f1-103">Use the **General** page of the **Multiple Flat Files Connection Manager Editor** dialog box to select a group of files that have the same data format, and to specify their data format.</span></span> <span data-ttu-id="047f1-104">Соединения с несколькими неструктурированными файлами дают возможность пакету подключиться к группе текстовых файлов с тем же форматом.</span><span class="sxs-lookup"><span data-stu-id="047f1-104">A multiple flat files connection enables a package to connect to a group of text files that have the same format.</span></span>  
  
 <span data-ttu-id="047f1-105">Дополнительные сведения о диспетчере соединений с несколькими неструктурированными файлами см. в разделе [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="047f1-105">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="047f1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="047f1-106">Options</span></span>  
 <span data-ttu-id="047f1-107">**Имя диспетчера подключений**</span><span class="sxs-lookup"><span data-stu-id="047f1-107">**Connection manager name**</span></span>  
 <span data-ttu-id="047f1-108">Задайте уникальное имя для соединения с несколькими неструктурированными файлами в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="047f1-108">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="047f1-109">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="047f1-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="047f1-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="047f1-110">**Description**</span></span>  
 <span data-ttu-id="047f1-111">Опишите соединение.</span><span class="sxs-lookup"><span data-stu-id="047f1-111">Describe the connection.</span></span> <span data-ttu-id="047f1-112">Рекомендуется описать цель соединения, чтобы пакеты самодокументировались и их проще было обслуживать.</span><span class="sxs-lookup"><span data-stu-id="047f1-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="047f1-113">**Имена файлов**</span><span class="sxs-lookup"><span data-stu-id="047f1-113">**File names**</span></span>  
 <span data-ttu-id="047f1-114">Введите путь и имена файлов для соединения с несколькими неструктурированными файлами.</span><span class="sxs-lookup"><span data-stu-id="047f1-114">Type the path and file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="047f1-115">Можно указать несколько файлов, используя символы-шаблоны (как в "C:\\*.txt") или разделив несколько имен файлов символом вертикальной черты (|).</span><span class="sxs-lookup"><span data-stu-id="047f1-115">You can specify multiple files by using wildcard characters, as in the example "C:\\*.txt", or by using the vertical pipe character (|) to separate multiple file names.</span></span> <span data-ttu-id="047f1-116">Все файлы должны иметь одинаковый формат данных.</span><span class="sxs-lookup"><span data-stu-id="047f1-116">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="047f1-117">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="047f1-117">**Browse**</span></span>  
 <span data-ttu-id="047f1-118">Просмотрите имена файлов для использования соединения с несколькими неструктурированными файлами.</span><span class="sxs-lookup"><span data-stu-id="047f1-118">Browse the file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="047f1-119">Можно выбрать несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="047f1-119">You can select multiple files.</span></span> <span data-ttu-id="047f1-120">Все файлы должны иметь одинаковый формат данных.</span><span class="sxs-lookup"><span data-stu-id="047f1-120">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="047f1-121">**Локаль**</span><span class="sxs-lookup"><span data-stu-id="047f1-121">**Locale**</span></span>  
 <span data-ttu-id="047f1-122">Укажите местоположение, чтобы дать необходимые сведения о порядке сортировки и преобразовании даты и времени.</span><span class="sxs-lookup"><span data-stu-id="047f1-122">Specify the location to provide information for ordering and for date and time conversion.</span></span>  
  
 <span data-ttu-id="047f1-123">**Юникод**</span><span class="sxs-lookup"><span data-stu-id="047f1-123">**Unicode**</span></span>  
 <span data-ttu-id="047f1-124">Укажите, следует ли использовать Юникод.</span><span class="sxs-lookup"><span data-stu-id="047f1-124">Indicate whether to use Unicode.</span></span> <span data-ttu-id="047f1-125">Использование Юникод исключает возможность указания кодовой страницы.</span><span class="sxs-lookup"><span data-stu-id="047f1-125">Using Unicode precludes specifying a code page.</span></span>  
  
 <span data-ttu-id="047f1-126">**Кодовая страница**</span><span class="sxs-lookup"><span data-stu-id="047f1-126">**Code page**</span></span>  
 <span data-ttu-id="047f1-127">Укажите кодовую страницу для текста не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="047f1-127">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="047f1-128">**Формат**</span><span class="sxs-lookup"><span data-stu-id="047f1-128">**Format**</span></span>  
 <span data-ttu-id="047f1-129">Укажите, будет ли использоваться форматирование с разделителями, с фиксированной шириной строк или без выравнивания по правому краю.</span><span class="sxs-lookup"><span data-stu-id="047f1-129">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span> <span data-ttu-id="047f1-130">Все файлы должны иметь одинаковый формат данных.</span><span class="sxs-lookup"><span data-stu-id="047f1-130">All files must have the same data format.</span></span>  
  
|<span data-ttu-id="047f1-131">Значение</span><span class="sxs-lookup"><span data-stu-id="047f1-131">Value</span></span>|<span data-ttu-id="047f1-132">Описание</span><span class="sxs-lookup"><span data-stu-id="047f1-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="047f1-133">С разделителями</span><span class="sxs-lookup"><span data-stu-id="047f1-133">Delimited</span></span>|<span data-ttu-id="047f1-134">Столбцы отделены друг от друга с помощью разделителей, указанных на странице **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="047f1-134">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="047f1-135">Фиксированная ширина</span><span class="sxs-lookup"><span data-stu-id="047f1-135">Fixed width</span></span>|<span data-ttu-id="047f1-136">Столбцы имеют фиксированную ширину, заданную перетаскиванием линий разметки на странице **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="047f1-136">Columns have a fixed width, specified by dragging marker lines on the **Columns** page.</span></span>|  
|<span data-ttu-id="047f1-137">Переменная ширина</span><span class="sxs-lookup"><span data-stu-id="047f1-137">Ragged right</span></span>|<span data-ttu-id="047f1-138">В файлах с неровным правым краем все столбцы имеют фиксированную ширину, кроме последнего. Последний столбец ограничен разделителем строк, заданным на странице **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="047f1-138">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter, specified on the **Columns** page.</span></span>|  
  
 <span data-ttu-id="047f1-139">**Ограничитель текста**</span><span class="sxs-lookup"><span data-stu-id="047f1-139">**Text qualifier**</span></span>  
 <span data-ttu-id="047f1-140">Укажите ограничитель текста, который следует использовать.</span><span class="sxs-lookup"><span data-stu-id="047f1-140">Specify the text qualifier to use.</span></span> <span data-ttu-id="047f1-141">Например, можно задать заключение текста в кавычки.</span><span class="sxs-lookup"><span data-stu-id="047f1-141">For example, you can specify to enclose text with quotation marks.</span></span>  
  
 <span data-ttu-id="047f1-142">**Разделитель строки заголовка**</span><span class="sxs-lookup"><span data-stu-id="047f1-142">**Header row delimiter**</span></span>  
 <span data-ttu-id="047f1-143">Выберите разделитель из списка разделителей строк заголовка или введите текст разделителя.</span><span class="sxs-lookup"><span data-stu-id="047f1-143">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="047f1-144">Значение</span><span class="sxs-lookup"><span data-stu-id="047f1-144">Value</span></span>|<span data-ttu-id="047f1-145">Описание</span><span class="sxs-lookup"><span data-stu-id="047f1-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="047f1-146">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="047f1-146">**{CR}{LF}**</span></span>|<span data-ttu-id="047f1-147">В качестве разделителей для строки заголовка используются сочетания символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="047f1-147">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="047f1-148">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="047f1-148">**{CR}**</span></span>|<span data-ttu-id="047f1-149">В качестве разделителей для строки заголовка используются символы возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="047f1-149">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="047f1-150">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="047f1-150">**{LF}**</span></span>|<span data-ttu-id="047f1-151">В качестве разделителей для строки заголовка используются символы перевода строки.</span><span class="sxs-lookup"><span data-stu-id="047f1-151">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="047f1-152">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="047f1-152">**Semicolon {;}**</span></span>|<span data-ttu-id="047f1-153">В качестве разделителя для строки заголовка используется точка с запятой.</span><span class="sxs-lookup"><span data-stu-id="047f1-153">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="047f1-154">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="047f1-154">**Colon {:}**</span></span>|<span data-ttu-id="047f1-155">В качестве разделителя для строки заголовка используется двоеточие.</span><span class="sxs-lookup"><span data-stu-id="047f1-155">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="047f1-156">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="047f1-156">**Comma {,}**</span></span>|<span data-ttu-id="047f1-157">В качестве разделителя для строки заголовка используется запятая.</span><span class="sxs-lookup"><span data-stu-id="047f1-157">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="047f1-158">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="047f1-158">**Tab {t}**</span></span>|<span data-ttu-id="047f1-159">В качестве разделителя для строки заголовка используется символ табуляции.</span><span class="sxs-lookup"><span data-stu-id="047f1-159">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="047f1-160">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="047f1-160">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="047f1-161">В качестве разделителя для строки заголовка используется вертикальная черта.</span><span class="sxs-lookup"><span data-stu-id="047f1-161">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="047f1-162">**Пропускаемые строки заголовка**</span><span class="sxs-lookup"><span data-stu-id="047f1-162">**Header rows to skip**</span></span>  
 <span data-ttu-id="047f1-163">Укажите число строк заголовка, которые нужно пропустить (если такие есть).</span><span class="sxs-lookup"><span data-stu-id="047f1-163">Specify the number of header rows to skip, if any.</span></span>  
  
 <span data-ttu-id="047f1-164">**Имена столбцов в первой строке данных**</span><span class="sxs-lookup"><span data-stu-id="047f1-164">**Column names in the first data row**</span></span>  
 <span data-ttu-id="047f1-165">Укажите, ожидать или задать имена столбцов в первой строке данных.</span><span class="sxs-lookup"><span data-stu-id="047f1-165">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047f1-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="047f1-166">See Also</span></span>  
 <span data-ttu-id="047f1-167">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="047f1-167">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="047f1-168">[Редактор диспетчера соединений с несколькими неструктурированными файлами &#40;страница столбцов&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="047f1-168">[Multiple Flat Files Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="047f1-169">[Редактор диспетчера соединений с несколькими неструктурированными файлами &#40;страница "Дополнительно"&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="047f1-169">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="047f1-170">Редактор диспетчера подключений с несколькими неструктурированными файлами (страница "Предварительный просмотр")</span><span class="sxs-lookup"><span data-stu-id="047f1-170">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
