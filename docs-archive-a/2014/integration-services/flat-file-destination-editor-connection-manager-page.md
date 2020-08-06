---
title: Редактор назначения «Неструктурированный файл» (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledestadapter.connection.f1
helpviewer_keywords:
- Flat File Destination Editor
ms.assetid: b01571fa-bc19-4742-8eed-ac163172a919
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6997b72851c2b7bfc56445e6ddb01cfe6e9b04cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655864"
---
# <a name="flat-file-destination-editor-connection-manager-page"></a><span data-ttu-id="23d14-102">Редактор назначения «Неструктурированный файл» (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="23d14-102">Flat File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="23d14-103">Страница **Диспетчер соединений** диалогового окна **Редактор назначения «Неструктурированный файл»** используется для выбора соединения с неструктурированными файлами для назначения, а также для указания, следует ли переписывать существующий целевой файл или добавлять данные в его конец.</span><span class="sxs-lookup"><span data-stu-id="23d14-103">Use the **Connection Manager** page of the **Flat File Destination Editor** dialog box to select the flat file connection for the destination, and to specify whether to overwrite or append to the existing destination file.</span></span> <span data-ttu-id="23d14-104">С помощью назначения «Неструктурированный файл» данные записываются в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="23d14-104">The flat file destination writes data to a text file.</span></span> <span data-ttu-id="23d14-105">Текстовый файл может иметь формат с разделителями, формат фиксированной ширины, фиксированной ширины с разделителями строк или формат без выключки вправо.</span><span class="sxs-lookup"><span data-stu-id="23d14-105">This text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="23d14-106">Дополнительные сведения о назначении «Неструктурированный файл» см. в разделе [Flat File Destination](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="23d14-106">To learn more about the Flat File destination, see [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="23d14-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="23d14-107">Options</span></span>  
 <span data-ttu-id="23d14-108">**диспетчер соединений с неструктурированными файлами**</span><span class="sxs-lookup"><span data-stu-id="23d14-108">**Flat File connection manager**</span></span>  
 <span data-ttu-id="23d14-109">Выберите из списка существующий диспетчер соединений или создайте новое соединение, нажав **Создать**.</span><span class="sxs-lookup"><span data-stu-id="23d14-109">Select an existing connection manager by using the list box, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="23d14-110">**Создать**</span><span class="sxs-lookup"><span data-stu-id="23d14-110">**New**</span></span>  
 <span data-ttu-id="23d14-111">Создайте новое соединение с помощью диалоговых окон **Формат неструктурированного файла** и **Редактор диспетчера соединений с неструктурированными файлами** .</span><span class="sxs-lookup"><span data-stu-id="23d14-111">Create a new connection by using the **Flat File Format** and **Flat File Connection Manager Editor** dialog boxes.</span></span>  
  
 <span data-ttu-id="23d14-112">Кроме стандартных форматов неструктурированных файлов — с разделителями, с фиксированной шириной строк и без выравнивания по правому краю — диалоговое окно **Формат неструктурированного файла** содержит четвертый параметр **Фиксированная ширина с разделителями строк**.</span><span class="sxs-lookup"><span data-stu-id="23d14-112">In addition to the standard flat file formats of delimited, fixed width, and ragged right, the **Flat File Format** dialog box has a fourth option, **Fixed width with row delimiters**.</span></span> <span data-ttu-id="23d14-113">Этот параметр является особым случаем формата без выравнивания по правому краю, в котором в службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] добавляют фиктивный столбец в качестве итогового столбца данных.</span><span class="sxs-lookup"><span data-stu-id="23d14-113">This option represents a special case of the ragged-right format in which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] adds a dummy column as the final column of data.</span></span> <span data-ttu-id="23d14-114">Этот фиктивный столбец обеспечивает фиксированную ширину итогового столбца.</span><span class="sxs-lookup"><span data-stu-id="23d14-114">This dummy column ensures that the final column has a fixed width.</span></span>  
  
 <span data-ttu-id="23d14-115">Параметр **Фиксированная ширина с разделителями строк** не доступен в диалоговом окне **Редактор диспетчера соединений с неструктурированными файлами**.</span><span class="sxs-lookup"><span data-stu-id="23d14-115">The **Fixed width with row delimiters** option is not available in the **Flat File Connection Manager Editor**.</span></span> <span data-ttu-id="23d14-116">В случае необходимости можно смоделировать этот параметр в редакторе.</span><span class="sxs-lookup"><span data-stu-id="23d14-116">If necessary, you can emulate this option in the editor.</span></span> <span data-ttu-id="23d14-117">Чтобы смоделировать этот параметр, выберите **Без выравнивания по правому краю** в поле **Формат**страницы **Общие**диалогового окна **Редактор диспетчера соединений с неструктурированными файлами**.</span><span class="sxs-lookup"><span data-stu-id="23d14-117">To emulate this option, on the **General** page of the **Flat File Connection Manager Editor**, for **Format**, select **Ragged right**.</span></span> <span data-ttu-id="23d14-118">Затем в редакторе на странице **Дополнительно** добавьте новый фиктивный столбец в качестве итогового столбца данных.</span><span class="sxs-lookup"><span data-stu-id="23d14-118">Then on the **Advanced** page of the editor, add a new dummy column as the final column of data.</span></span>  
  
 <span data-ttu-id="23d14-119">**Перезаписать данные в файле**</span><span class="sxs-lookup"><span data-stu-id="23d14-119">**Overwrite data in the file**</span></span>  
 <span data-ttu-id="23d14-120">Указывает, нужно ли переписывать существующий файл или добавлять данные в его конец.</span><span class="sxs-lookup"><span data-stu-id="23d14-120">Indicate whether to overwrite an existing file, or to append data to it.</span></span>  
  
 <span data-ttu-id="23d14-121">**Верхняя часть**</span><span class="sxs-lookup"><span data-stu-id="23d14-121">**Header**</span></span>  
 <span data-ttu-id="23d14-122">Введите блок текста, вставляемый в файл перед записью данных.</span><span class="sxs-lookup"><span data-stu-id="23d14-122">Type a block of text to insert into the file before any data is written.</span></span> <span data-ttu-id="23d14-123">Используйте этот параметр, чтобы включить дополнительные данные, например заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="23d14-123">Use this option to include additional information, such as column headings.</span></span>  
  
 <span data-ttu-id="23d14-124">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="23d14-124">**Preview**</span></span>  
 <span data-ttu-id="23d14-125">Осуществляйте предварительный просмотр результатов в диалоговом окне **Просмотр данных** .</span><span class="sxs-lookup"><span data-stu-id="23d14-125">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="23d14-126">В окне «Предварительный просмотр» может отображаться до 200 строк.</span><span class="sxs-lookup"><span data-stu-id="23d14-126">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d14-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="23d14-127">See Also</span></span>  
 <span data-ttu-id="23d14-128">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="23d14-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="23d14-129">Редактор назначения "Неструктурированный файл" (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="23d14-129">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/flat-file-destination-editor-mappings-page.md)  
  
  
