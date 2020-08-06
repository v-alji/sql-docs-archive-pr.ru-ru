---
title: Редактор источника «XML» (страница «вывод ошибок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmlsourceadapter.erroroutput.f1
helpviewer_keywords:
- XML Source Editor
ms.assetid: 2ddb97c2-1e43-478f-8872-b6efd41b931e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4842442ca798c53c9b5352491959a62314a3cd73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736491"
---
# <a name="xml-source-editor-error-output-page"></a><span data-ttu-id="e54c0-102">Редактор источника «XML» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="e54c0-102">XML Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="e54c0-103">Используйте страницу **Вывод ошибок** диалогового окна **Редактор источника «XML»** для выбора параметров обработки ошибок и задания свойств выходных столбцов ошибок.</span><span class="sxs-lookup"><span data-stu-id="e54c0-103">Use the **Error Output** page of the **XML Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="e54c0-104">Дополнительные сведения об источнике XML см. в разделе [XML Source](data-flow/xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="e54c0-104">For more information about the XML source, see [XML Source](data-flow/xml-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e54c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e54c0-105">Options</span></span>  
 <span data-ttu-id="e54c0-106">**Ввод-вывод**</span><span class="sxs-lookup"><span data-stu-id="e54c0-106">**Input/Output**</span></span>  
 <span data-ttu-id="e54c0-107">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="e54c0-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="e54c0-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e54c0-108">**Column**</span></span>  
 <span data-ttu-id="e54c0-109">Просмотрите внешние (исходные) столбцы, выбранные на странице **Диспетчер соединений** диалогового окна **Редактор источника "XML"**.</span><span class="sxs-lookup"><span data-stu-id="e54c0-109">View the external (source) columns that you selected on the **Connection Manager** page of the **XML Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="e54c0-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="e54c0-110">**Error**</span></span>  
 <span data-ttu-id="e54c0-111">Задайте действие, которое необходимо выполнить при возникновении ошибки: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="e54c0-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="e54c0-112">**См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="e54c0-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="e54c0-113">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="e54c0-113">**Truncation**</span></span>  
 <span data-ttu-id="e54c0-114">Укажите, что нужно сделать при усечении: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="e54c0-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="e54c0-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e54c0-115">**Description**</span></span>  
 <span data-ttu-id="e54c0-116">Просмотреть описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="e54c0-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="e54c0-117">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="e54c0-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="e54c0-118">Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="e54c0-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="e54c0-119">**Применить**</span><span class="sxs-lookup"><span data-stu-id="e54c0-119">**Apply**</span></span>  
 <span data-ttu-id="e54c0-120">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="e54c0-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54c0-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="e54c0-121">See Also</span></span>  
 <span data-ttu-id="e54c0-122">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e54c0-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e54c0-123">[Редактор источника "XML" &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/xml-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="e54c0-123">[XML Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/xml-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="e54c0-124">[Редактор источника "XML" &#40;столбцы "&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="e54c0-124">[XML Source Editor &#40;Columns Page&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="e54c0-125">Извлечение данных с помощью XML-источника</span><span class="sxs-lookup"><span data-stu-id="e54c0-125">Extract Data by Using the XML Source</span></span>](data-flow/extract-data-by-using-the-xml-source.md)  
  
  
