---
title: Источник "Неструктурированный файл" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Flat File
- text file reading [Integration Services]
- flat files
- Flat File source
ms.assetid: 4a64f7f3-f25d-4db0-93b3-a29496030e58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b1ca0f38c457256b3f2ed2ddb81bfbd0dc06b6c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751315"
---
# <a name="flat-file-source"></a><span data-ttu-id="f2e78-102">источник «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="f2e78-102">Flat File Source</span></span>
  <span data-ttu-id="f2e78-103">Источник «Неструктурированный файл» считывает данные из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="f2e78-103">The Flat File source reads data from a text file.</span></span> <span data-ttu-id="f2e78-104">Текстовый файл может иметь разделители, фиксированную ширину полей или смешанный формат.</span><span class="sxs-lookup"><span data-stu-id="f2e78-104">The text file can be in delimited, fixed width, or mixed format.</span></span>  
  
-   <span data-ttu-id="f2e78-105">В формате с разделителями для выделения столбцов и строк используются разделители столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="f2e78-105">Delimited format uses column and row delimiters to define columns and rows.</span></span>  
  
-   <span data-ttu-id="f2e78-106">В формате с фиксированной шириной для определения столбцов и строк используются параметры ширины.</span><span class="sxs-lookup"><span data-stu-id="f2e78-106">Fixed width format uses width to define columns and rows.</span></span> <span data-ttu-id="f2e78-107">Этот формат также включает символ для заполнения поля до его максимальной ширины.</span><span class="sxs-lookup"><span data-stu-id="f2e78-107">This format also includes a character for padding fields to their maximum width.</span></span>  
  
-   <span data-ttu-id="f2e78-108">В формате без выравнивания справа для выделения всех столбцов, кроме последнего, используются параметры ширины; для последнего столбца используется разделитель строк.</span><span class="sxs-lookup"><span data-stu-id="f2e78-108">Ragged right format uses width to define all columns, except for the last column, which is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="f2e78-109">Источник «Неструктурированный файл» можно настроить следующими способами.</span><span class="sxs-lookup"><span data-stu-id="f2e78-109">You can configure the Flat File source in the following ways:</span></span>  
  
-   <span data-ttu-id="f2e78-110">Добавьте к выходу преобразования столбец, содержащий имя текстового файла, из которого источник «Неструктурированный файл» извлекает данные.</span><span class="sxs-lookup"><span data-stu-id="f2e78-110">Add a column to the transformation output that contains the name of the text file from which the Flat File source extracts data.</span></span>  
  
-   <span data-ttu-id="f2e78-111">Укажите, распознает ли источник «Неструктурированный файл» строки с нулевой длиной в столбцах как значения NULL.</span><span class="sxs-lookup"><span data-stu-id="f2e78-111">Specify whether the Flat File source interprets zero-length strings in columns as null values.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2e78-112">Диспетчер соединений с неструктурированными файлами, используемый источником «Неструктурированный файл», должен быть настроен для использования формата с разделителями, чтобы распознавать строки с нулевой длиной как NULL.</span><span class="sxs-lookup"><span data-stu-id="f2e78-112">The Flat File connection manager that the Flat File source uses must be configured to use a delimited format to interpret zero-length strings as nulls.</span></span> <span data-ttu-id="f2e78-113">Если диспетчер соединений использует форматы фиксированной ширины или форматы без выравнивания справа, то данные, состоящие из пробелов, не могут быть представлены как значения NULL.</span><span class="sxs-lookup"><span data-stu-id="f2e78-113">If the connection manager uses the fixed width or ragged right formats, data that consists of spaces cannot be interpreted as null values.</span></span>  
  
 <span data-ttu-id="f2e78-114">Выходные столбцы на выходе источника "Неструктурированный файл" содержат свойство Flat File.</span><span class="sxs-lookup"><span data-stu-id="f2e78-114">The output columns in the output of the Flat File source include the FastParse property.</span></span> <span data-ttu-id="f2e78-115">Значение свойства Flat File показывает, использует ли столбец более быстрые, но не зависящие от локали процедуры ускоренного синтаксического анализа, предоставляемые службами [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , или стандартные процедуры, зависящие от локали.</span><span class="sxs-lookup"><span data-stu-id="f2e78-115">FastParse indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="f2e78-116">Дополнительные сведения см. в разделах [Fast Parse](../fast-parse.md) и [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="f2e78-116">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span>  
  
 <span data-ttu-id="f2e78-117">Выходные столбцы также содержат свойство UseBinaryFormat.</span><span class="sxs-lookup"><span data-stu-id="f2e78-117">Output columns also include the UseBinaryFormat property.</span></span> <span data-ttu-id="f2e78-118">Используйте это свойство для реализации поддержки двоичных данных, таких как данные с упакованным десятичным форматом, в файлах.</span><span class="sxs-lookup"><span data-stu-id="f2e78-118">You use this property to implement support for binary data, such as data with the packed decimal format, in files.</span></span> <span data-ttu-id="f2e78-119">По умолчанию Усебинариформат имеет значение `false` .</span><span class="sxs-lookup"><span data-stu-id="f2e78-119">By default UseBinaryFormat is set to `false`.</span></span> <span data-ttu-id="f2e78-120">Если вы хотите использовать двоичный формат, задайте для параметра Усебинариформат значение `true` , а для типа данных выходного столбца — `DT_BYTES` .</span><span class="sxs-lookup"><span data-stu-id="f2e78-120">If you want to use a binary format, set UseBinaryFormat to `true` and the data type on the output column to `DT_BYTES`.</span></span> <span data-ttu-id="f2e78-121">После этого источник «Неструктурированный файл» будет пропускать преобразование данных и выводить данные в выходные столбцы в первоначальном виде.</span><span class="sxs-lookup"><span data-stu-id="f2e78-121">When you do this, the Flat File source skips the data conversion and passes the data to the output column as is.</span></span> <span data-ttu-id="f2e78-122">Затем можно использовать такое преобразование, как «Производный столбец» или «Конвертация данных», чтобы привести данные типа `DT_BYTES` к другим типам данных, или можно создать пользовательский скрипт в преобразовании «Скрипт» для интерпретации данных.</span><span class="sxs-lookup"><span data-stu-id="f2e78-122">You can then use a transformation such as the Derived Column or Data Conversion to cast the `DT_BYTES` data to a different data type, or you can write custom script in a Script transformation to interpret the data.</span></span> <span data-ttu-id="f2e78-123">Также для интерпретации данных можно создать пользовательский компонент потока данных.</span><span class="sxs-lookup"><span data-stu-id="f2e78-123">You can also write a custom data flow component to interpret the data.</span></span> <span data-ttu-id="f2e78-124">Дополнительные сведения о типах данных, которые можно привести `DT_BYTES` к, см. в разделе [cast &#40;&#41;выражений служб SSIS ](../expressions/cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f2e78-124">For more information about which data types you can cast `DT_BYTES` to, see [Cast &#40;SSIS Expression&#41;](../expressions/cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="f2e78-125">Этот источник использует диспетчер соединений с неструктурированными файлами, чтобы получить доступ к текстовому файлу.</span><span class="sxs-lookup"><span data-stu-id="f2e78-125">This source uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="f2e78-126">Установка свойств для диспетчера соединений с неструктурированными файлами позволяет предоставить сведения о файле и о каждом из его столбцов, а также обозначить то, как источник «Неструктурированный файл» должен обрабатывать данные текстового файла.</span><span class="sxs-lookup"><span data-stu-id="f2e78-126">By setting properties on the Flat File connection manager, you can provide information about the file and each column in it, and specify how the Flat File source should handle the data in the text file.</span></span> <span data-ttu-id="f2e78-127">Например, можно определить символы-разделители для столбцов и строк в файле, тип данных и длину каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="f2e78-127">For example, you can specify the characters that delimit columns and rows in the file, and the data type and the length of each column.</span></span> <span data-ttu-id="f2e78-128">Дополнительные сведения см. в статье [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f2e78-128">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="f2e78-129">Данный источник содержит один выход и один выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="f2e78-129">This source has one output and one error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-source"></a><span data-ttu-id="f2e78-130">Настройка источника «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="f2e78-130">Configuration of the Flat File Source</span></span>  
 <span data-ttu-id="f2e78-131">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="f2e78-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f2e78-132">Дополнительные сведения о свойствах, которые можно задать в диалоговом окне **Редактор источника «Неструктурированный файл»** , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f2e78-132">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f2e78-133">Редактор источника "Неструктурированный файл" (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="f2e78-133">Flat File Source Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="f2e78-134">Редактор источника "Неструктурированный файл" (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="f2e78-134">Flat File Source Editor &#40;Columns Page&#41;</span></span>](../flat-file-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="f2e78-135">Редактор источника "Неструктурированный файл" (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="f2e78-135">Flat File Source Editor &#40;Error Output Page&#41;</span></span>](../flat-file-source-editor-error-output-page.md)  
  
 <span data-ttu-id="f2e78-136">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="f2e78-136">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="f2e78-137">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f2e78-137">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f2e78-138">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="f2e78-138">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="f2e78-139">Пользовательские свойства неструктурированного файла</span><span class="sxs-lookup"><span data-stu-id="f2e78-139">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="f2e78-140">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f2e78-140">Related Tasks</span></span>  
 <span data-ttu-id="f2e78-141">Дополнительные сведения о настройке свойств для компонента потока данных см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="f2e78-141">For details about how to set properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e78-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2e78-142">See Also</span></span>  
 <span data-ttu-id="f2e78-143">[Назначение «Неструктурированный файл»](flat-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="f2e78-143">[Flat File Destination](flat-file-destination.md) </span></span>  
 [<span data-ttu-id="f2e78-144">Поток данных</span><span class="sxs-lookup"><span data-stu-id="f2e78-144">Data Flow</span></span>](data-flow.md)  
  
  
