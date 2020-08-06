---
title: Редактор преобразования «Экспорт столбца» (страница «вывод ошибок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileextractortransformation.errorhandling.f1
helpviewer_keywords:
- Export Column Transformation Editor
ms.assetid: 260be463-01a9-460c-9c98-e5265cb2b1e9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 04a9c277bb4aaa28933d443bd12e6c2b39ed844e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752288"
---
# <a name="export-column-transformation-editor-error-output-page"></a><span data-ttu-id="11770-102">Редактор преобразования «Экспорт столбца» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="11770-102">Export Column Transformation Editor (Error Output Page)</span></span>
  <span data-ttu-id="11770-103">Используйте страницу **Вывод ошибок** диалогового окна **Редактор преобразования «Экспорт столбца»** , чтобы задать способ обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="11770-103">Use the **Error Output** page of the **Export Column Transformation Editor** dialog box to specify how to handle errors.</span></span>  
  
 <span data-ttu-id="11770-104">Дополнительные сведения о редакторе преобразований «Экспорт столбца» см. в разделе [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="11770-104">To learn more about the Export Column transformation, see [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="11770-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11770-105">Options</span></span>  
 <span data-ttu-id="11770-106">**Ввод-вывод**</span><span class="sxs-lookup"><span data-stu-id="11770-106">**Input/Output**</span></span>  
 <span data-ttu-id="11770-107">Просмотр имени вывода.</span><span class="sxs-lookup"><span data-stu-id="11770-107">View the name of the output.</span></span> <span data-ttu-id="11770-108">Щелкните имя, чтобы развернуть представление и отобразить столбцы.</span><span class="sxs-lookup"><span data-stu-id="11770-108">Click the name to expand the view to include columns.</span></span>  
  
 <span data-ttu-id="11770-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="11770-109">**Column**</span></span>  
 <span data-ttu-id="11770-110">Просмотрите выходные столбцы, выбранные на странице **Столбцы** диалогового окна **Редактор преобразования "Экспорт столбца"** .</span><span class="sxs-lookup"><span data-stu-id="11770-110">View the output columns that you selected on the **Columns** page of the **Export Column Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="11770-111">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="11770-111">**Error**</span></span>  
 <span data-ttu-id="11770-112">Задайте событие при возникновении ошибки: пропустить ошибку, перенаправить строку или завершить компонент с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="11770-112">Specify what you want to happen if an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="11770-113">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="11770-113">**Truncation**</span></span>  
 <span data-ttu-id="11770-114">Задайте событие при усечении: пропустить ошибку, перенаправить строку или завершить компонент с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="11770-114">Specify what you want to happen if a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="11770-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="11770-115">**Description**</span></span>  
 <span data-ttu-id="11770-116">Просмотрите описание операции.</span><span class="sxs-lookup"><span data-stu-id="11770-116">View the description of the operation.</span></span>  
  
 <span data-ttu-id="11770-117">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="11770-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="11770-118">Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="11770-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="11770-119">**Применить**</span><span class="sxs-lookup"><span data-stu-id="11770-119">**Apply**</span></span>  
 <span data-ttu-id="11770-120">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="11770-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11770-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="11770-121">See Also</span></span>  
 <span data-ttu-id="11770-122">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="11770-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="11770-123">Редактор преобразования "Экспорт столбца" (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="11770-123">Export Column Transformation Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/export-column-transformation-editor-columns-page.md)  
  
  
