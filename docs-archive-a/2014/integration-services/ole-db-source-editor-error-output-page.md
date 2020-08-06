---
title: Редактор источника OLE DB (страница «вывод ошибок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.errorhandling.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 7737c6ae-c16b-4856-aa6e-5882640093b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ded87747f041a4d8451048d4ef4671b029125873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667808"
---
# <a name="ole-db-source-editor-error-output-page"></a><span data-ttu-id="28882-102">Редактор источника «OLE DB» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="28882-102">OLE DB Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="28882-103">Используйте страницу **Вывод ошибок** диалогового окна **Редактор источника «OLE DB»** , чтобы выбрать параметры обработки ошибок и установить свойства столбцов вывода ошибок.</span><span class="sxs-lookup"><span data-stu-id="28882-103">Use the **Error Output** page of the **OLE DB Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="28882-104">Дополнительные сведения об источнике OLE DB см. в разделе [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="28882-104">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="28882-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="28882-105">Options</span></span>  
 <span data-ttu-id="28882-106">**Ввод-вывод**</span><span class="sxs-lookup"><span data-stu-id="28882-106">**Input/Output**</span></span>  
 <span data-ttu-id="28882-107">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="28882-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="28882-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="28882-108">**Column**</span></span>  
 <span data-ttu-id="28882-109">Просмотрите внешние (исходные) столбцы, выбранные на странице **Диспетчер соединений** диалогового окна **Редактор источника "OLE DB"** .</span><span class="sxs-lookup"><span data-stu-id="28882-109">View the external (source) columns that you selected on the **Connection Manager** page of the **OLE DB Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="28882-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="28882-110">**Error**</span></span>  
 <span data-ttu-id="28882-111">Задайте действие, которое необходимо выполнить при возникновении ошибки: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="28882-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="28882-112">**См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="28882-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="28882-113">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="28882-113">**Truncation**</span></span>  
 <span data-ttu-id="28882-114">Укажите, что нужно сделать при усечении: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="28882-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="28882-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28882-115">**Description**</span></span>  
 <span data-ttu-id="28882-116">Просмотреть описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="28882-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="28882-117">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="28882-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="28882-118">Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="28882-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="28882-119">**Применить**</span><span class="sxs-lookup"><span data-stu-id="28882-119">**Apply**</span></span>  
 <span data-ttu-id="28882-120">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="28882-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28882-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="28882-121">See Also</span></span>  
 <span data-ttu-id="28882-122">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="28882-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="28882-123">[Редактор OLE DBного источника &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="28882-123">[OLE DB Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="28882-124">[Страница "&#40;столбцов" редактора источника OLE DB&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="28882-124">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="28882-125">[Извлечение данных с помощью источника OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="28882-125">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="28882-126">Диспетчер соединений OLE DB</span><span class="sxs-lookup"><span data-stu-id="28882-126">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
