---
title: Преобразование "Экспорт столбца" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exportcolumntrans.f1
helpviewer_keywords:
- exporting data
- append options [Integration Services]
- Export Column transformation [Integration Services]
- columns [Integration Services], exporting
- inserting data
- truncate options [Integration Services]
ms.assetid: 678d2dfc-e40c-4fbb-b2cc-42fffc44478a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7ed2bef02d75b72870514e2333d2fa58720fb60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656494"
---
# <a name="export-column-transformation"></a><span data-ttu-id="fd9c0-102">Преобразование «Экспорт столбца»</span><span class="sxs-lookup"><span data-stu-id="fd9c0-102">Export Column Transformation</span></span>
  <span data-ttu-id="fd9c0-103">Преобразование «Экспорт столбца» считывает данные из потока и вставляет их в файл.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-103">The Export Column transformation reads data in a data flow and inserts the data into a file.</span></span> <span data-ttu-id="fd9c0-104">Например, если поток данных содержит сведения о продукте, такие как изображения каждого продукта, можно применить преобразование «Экспорт столбца» для сохранения изображений в файлы.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-104">For example, if the data flow contains product information, such as a picture of each product, you could use the Export Column transformation to save the images to files.</span></span>  
  
## <a name="append-and-truncate-options"></a><span data-ttu-id="fd9c0-105">Параметры присоединения и усечения</span><span class="sxs-lookup"><span data-stu-id="fd9c0-105">Append and Truncate Options</span></span>  
 <span data-ttu-id="fd9c0-106">Следующая таблица описывает, как изменение настроек присоединения и усечения влияет на результаты.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-106">The following table describes how the settings for the append and truncate options affect results.</span></span>  
  
|<span data-ttu-id="fd9c0-107">Append</span><span class="sxs-lookup"><span data-stu-id="fd9c0-107">Append</span></span>|<span data-ttu-id="fd9c0-108">Truncate</span><span class="sxs-lookup"><span data-stu-id="fd9c0-108">Truncate</span></span>|<span data-ttu-id="fd9c0-109">Файл существует</span><span class="sxs-lookup"><span data-stu-id="fd9c0-109">File exists</span></span>|<span data-ttu-id="fd9c0-110">Результаты</span><span class="sxs-lookup"><span data-stu-id="fd9c0-110">Results</span></span>|  
|------------|--------------|-----------------|-------------|  
|<span data-ttu-id="fd9c0-111">False</span><span class="sxs-lookup"><span data-stu-id="fd9c0-111">False</span></span>|<span data-ttu-id="fd9c0-112">False</span><span class="sxs-lookup"><span data-stu-id="fd9c0-112">False</span></span>|<span data-ttu-id="fd9c0-113">нет</span><span class="sxs-lookup"><span data-stu-id="fd9c0-113">No</span></span>|<span data-ttu-id="fd9c0-114">Это преобразование создает новый файл и записывает в него данные.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-114">The transformation creates a new file and writes the data to the file.</span></span>|  
|<span data-ttu-id="fd9c0-115">True</span><span class="sxs-lookup"><span data-stu-id="fd9c0-115">True</span></span>|<span data-ttu-id="fd9c0-116">False</span><span class="sxs-lookup"><span data-stu-id="fd9c0-116">False</span></span>|<span data-ttu-id="fd9c0-117">нет</span><span class="sxs-lookup"><span data-stu-id="fd9c0-117">No</span></span>|<span data-ttu-id="fd9c0-118">Это преобразование создает новый файл и записывает в него данные.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-118">The transformation creates a new file and writes the data to the file.</span></span>|  
|<span data-ttu-id="fd9c0-119">False</span><span class="sxs-lookup"><span data-stu-id="fd9c0-119">False</span></span>|<span data-ttu-id="fd9c0-120">True</span><span class="sxs-lookup"><span data-stu-id="fd9c0-120">True</span></span>|<span data-ttu-id="fd9c0-121">нет</span><span class="sxs-lookup"><span data-stu-id="fd9c0-121">No</span></span>|<span data-ttu-id="fd9c0-122">Это преобразование создает новый файл и записывает в него данные.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-122">The transformation creates a new file and writes the data to the file.</span></span>|  
|<span data-ttu-id="fd9c0-123">True</span><span class="sxs-lookup"><span data-stu-id="fd9c0-123">True</span></span>|<span data-ttu-id="fd9c0-124">True</span><span class="sxs-lookup"><span data-stu-id="fd9c0-124">True</span></span>|<span data-ttu-id="fd9c0-125">нет</span><span class="sxs-lookup"><span data-stu-id="fd9c0-125">No</span></span>|<span data-ttu-id="fd9c0-126">Преобразованию не удается провести проверку времени разработки.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-126">The transformation fails design time validation.</span></span> <span data-ttu-id="fd9c0-127">Оба этих свойства не могут быть установлены для `true`.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-127">It is not valid to set both properties to `true`.</span></span>|  
|<span data-ttu-id="fd9c0-128">False</span><span class="sxs-lookup"><span data-stu-id="fd9c0-128">False</span></span>|<span data-ttu-id="fd9c0-129">False</span><span class="sxs-lookup"><span data-stu-id="fd9c0-129">False</span></span>|<span data-ttu-id="fd9c0-130">Да</span><span class="sxs-lookup"><span data-stu-id="fd9c0-130">Yes</span></span>|<span data-ttu-id="fd9c0-131">Возникает ошибка во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-131">A run-time error occurs.</span></span> <span data-ttu-id="fd9c0-132">Файл существует, но преобразование не имеет к нему доступа для записи.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-132">The file exists, but the transformation cannot write to it.</span></span>|  
|<span data-ttu-id="fd9c0-133">False</span><span class="sxs-lookup"><span data-stu-id="fd9c0-133">False</span></span>|<span data-ttu-id="fd9c0-134">True</span><span class="sxs-lookup"><span data-stu-id="fd9c0-134">True</span></span>|<span data-ttu-id="fd9c0-135">Да</span><span class="sxs-lookup"><span data-stu-id="fd9c0-135">Yes</span></span>|<span data-ttu-id="fd9c0-136">Преобразование удаляет файл, затем создает новый и записывает в него данные.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-136">The transformation deletes and re-creates the file and writes the data to the file.</span></span>|  
|<span data-ttu-id="fd9c0-137">True</span><span class="sxs-lookup"><span data-stu-id="fd9c0-137">True</span></span>|<span data-ttu-id="fd9c0-138">False</span><span class="sxs-lookup"><span data-stu-id="fd9c0-138">False</span></span>|<span data-ttu-id="fd9c0-139">Да</span><span class="sxs-lookup"><span data-stu-id="fd9c0-139">Yes</span></span>|<span data-ttu-id="fd9c0-140">Преобразование открывает файл и записывает данные в конец файла.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-140">The transformation opens the file and writes the data at the end of the file.</span></span>|  
|<span data-ttu-id="fd9c0-141">True</span><span class="sxs-lookup"><span data-stu-id="fd9c0-141">True</span></span>|<span data-ttu-id="fd9c0-142">True</span><span class="sxs-lookup"><span data-stu-id="fd9c0-142">True</span></span>|<span data-ttu-id="fd9c0-143">Да</span><span class="sxs-lookup"><span data-stu-id="fd9c0-143">Yes</span></span>|<span data-ttu-id="fd9c0-144">Преобразованию не удается провести проверку времени разработки.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-144">The transformation fails design time validation.</span></span> <span data-ttu-id="fd9c0-145">Оба этих свойства не могут быть установлены для `true`.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-145">It is not valid to set both properties to `true`.</span></span>|  
  
## <a name="configuration-of-the-export-column-transformation"></a><span data-ttu-id="fd9c0-146">Настройка преобразования «Экспорт столбца»</span><span class="sxs-lookup"><span data-stu-id="fd9c0-146">Configuration of the Export Column Transformation</span></span>  
 <span data-ttu-id="fd9c0-147">Можно настроить преобразование «Экспорт столбца» следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fd9c0-147">You can configure the Export Column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="fd9c0-148">Обозначьте столбцы данных и столбцы, содержащие путь к файлам, в которые будут записаны данные.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-148">Specify the data columns and the columns that contain the path of files to which to write the data.</span></span>  
  
-   <span data-ttu-id="fd9c0-149">Обозначьте, следует ли операции вставки данных перезаписывать файлы или дописывать к ним.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-149">Specify whether the data-insertion operation appends or truncates existing files.</span></span>  
  
-   <span data-ttu-id="fd9c0-150">Укажите, будет ли записана в файл отметка порядка байтов (BOM).</span><span class="sxs-lookup"><span data-stu-id="fd9c0-150">Specify whether a byte-order mark (BOM) is written to the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fd9c0-151">Отметка порядка байтов будет записана только в том случае, если данные не были добавлены в конец уже существующего файла и если эти данные типа DT_NTEXT.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-151">A BOM is written only when the data is not appended to an existing file and the data has the DT_NTEXT data type.</span></span>  
  
 <span data-ttu-id="fd9c0-152">Преобразование использует пару входных столбцов: первый содержит имя файла, второй — данные.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-152">The transformation uses pairs of input columns: One column contains a file name, and the other column contains data.</span></span> <span data-ttu-id="fd9c0-153">Каждая строка в наборе данных может указывать отдельный файл.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-153">Each row in the data set can specify a different file.</span></span> <span data-ttu-id="fd9c0-154">По мере обработки строк преобразованием данные записываются в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-154">As the transformation processes a row, the data is inserted into the specified file.</span></span> <span data-ttu-id="fd9c0-155">Во время выполнения преобразование создает файлы, если они до этого не существовали, и записывает в них данные.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-155">At run time, the transformation creates the files, if they do not already exist, and then the transformation writes the data to the files.</span></span> <span data-ttu-id="fd9c0-156">Записываемые данные должны иметь тип DT_TEXT, DT_NTEXT или DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-156">The data to be written must have a DT_TEXT, DT_NTEXT, or DT_IMAGE data type.</span></span> <span data-ttu-id="fd9c0-157">Дополнительные сведения см. в разделе [Integration Services Data Types](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fd9c0-157">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="fd9c0-158">Это преобразование имеет один вход, один выход и один выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-158">This transformation has one input, one output, and one error output.</span></span>  
  
 <span data-ttu-id="fd9c0-159">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-159">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="fd9c0-160">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования "Экспорт столбца"**, см. в разделе [Редактор преобразования "Экспорт столбца" (страница "Столбцы")](../../export-column-transformation-editor-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="fd9c0-160">For more information about the properties that you can set in the **Export Column Transformation Editor** dialog box, see [Export Column Transformation Editor &#40;Columns Page&#41;](../../export-column-transformation-editor-columns-page.md).</span></span>  
  
 <span data-ttu-id="fd9c0-161">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-161">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="fd9c0-162">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="fd9c0-162">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fd9c0-163">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="fd9c0-163">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="fd9c0-164">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="fd9c0-164">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="fd9c0-165">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="fd9c0-165">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
