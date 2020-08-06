---
title: Редактор назначения «Excel» (страница «вывод ошибок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldestadapter.erroroutput.f1
helpviewer_keywords:
- Excel Destination Editor
ms.assetid: 72ae01cc-1774-4a36-9674-a0f2b2bf8c42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bee679f563105cade3053a13eb122f6d482a7d86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665018"
---
# <a name="excel-destination-editor-error-output-page"></a><span data-ttu-id="6c2c3-102">Редактор назначения «Excel» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="6c2c3-102">Excel Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="6c2c3-103">Используйте страницу **Дополнительно** диалогового окна **Редактор назначения «Excel»** , чтобы указать параметры обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="6c2c3-103">Use the **Advanced** page of the **Excel Destination Editor** dialog box to specify options for error handling.</span></span>  
  
 <span data-ttu-id="6c2c3-104">Дополнительные сведения о назначении Excel см. в разделе [Excel Destination](data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="6c2c3-104">To learn more about the Excel destination, see [Excel Destination](data-flow/excel-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6c2c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c2c3-105">Options</span></span>  
 <span data-ttu-id="6c2c3-106">**Вход или выход**</span><span class="sxs-lookup"><span data-stu-id="6c2c3-106">**Input or Output**</span></span>  
 <span data-ttu-id="6c2c3-107">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="6c2c3-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="6c2c3-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6c2c3-108">**Column**</span></span>  
 <span data-ttu-id="6c2c3-109">Просмотрите внешние (исходные) столбцы, выбранные в разделе **Диспетчер соединений** диалогового окна **Редактор источника "Excel"**.</span><span class="sxs-lookup"><span data-stu-id="6c2c3-109">View the external (source) columns that you selected in the **Connection Manager** node of the **Excel Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="6c2c3-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="6c2c3-110">**Error**</span></span>  
 <span data-ttu-id="6c2c3-111">Задайте действие, которое необходимо выполнить при возникновении ошибки: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="6c2c3-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="6c2c3-112">**См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="6c2c3-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="6c2c3-113">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="6c2c3-113">**Truncation**</span></span>  
 <span data-ttu-id="6c2c3-114">Укажите, что нужно сделать при усечении: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="6c2c3-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="6c2c3-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6c2c3-115">**Description**</span></span>  
 <span data-ttu-id="6c2c3-116">Просмотреть описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="6c2c3-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="6c2c3-117">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="6c2c3-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="6c2c3-118">Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="6c2c3-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="6c2c3-119">**Применить**</span><span class="sxs-lookup"><span data-stu-id="6c2c3-119">**Apply**</span></span>  
 <span data-ttu-id="6c2c3-120">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="6c2c3-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2c3-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c2c3-121">See Also</span></span>  
 <span data-ttu-id="6c2c3-122">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6c2c3-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6c2c3-123">[Редактор назначения "Excel" &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/excel-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="6c2c3-123">[Excel Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="6c2c3-124">[Редактор назначения "Excel" &#40;страниц сопоставления&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="6c2c3-124">[Excel Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="6c2c3-125">Просмотр файлов и таблиц Excel с помощью контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="6c2c3-125">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
