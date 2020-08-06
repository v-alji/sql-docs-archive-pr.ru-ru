---
title: Редактор источника "Неструктурированный файл" (страница "Диспетчер соединений") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.connection.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: 2efd6baa-ed75-4f3f-b667-514024cebdb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03c1693c001dad2c8e90211b065eda208c42a07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655857"
---
# <a name="flat-file-source-editor-connection-manager-page"></a><span data-ttu-id="cc09d-102">Редактор источника «Неструктурированный файл» (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="cc09d-102">Flat File Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="cc09d-103">Для выбора диспетчера соединений, который будет использоваться источником «Неструктурированный файл», используется страница **Диспетчер соединений** диалогового окна **Редактор источника «Неструктурированный файл»** .</span><span class="sxs-lookup"><span data-stu-id="cc09d-103">Use the **Connection Manager** page of the **Flat File Source Editor** dialog box to select the connection manager that the Flat File source will use.</span></span> <span data-ttu-id="cc09d-104">Источник «Неструктурированный файл» считывает данные из текстового файла, который может содержать разделители, поля фиксированной ширины или иметь смешанный формат.</span><span class="sxs-lookup"><span data-stu-id="cc09d-104">The Flat File source reads data from a text file, which can be in a delimited, fixed width, or mixed format.</span></span>  
  
 <span data-ttu-id="cc09d-105">Источник «Неструктурированный файл» может использовать один из следующих типов диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="cc09d-105">A Flat File source can use one of the following types of connection managers:</span></span>  
  
-   <span data-ttu-id="cc09d-106">Диспетчер соединений с неструктурированными файлами, если источник является отдельным неструктурированным файлом.</span><span class="sxs-lookup"><span data-stu-id="cc09d-106">A Flat File connection manager if the source is a single flat file.</span></span> <span data-ttu-id="cc09d-107">Дополнительные сведения см. в статье [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cc09d-107">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
-   <span data-ttu-id="cc09d-108">Диспетчер соединения с несколькими неструктурированными файлами, если источник представлен несколькими неструктурированными файлами и задачей потока данных внутри контейнера цикла (например, контейнера «цикл по элементам»).</span><span class="sxs-lookup"><span data-stu-id="cc09d-108">A Multiple Flat Files connection manager if the source is multiple flat files and the Data Flow task is inside a loop container, such as the For Loop container.</span></span> <span data-ttu-id="cc09d-109">В каждом цикле контейнера источник неструктированных файлов загружает данные из следующего имени файла, которое предоставляет диспетчер соединения с несколькими неструктурированными файлами.</span><span class="sxs-lookup"><span data-stu-id="cc09d-109">On each loop of the container, the Flat File source loads data from the next file name that the Multiple Flat Files connection manager provides.</span></span> <span data-ttu-id="cc09d-110">Дополнительные сведения см. в разделе [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cc09d-110">For more information, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
 <span data-ttu-id="cc09d-111">Дополнительные сведения об источнике «Неструктурированный файл» см. в разделе [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="cc09d-111">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cc09d-112">Варианты</span><span class="sxs-lookup"><span data-stu-id="cc09d-112">Options</span></span>  
 <span data-ttu-id="cc09d-113">**Диспетчер соединений с неструктурированными файлами**</span><span class="sxs-lookup"><span data-stu-id="cc09d-113">**Flat file connection manager**</span></span>  
 <span data-ttu-id="cc09d-114">Выберите существующий диспетчер соединений из списка или создайте новый диспетчер соединений, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="cc09d-114">Select an existing connection manager from the list, or create a new connection manager by clicking **New**.</span></span>  
  
 <span data-ttu-id="cc09d-115">**Создать**</span><span class="sxs-lookup"><span data-stu-id="cc09d-115">**New**</span></span>  
 <span data-ttu-id="cc09d-116">Создайте новый диспетчер соединений с помощью диалогового окна **Редактор диспетчера соединений с неструктурированными файлами** .</span><span class="sxs-lookup"><span data-stu-id="cc09d-116">Create a new connection manager by using the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="cc09d-117">**Оставлять значения NULL из источника в потоке данных**</span><span class="sxs-lookup"><span data-stu-id="cc09d-117">**Retain null values from the source as null values in the data flow**</span></span>  
 <span data-ttu-id="cc09d-118">Укажите, нужно ли сохранять значения NULL при извлечении данных.</span><span class="sxs-lookup"><span data-stu-id="cc09d-118">Specify whether to keep null values when data is extracted.</span></span> <span data-ttu-id="cc09d-119">Значение по умолчанию этого свойства равно **false**.</span><span class="sxs-lookup"><span data-stu-id="cc09d-119">The default value of this property is **false**.</span></span> <span data-ttu-id="cc09d-120">Когда значение равно f`alse`, источник неструктурированных файлов заменяет значения NULL из данных источника соответствующими значениями по умолчанию для каждого столбца, например пустыми строками для строковых столбцов и нулями для числовых столбцов.</span><span class="sxs-lookup"><span data-stu-id="cc09d-120">When this value is f`alse`, the Flat File source replaces null values from the source data with appropriate default values for each column, such as empty strings for string columns and zero for numeric columns.</span></span>  
  
 <span data-ttu-id="cc09d-121">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="cc09d-121">**Preview**</span></span>  
 <span data-ttu-id="cc09d-122">Осуществляйте предварительный просмотр результатов в диалоговом окне **Просмотр данных** .</span><span class="sxs-lookup"><span data-stu-id="cc09d-122">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="cc09d-123">В окне «Предварительный просмотр» может отображаться до 200 строк.</span><span class="sxs-lookup"><span data-stu-id="cc09d-123">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc09d-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="cc09d-124">See Also</span></span>  
 <span data-ttu-id="cc09d-125">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cc09d-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="cc09d-126">[Редактор источника «Неструктурированный файл» &#40;столбцов&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="cc09d-126">[Flat File Source Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="cc09d-127">[Редактор источника "Неструктурированный файл" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="cc09d-127">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="cc09d-128">Диспетчер подключений неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="cc09d-128">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
