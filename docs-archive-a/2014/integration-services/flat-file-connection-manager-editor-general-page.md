---
title: Редактор диспетчера соединений с неструктурированными файлами (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.general.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 77296024-5c1a-4f6a-9665-0b50d45d744c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 478c7bcf56e300b47af93862bf66409a3c94b5f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655869"
---
# <a name="flat-file-connection-manager-editor-general-page"></a><span data-ttu-id="6e166-102">Редактор диспетчера соединений с неструктурированными файлами (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="6e166-102">Flat File Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="6e166-103">Используйте страницу **Общие** диалогового окна **Редактор диспетчера соединений с неструктурированными файлами** , чтобы выбрать файл и формат данных.</span><span class="sxs-lookup"><span data-stu-id="6e166-103">Use the **General** page of the **Flat File Connection Manager Editor** dialog box to select a file and data format.</span></span> <span data-ttu-id="6e166-104">Соединение с неструктурированным файлом дает пакету возможность установить соединение с текстовым файлом.</span><span class="sxs-lookup"><span data-stu-id="6e166-104">A flat file connection enables a package to connect to a text file.</span></span>  
  
 <span data-ttu-id="6e166-105">Дополнительные сведения о диспетчере соединений с неструктурированными файлами см. в разделе [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6e166-105">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6e166-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e166-106">Options</span></span>  
 <span data-ttu-id="6e166-107">**Имя диспетчера подключений**</span><span class="sxs-lookup"><span data-stu-id="6e166-107">**Connection manager name**</span></span>  
 <span data-ttu-id="6e166-108">Укажите уникальное имя для соединения с неструктурированным файлом в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="6e166-108">Provide a unique name for the flat file connection in the workflow.</span></span> <span data-ttu-id="6e166-109">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e166-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="6e166-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6e166-110">**Description**</span></span>  
 <span data-ttu-id="6e166-111">Опишите соединение.</span><span class="sxs-lookup"><span data-stu-id="6e166-111">Describe the connection.</span></span> <span data-ttu-id="6e166-112">Рекомендуется описать цель соединения, чтобы пакеты самодокументировались и их проще было обслуживать.</span><span class="sxs-lookup"><span data-stu-id="6e166-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="6e166-113">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="6e166-113">**File name**</span></span>  
 <span data-ttu-id="6e166-114">Введите путь и имя файла для использования в соединении с неструктурированным файлом.</span><span class="sxs-lookup"><span data-stu-id="6e166-114">Type the path and file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="6e166-115">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="6e166-115">**Browse**</span></span>  
 <span data-ttu-id="6e166-116">Укажите имя файла для использования в соединении с неструктурированным файлом.</span><span class="sxs-lookup"><span data-stu-id="6e166-116">Locate the file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="6e166-117">**Локаль**</span><span class="sxs-lookup"><span data-stu-id="6e166-117">**Locale**</span></span>  
 <span data-ttu-id="6e166-118">Укажите локаль, чтобы предоставить определяемые языком правила для сортировки данных и формата даты и времени.</span><span class="sxs-lookup"><span data-stu-id="6e166-118">Specify the locale to provide language-specific information for ordering and for date and time formats.</span></span>  
  
 <span data-ttu-id="6e166-119">**Юникод**</span><span class="sxs-lookup"><span data-stu-id="6e166-119">**Unicode**</span></span>  
 <span data-ttu-id="6e166-120">Укажите, следует ли использовать Юникод.</span><span class="sxs-lookup"><span data-stu-id="6e166-120">Indicate whether to use Unicode.</span></span> <span data-ttu-id="6e166-121">При использовании Юникод невозможно указать кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="6e166-121">If you use Unicode, you cannot specify a code page.</span></span>  
  
 <span data-ttu-id="6e166-122">**Кодовая страница**</span><span class="sxs-lookup"><span data-stu-id="6e166-122">**Code page**</span></span>  
 <span data-ttu-id="6e166-123">Укажите кодовую страницу для текста не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="6e166-123">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="6e166-124">**Формат**</span><span class="sxs-lookup"><span data-stu-id="6e166-124">**Format**</span></span>  
 <span data-ttu-id="6e166-125">Укажите, используется ли в файле форматирование с разделителями, с фиксированной шириной столбцов или форматирование без ограничения длины строк.</span><span class="sxs-lookup"><span data-stu-id="6e166-125">Indicate whether the file uses delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="6e166-126">Значение</span><span class="sxs-lookup"><span data-stu-id="6e166-126">Value</span></span>|<span data-ttu-id="6e166-127">Описание</span><span class="sxs-lookup"><span data-stu-id="6e166-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e166-128">С разделителями</span><span class="sxs-lookup"><span data-stu-id="6e166-128">Delimited</span></span>|<span data-ttu-id="6e166-129">Столбцы отделены друг от друга с помощью разделителей, указанных на странице **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="6e166-129">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="6e166-130">Фиксированная ширина</span><span class="sxs-lookup"><span data-stu-id="6e166-130">Fixed width</span></span>|<span data-ttu-id="6e166-131">Столбцы имеют фиксированную ширину.</span><span class="sxs-lookup"><span data-stu-id="6e166-131">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="6e166-132">Переменная ширина</span><span class="sxs-lookup"><span data-stu-id="6e166-132">Ragged right</span></span>|<span data-ttu-id="6e166-133">В файлах с текстом без выравнивания вправо каждый столбец имеет фиксированную ширину, за исключением последнего столбца.</span><span class="sxs-lookup"><span data-stu-id="6e166-133">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="6e166-134">Он отделяется разделителем строк.</span><span class="sxs-lookup"><span data-stu-id="6e166-134">It is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="6e166-135">**Ограничитель текста**</span><span class="sxs-lookup"><span data-stu-id="6e166-135">**Text qualifier**</span></span>  
 <span data-ttu-id="6e166-136">Укажите ограничитель текста, который следует использовать.</span><span class="sxs-lookup"><span data-stu-id="6e166-136">Specify the text qualifier to use.</span></span> <span data-ttu-id="6e166-137">Например, можно указать, что текстовые поля должны быть заключены в кавычки.</span><span class="sxs-lookup"><span data-stu-id="6e166-137">For example, you can specify that text fields are enclosed in quotation marks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e166-138">После выбора ограничителя текста невозможно повторно выбрать параметр **None** .</span><span class="sxs-lookup"><span data-stu-id="6e166-138">After you select a text qualifier, you cannot re-select the **None** option.</span></span> <span data-ttu-id="6e166-139">Тип **None** предназначен для отмены выбора ограничителя текста.</span><span class="sxs-lookup"><span data-stu-id="6e166-139">Type **None** to de-select the text qualifier.</span></span>  
  
 <span data-ttu-id="6e166-140">**Разделитель строки заголовка**</span><span class="sxs-lookup"><span data-stu-id="6e166-140">**Header row delimiter**</span></span>  
 <span data-ttu-id="6e166-141">Выберите разделитель из списка разделителей строк заголовка или введите текст разделителя.</span><span class="sxs-lookup"><span data-stu-id="6e166-141">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="6e166-142">Значение</span><span class="sxs-lookup"><span data-stu-id="6e166-142">Value</span></span>|<span data-ttu-id="6e166-143">Описание</span><span class="sxs-lookup"><span data-stu-id="6e166-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e166-144">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="6e166-144">**{CR}{LF}**</span></span>|<span data-ttu-id="6e166-145">В качестве разделителей для строки заголовка используются сочетания символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="6e166-145">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="6e166-146">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="6e166-146">**{CR}**</span></span>|<span data-ttu-id="6e166-147">В качестве разделителей для строки заголовка используются символы возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="6e166-147">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="6e166-148">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="6e166-148">**{LF}**</span></span>|<span data-ttu-id="6e166-149">В качестве разделителей для строки заголовка используются символы перевода строки.</span><span class="sxs-lookup"><span data-stu-id="6e166-149">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="6e166-150">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="6e166-150">**Semicolon {;}**</span></span>|<span data-ttu-id="6e166-151">В качестве разделителя для строки заголовка используется точка с запятой.</span><span class="sxs-lookup"><span data-stu-id="6e166-151">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="6e166-152">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="6e166-152">**Colon {:}**</span></span>|<span data-ttu-id="6e166-153">В качестве разделителя для строки заголовка используется двоеточие.</span><span class="sxs-lookup"><span data-stu-id="6e166-153">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="6e166-154">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="6e166-154">**Comma {,}**</span></span>|<span data-ttu-id="6e166-155">В качестве разделителя для строки заголовка используется запятая.</span><span class="sxs-lookup"><span data-stu-id="6e166-155">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="6e166-156">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="6e166-156">**Tab {t}**</span></span>|<span data-ttu-id="6e166-157">В качестве разделителя для строки заголовка используется символ табуляции.</span><span class="sxs-lookup"><span data-stu-id="6e166-157">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="6e166-158">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="6e166-158">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="6e166-159">В качестве разделителя для строки заголовка используется вертикальная черта.</span><span class="sxs-lookup"><span data-stu-id="6e166-159">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="6e166-160">**Пропускаемые строки заголовка**</span><span class="sxs-lookup"><span data-stu-id="6e166-160">**Header rows to skip**</span></span>  
 <span data-ttu-id="6e166-161">Укажите количество строк заголовка или строк начальных данных, которые следует пропускать при необходимости.</span><span class="sxs-lookup"><span data-stu-id="6e166-161">Specify the number of header rows or initial data rows to skip, if any.</span></span>  
  
 <span data-ttu-id="6e166-162">**Имена столбцов в первой строке данных**</span><span class="sxs-lookup"><span data-stu-id="6e166-162">**Column names in the first data row**</span></span>  
 <span data-ttu-id="6e166-163">Укажите, ожидать или задать имена столбцов в первой строке данных.</span><span class="sxs-lookup"><span data-stu-id="6e166-163">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e166-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e166-164">See Also</span></span>  
 <span data-ttu-id="6e166-165">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6e166-165">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6e166-166">[Редактор диспетчера соединений с неструктурированными файлами &#40;столбцы&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="6e166-166">[Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="6e166-167">[Редактор диспетчера соединений с неструктурированными файлами &#40;страница "Дополнительно"&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="6e166-167">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="6e166-168">Редактор диспетчера подключений с неструктурированными файлами (страница "Предварительный просмотр")</span><span class="sxs-lookup"><span data-stu-id="6e166-168">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
