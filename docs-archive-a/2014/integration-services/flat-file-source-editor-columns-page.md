---
title: Редактор источника "Неструктурированный файл" (страница "столбцы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.columns.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: b5af5f65-c087-44fd-b5ae-d0441245fef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9b0249b2b17d50fdef4b5cf4aff70a1318614257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655861"
---
# <a name="flat-file-source-editor-columns-page"></a><span data-ttu-id="004d8-102">Редактор источника «Неструктурированный файл» (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="004d8-102">Flat File Source Editor (Columns Page)</span></span>
  <span data-ttu-id="004d8-103">С помощью узла **Столбцы** диалогового окна **Редактор источника "Неструктурированный файл"** можно сопоставлять выходной столбец с каждым внешним (исходным) столбцом.</span><span class="sxs-lookup"><span data-stu-id="004d8-103">Use the **Columns** node of the **Flat File Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="004d8-104">`FileNameColumnName`Свойство источника "Неструктурированный файл" и `FastParse` свойство его выходных столбцов недоступны в **редакторе источника "Неструктурированный файл**", но могут быть заданы с помощью **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="004d8-104">The `FileNameColumnName` property of the Flat File source and the `FastParse` property of its output columns are not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="004d8-105">Дополнительные сведения об этих свойствах см. в подразделе «Источник "Неструктурированный файл"» раздела [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="004d8-105">For more information on these properties, see the Flat File Source section of [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="004d8-106">Дополнительные сведения об источнике «Неструктурированный файл» см. в разделе [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="004d8-106">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="004d8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="004d8-107">Options</span></span>  
 <span data-ttu-id="004d8-108">**Доступные внешние столбцы**</span><span class="sxs-lookup"><span data-stu-id="004d8-108">**Available External Columns**</span></span>  
 <span data-ttu-id="004d8-109">Просмотр списка доступных внешних столбцов источника данных.</span><span class="sxs-lookup"><span data-stu-id="004d8-109">View the list of available external columns in the data source.</span></span> <span data-ttu-id="004d8-110">В этой таблице нельзя добавлять или удалять столбцы.</span><span class="sxs-lookup"><span data-stu-id="004d8-110">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="004d8-111">**Внешний столбец**</span><span class="sxs-lookup"><span data-stu-id="004d8-111">**External Column**</span></span>  
 <span data-ttu-id="004d8-112">Просмотр внешних (исходных) столбцов в том порядке, в котором их будет считывать задача.</span><span class="sxs-lookup"><span data-stu-id="004d8-112">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="004d8-113">Этот порядок можно изменить, вначале очистив выделенные столбцы в таблице, а затем выбрав в списке внешние столбцы в другом порядке.</span><span class="sxs-lookup"><span data-stu-id="004d8-113">You can change this order by first clearing the selected columns in the table, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="004d8-114">**Выходной столбец**</span><span class="sxs-lookup"><span data-stu-id="004d8-114">**Output Column**</span></span>  
 <span data-ttu-id="004d8-115">Введите уникальное имя для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="004d8-115">Provide a unique name for each output column.</span></span> <span data-ttu-id="004d8-116">По умолчанию используется имя выбранного внешнего (исходного) столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="004d8-116">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="004d8-117">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="004d8-117">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="004d8-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="004d8-118">See Also</span></span>  
 <span data-ttu-id="004d8-119">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="004d8-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="004d8-120">[Редактор источника "Неструктурированный файл" &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="004d8-120">[Flat File Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="004d8-121">[Редактор источника "Неструктурированный файл" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="004d8-121">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="004d8-122">Диспетчер подключений неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="004d8-122">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
