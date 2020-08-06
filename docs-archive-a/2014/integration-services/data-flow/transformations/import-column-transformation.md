---
title: Преобразование "Импорт столбца" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.importcolumntrans.f1
helpviewer_keywords:
- Import Column transformation [Integration Services]
- columns [Integration Services], importing
- importing data, SSIS packages
- inserting data
ms.assetid: ac3b74c1-ef54-4297-8062-1734324fffcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4330438614cce7892e74dc9a1dcbb6680b72972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667319"
---
# <a name="import-column-transformation"></a><span data-ttu-id="ca204-102">Преобразование «Импорт столбца»</span><span class="sxs-lookup"><span data-stu-id="ca204-102">Import Column Transformation</span></span>
  <span data-ttu-id="ca204-103">Преобразование «Импорт столбца» считывает данные из файлов и добавляет данные в столбцы потока данных.</span><span class="sxs-lookup"><span data-stu-id="ca204-103">The Import Column transformation reads data from files and adds the data to columns in a data flow.</span></span> <span data-ttu-id="ca204-104">С помощью этого преобразования пакет может добавлять в поток данных текст и изображения, хранимые в отдельных файлах.</span><span class="sxs-lookup"><span data-stu-id="ca204-104">Using this transformation, a package can add text and images stored in separate files to a data flow.</span></span> <span data-ttu-id="ca204-105">Например, поток данных, загружающий данные в таблицу сведений о продуктах, может содержать преобразование «Импорт столбца», чтобы выполнять импорт отзывов покупателей о каждом продукте из файлов и добавлять обзоры в поток данных.</span><span class="sxs-lookup"><span data-stu-id="ca204-105">For example, a data flow that loads data into a table that stores product information can include the Import Column transformation to import customer reviews of each product from files and add the reviews to the data flow.</span></span>  
  
 <span data-ttu-id="ca204-106">Можно настроить преобразование «Импорт столбца» следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ca204-106">You can configure the Import Column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="ca204-107">Укажите столбцы, в которые преобразование добавляет данные.</span><span class="sxs-lookup"><span data-stu-id="ca204-107">Specify the columns to which the transformation adds data.</span></span>  
  
-   <span data-ttu-id="ca204-108">Укажите, ожидает ли преобразование отметку порядка байтов (BOM).</span><span class="sxs-lookup"><span data-stu-id="ca204-108">Specify whether the transformation expects a byte-order mark (BOM).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca204-109">Отметка порядка байтов предполагается, только если данные принадлежат к типу данных DT_NTEXT.</span><span class="sxs-lookup"><span data-stu-id="ca204-109">A BOM is only expected if the data has the DT_NTEXT data type.</span></span>  
  
 <span data-ttu-id="ca204-110">Столбец входа преобразования содержит имена файлов, в которых хранятся данные.</span><span class="sxs-lookup"><span data-stu-id="ca204-110">A column in the transformation input contains the names of files that hold the data.</span></span> <span data-ttu-id="ca204-111">Каждая строка в наборе данных может указывать на отдельный файл.</span><span class="sxs-lookup"><span data-stu-id="ca204-111">Each row in the dataset can specify a different file.</span></span> <span data-ttu-id="ca204-112">Когда преобразование «Импорт столбца» обрабатывает строку, оно считывает имя файла, открывает соответствующий файл в файловой системе и загружает содержимое файла в выходной столбец.</span><span class="sxs-lookup"><span data-stu-id="ca204-112">When the Import Column transformation processes a row, it reads the file name, opens the corresponding file in the file system, and loads the file content into an output column.</span></span> <span data-ttu-id="ca204-113">Тип данных выходного столбца должен быть DT_TEXT, DT_NTEXT или DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="ca204-113">The data type of the output column must be DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span> <span data-ttu-id="ca204-114">Дополнительные сведения см. в разделе [Integration Services Data Types](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ca204-114">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="ca204-115">Это преобразование имеет один вход, один выход и один выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="ca204-115">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="configuration-of-the-import-column-transformation"></a><span data-ttu-id="ca204-116">Настройка преобразования «Импорт столбца»</span><span class="sxs-lookup"><span data-stu-id="ca204-116">Configuration of the Import Column Transformation</span></span>  
 <span data-ttu-id="ca204-117">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="ca204-117">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ca204-118">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="ca204-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="ca204-119">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ca204-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ca204-120">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="ca204-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="ca204-121">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="ca204-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="ca204-122">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="ca204-122">Related Tasks</span></span>  
 <span data-ttu-id="ca204-123">Дополнительные сведения о настройке свойств компонента см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ca204-123">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca204-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca204-124">See Also</span></span>  
 <span data-ttu-id="ca204-125">[Преобразование «Экспорт столбца»](export-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ca204-125">[Export Column Transformation](export-column-transformation.md) </span></span>  
 <span data-ttu-id="ca204-126">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="ca204-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="ca204-127">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="ca204-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
