---
title: Редактор источника "Неструктурированный файл" (страница "вывод ошибок") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.errorhandling.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: c50500e7-0c74-42a0-865f-301f03feffab
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 096de22c65d605fc1beea06cbb6ad5909788b408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655859"
---
# <a name="flat-file-source-editor-error-output-page"></a><span data-ttu-id="c0ad6-102">Редактор источника «Неструктурированный файл» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="c0ad6-102">Flat File Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="c0ad6-103">На странице **Вывод ошибок** диалогового окна **Редактор источника "Неструктурированный файл"** можно задать параметры обработки ошибок и определить свойства столбцов для вывода ошибок.</span><span class="sxs-lookup"><span data-stu-id="c0ad6-103">Use the **Error Output** page of the **Flat File Source Editor** dialog box to select error-handling options and to set properties on error output columns.\</span></span>  
  
 <span data-ttu-id="c0ad6-104">Дополнительные сведения об источнике «Неструктурированный файл» см. в разделе [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="c0ad6-104">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0ad6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0ad6-105">Options</span></span>  
 <span data-ttu-id="c0ad6-106">**Ввод-вывод**</span><span class="sxs-lookup"><span data-stu-id="c0ad6-106">**Input/Output**</span></span>  
 <span data-ttu-id="c0ad6-107">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="c0ad6-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="c0ad6-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c0ad6-108">**Column**</span></span>  
 <span data-ttu-id="c0ad6-109">Просмотрите внешние (исходные) столбцы, выбранные на странице **Диспетчер соединений** диалогового окна **Редактор источника "Неструктурированный файл"**.</span><span class="sxs-lookup"><span data-stu-id="c0ad6-109">View the external (source) columns that you selected on the **Connection Manager** page of the **Flat File Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="c0ad6-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="c0ad6-110">**Error**</span></span>  
 <span data-ttu-id="c0ad6-111">Задайте действие, которое необходимо выполнить при возникновении ошибки: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="c0ad6-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="c0ad6-112">**См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="c0ad6-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="c0ad6-113">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="c0ad6-113">**Truncation**</span></span>  
 <span data-ttu-id="c0ad6-114">Укажите, что нужно сделать при усечении: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="c0ad6-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="c0ad6-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c0ad6-115">**Description**</span></span>  
 <span data-ttu-id="c0ad6-116">Просмотреть описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="c0ad6-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="c0ad6-117">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="c0ad6-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="c0ad6-118">Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="c0ad6-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="c0ad6-119">**Применить**</span><span class="sxs-lookup"><span data-stu-id="c0ad6-119">**Apply**</span></span>  
 <span data-ttu-id="c0ad6-120">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="c0ad6-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ad6-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0ad6-121">See Also</span></span>  
 <span data-ttu-id="c0ad6-122">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c0ad6-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c0ad6-123">[Редактор источника "Неструктурированный файл" &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="c0ad6-123">[Flat File Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="c0ad6-124">[Редактор источника «Неструктурированный файл» &#40;столбцов&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="c0ad6-124">[Flat File Source Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="c0ad6-125">Диспетчер подключений неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="c0ad6-125">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
