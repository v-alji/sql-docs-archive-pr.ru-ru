---
title: Редактор диспетчера соединений с Excel | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelconnection.f1
helpviewer_keywords:
- Excel Connection Manager Editor
ms.assetid: 7ff097e4-cafb-4885-a898-05b2a46628c1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f66de13b710e5ccb577e6f2d67c215572e34767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665020"
---
# <a name="excel-connection-manager-editor"></a><span data-ttu-id="48bf5-102">редактор диспетчера соединений с Excel</span><span class="sxs-lookup"><span data-stu-id="48bf5-102">Excel Connection Manager Editor</span></span>
  <span data-ttu-id="48bf5-103">Диалоговое окно **Редактор диспетчера соединений с Excel** используется для добавления подключения к существующему или новому файлу книги [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48bf5-103">Use the **Excel Connection Manager Editor** dialog box to add a connection to an existing or a new [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook file.</span></span>  
  
 <span data-ttu-id="48bf5-104">Дополнительные сведения о диспетчере соединений с Excel см. в разделе [Диспетчер соединений с Excel](connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="48bf5-104">To learn more about the Excel connection manager, see [Excel Connection Manager](connection-manager/excel-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48bf5-105">Подключить защищенный паролем файл Excel нельзя.</span><span class="sxs-lookup"><span data-stu-id="48bf5-105">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="options"></a><span data-ttu-id="48bf5-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="48bf5-106">Options</span></span>  
 <span data-ttu-id="48bf5-107">**Путь к файлу Excel**</span><span class="sxs-lookup"><span data-stu-id="48bf5-107">**Excel file path**</span></span>  
 <span data-ttu-id="48bf5-108">Введите путь и имя существующего или нового файла книги Excel с расширением XLS.</span><span class="sxs-lookup"><span data-stu-id="48bf5-108">Type the path and file name of an existing or a new Excel workbook file (.xls).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="48bf5-109">**Редактор назначения «Excel** » автоматически создает файл Excel при выборе **подключения Excel** , указывающего на новый или несуществующий файл, а затем нажмите кнопку **создать** для **имени листа Excel**.</span><span class="sxs-lookup"><span data-stu-id="48bf5-109">The **Excel Destination Editor** automatically creates the Excel file when you select an **Excel Connection** that points to a new/non-existent file and then click **New** for **Name of the Excel Sheet**.</span></span>  
  
 <span data-ttu-id="48bf5-110">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="48bf5-110">**Browse**</span></span>  
 <span data-ttu-id="48bf5-111">Используйте диалоговое окно **Открыть** , чтобы перейти в папку, в которой находится файл Excel, или в место, где нужно создать новый файл.</span><span class="sxs-lookup"><span data-stu-id="48bf5-111">Use the **Open** dialog box to navigate to the folder in which the excel file exists or where you want to create the new file.</span></span>  
  
 <span data-ttu-id="48bf5-112">**Версия Excel**</span><span class="sxs-lookup"><span data-stu-id="48bf5-112">**Excel version**</span></span>  
 <span data-ttu-id="48bf5-113">Позволяет указать версию Microsoft Excel, в которой был создан файл.</span><span class="sxs-lookup"><span data-stu-id="48bf5-113">Specify the version of Microsoft Excel that was used to create the file.</span></span>  
  
|<span data-ttu-id="48bf5-114">Параметр</span><span class="sxs-lookup"><span data-stu-id="48bf5-114">Option</span></span>|<span data-ttu-id="48bf5-115">Описание</span><span class="sxs-lookup"><span data-stu-id="48bf5-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="48bf5-116">Excel 97-2003</span><span class="sxs-lookup"><span data-stu-id="48bf5-116">Excel 97-2003</span></span>|<span data-ttu-id="48bf5-117">Файл был создан с помощью Excel 97 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="48bf5-117">File was created using Excel 97 or later.</span></span>|  
|<span data-ttu-id="48bf5-118">Excel 3,0</span><span class="sxs-lookup"><span data-stu-id="48bf5-118">Excel 3.0</span></span>|<span data-ttu-id="48bf5-119">Файл был создан с помощью Excel 3,0.</span><span class="sxs-lookup"><span data-stu-id="48bf5-119">File was created using Excel 3.0.</span></span>|  
|<span data-ttu-id="48bf5-120">Excel 4,0</span><span class="sxs-lookup"><span data-stu-id="48bf5-120">Excel 4.0</span></span>|<span data-ttu-id="48bf5-121">Файл был создан с помощью Excel 4.0.</span><span class="sxs-lookup"><span data-stu-id="48bf5-121">File was created using Excel 4.0.</span></span>|  
|<span data-ttu-id="48bf5-122">Excel 5,0</span><span class="sxs-lookup"><span data-stu-id="48bf5-122">Excel 5.0</span></span>|<span data-ttu-id="48bf5-123">Файл был создан с помощью Excel 95 (7.0).</span><span class="sxs-lookup"><span data-stu-id="48bf5-123">File was created using Excel 95 (7.0).</span></span>|  
  
 <span data-ttu-id="48bf5-124">**Первая строка содержит имена столбцов**</span><span class="sxs-lookup"><span data-stu-id="48bf5-124">**First row has column names**</span></span>  
 <span data-ttu-id="48bf5-125">Позволяет указать, содержит ли первая строка данных выбранного листа имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="48bf5-125">Specify whether the first row of data in the selected worksheet contains column names.</span></span> <span data-ttu-id="48bf5-126">По умолчанию значение этого параметра равно **True**.</span><span class="sxs-lookup"><span data-stu-id="48bf5-126">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48bf5-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="48bf5-127">See Also</span></span>  
 <span data-ttu-id="48bf5-128">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="48bf5-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="48bf5-129">Просмотр файлов и таблиц Excel с помощью контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="48bf5-129">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
