---
title: Редактор преобразования «Экспорт столбца» (страница «Столбцы») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileextractortransformation.columns.f1
helpviewer_keywords:
- Export Column Transformation Editor
ms.assetid: b659a5c2-5509-4b5b-9c82-136c971d5c7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 404b404e2328228049ae46fb1c3089b0b4089f0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657835"
---
# <a name="export-column-transformation-editor-columns-page"></a><span data-ttu-id="8dec5-102">Редактор преобразования «Экспорт столбца» (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="8dec5-102">Export Column Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="8dec5-103">Страница **Столбцы** диалогового окна **Редактор преобразования «Экспорт столбца»** используется для задания столбцов в потоке данных, извлекаемых в файлы.</span><span class="sxs-lookup"><span data-stu-id="8dec5-103">Use the **Columns** page of the **Export Column Transformation Editor** dialog box to specify columns in the data flow to extract to files.</span></span> <span data-ttu-id="8dec5-104">Можно указать, будет ли преобразование «Экспорт столбца» добавлять данные в конец файла или перезаписывать существующий файл.</span><span class="sxs-lookup"><span data-stu-id="8dec5-104">You can specify whether the Export Column transformation appends data to a file or overwrites an existing file.</span></span>  
  
 <span data-ttu-id="8dec5-105">Дополнительные сведения о редакторе преобразований «Экспорт столбца» см. в разделе [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8dec5-105">To learn more about the Export Column transformation, see [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8dec5-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="8dec5-106">Options</span></span>  
 <span data-ttu-id="8dec5-107">**Извлечь столбец**</span><span class="sxs-lookup"><span data-stu-id="8dec5-107">**Extract Column**</span></span>  
 <span data-ttu-id="8dec5-108">Производится выбор из списка входных столбцов, содержащих текстовые данные или изображения.</span><span class="sxs-lookup"><span data-stu-id="8dec5-108">Select from the list of input columns that contain text or image data.</span></span> <span data-ttu-id="8dec5-109">Все строки должны иметь определения для параметров **Извлечь столбец** и **Столбец пути к файлу**.</span><span class="sxs-lookup"><span data-stu-id="8dec5-109">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="8dec5-110">**Столбец пути к файлу**</span><span class="sxs-lookup"><span data-stu-id="8dec5-110">**File Path Column**</span></span>  
 <span data-ttu-id="8dec5-111">Производится выбор из списка входных столбцов, содержащих пути к файлам и имена файлов.</span><span class="sxs-lookup"><span data-stu-id="8dec5-111">Select from the list of input columns that contain file paths and file names.</span></span> <span data-ttu-id="8dec5-112">Все строки должны иметь определения для параметров **Извлечь столбец** и **Столбец пути к файлу**.</span><span class="sxs-lookup"><span data-stu-id="8dec5-112">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="8dec5-113">**Разрешить добавление**</span><span class="sxs-lookup"><span data-stu-id="8dec5-113">**Allow Append**</span></span>  
 <span data-ttu-id="8dec5-114">Определяет, будет ли преобразование добавлять данные к существующим файлам.</span><span class="sxs-lookup"><span data-stu-id="8dec5-114">Specify whether the transformation appends data to existing files.</span></span> <span data-ttu-id="8dec5-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="8dec5-115">The default is `false`.</span></span>  
  
 <span data-ttu-id="8dec5-116">**Принудительное усечение**</span><span class="sxs-lookup"><span data-stu-id="8dec5-116">**Force Truncate**</span></span>  
 <span data-ttu-id="8dec5-117">Определяет, будет ли преобразование удалять содержимое существующих файлов перед записью данных.</span><span class="sxs-lookup"><span data-stu-id="8dec5-117">Specify whether the transformation deletes the contents of existing files before writing data.</span></span> <span data-ttu-id="8dec5-118">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="8dec5-118">The default is `false`.</span></span>  
  
 <span data-ttu-id="8dec5-119">**Запись BOM**</span><span class="sxs-lookup"><span data-stu-id="8dec5-119">**Write BOM**</span></span>  
 <span data-ttu-id="8dec5-120">Определяет, будет ли в файл записываться метка порядка следования байтов (BOM).</span><span class="sxs-lookup"><span data-stu-id="8dec5-120">Specify whether to write a byte-order mark (BOM) to the file.</span></span> <span data-ttu-id="8dec5-121">Метка BOM записывается только в случае, если данные имеют тип данных `DT_NTEXT` или DT_WSTR и не присоединяются к существующему файлу данных.</span><span class="sxs-lookup"><span data-stu-id="8dec5-121">A BOM is only written if the data has the `DT_NTEXT` or DT_WSTR data type and is not appended to an existing data file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dec5-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="8dec5-122">See Also</span></span>  
 <span data-ttu-id="8dec5-123">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8dec5-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="8dec5-124">Редактор преобразования "Экспорт столбца" (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="8dec5-124">Export Column Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/export-column-transformation-editor-error-output-page.md)  
  
  
